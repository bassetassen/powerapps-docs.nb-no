---
title: Forstå post referanser og polymorfiske oppslag | Microsoft Docs
description: Arbeid med post referanser og polymorfiske oppslag i lerret apper
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 09/14/2019
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: ebb7b9d5eb203a32ef0ec931a8f653125e8f5f26
ms.sourcegitcommit: 5899d37e38ed7111d5a9d9f3561449782702a5e9
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 09/17/2019
ms.locfileid: "71037949"
ms.PowerAppsDecimalTransform: true
---
# <a name="understand-record-references-and-polymorphic-lookups-in-canvas-apps"></a>Forstå post referanser og polymorfiske oppslag i lerret apper

Når du skrev et forsknings papir i skolen, så du sannsynligvis en liste over referansene dine på slutten. Du tok ikke med en kopi av det faktiske bakgrunns materialet du brukte, men i stedet en nett kobling, bok tittel og forfatter, eller annen informasjon, slik at noen kan spore den opprinnelige kilden. Du har blandet ulike typer kilder i én liste, avis artikler ved siden av lyd innspillinger, hver med sine egne spesifikke detaljer for et riktig sitat. Wikipedia-artikler inkluderer for eksempel ofte en [lang liste over referanser](https://en.wikipedia.org/wiki/Microsoft#References).

I lerret apps fungerer du ofte med kopier av poster som lastes ned fra data kilder. Du bruker [**oppslags**](functions/function-filter-lookup.md) -og [**filter**](functions/function-filter-lookup.md) funksjonene og [**Galleri**](controls/control-gallery.md) kontrollens **valgte** egenskap til å identifisere den bestemte posten du ønsker. Alle postene fra **filter** eller **valgte** vil være av samme enhets type, slik at du kan bruke felt med en enkel. *NOTATION.* Disse kopiene inkluderer ofte referanse informasjon, slik at du kan bruke [**patch**](functions/function-patch.md) -funksjonen til å oppdatere den opprinnelige kilden.

Lerret apper støtter også *post referanser*. På samme måte som en referanse til forsknings papir, refererer en post referanse til en post uten å inkludere en fullstendig kopi av den. En slik referanse kan referere til en post i en hvilken som helst enhet. I tillegg til slike bok referanser kan du blande poster fra ulike enheter i én kolonne.

Mange operasjoner på post referanser er identiske for å arbeide med poster. Du kan sammenligne post referanser med hverandre og til fullstendige poster. Du kan angi en post referanses verdi med **patch** -funksjonen, på samme måte som med et oppslag med en fullstendig post.

Det er én viktig bruks forskjell: du får ikke direkte tilgang til feltene i en post referanse uten først å opprette en enhet den refererer til. Dette er fordi lerret apper krever at alle typer er kjent når du skriver formler. Fordi du ikke vet typen post referanse før appen kjører, kan du ikke bruke den enkle. *NOTATION direkte* . Du må først fastsette enhets typen dynamisk med [**IsType**](functions/function-astype-istype.md) -funksjonen og deretter bruke. *Feltkode* i resultatet av [**AsType**](functions/function-astype-istype.md) -funksjonen.

*Enhets typen* refererer til skjemaet for hver post i en enhet. Hver enhet har et unikt sett med felter med ulike navn og data typer. Hver post i enheten arver strukturen. to poster har samme enhets type hvis de kommer fra samme enhet.

## <a name="polymorphic-lookups"></a>Polymorfisk oppslag

Common Data Service støtter relasjoner mellom poster. Hver post i **kontoer** -enheten har et **primær kontakt** oppslags felt til en post i **kontakter** -enheten. Oppslaget kan bare referere til en post i **kontakter** , og kan ikke referere til en post i, si, **Teams** -enheten. Den siste detaljene er viktig fordi du alltid vet hvilke felt som er tilgjengelige for oppslaget.

Common Data Service støtter også polymorfiske oppslag, som kan referere til en post fra en enhet i et sett. **Eier** -feltet kan for eksempel referere til en post i **bruker** enheten eller **team** enheten. Det samme oppslags feltet i ulike poster kan referere til poster i ulike enheter. I dette tilfellet vet du ikke alltid hvilke felt som vil være tilgjengelige.

Arbeidsom råde post referanser ble utformet for å jobbe med polymorfiske oppslag i Common Data Service. Du kan også bruke post referanser utenfor denne konteksten, som er måten de to begrepene skiller seg på.

I den neste delen begynner du å utforske disse begrepene ved å arbeide med **eierskaps** oppslaget.

## <a name="show-the-fields-of-a-record-owner"></a>Vis feltene for en post eier

Hver enhet i Common Data Service inkluderer et **eier** felt. Dette feltet kan ikke fjernes, du kan ikke legge til et annet, og det krever alltid en verdi.

Slik viser du dette feltet i **kontoen** heten:

1. Åpne [dette powerapps-nettstedet](http://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc).
1. Velg **data** > **enheter**i det venstre navigasjons feltet.
1. Velg **konto**i listen over enheter.
1. I hjørnet øverst til høyre åpner du Filter listen (som standard er satt til **standard** ), og deretter velger du **alle**.
1. Rull ned til **eier** -feltet vises.

 > [!div class="mx-imgBorder"]
 > ![Eier felt på konto enhet](media/working-with-references/owner-field.png)

Dette oppslags feltet kan referere til en post fra **team** enheten eller **brukerne** heten. Ikke alle poster i disse enhetene har tillatelse til å være en **eier**. se de støttede rollene hvis du kjører på et problem.

Denne grafikken viser et enkelt galleri med **kontoer**, der **konto** enheten er lagt til i appen som en data kilde:

> [!div class="mx-imgBorder"]
> ![Kontoer som vises i en Galleri-kontroll](media/working-with-references/accounts-gallery.png)

> [!IMPORTANT]
> I dette emnet viser grafikken noen navn og andre verdier som ikke er en del av eksempel dataene som leveres med Common Data Service. Trinnene viser nøyaktig hvordan du konfigurerer kontroller for et bestemt resultat, men opplevelsen vil variere basert på dataene for organisasjonen.

Hvis du vil vise eieren av hver konto i galleriet, kan det hende du blir fristet til å bruke formelen **ThisItem.Owner.name**. Navn-feltet i **team** enheten er imidlertid **team navn**, og navn-feltet i **bruker** enheten er **fullt navn**. Appen kan ikke vite hvilken type oppslag du jobber med før du kjører appen, og den kan variere mellom poster i **kontoer** -enheten.

Du trenger en formel som kan tilpasses dette avviket. Du må også legge til data kildene for enhets typene som **eieren** kan være (i dette tilfellet **brukere** og **team**). Legg til disse tre data kildene i appen:

> [!div class="mx-imgBorder"]
> ![Kontoer, team og brukere av enheter i data-ruten](media/working-with-references/accounts-datasources.png)

Med disse data kildene på plass kan du bruke denne formelen til å vise navnet på en bruker eller et team:

```powerapps-comma
If( IsType( ThisItem.Owner; [@Teams] );
    "Team: " & AsType( ThisItem.Owner; [@Teams] ).'Team Name';
    "User: " & AsType( ThisItem.Owner; [@Users] ).'Full Name' )
```

> [!div class="mx-imgBorder"]
> ![Kontoer som vises i en Galleri-kontroll med eier felt som vises](media/working-with-references/accounts-displayowner.png)

I denne formelen tester **IsType** -funksjonen **eier** -feltet mot **Teams** -enheten. Hvis det er av enhets typen, endres **AsType** -funksjonen til en **team** -post. På dette tidspunktet har du tilgang til alle feltene i **team** enheten, inkludert **gruppe navn**, ved hjelp av *. NOTATION.* Hvis **IsType** bestemmer at **eieren** ikke er en post i **Teams** -enheten, må feltet være en post i **bruker** enheten, fordi **eier** -feltet er nødvendig (kan ikke være *tomt*).

Du bruker den [globale detvetydige operatoren](functions/operators.md#disambiguation-operator) for **[@Teams]** og **[@Users]** for å sikre at du bruker den globale enhets typen. Du trenger den ikke i dette tilfellet, men det er lurt å bruke det. Én-til-mange-relasjoner er ofte i konflikt i post omfanget i galleriet, og denne øvelsen unngår dette forvirring.

Hvis du vil bruke noen av feltene i en post referanse, må du først bruke **AsType** -funksjonen til å endre den til en bestemt enhets type. Du har ikke tilgang til felt direkte fra **eier** -feltet, fordi systemet ikke vet hvilken enhets type du vil bruke.

**AsType** -funksjonen returnerer en feil hvis **eier** -feltet ikke Sams varer med enhets typen det er bedt om, så du kan bruke **IfError** -funksjonen til å forenkle denne formelen. Først slår du på eksperiment-funksjonen **feil behandling på formel nivå**:

> [!div class="mx-imgBorder"]
> ![Eksperimentell Bytt til å aktivere feil administrasjon på formel nivå](media/working-with-references/accounts-iferror.png)

Deretter erstatter du den forrige formelen med denne:

```powerapps-comma
IfError(
    "Team: " & AsType( ThisItem.Owner; [@Teams] ).'Team Name';
    "User: " & AsType( ThisItem.Owner; [@Users] ).'Full Name' )
```

## <a name="filter-based-on-an-owner"></a>Filter basert på en eier

Gratulerer – du er ferdig med å jobbe med en post referanse. Andre bruks tilfeller er enklere fordi de ikke har tilgang til felt i posten. Som et tilfelle i punkt, ta filtrering, som du vil utforske i denne delen.

Legg til en **kombinasjons boks** kontroll over galleriet, og angi disse egenskapene for den nye kontrollen:

- **Elementer**:`Users`
- **SelectMultiple**:`false`

> [!div class="mx-imgBorder"]
> ![Ekstra kombinasjons boks kontroll ovenfor galleri med elementer-egenskap satt til brukere](media/working-with-references/filter-insert-combobox.png)

Hvis du vil filtrere galleriet etter en bestemt bruker som er valgt fra denne kombinasjons boksen, kan du angi **element** -egenskapen for galleriet til denne formelen:

```powerapps-comma
Filter( Accounts; Owner = ComboBox1.Selected )
```

> [!div class="mx-imgBorder"]
> ![Filtrert Galleri basert på verdi angitt i kombinasjons boks kontrollen](media/working-with-references/filter-accounts.png)

> [!IMPORTANT]
> Instruksjonene i dette emnet er nøyaktige hvis du følger trinnene nøyaktig. En formel som refererer til en kontroll ved navn, mislykkes imidlertid Hvis kontrollen har et annet navn. Hvis du sletter og legger til en kontroll av samme type, endres tallet på slutten av kontrollens navn. For en formel som viser en feil, må du bekrefte at den inneholder riktige navn på alle kontroller.

Du trenger ikke bruke **IsType** eller **AsType** , fordi du sammenligner post referanser med andre post referanser eller til fullstendige poster. Appen vet enhets typen til **ComboBox1. er valgt** fordi den er avledet fra **bruker** enheten. Kontoer som eieren er et team til, Sams varer ikke med filter kriteriet.

Du kan få litt fancier ved å støtte filtrering ved hjelp av en bruker eller en gruppe.

1. Lag litt plass nær toppen av skjermen ved å endre størrelsen på galleriet og flytte kombinasjons boksen, sett inn en [ **radio** kontroll](controls/control-radio.md) over galleriet, og angi deretter disse egenskapene for den nye kontrollen:

    - **Elementer**:`[ "All"; "Users"; "Teams" ]`
    - **Oppsett**:`Layout.Horizontal`

1. Angi denne egenskapen for **kombinasjons boks** kontrollen (hvis kombinasjons boksen forsvinner, og velg **brukere** i radio-kontrollen):

    - **Synlige**:`Radio1.Selected.Value = "Users"`

1. Kopier og lim inn **kombinasjons boks** -kontrollen, Flytt kopien direkte over originalen, og angi deretter disse egenskapene for kopien:

    - **Elementer**:`Teams`
    - **Synlige**:`Radio1.Selected.Value = "Teams"`

    Appen viser bare én kombinasjons boks om gangen, avhengig av tilstanden til radio kontrollen. Siden de er rett over hverandre, ser de ut til å være den samme kontrollen som endrer innholdet.

1. Til slutt angir du **elementer** -egenskapen for **Galleri** -kontrollen til denne formelen:

    ```powerapps-comma
    Filter( Accounts;
        Radio1.Selected.Value = "All"
        Or (Radio1.Selected.Value = "Users" And Owner = ComboBox1.Selected)
        Or (Radio1.Selected.Value = "Teams" And Owner = ComboBox1_1.Selected)
    )
    ```

    > [!div class="mx-imgBorder"]
    > ![Filtrert galleri som viser alle poster eller en bestemt bruker eller gruppe](media/working-with-references/filter-combobox.png)

Med disse endringene kan du vise alle poster eller filtrere dem basert på en bruker eller et team:

> [!div class="mx-imgBorder"]
> ![Animasjon som viser ulike filtrerte resultater basert på radio-kontrollen og kombinasjons boksene](media/working-with-references/filter-allthree.gif)

Formelen er full kan delegeres. Delen som sammenligner radio knapp verdiene, er en konstant på tvers av alle poster, og evalueres før resten av filteret sendes til Common Data Service.

Hvis du vil filtrere etter eier typen, kan du bruke **IsType** -funksjonen, men det er ikke kan delegeres ennå.

> [!div class="mx-imgBorder"]
> ![Filtrer etter eier type ved hjelp av IsType](media/working-with-references/filter-bytype.png)

## <a name="update-the-owner-by-using-patch"></a>Oppdater eieren ved hjelp av patch

Du kan oppdatere **eier** feltet på samme måte som med alle andre oppslag. Slik angir du eieren av den gjeldende valgte kontoen til det første teamet:

```powerapps-comma
Patch( Accounts; Gallery1.Selected; { Owner: First( Teams ) } )
```

Denne Fremgangs måten er ikke forskjellig fra et vanlig oppslag fordi appen kjenner til typen for **første (Team)** . Hvis du vil bruke den første brukeren i stedet, erstatter du den delen med **først (brukere)** . **Patch** -funksjonen vet at **eier** -feltet kan settes til én av disse to enhets typene.

Slik legger du til denne funksjonen i appen:

1. Velg **radio** -kontrollen og de to **kombinasjons boks** kontrollene samtidig, i **tre visnings** ruten.

1. Velg **Kopier disse elementene**på ellipse-menyen.

    > [!div class="mx-imgBorder"]
    > ![Kopi av flere kontroller ved hjelp av tre visningen](media/working-with-references/patch-copy.png)

1. Velg **Lim inn**på samme-menyen.

    > [!div class="mx-imgBorder"]
    > ![Lim inn flere kontroller ved hjelp av tre visningen](media/working-with-references/patch-paste.png)

1. Flytt de kopierte kontrollene til høyre i galleriet.

    > [!div class="mx-imgBorder"]
    > ![Flyttede kopierte kontroller til høyre i galleriet](media/working-with-references/patch-position.png)

1. Velg den kopierte **radio** -kontrollen, og endre deretter disse egenskapene:

    - Elementene`[ "Users"; "Teams" ]`
    - Standarden`If( IsType( Gallery1.Selected.Owner; Users ); "Users"; "Teams" )`

    > [!div class="mx-imgBorder"]
    > ![Fjernet alt valget fra Radio kontrollen](media/working-with-references/patch-noall.png) 

1. Velg **brukere** i **radio** -kontrollen, slik at **kombinasjons boks** kontrollen som viser brukerne, er synlig.

1. Velg den synlige **kombinasjons boks** -kontrollen, og angi deretter **DefaultSelectedItems** -egenskapen til denne formelen:

    ```powerapps-comma
    If( IsType( Gallery1.Selected.Owner; Users );
        AsType( Gallery1.Selected.Owner; Users );
        Blank()
    )
    ```

    > [!div class="mx-imgBorder"]
    > ![Standard egenskaps sett for brukerens kombinasjons boks](media/working-with-references/patch-default-users.png)

1. Velg **Teams** i **radio** -kontrollen, slik at **kombinasjons boks** kontrollen som viser team, er synlig.

1. Velg **radio** kontrollen hvis du vil foreta valg vekk fra den nå usynlige **kombinasjons boks** kontrollen for brukere.

1. Velg den synlige **kombinasjons boks** kontrollen for Teams, og angi deretter **DefaultSelectedItems** -egenskapen til denne formelen:

    ```powerapps-comma
    If( IsType( Gallery1.Selected.Owner; Teams );
        AsType( Gallery1.Selected.Owner; Teams );
        Blank()
    )
    ```

    > [!div class="mx-imgBorder"]
    > ![Standard egenskaps sett for Teams-kombinasjons boksen](media/working-with-references/patch-default-teams.png)

1. Sett inn en **knapp** -kontroll, Flytt den under **kombinasjons boks** -kontrollen, og angi deretter **tekst** -egenskapen `"Patch Owner"`for knappen til.

1. Angi **OnSelect** -egenskapen for knappen til denne formelen:

    ```powerapps-comma
    Patch( Accounts; Gallery1.Selected;
        { Owner: If( Radio1_1.Selected.Value = "Users";
                ComboBox1_2.Selected;
                ComboBox1_3.Selected ) } )
    ```

    > [!div class="mx-imgBorder"]
    > ![Formel angitt på knappe kontroll](media/working-with-references/patch-button.png)

De kopierte **radio** -og **kombinasjons boks** kontrollene viser eieren av den merkede kontoen i galleriet. Med de samme kontrollene kan du angi eieren av kontoen for enhver gruppe eller bruker ved å velge knappen:

> [!div class="mx-imgBorder"]
> ![Animasjon som viser en eier oppdatering med enten en bruker eller en gruppe](media/working-with-references/patch-allthree.gif)

## <a name="show-the-owner-by-using-a-form"></a>Å vise eieren ved hjelp av et skjema

Du kan vise et **eier** felt i et skjema ved å legge til et egen definert kort. På denne måten kan du ikke endre verdien i feltet med en skjema-kontroll.

1. Sett inn en **redigerings skjema** -kontroll, og endre deretter størrelsen og Flytt den til hjørnet nederst til høyre.

1. Åpne **data kilde** -listen på **Egenskaper** -fanen nær høyre side av skjermen, og velg deretter **kontoer**.

    > [!div class="mx-imgBorder"]
    > ![Skjema kontroll som viser ekstra felt med tomme verdier](media/working-with-references/form-insert.png)  

1. Angi skjemaets **element** -egenskap til `Gallery1.Selected`.

    > [!div class="mx-imgBorder"]
    > ![Skjema kontroll som viser at flere felt er fylt ut fra det valgte elementet i galleriet](media/working-with-references/form-item.png)

1. Velg **Rediger felt**på **Egenskaper** -fanen nær høyre side av skjermen.

1. Velg ellipsen i **felt** -ruten, og velg deretter **Legg til et egen definert kort**.

    > [!div class="mx-imgBorder"]
    > ![Kommando for å legge til et egen definert kort](media/working-with-references/form-customcard.png)

    Det nye kortet vises nederst i skjema-kontrollen.

1. Endre størrelsen på kortet etter behov for å vise all teksten.

    > [!div class="mx-imgBorder"]
    > ![Egen definert kort som er satt inn, tomt](media/working-with-references/form-inserted-customcard.png)

1. Sett inn en **etikett** -kontroll i det egen definerte kortet, og angi deretter **tekst** -egenskapen for etiketten til formelen du brukte i galleriet:

    ```powerapps-comma
    If( IsType( ThisItem.Owner; Teams );
        "Team: " & AsType( ThisItem.Owner; Teams ).'Team Name';
        "User: " & AsType( ThisItem.Owner; Users ).'Full Name' )
    ```

    > [!div class="mx-imgBorder"]
    > ![Egen definert kort som viser eier-feltet i en etikett-kontroll](media/working-with-references/form-displayowner.png)

For hvert valg i galleriet, vises flere felt i kontoen, inkludert postens eier, i skjemaet. Hvis du endrer eieren ved hjelp av **oppdaterings** knappen, viser skjema-kontrollen også denne endringen.

> [!div class="mx-imgBorder"]
> ![Animasjon som viser skjema kontrollen som svarer på endringer i galleriet](media/working-with-references/form-allthree.gif)

## <a name="show-the-fields-of-a-customer"></a>Vis feltene til en kunde

I Common Data Service er **kunde** oppslags feltet et annet polymorfisk oppslag som er veldig lik **eieren**.

**Eieren** er begrenset til én per enhet, men enheter kan inneholde null, ett eller flere oppslags felt for **kunder** . System entiteten **kontakter** inkluderer feltet **firma navn** , som er et oppslags felt for **kunde** .

> [!div class="mx-imgBorder"]
> ![Kontakt enhet som viser firmanavn-felt som kunde data type som ikke er nødvendig](media/working-with-references/customer-companyname.png)

Du kan legge til flere oppslags felt for **kunde** i en enhet ved å velge **kunde** data typen for et nytt felt.

![Kunde data typen fra listen over data typer ved oppretting av et felt](media/working-with-references/customer-datatype.png)

Et oppslags felt for **kunde** kan referere til en post fra **konto** enheten eller **kontakt** enheten. Du kommer til å bruke **IsType** -og **AsType** -funksjonene med disse enhetene, så det er nå et godt tidspunkt å legge dem til som data kilder (du kan la **grupper** og **brukere** være på plass).

> [!div class="mx-imgBorder"]
> ![Kontoer, team, brukere og kontakt enheter i data-ruten](media/working-with-references/customer-datasources.png)

Behandling av feltene for **kunde** og **eier** er så likt at du kan kopiere appen i en bokstavelig måte (lagre**fil** > **som**, og deretter angi et annet navn) og gjøre disse enkle omplasseringene:

| Location | Eksempel på **eier** | **Kunde** eksempel |
|----------|-----------|------------------|
| Implementere | **Ren** | **Kunde navn** |
| Implementere | **Muligheten** | **Plan** |
| Implementere | **Gruppene** | **Kontaktmappe** |
| **Element** egenskap for Galleri | **Plan** | **Kontaktmappe** |
| **Element** -egenskapen for skjemaet | **Plan** | **Kontaktmappe** |
| Det første argumentet for **oppdatering**<br>i **OnSelect** -egenskapen for knappen | **Plan** | **Kontaktmappe** |
| **Element** -egenskapen til filter radioen | **[&nbsp;"Alle";&nbsp;"brukere";&nbsp;"Teams&nbsp;"]** | **[&nbsp;"Alle";&nbsp;"kontoer";&nbsp;"kontakter"&nbsp;]** |
| **Element** egenskap for oppdaterings radio | **[«Brukere»; «Team»]** | **[«Kontoer»; «kontakter»]** |
| **Synlig** -egenskapen for kombinasjons boksen | **"Brukere"** og **"Teams"** | **«Kontoer»** og **«kontakter»** |

Det nye galleriet skal for eksempel ha denne **element** -egenskapen:

```powerapps-comma
Filter( Contacts;
    Radio1.Selected.Value = "All"
    Or (Radio1.Selected.Value = "Accounts" And 'Company Name' = ComboBox1.Selected)
    Or (Radio1.Selected.Value = "Contacts" And 'Company Name' = ComboBox1_1.Selected)
)
```

> [!div class="mx-imgBorder"]
> ![Kunde-app avledet fra eier appen med enkle endringer tatt i bruk](media/working-with-references/customer-simple-update.png)

To viktige forskjeller mellom **kunden** og **eieren** krever en oppdatering av formlene i galleriet og skjemaet:

1. Én-til-mange-relasjoner mellom **kontoer** og **kontakter** prioriteres når du refererer til disse enhets typene etter navn. I stedet for **kontoer**, kan du bruke  **\[ \@kontoer]** ; i stedet for **kontakter**kan du bruke  **\[ \@kontakter]** . Ved å bruke den [globale detvetydige operatoren](functions/operators.md#disambiguation-operator), sikrer du at du refererer til enhets typen i **IsType** og **AsType**. Dette problemet finnes bare i post konteksten til galleri-og skjema kontrollene.

1. **Eier** -feltet må ha en verdi, men **kunde** felt kan være *tomme*. Hvis du vil vise riktig resultat uten et typenavn, kan du teste dette tilfellet med [ **IsBlank** -funksjonen](functions/function-isblank-isempty.md)og vise en tom tekst streng i stedet.

Begge disse endringene er i den samme formelen, som vises i det egen definerte kortet i skjemaet, i tillegg til i **tekst** -egenskapen i galleriets etikett-kontroll:

```powerapps-comma
If( IsBlank( ThisItem.'Company Name' ); "";
    IsType( ThisItem.'Company Name'; [@Accounts] );
        "Account: " & AsType( ThisItem.'Company Name'; [@Accounts] ).'Account Name';
    "Contact: " & AsType( ThisItem.'Company Name'; [@Contacts] ).'Full Name'
)
```

> [!div class="mx-imgBorder"]
> ![Oppdater til tekst-egenskapen for kontrollen for under tittel etikett i galleriet](media/working-with-references/customer-update.png)

Med disse endringene kan du vise og endre **Firmanavn** -feltet i **kontakter** -enheten.

> [!div class="mx-imgBorder"]
> ![Animasjon som viser hvordan valg av en kontakt endrer de andre kontrollene og skjemaet](media/working-with-references/customer-allthree.gif)

## <a name="understand-regarding-lookup-fields"></a>Forstå angående oppslags felt

Oppslags feltet **angående** er det samme som det du allerede har jobbet med i dette emnet. Du begynner med å bruke mønstrene som dette emnet beskrevet tidligere, og deretter lærer du andre triks.

Du kan starte ganske enkelt med **telefaks** enheten. Denne enheten har et polymorfisk **om** oppslags felt, som kan referere til **kontoer**, **kontakter**og andre enheter. Du kan ta appen for **kunder** og endre den for **telefakser**.

| Location | **Kunde** eksempel | Eksempel på **telefakser** |
|----------|-----------|------------------|
| Implementere | **Kunde navn** | **Angående** |
| **Element** egenskap for Galleri | **Kontaktmappe** | **Tatt** |
| **Element** -egenskapen for skjemaet | **Kontaktmappe** | **Tatt** |
| Det første argumentet for **oppdatering**<br> i **OnSelect** -egenskapen for knappen | **Kontaktmappe** | **Tatt** |

På nytt må du legge til en data kilde: denne gangen for **telefakser**. Velg **data kilder**på **Vis** -fanen:

> [!div class="mx-imgBorder"]
> ![Data rute som viser kontoer, team, brukere, kontakter og faks enheter](media/working-with-references/faxes-datasources.png)

En viktig forskjell for **angående** er at det ikke er begrenset til **kontoer** og **kontakter**. Listen over enheter er faktisk utvidbar med egen definerte enheter. Meste parten av appen kan ha plass til dette punktet uten endringer, men du må oppdatere formelen for etiketten i galleriet og skjemaet:

```powerapps-comma
If( IsBlank( ThisItem.Regarding ); "";
    IsType( ThisItem.Regarding; [@Accounts] );
        "Account: " & AsType( ThisItem.Regarding; [@Accounts] ).'Account Name';
    IsType( ThisItem.Regarding; [@Contacts] );
        "Contacts: " & AsType( ThisItem.Regarding; [@Contacts] ).'Full Name';
    ""
)
```

> [!div class="mx-imgBorder"]
> ![Oppdatert tekst-egenskapen for under tittel-kontrollen for angående oppslag](media/working-with-references/regarding-label.png)

Når du har gjort disse endringene, arbeider du med **angående** -oppslag på samme måte som du gjorde **eier** -og **kunde** oppslagene.

> [!div class="mx-imgBorder"]
> ![Animasjon som viser hvordan du velger et element i galleriet, endrer de andre kontrollene og skjemaet](media/working-with-references/regarding-allthree.gif)

## <a name="understand-regarding-relationships"></a>Forstå angående relasjoner

**Angående** er forskjellig fra **eier** og **kunde** , fordi den førstnevnte omfatter en mange-til-én-relasjon. Med en omvendt, en-til-mange-relasjon kan du skrive **først (kontoer). Fakser**.

La oss sikkerhetskopiere og se på enhets definisjonene. I Common Data Service er enheter som **fakser**, **oppgaver**, **e-postmeldinger**, **notater**, **telefon oppringinger**, **brev**og **Chat** angitt som [*aktiviteter*](../../developer/common-data-service/activity-entities.md). Du kan også opprette dine egne [egen definerte aktivitets enheter](../../developer/common-data-service/custom-activities.md). Når du viser eller oppretter en aktivitets enhet, vises innstillingene under **flere innstillinger**.

![Aktivitets enhets innstilling ved oppretting av en enhet](media/working-with-references/activity-entitytype.png)

Andre enheter kan være relatert til en aktivitets enhet hvis de er aktivert som en *aktivitets oppgave* i enhetens innstillinger. **Kontoer**, **kontakter**og mange andre standard enheter er så utpekt (på nytt under **flere innstillinger**).

![Aktivitets oppgave innstilling ved oppretting av en enhet](media/working-with-references/activity-entityuse.png)

Alle aktivitets enheter og aktivitet for aktivitets enheter har en implisert relasjon. Hvis du endrer filteret til **alle** øverst på skjermen, velger du **faks** enheten, og deretter velger du **relasjoner** -fanen, alle enheter som kan være et mål for et **angående** oppslag.

> [!div class="mx-imgBorder"]
> ![Relasjoner til telefaksen heten som viser angående mange-til-én-relasjoner](media/working-with-references/activity-manytoone.png)

Hvis du viser relasjonene for **kontoer** -enheten, vises alle enheter som kan være en kilde for et **angående** oppslags felt.

> [!div class="mx-imgBorder"]
> ![Relasjoner mellom kontoen heten som viser om én-til-mange-relasjoner](media/working-with-references/activity-onetomany.png)

Hva betyr det?

- Når du skriver formler, må du vurdere at listen over aktivitets enheter ikke er reparert, og du kan opprette din egen. Formelen må håndtere en aktivitets enhet som du ikke forventet.
- Aktivitets oppgaver og-aktiviteter har en én-til-mange-relasjon. Du kan enkelt be om alle telefakser som er relatert til en konto.

For å utforske dette konseptet i appen:

1. Legg til en annen skjerm.

    > [!div class="mx-imgBorder"]
    > ![Sett inn en tom skjerm](media/working-with-references/activitypointer-newscreen.png)

1. Sett inn en Galleri-kontroll, endre størrelsen på den, og Flytt den til venstre side av skjermen.

1. På **Egenskaper** -fanen, nær høyre side av skjermen, kan du angi **elementene** i galleriet til- **kontoer**.

    > [!div class="mx-imgBorder"]
    > ![Angi elementer til kontoer i egenskaps rute](media/working-with-references/activitypointer-accounts.png)

1. Angi oppsettet for galleriet til **Tittel**, og angi deretter Tittel-feltet til **konto navn**.

    > [!div class="mx-imgBorder"]
    > ![Angi oppsett til tittel for Galleri-kontrollen i egenskaper-ruten](media/working-with-references/activitypointer-account-name.png)

1. Legg til et annet galleri, endre størrelsen på den, og Flytt den til høyre side av skjermen.

1. Angi **elementer** -egenskapen for det nye galleriet `Gallery2.Selected.Faxes`til.

    Dette trinnet returnerer den filtrerte listen over fakser for en gitt konto.

    > [!div class="mx-imgBorder"]
    > ![Angi elementer-egenskapen for galleriet som viser fakser](media/working-with-references/activitypointer-faxes.png)

1. Angi oppsettet for galleriet til **Tittel og under tittel**, og angi deretter Tittel-feltet for å vise **Emne** -feltet (som kan være **Emne**med små bokstaver).

    > [!div class="mx-imgBorder"]
    > ![Angi tittel til emne felt](media/working-with-references/activitypointer-subject.png)

Når du velger et element i listen over kontoer, viser faks listen faks bare for denne kontoen.

> [!div class="mx-imgBorder"]
> ![Animasjon som viser utvalget i konto galleriet som driver listen over fakser](media/working-with-references/activitypointer-allthree.gif)

## <a name="activity-entity"></a>Aktivitets enhet

Som det forrige avsnittet beskriver, kan du vise alle faksene for en konto. Du kan imidlertid også vise alle aktivitetene for en konto, inkludert fakser, e-postmeldinger, telefon samtaler og andre samhandlinger.

For det siste scenarioet bruker du **aktiviteten** heten. Du kan vise denne enheten ved å slå på **alle** i øvre høyre hjørne for å fjerne filteret fra listen over enheter.

> [!div class="mx-imgBorder"]
> ![Liste over enheter som viser aktivitets enheten](media/working-with-references/activitypointer-entity.png)

**Aktiviteten** heten er spesial. Når du legger til en post i **faks** enheten, oppretter systemet også en post i **aktivitets** enheten med feltene som er felles for alle aktivitets enheter. Av disse feltene, er **subjekt** en av de mest interessante.

Du kan vise alle aktiviteter ved å endre bare én linje i det forrige eksemplet. Erstatt `Gallery2.Selected.Faxes` med `Gallery2.Selected.Activities`.

> [!div class="mx-imgBorder"]
> ![Element egenskap for det andre galleriet, endre fra fakser til aktiviteter](media/working-with-references/activitypointer-gallery.png)

Poster kommer fra **aktivitets** enheten, men du kan likevel bruke **IsType** -funksjonen til å identifisere hvilken type aktivitet de er. Før du bruker **IsType** med en enhets type, må du legge til data kilden på nytt.

> [!div class="mx-imgBorder"]
> ![Data rute som viser alle enhetene som kreves for funksjonen IsType](media/working-with-references/activity-datasources.png)

Ved å bruke denne formelen kan du vise oppførings typen i en etikett-kontroll i galleriet:

```powerapps-comma
If( IsType( ThisItem; [@Faxes] ); "Fax";
    IsType( ThisItem; [@'Phone Calls'] ); "Phone Call";
    IsType( ThisItem; [@'Email Messages'] ); "Email Message";
    IsType( ThisItem; [@Chats] ); "Chat";
    "Unknown"
)
```

> [!div class="mx-imgBorder"]
> ![Angi tekst-egenskap til formel for å vise informasjon om telefakser, telefon samtaler og andre aktiviteter](media/working-with-references/activitypointer-type.png)

Du kan også bruke **AsType** for å få tilgang til feltene av den bestemte typen. Denne formelen bestemmer for eksempel typen for hver aktivitet og, for telefon samtaler, viser telefon nummeret og samtale retningen fra **Telefon nummer** enheten:

```powerapps-comma
If( IsType( ThisItem; [@Faxes] ); "Fax";
    IsType( ThisItem; [@'Phone Calls'] );
       "Phone Call: " &
       AsType( ThisItem; [@'Phone Calls'] ).'Phone Number' &
       " (" & AsType( ThisItem; [@'Phone Calls'] ).Direction & ")";
    IsType( ThisItem; [@'Email Messages'] ); "Email Message";
    IsType( ThisItem; [@Chats] ); "Chat";
    "Unknown"
)
```

> [!div class="mx-imgBorder"]
> ![Utvidet tekst-egenskap med mer informasjon for en telefon samtale](media/working-with-references/activitypointer-phonecall.png)

Som et resultat av dette viser appen en fullstendig liste over aktiviteter. **Emne** feltet vises for alle typer aktiviteter, enten formelen tar dem inn i betraktning eller ikke. Du kan vise sine type navn og type spesifikk informasjon om hver aktivitet for typer aktiviteter du er kjent med.

> [!div class="mx-imgBorder"]
> ![Fullført skjerm viser informasjon for ulike typer aktiviteter](media/working-with-references/activitypointer-complete.png)

## <a name="notes-entity"></a>Notat enhet

Så langt har alle eksemplene som **gjelder** , basert på aktiviteter, men **Notes** -enheten representerer en annen sak.

Når du oppretter en enhet, kan du aktivere vedlegg.

> [!div class="mx-imgBorder"]
> ![Aktivering av vedlegg og notater ved oppretting av en enhet](media/working-with-references/notes-entity.png)

Hvis du merker av for å aktivere vedlegg, kan du opprette en **angående** -relasjon med **Notes** -enheten, som denne grafikken viser for **kontoer** -enheten:

> [!div class="mx-imgBorder"]
> ![Konto enhet som viser relasjon til notater gjennom en én-til-mange-relasjon](media/working-with-references/notes-relationships.png)

Andre enn denne forskjellen bruker du **angående** -oppslag på samme måte som du bruker aktiviteter i. Enheter som er aktivert for vedlegg, har en én-til-mange-relasjon til **notater**, som i dette eksemplet:

`First( Accounts ).Notes`

> [!NOTE]
> Ved denne skriving er det ingen **Lookup tilgjengelig** for **Notes** -enheten. Du kan ikke lese eller filtrere basert på **angående** -feltet, og du kan ikke angi feltet ved hjelp av **patch**.
>
> Det er imidlertid mulig **å gjøre en** -til-mange-relasjon tilgjengelig, slik at du kan filtrere en liste over notater for en post som er aktivert for vedlegg. Du kan også bruke [**Relater**](functions/function-relate-unrelate.md) -funksjonen til å legge til et notat i **Notes** -tabellen for en post, men notatet må opprettes først, som i dette eksemplet:
>
>`Relate( ThisItem.Notes; Patch( Notes; Defaults( Notes ); { Title: "A new note" } ) )`

## <a name="activity-parties"></a>Aktivitets parter

Som denne skriving støtter ikke lerrets programmer aktivitets parter.