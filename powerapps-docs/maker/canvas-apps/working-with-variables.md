---
title: Å forstå variabler | Microsoft Docs
description: Referanseinformasjon for å arbeide med tilstand, kontekstvariabler og samlinger
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 07/06/2017
ms.author: gregli
ms.openlocfilehash: b5986c927b75ed7a6e38af913cbfb9877121d0a5
ms.sourcegitcommit: dfa0e1a7981814e15e6ca4720e2a5f930e859db1
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 07/13/2018
ms.locfileid: "39017828"
---
# <a name="understand-variables-in-powerapps"></a>Å forstå variabler i PowerApps
Hvis du har brukt et annet programmeringsverktøy, for eksempel Visual Basic eller JavaScript, kan det hende du spør: **hvor er variablene?** PowerApps er litt annerledes, og krever en annen fremgangsmåte. I stedet for hente en variabel, kan du stille deg selv spørsmålet: **Hva ville jeg gjort i Excel?**

I andre verktøy kan du kanskje eksplisitt ha utført en beregning og lagret resultatet i en variabel. PowerApps og Excel omberegner imidlertid automatisk formler etter som inndataene endres, slik at du vanligvis ikke trenger å opprette og oppdatere variabler. Ved å følge denne fremgangsmåten når det er mulig, kan du enklere opprette, forstå og vedlikeholde appen.

I noen tilfeller må du bruke variabler i PowerApps, noe som utvider Excel sin modell ved å legge til [formler for virkemåte](working-with-formulas-in-depth.md). Disse formlene kjøres for eksempel når en bruker velger en knapp. I en formel for virkemåte, er det er ofte nyttig å angi en variabel som skal brukes i andre formler.

Generelt bør du unngå å bruke variabler. Men noen ganger er det bare en variabel som kan aktivere opplevelsen som du vil ha.

## <a name="translate-excel-into-powerapps"></a>Å oversette Excel til PowerApps
### <a name="excel"></a>Excel
La oss gå gjennom hvordan Excel fungerer. En celle kan inneholde en verdi, for eksempel et tall eller en streng, eller en formel som er basert på verdiene i andre celler. Etter at brukeren angir en annen verdi i en celle, vil Excel automatisk beregne formler som er avhengige av den nye verdien på nytt. Du trenger å gjøre noe programmering for å aktivere denne virkemåten.

![](media/working-with-variables/excel-recalc.png)

Excel har ikke variabler. Verdien til en celle som inneholder en formel endres basert på inndataene, men det finnes ingen måte å huske resultatet av en formel på og lagre dem i en celle, eller noen andre steder. Hele regnearket endres og alle tidligere beregnede verdier går tapt, hvis du endrer verdien for en celle.  En Excel-bruker kan kopiere og lime inn celler, men det er noe brukeren kontrollerer manuelt og er ikke mulig med formler.

### <a name="powerapps"></a>PowerApps
Apper du oppretter i PowerApps, fungerer omtrent på samme måte som Excel. I stedet for å oppdatere celler, kan du legge til kontroller hvor som helst på en skjerm og navngi dem for bruk i formler.

Du kan for eksempel gjenskape virkemåten til Excel i en app ved å legge til en **[Etikett](controls/control-text-box.md)**-kontroll, kalt **TextBox1**, og to **[Tekstinndata](controls/control-text-input.md)**-kontroller, kalt **TextInput1** og **TextInput2**. Hvis du deretter setter **[Tekst](controls/properties-core.md)**-egenskapen for **Tekstboks1** til **TextInput1 + TextInput2**, vil den alltid vise summen av tallet som er i **TextInput1** og **TextInput2** automatisk.

![](media/working-with-variables/recalc1.png)

Legg merke til at **Tekstboks1**-kontrollen som er valgt, viser **[Tekst](controls/properties-core.md)**-formelen i formellinjen øverst på skjermen.  Her finner vi formelen **TextInput1 + TextInput2**.  Denne formelen oppretter en avhengighet mellom disse kontrollene, på samme måte som avhengigheter opprettes mellom cellene i en Excel-arbeidsbok.  La oss endre verdien av **TextInput1**:

![](media/working-with-variables/recalc2.png)

Formelen for **TextBox1** har blitt automatisk beregnet på nytt, og viser den nye verdien.

I PowerApps kan du bruke formler til å bestemme, ikke bare den primære verdien av en kontroll, men også egenskaper som formatering. I eksemplet nedenfor er en formel for **[Farge](controls/properties-color-border.md)**-egenskapen for etiketten som automatisk viser negative verdier i rødt. **[If](functions/function-if.md)**-funksjonen bør du kunne kjenne igjen fra Excel:
<br>**If( Value(TextBox1.Text) < 0, Red, Black )**

![](media/working-with-variables/recalc-color1.png)

Hvis resultatet av våre beregningen i **TextBox1.Text** er negativ, blir tallet vist i rødt:

![](media/working-with-variables/recalc-color2.png)

Du kan bruke formler for et bredt utvalg av scenarioer:

* En kartkontroll kan vise den gjeldende posisjonen din med en formel som bruker **Location.Latitude** og **Location.Longitude** ved hjelp av enhetens GPS.  Kartet sporer automatisk plasseringen din, når du flytter på deg.
* Andre brukere kan oppdatere [datakilder](working-with-data-sources.md).  Andre i gruppen kan kanskje for eksempel oppdatere elementer i en SharePoint-liste.  Når du oppdaterer en datakilde, beregnes automatisk alle avhengige formler for å gjenspeile de oppdaterte dataene. Videre kan du kanskje angi **[Elementer](controls/properties-core.md)**-egenskapen i et galleri til formelen **Filter (SharePointList)**, som automatisk viser det nylig filtrerte settet med [poster](working-with-tables.md#records).

### <a name="benefits"></a>Fordeler
Det er mange fordeler med å bruke formler til å bygge apper:

* Hvis du kjenner Excel, kjenner du også PowerApps. Modellen og formelspråket er det samme.
* Hvis du har brukt andre programmeringsverktøy, kan du tenke deg hvor mye kode som ville vært nødvendig for å fullføre disse eksemplene.  I Visual Basic måtte du ha skrevet en hendelsesbehandling for endringshendelsen på hver kontroll for tekstinndata.  Koden for å utføre beregningen i hver av disse er overflødig og kan komme ut av balanse, eller du måtte ha skrevet en felles delrutine.  Du oppnådde alt dette med en enkelt, én-linje formel i PowerApps.
* For å forstå hvor teksten i **Tekstboks1** kommer fra, vet du nøyaktig hvor du skal lete: formelen i **[Tekst](controls/properties-core.md)**-egenskapen.  Det finnes ingen annen måte å påvirke teksten i kontrollen.  I et tradisjonelt programmeringsverktøy kan eventuelle hendelsesbehandlinger eller delrutiner endre verdien for etiketten, fra hvor som helst i programmet.  Dette kan gjøre det vanskelig å spore når og hvor en variabel ble endret.
* Hvis brukeren endrer en glidebryteren og deretter ombestemmer seg, kan de endre glidebryteren tilbake til den opprinnelige verdien.  Og det er som om ingenting ble endret: appen viser de samme kontrollverdiene som den gjorde før.  Det er ingen konsekvenser for å eksperimentere og spørre «hva om», på samme måte som i Excel.  

Du vil vanligvis komme bedre ut av det, hvis du kan oppnå en effekt ved hjelp av en formel. La formelmotoren i PowerApps arbeide for deg.  

## <a name="know-when-to-use-variables"></a>Slik vet du når du skal bruke variabler
La oss endre den enkle kalkulatoren til å fungere som en gammeldags kalkulator, med en løpende sum. Hvis du velger en **Legg til**-knapp, skal du legge til et tall til den løpende summen. Hvis du velger en **Tøm**-knapp, vil du tilbakestille den løpende totalsummen til null.

![](media/working-with-variables/button-changes-state.png)

Kalkulatoren bruker noe som ikke finnes i Excel: en knapp. I denne appen kan du ikke bruke bare formler til å beregne den løpende summen, fordi verdien avhenger av en serie med handlinger som brukeren gjør. Den løpende summen må i stedet registreres og oppdateres manuelt. De fleste programmeringsverktøy lagrer denne informasjonen i en *variabel*.    

Noen ganger trenger du en variabel for at appen skal oppføre seg slik du ønsker.  Men tilnærmingen leveres med advarsler:

* Du må oppdatere den løpende summen manuelt. Automatisk omberegning gjør ikke dette for deg.
* Den løpende summen kan ikke lenger beregnes basert på verdiene i andre kontroller. Det avhenger av hvor mange ganger brukeren valgte **Legg til**-knappen, og hvilken verdi som var i kontrollen for tekstinndata hver gang. Angav brukeren 77, og valgte **Legg til** to ganger, eller angav de 24 og 130 for hvert av tilleggene? Du kan ikke se forskjell når summen har nådd 154.
* Endringer i totalen kan komme fra forskjellige baner. I dette eksemplet kan både **Legg til-** og **Fjern**-knappene oppdatere summen. Hvilken knapp forårsaker problemet, hvis appen ikke fungerer slik du forventer?

## <a name="create-a-global-variable"></a>Å opprette en global variabel
Vi krever en variabel som inneholder den løpende summen, hvis du vil opprette kalkulatoren. De enkleste variablene å arbeide med i PowerApps er *globale variabler*.  

Slik fungerer globale variabler:

* Du kan angi verdien for den globale variabelen med **[Set](functions/function-set.md)**-funksjonen.  **Set(MyVar, 1)** angir den globale variabelen **MyVar** til en verdi på **1**.
* Du bruker den globale variabelen ved å referere til navnet som brukes med **Set**-funksjonen.  **MyVar** vil returnere **1** i dette tilfellet.
* Globale variabler kan inneholde en hvilken som helst verdi, inkludert strenger, tall, poster, og [tabeller](working-with-tables.md).

La oss gjenoppbygge kalkulatoren vår ved hjelp av en global variabel:

1. Legg til en inndata-kontroll kalt **TextInput1**, og to knapper, kalt **Button1** og **Button2**.

2. Angi **[Tekst](controls/properties-core.md)**-egenskapen for **Button1** til **Legg til**, og angi **Tekst**-egenskapen for **Button2** til **Tøm**.

3. For å oppdatere den løpende summen hver gang en bruker velger **Legg til**-knappen, kan du angi **[OnSelect](controls/properties-core.md)**-egenskapen til denne formelen:
   
    **Set( RunningTotal, RunningTotal + Text1 )**
   
    Første gang en bruker velger **Legg til**-knappen og kaller på **[Angi](functions/function-set.md)**, blir **RunningTotal** opprettet med en standardverdi på *tom*.  I tillegg blir den behandlet som en null.
   
    ![](media/working-with-variables/global-variable-1.png)
4. For å angi den løpende totalsummen til **0** hver gang en bruker velger **Tøm**-knappen, kan du angi **[OnSelect](controls/properties-core.md)**-egenskapen til denne formelen:
   
    **Set( RunningTotal, 0 )**
   
    ![](media/working-with-variables/global-variable-2.png)
5. Legg til en **[Etikett](controls/control-text-box.md)**-kontroll, og angi **[Tekst](controls/properties-core.md)**-egenskapen til **RunningTotal**.
   
    Denne formelen beregnes automatisk og viser brukeren verdien av **RunningTotal** samtidig med at den endres basert på knappene som brukeren velger.
   
    ![](media/working-with-variables/global-variable-3.png)
6. Forhåndsvis appen, og så har vi kalkulatoren vår som beskrevet ovenfor.  Skriv inn et tall i tekstboksen og trykk på **Legg til**-knappen flere ganger.  Når du er klar kan du gå tilbake til redigeringsopplevelsen ved hjelp av ESC.  
   
    ![](media/working-with-variables/global-variable-4.png)
7. Velg **Fil**-menyen, og velg **Variabler** i den venstre ruten, for å se vår globale variabelverdi.
   
    ![](media/working-with-variables/global-variable-file-1.png)
8. Hvis du vil se alle steder der variabelen blir definert og brukt, velger du den.
   
    ![](media/working-with-variables/global-variable-file-2.png)

## <a name="types-of-variables"></a>Ulike typer variabler
Det finnes tre typer variabler i PowerApps:

| Variabeltype | Område | Beskrivelse | Funksjoner |
| --- | --- | --- | --- |
| Globale variabler |App |Enklest å bruke.  Inneholder et tall, en tekststreng, Boolean, post, tabell, osv. som kan være referanser fra hvor som helst i appen. |[**Angi**](functions/function-set.md) |
| Kontekstvariabler |Skjerm |Bra for å sende verdier til en skjerm, omtrent som parametere er til en prosedyre i andre språk.  Kan bare refereres fra en skjerm. |[**UpdateContext**](functions/function-navigate.md) |
| Samlinger |App |Inneholder en tabell som kan være referanser fra hvor som helst i appen.  Tillater innholdet i tabellen å endres, i stedet for å angis i sin helhet. Du kan lagre til den lokale enheten for senere bruk. |[**Collect**](functions/function-savedata-loaddata.md)<br>osv. |

Alle variabler opprettes implisitt når de brukes i funksjonene **Set**, **UpdateContext**, **Navigate** eller **Collect**.  Det er ingen eksplisitt deklarasjon av variabler som gjøres i andre programmeringsverktøy.  Typer av variablene avledes også implisitt fra verdier som er plassert i dem.

Alle variabler beholdes i minnet mens appen kjører.  Verdiene som holdes i variabler, går tapt etter at appen lukkes.  Du kan lagre innholdet i en variabel i en datakilde ved hjelp av funksjonene **Patch** eller **Collect**, eller du kan lagre til den lokale enheten med **SaveData**-funksjonen når det gjelder samlinger.  Når appen først lastes inn, har alle variabler en *tom* verdi.

Du kan bruke navnene på variablene til å lese verdien.  For eksempel Når **Set( MyColor, Red )** er definert kan du for eksempel bruke **MyVar** hvor som helst fargeverdien kan brukes, og den vil bli erstattet med **rødt**.  Det er mulig å ha en global variabel, eller en samling, med samme navn som en kontekstvariabel.  I dette tilfellet vil kontekstvariabelen ha prioritet.  Du kan fremdeles referere til den globale variabelen eller samling ved hjelp av [tvetydighetsoperatoren](functions/operators.md#disambiguation-operator) **@[MyColor]**.

## <a name="create-a-context-variable"></a>Å opprette en kontekstvariabel
La oss se på hvordan kalkulatoren vår vil opprettes ved hjelp av en kontekstvariabel i stedet for en global variabel.    

Slik fungerer kontekstvariablene:

* Du oppretter og angir kontekstvariablene ved hjelp av **[UpdateContext](functions/function-updatecontext.md)**-funksjonen.  Hvis en kontekstvariabel ikke allerede finnes når du først oppdaterer, blir den opprettet med en standardverdi på *tom*.
* Du oppretter og oppdaterer kontekstvariablene med poster. I andre programmeringsverktøy bruker du vanligvis "=" for tildeling, som i "x = 1".  For kontekstvariablene kan du bruke **{x: 1}** i stedet. Når du bruker en kontekstvariabel, må du bruke navnet direkte.  
* Du kan også angi en kontekstvariabel når en skjerm vises, ved hjelp av **[Navigate](functions/function-navigate.md)**-funksjonen. Hvis du tenker på en skjerm som en slags prosedyre eller delrutine, ligner dette på parameteroverføring i andre programmeringsverktøy.
* Kontekstvariablene er begrenset til konteksten for en enkelt skjerm, som er hvor de får navnet sitt fra, med unntak av **[Navigate](functions/function-navigate.md)**.  Du kan ikke bruke eller angi dem utenfor denne konteksten.
* Kontekstvariabler kan inneholde en hvilken som helst verdi, inkludert strenger, tall, poster, og [tabeller](working-with-tables.md).

La oss gjenoppbygge kalkulatoren vår ved hjelp av en kontekstvariabel:

1. Legg til en inndata-kontroll kalt **TextInput1**, og to knapper, kalt **Button1** og **Button2**.

2. Angi **[Tekst](controls/properties-core.md)**-egenskapen for **Button1** til **Legg til**, og angi **Tekst**-egenskapen for **Button2** til **Tøm**.

3. For å oppdatere den løpende summen hver gang en bruker velger **Legg til**-knappen, kan du angi **[OnSelect](controls/properties-core.md)**-egenskapen til denne formelen:
   
    **UpdateContext( { RunningTotal: RunningTotal + Text1 } )**
   
    Første gang en bruker velger **Legg til**-knappen og kaller på **[UpdateContext](functions/function-updatecontext.md)**, blir **RunningTotal** opprettet med en standardverdi på *tom*.  I tillegg blir den behandlet som en null.
   
    ![](media/working-with-variables/context-variable-1.png)
4. For å angi den løpende totalsummen til **0** hver gang en bruker velger **Tøm**-knappen, kan du angi **[OnSelect](controls/properties-core.md)**-egenskapen til denne formelen:
   
    **UpdateContext( { RunningTotal: 0 } )**
   
    På nytt ser vi at **[UpdateContext](functions/function-updatecontext.md)** brukes med formelen **UpdateContext( { RunningTotal: 0 } )**.
   
    ![](media/working-with-variables/context-variable-2.png)
5. Legg til en **[Etikett](controls/control-text-box.md)**-kontroll, og angi **[Tekst](controls/properties-core.md)**-egenskapen til **RunningTotal**.
   
    Denne formelen beregnes automatisk og viser brukeren verdien av **RunningTotal** samtidig med at den endres basert på knappene som brukeren velger.
   
    ![](media/working-with-variables/context-variable-3.png)
6. Forhåndsvis appen, og så har vi kalkulatoren vår som beskrevet ovenfor.  Skriv inn et tall i tekstboksen og trykk på **Legg til**-knappen flere ganger.  Når du er klar kan du gå tilbake til redigeringsopplevelsen ved hjelp av ESC.  
   
    ![](media/working-with-variables/context-variable-4.png)
7. Du kan angi verdien til en kontekstvariabel mens du navigerer til en skjerm.  Dette er nyttig for å overføre «kontekst» eller «parametere» fra en skjerm til en annen.  Hvis du vil se dette, kan du sette inn en ny skjerm, og sette inn en knapp med **OnSelect**-egenskapen satt til:
   
    **Navigate( Screen1, None, { RunningTotal: -1000 } )**
   
    ![](media/working-with-variables/context-variable-5.png)
   
    Hvis du velger denne knappen på **Skjerm2** (som du kan gjøre samtidig med at du redigerer, hvis du velger knappen på enden) vises **Skjerm1**, og angir også kontekstvariabelen **RunningTotal** til -1000.
   
    ![](media/working-with-variables/context-variable-6.png)
8. Velg **Fil**-menyen, og velg **Variabler** i den venstre ruten, for å se verdien for kontekstvariabelen.
   
    ![](media/working-with-variables/context-variable-file-1.png)
9. Hvis du vil se hvor kontekstvariabelen defineres og brukes, velger du den.
   
    ![](media/working-with-variables/context-variable-file-2.png)

## <a name="create-a-collection"></a>Opprett en samling
Til slutt skal vi se på å opprette vår egen kalkulator med en samling.  Siden en samling inneholder en tabell som er enkel å endre, kan vi få denne kalkulatoren til å beholde et «listepapir» for hver verdi, etter som de blir registrert.

Slik fungerer samlinger:

* Opprett og angi samlinger ved å bruke **[ClearCollect](functions/function-clear-collect-clearcollect.md)**-funksjonen.  Du kan også bruke **[Collect](functions/function-clear-collect-clearcollect.md)**-funksjonen, men den vil effektivt kreve en annen variabel i stedet for å erstatte den gamle.  
* En samling er en type datakilde, og derfor en tabell. Hvis du vil ha tilgang til en enkelt verdi i en samling, kan du bruke **[First](functions/function-first-last.md)**-funksjonen, og trekke ut et felt fra den resulterende posten. Hvis du har brukt en enkeltverdi med **[ClearCollect](functions/function-clear-collect-clearcollect.md)**, vil dette være **Verdi**-feltet, som i dette eksemplet:<br>**First(** *VariableName* **).Value**

La oss opprette kalkulatoren vår ved å bruke en samling:

1. Legg til en **[Tekstinndata](controls/control-text-input.md)**-kontroll, kalt **TextInput1**, og to knapper, kalt **Button1** og **Button2**.

2. Angi **[Tekst](controls/properties-core.md)**-egenskapen for **Button1** til **«Legg til»**, og angi **Tekst**-egenskapen for **Button2** til **«Tøm»**.

3. For å oppdatere den løpende summen hver gang en bruker velger **Legg til**-knappen, kan du angi **[OnSelect](controls/properties-core.md)**-egenskapen til denne formelen:
   
    **Collect( PaperTape, TextInput1.Text )**
   
    Denne formelen vil legge til den nye verdien til slutten av samlingen.  Ettersom vi legger til en enkelt verdi, vil **Collect** automatisk plassere det i én kolonnetabell med kolonnenavnet **Verdi**, som vi skal bruke senere.
   
    ![](media/working-with-variables/papertape-1.png)
4. Angi **[OnSelect](controls/properties-core.md)**-egenskapen til denne formelen for å tømme listepapiret, når brukeren velger **Tøm**-knappen:
   
    **Clear( PaperTape )**
   
    ![](media/working-with-variables/papertape-2.png)
5. Legg til en etikett og angi **[Tekst](controls/properties-core.md)**-egenskapen til denne formelen for å vise den løpende summen:
   
    **Sum( PaperTape, Value )**
   
    ![](media/working-with-variables/papertape-3.png)
6. Trykk på F5 for å åpne forhåndsvisning, skriv inn tall i tekstinndata-kontrollen, og velg knapper, hvis du vil kjøre kalkulatoren.
   
    ![](media/working-with-variables/papertape-run-1.png)
7. Trykk på ESC for å gå tilbake til standardarbeidsområdet.
8. Hvis du vil vise listepapir, kan du sette inn en **Datatabell**-kontroll, og angi **[Elementer](controls/properties-core.md)**-egenskapen til denne formelen:
   
    **PaperTape**
   
    Du må også velge kolonnene du vil vise i den høyre ruten, og i vårt tilfelle kan du vise **Verdi**-kolonnen:
   
    ![](media/working-with-variables/papertape-4.png)
9. Hvis du vil se verdiene i samlingen, kan du velge **Samlinger** på **Fil**-menyen.
   
    ![](media/working-with-variables/papertape-file.png)
10. Legg til to ekstra knapp-kontroller og angi teksten til **Last inn** og **Lagre**, hvis du vil lagre og hente samlingen.  For **Last inn**, kan du angi **OnSelect** til:
    
     **Clear( PaperTape ); LoadData( PaperTape, "StoredPaperTape", true )**
    
     Vi må tømme samlingen først, siden **LoadData** vil tilføye de lagrede verdiene til slutten av samlingen.
    
     ![](media/working-with-variables/papertape-5.png)
11. For **Lagre**, kan du angi **OnSelect** til:
    
     **SaveData( PaperTape, "StoredPaperTape" )**
    
     ![](media/working-with-variables/papertape-6.png)
12. Forhåndsvis på nytt ved å trykke på F5, skriv inn tall i Tekstinndata-kontrollen, og velg knapper.  Velg **Lagre**-knappen.  Lukk og last inn appen, og velg **Last inn**-knappen for å laste inn samlingen på nytt.  
    
    > [!NOTE]
    > **SaveData** og **LoadData** fungerer ikke i PowerApps Studio, men de gjør det i PowerApps Mobile.

