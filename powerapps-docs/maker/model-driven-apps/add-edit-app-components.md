---
title: Opplæring for å legge til eller redigere modelldrevne applikasjonskomponenter med PowerApps | MicrosoftDocs
description: Bruk apputformingen til PowerApps til å legge til eller redigere komponenter
keywords: ''
ms.date: 10/15/2018
ms.service: crm-online
ms.custom: null
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - PowerApps
author: Mattp123
ms.assetid: be93b9d7-f1c2-4ee7-8d7c-0f5c34dfa5f7
ms.author: matp
ms.reviewer: null
ms.suite: null
ms.tgt_pltfrm: null
caps.latest.revision: 17
topic-status: Drafting
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="tutorial-add-or-edit-model-driven-app-components-in-the-powerapps-app-designer"></a>Opplæring: Legge til eller redigere modelldrevne applikasjonskomponenter i apputformingen til PowerApps

I denne opplæringen lærer du hvordan du kan legge til komponenter og fjerne komponenter fra en modelldrevet app. 

En modelldrevet app består av ulike komponenter. Du kan legge til to komponenttyper i en app: artefakter og enhetsaktiva. I konteksten for appen er utforming, enheter, instrumentbord og forretningsprosessflyter alle artefakter av en app. Enhetsaktiva består av skjemaer, visninger, diagrammer og instrumentbord.  
  
Apputformingen refererer til eksisterende metadata i standardløsningen. Du kan bruke den til å opprette komponenter, som skjemaer, visninger, diagrammer og instrumentbord.  
  
## <a name="app-designer-layout"></a>Oppsett for apputforming  
 Apputformingen har to hovedområder. Til venstre er lerretet der du kan legge til appkomponenter.  
  
![Apputformingslerret](../model-driven-apps/media/app-designer-canvas-pane.png)

 Til høyre er kategorier du vil bruke for å velge komponenter og angi egenskapene for komponenten.  
 
 > [!div class="mx-imgBorder"]
 > ![Apputformingskomponenter](../model-driven-apps/media/app-designer-canvas-components-tab.png "Apputformingskomponenter")  
  
 På lerretet ser du områder for områdekart, forretningsprosessflyt, instrumentbord og enheter. Når du velger et instrumentbord eller en forretningsprosessflyten, eller konfigurere et områdekart, vil apputforming automatisk legge til enhetene som brukes i disse komponentene, på lerretet. Når enhetene er på plass, trenger du bare å velge hver enhet og legge til nødvendige enhetsaktiva, for eksempel skjemaer, visninger og diagrammer.
 
 Du kan også bruke **Søk på lerret** for å søke etter komponenter på lerretet. Når du velger **Søk på lerret**, åpnes en ny søkekategori til høyre for kategorier i ruten til høyre.   
 
 > [!div class="mx-imgBorder"]
 > ![Alternativer for søk på lerret](media/app-designer-search-tab.png "Søk på lerret")

## <a name="open-an-app"></a>Åpne en app
1. Logg på [PowerApps](https://web.powerapps.com/). 

2. Velg en eksisterende modelldrevet app eller velg **Begynn fra tom**. Du finner informasjon om hvordan du oppretter en app i [Opprett eller rediger en modelldreven app ved hjelp av apputforming](create-edit-app.md#create-an-app).

## <a name="add-an-artifact-entity-dashboard-or-business-process-flow"></a>Legge til en artefakt (enheten, instrumentbord eller forretningsprosessflyt)  
 Når du legger til et instrumentbord eller en forretningsprosessflyt til en app, legges enhetene som de bruker, automatisk til appen. Når du legger til en enhet, legges det automatisk til fliser for aktiva. Det er to måter du kan legge til artefakter på utformingslerretet: ved hjelp av **Legg til**-knappen ![Legg til-knappen i utformingen](../model-driven-apps/media/dynamics365-designer-addbutton.PNG "Legg til-knappen i utformingen") på kommandolinjen, eller ved hjelp av flisene i kategorien **Komponenter**.  
  
 Her er fremgangsmåten for å legge til et instrumentbord i appen. Bruk samme fremgangsmåte for å legge til en forretningsprosessflyt eller enhet.  
  
1.  På apputformingslerretet velger du **Instrumentbord**-flisen.  
  
     På apputformingslerretet viser ruten til høyre instrumentbordene som er tilgjengelige i standardløsningen.  
  
    > [!TIP]
    >  Alternativt kan du også gjøre ett av følgende:  
    >   
    > - Velg **Legg til** ![Legg til-knappen i utformingen](../model-driven-apps/media/dynamics365-designer-addbutton.PNG "Legg til-knappen i utformingen"), og velg deretter **Instrumentbord**.  
    > - I kategorien **Komponenter**, under **Artefakter**, velger du **Instrumentbord**.  
  
2.  I **søkeboksen** skriver du inn noen nøkkelord for navnet på instrumentbordet du søker etter.  
  
     Listen over instrumentbord filtreres for å vise resultater som samsvarer med nøkkelordene dine.  
  
3.  Hvis du vil at brukerne bare kan bruke utvalgte instrumentbord, merker du av for instrumentbordene du vil legge til. Du kan velge blant følgende typer instrumentbord:
    - **Klassisk instrumentbord** vises i både webappen og appen for enhetlig grensesnitt.
    - **Interaktive instrumentbord** vises bare i appen for enhetlig grensesnitt. Hvis du har valgt klienttypen webapp for appen, vises ikke alternativet **Interaktive instrumentbord**.

     Disse instrumentbordene legges til i **Instrumentbord**-flisen på lerretet for apputforming. **Instrumentbord**-flisen viser også hvor mange instrumentbord som du la til i appen. Hvis du ikke velger et instrumentbord, vil **Alle** vises i stedet for antallet instrumentbord, og alle instrumentbord være tilgjengelige for brukerne når de bruker appen,.  
  
     Alle enheter som instrumentbordet bruker, legges også til i **Enhetsvisning**-området. Hvis du for eksempel legger til instrumentbordet Kundeservicesjef, blir enhetene Sak, Rettighet og Køelement lagt til i Enhetsvisning-området. For hver enhet legges det også til fliser for aktivaene til enheten. Du kan bruke disse flisene for å legge til skjemaer, visninger og diagrammer. Mer informasjon: [Legge til eller redigere appkomponenter i apputforming til PowerApps](add-edit-app-components.md#bkmk_AddEntityAssets)   
  
    ![Legge til enhet på apputformingslerretet](../model-driven-apps/media/add-entity-app-designer-canvas.png "Legge til enhet på apputformingslerretet")  
  
4.  Hvis instrumentbordet du vil bruke, ikke finnes i standardløsningen, kan du opprette et instrumentbord ved å velge **Opprett ny** i **Komponenter**-kategorien til høyre på lerretet.  
  
     > [!div class="mx-imgBorder"]
     > ![Opprette Ny-kobling i kategorien Komponenter i apputforming](../model-driven-apps/media/app-designer-components-tab-create-new.png "Opprette Ny-kobling i kategorien Komponenter i apputforming")  
  
     Instrumentbordutformingen åpnes. Mer informasjon: [Opprette og redigere instrumentbord](create-edit-dashboards.md)  
  
    > [!NOTE]
    > - Når du legger til en forretningsprosessflyt eller enhet, vil alternativet **Opprett ny** åpne tilsvarende utforming. Hvis du vil lære mer om hvordan du oppretter forretningsprosessflyter eller enheter, kan du se [Opprette en forretningsprosessflyt](/flow/create-business-process-flow) og [Opprette en egendefinert enhet](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-create-entity).  
      
  
5.  Når du er ferdig med å legge til artefakter på kommandolinjen, kan du velge **Lagre**.  
  
<a name="bkmk_AddEntityAssets"></a>   
## <a name="add-entity-assets-forms-views-charts-or-dashboards"></a>Legge til enhetsaktiva (skjemaer, visninger, diagrammer eller instrumentbord)  
 Med artefakter på plass, kan du begynne å legge til enhetsaktiva, som skjemaer, visninger, diagrammer og instrumentbord, i appen.
Hvis du i tillegg bruker klienten for enhetlig grensesnitt, kan du også legge til instrumentbordaktiva for enheten i appen.  
  
 Denne delen beskriver fremgangsmåten for å legge til et skjema i appen. Bruk samme fremgangsmåte for å legge til en visning eller et diagram i appen.  
  
1.  På apputformingslerretet velger du **Skjemaer**-flisen for enheten du vil legge til et skjema i.  
  
     På lerretet for apputforming merkes hele raden for enheten. Til høyre kan du se alle eksisterende skjemaer for den valgte enheten.  
  
    > [!NOTE]
    >  Alternativt kan du også gjøre ett av følgende:  
    >   
    > - Velg **Legg til** ![Legg til-knappen i utformingen](../model-driven-apps/media/dynamics365-designer-addbutton.PNG "Legg til-knappen i utformingen"), og velg deretter **Skjemaer**.  
    > - I kategorien **Komponenter**, under **Enhetsressurser**, velger du **Skjemaer**.  
  
    > [!TIP]
    >  For alle enheter som er valgt for appen vises knappen **Flere alternativer** (**...**) i listen **Velg enheter** i kategorien **Komponenter**. Hvis du vil legge til alle aktiva for den valgte enheten, velger du **Flere alternativer** (**...**) og deretter **Legg til alle aktiva**.  
  
2.  Hvis du vil at appbrukerne bare kan bruke utvalgte skjemaer, merker du av for skjemaene du vil legge til. Skjemaene definerer hvordan brukere skal se og samhandle med data i appen. 
 
     Skjemaflisen for den valgte enheten viser antall skjemaer som er lagt til.  
  
     ![Skjemaflis for saksenhet](../model-driven-apps/media/add-forms-entity.png "Skjemaflis for saksenhet")  
  
     Hvis du for eksempel ikke velger et skjema for en enhet, vises alle skjemaer for enheten til sluttbrukere når de bruker appen. Denne virkemåten er også identisk for visninger og diagrammer hvis det ikke er valgt visning eller diagram. Dette bidrar til å opprette apps raskt når du trenger å arbeide med alle tilgjengelige komponenter. Det er ingen grunn til å velge hver enkelt komponent under apputformingen.  

     Hvis ingen instrumentbord eller forretningsprosessflyter er valgt, er alle instrumentbord og forretningsprosessflyter tilgjengelige for brukere når de bruker appen.
  
    > [!NOTE]
    > Hver enhet som du legger til, må ha minst ett aktivt skjema for at appen skal kjøre. Hvis du har valgt flere skjemaer, brukes det første aktive skjemaet som vises i standardløsningen når brukere kjører appen.  
  
3.  Hvis du vil legge til et nytt skjema som ikke er tilgjengelige i listen, velger du **Opprett nytt**.  
  
     Velg skjematypen du vil opprette, i rullegardinlisten.  
  
    > [!NOTE]
    >  Rullegardinlisten er bare tilgjengelig når du legger til skjemaer. Den er ikke tilgjengelig for visninger og diagrammer.  
  
     Skjemautformingen åpnes. Mer informasjon: [Opprette og utforme skjemaer](create-design-forms.md)  
  
     Når du legger til en visning eller et diagram, vil alternativet **Opprett ny** åpne tilsvarende utforming. Mer informasjon: [Forstå visninger](create-edit-views.md) og [Opprette eller redigere et systemdiagram](create-edit-system-chart.md)  
  
    > [!NOTE]
    >  Når du legger til en visning, kan du bare referere til fellesvisninger som er oppført under **Visninger**-noden i løsningsutforskeren.  
  
4. Velg pil ned ![Rullegardinlisteikon](../model-driven-apps/media/drop-down-icon.png "Pil ned") for å vise flisen og en liste over skjemaer som er lagt til.  
  
     ![Skjemaflis utvidet i apputforming](../model-driven-apps/media/app-designer-expanded-form-tile.png "Skjemaflis utvidet i apputforming")  
  
5.  Gjenta disse trinnene for å legge til enhetsvisninger og diagrammer i appen.  
  
6.  Velg **Lagre**.  
  
## <a name="edit-or-remove-artifacts"></a>Redigere eller fjerne artefakter  
  
- Hvis du vil redigere et instrumentbord eller en forretningsprosessflyten, velger du pil ned ![Rullegardinlisteikon](../model-driven-apps/media/drop-down-icon.png "Pil ned") for å utvide flisen, og deretter velger du knappen for områdekartutforming ![Knappen for å åpne områdekartutforming](../model-driven-apps/media/dynamics365-open-designer.PNG "Knappen for å åpne områdekartutforming") som tilsvarer instrumentbord eller forretningsarbeidsflyten som du vil redigere.  
  
     Utformingen for valgt artefakt åpnes.  
  
- Hvis du vil fjerne et instrumentbord eller en forretningsprosessflyt, velger du pil ned ![Rullegardinlisteikon](../model-driven-apps/media/drop-down-icon.png "Pil ned") for å utvide flisen, og deretter velger du instrumentbordet eller forretningsprosessflyten som du vil fjerne. Velg **Fjern** på kommandolinjen.  

    En annen metode for å fjerne et instrumentbord eller en forretningsprosessflyt er ved å fjerne merket for alternativet i kategorien **Komponenter**.
  
- Hvis du vil redigere eller fjerne en enhet, velger du enhetsflisen og velger deretter **Rediger** eller **Fjern** på kommandolinjen. Når du redigerer en enhet, åpnes løsningsutforskeren der du kan gjøre endringer for enheten.  
  
     Hvis du vil fjerne en komponent, kan du også velge instrumentbordet, forretningsprosessflyten eller enhetsflisen. Fjern merket for artefakten som du vil fjerne fra utformingen, i kategorien **Komponenter**.  
  
    > [!NOTE]
    >  Når du gjør endringer i en enhet – som å endre visningsnavnet eller beskrivelsen for en enhet – vises ikke endringene i apputformingen med mindre de publiseres i løsningsutforskeren.  
  
## <a name="edit-or-remove-entity-assets"></a>Redigere eller fjerne enhetsaktiva  

### <a name="edit-entity-assets"></a>Redigere enhetsaktiva
  
1. Velg pil ned ![Rullegardinlisteikon](../model-driven-apps/media/drop-down-icon.png "Pil ned") for å utvide flisen for skjemaer, visninger, diagrammer og instrumentbord.  
  
2. Velg skjemaet, visningen, diagrammet eller instrumentbordet du vil redigere.  
  
3. Velg **Rediger** på kommandolinjen.

   eller

   Velg knappen for områdekartutforming![Knappen for å åpne områdekartutforming](../model-driven-apps/media/dynamics365-open-designer.PNG "Knappen for å åpne områdekartutforming") som tilsvarer skjemaet, visningen, diagrammet eller instrumentbordet.  

### <a name="remove-entity-assets"></a>Fjerne enhetsaktiva  

1. Velg pil ned ![Rullegardinlisteikon](../model-driven-apps/media/drop-down-icon.png "Pil ned") for å utvide flisen for skjemaer, visninger, diagrammer og instrumentbord.  
  
2. Velg skjemaet, visningen, diagrammet eller instrumentbordet du vil redigere.

3. Velg **Fjern** på kommandolinjen. 

Du kan også velge flisen for skjemaer, visninger, diagrammer og instrumentbord, og deretter gå til kategorien **Komponenter** og fjerne merket for aktiva du vil fjerne fra utformingen.  
  
## <a name="next-steps"></a>Neste trinn  
 [Opprette et områdekart for en app](create-site-map-app.md) </br>  
 [Validere og publisere en app](validate-app.md)
