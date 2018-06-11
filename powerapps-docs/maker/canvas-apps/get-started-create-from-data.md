---
title: Å generere en app fra Excel | Microsoft Docs
description: Slik bruker du PowerApps til å automatisk generere en app ved hjelp av en Excel-fil som er lagret i en skylagringskonto
documentationcenter: na
author: AFTOWen
manager: kfile
ms.service: powerapps
ms.devlang: na
ms.topic: conceptual
ms.component: canvas
ms.date: 03/18/2018
ms.author: anneta
ms.openlocfilehash: 54d53d5f3385be4b5d38a2bf220da139ba3bd3a4
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/04/2018
ms.locfileid: "31827262"
---
# <a name="generate-an-app-from-excel-in-powerapps"></a>Å generere en app fra Excel i PowerApps
I dette emnet vil du automatisk generere din første app i PowerApps ved hjelp av data fra en Excel-tabell. Du velger en Excel-fil, genererer en app og kjører deretter appen du genererer. Alle genererte apper inkluderer skjermer for å bla gjennom poster, vise postdetaljer og opprette eller oppdatere poster. Du kan raskt få en fungerende app ved hjelp av Excel-data ved å generere en app, og deretter kan du tilpasse appen for bedre å møte dine behov. 

Excel-filen må være i en konto for lagring i skyen, for eksempel OneDrive, Google Drive eller Dropbox. Dette emnet bruker OneDrive for Business.

Hvis du ikke har en PowerApps-lisens, kan du [registrere deg gratis](../signup-for-powerapps.md).

## <a name="prerequisites"></a>Forutsetninger ##
Hvis du ønsker å følge dette emnet helt etter boken, kan du laste ned [Flooring Estimates](https://az787822.vo.msecnd.net/documentation/get-started-from-data/FlooringEstimates.xlsx)-filen i Excel og lagre den i [skylagringskontoen](connections/cloud-storage-blob-connections.md).

> [!IMPORTANT]
> Du kan også bruke din egen Excel-fil, men dataene må være formatert som en tabell. Hvis du vil ha mer informasjon, kan du se [Å formatere en tabell i Excel](how-to-excel-tips.md). 

## <a name="generate-the-app"></a>Å generere appen
1. Logg deg på [PowerApps](https://web.powerapps.com).

    ![Hjemmesiden for PowerApps](./media/get-started-create-from-data/sign-in.png)

1. Under **Lag apper som disse** holder du pekeren over **Begynn fra data**, og deretter velger du **Lag denne appen**.

    ![Alternativ for å opprette en app](./media/get-started-create-from-data/make-this-app.png)

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

1. Klikk eller trykk på plusstegnet for å legge til en post, og legg til dataene du måtte ønske. Deretter klikker eller trykker du på hakeikonet for å lagre endringene.

1. Klikk eller trykk på Neste-pilen for posten som du har lagt til, klikk eller trykk på blyantikonet for å redigere posten, oppdater ett eller flere felt og klikk eller trykk på hakeikonet for å lagre endringene.

1. Klikk eller trykk på Neste-pilen for posten som du har lagt til, klikk eller trykk på blyantikonet for å redigere posten, oppdater ett eller flere felt og klikk eller trykk på hakeikonet for å lagre endringene.

1. Klikk eller trykk på Neste-pilen for posten som du har lagt til, og klikk eller trykk så på papirkurvikonet for å slette posten.

## <a name="next-steps"></a>Neste trinn
Tilpass standard Bla gjennom-skjermen slik at den passer dine behov. Du kan for eksempel sortere og filtrere listen etter produktnavn og ikke kategori.

> [!div class="nextstepaction"]
> [Å tilpasse en standard Bla gjennom-skjerm](customize-layout-sharepoint.md).