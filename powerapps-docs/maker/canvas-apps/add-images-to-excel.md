---
title: Å legge til bilder i Excel | Microsoft Docs
description: Trinnvise instruksjoner for å legge til bildefiler og tegninger med penn til Excel i en konto for lagring i skyen
author: AFTOwen
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 10/25/2016
ms.author: anneta
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 89b05b5e1e8073b082e73564f744b7b85fc70426
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/24/2018
ms.locfileid: "42863946"
---
# <a name="add-images-to-excel-from-powerapps"></a>Å legge til bilder til Excel fra PowerApps
Opprette en app automatisk hvor brukere kan vise, legge til eller slette bilder fra filer eller tegninger fra en **Penn**-kontroll. Appen er basert på en Excel-fil som du oppretter og laster opp til en konto for lagring i skyen.

## <a name="prerequisites"></a>Forutsetninger

* Kjennskap til [å legge til og konfigurere kontroller](add-configure-controls.md).
* Kjennskap til [konfigurering av Excel-data som en tabell](https://support.office.com/article/Format-an-Excel-table-6789619F-C889-495C-99C2-2F971C0E2370?ui=en-US&rs=en-US&ad=US).
* En [PowerApps-tilkobling](add-data-connection.md) til en konto for skylagring (for eksempel Dropbox, OneDrive eller Google Drive) der du kan lagre en Excel-fil.

## <a name="create-the-data-source-and-the-app"></a>Slik oppretter man datakilden og appen
1. I Excel kan du legge til **Bildetekst** og **Bilde [Bilde]** til to valgfrie celler ved siden av hverandre (for eksempel A1 og B1) og som er rett ovenfor to tomme celler.
2. Formater cellene du har oppdatert, og cellene like under dem som en tabell, og gi navn til tabellen (for eksempel **Bilder**).
   
    ![Å opprette en tabell](./media/add-images-to-excel/create-table.png)
3. Lagre filen (for eksempel som **ImageDemo**), og last den opp til kontoen for lagring i skyen.
4. I PowerApps kan du klikke eller trykke på **Ny** på **Fil**-menyen (langs venstre kant hvis du ennå ikke har åpnet en app), og deretter klikker eller trykker du på **Telefonoppsett** i flisen for kontoen for lagring i skyen.
   
    ![Velge konto for lagring i skyen](./media/add-images-to-excel/select-account.png)
5. Klikk eller trykk på filen du opprettet under **Velg en Excel-fil**.
   
    ![Å velge arbeidsbok](./media/add-images-to-excel/select-workbook.png)
6. Under **Velg en tabell** klikker eller trykker du på tabellen som du opprettet, og deretter klikker eller trykker du på **Koble til**.
   
    ![Å velge tabell](./media/add-images-to-excel/select-table.png)
7. Hvis hurtiginnføringen vises, følger du den, eller du kan klikke eller trykke på **Hopp over**.
   
    ![Første skjermbildet i Hurtiginnføring](./media/add-images-to-excel/quick-tour.png)

## <a name="add-an-image-from-a-file"></a>Å legge til et bilde fra en fil
1. Åpne forhåndsvisningsmodus ved å trykke på F5 (eller ved å klikke på avspillingsknappen nær hjørnet øverst til høyre). Deretter klikker eller trykker du på pluss-ikonet øverst til høyre.
   
    ![Pluss-ikonet](./media/add-images-to-excel/plus-icon.png)
2. I **Bildetekst**-boksen skriver eller limer du inn en kort beskrivelse av bildefilen du vil legge til, og deretter klikker eller trykker du under for å angi filen.
3. I dialogboksen **Åpne** blar du til du finner filen du vil legge til, klikker eller trykker på den, og deretter klikker eller trykker du på **Åpne**.
   
    ![Å legge til en bildetekst og et bilde](./media/add-images-to-excel/add-image.png)
4. Klikk eller trykk på hakeikonet i øvre høyre hjørne for å lagre endringene.
   
    ![Å lagre endringer](./media/add-images-to-excel/checkmark-icon.png)
5. Legg til så mange bilder du ønsker, ved å gjenta de forrige tre trinnene, og trykk deretter på Esc for å gå tilbake til standardarbeidsområdet.
6. (valgfritt) Slett begge **Etikett**-kontrollene som viser bildeteksten for hvert bilde.

## <a name="add-a-drawing"></a>Å legge til en tegning
1. Vis **EditScreen1** ved å klikke eller trykke på den i det venstre navigasjonsfeltet, og klikk eller trykk deretter på bildekortet for å merke det.
   
    ![Å velge bildekort](./media/add-images-to-excel/select-card.png)
2. Klikk eller trykk på kortvelgeren for bildekortet i ruten til høyre, og deretter klikker eller trykker du på **Legg til notater**.
   
    ![Å legge til notater](./media/add-images-to-excel/add-notes.png)
3. Vis **BrowseScreen1** ved å klikke eller trykke på den i det venstre navigasjonsfeltet, og deretter åpner du forhåndsvisningsmodus.
4. Klikk eller trykk på pluss-ikonet øverst til høyre, legg til en bildetekst og tegn et bilde i **pennkontrollen**.
   
    ![Å tegne et bilde](./media/add-images-to-excel/draw-picture.png)
5. Klikk eller trykk på hakeikonet i øvre høyre hjørne for å lagre endringene.
   
    ![Å lagre endringer](./media/add-images-to-excel/checkmark-icon.png)
6. Legg til så mange bilder du ønsker, ved å gjenta de forrige to trinnene, og trykk deretter på Esc for å gå tilbake til standardarbeidsområdet.

