---
title: Tilpass et skjema i en lerretsapp | Microsoft Docs
description: Angi hvilke data som skal vises i et lerretsappskjema i PowerApps, hvilken rekkefølge de skal vises i, og i hvilke kontroller.
author: AFTOwen
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 03/17/2018
ms.author: anneta
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 1a6465a00f135489d594bad75b8a25942e05dd25
ms.sourcegitcommit: f4b71ea0996603b3358377a0da21b9e4428a287c
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/02/2019
ms.locfileid: "58870935"
---
# <a name="customize-a-canvas-app-form-in-powerapps"></a>Tilpass et lerretsappskjema i PowerApps

Tilpass en **Visningsskjema**-kontroll og en **Redigeringsskjema**-kontroll i en lerretsapp slik at de viser de viktigste dataene i den mest intuitive rekkefølgen, for å gjøre det enkelt for brukerne å forstå og oppdatere dataene.

Hvert skjema består av ett eller flere kort, som viser data fra en bestemt kolonne i datakilden. Ved å følge trinnene i dette emnet kan du angi hvilke kort som skal vises i et skjema og flytte kortene opp og ned innenfor et skjema.

Hvis du er kjent med lerret-pps, kan du se [Hva er lerret-apper?](getting-started.md).

## <a name="prerequisites"></a>Forutsetninger

[Å genere en app](data-platform-create-app.md) fra Common Data Service, og deretter [tilpasse galleriet](customize-layout-sharepoint.md) i denne appen.

## <a name="show-and-hide-cards"></a>Å vise og skjule kort

1. Logg deg på [PowerApps](http://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc), og åpne deretter appen du genererte og tilpasset.

1. I det venstre navigasjonsfeltet skriver eller limer inn **D** i søkefeltet for å filtrere listen over elementer, og velg deretter **DetailForm1**.

    > [!div class="mx-imgBorder"]
    > ![Slik velger du detaljskjermbilde](./media/customize-forms-sharepoint/select-detailform.png)

1. Velg **Rediger felt** på **Egenskaper**-fanen i den høyre ruten for å åpne **Felt**-ruten.

    > [!div class="mx-imgBorder"]
    > ![Åpne felt-ruten](./media/customize-forms-sharepoint/edit-fields.png)

1. Skjule et felt, slik som **beskrivelse**, ved å holde pekeren over den, å velge ellipsen (...) som vises, og deretter velge **fjerne**.

    > [!div class="mx-imgBorder"]
    > ![Liste over felt](./media/customize-forms-sharepoint/hide-fields.png)

1. Vise et felt ved å velge **Legg til felt**, å skrive eller lime inn de første bokstavene i feltnavnet i søkeboksen, hvis du merker for feltet, og deretter velge **Legg til**.

    > [!div class="mx-imgBorder"]
    > ![Liste over felt](./media/customize-forms-sharepoint/show-field.png)

## <a name="reorder-the-cards"></a>Å endre rekkefølgen på kortene

1. I den **felt** dra den **kontonavn** feltet til toppen av listen over felt.

    Kortene i **DetailForm1** gjenspeiler endringen.

    > [!div class="mx-imgBorder"]
    > ![Omorganiserte kort](./media/customize-forms-sharepoint/reordered-card.png)

1. (valgfritt) Endre rekkefølgen på de andre kortene i denne sekvensen:

    - Kontonavn
    - Antall ansatte
    - Årlig omsetning
    - Primære telefon
    - Adresse 1: Gateadresse 1
    - Adresse 1: Gate/vei 2
    - Adresse 1: Poststed
    - Adresse 1: Postnummer

1. I det venstre navigasjonsfeltet skriver eller limer inn **Ed** i søket, og velg deretter **EditForm1** å merke den.

1. Gjenta trinnene i fremgangsmåten ovenfor og i denne, slik at feltene i **EditForm1** samsvarer med dem i **DetailForm1**.

## <a name="run-the-app"></a>Å kjøre appen

1. I det venstre navigasjonsfeltet skriver eller limer inn **Br** i søket, og velg deretter **BrowseScreen1** å merke den.

1. Åpne forhåndsvisningsmodus ved å trykke på F5 (eller ved å velge **Forhåndsvisning**-ikonet nær hjørnet øverst til høyre).

    > [!div class="mx-imgBorder"]
    > ![Forhåndsvisningsikonet](./media/customize-forms-sharepoint/open-preview.png)

1. I hjørnet øverst til høyre velger du pluss-ikonet for å legge til en post i **EditScreen1**.

    > [!div class="mx-imgBorder"]
    > ![Å legge til post](./media/customize-forms-sharepoint/add-record.png)

1. Legg til dataene du ønsker, og velg deretter på hakeikonet øverst i høyre hjørne for å lagre endringene og gå tilbake til **BrowseScreen1**.

    > [!div class="mx-imgBorder"]
    > ![Å lagre poster](./media/customize-forms-sharepoint/save-record.png)

1. Velg pilen til elementet du nettopp opprettet for å vise detaljer om elementet i **DetailScreen1**.

    > [!div class="mx-imgBorder"]
    > ![Høyrepil](./media/customize-forms-sharepoint/right-arrow.png)

1. I hjørnet øverst til høyre velger du redigeringsikonet for å oppdatere posten i **EditScreen1**.

    > [!div class="mx-imgBorder"]
    > ![Å redigere poster](./media/customize-forms-sharepoint/edit-record.png)

1. Endre informasjonen i ett eller flere felt, og velg deretter haken øverst i høyre hjørne for å lagre endringene og gå tilbake til **DetailScreen1**.

    > [!div class="mx-imgBorder"]
    > ![Å lagre endringer](./media/customize-forms-sharepoint/save-record.png)

1. Nær hjørnet øverst til høyre velger du på Papirkurv ikonet til å slette posten som du nettopp har oppdatert, og gå tilbake til **BrowseScreen1**.

    > [!div class="mx-imgBorder"]
    > ![Å slette poster](./media/customize-forms-sharepoint/delete-record.png)

1. Lukk forhåndsvisningsmodus ved å trykke på Esc (eller ved å velge Lukk-ikonet nær hjørnet øverst til venstre).

## <a name="next-steps"></a>Neste trinn

- [Å lagre og publisere](save-publish-app.md) appen.
- [Å tilpasse et kort](customize-card.md) i appen.