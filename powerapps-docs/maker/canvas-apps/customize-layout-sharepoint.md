---
title: Opplæring for tilpassing av et galleri | Microsoft Docs
description: I denne opplæringen tilpasser du standard Bla gjennom-skjermen, inkludert galleriet, i en app som er generert i PowerApps.
services: ''
suite: powerapps
documentationcenter: na
author: AFTOwen
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/11/2018
ms.author: anneta
ms.openlocfilehash: 30ec6be11b40e01dddfe09cf0ac8af0ed3a8a437
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/22/2018
ms.locfileid: "30996117"
---
# <a name="tutorial-customize-a-gallery-in-powerapps"></a>Opplæring: Tilpassing av et galleri i PowerApps
I denne opplæringen tilpasser du standard Bla gjennom-skjermen, inkludert galleriet, i en app som er generert i PowerApps. Du kan administrere data ved bruk av standardappen uten å tilpasse den, men den blir mye kraftigere og enklere å bruke hvis du gjør følgende endringer:

> [!div class="checklist"]
> * Endrer oppsettet
> * Endrer dataene som vises
> * Angir kolonnene for filtrering og sortering
> * Tester filtrering og sortering
> * Endrer tittelen
> * Viser et rullefelt

Denne opplæringen starter med en app som er generert fra [Common Data Service for apper](../common-data-service/data-platform-intro.md), men samme konsepter gjelder for apper som er generert fra SharePoint, Excel og andre datakilder. 

Hvis du ikke har en lisens for PowerApps, kan du [registrere deg gratis](../signup-for-powerapps.md).

## <a name="prerequisites"></a>Forutsetninger
Før du begynner denne opplæringen, må du [generere en app](data-platform-create-app.md) fra Common Data Service for apper.

## <a name="open-the-generated-app"></a>Slik åpner du den genererte appen
1. Logg deg på [PowerApps](https://web.powerapps.com), og klikk eller trykk deretter på **Apper** nær venstre kant.

    ![Hjemmesiden for PowerApps](./media/customize-layout-sharepoint/sign-in.png)

1. Finn appen du har generert, og klikk eller trykk deretter på ellipse-ikonet (**...**) for appen, nær høyre kant.

    ![Appliste](./media/customize-layout-sharepoint/open-for-edit.png)

1. Klikk eller trykk på alternativet for å redigere appen i menyen som vises. 

## <a name="customize-the-gallery"></a>Tilpassing av galleriet
1. Klikk eller trykk på et element på Bla gjennom-skjermen, unntatt den første i listen over kontoer.

    **Galleri**-kontrollen velges i dette trinnet. Denne viser listen over kontoer.

    ![Valgt galleri](./media/customize-layout-sharepoint/select-gallery.png)

1. Klikk eller trykk på **Kontoer** til høyre for **Data**-etiketten, i den høyre ruten.

    ![Åpne ** Data**-ruten](./media/customize-layout-sharepoint/open-data-pane.png)

1. Klikk eller trykk på pil ned i **Data**-ruten, for å åpne listen over alternativer under **Oppsett**.

    ![Visning av alternativer for oppsett](./media/customize-layout-sharepoint/show-layouts.png)

1. Klikk eller trykk på alternativet som bare viser en tittel, i listen over alternativer.

    ![Velg oppsett bare med tittel](./media/customize-layout-sharepoint/choose-layout.png)

1. Klikk eller trykk på pil ned i **Data**-ruten, for å åpne listen over alternativer for tittel.

    ![Velg oppsett bare med tittel](./media/customize-layout-sharepoint/show-title-options.png)

1. Klikk eller trykk på **navn** i listen over alternativer, for å vise dataene i **Galleri**-kontrollen.

    ![Det endelige galleriet](./media/customize-layout-sharepoint/final-gallery.png)


## <a name="set-the-sort-and-search-columns"></a>Angi kolonnene for sortering og søk
1. Velg **Galleri**-kontroll som beskrevet i den forrige delen.

    ![Valg av galleri](./media/customize-layout-sharepoint/select-gallery-title.png)

2. Kontroller at egenskapslisten viser **Items**  nær det øvre venstre hjørnet.

    ![Items-egenskap](./media/customize-layout-sharepoint/items-property.png)

    Verdien for denne egenskapen vises på formellinjen, og bestemmer ikke bare datakilden for galleriet, men også kolonnene for filtrering og sortering.

1. Du kan erstatte begge forekomstene av **emailaddress1** til **name** på formellinjen, og behold de doble anførselstegnene rundt hver forekomst.

    Formelen må samsvare med dette eksemplet:

    ![Formel for Items-egenskapen](./media/customize-layout-sharepoint/items-value.png)

    Den første forekomsten av **name** angir at brukeren kan filtrere listen slik at den bare viser de postene der kontonavnet inneholder teksten brukeren skrev inn i søkefeltet. Den andre forekomsten av **name** angir at brukeren kan sortere listen alfabetisk etter kontonavn. Hvis du vil ha mer informasjon om disse og andre funksjoner, kan du se [formelreferansen](formula-reference.md).

## <a name="test-sorting-and-searching"></a>Test-sortering og søk
1. Åpne forhåndsvisningsmodus ved å trykke på F5 (eller ved å klikke på avspillingsknappen nær hjørnet øverst til høyre).

    ![Åpne forhåndsvisningsmodus](./media/customize-layout-sharepoint/open-preview.png)

1. Nær øvre høyre hjørne av skjermbildet Bla gjennom, klikk ikonet sorter én eller flere ganger for å endre den alfabetiske sorteringsrekkefølgen mellom stigende og synkende.

    ![Testing av sorteringsikonet](./media/customize-layout-sharepoint/sort-button.png)

1. Skriv inn **k** i søkeboksen for å bare vise navnene på kontoene som inneholder bokstaven du skrev inn.

    ![Test søkefeltet](./media/customize-layout-sharepoint/test-filter.png)

1. Fjern all tekst fra søkefeltet, og lukk deretter Forhåndsvisningmodus ved å trykke på Esc (eller ved å klikke eller trykke på lukkeikonet *under* tittellinjen til PowerApps).

## <a name="change-the-title-of-the-screen"></a>Endring av skjermtittel
1. Klikk eller trykk på skjermtittelen for å velge den.

    ![Valg av skjermtittel](./media/customize-layout-sharepoint/select-title.png)

1. Pass på at egenskapslisten viser **Text**, og skriv deretter inn **Bla gjennom**, omgitt av doble anførselstegn, på formellinjen.

    ![Oppdatering av skjermtittelen](./media/customize-layout-sharepoint/change-screen-title.png)

    Skjermen gjenspeiler endringen.

    ![Ny skjermtittel](./media/customize-layout-sharepoint/new-screen-title.png)

## <a name="show-a-scroll-bar"></a>Visning av et rullefelt
Hvis brukerne ikke har berøringsskjermer eller musehjul, konfigurerer du **Galleri**-kontrollen til å vise et rullefelt når brukeren beveger seg over det med musen. På denne måten kan brukerne vise alle kontoene, selv om ikke skjermen kan vise alle samtidig.

1. Velg **Galleri**-kontroll som beskrevet i den første prosedyren.

    ![Valg av galleri](./media/customize-layout-sharepoint/select-gallery-sorted.png)

1. Klikk eller trykk på **Vis rullefelt** på **Galleri**-fanen, og bekreft at verdien for egenskapen er endret til **sann**. 

    ![Visning av rullefelt](./media/customize-layout-sharepoint/show-scrollbar.png)

## <a name="next-steps"></a>Neste trinn
I denne opplæringen har du tilpasset **Galleri**-kontrollen og tittelen på standard Bla gjennom-skjermen til en generert app. Du kan også tilpasse standardskjermene for å vise detaljer og opprette eller oppdatere kontoer. Disse skjermene inneholder en **Visningsskjema**-kontroll og en **Redigeringsskjema**-kontroll, og du kan endre (for eksempel) hvilke typer data de viser og i hvilken rekkefølge disse blir vist.

> [!div class="nextstepaction"]
> [Tilpassing av skjemaer](customize-forms-sharepoint.md)