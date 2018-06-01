---
title: Å legge til bilder i Excel | Microsoft Docs
description: Trinnvise instruksjoner for å legge til bildefiler og tegninger med penn til Excel i en konto for lagring i skyen
services: ''
suite: powerapps
documentationcenter: ''
author: skjerland
manager: anneta
editor: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/25/2016
ms.author: sharik
ms.openlocfilehash: 75b3315833fc6ced9ef3d8eb252d0f8639ccd696
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/22/2018
ms.locfileid: "30995862"
---
# <a name="add-images-to-excel-from-powerapps"></a>Å legge til bilder til Excel fra PowerApps
Opprette en app automatisk hvor brukere kan vise, legge til eller slette bilder fra filer eller tegninger fra en **pennkontroll**. Appen er basert på en Excel-fil som du oppretter og laster opp til en konto for lagring i skyen.

## <a name="prerequisites"></a>Forutsetninger

* Kjennskap til [å legge til og konfigurere kontroller](add-configure-controls.md).
* Kjennskap til [konfigurering av Excel-data som en tabell](https://support.office.com/article/Format-an-Excel-table-6789619F-C889-495C-99C2-2F971C0E2370?ui=en-US&rs=en-US&ad=US).
* En [PowerApps-tilkobling](add-data-connection.md) til en konto for skylagring (for eksempel Dropbox, OneDrive eller Google Drive) der du kan lagre en Excel-fil.

## <a name="create-the-data-source-and-the-app"></a>Slik oppretter man datakilden og appen
1. I Excel kan du legge til **Bildetekst** og **Bilde [Bilde]** til to valgfrie celler som er side ved side (for eksempel A1 og B1) og som er rett ovenfor to tomme celler.
2. Formater celler som du har oppdatert og cellene like under dem som en tabell, og gi navn til tabellen (for eksempel **Bilder**).
   
    ![Å opprette en tabell](./media/add-images-to-excel/create-table.png)
3. Lagre filen (for eksempel som **ImageDemo**), og last det opp til kontoen for skylagring.
4. I PowerApps kan du klikke eller trykke på **Ny** på **Fil**-menyen (langs venstre kant hvis du ennå ikke har åpnet en app), og deretter klikker eller trykker du på **Telefonoppsett** i flisen for kontoen for skylagring.
   
    ![Velge konto for lagring i skyen](./media/add-images-to-excel/select-account.png)
5. Klikk eller trykk på filen du opprettet under **Velg en Excel-fil**.
   
    ![Å velge arbeidsbok](./media/add-images-to-excel/select-workbook.png)
6. Under **Velg en tabell** klikker eller trykker du på tabellen som du opprettet, og deretter klikker eller trykker du på **Koble til**.
   
    ![Å velge tabell](./media/add-images-to-excel/select-table.png)
7. Hvis du nettopp installerte eller oppgraderte PowerApps, kan du ta en titt på hurtiginnføringen, eller klikk eller trykk på **Hopp over**.
   
    ![Første skjermbildet i Hurtiginnføring](./media/add-images-to-excel/quick-tour.png)

## <a name="add-an-image-from-a-file"></a>Å legge til et bilde fra en fil
1. Åpne forhåndsvisningsmodus ved å trykke på F5 (eller ved å klikke på avspillingsknappen nær hjørnet øverst til høyre). Deretter klikker eller trykker du på pluss-ikonet øverst til høyre.
   
    ![Pluss-ikonet](./media/add-images-to-excel/plus-icon.png)
2. I **Bildetekst**-boksen skriver eller limer du inn en kort beskrivelse av bildefilen du vil legge til, og deretter klikker eller trykker du under for å angi en fil.
3. I dialogboksen **Åpne** blar du til du finner filen du vil legge til, klikker eller trykker på den, og deretter klikker eller trykker du på **Åpne**.
   
    ![Å legge til en bildetekst og et bilde](./media/add-images-to-excel/add-image.png)
4. Klikk eller trykk på ikon med hake øverst til høyre for å lagre endringene.
   
    ![Å lagre endringer](./media/add-images-to-excel/checkmark-icon.png)
5. Legg til så mange bilder som du ønsker ved å gjenta de forrige tre trinnene, og trykk deretter på ESC for å gå tilbake til standardarbeidsområdet.
6. (valgfritt) Slett begge **Etikett**-kontrollene som viser tittelen på hvert bilde.

## <a name="add-a-drawing"></a>Å legge til en tegning
1. Vis **EditScreen1** ved å klikke eller trykke på den i det venstre navigasjonsfeltet, og klikk eller trykk deretter på bildekortet for å merke det.
   
    ![Å velge bildekort](./media/add-images-to-excel/select-card.png)
2. Klikk eller trykk på kortvelgeren for bildekortet i ruten til høyre, og deretter klikker eller trykker du på **Legg til notater**.
   
    ![Å legge til notater](./media/add-images-to-excel/add-notes.png)
3. Vis **BrowseScreen1** ved å klikke eller trykke på den i det venstre navigasjonsfeltet, og deretter åpner du forhåndsvisningsmodus.
4. Klikk eller trykk på pluss-ikonet øverst til høyre, legg til en bildetekst og tegn et bilde i **pennkontrollen**.
   
    ![Å tegne et bilde](./media/add-images-to-excel/draw-picture.png)
5. Klikk eller trykk på ikon med hake øverst til høyre for å lagre endringene.
   
    ![Å lagre endringer](./media/add-images-to-excel/checkmark-icon.png)
6. Legg til så mange bilder som du ønsker ved å gjenta de forrige to trinnene, og trykk deretter på ESC for å gå tilbake til standardarbeidsområdet.

