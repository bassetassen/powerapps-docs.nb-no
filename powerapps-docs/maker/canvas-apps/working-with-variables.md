---
title: Slik fungerer variabler i lerretsapper | Microsoft Docs
description: Referanseinformasjon om å arbeide med tilstand, kontekstvariabler og samlinger i lerretsapper
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 02/28/2019
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 6f46dcdf300c91be9fbc2f39e6b2a5418a4b82de
ms.sourcegitcommit: 825daacc9a812637815afc1ce6fad28f0cebd479
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/04/2019
ms.locfileid: "57803761"
---
# <a name="understand-canvas-app-variables-in-powerapps"></a>Slik fungerer lerretsappvariabler i PowerApps

Hvis du har brukt et annet programmeringsverktøy, for eksempel Visual Basic eller JavaScript, du kan det hende spør: **Hvor er variablene?** PowerApps er litt annerledes, og krever en annen fremgangsmåte. I stedet for hente en variabel når du bygger en lerret-app, kan du stille deg selv: **Hva ville jeg gjort i Excel?**

I andre verktøy kan du kanskje eksplisitt ha utført en beregning og lagret resultatet i en variabel. PowerApps og Excel omberegner imidlertid automatisk formler etter som inndataene endres, slik at du vanligvis ikke trenger å opprette og oppdatere variabler. Ved å følge denne fremgangsmåten når det er mulig, kan du enklere opprette, forstå og vedlikeholde appen.

I noen tilfeller må du bruke variabler i PowerApps, noe som utvider Excel sin modell ved å legge til [formler for virkemåte](working-with-formulas-in-depth.md). Disse formlene kjøres for eksempel når en bruker velger en knapp. I en formel for virkemåte, er det er ofte nyttig å angi en variabel som skal brukes i andre formler.

Generelt bør du unngå å bruke variabler. Men noen ganger er det bare en variabel som kan aktivere opplevelsen som du vil ha. Variabler opprettes implisitt og skrevet inn når de vises i funksjoner som angi verdiene. 

## <a name="translate-excel-into-powerapps"></a>Å oversette Excel til PowerApps

### <a name="excel"></a>Excel

La oss gå gjennom hvordan Excel fungerer. En celle kan inneholde en verdi, for eksempel et tall eller en streng, eller en formel som er basert på verdiene i andre celler. Etter at brukeren angir en annen verdi i en celle, vil Excel automatisk beregne formler som er avhengige av den nye verdien på nytt. Du trenger å gjøre noe programmering for å aktivere denne virkemåten.

I eksemplet nedenfor celle **A3** er satt til formelen **A1 + A2**. Hvis **A1** eller **A2** endringer, **A3** automatisk beregnes på nytt for å gjenspeile endringen. Denne virkemåten krever ingen koding utenfor selve formelen.

![Animasjon av omberegning summen av to tall i Excel](media/working-with-variables/excel-recalc.gif)

Excel har ikke variabler. Verdien til en celle som inneholder en formel endres basert på inndataene, men det finnes ingen måte å huske resultatet av en formel på og lagre dem i en celle, eller noen andre steder. Hele regnearket endres og alle tidligere beregnede verdier går tapt, hvis du endrer verdien for en celle. En Excel-bruker kan kopiere og lime inn celler, men det er noe brukeren kontrollerer manuelt og er ikke mulig med formler.

### <a name="powerapps"></a>PowerApps

Apper du oppretter i PowerApps, fungerer omtrent på samme måte som Excel. I stedet for å oppdatere celler, kan du legge til kontroller hvor som helst på en skjerm og navngi dem for bruk i formler.

Du kan for eksempel replikere Excel virkemåten i en app ved å legge til en **[etikett](controls/control-text-box.md)** kontroll, kalt **Label1**, og to **[tekstinndataene](controls/control-text-input.md)** kontroller, kalt **TextInput1** og **TextInput2**. Hvis du deretter setter den **[tekst](controls/properties-core.md)** -egenskapen for **Label1** til **TextInput1 + TextInput2**, vil den alltid vise summen av uansett hvilke tall er i **TextInput1** og **TextInput2** automatisk.

![Beregner summen av to tall i PowerApps](media/working-with-variables/recalc1.png)

Legg merke til at den **Label1** kontrollen er valgt, viser den **[tekst](controls/properties-core.md)** formelen i formellinjen øverst på skjermen. Her finner vi formelen **TextInput1 + TextInput2**. Denne formelen oppretter en avhengighet mellom disse kontrollene, på samme måte som avhengigheter opprettes mellom cellene i en Excel-arbeidsbok.  La oss endre verdien for **TextInput1**:

![Animasjon av beregning av summen av to tall i PowerApps](media/working-with-variables/recalc2.gif)

Formelen for **Label1** har blitt automatisk beregnet på nytt, viser den nye verdien.

I PowerApps kan du bruke formler til å bestemme, ikke bare den primære verdien av en kontroll, men også egenskaper som formatering. I eksemplet nedenfor er en formel for **[Farge](controls/properties-color-border.md)**-egenskapen for etiketten som automatisk viser negative verdier i rødt. **[If](functions/function-if.md)**-funksjonen bør du kunne kjenne igjen fra Excel:

`If( Value(Label1.Text) < 0, Red, Black )`

![Animasjon av betinget formatering](media/working-with-variables/recalc-color.gif)

Du kan bruke formler for et bredt utvalg av scenarioer:

* En kartkontroll kan vise den gjeldende posisjonen din med en formel som bruker **Location.Latitude** og **Location.Longitude** ved hjelp av enhetens GPS.  Kartet sporer automatisk plasseringen din, når du flytter på deg.
* Andre brukere kan oppdatere [datakilder](working-with-data-sources.md).  Andre i gruppen kan kanskje for eksempel oppdatere elementer i en SharePoint-liste.  Når du oppdaterer en datakilde, beregnes automatisk alle avhengige formler for å gjenspeile de oppdaterte dataene. Videre kan du kanskje angi **[Elementer](controls/properties-core.md)**-egenskapen i et galleri til formelen **Filter (SharePointList)**, som automatisk viser det nylig filtrerte settet med [poster](working-with-tables.md#records).

### <a name="benefits"></a>Fordeler

Det er mange fordeler med å bruke formler til å bygge apper:

* Hvis du kjenner Excel, kjenner du også PowerApps. Modellen og formelspråket er det samme.
* Hvis du har brukt andre programmeringsverktøy, kan du tenke deg hvor mye kode som ville vært nødvendig for å fullføre disse eksemplene.  I Visual Basic måtte du ha skrevet en hendelsesbehandling for endringshendelsen på hver kontroll for tekstinndata.  Koden for å utføre beregningen i hver av disse er overflødig og kan komme ut av balanse, eller du måtte ha skrevet en felles delrutine.  Du oppnådde alt dette med en enkelt, én-linje formel i PowerApps.
* Å forstå hvor **Label1**'s tekst er kommer fra, vet du nøyaktig hvor du skal lete: formelen i den **[tekst](controls/properties-core.md)** egenskapen.  Det finnes ingen annen måte å påvirke teksten i kontrollen.  I et tradisjonelt programmeringsverktøy kan eventuelle hendelsesbehandlinger eller delrutiner endre verdien for etiketten, fra hvor som helst i programmet.  Dette kan gjøre det vanskelig å spore når og hvor en variabel ble endret.
* Hvis brukeren endrer en glidebryteren og deretter ombestemmer seg, kan de endre glidebryteren tilbake til den opprinnelige verdien.  Og det er som om ingenting ble endret: appen viser de samme kontrollverdiene som den gjorde før.  Det er ingen konsekvenser for å eksperimentere og spørre «hva om», på samme måte som i Excel.  

Du vil vanligvis komme bedre ut av det, hvis du kan oppnå en effekt ved hjelp av en formel. La formelmotoren i PowerApps arbeide for deg.  

## <a name="know-when-to-use-variables"></a>Slik vet du når du skal bruke variabler

La oss endre den enkle kalkulatoren til å fungere som en gammeldags kalkulator, med en løpende sum. Hvis du velger en **Legg til**-knapp, skal du legge til et tall til den løpende summen. Hvis du velger en **Tøm**-knapp, vil du tilbakestille den løpende totalsummen til null.

| Vis | Beskrivelse |
|----|----|
| <style> IMG {max bredde: none} </style> ![App med en tekst inndata-kontroll, en etikett og to knapper](media/working-with-variables/button-changes-state-1.png) | Når appen starter, er den løpende summen 0.<br><br>Den røde prikken representerer brukerens fingeren i tekstinndata-boksen, der brukeren skriver inn **77**. |
| ![Tekstinndata-kontrollen inneholder 77, og Legg til-knappen trykkes](media/working-with-variables/button-changes-state-2.png) | Brukeren velger den **Legg til** knappen. |
| ![Totalt antall er 77, og en annen 77 det legges til den](media/working-with-variables/button-changes-state-3.png) | 77 legges til den løpende summen.<br><br>Brukeren velger den **Legg til** knappen igjen. |
| ![Totalt antall er 154 før merket er fjernet.](media/working-with-variables/button-changes-state-4.png) | 77 legges på nytt til den løpende summen, noe som resulterer i 154.<br><br>Brukeren velger den **tydelig** knappen. |
| ![Summen er fjernet.](media/working-with-variables/button-changes-state-5.png) | Den løpende summen tilbakestilles til 0. |

Kalkulatoren bruker noe som ikke finnes i Excel: en knapp. I denne appen kan du ikke bruke bare formler til å beregne den løpende summen, fordi verdien avhenger av en serie med handlinger som brukeren gjør. Den løpende summen må i stedet registreres og oppdateres manuelt. De fleste programmeringsverktøy lagrer denne informasjonen i en *variabel*.

Noen ganger trenger du en variabel for at appen skal oppføre seg slik du ønsker.  Men tilnærmingen leveres med advarsler:

* Du må oppdatere den løpende summen manuelt. Automatisk omberegning gjør ikke dette for deg.
* Den løpende summen kan ikke lenger beregnes basert på verdiene i andre kontroller. Det avhenger av hvor mange ganger brukeren valgte **Legg til**-knappen, og hvilken verdi som var i kontrollen for tekstinndata hver gang. Angav brukeren 77, og valgte **Legg til** to ganger, eller angav de 24 og 130 for hvert av tilleggene? Du kan ikke se forskjell når summen har nådd 154.
* Endringer i totalen kan komme fra forskjellige baner. I dette eksemplet kan både **Legg til-** og **Fjern**-knappene oppdatere summen. Hvilken knapp forårsaker problemet, hvis appen ikke fungerer slik du forventer?

## <a name="use-a-global-variable"></a>Bruk en global variabel

Vi krever en variabel som inneholder den løpende summen, hvis du vil opprette kalkulatoren. De enkleste variablene å arbeide med i PowerApps er *globale variabler*.  

Slik fungerer globale variabler:

* Du kan angi verdien for den globale variabelen med **[Set](functions/function-set.md)**-funksjonen.  **Set(MyVar, 1)** angir den globale variabelen **MyVar** til en verdi på **1**.
* Du bruker den globale variabelen ved å referere til navnet som brukes med **Set**-funksjonen.  **MyVar** vil returnere **1** i dette tilfellet.
* Globale variabler kan inneholde en hvilken som helst verdi, inkludert strenger, tall, poster, og [tabeller](working-with-tables.md).

La oss gjenoppbygge kalkulatoren vår ved hjelp av en global variabel:

1. Legg til en inndata-kontroll kalt **TextInput1**, og to knapper, kalt **Button1** og **Button2**.

2. Angi **[Tekst](controls/properties-core.md)**-egenskapen for **Button1** til **Legg til**, og angi **Tekst**-egenskapen for **Button2** til **Tøm**.

3. For å oppdatere den løpende summen hver gang en bruker velger **Legg til**-knappen, kan du angi **[OnSelect](controls/properties-core.md)**-egenskapen til denne formelen:

    **Angi (RunningTotal, RunningTotal + TextInput1)**

    Bare forekomster av denne formelen oppretter **RunningTotal** som en global variabel som inneholder et tall grunn av den **+** operatoren. Du kan referere til **RunningTotal** hvor som helst i appen. Hver gang brukeren åpner denne appen, **RunningTotal** har en opprinnelig verdi for *tom*.

    Første gang en bruker velger den **Legg til** knappen og **[angi](functions/function-set.md)** kjører, **RunningTotal** er satt til verdien  **RunningTotal + TextInput1**.

    ![OnSelect-egenskapen for knappen Legg er satt til Set-funksjonen](media/working-with-variables/global-variable-1.png)

4. For å angi den løpende totalsummen til **0** hver gang en bruker velger **Tøm**-knappen, kan du angi **[OnSelect](controls/properties-core.md)**-egenskapen til denne formelen:

    **Set( RunningTotal, 0 )**

    ![OnSelect-egenskapen til Clear-knappen er satt til Set-funksjonen](media/working-with-variables/global-variable-2.png)

5. Legg til en **[Etikett](controls/control-text-box.md)**-kontroll, og angi **[Tekst](controls/properties-core.md)**-egenskapen til **RunningTotal**.

    Denne formelen beregnes automatisk og viser brukeren verdien av **RunningTotal** samtidig med at den endres basert på knappene som brukeren velger.

    ![Text-egenskapen for etiketten er satt til navnet på variabelen](media/working-with-variables/global-variable-3.png)

6. Forhåndsvis appen, og så har vi kalkulatoren vår som beskrevet ovenfor. Skriv inn et tall i tekstboksen og trykk på **Legg til**-knappen flere ganger. Når du er klar kan du gå tilbake til redigeringsopplevelsen ved hjelp av ESC.

    ![Tekstinndata-kontrollen inneholder en verdi, og etiketten inneholder den løpende summen](media/working-with-variables/global-variable-4.png)

7. Hvis du vil vise den globale variabelen verdi, kan du velge den **filen** -menyen, og velg **variabler** i ruten til venstre.

    ![Variabler alternativet i Fil-menyen](media/working-with-variables/global-variable-file-1.png)

8. Hvis du vil vise alle steder der variabelen er definert og brukt, velger du den.

    ![Liste over plassering der variabelen brukes](media/working-with-variables/global-variable-file-2.png)

## <a name="types-of-variables"></a>Ulike typer variabler

PowerApps har tre typer variabler:

| Variabeltype | Omfang | Beskrivelse | Funksjoner som etablerer |
| --- | --- | --- | --- |
| Globale variabler |App |Enklest å bruke. Inneholder et tall, en tekststreng, Boolean, post, tabell, osv. som kan være referanser fra hvor som helst i appen. |[**Angi**](functions/function-set.md) |
| Kontekstvariabler |Skjerm |Bra for å sende verdier til en skjerm, omtrent som parametere er til en prosedyre i andre språk. Kan refereres fra bare ett skjermbilde. |[**UpdateContext**](functions/function-updatecontext.md)<br>[**Navigere**](functions/function-navigate.md) |
| Samlinger |App |Inneholder en tabell som kan refereres fra hvor som helst i appen. Tillater innholdet i tabellen å endres, i stedet for å angis i sin helhet. Du kan lagre til den lokale enheten for senere bruk. |[**Samle inn**](functions/function-clear-collect-clearcollect.md)<br>[**ClearCollect**](functions/function-clear-collect-clearcollect.md) |

## <a name="create-and-remove-variables"></a>Opprette og fjerne variabler

Alle variabler opprettes implisitt når de vises i en **angi**, **UpdateContext**, **Navigate**, **samle inn**, eller  **ClearCollect** funksjonen. Hvis du vil deklarere en variabel og typen, trenger du bare inkludere den i noen av disse funksjonene hvor som helst i appen. Ingen av disse funksjonene opprette variabler. de kan bare fylle variabler med verdier. Du erklærer aldri variabler eksplisitt som du kanskje i et annet programmeringsverktøy, og alle å skrive inn er implisitt fra bruk.

Du kan for eksempel ha en knapp-kontroll med en **OnSelect** formelen lik **Set (X, 1)**. Denne formelen oppretter **X** som en variabel med en type for tallet. Du kan bruke **X** har verdien i formler som et tall, og denne variabelen *tom* når du åpner appen, men før du velger knappen. Når du velger knappen, gir du **X** verdien for **1**.

Hvis du har lagt til en annen knappen, og angi dens **OnSelect** egenskapen til **Set (X, "Hei")**, vil det oppstå en feil fordi typen (tekststreng) ikke, samsvarer med i den forrige **angi**(tall). Alle implisitt definisjoner av variabelen må godta på typen. På nytt, alt dette skjedde fordi du nevnt **X** i formler, ikke fordi noen av disse formlene faktisk hadde kjørt.

Du fjerner en variabel ved å fjerne alle de **angi**, **UpdateContext**, **Navigate**, **samle inn**, eller **ClearCollect**  funksjoner som opprette implisitt variabelen. Uten disse funksjonene finnes ikke variabelen. Du må også fjerne alle referanser til variabelen fordi de vil forårsake en feil.

## <a name="variable-lifetime-and-initial-value"></a>Variabel levetiden og første verdi

Alle variabler beholdes i minnet mens appen kjører. Etter at appen lukkes, verdiene som holdes i variabler går tapt.

Du kan lagre innholdet i en variabel i en datakilde ved hjelp av den **Patch** eller **samle inn** funksjoner. Du kan også lagre verdier i samlinger på den lokale enheten ved hjelp av den [ **SaveData** ](functions/function-savedata-loaddata.md) funksjonen.

Når brukeren åpner appen, har alle variabler en opprinnelig verdi for *tom*.

## <a name="reading-variables"></a>Lesing av variabler

Du kan bruke variabelens navnet til å lese verdien. Du kan for eksempel definere en variabel med denne formelen:

`Set( Radius, 12 )`

Du kan bare bruke **Radius** hvor som helst at du kan bruke et tall, og den vil bli erstattet med **12**:

`Pi() * Power( Radius, 2 )`

Hvis du gir en kontekstvariabel samme navn som en global variabel eller en samling, forrang kontekstvariabelen. Men du kan fremdeles referere til den globale variabelen eller samling Hvis du bruker den [tvetydighetsoperatoren](functions/operators.md#disambiguation-operator) **@[Radius]**.

## <a name="use-a-context-variable"></a>Bruk en kontekstvariabel

La oss se på hvordan kalkulatoren vår vil opprettes ved hjelp av en kontekstvariabel i stedet for en global variabel.

Slik fungerer kontekstvariablene:

* Du må opprette og angir kontekstvariablene ved hjelp av implisitt den **[UpdateContext](functions/function-updatecontext.md)** eller **[Navigate](functions/function-navigate.md)** funksjonen. Når appen starter, startverdien for alle kontekstvariabler er *tom*.
* Du oppdaterer kontekstvariablene med poster. I andre programmeringsverktøy bruker du vanligvis "=" for tildeling, som i "x = 1". For kontekstvariablene kan bruke **{x: 1}** i stedet. Når du bruker en kontekstvariabel, kan du bruke navnet direkte uten syntaksen for posten.
* Du kan også angi en kontekstvariabel når du bruker den **[Navigate](functions/function-navigate.md)** funksjonen for å vise en skjerm. Hvis du tror på en skjerm som en slags prosedyre eller delrutine, denne fremgangsmåten ligner på parameteroverføring i andre programmeringsverktøy.
* Kontekstvariablene er begrenset til konteksten for en enkelt skjerm, som er hvor de får navnet sitt fra, med unntak av **[Navigate](functions/function-navigate.md)**. Du kan ikke bruke eller angi dem utenfor denne konteksten.
* Kontekstvariabler kan inneholde en hvilken som helst verdi, inkludert strenger, tall, poster, og [tabeller](working-with-tables.md).

La oss gjenoppbygge kalkulatoren vår ved hjelp av en kontekstvariabel:

1. Legg til en inndata-kontroll kalt **TextInput1**, og to knapper, kalt **Button1** og **Button2**.

2. Angi **[Tekst](controls/properties-core.md)**-egenskapen for **Button1** til **Legg til**, og angi **Tekst**-egenskapen for **Button2** til **Tøm**.

3. For å oppdatere den løpende summen hver gang en bruker velger **Legg til**-knappen, kan du angi **[OnSelect](controls/properties-core.md)**-egenskapen til denne formelen:

    **UpdateContext ({RunningTotal: RunningTotal + TextInput1})**

    Bare forekomster av denne formelen oppretter **RunningTotal** som en kontekstvariabel som inneholder et tall grunn av den **+** operatoren. Du kan referere til **RunningTotal** hvor som helst i dette skjermbildet. Hver gang brukeren åpner denne appen, **RunningTotal** har en opprinnelig verdi for *tom*.

    Første gang som brukeren velger den **Legg til** knappen og **[UpdateContext](functions/function-updatecontext.md)** kjører, **RunningTotal** er satt til verdien **RunningTotal + TextInput1**.

    ![OnSelect-egenskapen for knappen Legg til](media/working-with-variables/context-variable-1.png)

4. For å angi den løpende totalsummen til **0** hver gang en bruker velger **Tøm**-knappen, kan du angi **[OnSelect](controls/properties-core.md)**-egenskapen til denne formelen:

    **UpdateContext ({RunningTotal: 0 } )**

    På nytt, **[UpdateContext](functions/function-updatecontext.md)** brukes med formelen **UpdateContext ({RunningTotal: 0 } )**.

    ![OnSelect-egenskapen til fjern-knapp](media/working-with-variables/context-variable-2.png)

5. Legg til en **[Etikett](controls/control-text-box.md)**-kontroll, og angi **[Tekst](controls/properties-core.md)**-egenskapen til **RunningTotal**.

    Denne formelen beregnes automatisk og viser brukeren verdien av **RunningTotal** samtidig med at den endres basert på knappene som brukeren velger.

    ![Text-egenskapen for etikett](media/working-with-variables/context-variable-3.png)

6. Forhåndsvis appen, og så har vi kalkulatoren vår som beskrevet ovenfor. Skriv inn et tall i tekstboksen og trykk på **Legg til**-knappen flere ganger. Når du er klar kan du gå tilbake til redigeringsopplevelsen ved hjelp av ESC.

    ![Tekstinndata-kontrollen viser en verdi, og etiketten viser løpende total](media/working-with-variables/context-variable-4.png)

7. Du kan angi verdien til en kontekstvariabel mens du navigerer til en skjerm. Dette er nyttig for å overføre «kontekst» eller «parametere» fra en skjerm til en annen. For å demonstrere denne teknikken, må du sette inn en skjerm, sette inn en knapp, og angi dens **OnSelect** egenskapen til denne formelen:

    **Navigate( Screen1, None, { RunningTotal: -1000 } )**

    ![OnSelect-egenskapen for en knapp](media/working-with-variables/context-variable-5.png)

    Hold nede Alt-tasten mens du velger denne knappen for å både Vis **Screen1** og angi kontekstvariabelen **RunningTotal** til-1000.

    ![Screen1 er åpen](media/working-with-variables/context-variable-6.png)

8. For å vise verdien for kontekstvariabelen, velg den **filen** -menyen, og velg deretter **variabler** i ruten til venstre.

    ![Variabler-alternativet i Fil-menyen](media/working-with-variables/context-variable-file-1.png)

9. Hvis du vil vise hvor kontekstvariabelen defineres og brukes, velger du den.

    ![Liste over hvor en variabel er brukt](media/working-with-variables/context-variable-file-2.png)

## <a name="use-a-collection"></a>Bruk en samling

Til slutt skal vi se på å opprette vår egen kalkulator med en samling.  Siden en samling inneholder en tabell som er enkel å endre, kan vi få denne kalkulatoren til å beholde et «listepapir» for hver verdi, etter som de blir registrert.

Slik fungerer samlinger:

* Opprett og angi samlinger ved å bruke **[ClearCollect](functions/function-clear-collect-clearcollect.md)**-funksjonen.  Du kan også bruke **[Collect](functions/function-clear-collect-clearcollect.md)**-funksjonen, men den vil effektivt kreve en annen variabel i stedet for å erstatte den gamle.  
* En samling er en type datakilde, og derfor en tabell. Hvis du vil ha tilgang til en enkelt verdi i en samling, kan du bruke **[First](functions/function-first-last.md)**-funksjonen, og trekke ut et felt fra den resulterende posten. Hvis du har brukt en enkeltverdi med **[ClearCollect](functions/function-clear-collect-clearcollect.md)**, vil dette være **Verdi**-feltet, som i dette eksemplet:<br>
**First(** *VariableName* **).Value**

La oss opprette kalkulatoren vår ved å bruke en samling:

1. Legg til en **[Tekstinndata](controls/control-text-input.md)**-kontroll, kalt **TextInput1**, og to knapper, kalt **Button1** og **Button2**.

2. Angi **[Tekst](controls/properties-core.md)**-egenskapen for **Button1** til **«Legg til»**, og angi **Tekst**-egenskapen for **Button2** til **«Tøm»**.

3. For å oppdatere den løpende summen hver gang en bruker velger **Legg til**-knappen, kan du angi **[OnSelect](controls/properties-core.md)**-egenskapen til denne formelen:

    **Collect( PaperTape, TextInput1.Text )**

    Bare forekomster av denne formelen oppretter **PaperTape** som en samling som inneholder en enkeltkolonne-tabell med tekststrenger. Du kan referere til **PaperTape** hvor som helst i denne appen. Hver gang en bruker åpner denne appen, **PaperTape** er en tom tabell.

    Når denne formelen kjører, legges det til den nye verdien til slutten av samlingen. Fordi vi legger til en enkelt verdi, **samle inn** automatisk plassere dataene i en enkeltkolonne-tabell, og navnet på den kolonnen er **verdien**, som du vil bruke senere.

    ![OnSelect-egenskapen for knappen Legg til](media/working-with-variables/papertape-1.png)

4. Å fjerne listepapir når brukeren velger den **fjerner** knappen, kan du angi dens **[OnSelect](controls/properties-core.md)** egenskapen til denne formelen:

    **Clear( PaperTape )**

    ![OnSelect-egenskapen til fjern-knapp](media/working-with-variables/papertape-2.png)

5. Legg til en etikett og angi **[Tekst](controls/properties-core.md)**-egenskapen til denne formelen for å vise den løpende summen:

    **Sum( PaperTape, Value )**

    ![Text-egenskapen for etiketten](media/working-with-variables/papertape-3.png)

6. Trykk på F5 for å åpne forhåndsvisning, skriv inn tall i tekstinndata-kontrollen, og velg knapper, hvis du vil kjøre kalkulatoren.

    ![Tekstinndata-kontrollen viser en verdi, og etiketten vises den løpende summen](media/working-with-variables/papertape-run-1.png)

7. Trykk på ESC for å gå tilbake til standardarbeidsområdet.

8. Hvis du vil vise listepapir, kan du sette inn en **Datatabell**-kontroll, og angi **[Elementer](controls/properties-core.md)**-egenskapen til denne formelen:

    **PaperTape**

    I den høyre ruten, velger du den **verdien** kolonnen for å vise den.

    ![Datatabell som viser verdiene som legges til i samlingen](media/working-with-variables/papertape-4.png)

9. Hvis du vil se verdiene i samlingen, kan du velge **Samlinger** på **Fil**-menyen.

    ![Forhåndsvisning av samlingen PaperTape](media/working-with-variables/papertape-file.png)

10. Å lagre og hente samlingen, Legg til to ekstra knapp-kontroller, og angi deres **tekst** egenskaper til **Load** og **lagre**. Angi den **OnSelect** -egenskapen for den **Load** knappen til denne formelen:

     **Clear( PaperTape ); LoadData( PaperTape, "StoredPaperTape", true )**

     Du må slette samlingen først fordi **LoadData** vil tilføye de lagrede verdiene til slutten av samlingen.

     ![OnSelect-egenskapen til Last inn](media/working-with-variables/papertape-5.png)

11. Angi den **OnSelect** -egenskapen for den **lagre** knappen til denne formelen:

     **SaveData( PaperTape, "StoredPaperTape" )**

     ![OnSelect *-egenskapen til lagre-knappen](media/working-with-variables/papertape-6.png)

12. Forhåndsvis på nytt ved å trykke på F5, skriv inn tall i Tekstinndata-kontrollen, og velg knapper. Velg **Lagre**-knappen. Lukk og Last inn appen på nytt, og velg den **Load** knappen for å laste inn samlingen på nytt.

> [!NOTE]
> **SaveData** og **LoadData** -funksjonen i PowerApps Mobile, men ikke PowerApps Studio eller nettspiller for PowerApps.