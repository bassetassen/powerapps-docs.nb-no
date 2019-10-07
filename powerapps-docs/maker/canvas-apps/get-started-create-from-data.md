---
title: Generer en lerretsapp fra Excel | Microsoft Docs
description: Bruk PowerApps til å generere en lerretsapp automatisk ved hjelp av en Excel-fil som er lagret på en skylagringskonto.
author: tapanm-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 01/14/2019
ms.author: tapanm
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 576e61e6e4ea1aad317fdec8f49f76bfcd1e0b6a
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/07/2019
ms.locfileid: "71990259"
---
# <a name="generate-a-canvas-app-from-excel-in-powerapps"></a>Generer en lerretsapp fra Excel i PowerApps

Dette emnet beskriver hvordan du genererer din første lerretsapp i PowerApps automatisk ved hjelp av data fra en Excel-tabell. Du velger en Excel-fil, genererer en app og kjører deretter appen du genererer. Alle genererte apper inkluderer skjermer for å bla gjennom poster, vise postdetaljer og opprette eller oppdatere poster. Du kan raskt få en fungerende app ved hjelp av Excel-data ved å generere en app, og deretter kan du tilpasse appen for bedre å møte dine behov. 

Excel-filen må være i en konto for lagring i skyen, for eksempel OneDrive, Google Drive eller Dropbox. Dette emnet bruker OneDrive for Business.

Hvis du ikke har en PowerApps-lisens, kan du [registrere deg gratis](../signup-for-powerapps.md).

## <a name="prerequisites"></a>Forutsetninger

Hvis du ønsker å følge dette emnet helt etter boken, kan du laste ned [Flooring Estimates](https://az787822.vo.msecnd.net/documentation/get-started-from-data/FlooringEstimates.xlsx)-filen i Excel og lagre den i [skylagringskontoen](connections/cloud-storage-blob-connections.md).

> [!IMPORTANT]
> Du kan også bruke din egen Excel-fil, men dataene må være formatert som en tabell. Hvis du vil ha mer informasjon, kan du se [Å formatere en tabell i Excel](how-to-excel-tips.md). 

## <a name="generate-the-app"></a>Å generere appen

1. Logg deg på [PowerApps](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc).

1. Hold pekeren over **Begynn fra data** under **Lag din egen app**, og velg deretter **Lag denne appen**.

    ![Alternativ for å opprette en app](./media/get-started-create-from-data/start-from-data.png)

1. Klikk eller trykk på **Telefonoppsett** under **Start med dataene** på flisen for skylagringskontoen.

    ![Alternativ for å opprette en app](./media/get-started-create-from-data/odfb-tile.png)

1. Hvis du blir bedt om det, klikker eller trykker du på **Koble til** og oppgir legitimasjon for denne kontoen.

1. Bla til **FlooringEstimates.xlsx** under **Velg en Excel-fil**, og deretter klikker eller trykker du på den. 

1. Klikk eller trykk på **FlooringEstimates** under **Velg en tabell**, og deretter klikker eller trykker du på **Koble til**.

    ![Alternativ for å opprette en app](./media/get-started-create-from-data/choose-table.png)

## <a name="run-the-app"></a>Å kjøre appen

1. Åpne forhåndsvisningsmodus ved å trykke på F5 (eller ved å klikke på avspillingsikonet nær hjørnet øverst til høyre).

    ![Å åpne Forhåndsvisning](./media/get-started-create-from-data/open-preview.png)

1. Veksle sorteringsrekkefølgen ved å klikke eller trykke på Sorter-ikonet nær øvre høyre hjørne.

    ![Sorter-ikonet](./media/get-started-create-from-data/sort-icon.png)

1. Du kan også filtrere listen ved å skrive inn ett eller flere tegn i søkefeltet.

    Du kan for eksempel skrive eller lime inn **Honey** for å vise den eneste posten som denne strengen vises for i produkt navnet, kategorien eller oversikten.

    ![Filter eksempel](./media/get-started-create-from-data/filter-example.png)

1. Legg til en post:

    1. Velg pluss ikonet.

        ![Pluss-ikonet](./media/get-started-create-from-data/plus-icon.png)

    1. Legg til de ønskede dataene, og velg deretter merke ikonet for å lagre endringene.

        ![Lagre ikon](./media/get-started-create-from-data/save-icon.png)

1. Rediger en post:

    1. Velg pilen for posten du vil redigere.

        ![Neste-pil](./media/get-started-create-from-data/next-arrow.png)

    1. Velg blyant ikonet.

        ![Blyantikon](./media/get-started-create-from-data/pencil-icon.png)

    1. Oppdater ett eller flere felt, og velg merke ikonet for å lagre endringene.

        ![Lagre ikon](./media/get-started-create-from-data/save-icon.png)

        Som et alternativ kan du velge Avbryt-ikonet for å forkaste endringene.

1. Slett en post:

    1. Velg den neste pilen for posten du vil slette.

        ![Neste-pil](./media/get-started-create-from-data/next-arrow.png)

    1. Velg papir kurv ikonet.

        ![Papirkurv-ikon](./media/get-started-create-from-data/trash-icon.png)

## <a name="next-steps"></a>Neste trinn

Tilpass standard Bla gjennom-skjermen slik at den passer dine behov. Du kan for eksempel sortere og filtrere listen etter produkt navn, ikke kategori eller oversikt.

> [!div class="nextstepaction"]
> [Å tilpasse en standard Bla gjennom-skjerm](customize-layout-sharepoint.md).
