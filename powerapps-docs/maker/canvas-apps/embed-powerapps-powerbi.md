---
title: Slik bygger du inn en ny app i en Power BI-rapport | Microsoft Docs
description: Slik bygger du inn en app som bruker samme datakilde og kan filtreres som andre rapportelementer
services: powerapps
suite: powerapps
documentationcenter: na
author: mgblythe
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: tutorial
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/15/2018
ms.author: mblythe
ms.openlocfilehash: 839a9ce79f86fccd9fb91afe3938cc76160f0c08
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/22/2018
ms.locfileid: "30996047"
---
# <a name="tutorial-embed-a-new-app-in-a-power-bi-report"></a>Opplæring: Slik bygger du inn en ny app i en Power BI-rapport

Med Power BI kan du utvide funksjonene ved å legge til *egendefinerte visualobjekter* i en rapport. I denne opplæringen bruker du det egendefinerte visualobjektet fra PowerApps til å opprette en ny app som er innebygd i eksempelrapporten. Appen samhandler med andre elementer i denne rapporten.

Hvis du ikke har et PowerApps-abonnement, kan du [opprette en gratiskonto](../signup-for-powerapps.md) før du begynner.

I denne opplæringen lærer du hvordan du kan:
> [!div class="checklist"]
> * Importere det egendefinerte visualobjektet fra PowerApps til en Power BI-rapport
> * Opprette en ny app som bruker data fra rapporten
> * Vise appen i rapporten

## <a name="prerequisites"></a>Forutsetninger

* [Google Chrome](https://www.google.com/chrome/browser/) eller [Microsoft Edge](https://www.microsoft.com/windows/microsoft-edge)-nettleser
* Et [Power BI-abonnement](https://docs.microsoft.com/power-bi/service-self-service-signup-for-power-bi), med et installert [Eksempel på mulighetsanalyse](https://docs.microsoft.com/power-bi/sample-opportunity-analysis#get-the-content-pack-for-this-sample)
* En forståelse av hvordan du [oppretter apper i PowerApps](data-platform-create-app-scratch.md) og hvordan du [redigerer Power BI-rapporter](https://docs.microsoft.com/power-bi/service-the-report-editor-take-a-tour)

## <a name="import-the-powerapps-custom-visual"></a>Import av et egendefinert visualobjekt fra PowerApps

Det første trinnet er å importere det egendefinerte visualobjektet fra PowerApps slik at du kan bruke det i eksempelrapporten.

1. Klikk eller trykk på **Kommende muligheter**-fanen i rapporten Eksempel på mulighetsanalyse.

2. Klikk eller trykk på **Rediger rapport** øverst i rapporten.

3. Klikk eller trykk på ellipsene (**. . .**) > **Importer fra Marketplace** i **Visualiseringer**-ruten. 

    ![Import fra Marketplace](media/embed-powerapps-powerbi/import-visual.png)

4. Søk etter PowerApps, og klikk deretter på **Legg til** på **Power BI-visualobjekter**-skjermen. Power BI legger til det egendefinerte visualobjektikonet på bunnen av **Visualiseringer**-ruten.

    ![PowerApps-visualobjektikonet](media/embed-powerapps-powerbi/powerapps-icon.png)

5. Lagre rapporten.

## <a name="create-a-new-app"></a>Oppretting av en ny app
Du kan nå legge til det egendefinerte visualobjektet i rapporten og opprette en ny app som er basert på dataene i rapporten. Når du oppretter appen, starter PowerApps Studio med en direkte datatilkobling mellom PowerApps og Power BI.

1. Flytt og endre størrelsen på noen av rapportflisene for å lage plass til en app.

    ![Flytting og endring av størrelsen på rapportfliser](media/embed-powerapps-powerbi/move-resize.png)

2. Klikk eller trykk på det egendefinerte visualobjektikonet fra PowerApps, og endre størrelsen på flisen så den passer inn på plassen du har laget.

3. Velg **Navn**, **Produktkode** og **Salgstrinn** i **Felt**-ruten. 

    ![Velg felt](media/embed-powerapps-powerbi/select-fields.png)

4. Velg PowerApps-miljøet der du vil opprette appen, i den egendefinerte visualobjekt-flisen, og klikk eller trykk deretter på **Opprett ny**.

    ![Oppretting av ny app](media/embed-powerapps-powerbi/create-new-app.png)

    Du ser at en grunnleggende app er opprettet i PowerApps Studio, med et *galleri* som viser ett av feltene du valgte i Power BI.

5.  Endre størrelsen på galleriet slik at det tar opp bare en halvdel av skjermen. 

6. Klikk eller trykk på **Screen1** i den venstre ruten, og angi deretter skjermens **Fill**-egenskap til LightBlue (slik at den vises bedre i rapporten).

    ![App med endret størrelse på galleriet](media/embed-powerapps-powerbi/app-gallery.png)

6. Legg til en etikettkontroll under galleriet, med **Text**-egenskapen angitt til `"Opportunity Count: " & CountRows(Gallery1.AllItems)`. Den viser nå det totale antallet muligheter i datasettet.

    ![Antall muligheter](media/embed-powerapps-powerbi/opportunity-count.png)

7. Lagre appen med navnet Muligheter. 


## <a name="view-the-app-in-the-report"></a>Slik vises appen i rapporten
Appen er nå tilgjengelig i rapporten, og den fungerer sammen med andre visualobjekter, fordi de deler den samme datakilden.

Velg **Jan** i sliceren i Power BI-rapporten, som filtrerer hele rapporten, inkludert dataene i appen.

![Filtrering av rapport](media/embed-powerapps-powerbi/filtered-report.png)

Legg merke til at antall muligheter i appen samsvarer med tallet øverst til venstre i rapporten. Du kan velge andre elementer i rapporten, og dataene i appen oppdateres.


## <a name="clean-up-resources"></a>Fjerning av ressurser
Hvis du ikke vil bruke Eksempel på mulighetsanalyse lenger, kan du slette instrumentbordet, rapporten og datasettet.


## <a name="next-steps"></a>Neste trinn
I denne opplæringen har du lært hvordan du kan:
> [!div class="checklist"]
> * Importere det egendefinerte visualobjektet fra PowerApps til en Power BI-rapport
> * Opprette en ny app som bruker data fra rapporten
> * Slik vises appen i rapporten

Gå videre til den neste artikkelen for å finne ut mer
> [!div class="nextstepaction"]
> [Egendefinert visualobjekt fra PowerApps for Power BI](powerapps-custom-visual.md)

