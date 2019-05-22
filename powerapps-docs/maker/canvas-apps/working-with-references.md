---
title: Forstå posten referanser og polymorfisk oppslag | Microsoft Docs
description: Arbeide med post-referanser og polymorfisk oppslag i lerret-apper
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 05/17/2019
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 80755667a9c7c36eb47999f7f8b2f939eb032c69
ms.sourcegitcommit: 93096dfa1aadba77159db1e5922f3d5528eecb7a
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 05/21/2019
ms.locfileid: "65986440"
---
# <a name="understand-record-references-and-polymorphic-lookups-in-canvas-apps"></a>Forstå posten referanser og polymorfisk oppslag i lerret-apper

Når du har skrevet en forskningsrapport på skolen, inkludert du sannsynligvis en liste over dine referanser på slutten. Du ikke tok med en kopi av det faktiske bakgrunn materialet du bruker, men i stedet en webkobling, boken tittel og forfatter eller annen informasjon slik at noen kan spore den opprinnelige kilden. Du har ulike typer kilder i en enkelt liste, avis artikler ved siden av lydopptak, hver med sine egne spesifikke detaljer for et riktig sitat. For eksempel Wikipedia artikler inneholder ofte en [lang liste med referanser](https://en.wikipedia.org/wiki/Microsoft#References).

Lerretsapper kan arbeider du ofte med kopier av poster som skal hentes fra datakilder. Du bruker den [ **oppslag** ](functions/function-filter-lookup.md) og [ **Filter** ](functions/function-filter-lookup.md) funksjoner og [ **galleriet** ](controls/control-gallery.md) kontrollens **valgt** til å identifisere bestemte posten du vil bruke. Alle postene fra **Filter** eller **valgt** vil være av samme enhetstype, slik at du kan bruke felt med en enkel. *Feltet* notasjon. Disse kopiene inneholder ofte referanseinformasjon slik at du kan bruke den [ **Patch** ](functions/function-patch.md) funksjonen for å oppdatere den opprinnelige kilden.

Lerret-apper støtter også *registrere referanser*. Mye som en forskningsrapport referanse refererer en postreferanse til en post uten å inkludere en fullstendig kopi av den. Slike en referanse kan referere til en post i en hvilken som helst enhet. Som forskningsrapport referanser, kan du også blande poster fra ulike enheter i en enkelt kolonne.

Mange operasjoner på post-referanser er identisk med å arbeide med poster. Du kan sammenligne posten referanser til hverandre og til full poster. Du kan angi verdien for en post referanse med den **Patch** fungere slik du ville gjøre et oppslag med en fullstendig post.

Det er en viktig Bruk forskjell: du har ikke direkte tilgang til feltene i en postreferanse uten først å opprette den refererer til hvilken enhet. Dette er fordi lerret-apper krever at alle typer være kjent når du skriver formler. Fordi du ikke kjenner typen for en referanse til appen kjører, kan du ikke bruke enkle. *Feltet* notasjon direkte. Du må først dynamisk bestemme hvilken enhet med den [ **IsType** ](functions/function-astype-istype.md) fungere og bruk deretter. *Feltet* notasjon på resultatet av den [ **AsType** ](functions/function-astype-istype.md) funksjonen.

*Enhetstypen* refererer til skjemaet for hver post i en enhet. Hver enhet har et unikt sett med felt med forskjellige kolonnenavnene og datatypene. Hver post i enheten arver denne strukturen. to poster har den samme enhetstypen hvis de kommer fra samme enhet.

## <a name="polymorphic-lookups"></a>Polymorfisk oppslag

Common Data Service støtter relasjoner mellom poster. Hver post i den **kontoer** enheten har en **hovedkontakt** oppslagsfelt til en post i den **kontakter** enhet. Oppslaget kan bare referere til en post i **kontakter** og kan ikke referere til en post i, si, den **Teams** enhet. At siste detaljer er viktig fordi du alltid vet hvilke felt vil være tilgjengelig for oppslaget.

Common Data Service støtter også polymorfisk oppslag, som kan referere til en post fra en hvilken som helst enhet i et sett. For eksempel den **eieren** felt kan referere til en post i den **brukere** enhet eller **Teams** enhet. Samme oppslagsfeltet i forskjellige poster kan referere til poster i ulike enheter. I dette tilfellet kan du alltid ikke vet hva felt vil være tilgjengelig.

Lerretet posten referanser ble utformet for å arbeide med polymorfisk oppslag i Common Data Service. Du kan også bruke posten referanser utenfor denne konteksten, som er hvordan de to konseptene seg.

I neste del, du begynner å utforske disse konseptene ved å arbeide med den **eieren** oppslag.

## <a name="show-the-fields-of-a-record-owner"></a>Vis feltene for eieren av en post

Hver enhet i Common Data Service inkluderer en **eieren** felt. Dette feltet kan ikke fjernes, du kan ikke legge til en annen, og den krever alltid en verdi.

Å vise dette feltet i den **kontoen** enhet:

1. Åpne [dette PowerApps-området](http://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc).
1. I navigasjonsfeltet til venstre velger du **Data** > **enheter**.
1. I listen over enheter, velger du **kontoen**.
1. Åpne filter-listen i hjørnet øverst til høyre (som er angitt **standard** som standard), og velg deretter **alle**.
1. Bla ned til den **eieren** feltet vises.

 > [!div class="mx-imgBorder"]
 > ![Eier-feltet på konto-enhet](media/working-with-references/owner-field.png)

Dette oppslagsfeltet kan referere til en post fra enten den **Teams** enhet eller **brukere** enhet. Ikke alle postene i disse enhetene har tillatelse til å være en **eieren**; Kontroller støttede rollene hvis det oppstår et problem.

Dette bildet viser et enkelt galleri med **kontoer**, der den **kontoer** enheten har blitt lagt til appen som en datakilde:

> [!div class="mx-imgBorder"]
> ![Kontoer som vises i en gallerikontroll](media/working-with-references/accounts-gallery.png)

> [!IMPORTANT]
> I dette emnet viser grafikken noen navn og andre verdier som ikke er en del av eksempeldata som leveres med Common Data Service. Trinnene demonstrerer nøyaktig hvordan du konfigurerer kontroller for et bestemt resultat, men opplevelsen din vil variere avhengig av dataene for organisasjonen din.

Hvis du vil vise eieren av hver konto i galleriet, kan du bli fristet til å bruke formelen **ThisItem.Owner.Name**. Imidlertid Navn-feltet i den **Team** enheten er **lagnavnet**, og Navn-feltet i den **bruker** enheten er **fullt navn**. Appen kan ikke vet hvilken type oppslag du arbeider med frem til du kjøre appen, og den kan variere mellom poster i den **kontoer** enhet.

Du trenger en formel som kan tilpasses til denne variasjonen. Du må også legge til datakildene enheten typer som **eieren** kan være (i dette tilfellet **brukere** og **Teams**). Legg til disse tre datakilder i appen:

> [!div class="mx-imgBorder"]
> ![Kontoer, grupper og brukere enheter i Data-ruten](media/working-with-references/accounts-datasources.png)

Kilder i plassere, bruke denne formelen til å vise navnet på en bruker eller et team med disse dataene:

```powerapps-dot
If( IsType( ThisItem.Owner, [@Teams] ),
    "Team: " & AsType( ThisItem.Owner, [@Teams] ).'Team Name',
    "User: " & AsType( ThisItem.Owner, [@Users] ).'Full Name' )
```

> [!div class="mx-imgBorder"]
> ![Kontoer som vises i en gallerikontroll med eier-feltet vises](media/working-with-references/accounts-displayowner.png)

I denne formelen den **IsType** funksjonen tester den **eieren** feltet mot den **Teams** enhet. Hvis det er for enheten den **AsType** funksjonen konverteringstypen den til en **Team** post. Du har nå tilgang til alle feltene til den **Teams** enhet, inkludert **lagnavnet**, ved hjelp av den *. Feltet* notasjon. Hvis **IsType** bestemmer som den **eieren** er ikke en post i den **Teams** enhet, dette feltet må være en post i den **brukere** enheten fordi den **eieren** feltet er obligatorisk (kan ikke være *tom*).

Du bruker den [globale tvetydighetsoperatoren](functions/operators.md#disambiguation-operator) for **[@Teams]** og **[@Users]** å sikre at du bruker den globale enhetstypen. Du trenger ikke den i dette tilfellet, men det er en god vane til skjemaet. Én-til-mange-relasjoner konflikt ofte i galleriets postomfang, og denne øvelsen unngår denne forvirring.

Hvis du vil bruke en hvilken som helst felt for en postreferanse, må du først bruke den **AsType** funksjonen til å bruke den til en bestemt enhet-type. Du får ikke tilgang til felt direkte fra den **eieren** feltet fordi systemet ikke vet hvilke enhetstypen du vil bruke.

Den **AsType** -funksjonen returnerer en feil hvis den **eieren** felt, samsvarer ikke med enheten blir forespurt, slik at du kan bruke den **IfError** funksjonen til å forenkle denne formelen. Først aktivere funksjonen for eksperimentell **Feiladministrasjon på formelnivå**:

> [!div class="mx-imgBorder"]
> ![Eksperimentell Bytt til slå på feiladministrasjon på formelnivå](media/working-with-references/accounts-iferror.png)

Deretter erstatte formelen med dette:

```powerapps-dot
IfError(
    "Team: " & AsType( ThisItem.Owner, [@Teams] ).'Team Name',
    "User: " & AsType( ThisItem.Owner, [@Users] ).'Full Name' )
```

## <a name="filter-based-on-an-owner"></a>Filtrere basert på eier

Gratulerer – du er ferdig med det de vanskeligste aspektet ved å arbeide med en postreferanse. Andre brukstilfeller er det enklere fordi de ikke tilgang til feltene i posten. Som et tilfelle in punkt, ta filtrering, som du vil utforske i denne delen.

Legg til en **kombinasjonsboks** kontroll over galleriet, og angi egenskapene for den nye kontrollen:

- **Elementer**: `Users`
- **SelectMultiple**: `false`

> [!div class="mx-imgBorder"]
> ![Lagt til Kombinasjonsboks kontrollen over galleriet med elementer-egenskapen satt til brukere](media/working-with-references/filter-insert-combobox.png)

Hvis du vil filtrere galleriet av en bestemt bruker valgt fra denne kombinasjonsboksen, kan du angi galleriets **elementer** egenskapen til denne formelen:

```powerapps-dot
Filter( Accounts, Owner = ComboBox1.Selected )
```

> [!div class="mx-imgBorder"]
> ![Filtrerte galleriet basert på verdien som er angitt i kombinasjonsboksen kontroll](media/working-with-references/filter-accounts.png)

> [!IMPORTANT]
> Instruksjonene i dette emnet er nøyaktige Hvis du følge trinnene nøyaktig. Alle formler som refererer til en kontroll med navn blir imidlertid ikke hvis kontrollen har et annet navn. Hvis du sletter og legge til en kontroll av samme type, endres nummeret på slutten av navnet på kontrollen. For enhver formel som viser en feil, må du kontrollere at den inneholder riktig navnene på alle kontroller.

Du trenger ikke bruke **IsType** eller **AsType** fordi du sammenligner posten referanser til andre referanser til posten eller til hele poster. Appen er kjent enhet **ComboBox1.Selected** fordi den er avledet fra den **brukere** enhet. Kontoer som er eier av et team ikke samsvarer med filterkriteriet.

Du kan få litt mer avansert ved å støtte filtrering av en bruker eller et team.

1. Frigjør mer plass nær toppen av skjermen ved å endre størrelse på galleriet og å flytte kombinasjonsboksen, Sett inn en [ **Radio** kontrollen](controls/control-radio.md) over galleriet, og angi disse egenskapene for den nye kontrollen:

    - **Elementer**: `[ "All", "Users", "Teams" ]`
    - **Oppsett**: `Layout.Horizontal`

1. For den **kombinasjonsboks** kontroll, angi denne egenskapen (Hvis kombinasjonsboksen forsvinner, velg **brukere** i radio-kontrollen):

    - **Synlig**: `Radio1.Selected.Value = "Users"`

1. Kopiere og lime inn den **kombinasjonsboks** kontroll, Flytt kopien direkte over opprinnelige, og deretter angi følgende egenskaper for kopien:

    - **Elementer**: `Teams`
    - **Synlig**: `Radio1.Selected.Value = "Teams"`

    Appen vises bare én kombinasjonsboks om gangen, avhengig av tilstanden til radio-kontrollen. Fordi de er direkte over hverandre, vises de skal være den samme kontrollen som endrer innholdet.

1. Til slutt konfigurerer den **elementer** -egenskapen for den **galleriet** kontrollen som denne formelen:

    ```powerapps-dot
    Filter( Accounts,
        Radio1.Selected.Value = "All"
        Or (Radio1.Selected.Value = "Users" And Owner = ComboBox1.Selected)
        Or (Radio1.Selected.Value = "Teams" And Owner = ComboBox1_1.Selected)
    )
    ```

    > [!div class="mx-imgBorder"]
    > ![filtrerte galleri som viser alle poster eller en bestemt bruker eller gruppe](media/working-with-references/filter-combobox.png)

Med disse endringene, kan du vise alle poster eller filtrere dem basert på en bruker eller en gruppe:

> [!div class="mx-imgBorder"]
> ![animasjon som viser forskjellige filtrerte resultater basert på radio-kontrollen og kombinasjonsboks boksene](media/working-with-references/filter-allthree.gif)

Formelen er fullstendig kan delegeres. Delen som sammenligner alternativknapp-verdiene er en konstant på tvers av alle poster og evalueres før resten av filteret sendes til Common Data Service.

Hvis du vil filtrere på av eieren, kan du bruke den **IsType** -funksjonen, men det er ikke ennå kan delegeres.

> [!div class="mx-imgBorder"]
> ![Filtrere etter Eiertype ved hjelp av IsType](media/working-with-references/filter-bytype.png)

## <a name="update-the-owner-by-using-patch"></a>Oppdatere eieren ved hjelp av oppdateringen

Du kan oppdatere den **eieren** feltet på samme måte som alle andre oppslag. Angi den valgte kontoeier til første-teamet:

```powerapps-dot
Patch( Accounts, Gallery1.Selected, { Owner: First( Teams ) } )
```

Denne fremgangsmåten ikke skiller seg fra et vanlig oppslag at appen er kjent **første (Teams)**. Hvis du vil den første brukeren i stedet, kan du erstatte den delen med **første (brukere)**. Den **Patch** funksjonen vet som den **eieren** feltet kan være satt til en av disse to enhetstyper.

Å legge til denne funksjonaliteten til appen:

1. I den **trevisning** rute, velger du **Radio** kontroll og to **kombinasjonsboks** kontroller på samme tid.

1. Ellipse-menyen, velg **Kopier disse elementene**.

    > [!div class="mx-imgBorder"]
    > ![Kopi av flere kontroller ved hjelp av trevisningen](media/working-with-references/patch-copy.png)

1. På den samme menyen, velg **Lim inn**.

    > [!div class="mx-imgBorder"]
    > ![Lim inn på flere kontroller ved hjelp av trevisningen](media/working-with-references/patch-paste.png)

1. Flytt de kopierte kontrollene til høyre i galleriet.

    > [!div class="mx-imgBorder"]
    > ![Flyttet kopierte kontrollene til høyre i galleriet](media/working-with-references/patch-position.png)

1. Velg den kopierte **Radio** kontroll, og deretter endre disse egenskapene:

    - Elementer: `[ "Users", "Teams" ]`
    - Standard: `If( IsType( Gallery1.Selected.Owner, Users ), "Users", "Teams" )`

    > [!div class="mx-imgBorder"]
    > ![Fjernet alle valget fra radio-kontrollen](media/working-with-references/patch-noall.png) 

1. I den **Radio** kontroll, velg **brukere** slik at den **kombinasjonsboks** kontroll som viser brukere er synlig.

1. Velg den synlig **kombinasjonsboks** kontroll, og angi deretter det **DefaultSelectedItems** egenskapen til denne formelen:

    ```powerapps-dot
    If( IsType( Gallery1.Selected.Owner, Users ),
        AsType( Gallery1.Selected.Owner, Users ),
        Blank()
    )
    ```

    > [!div class="mx-imgBorder"]
    > ![Standardegenskapen angis for kombinasjonsboksen brukere](media/working-with-references/patch-default-users.png)

1. I den **Radio** kontroll, velg **Teams** slik at den **kombinasjonsboks** kontroll som viser en liste over grupper er synlig.

1. Velg den **Radio** kontroll til å ta valg bort fra nå-usynlig **kombinasjonsboks** kontroll for brukere.

1. Velg den synlig **kombinasjonsboks** kontroll for Team, og deretter angi dens **DefaultSelectedItems** egenskapen til denne formelen:

    ```powerapps-dot
    If( IsType( Gallery1.Selected.Owner, Teams ),
        AsType( Gallery1.Selected.Owner, Teams ),
        Blank()
    )
    ```

    > [!div class="mx-imgBorder"]
    > ![Standardegenskapen angis for kombinasjonsboksen grupper](media/working-with-references/patch-default-teams.png)

1. Sett inn en **knappen** kontroll, Flytt den under den **kombinasjonsboks** kontroll, og deretter angi knappens **tekst** egenskapen til `"Patch Owner"`.

1. Angi den **OnSelect** -egenskapen for knappen til denne formelen:

    ```powerapps-dot
    Patch( Accounts, Gallery1.Selected,
        { Owner: If( Radio1_1.Selected.Value = "Users",
                ComboBox1_2.Selected,
                ComboBox1_3.Selected ) } )
    ```

    > [!div class="mx-imgBorder"]
    > ![Formelen angitt på knapp-kontroll](media/working-with-references/patch-button.png)

Den kopierte **Radio** og **kombinasjonsboks** kontrollene viser eieren for kontoen for øyeblikket er valgt i galleriet. Med de samme kontrollene, kan du angi eieren av kontoen til en hvilken som helst team eller en bruker ved å velge knappen:

> [!div class="mx-imgBorder"]
> ![Animasjon som viser oppdateringen av eieren med en bruker eller en gruppe](media/working-with-references/patch-allthree.gif)

## <a name="show-the-owner-by-using-a-form"></a>Vis eieren ved bruk av et skjema

Du kan vise en **eieren** feltet i et skjema ved å legge til et egendefinert kort. Du kan ikke endre verdien av feltet med en skjema-kontroll i skrivende stund.

1. Sett inn en **redigeringsskjema** kontroll, og deretter endre størrelse på og flytte den til hjørnet nederst til høyre.

1. På den **Egenskaper** fanen nær høyre side av skjermen, åpner du **datakilden** listen, og velg deretter **kontoer**.

    > [!div class="mx-imgBorder"]
    > ![Skjema-kontroll som viser flere felt med tomme verdier](media/working-with-references/form-insert.png)  

1. Angi skjemaets **element** egenskapen til `Gallery1.Selected`.

    > [!div class="mx-imgBorder"]
    > ![Skjema-kontroll som viser flere felt er fylt ut fra det valgte elementet i galleriet](media/working-with-references/form-item.png)

1. På den **Egenskaper** fanen nær høyre side av skjermen, velg **Rediger felt**.

1. I den **felt** ruten, velg ellipsen, og velg deretter **legge til et egendefinert kort**.

    > [!div class="mx-imgBorder"]
    > ![Kommandoen for å legge til et egendefinert kort](media/working-with-references/form-customcard.png)

    Det nye kortet vises nederst i skjema-kontrollen.

1. Endre størrelsen på kortet etter behov for å vise hele teksten.

    > [!div class="mx-imgBorder"]
    > ![Satt inn egendefinert kort, tom](media/working-with-references/form-inserted-customcard.png)

1. Sett inn en **etikett** kontroll i det egendefinerte kortet, og deretter angi etikettens **tekst** egenskapen formelen som du brukte i galleriet:

    ```powerapps-dot
    If( IsType( ThisItem.Owner, Teams ),
        "Team: " & AsType( ThisItem.Owner, Teams ).'Team Name',
        "User: " & AsType( ThisItem.Owner, Users ).'Full Name' )
    ```

    > [!div class="mx-imgBorder"]
    > ![Egendefinert kort som viser eier-feltet i en etikettkontroll](media/working-with-references/form-displayowner.png)

For hvert valg i galleriet vises flere felt med den kontoen, inkludert postens eier, i skjemaet. Hvis du endrer eieren ved hjelp av den **Patch** knappen, skjema-kontrollen viser også denne endringen.

> [!div class="mx-imgBorder"]
> ![Animasjon som viser skjemakontrollen svarer på endringer i galleriet](media/working-with-references/form-allthree.gif)

## <a name="show-the-fields-of-a-customer"></a>Vis feltene for en kunde

I Common Data Service, den **kunden** oppslagsfelt er en annen polymorfisk oppslag som er veldig lik **eieren**.

**Eier** er begrenset til ett per enhet, men enheter kan inneholde null, ett eller flere **kunden** oppslagsfelt. Den **kontakter** systemenhet inkluderer den **firmanavn** feltet, som er en **kunden** oppslagsfelt.

> [!div class="mx-imgBorder"]
> ![Kontakt-enhet som viser Firmanavn-feltet som en kunde-datatype som ikke er obligatorisk](media/working-with-references/customer-companyname.png)

Du kan legge til mer **kunden** oppslagsfelt til en enhet ved å velge den **kunden** datatypen for et nytt felt.

![Kundedata typen fra listen over datatyper når du oppretter et felt](media/working-with-references/customer-datatype.png)

A **kunden** oppslagsfelt kan referere til en post ved bruk av **kontoer** enhet eller **kontakter** enhet. Du skal bruke den **IsType** og **AsType** functions med disse enhetene, slik at den nå er det på tiden å legge dem som datakilder (du kan la **Teams** og **brukere**  på sted).

> [!div class="mx-imgBorder"]
> ![Kontoer, Team, brukere og kontakter enheter i Data-ruten](media/working-with-references/customer-datasources.png)

Behandlingen av den **kunden** og **eieren** felt er så like at du bokstavelig talt kan kopiere appen (**filen** > **Lagre som**, og deretter angi et annet navn) og gjøre disse enkle erstatninger:

| Location | **Eier** utvalg | **Kunden** utvalg |
|----------|-----------|------------------|
| I hele | **Eier** | **'Kundenavn'** |
| I hele | **Brukere** | **Kontoer** |
| I hele | **Grupper** | **Kontakter** |
| Galleriets **elementer** egenskapen | **Kontoer** | **Kontakter** |
| Skjemaets **elementer** egenskapen | **Kontoer** | **Kontakter** |
| Det første argumentet for **oppdateringen**<br>i knappens **OnSelect** egenskapen | **Kontoer** | **Kontakter** |
| Filtrere radio's **elementer** egenskapen | **[&nbsp;«Alle»,&nbsp;«Brukere»,&nbsp;«Team»&nbsp;]** | **[&nbsp;«Alle»,&nbsp;"-kontoer",&nbsp;"Kontakter"&nbsp;]** |
| Oppdatering radio's **elementer** egenskapen | **[«Brukere», «Team»]** | **[«Forretningsforbindelser», «Kontakter»]** |
| Kombinasjonsboks for **Visible** egenskapen | **«Brukere»** og **«Team»** | **"-Kontoer"** og **"Kontakter"** |

For eksempel nye galleriet skal ha dette **elementer** egenskapen:

```powerapps-dot
Filter( Contacts,
    Radio1.Selected.Value = "All"
    Or (Radio1.Selected.Value = "Accounts" And 'Company Name' = ComboBox1.Selected)
    Or (Radio1.Selected.Value = "Contacts" And 'Company Name' = ComboBox1_1.Selected)
)
```

> [!div class="mx-imgBorder"]
> ![Kunde-app som er avledet fra appen eier med enkle endringer som er brukt](media/working-with-references/customer-simple-update.png)

To viktige forskjeller mellom **kunden** og **eieren** krever en oppdatering til formler i galleriet, og skjemaet:

1. Én-til-mange-relasjoner mellom **kontoer** og **kontakter** forrang når du refererer til disse enhetstyper etter navn. I stedet for **kontoer**, bruke  **\[ \@kontoer]**; i stedet for **kontakter**, bruke  **\[ \@ Kontakter]**. Ved hjelp av den [globale tvetydighetsoperatoren](functions/operators.md#disambiguation-operator), sikrer du at du refererer til enhetstypen i **IsType** og **AsType**. Dette problemet finnes bare i konteksten oppføring i kontrollene galleriet og skjemaet.

1. Den **eieren** feltet må ha en verdi, men **kunden** felt kan være *tom*. Hvis du vil vise korrekt resultat uten et typenavn, kan du teste for denne saken med den [ **IsBlank** funksjonen](functions/function-isblank-isempty.md), og vise en tom tekststreng i stedet.

Begge disse endringene er i den samme formelen, som vises i det egendefinerte kortet i skjemaet, samt som i den **tekst** -egenskapen for galleriets etikettkontroll:

```powerapps-dot
If( IsBlank( ThisItem.'Company Name' ), "",
    IsType( ThisItem.'Company Name', [@Accounts] ),
        "Account: " & AsType( ThisItem.'Company Name', [@Accounts] ).'Account Name',
    "Contact: " & AsType( ThisItem.'Company Name', [@Contacts] ).'Full Name'
)
```

> [!div class="mx-imgBorder"]
> ![Oppdater til Text-egenskapen for undertittel etikettkontrollen i galleriet](media/working-with-references/customer-update.png)

Med disse endringene, kan du vise og endre den **firmanavn** feltet i den **kontakter** enhet.

> [!div class="mx-imgBorder"]
> ![Animasjon som viser hvordan å velge en kontakt endres de andre kontrollene, og skjemaet](media/working-with-references/customer-allthree.gif)

> [!NOTE]
> I skrivende stund **kunden** oppslag har disse begrensningene:
>
> - Du kan ikke filtrere en liste basert på en bestemt post i den **kontakter** eller **kontoer** enheter. Filter alternativknapp-kontroll i det forrige eksemplet vil ikke fungere.
> - Bare kunde-feltet som fungerer som er den systemdefinerte **'Firmanavn'** på den **kontakter** enhet, som ble brukt i det forrige eksemplet. Legger til et kundefelt for egendefinerte ennå støttes ikke.
> - Du kan ikke fjerne kunde-feltet ved hjelp av **Patch** å angi den til *tom*.

## <a name="understand-regarding-lookup-fields"></a>Forstå angående oppslagsfelt

Den **angående** oppslagsfelt er litt forskjellig fra de som du allerede har arbeidet med i dette emnet. Du begynner ved å bruke mønstrene som dette emnet som er beskrevet tidligere, og deretter vil du lære andre triks.

Du kan starte ganske enkelt med den **telefakser** enhet. Denne enheten har en polymorfisk **angående** oppslagsfelt, som kan referere til **kontoer**, **kontakter**, og andre enheter. Du kan gjøre appen **kunder** og endre det for **telefakser**.

| Location | **Kunden** utvalg | **Telefakser** utvalg |
|----------|-----------|------------------|
| I hele | **'Kundenavn'** | **Angående** |
| Galleriets **elementer** egenskapen | **Kontakter** | **Telefakser** |
| Skjemaets **elementer** egenskapen | **Kontakter** | **Telefakser** |
| Det første argumentet for **oppdateringen**<br> i knappens **OnSelect** egenskapen | **Kontakter** | **Telefakser** |

På nytt, må du legge til en datakilde: dette tidspunktet for **telefakser**. På den **Vis** fanen og velge **datakilder**:

> [!div class="mx-imgBorder"]
> ![Data-ruten viser kontoer, Teams, brukere, kontakter og telefakser enheter](media/working-with-references/faxes-datasources.png)

En viktig forskjell for **angående** er at den ikke begrenset til **kontoer** og **kontakter**. Listen over enheter er faktisk extensible med egendefinerte enheter. Mest mulig ut av appen har plass til dette punktet uten endring, men du må oppdatere formelen for etiketten i galleriet, og skjemaet:

```powerapps-dot
If( IsBlank( ThisItem.Regarding ), "",
    IsType( ThisItem.Regarding, [@Accounts] ),
        "Account: " & AsType( ThisItem.Regarding, [@Accounts] ).'Account Name',
    IsType( ThisItem.Regarding, [@Contacts] ),
        "Contacts: " & AsType( ThisItem.Regarding, [@Contacts] ).'Full Name',
    ""
)
```

> [!div class="mx-imgBorder"]
> ![Oppdaterte Text-egenskapen for kontrollen Undertittel for angående oppslag](media/working-with-references/regarding-label.png)

Etter at du har disse endringene, du arbeider med den **angående** oppslag akkurat som du gjorde det **eieren** og **kunden** oppslag.

> [!div class="mx-imgBorder"]
> ![Animasjon som viser hvordan du velger et element i galleriet endres de andre kontrollene, og skjemaet](media/working-with-references/regarding-allthree.gif)

> [!NOTE]
> I skrivende stund **angående** oppslag har disse begrensningene:
>
> - Du kan ikke filtrere en liste basert på en bestemt post. Filter alternativknapp-kontroll i det forrige eksemplet vil ikke fungere.
> - Du kan ikke fjerne feltet angående ved hjelp av **Patch** å angi den til *tom*.

## <a name="understand-regarding-relationships"></a>Forstå angående relasjoner

**Angående** er forskjellig fra **eieren** og **kunden** fordi tidligere omfatter en mange-til-én-relasjon. Per definisjon, en omvendt, én-til-mange-relasjon kan du skrive **første (kontoer). Telefakser**.

La oss ta sikkerhetskopi, og se på enheten definisjonene. I Common Data Service, enheter som **telefakser**, **oppgaver**, **e-postmeldinger**, **notater**, **telefonsamtaler**, **Bokstaver**, og **chatter** er tilordnet som [ *aktiviteter*](../../developer/common-data-service/activity-entities.md). Du kan også opprette dine egne [egendefinert aktivitet enheter](../../developer/common-data-service/custom-activities.md). Når du viser eller opprette en aktivitetsenhet, innstillingene vises under **flere innstillinger**.

![Enheten aktivitetsinnstilling når du oppretter en enhet](media/working-with-references/activity-entitytype.png)

Andre enheter kan være relatert til en aktivitetsenhet hvis de er aktivert som en *aktivitet oppgave* i enhetens innstillinger. **Kontoer**, **kontakter**, og mange andre standardenheter så er angitt (på nytt, under **flere innstillinger**).

![Oppgave aktivitetsinnstilling når du oppretter en enhet](media/working-with-references/activity-entityuse.png)

Alle aktivitet enheter og aktivitet-aktivitet enheter har en indirekte relasjon. Hvis du endre filteret på **alle** øverst på skjermen, velg den **telefakser** enhet, og velg deretter den **relasjoner** fanen, alle enheter som kan være et mål for en  **Angående** oppslag vises.

> [!div class="mx-imgBorder"]
> ![Relasjoner i telefakser enheten som viser om mange-til-én-relasjoner](media/working-with-references/activity-manytoone.png)

Hvis du viser relasjonene for den **kontoer** enhet, alle enhetene som kan være en kilde til en **angående** oppslagsfelt vises.

> [!div class="mx-imgBorder"]
> ![Relasjonene for konto-enheten som viser om én-til-mange-relasjoner](media/working-with-references/activity-onetomany.png)

Hva betyr det alle?

- Når du skriver formler, må du vurdere å at listen over enheter for aktiviteten er ikke løst, og du kan opprette din egen. Formelen må håndtere en aktivitetsenhet som du ikke forventet på riktig måte.
- Aktivitet aktiviteter og aktiviteter har en én-til-mange-relasjon. Du kan enkelt å be om alle telefakser som er knyttet til en konto.

Å utforske Dette konseptet i appen:

1. Legg til en annen skjerm.

    > [!div class="mx-imgBorder"]
    > ![Sett inn en tom skjerm](media/working-with-references/activitypointer-newscreen.png)

1. Sett inn en galleri-kontroll, endre størrelsen på den og deretter flytte den til venstre side av skjermen.

1. På den **Egenskaper** fanen nær høyre side av skjermen, angi galleriets **elementer** til **kontoer**.

    > [!div class="mx-imgBorder"]
    > ![Angi elementer til kontoer i Rapportruten](media/working-with-references/activitypointer-accounts.png)

1. Angi galleriets oppsett **tittel**, og deretter angi tittel-feltet til **kontonavn**.

    > [!div class="mx-imgBorder"]
    > ![Angi oppsett til tittel for galleri-kontrollen i Egenskaper-ruten](media/working-with-references/activitypointer-account-name.png)

1. Legge til et andre galleri, endre størrelsen på den og deretter flytte den til høyre side av skjermen.

1. Angi ny galleriets **elementer** egenskapen til `Gallery2.Selected.Faxes`.

    Dette trinnet returnerer den filtrerte listen over telefakser for en gitt konto.

    > [!div class="mx-imgBorder"]
    > ![Angi Items-egenskapen for galleriet som viser telefakser](media/working-with-references/activitypointer-faxes.png)

1. Angi galleriets oppsett **tittel og undertittel**, og deretter angi tittel-feltet til å vise den **emne** felt (noe som kan være små bokstaver **emne**).

    > [!div class="mx-imgBorder"]
    > ![Angi tittel til emnefeltet](media/working-with-references/activitypointer-subject.png)

Når du velger et element i listen over kontoer, viser listen over telefakser telefakser for bare denne kontoen.

> [!div class="mx-imgBorder"]
> ![Animasjon som viser merkede området i galleriet kontoer fremmer listen over telefakser](media/working-with-references/activitypointer-allthree.gif)

## <a name="activity-entity"></a>Aktivitet-enhet

Som den forrige delen beskriver, kan du vise alle telefakser for en konto. Du kan imidlertid også vise alle aktivitetene for en konto, inkludert telefakser, e-postmeldinger, telefonsamtaler og andre funksjoner.

For scenariet sistnevnte vil du bruke den **aktivitet** enhet. Du kan vise denne enheten ved å aktivere **alle** øverst i høyre hjørne for å fjerne filteret fra listen over enheter.

> [!div class="mx-imgBorder"]
> ![Listen over enheter som viser aktiviteten enheten](media/working-with-references/activitypointer-entity.png)

Den **aktivitet** enhet som er spesielt. Hver gang du legger til en post til den **telefakser** enhet, systemet oppretter også en post i den **aktivitet** enhet med feltene som er felles på tvers av alle aktivitet-enheter. Av disse feltene, **emne** er en av de mest interessante.

Du kan vise alle aktiviteter ved å endre bare én linje i det forrige eksemplet. Erstatt `Gallery2.Selected.Faxes` med `Gallery2.Selected.Activities`.

> [!div class="mx-imgBorder"]
> ![Endring av elementer-egenskapen for det andre galleriet, endre fra telefakser til aktiviteter](media/working-with-references/activitypointer-gallery.png)

Poster som kommer fra den **aktivitet** enhet, men du kan likevel bruke den **IsType** funksjonen for å angi hvilken type aktivitet de er. På nytt, før du bruker **IsType** med en enhetstype, må du legge til datakilden.

> [!div class="mx-imgBorder"]
> ![Data-ruten viser alle enheter som er nødvendige for funksjonen IsType](media/working-with-references/activity-datasources.png)

Ved å bruke denne formelen, kan du vise oppføringstypen i en etikett i galleriet:

```powerapps-dot
If( IsType( ThisItem, [@Faxes] ), "Fax",
    IsType( ThisItem, [@'Phone Calls'] ), "Phone Call",
    IsType( ThisItem, [@'Email Messages'] ), "Email Message",
    IsType( ThisItem, [@Chats] ), "Chat",
    "Unknown"
)
```

> [!div class="mx-imgBorder"]
> ![Angi tekst-egenskapen til formel for å vise informasjon for telefakser, telefonsamtaler og andre aktiviteter](media/working-with-references/activitypointer-type.png)

Du kan også bruke **AsType** å få tilgang til feltene i en bestemt type. For eksempel denne formelen bestemmer hvilken type hver aktivitet og, for telefonsamtaler, viser retningen til telefon tall og kall fra den **telefonnumre** enhet:

```powerapps-dot
If( IsType( ThisItem, [@Faxes] ), "Fax",
    IsType( ThisItem, [@'Phone Calls'] ),
       "Phone Call: " &
       AsType( ThisItem, [@'Phone Calls'] ).'Phone Number' &
       " (" & AsType( ThisItem, [@'Phone Calls'] ).Direction & ")",
    IsType( ThisItem, [@'Email Messages'] ), "Email Message",
    IsType( ThisItem, [@Chats] ), "Chat",
    "Unknown"
)
```

> [!div class="mx-imgBorder"]
> ![Utvidet text-egenskapen med mer informasjon for en telefonsamtale](media/working-with-references/activitypointer-phonecall.png)

Appen viser derfor en fullstendig liste over aktiviteter. Den **emne** feltet vises for alle typer aktiviteter, om formelen tar dem i betraktning eller ikke. For typer aktiviteter som du vet om, kan du vise deres typenavn og typespesifikke informasjon om hver aktivitet.

> [!div class="mx-imgBorder"]
> ![Fullført skjerm som viser informasjon for ulike typer aktiviteter](media/working-with-references/activitypointer-complete.png)

## <a name="notes-entity"></a>Notater enhet

Så langt har alle de **angående** eksempler er basert på aktiviteter, men den **notater** enhet representerer et annet tilfelle.

Når du oppretter en enhet, kan du aktivere vedlegg.

> [!div class="mx-imgBorder"]
> ![Aktivering av vedlegg og notater når du oppretter en enhet](media/working-with-references/notes-entity.png)

Hvis du velger i avmerkingsboksen for å aktivere vedlegg, oppretter du en **angående** relasjon med den **notater** enhet, som denne grafikken viser for den **kontoer** enhet:

> [!div class="mx-imgBorder"]
> ![Konto-enhet som viser forholdet til notater gjennom en én-til-mange-relasjon](media/working-with-references/notes-relationships.png)

Enn denne forskjellen kan du bruke den **angående** oppslag på samme måte som du bruker aktiviteter. Enheter som er aktivert for vedlegg har en én-til-mange-relasjon til **notater**, som i dette eksemplet:

`First( Accounts ).Notes`

> [!NOTE]
> I skrivende stund den **angående** oppslag er ikke tilgjengelig for den **notater** enhet. Du kan ikke lese eller filtrere basert på den **angående** feltet, og du kan ikke angi feltet ved hjelp av **Patch**.
>
> Imidlertid omvendt **notater** én-til-mange-relasjon er tilgjengelig, slik at du kan filtrere en liste over notater for en post som er aktivert for vedlegg. Du kan også bruke den [ **relatere** ](functions/function-relate-unrelate.md) funksjonen til å legge til et notat i en post **notater** tabell, men notatet må opprettes først, som i dette eksemplet:
>
>`Relate( ThisItem.Notes, Patch( Notes, Defaults( Notes ), { Title: "A new note" } ) )`

## <a name="activity-parties"></a>Aktivitetsparter

I skrivende stund støtter ikke lerretsapper aktivitetsparter.