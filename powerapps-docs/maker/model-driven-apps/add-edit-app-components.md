---
title: Opplæring for å legge til eller redigere modelldrevne appkomponenter med PowerApps | MicrosoftDocs
description: Bruk apputforming for PowerApps til å legge til eller redigere komponenter
keywords: ''
ms.date: 03/30/2018
ms.service: crm-online
ms.custom: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- PowerApps
author: Mattp123
ms.assetid: be93b9d7-f1c2-4ee7-8d7c-0f5c34dfa5f7
ms.author: matp
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
caps.latest.revision: 17
topic-status: Drafting
ms.openlocfilehash: 87fec3bff3ad21a5c0474b67f001cca5c902d609
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/08/2018
ms.locfileid: "39696092"
---
# <a name="tutorial-add-or-edit-model-driven-app-components-in-the-powerapps-app-designer"></a>Opplæring: legg til eller rediger modelldrevne appkomponenter for PowerApps apputforming

I denne opplæringen finner du ut hvordan du legger til komponenter til og fjerner komponenter fra en modelldrevet app. 

En modelldrevet app består av ulike komponenter. Du kan legge til to typer komponenter i en app: artefakter og enhetsressurser. Enheter, instrumentbord og forretningsprosessflyter er alle artefakter til appen, i forbindelse med apputforming. Enhetsressurser består av skjemaer, visninger, diagrammer og instrumentbord.  
  
Apputforming referer til eksisterende metadata i standardløsningen. Du kan bruke den til å opprette komponenter som skjemaer, visninger, diagrammer og instrumentbord.  
  
## <a name="app-designer-layout"></a>Apputforming-oppsett  
 Apputforming har to hovedområder. På venstre side er lerretet hvor du legger til appkomponenter.  
  
![Apputforming-lerret](../model-driven-apps/media/app-designer-canvas-pane.png)

 Til høyre ser du fanene som du bruker for å velge komponenter og angi komponentegenskaper.  
  
 ![Apputforming-komponenter](../model-driven-apps/media/app-designer-canvas-components-tab.png "Apputforming-komponenter")  
  
 På lerretet ser du områder for områdekartet, forretningsprosessflyt, instrumentbord og enheter. Når du velger et instrumentbord eller en forretningsprosessflyt, eller konfigurerer et områdekart, legger apputforming automatisk til enhetene som brukes i disse komponentene, på lerretet. Etter at enhetene er på plass, trenger du bare å velge hver enhet og legge til nødvendige enhetsressurser som skjemaer, visninger og diagrammer i enhetene.
 
 Du kan også bruke **Søk på lerret** til å søke etter komponenter på lerretet. Når du velger **Søk på lerret**, åpnes en ny søkefane til høyre for fanene i ruten lengst til høyre.   
  
 ![Alternativer for lerretsøk](media/app-designer-search-tab.png "Lerretsøk")

## <a name="open-an-app"></a>Å åpne en app
1. Logg deg på [PowerApps](https://web.powerapps.com/). 

2. Velg **Modelldrevet** > **Apper**, og deretter velger du en eksisterende app eller **Opprett en app**. Hvis du vil ha informasjon om hvordan du oppretter en app, kan du se [Opprett eller rediger en modelldrevet app ved bruk av apputforming](create-edit-app.md#create-an-app).

## <a name="add-an-artifact-entity-dashboard-or-business-process-flow"></a>Legg til en artefakt (enhet, instrumentbord eller forretningsprosessflyt)  
 Når du legger til et instrumentbord eller en forretningsprosessflyt i en app, legges enhetene de bruker automatisk til i appen. Når du legger til en enhet, legges flisene for ressursene til automatisk. Du kan legge til artefakter på utformingslerretet på to måter: ved å bruke **Legg til**-knappen ![Legg til-knapp på utformeren](../model-driven-apps/media/dynamics365-designer-addbutton.PNG "Legg til-knapp på utformeren") på kommandolinjen, eller ved å bruke flisene på **Komponenter**-fanen.  
  
 Her ser du fremgangsmåten for å legge til et instrumentbord i en app. Bruk den samme fremgangsmåten for å legge til en forretningsprosessflyt eller enhet.  
  
1.  Velg **Instrumentbord**-flisen på apputforming-lerretet.  
  
     På apputforming-lerretet ser du instrumentbordene som er tilgjengelige i standardløsningen, i ruten lengst til høyre.  
  
    > [!TIP]
    >  Du kan alternativt også gjøre ett av følgende:  
    >   
    > - Velg **Legg til** ![Legg til-knapp på utformeren](../model-driven-apps/media/dynamics365-designer-addbutton.PNG "Legg til-knapp på utformeren"), og velg deretter **Instrumentbord**.  
    > - Velg **Instrumentbord** på **Komponenter**-fanen, under **Artefakter**.  
  
2.  Skriv inn et par nøkkelord for instrumentbordnavnet du leter etter, i **Søk**-boksen.  
  
     Instrumentbordlisten filtreres for å vise resultatene som stemmer overens med nøkkelordene.  
  
3.  Hvis du ønsker at brukerne bare skal bruke utvalgte instrumentbord, merker du av for det instrumentbordet du ønsker å legge til. Du kan velge fra følgende typer instrumentbord:
    - **Klassiske instrumentbord** vises både i nettappen og Enhetlig grensesnitt-appen.
    - **Interaktive instrumentbord** vises bare i Enhetlig grensesnitt-appen. Hvis du har valgt klienttypen for appen som nettapp, vises ikke alternativet **Interaktive instrumentbord**.

     Disse instrumentbordene legges til på **Instrumentbord**-flisen på apputforming-lerretet. **Dashboard**-flisen viser også en telling av antallet instrumentbord som ble lagt til i appen. Hvis du ikke velger et instrumentbord, vises **Alle** i stedet for instrumentbordantallet, og alle instrumentbordene blir tilgjengelig til brukerne når de bruker appen.  
  
     Alle enhetene instrumentbordet bruker legges også til i **Enhetsvisning**-området. Hvis du for eksempel legger til instrumentbordet Kundeserviceleder, legges Tilfelle-, Rettigheter- og Køelement-enhetene til i Enhetsvisning-området. Fliser for ressursene legges også til, for hver enhet. Du kan bruke disse flisene for å legge til skjemaer, visninger og diagrammer. Mer informasjon[: legg til eller rediger komponenter apputforming for PowerApps](add-edit-app-components.md#bkmk_AddEntityAssets)   
  
    ![Legg til enhet på apputforming-lerretet](../model-driven-apps/media/add-entity-app-designer-canvas.png "Legg til en enhet på apputforming-lerretet")  
  
4.  Hvis instrumentbordet du ønsker ikke finnes i standardløsningen, kan du opprette et instrumentbord ved å velge **Opprett ny** på **Komponenter**-fanen til høyre på lerretet.  
  
     ![Opprett ny kobling på Komponenter-fanen i apputforming](../model-driven-apps/media/app-designer-components-tab-create-new.png "Opprett ny kobling på Komponenter-fanen i apputforming")  
  
     Instrumentbordutforming åpnes. Hvis du vil ha mer informasjon, kan du se [Opprett og rediger instrumentbord](create-edit-dashboards.md)  
  
    > [!NOTE]
    > - Når du legger til en forretningsprosessflyt eller enhet, åpner **Opprett ny**-alternativet den tilsvarende utformeren. Hvis du vil finne ut mer om hvordan du oppretter forretningsprosessflyter eller enheter, kan du se [Opprett en forretningsprosessflyt](/flow/create-business-process-flow) og [Opprett en egendefinert enhet](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-create-entity).  
      
  
5.  Når du er ferdig å legge til artefakter, velger du **Lagre** på kommandolinjen.  
  
<a name="bkmk_AddEntityAssets"></a>   
## <a name="add-entity-assets-forms-views-charts-or-dashboards"></a>Legg til enhetsressurser (skjemaer, visninger, diagrammer eller instrumentbord)  
 Med artefakter på plass kan du begynne å legge til enhetsressurser som skjemaer, visninger, diagrammer og instrumentbord i appen.
Hvis du i tillegg bruker Enhetlig grensesnitt-klienten, kan du også legge til instrumentbordressurser for enheten i appen.  
  
 Denne inndelingen beskriver fremgangsmåten for å legge til et skjema i appen. Bruk den samme fremgangsmåten for å legge til en visning eller et diagram i appen.  
  
1.  Velg **Skjemaer**-flisen på apputforming-lerretet for enheten du ønsker å legge til et skjema i.  
  
     Hele raden for enheten merkes på apputforming-lerretet. Til høyre ser du alle eksisterende skjemaer for den utvalgte enheten.  
  
    > [!NOTE]
    >  Du kan alternativt også gjøre ett av følgende:  
    >   
    > - Velg **Legg til** ![Legg til-knapp på utformeren](../model-driven-apps/media/dynamics365-designer-addbutton.PNG "Legg til-knapp på utformeren"), og velg deretter **Skjemaer**.  
    > - Velg **Skjemaer** på **Komponenter**-fanen under **Enhetsressurser**.  
  
    > [!TIP]
    >  En **Flere alternativer**-knapp (**...**) vises i **Velg enheter**-listen på **Komponenter**-fanen, for alle enheter som er utvalgt for appen. Hvis du vil legge til alle ressurser for den valgte enheten, kan du velge **Flere alternativer** (**...**), og velg deretter **Legg til alle ressurser**.  
  
2.  Hvis du ønsker at appbrukerne bare skal bruke utvalgte skjemaer, merker du av for skjemaene du ønsker å legge til. Skjemaene definerer hvordan brukere vil se og samhandle med dataene i appen. 
 
     Skjema-flisen i den utvalgte enheten viser hvor mange skjemaer som er lagt til.  
  
     ![Skjema-flis for tilfelleenheten](../model-driven-apps/media/add-forms-entity.png "Skjema-flis for tilfelleenheten")  
  
     Hvis du for eksempel ikke velger et skjema for en enhet, vises alle skjemaene for denne enheten til sluttbrukere mens de bruker appen. Denne virkemåten gjelder også for visninger og diagrammer, hvis ingen visning eller diagram er valgt. Dette bidrar til å opprette apper raskt når du trenger å arbeide med alle tilgjengelige komponenter. Det er ikke nødvendig å velge hver komponent under utforming av apper.  

     Hvis ingen instrumentbord eller forretningsprosessflyter er valgt, blir alle instrumentbord og forretningsprosessflyter tilgjengelig for brukere mens de bruker appen.
  
    > [!NOTE]
    > Hver enhet som du legger til, må ha minst ett aktivt skjema å kjøre appen. Hvis du har valgt flere skjemaer, brukes det første aktive skjemaet som vises i standardløsningen, når brukere kjører appen.  
  
3.  Hvis du vil legge til et nytt skjema som ikke er tilgjengelig i listen, velger du **Opprett ny**.  
  
     I rullegardinlisten velger du skjematypen du vil opprette.  
  
    > [!NOTE]
    >  Rullegardinlisten er bare tilgjengelig når du legger til skjemaer. Den er ikke tilgjengelig for visninger og diagrammer.  
  
     Skjemautformingen åpnes. Hvis du vil ha mer informasjon, kan du se [Opprett og utform skjemaer](create-design-forms.md)  
  
     Når du legger til en isning eller et diagram, åpner **Opprett ny**-alternativet den tilsvarende utformeren. Hvis du vil ha mer informasjon, kan du se [Forstå visninger](create-edit-views.md) og [Opprett eller rediger et systemdiagram](create-edit-system-chart.md)  
  
    > [!NOTE]
    >  Når du legger til en visning, kan du bare referere til offentlige visninger som er oppført under **Visninger**-noden i løsningsutforsker.  
  
4. Velg pil ned ![rullegardinikon](../model-driven-apps/media/drop-down-icon.png "pil ned") for å utvide flisen og se en liste over skjemaer som er lagt til.  
  
     ![Skjema-flisen utvidet i apputforming](../model-driven-apps/media/app-designer-expanded-form-tile.png "Skjema-flisen utvidet i apputformingen")  
  
5.  Gjenta denne fremgangsmåten for å legge til enhetsvisninger og diagrammer i appen.  
  
6.  Velg **Lagre**.  
  
## <a name="edit-or-remove-artifacts"></a>Rediger eller fjern artefakter  
  
- Hvis du vil redigere et instrumentbord eller en forretningsprosessflyt, velger du pil ned ![rullegardinikon](../model-driven-apps/media/drop-down-icon.png "pil ned") for å utvide flisen, og velg deretter knappen Områdekartutforming ![knappen Åpen områdekartutforming](../model-driven-apps/media/dynamics365-open-designer.PNG "knappen Åpen områdekartutforming") som tilsvarer instrumentbordet eller forretningsprosessflyten som du vil redigere.  
  
     Utformingsverktøyet for den valgte artefakten, åpnes.  
  
- Hvis du vil fjerne et instrumentbord eller en forretningsprosessflyt, velger du pil ned ![rullegardinikon](../model-driven-apps/media/drop-down-icon.png "pil ned") for å utvide flisen, og velg deretter instrumentbordet eller frretningsprosessflyten som du vil fjerne. Velg **Fjern** på kommandolinjen.  

    En annen måte å fjerne et instrumentbord eller en forretningsprosessflyt på er ved å fjerne det tilsvarende merket på **Komponenter**-fanen.
  
- Hvis du vil redigere eller fjerne en enhet, velger du enhetsflisen, og velg deretter **Rediger** eller **Fjern** på kommandolinjen. Når du redigerer en enhet, åpnes løsningsutforskeren. Her kan du gjøre endringer i enheten.  
  
     En annen måte å fjerne en komponent på er å velge instrumentbordet, forretningsprosessflyten eller enhetflisen. Fjern merket for artefaktene du vil fjerne fra utformeren, på **Komponenter**-fanen.  
  
    > [!NOTE]
    >  Når du gjør endringer i en enhet&mdash;, som å endre navn eller beskrivelse for en enhetsvisning&mdash;, vises ikke endringene i apputforming med mindre endringene publiseres i løsningsutforskeren.  
  
## <a name="edit-or-remove-entity-assets"></a>Rediger eller fjern enhetsressurser  

### <a name="edit-entity-assets"></a>Rediger enhetsressurser
  
1. Velg pil ned ![rullegardinikon](../model-driven-apps/media/drop-down-icon.png "pil ned") for å utvide flisen for skjemaer, visninger, diagrammer eller instrumentbord.  
  
2. Velg skjemaet, visningen, diagrammet eller instrumentbordet som du vil redigere.  
  
3. Velg **Rediger** på kommandolinjen.

   eller

   Velg knappen Områdekartutforming ![knappen Åpen områdekartutforming](../model-driven-apps/media/dynamics365-open-designer.PNG "knappen Åpen områdekartutforming") tilsvarer skjemaet, visningen, diagrammet eller instrumentbordet.  

### <a name="remove-entity-assets"></a>Fjern enhetsressurser  

1. Velg pil ned ![rullegardinikon](../model-driven-apps/media/drop-down-icon.png "pil ned") for å utvide flisen for skjemaer, visninger, diagrammer eller instrumentbord.  
  
2. Velg skjemaet, visningen, diagrammet eller instrumentbordet som du vil redigere.

3. Velg **Fjern** på kommandolinjen. 

Eventuelt kan du velge flisen for skjemaer, visninger, diagrammer eller instrumentbord, og deretter fjerner du merket for ressursene du vil fjerne fra utformeren, på **Komponenter**-fanen.  
  
## <a name="next-steps"></a>Neste trinn  
 [Opprett et områdekart for en app](create-site-map-app.md) </br>  
 [Valider og publiser en app](validate-app.md)
