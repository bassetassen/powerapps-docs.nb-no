---
title: Tilpass et kort i en lerretsapp | Microsoft Docs
description: Endre standardkontrollen som vises i et kort i et detaljer eller redigere skjemaet i en lerretsapp
author: AFTOwen
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 03/18/2018
ms.author: anneta
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: ddc1c677ed95caf10d8cd6e0e7e12e6aaf88a0f5
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/23/2019
ms.locfileid: "61559866"
---
# <a name="customize-a-card-in-a-canvas-app"></a>Tilpass et kort i en lerretsapp

Utfør grunnleggende tilpasning (uten å låse opp et kort), for eksempel ved å endre kontrollen til kortet. Utfør avansert tilpasning ved å låse opp kortet og for eksempel legge til en kontroll som ikke er tilgjengelig for dette kortet som standard.

Hvis du vil ha en oversikt, kan du se [Forstå datakort](working-with-cards.md).

## <a name="prerequisites"></a>Forutsetninger

- Finn ut hvordan du [legger til og konfigurerer kontroller](add-configure-controls.md) i PowerApps.
- Du kan se gjennom dette emnet for bare generelle begreper, eller du kan følge det nøyaktig ved Hvis du først fullføre prosedyrene i disse emnene:

    1. [Generere en app](data-platform-create-app.md).
    1. [Tilpasse galleriet i appen](customize-layout-sharepoint.md).
    1. [Tilpasse skjemaene i appen](customize-forms-sharepoint.md).

## <a name="customize-a-locked-card"></a>Tilpass et låst kort

I denne prosedyren bytter du ut en **[innskriving av tekst](controls/control-text-input.md)** kontroll med en **[glidebryteren] (Kontroller/kontroll-slider.md** kontroll uten å låse opp kortet.

1. Appen du genererte og tilpasset, velg **EditForm1** i navigasjonsruten til venstre, og velg deretter **Rediger felt** på den **Egenskaper** fanen i ruten til høyre.

1. I listen over felt, velger du pil ned for **antall ansatte**, og åpne deretter listen under **kontroll av typen**.

    > [!div class="mx-imgBorder"]
    > ![Rullegardinliste over alternativer for et tallkort](./media/customize-card/card-selector.png)

1. Velg **Rediger glidebryter**.

    Skjermen gjenspeiler endringen.

    > [!div class="mx-imgBorder"]
    > ![EditForm1 med glidebryter](./media/customize-card/add-slider.png)

## <a name="unlock-and-customize-a-card"></a>Lås opp og tilpass et kort

I denne prosedyren må du låse opp et kort og oppdatere den **Maks** -egenskapen for den **glidebryteren** kontrollen du nettopp la til.

1. I **EditForm1**, og velg den **glidebryteren** kontroll i den **antall ansatte** kort.

    > [!div class="mx-imgBorder"]
    > ![Velg glidebryteren](./media/customize-card/select-slider.png)

1. På den **avansert** fanen i den høyre ruten, deretter på Lås-ikonet for å låse opp kortet.

    > [!div class="mx-imgBorder"]
    > ![Låse opp kortet](./media/customize-card/lock-icon.png)

1. Angi den **Maks** -egenskapen for den **glidebryteren** kontrollen til 10 000.

    > [!div class="mx-imgBorder"]
    > ![Maksimal egenskap på Avansert-fanen](./media/customize-card/max-property.png)

    Den **glidebryteren** kontrollen viser mer nøyaktige verdier.

    > [!div class="mx-imgBorder"]
    > ![Glidebryter område: 0-10,000](./media/customize-card/final-slider.png)

## <a name="next-steps"></a>Neste trinn

Nå som du har en grunnleggende forståelse av hvordan du genererer en app og tilpasser et galleri, et skjema og et kort, kan du [bygge din egen app fra grunnen av](data-platform-create-app-scratch.md).