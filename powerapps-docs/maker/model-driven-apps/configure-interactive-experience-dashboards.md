---
title: Konfigurere instrumentbord for interaktiv opplevelse for modelldrevet app i PowerApps | Microsoft Docs
description: Finn ut hvordan du konfigurerer instrumentbord for interaktiv opplevelse i PowerApps
keywords: Interaktive instrumentbord; Customer Service; Microsoft Dynamics 365; interaktiv servicehub
author: Mattp123
ms.author: matp
manager: kvivek
ms.custom: ''
ms.date: 05/21/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
ms.assetid: d1446a95-14bf-4b15-a905-72fce07f4c76
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="configure-model-driven-app-interactive-experience-dashboards"></a>Konfigurere instrumentbord for interaktiv opplevelse for modelldrevet app

Instrumentbord for interaktiv opplevelse kan være en arbeidsplass på ett sted for appbrukere, for eksempel servicerepresentanter, der de kan vise informasjon om arbeidsmengde og utføre handlinger. De er fullt ut konfigurerbare, sikkerhetsrollebasert og gir informasjon om arbeidsmengde på tvers av flere strømmer i sanntid. Brukere av interaktive instrumentbord trenger ikke å bla gjennom programmet etter en bestemt oppføring. De kan behandle den direkte fra instrumentbordet. 

 Instrumentbordene for interaktiv opplevelse kommer i to utgaver: for flere strømmer og for enkeltstrøm. Instrumentbord for flere strømmer kan i tillegg være hjemmeside eller enhetsspesifikke instrumentbord. De enhetsspesifikke instrumentborden er konfigurert i en annen del av brukergrensesnittet, og delvis forhåndslastet med enhetsspesifikk konfigurasjonsinformasjon.  
  
 Instrumentbordene for flere strømmer viser data i sanntid over flere datastrømmer. Det er ingen grense for hvor mange strømmer kan du konfigurere på instrumentbordet. Dataene i en strøm kan bare være basert på én enhet, men hver strøm kan være basert på en ulik enhet. På de enhetsspesifikke instrumentbordene er alle strømmene basert på samme enhet. Data strømmer fra ulike visninger eller køer, som **Mine aktiviteter**, **Mine saker** eller **Saker i køen banktjenester**. 
  
 Instrumentbordene for enkeltstrøm viser sanntidsdata over én stream basert på en enhet, visning eller kø. Flisene er plassert på høyre side av instrumentborde og vises alltid. Instrumentbordene for enkeltstrøm er vanligvis nyttige for kundeemner eller ledere på Lag 2 som overvåker færre, men mer komplekse eller oppjusterte saker.  
  
 Instrumentbord for flere strømmer og instrumentbord for enkeltstrøm gir deg interaktive diagrammer som gir deg en oversikt over relevante oppføringer, for eksempel saker etter prioritet eller status. Disse diagrammene fungerer også som visuelle filtre. Visuelle filtre (interaktive diagrammer) er basert på flere enheter, og i instrumentbordene for enkeltstrøm er det enheten i dataflyten som definerer den enheten for visuelt filter.   
  
 Brukere kan bruke ekstra filtrering med globale filtre og tidsrammefiltre. Det globale filteret fungerer på feltnivå på alle diagrammer, og også på strømmer og fliser som er basert på filterenheten (du angir filternheten når du konfigurerer de visuelle filtrene). 
  
> [!NOTE]
>  De interaktive instrumentbordene er løsningsorienterte og kan eksporteres og deretter importeres inn i et annet miljø som en løsning. Køene som strømmerne og flisene er basert på, er imidlertid ikke løsningsavhengige. Før du importerer instrumentbordløsningen til målsystemet, må køene opprettes manuelt i målsystemet i **Innstillinger** > **Servicebehandling** > **Køer**. Når du har opprettet køene, importer instrumentbordløsningen til målsystemet, og deretter rediger datastrømmer eller fliser som er basert på køene, for å tilordne de nylig opprettede køene på riktig måte.  
  
 Illustrasjonene i dette emnet viser instrumentbord for flere strømmer og enkeltstrøm med topptekstruten. Nedenfor hodet ser du visuelle filtre og strømmer. På instrumentbordet for enkeltstrøm ser du også fliser. For hver instrumentbordtype, kan du velge mellom flere ulike oppsett som også vises. Instrumentbordoverskriften som vises her, inneholder følgende kontroller og valgbare ikoner, fra venstre mot høyre: instrumentbordvelger, oppdatering, ikon for visuelt filter, ikon for globalt filter og tidsrammefilter.  
  
### <a name="multi-stream-dashboard-standard-view"></a>Standardvisning for instrumentbord for flere strømmer  
 I instrumentbordet for flere strømmer ser du en rekke visuelle filtre øverst med datastrømmene nedenfor disse.  
 
![Interaktivt instrumentbord for flere strømmer](../model-driven-apps/media/interactive-dashboards-multi-stream.png) 
   
### <a name="multi-stream-dashboard-tile-view"></a>Flisvisning for instrumentbord for flere strømmer  
 Samme instrumentbord, bare i flisvisning.  
  
 ![Flisvisning for instrumentbord for flere strømmer](../model-driven-apps/media/interactive-dashboards-multi-stream-tiles.png "Flisvisning for instrumentbord for flere strømmer")  
  
### <a name="multi-stream-dashboard-layouts"></a>Oppsett for instrumentbord for flere strømmer  
 Du kan velge mellom fire ulike oppsett for instrumentbord for flere strømmer.  

 > [!div class="mx-imgBorder"] 
 > ![Oppsett for instrumentbord for flere strømmer](../model-driven-apps/media/interactive-dashboards-multi-stream-layout.png "Oppsett for instrumentbord for flere strømmer")  
  
### <a name="multi-stream-entity-specific-dashboard"></a>Enhetsspesifikt instrumentbord for flere strømmer  
 Det enhetsspesifikke instrumentbordet for `Case`-enheten er vist her.  
  
 ![Instrumentbord for åpne saker](../model-driven-apps/media/interactive-dashboard-cases-dashboard.PNG "Instrumentbord for åpne saker")  
  
### <a name="single-stream-dashboard"></a>Instrumentbord for enkeltstrøm  
 Instrumentbordet for enkeltstrøm inneholder datastrømmen til venstre og visuelle filtre og fliser til høyre.  
  
 ![Instrumentbord for enkeltstrøm for interaktiv servicehub](../model-driven-apps/media/interactive-dashboards-single-stream.png "Instrumentbord for enkeltstrøm for interaktiv servicehub")  
  
### <a name="single-stream-dashboard-layouts"></a>Oppsett for instrumentbord for enkeltstrøm  
 Du kan velge mellom fire ulike oppsett for instrumentbord for enkeltstrøm.  
 
 > [!div class="mx-imgBorder"] 
 > ![Oppsett for instrumentbord for enkeltstrøm](../model-driven-apps/media/interactive-dashboards-single-stream-layout.png "Oppsett for instrumentbord for enkeltstrøm")  
  
<a name="BKMK_Enable"></a>   
## <a name="configure-entities-fields-and-security-roles-for-the-interactive-dashboards"></a>Konfigurere enheter, felt og sikkerhetsroller for de interaktive instrumentbordene  
 Når du konfigurerer interaktive instrumentbord, er første oppgave å aktivere enheter, felt og sikkerhetsroller for interaktiv opplevelse.  
  
### <a name="entities-enabled-for-interactive-experience"></a>Enheter aktiverte for interaktiv opplevelse
 Alle enheter som støttes i det enhetlige grensesnittet, er aktiverte for instrumentbordene for interaktiv opplevelse.
  
### <a name="configure-fields"></a>Konfigurere felt  
 For at et felt skal vises i det globale filteret og inkluderes i sorteringen av datastrømmen, du må angi to flagg, som vist i eksemplet nedenfor for **IsEscalated**-feltet for Sak-enheten.  

 > [!div class="mx-imgBorder"] 
 > ![Aktivere et felt for globalt filter og sortering](../model-driven-apps/media/global-filter-sort-8.png "Aktivere et felt for globalt filter og sortering")  
  
### <a name="configure-global-filter-fields"></a>Konfigurere felt for globale filtre  
 For at et felt skal vises i det globale filteret, må du angi flagget **Vises i globalt filter i interaktiv opplevelse** for dette feltet. Feltene som du konfigurerer, vises i det globale filterets undermenyvindu når du klikker ikonet Globalt filter i instrumentbordets overskrift. I undermenyvinduet kan servicerepresentantene velge feltene de vil filtrere globalt, i diagrammer og også i strømmer og fliser som er basert på filterenheten. For mer informasjon om filterenhet, kan du se delen "Konfigurere interaktivt instrumentbord for flere strømmer" senere i dette emnet.  
  
 Det globale filterets undermenyvindu vises her:  
  
 ![Legge til to felt for globale filtre](../model-driven-apps/media/interactive-dashboards-global-filter-two-fields.png "Legge til to felt for globale filtre")  
  
> [!NOTE]
>  Når du konfigurerer et visuelt filter (interaktivt diagram) basert på felt som for eksempel prioritet eller status, er det lurt å aktivere også disse feltene (prioritet, status) slik at de vises i det globale filteret.  
  
Denne fremgangsmåten viser fremgangsmåten for å angi flagget for globalt filter:
  
1. Åpne [løsningsutforskeren](advanced-navigation.md#solution-explorer).  
  
2. Vis **Enheter** under **Komponenter**, og vis deretter ønsket enhet. Hvis enheten du ønsker, ikke vises, velger du **Legg til eksisterende** for å legge den til.  
  
3.  I navigasjonsruten velger du **Felt**, og i rutenettet dobbeltklikker du feltet du vil aktivere.  
  
4.  Merk av for**Vises i globalt filter i interaktiv opplevelse** i kategorien **Generelt**. Velg **Lagre og lukk**.  
  
5.  Velg **Publiser** for at endringene skal tre i kraft.  
  
6.  Velg **Klargjør klienttilpassinger**.  
  
### <a name="configure-sortable-fields"></a>Konfigurere felt som kan sorteres  
 For at et felt skal bli brukt til sortering av data fra strømmen, må du angi flagget **Sorterbar på instrumentbordet for interaktiv opplevelse**. Feltene som du konfigurerer for sortering, vises i rullegardinlisten i undermenydialogboksen **Rediger egenskap** når brukeren velger **Mer (...)** i strømhodet. Illustrasjonen nedenfor viser dialogboksen undermeny med listen over tilgjengelige felt for sortering, i rullegardinlisten **Sorter etter** -. Standardsorteringen er alltid satt til feltet **Endret den**.  
  
 ![Sortere etter rullegardinliste](../model-driven-apps/media/interactive-dashboard-sortable-fields-dropdown.png "Sortere etter rullegardinliste")  
  
Denne fremgangsmåten viser fremgangsmåten for å angi sorteringsflagget:
  
1. Åpne [løsningsutforskeren](advanced-navigation.md#solution-explorer).   
2. Vis **Enheter** under **Komponenter**, og vis deretter ønsket enhet. Hvis standardenheten du ønsker, ikke vises, velger du **Legg til eksisterende** for å legge den til.  
  
3.  I navigasjonsruten velger du **Felt**, og i rutenettet dobbeltklikker du feltet du vil aktivere.  
  
4.  Merk av for**Sorterbar på instrumentbordet for interaktiv opplevelse** i kategorien **Generelt**. Velg **Lagre og lukk**.  
  
5.  Velg **Publiser** for at endringene skal tre i kraft.  
  
6.  Velg **Klargjør klienttilpassinger**.  
  
### <a name="enable-security-roles"></a>Aktivere sikkerhetsroller  
 Velg og aktiver sikkerhetsroller som skal kunne vise de interaktive instrumentbordene.  
  
Følgende fremgangsmåte inneholder trinn for å aktivere sikkerhetsroller for interaktiv opplevelse:
  
1. Åpne [løsningsutforskeren](advanced-navigation.md#solution-explorer).  
  
2. Velg **Instrumentbord** under **Komponenter**.  
  
4.  Velg det interaktive instrumentbordet du vil bruke, i rutenettet, og velg **Aktiver sikkerhetsroller** på oppgavelinjen.  
  
5.  I **Tilordne sikkerhetsroller**-dialogboksen velger du **Vis bare for disse valgte rollene**-alternativet, og velger rollene du vil aktivere. Velg **OK**.  
  
6.  Velg **Publiser** for at endringene skal tre i kraft.  
  
7.  Velg **Klargjør klienttilpassinger**.  
  
 ![Aktivere sikkerhetsroller](../model-driven-apps/media/interactive-dashboards-enable-security-roles.png "Aktivere sikkerhetsroller")  
  
 ![Tilordne sikkerhetsroller](../model-driven-apps/media/interactive-dashboards-assign-security-roles.png "Tilordne sikkerhetsroller")  
  
<a name="BKMK_Configure"></a>   
## <a name="configure-interactive-experience-dashboards"></a>Sorterbar på instrumentbordet for interaktiv opplevelse  
 Følgende avsnitt beskriver hvordan du konfigurerer ulike typer interaktive instrumentbord.  
  
### <a name="configure-a-multi-stream-interactive-dashboard-using-the-4-column-layout"></a>Konfigurere et interaktivt instrumentbord for flere strømmer ved hjelp av 4-kolonneoppsettet  
 
1.  Logg på [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc).

2.  Velg **Modelldrevet** (nederst til venstre).  
  
3.  Velg **Data** > **Enheter** > velg enheten du vil ha. 

4.  Velg **Instrumentbord**-kategorien, og velg deretter **Legg til instrumentbordet** på verktøylinjen.  
  
5.  Velg oppsett, kolonnebredde 2, 3 eller 4.  
  
6.  Når instrumentbordskjemaet åpnes, fyller du ut filtreringsinformasjonen øverst i skjemaet, som vist her.  
 
 > [!div class="mx-imgBorder"] 
 > ![Legge til visuelle filtre](../model-driven-apps/media/interactive-dashboards-add-visual-filters.png "Legge til visuelle filtre")  
  
   - **Filtrer enhet**: Attributtent for de visuelle filtrene (interaktive diagrammene) og globalt filter, er basert på denne enheten.  
      
    - **Enhetsvisning**: De visuelle filtrene (interaktive diagrammene) er basert på denne visningen.  
      
    - **Filtrer etter**: Feltet som tidsrammefilteret brukes på.  
      
    - **Tidsramme**: Standardtidsrammefilterverdi for feltet **Filtrer etter**.  
      
 Når du har angitt filtreringsinformasjonen, kan du begynne å legge til komponenter for diagrammene og datastrømmene. Hvis du vil legge til en komponent, velger du bare elementet i midten av diagrammet eller strømmen, og når dialogboksen vises, skriver du inn den nødvendige informasjonen, som vist i illustrasjonene som følger.  
  
 Legg til hjuldiagrammet **Aktiviteter etter prioritet**.
  
 > [!div class="mx-imgBorder"] 
 > ![Legge til en hjuldiagramkomponent](../model-driven-apps/media/interactive-dashboards-add-chart-circle.png "Legge til en hjuldiagramkomponent")  
  
 Noen diagrammer, for eksempel liggende stolpediagrammer eller sektordiagrammer, gjengir dataene som er lagret i systemet. Hjuldiagrammene og merkediagrammene lastes som statiske bilder og viser ikke forhåndsvisningen av de faktiske dataene.  
  
> [!NOTE]
>  Diagrammene som er konfigurert for de visuelle filtrene, kan bruke feltene i **Filter**-enhet, i tillegg til relaterte enheter. Når du bruker diagrammer som er basert på relaterte enhetsfelt, kan kundeservicerepresentantene filtrere diagrammer ved hjelp av disse relaterte enhetsfeltene. Feltene som er basert på den relaterte enheten, har vanligvis har følgende format i vinduet for diagramkonfigurasjonen: "feltnavn (enhetsnavn)", for eksempel feltet **Endret av (representant)**. For å opprette diagrammer med flere enheter må du legge til felt for en relatert enhet i en av visningene og deretter bruke disse feltene under oppretting av diagrammer.  
 
 > [!div class="mx-imgBorder"] 
 > ![Opprette diagrammer for visuelle filtre](../model-driven-apps/media/interactive-dashboard-visual-charts-x-y-axes.PNG "Opprette diagrammer for visuelle filtre")  
  
 Nå konfigurerer du strømmene. Akkurat som når du legger til komponenter i diagrammene, velger du elementet i strømpanelet. Når dialogboksen vises, velger du **Vis** eller **Kø** avhengig av hvilket element du vil at strømmen skal bruke. Angi den nødvendige informasjonen, som vist i illustrasjonene.  
  
> [!NOTE]
>  **Kø**-alternativet er tilgjengelig i dialogboksen bare for enheter aktivert for kø. For enhetsinstrumentbord, hvis enheten ikke er aktivert for kø, ser du ikke **Kø**-alternativet i dialogboksen. Du kan bare bruke **Vis**-alternativet i strømmen av instrumentbord for enheter som ikke er aktivert for kø.  
  
 Konfigurer strømmen for **Elementer tilgjengelige for å arbeide med** som vist her:  
  
 ![Legge til en strøm for mine aktive saker](../model-driven-apps/media/interactive-dashboards-add-stream-case.png "Legge til en strøm for mine aktive saker")  
  
 Illustrasjonen nedenfor er et eksempel på diagrampanelet fra venstre mot høyre: hjuldiagram, merkediagram og liggende stolpediagram:  
 
 > [!div class="mx-imgBorder"] 
 > ![Alle interaktive diagrammer](../model-driven-apps/media/interactive-dashboards-add-all-charts.png "Alle interaktive diagrammer")  
  
 Denne illustrasjonen er et eksempel på strømpanelet med flere strømmer:  
 
 > [!div class="mx-imgBorder"] 
 > ![Legge til alle strømmer](../model-driven-apps/media/interactive-dashboards-add-all-streams.png "Legge til alle strømmer")  
  
 Når du er ferdig med å konfigurere instrumentbordet, lagrer du det og publiserer tilpassingene for at endringene skal tre i kraft. Velg også **Forbered klienttilpassinger**.  
  
#### <a name="edit-or-delete-individual-streams-of-an-existing-dashboard"></a>Redigere eller slette individuelle strømmer av et eksisterende instrumentbord  
  
1. Logg på [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc).   
  
2. Velg **Modelldrevet** (nederst til venstre), **Data** > **Enheter** > velg ønsket enhet. Velg kategorien **Tnstrumentbord**.  
  
     – ELLER –  
   
   Åpne [løsningsutforskeren](advanced-navigation.md#solution-explorer), og deretter under **Komponenter** velg **Instrumentbord**.
  
3.  I rutenettet velger du det interaktive instrumentbordet du vil redigere, for å åpne det.  
  
4.  Velg strømmen du vil redigere, og velg deretter **Rediger komponent**.  
  
5.  Avhengig av om du vil legge til en visning eller kø i strømmen, velger du visnings- eller kødetaljene for strømmen og velger deretter **Angi**.  
  
6.  Velg **Lagre**.  
  
 Du kan også slette en enkelt strøm fra et instrumentbord. Dette gjør du ved å velge strømmen og deretter velge **Slett** på kommandolinjen.  
  
### <a name="configure-an-entity-specific-dashboard"></a>Konfigurere et enhetsspesifikt instrumentbord  
 Et enhetsspesifikt instrumentbord er et instrumentbord for flere strømmer. Konfigurering av dette instrumentbordet ligner på konfigurering av et instrumentbord med flere strømmer som startside, men du gjør det på et annet sted i brukergrensesnittet og det finnes andre mindre forskjeller. I stedet for å velge en enhet, er for eksempel noen av feltene i det enhetsspesifikke instrumentbordet forhåndsinnstilt til enheten som du oppretter instrumentbordet for.  
  
1.  Logg på [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc).

2.  Velg **Modelldrevet** (nederst til venstre).  
  
3.  Velg **Data** > **Enheter** > velg enheten du vil ha. 

4.  Velg **Instrumentbord**-kategorien, og velg deretter **Legg til instrumentbordet** på verktøylinjen.  
  
5.  Velg oppsett, kolonnebredde 2, 3 eller 4.    
  
6.  Når instrumentbordskjemaet åpnes, er feltet **Filtrer enhet** forhåndsinnstilt til enheten som du oppretter instrumentbordet for. Rullegardinlisten **Enhetsvisning** viser de tilgjengelige visningene for enheten. Velg visningen, og fyll ut resten av den nødvendige informasjonen på siden.  
  
 Resten av oppsettet er veldig likt oppsettet for instrumentbord for flere strømmer som startside, som er beskrevet i den forrige delen.  
  
### <a name="configure-a-single-stream-dashboard"></a>Konfigurere et instrumentbord for enkeltstrøm  
 Konfigurering av et instrumentbord for enkeltstrøm ligner konfigurering av instrumentbordet for flere strømmer. Alle UI-navigasjonstrinnene er de samme som for instrumentbordet for flere strømmer. Du kan velge et oppsett som inneholder fliser eller oppsett som ikke inneholder fliser. Hvis flisene er inkludert, vises de alltid på instrumentbordet. Hvis du vil konfigurere en flis, velger du ikonet i midten av flisen. Når vinduet **Legg til flis** åpnes, fyller du ut de nødvendige dataene. Illustrasjonen nedenfor er et eksempel på flisoppsettet.  
  
 ![Legge til en flis på instrumentbordet for enkeltstrøm](../model-driven-apps/media/interactive-dashboard-add-tile-single-stream.png "Legge til en flis på instrumentbordet for enkeltstrøm")  
  
<a name="BKMK_ConfigureColors"></a>   
## <a name="configure-dashboard-colors"></a>Konfigurere instrumentbordfarger  
 For alle felt av typen **Alternativsett** og **To alternativer**, for eksempel **Sakstype**, **IsEscalated** eller **Prioritet** i `Case`-enheten, kan du konfigurere en bestemt farge som skal vises i diagrammene og strømmene for bestemte feltverdier. Høyt prioriterte saker kan for eksempel vises i rødt, middels prioriterte saker i blått og lavt prioriterte saker i grønt, i de interaktive diagrammene. I strømmene vil det være en tynn, loddrett, farget linje ved siden av beskrivelsen av arbeidselementet.  
  
> [!NOTE]
>  Fargekodingen er ikke tilgjengelig for merkediagrammer og hjuldiagrammer. Disse diagrammene vises på instrumentbordet i hvite, grå og svarte sjatteringer.  
  
1.  Åpne [løsningsutforskeren](advanced-navigation.md#solution-explorer).  
2.  Vis **Enheter** under **Komponenter**, og vis deretter ønsket enhet. Hvis enheten du ønsker, ikke vises, velger du **Legg til eksisterende** for å legge den til.  
  
3.  Velg **Felt** i navigasjonsruten. Dobbeltklikk feltet du vil konfigurere fargen for, i ruten.  
  
4.  I **Generelt**-kategorien i **Type**-delområdet velger du **Ja** og deretter **Rediger**.  
  
5.  Når dialogboksen **Endre listeverdi** vises, angir du den nye verdien i **Farge**-tekstboksen. Velg **OK**.  
  
     Velg **Lagre og lukk**.  
  
7.  Velg **Publiser** for at endringene skal tre i kraft.  
  
I det følgende eksemplet, endrer vi farge for feltet **IsEscalated**. Bruk **Rediger**-knappen til å åpne dialogboksen **Endre listeverdi**:  
 
 > [!div class="mx-imgBorder"] 
 > ![Endre farge på instrumentbordet](../model-driven-apps/media/interactive-dashboards-change-color-edit-button.PNG "Endre farge på instrumentbordet")  
  
Når dialogboksen **Endre listeverdi** åpnes, velger du fargen som vist her:  
  
 ![Endre instrumentbordfarge](../model-driven-apps/media/interactive-dashboards-modify-color-value.png "Endre instrumentbordfarge")  
  
### <a name="next-steps"></a>Neste trinn  
 
[Opprette eller redigere instrumentbord](create-edit-dashboards.md)
 

