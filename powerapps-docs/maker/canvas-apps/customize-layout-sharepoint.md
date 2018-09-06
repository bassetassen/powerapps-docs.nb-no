---
title: Opplæring – slik tilpasser du et galleri i en generert app | Microsoft Docs
description: I denne opplæringen kan du tilpasse dataene som vises i galleriet og andre elementer for en app som har blitt generert automatisk i PowerApps.
author: AFTOwen
manager: kvivek
ms.service: powerapps
ms.topic: tutorial
ms.custom: canvas
ms.reviewer: ''
ms.date: 05/06/2018
ms.author: anneta
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 6e77ddfcc572a776e80ab90d3907aaa7b67f01ea
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/24/2018
ms.locfileid: "42864776"
---
# <a name="tutorial-customize-a-gallery-in-powerapps"></a>Opplæring: Tilpassing av et galleri i PowerApps

I denne opplæringen får du tilpasse en liste over poster, kalt et galleri, og gjøre andre endringer i en app som ble generert automatisk i Microsoft PowerApps. Brukere kan administrere data i appen selv om du ikke gjør disse endringene, men appen vil være enklere å bruke hvis du tilpasser den for organisasjonens behov.

Galleriet for denne opplæringen samsvarer eksempelvis med denne grafikken som standard. E-postadressen er mer fremtredende enn andre typer data, og brukere kan sortere og filtrere galleriet basert på teksten i denne adressen:

![Standard-galleriet](./media/customize-layout-sharepoint/gallery-before.png)

Brukerne kan imidlertid være mer interessert i navnet på kontoen enn i e-postadressen, så du kan konfigurere galleriet til å utheve, sortere og filtrere basert på de viktige dataene for organisasjonen. I tillegg kan du endre tittelen på standardskjermen for å skille den fra de andre skjermene i appen.

![Det endelige galleriet](./media/customize-layout-sharepoint/gallery-after.png)

Du kan også legge til et rullefelt slik at brukere som ikke har berøringsskjermer eller musehjul kan bla gjennom hele galleriet.

> [!div class="checklist"]
> * Å endre gallerioppsettet
> * Endre datatypen som vises i galleriet
> * Å endre kolonnene hvor brukere kan sortere og søke etter dataene
> * Å endre tittelen på skjermen
> * Visning av et rullefelt

Denne opplæringen starter med en app som ble generert fra en bestemt datakilde. De samme prinsippene gjelder imidlertid for alle apper som du genererer i PowerApps, enten fra en SharePoint-liste, en Excel-tabell eller en annen datakilde.

Hvis du ikke er registrert for PowerApps, kan du [registrere deg gratis](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) før du begynner.

## <a name="prerequisites"></a>Forutsetninger

[Generer en app](data-platform-create-app.md) fra **Kontoer**-enheten for Common Data Service (CDS) for apper.

## <a name="open-the-generated-app"></a>Slik åpner du den genererte appen

1. Logg deg på [PowerApps](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc), og klikk eller trykk deretter på **Apper** nær venstre kant.

    [![Hjemmesiden for PowerApps](./media/customize-layout-sharepoint/sign-in.png)](./media/customize-layout-sharepoint/sign-in.png#lightbox)

1. Finn appen du genererte, velg ellipse-ikonet (**...** ), og velg deretter **Rediger**.

    ![Å åpne appen for redigering](./media/customize-layout-sharepoint/open-app.png)

1. Hvis dialogboksen **Velkommen til PowerApps Studio** vises, klikker eller trykker du på **Hopp over**.

## <a name="change-the-layout"></a>Endrer oppsettet

1. Velg **BrowseGallery1** i den venstre navigasjonsruten.

    Når galleriet er valgt, omgis det av en valgboks med håndtak.

    ![Valg av galleri](media/customize-layout-sharepoint/select-gallery-1.png)

1. Nær høyre kant velger du **Kontoer** for å åpne **Data**-ruten.

    ![Åpne ** Data**-ruten](./media/customize-layout-sharepoint/open-data-pane.png)

1. I **Data**-ruten åpner du listen over alternativer under **Oppsett**.

    ![Visning av alternativer for oppsett](./media/customize-layout-sharepoint/show-layouts.png)

1. Velg alternativet som bare viser en tittel i listen over alternativer.

    ![Velg oppsett bare med tittel](./media/customize-layout-sharepoint/choose-layout.png)

1. Åpne listen over alternativer for tittelen i **Data**-ruten.

    Navnet på denne kontrollen avsluttes med et tall, for eksempel **Title1**, men tallet kan variere avhengig av andre handlinger du har gjort.

    ![Å åpne listen over alternativer for titteletikett](./media/customize-layout-sharepoint/show-title-options.png)

1. I listen over alternativer velger du **Kontonavn (navn)** og lukker deretter **Data**-ruten.

    Galleriet viser navnet på hver konto.

    ![Det endelige galleriet](./media/customize-layout-sharepoint/final-gallery.png)

## <a name="change-sort-and-search-columns"></a>Å endre kolonnene for sortering og søk

1. Velg galleriet, som beskrevet i den forrige inndelingen.

    ![Valg av galleri](./media/customize-layout-sharepoint/select-gallery-title.png)

1. Bekreft at egenskapslisten viser **Elementer** nær det øvre venstre hjørnet.

    ![Elementer-egenskaper](./media/customize-layout-sharepoint/items-property.png)

    Verdien for denne egenskapen vises på formellinjen. Du setter denne egenskapen til å angi ikke bare datakilden for galleriet, men også kolonnene hvor brukere kan sortere og søke i dataene.

1. Kopier denne formelen, og lim den deretter inn i formellinjen.

    ```SortByColumns(Search(Accounts, TextSearchBox1.Text, "name"), "name", If(SortDescending1, Descending, Ascending))```

    Ved hjelp av denne formelen kan du kontrollere at:

    * Hvis en bruker skriver inn ett eller flere tegn i søkefeltet, viser galleriet kun kontonavnene som inneholder teksten brukeren skrev inn.
    * Hvis en bruker velger Sorter-ikonet, sorteres galleriet alfabetisk etter kontonavn i enten stigende eller synkende rekkefølge, avhengig av hvor mange ganger brukeren velger ikonet.

     Hvis du vil ha mer informasjon om disse og andre funksjoner, kan du se [formelreferansen](formula-reference.md).

### <a name="test-sorting-and-searching"></a>Testing av sortering og søk

1. Åpne forhåndsvisningsmodus ved å trykke på F5 (eller ved å velge avspillingsknappen nær hjørnet øverst til høyre).

    ![Å åpne forhåndsvisningsmodus](./media/customize-layout-sharepoint/open-preview.png)

1. Nær øvre høyre hjørne av skjermbildet Bla gjennom kan du klikke på sorteringsikonet én eller flere ganger for å endre den alfabetiske sorteringsrekkefølgen mellom stigende og synkende.

    ![Testing av sorteringsikonet](./media/customize-layout-sharepoint/sort-button.png)

1. Skriv inn **k** i søkeboksen for å bare vise navnene på kontoene som inneholder bokstaven du skrev inn.

    ![Å teste søkefeltet](./media/customize-layout-sharepoint/test-filter.png)

1. Fjern all tekst fra søkefeltet, og lukk deretter Forhåndsvisningmodus ved å trykke på ESC (eller ved å klikke eller trykke på lukkeikonet nær øvre høyre hjørne).

## <a name="change-the-screen-title"></a>Å endre tittelen på skjermen

1. Velg tittelen på skjermen ved å klikke eller trykke på den.

    ![Valg av skjermtittel](./media/customize-layout-sharepoint/select-title.png)

1. Pass på at egenskapslisten viser **Tekst**, og erstatt deretter **Kontoer** i formellinjen med **Bla gjennom** (hvor de doble anførselstegnene beholdes).

    ![Oppdatering av skjermtittelen](./media/customize-layout-sharepoint/change-screen-title.png)

    Skjermen gjenspeiler endringen.

    ![Ny skjermtittel](./media/customize-layout-sharepoint/new-screen-title.png)

## <a name="show-a-scrollbar"></a>Viser et rullefelt

Hvis brukerne ikke har berøringsskjermer eller musehjul, konfigurerer du galleriet til å vise et rullefelt når brukeren holder pekeren over det. På denne måten kan brukerne vise alle kontoene, selv om ikke skjermen kan vise alle samtidig.

1. Velg galleriet, som den første prosedyren beskriver.

    ![Valg av galleri](./media/customize-layout-sharepoint/select-gallery-sorted.png)

1. Velg **Vis rullefelt** på **Galleri**-fanen, og bekreft at verdien for egenskapen er endret til **sann**.

    ![Visning av rullefelt](./media/customize-layout-sharepoint/show-scrollbar.png)

## <a name="next-steps"></a>Neste trinn

I denne opplæringen har du tilpasset galleriet og gjort andre endringer i standardskjermen for å bla gjennom postene i en generert app. Du kan også tilpasse standardskjermene for å vise detaljer og opprette eller oppdatere kontoer. Når skjermbildet Bla gjennom inneholder et galleri, inneholder de andre to skjermene i appen skjemaer. Du kan for eksempel endre hvilke typer data skjemaet skal vise, og i hvilken rekkefølge.

> [!div class="nextstepaction"]
> [Tilpassing av skjemaer](customize-forms-sharepoint.md)
