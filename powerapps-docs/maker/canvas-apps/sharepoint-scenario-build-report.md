---
title: Å opprette en Power BI-rapport for å analysere prosjekter i Microsoft Docs
description: I denne oppgaven skal vi opprette en Power BI-rapport basert på to SharePoint-lister.
author: fikaradz
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 01/10/2018
ms.author: fikaradz
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 7eb5e7385c57e0cabaab1c8457f17dc1feff96fb
ms.sourcegitcommit: c52c1869510a9a37d9f7b127e06f07583529588b
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/28/2019
ms.locfileid: "64671039"
---
# <a name="create-a-power-bi-report-to-analyze-projects"></a>Å opprette en Power BI-rapport for å analysere prosjekter
> [!NOTE]
> Denne artikkelen er en del av en opplæringsserie om hvordan du bruker PowerApps, Microsoft Flow og Power BI med SharePoint Online. Sørg for å lese [serieinnføringen](sharepoint-scenario-intro.md) for å få et inntrykk av det store bildet, i tillegg til relaterte nedlastinger.

I denne oppgaven skal vi opprette en Power BI-rapport basert på de to SharePoint-listene. Vi skal hente listedata inn i Power BI Desktop og bearbeide dem litt, utføre litt grunnleggende datamodellering, og opprette et sett med visualobjekter som forteller oss noe om dataene.

> [!TIP]
> [Nedlastingspakken](https://aka.ms/o4ia0f) for dette scenarioet inkluderer en fullført versjon av denne rapporten: project-analysis.pbix.

## <a name="quick-review-of-power-bi-desktop"></a>Rask gjennomgang av Power BI Desktop
Før vi tar for oss rapportopprettelsen, skal vi gå gjennom Power BI Desktop. Dette er et kraftfullt verktøy med mange funksjoner, så vi skal fokusere på en oversikt over det du skal bruke for denne oppgaven. Det er tre hovedarbeidsområder eller *visninger* i Power BI Desktop: **Rapporten** visning, **Data** visning, og **relasjoner** visning. Power BI Desktop inkluderer også **Redigeringsprogram for spørring**, som åpnes i et eget vindu.

Det følgende skjermbildet viser de tre visningsikonene til venstre i Power BI Desktop: **Rapporten**, **Data**, og **relasjoner**, fra topp til bunn. Den gule linjen til venstre angir den gjeldende visningen, som i dette tilfellet er **Rapportvisning**. Du endrer visningene ved å velge ett av disse tre ikonene.

![Visninger i Power BI Desktop](./media/sharepoint-scenario-build-report/05-00-00-tabs.png)

**Rapportvisningen** har fem hovedområder:

1. Båndet, som viser vanlige oppgaver forbundet med rapporter og visualiseringer.
2. **Rapportvisningen**, eller arbeidssonen, der visualiseringer opprettes og ordnes.
3. Faneområdet **Sider** langs bunnen, der du kan velge eller legge til en rapportside.
4. **Visualiseringer**-ruten, hvor du endrer visualiseringer, tilpasser farger eller akser, bruker filtre, drar felter og mer.
5. **Felter**-ruten, hvor du kan dra spørringselementer og filtre over på **Rapportvisningen** eller til **Filtre**-området i **Visualiseringer**-ruten.

![Faner, visninger og ruter i Power BI Desktop](./media/sharepoint-scenario-build-report/05-00-01-report.png)

**Data**-visningen har tre hovedområder:

1. Båndet, der **Modellering**-fanen er valgt nedenfor. På denne fanen oppretter du tabeller og kolonner, og foretar andre endringer for datamodellen.
2. Den midtre ruten, som viser data for den valgte tabellen.
3. **Felter**-ruten, hvor du kontrollerer hvordan feltene vises i rapportene.

![Datavisningen i Power BI Desktop](./media/sharepoint-scenario-build-report/05-00-02-data.png)

Vi bruker ikke **Relasjoner**-visningen i denne oppgaven, men du kan finne ut mer om den etter at vi henter inn listedataene i Power BI Desktop.

I **Redigeringsprogram for spørring** bygger du spørringer og transformerer data, og deretter laster du inn den forbedrede datamodellen i Power BI Desktop. **Redigeringsprogram for spørring** har fire hovedområder:

1. Båndet, som har mange alternativer for å forme og transformere dataene som du henter inn.
2. Den venstre ruten, hvor spørringer er oppført og tilgjengelig for utvalg, visning og forming.
3. Den midtre ruten, hvor data fra den utvalgte spørringen vises og er tilgjengelig for forming.
4. Vinduet **Spørringsinnstillinger**, som viser egenskapene for spørringene og utførte datatransformasjonstrinn.

![Redigeringsprogram for spørring for Power BI Desktop](./media/sharepoint-scenario-build-report/05-00-03-query.png)

## <a name="step-1-get-data-into-power-bi-desktop"></a>Trinn 1: Hente data i Power BI Desktop
I dette trinnet skal vi først koble til de to listene. Deretter skal vi ordne dataene ved å fjerne kolonner vi ikke trenger for våre dataanalyser. Vi skal også endre datatypene til noen av de gjenværende kolonnene slik at beregningene fungerer. Hvis du vil ha mer informasjon om hvordan du ordner data i Power BI Desktop, kan du se [Hente data](https://powerbi.microsoft.com/guided-learning/powerbi-learning-1-1-overview-of-power-bi-desktop)-delen i Veiledet opplæring-kurset.

### <a name="connect-to-sharepoint-lists"></a>Å koble til SharePoint-lister
1. Trykk eller klikk på **Hent data** og deretter på **Mer…** på **Hjem**-fanen i Power BI Desktop
   
    ![Å hente data](./media/sharepoint-scenario-build-report/05-01-01-get-data.png)
2. Klikk eller trykk på **SharePoint Online-liste** og deretter på **Koble til** i dialogboksen **Hent data**.
   
    ![Å koble til en SharePoint-liste](./media/sharepoint-scenario-build-report/05-01-02-sharepoint-list.png)
3. Angi nettadressen for SharePoint-området, og klikk eller trykk deretter på **OK**.
   
    ![Nettadresse for SharePoint-liste](./media/sharepoint-scenario-build-report/05-01-03-sharepoint-url.png)
4. Hvis du får opp følgende dialogboks, må du sørge for at du er pålogget med riktig legitimasjon, og deretter klikke eller trykke på **Koble til**.
   
    ![Legitimasjon for SharePoint-liste](./media/sharepoint-scenario-build-report/05-01-04-credentials.png)
5. Velg **Prosjektdetaljer** og **Prosjektforespørsler**, og klikk eller trykk deretter på **Rediger**.
   
    ![Å velge SharePoint-lister](./media/sharepoint-scenario-build-report/05-01-05-list-navigator.png)
   
    Listene vises nå som tabeller i redigeringsprogrammet for spørring.
   
    ![Tabeller i redigeringsprogrammet for spørring](./media/sharepoint-scenario-build-report/05-01-06-query-editor.png)

### <a name="remove-unnecessary-columns-from-the-tables"></a>Å fjerne unødvendige kolonner fra tabellene
1. Klikk eller trykk på **Prosjektdetaljer** i navigasjonsruten til venstre.
2. Velg kolonnen **FileSystemObjectType** i den midtre ruten, og klikk eller trykk deretter på **Fjern kolonner**.
   
    ![Å fjerne kolonner](./media/sharepoint-scenario-build-report/05-01-07-remove-column.png)
3. Fjern de to kolonnene etter den **Id** kolonne: **ServerRedirectedEmbedURL** og **ContentTypeId**. 
   > [!TIP]
   > Bruk SKIFT til å velge begge kolonnene, og klikk eller trykk deretter på **Fjern kolonner**.
4. Fjern alle kolonnene til høyre for **PMAssigned**-kolonnen (totalt 22 kolonner). Tabellen skal samsvare med følgende bilde:
   
    ![Prosjektdetaljer-tabellen i redigeringsprogrammet for spørring](./media/sharepoint-scenario-build-report/05-01-08-table-details.png)
5. Gjenta prosessen du nettopp gjorde, nå for **Prosjektforespørsler**: fjern **FileSystemObjectType**, **ServerRedirectedEmbedURL**, **ContentTypeId** og alle kolonnene til høyre for **Godkjent**-kolonnen (totalt 22 kolonner). Tabellen skal samsvare med følgende bilde:
   
    ![ Prosjektforespørsler-tabellen i redigeringsprogrammet for spørring](./media/sharepoint-scenario-build-report/05-01-09-table-requests.png)

### <a name="change-the-data-type-on-project-details-columns"></a>Å endre datatypen i Prosjektdetaljer-kolonnene
1. Velg den **ProjectedDays** kolonnen, klikk eller trykk på **datatype: En hvilken som helst**, deretter **heltall**.
   
    ![Å endre datatypen til et heltall](./media/sharepoint-scenario-build-report/05-01-10-datatype-number.png)
2. Gjenta forrige trinn for **ActualDays**-kolonnen.
3. Velg den **ApprovedDate** kolonnen, klikk eller trykk på **datatype: En hvilken som helst**, deretter **dato**.
   
    ![ Å endre datatype til dato](./media/sharepoint-scenario-build-report/05-01-11-datatype-date.png)

4. Gjenta det forrige trinnet for **ProjectedStartDate**- og **ProjectedEndDate**-kolonnene.

### <a name="change-the-data-type-on-project-requests-columns"></a>Å endre datatypen i Prosjektforespørsler-kolonnene

1. Velg den **EstimatedDays** kolonnen, klikk eller trykk på **datatype: En hvilken som helst**, deretter **heltall**.

2. Velg den **RequestDate** kolonnen, klikk eller trykk på **datatype: En hvilken som helst**, deretter **dato**.

### <a name="apply-and-save-changes"></a>Å bruke og lagre endringer

1. Klikk eller trykk på **Lukk og bruk** på **Hjem**-fanen for å lukke redigeringsprogrammet for spørring og gå tilbake til hovedvinduet til Power BI Desktop.
   
    ![Å lukke og bruke endringer](./media/sharepoint-scenario-build-report/05-01-12-close-apply.png)

2. Klikk eller trykk på **Fil** og deretter på **Lagre**, og lagre med navnet project-analysis.pbix.

## <a name="step-2-improve-the-data-model"></a>Trinn 2: Forbedre datamodellen
Nå som vi har hentet inn dataene fra våre SharePoint-lister og til Power BI Desktop, skal vi ta for oss datamodellering. Datamodellering kan være en tidkrevende prosess, men vi skal raskt vise deg noen interessante ting du kan gjøre for å få mer ut av listedataene i Power BI Desktop:

* Å endre hvordan to tabeller er relatert til hverandre
* Å legge til en datatabell slik at vi kan utføre beregninger basert på ukedager
* Å legge til beregnede kolonner for å beregne varigheten mellom prosjektmilepæler
* Å legge til målinger for å beregne variansen i forventede kontra faktiske dager for et prosjekt

Etter at disse trinnene er fullført, kan vi bygge visualiseringer som drar nytte av forbedringene til modellen vår. Hvis du vil ha mer informasjon om hvordan du modellerer data i Power BI Desktop, kan du se [Modellering](https://powerbi.microsoft.com/guided-learning/powerbi-learning-2-1-intro-modeling-data)-delen i Veiledet opplæring-kurset.

### <a name="change-table-relationships"></a>Å endre tabellrelasjoner
Når Power BI Desktop henter inn listene, oppretter programmet en relasjon mellom dem basert på **Id**-kolonnen i begge tabellene. Relasjonene skal faktisk være mellom **Id**-kolonnen i **Prosjektforespørsler**-tabellen og **RequestId**-kolonnen i **Prosjektdetaljer**-tabellen. La oss rette opp i det:

1. Klikk eller trykk på **Datavisning**-ikonet.
   
    ![Datavisning](./media/sharepoint-scenario-build-report/05-02-01-data-view.png)

2. Klikk eller trykk på **Behandle relasjoner** på **Modellering**-fanen. Vi forblir på denne fanen i **Data**-visningen for alle datamodelleringstrinnene.
   
    ![Å behandle relasjoner](./media/sharepoint-scenario-build-report/05-02-02-manage-relationships.png)

3. Sørg for at den eksisterende relasjonen er valgt, klikk eller trykk på **Slett**, og deretter på **Slett** på nytt for å bekrefte.
   
    ![Å slette en relasjon](./media/sharepoint-scenario-build-report/05-02-03-delete-relationship.png)

4. Klikk på **Ny** for å opprette en annen relasjon.

5. I dialogboksen **Opprett relasjon**:
   
   1. Velg **Prosjektforespørsler** for den første tabellen, og **Id**-kolonnen.
   
   2. Velg **Prosjektdetaljer** for den andre tabellen, og **RequestId**-kolonnen.
   
   3. Skjermen skal nå se ut som på følgende bilde. Når du er klar, klikker eller trykker du på **OK**, deretter på **Lukk**.
      
       ![Å opprette en relasjon](./media/sharepoint-scenario-build-report/05-02-04-create-relationship.png)

### <a name="add-a-date-table-to-make-date-based-calculations-easier"></a>Å legge til en datatabell for enklere databaserte beregninger
1. Klikk eller trykk på **Ny tabell**.
   
    ![Ny tabell](./media/sharepoint-scenario-build-report/05-02-05-modeling-table.png)
2. Skriv inn denne formelen i formellinjen: **Datoer = CALENDARAUTO()**.
   
    ![Formellinje med Dates = CALENDARAUTO()](./media/sharepoint-scenario-build-report/05-02-06-formula-bar.png)
   
    Denne formelen oppretter en tabell med navnet **Datoer** med én enkelt datokolonne. Tabellen inneholder alle datoer fra din andre tabell, og den oppdateres automatisk hvis flere datoer legges til (det vil si, hvis dataene oppdateres).
   
    Denne formelen og de andre i denne delen bruker dataanalyseuttrykk (DAX), et formelspråk for Power BI og andre teknologier. Hvis du vil ha mer informasjon, kan du se [Grunnleggende om DAX i Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-quickstart-learn-dax-basics).
3. Trykk på ENTER for å opprette **Datoer**-tabellen.
   
    ![Datoer-tabell](./media/sharepoint-scenario-build-report/05-02-07-date-table.png)

### <a name="add-a-calculated-column-to-the-dates-table"></a>Å legge til en beregnet kolonne i Datoer-tabellen
1. Klikk eller trykk på **Ny kolonne** fra denne datotabellen.
   
    ![Ny kolonne](./media/sharepoint-scenario-build-report/05-02-00-modeling-column.png)
2. Skriv inn denne formelen i formellinjen: **IsWeekDay = SWITCH(WEEKDAY(Dates[Date]), 1,0,7,0,1)**.
   
    Denne formelen bestemmer om en dato i **Dato**-kolonnen er en ukedag. Hvis datoen er en ukedag, får **IsWeekDay**-kolonnen verdien 1 – ellers får den verdien 0.
3. Trykk på ENTER for å legge til kolonnen **IsWeekDay** i **Datoer**-tabellen.
   
    ![Å legge til kolonnen IsWeekDay](./media/sharepoint-scenario-build-report/05-02-08-column-isweekday.png)

### <a name="add-a-calculated-column-to-the-project-details-table"></a>Å legge til en beregnet kolonne i Prosjektdetaljer-tabellen
1. Klikk eller trykk på **Prosjektdetaljer**-tabellen i den høyre ruten, og deretter på **Ny kolonne**.
   
    ![Ny kolonne](./media/sharepoint-scenario-build-report/05-02-00-modeling-column.png)
2. Skriv inn denne formelen i formellinjen:
   
    ```dax
    ApprovedStartDiff = CALCULATE(SUM(Dates[IsWeekday]),
       DATESBETWEEN(Dates[Date],
          'Project Details'[ApprovedDate],
          'Project Details'[ProjectedStartDate]
      )
    )
    ```
   
    Denne formelen beregner forskjellen i dager mellom da et prosjekt ble godkjent og da det er forventet å begynne. Den bruker kolonnen **IsWeekday** fra **Datoer**-tabellen, så den teller bare ukedager.
3. Trykk på ENTER for å legge til kolonnen **ApprovedStartDiff** i **Prosjektdetaljer**-tabellen.
   
    ![Å legge til kolonnen ApprovedStartDiff](./media/sharepoint-scenario-build-report/05-02-09-column-approvedstartdiff.png)

### <a name="add-a-calculated-column-to-the-project-requests-table"></a>Å legge til en beregnet kolonne i Prosjektforespørsler-tabellen
1. Klikk eller trykk på **Prosjektforespørsler**-tabellen i den høyre ruten, deretter på **Ny kolonne**.
   
    ![Ny kolonne](./media/sharepoint-scenario-build-report/05-02-00-modeling-column.png)
2. Skriv inn denne formelen i formellinjen:
   
    ```dax
    RequestDateAge = CALCULATE(SUM(Dates[IsWeekday]),
       DATESBETWEEN(Dates[Date],
          'Project Requests'[RequestDate],
          NOW()
       )
    )
    ```
   
    Denne formelen beregner forskjellen i dager mellom da et prosjekt ble forespurt og dagens dato (NOW()). Formelen teller også her bare ukedagene. Denne kolonnen brukes for å finne det prosjektet som har hatt status som ventende lengst.
3. Trykk på ENTER for å legge til kolonnen **RequestDateAge** i **Prosjektforespørsler**-tabellen.
   
    ![Å legge til kolonnen RequestDateAge](./media/sharepoint-scenario-build-report/05-02-10-column-requestdateage.png)

### <a name="add-a-measure-to-the-project-details-table"></a>Å legge til et mål i en Prosjektdetaljer-tabell
1. Klikk eller trykk på **Prosjektdetaljer**-tabellen i den høyre ruten, deretter på **Nytt mål**.
   
    ![Nytt mål](./media/sharepoint-scenario-build-report/05-02-00-modeling-measure.png)
2. Skriv inn denne formelen i formellinjen:
   
    ```dax
    VarProjectedActual = DIVIDE(
        SUM('Project Details'[ActualDays]) - SUM('Project Details'[ProjectedDays]),
        SUM('Project Details'[ProjectedDays])
    )
    ```
   
    Denne formelen beregner variansen mellom faktiske og forventede dager for et prosjekt. Vi legger dette til som et mål i stedet for en beregnet kolonne, og formelen returnerer de riktige resultatene uansett hvordan dataene er filtrert eller samlet i en rapport.
3. Trykk på ENTER for å legge til målet **VarProjectedActual** i **Prosjektdetaljer**-tabellen.
   
    ![Å legge til målet VarProjectedActual](./media/sharepoint-scenario-build-report/05-02-11-measure-varprojectedactual.png)

### <a name="add-a-measure-to-the-project-requests-table"></a>Å legge til et mål i en Prosjektforespørsler-tabell
1. Klikk eller trykk på **Prosjektforespørsler**-tabellen i den høyre ruten, deretter på **Nytt mål**.
   
    ![Nytt mål](./media/sharepoint-scenario-build-report/05-02-00-modeling-measure.png)
2. Skriv inn denne formelen i formellinjen:
   
    ```dax
    MaxDaysPending = MAXX(
        FILTER('Project Requests', 'Project Requests'[Approved]="Pending"),
        'Project Requests'[RequestDateAge]
    )
    ```
   
    Denne formelen finner prosjektet som har hatt status som ventende lengst, basert på den beregnede kolonnen vi definerte tidligere.
3. Trykk på ENTER for å legge til målet **MaxDaysPending** i **Prosjektforespørsler**-tabellen.
   
    ![Å legge til målet MaxDaysPending](./media/sharepoint-scenario-build-report/05-02-12-measure-maxdayspending.png)

## <a name="step-3-create-report-visualizations"></a>Trinn 3: Opprette visualiseringer i rapporter
Nå har vi kommet til det trinnet som mange tenker på når det kommer til dataanalyser: å opprett visualiseringer slik at vi kan finne mønstre i dataene våre. I dette trinnet skal vi opprette fire visualiseringer:

* Et kolonnediagram som viser forventede dager kontra faktiske dager for et prosjekt
* Et kolonnediagram som viser variansen for hvert prosjekt
* Et kort som viser prosjektet som har ventet lengst
* En tabell som viser tiden mellom godkjenningen og oppstarten for et prosjekt

Etter at vi har opprettet disse rapportvisualiseringene i Power BI Desktop, skal vi publisere dataene og rapportene til Power BI-tjenesten slik at vi kan opprette og dele instrumentbordene. Hvis du vil ha mer informasjon om hvordan du oppretter rapporter i Power BI Desktop, kan du se [Visualiseringer](https://powerbi.microsoft.com/guided-learning/powerbi-learning-3-1-intro-visualizations)-delen i Veiledet opplæring-kurset.

### <a name="create-a-bar-chart-to-show-projected-versus-actual"></a>Å opprette et stolpediagram for å vise forventet kontra faktisk
1. Klikk eller trykk på **Rapportvisning**-ikonet. Vi fortsetter i denne visningen i Power BI Desktop.
   
    ![Rapportvisning](./media/sharepoint-scenario-build-report/05-03-01-report-view.png)
2. Klikk eller trykk på **Gruppert stående stolpediagram** i **Visualiseringer**-ruten til høyre.
   
    ![Visualiseringer – gruppert stående stolpediagram](./media/sharepoint-scenario-build-report/05-03-00-visuals-column.png)
3. Dra **PMAssigned** og **Tittel** fra **Prosjektdetaljer** i **Felter**-ruten til **Akse** i **Visualiseringer**-ruten.
   
    ![Akse i Visualiseringer-ruten](./media/sharepoint-scenario-build-report/05-03-00-axis.png)
4. Dra **ActualDays** og **ProjectedDays** fra **Prosjektdetaljer** i **Felter**-ruten til **Verdi** i **Visualiseringer**-ruten.
   
    ![Verdi i Visualiseringer-ruten](./media/sharepoint-scenario-build-report/05-03-03-value-projected.png)
5. Visualiseringen skal nå se ut som på følgende bilde.
   
    ![ProjectedDays og ActualDays etter PMAssigned](./media/sharepoint-scenario-build-report/05-03-04-chart-projected.png)
6. Dra **Status** fra **Prosjektdetaljer** i **Felter**-ruten til **Filtre**-området til **Visualiseringer**-ruten, deretter merker du av for **Fullført**.
   
   ![Å filtrere etter Status-kolonnen](./media/sharepoint-scenario-build-report/05-03-05-filters-projected.png)
   
   Diagrammet filtreres nå for å vise bare fullførte prosjekter. Det gir mening fordi vi sammenligner forventede dager med faktiske dager.
7. Klikk på pilene øverst til venstre i diagrammet for å flytte opp og ned i hierarkiet til prosjektledere og prosjekter. På følgende bilde ser du hvordan det ser ut når man driller ned i prosjekter.
   
   ![Å drille ned i et kolonnediagram](./media/sharepoint-scenario-build-report/05-03-06-chart-projected-drill.png)

### <a name="create-a-bar-chart-to-show-variance-from-projected"></a>Å opprette et stolpediagram for å vise variansen fra forventet
1. Klikk eller trykk på arbeidssonen utenfor visualiseringen du nettopp opprettet.
2. Klikk eller trykk på **Gruppert stående stolpediagram** i **Visualiseringer**-ruten til høyre.
   
    ![Visualiseringer – gruppert stående stolpediagram](./media/sharepoint-scenario-build-report/05-03-00-visuals-column.png)
3. Dra **PMAssigned** og **Tittel** fra **Prosjektdetaljer** i **Felter**-ruten til **Akse** i **Visualiseringer**-ruten.
   
    ![Akse i Visualiseringer-ruten](./media/sharepoint-scenario-build-report/05-03-00-axis.png)
4. Dra **VarProjectedActual** fra **Prosjektdetaljer** i **Felter**-ruten til **Verdi** i **Visualiseringer**-ruten.
   
    ![Verdi i Visualiseringer-ruten](./media/sharepoint-scenario-build-report/05-03-07a-value-variance.png)
5. Dra **Status** fra **Prosjektdetaljer** i **Felter**-ruten til **Filtre**-området til **Visualiseringer**-ruten, deretter merker du av for **Fullført**.
   
    ![Å filtrere etter Status-kolonnen](./media/sharepoint-scenario-build-report/05-03-07b-filters-variance.png)
   
    Visualiseringen skal nå se ut som på følgende bilde.
   
    ![VarProjectedActual etter PMAssigned](./media/sharepoint-scenario-build-report/05-03-08-chart-variance.png)
   
    Du kan se av dette diagrammet hvor mye mer variasjon det er for prosjekter som ble kjørt av Jostein Bergersen kontra Linda Skistad. Drill ned for å se variasjonen etter prosjekt, og om forventede dager var flere eller færre enn de faktiske dagene.
   
    ![VarProjectedActual etter Tittel](./media/sharepoint-scenario-build-report/05-03-09-chart-variance-drill.png)
6. Før vi oppretter flere visualiseringer, skal vi flytte og endre størrelse på de du allerede har opprettet slik at de passer ved siden av hverandre.
   
    ![Å tilpasse diagrammer ved siden av hverandre](./media/sharepoint-scenario-build-report/05-03-10-two-charts.png)

### <a name="create-a-card-that-shows-the-longest-pending-project"></a>Å opprette et kort som viser prosjektet som har ventet lengst
1. Klikk eller trykk på arbeidssonen utenfor visualiseringen du nettopp opprettet.
2. Klikk eller trykk på **Kort** i **Visualiseringer**-ruten til høyre.
   
    ![Visualiseringer – kort](./media/sharepoint-scenario-build-report/05-03-11-visuals-card.png)
3. Dra **MaxDaysPending** fra **Prosjektforespørsler** i **Felter**-ruten til **Felter** i **Visualiseringer**-ruten.
   
    ![Felter i Visualiseringer-ruten](./media/sharepoint-scenario-build-report/05-03-12-value-max.png)
4. Klikk eller trykk på **Format** (malerkosten), deretter angir du **Kantlinje** til **På**.
   
    ![Å kopiere format – kantlinje](./media/sharepoint-scenario-build-report/05-03-13a-format.png)
5. Angi **Tittel** til **På**, deretter legger du til tittelen Maksimalt antall dager for venting på godkjenning.
   
    ![Å legge til en tittel](./media/sharepoint-scenario-build-report/05-03-13b-title.png)
   
    Visualiseringen skal nå se ut som på følgende bilde.
   
    ![ Maksimalt antall dager for venting på godkjenning](./media/sharepoint-scenario-build-report/05-03-14-chart-max.png)
   
    Etter at vi publiserer denne rapporten, bruker vi denne flisen til å utløse et varsel hvis maksimumverdien for et ventende prosjekt når en bestemt terskel.

### <a name="create-a-table-that-shows-the-time-between-project-approval-and-projected-start-date"></a>Å opprette en tabell som viser tiden mellom godkjenningen og oppstarten for et prosjekt
1. Klikk eller trykk på arbeidssonen utenfor visualiseringen du nettopp opprettet.
2. Klikk eller trykk på **Tabell** i **Visualiseringer**-ruten til høyre.
   
    ![Visualiseringer – tabell](./media/sharepoint-scenario-build-report/05-03-15-visuals-table.png)
3. Dra**PMAssigned**, **Tittel** og **ApprovedStartDiff** fra **Prosjektdetaljer** i **Felter**-ruten til **Verdier** i **Visualiseringer**-ruten.
   
    ![Verdier i Visualiseringer-ruten](./media/sharepoint-scenario-build-report/05-03-16-value-diff.png)
4. Dra **ProjectedStartDate** fra **Prosjektdetaljer** i **Felter**-ruten til **Filtre**-området til **Visualiseringer**-ruten, deretter merker du av for alle datoene bortsett fra **(tom)**.
   
    ![Å filtrere etter ProjectedStartDate](./media/sharepoint-scenario-build-report/05-03-17-filters-diff.png)
5. Endre størrelsen på kolonnene i tabellen slik at du kan se alle dataene, og sorter etter **ApprovedStartDiff**, i synkende rekkefølge. Visualiseringen skal nå se ut som på følgende bilde.
   
    ![Tabell med verdier for ApprovedStartDiff](./media/sharepoint-scenario-build-report/05-03-18-chart-diff.png)
6. Klikk eller trykk på Pil ned for **ApprovedStartDiff** i **Verdier**-området, deretter klikker eller trykker du på **Gjennomsnitt**. Nå kan vi se gjennomsnittlig varighet mellom godkjenningen og oppstarten for et prosjekt.
   
    ![Å beregne gjennomsnitt](./media/sharepoint-scenario-build-report/05-03-20a-average-menu.png)
7. Klikk eller trykk på Pil ned for **ApprovedStartDiff** på nytt, klikk eller trykk på **Betinget formatering**, og deretter klikker eller trykker du på **Bakgrunnsfargeskalaer**.
   
   ![Betinget formatering](./media/sharepoint-scenario-build-report/05-03-20b-conditional-menu.png)
8. Angi farger for feltene **Minimum** og **Maksimum** som vist nedenfor, og klikk eller trykk deretter på **OK**.
   
   ![Alternativer for betinget formatering](./media/sharepoint-scenario-build-report/05-03-21-conditional-dialog.png)
   
   Visualiseringen skal nå se ut som på følgende bilde.
   
   ![Fullført betinget formatering](./media/sharepoint-scenario-build-report/05-03-22-chart-diff-completed.png)
   
   Som du kan se så pleier prosjektene som Jostein Bergesen kjører, å starte mye senere enn godkjenningen. Det kan være andre faktorer enn den tilordnede lederen, men det kan være greit å se nærmere på dette.

Da har vi kommet til slutten av rapportdelen, og du har nå en fullstendig rapport basert på data som ble importert fra SharePoint og ordnet og modellert i Power BI Desktop. Hvis alt gikk etter planen, skal rapporten din se ut som på følgende bilde.

![Fullstendig rapport](./media/sharepoint-scenario-build-report/05-03-23-report-completed.png)

## <a name="next-steps"></a>Neste trinn
Det neste trinnet i denne opplæringsserien er å [publisere rapporten for Power BI-prosjektet og opprette et instrumentbord](sharepoint-scenario-publish-report.md).

