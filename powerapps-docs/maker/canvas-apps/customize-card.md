---
title: Tilpass et kort i en lerret-app | Microsoft Docs
description: Endre standard kontrollen som vises i et kort på en detaljer-eller redigerings skjema i en lerret-app
author: tapanm-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 03/18/2018
ms.author: tapanm
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 5bcf1515f72bdce0872f91c64b5ac4fe5028ee2c
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/07/2019
ms.locfileid: "71985911"
---
# <a name="customize-a-card-in-a-canvas-app"></a>Tilpasse et kort i en lerret-app

Utfør grunnleggende tilpasning (uten å låse opp et kort), for eksempel ved å endre kontrollen til kortet. Utfør avansert tilpasning ved å låse opp kortet og for eksempel legge til en kontroll som ikke er tilgjengelig for dette kortet som standard.

Hvis du vil ha en oversikt, kan du se [Forstå datakort](working-with-cards.md).

## <a name="prerequisites"></a>Forutsetninger

- Finn ut hvordan du [legger til og konfigurerer kontroller](add-configure-controls.md) i PowerApps.
- Du kan gå gjennom dette emnet bare for generelle begreper, eller du kan følge det trinn for trinn hvis du først full fører prosedyrene i disse emnene:

    1. [Generere en app](data-platform-create-app.md).
    1. [Tilpasse galleriet i appen](customize-layout-sharepoint.md).
    1. [Tilpasse skjemaene i appen](customize-forms-sharepoint.md).

## <a name="customize-a-locked-card"></a>Tilpass et låst kort

I denne prosedyren skal du erstatte en **[tekst inn data-](controls/control-text-input.md)** kontroll med **[glidebryter] (kontroller/kontroll-Glide bryte ren. MD-** kontroll uten å låse opp kortet.

1. Velg **EditForm1** i det venstre navigasjons feltet i appen som du genererte og tilpasset, og velg deretter **Rediger felt** på **Egenskaper** -fanen i ruten til høyre.

1. Velg pil ned for **antall ansatte**i listen over felt, og åpne deretter listen under **kontroll type**.

    > [!div class="mx-imgBorder"]
    > @no__t – 0Drop liste over alternativer for et nummer kort @ no__t-1

1. Velg **Rediger glidebryter**.

    Skjermen gjenspeiler endringen.

    > [!div class="mx-imgBorder"]
    > ![EditForm1 med Glide bryte ren @ no__t-1

## <a name="unlock-and-customize-a-card"></a>Lås opp og tilpass et kort

I denne prosedyren kan du låse opp et kort og oppdatere **Max** -egenskapen til **Glide** kontrollen du nettopp la til.

1. Velg **Glide** kontrollen i **antall ansatt** -kortet i **EditForm1**.

    > [!div class="mx-imgBorder"]
    > @no__t – 0Select Glide bryte ren @ no__t-1

1. Velg lås-ikonet i **Avansert** -fanen i ruten til høyre for å låse opp kortet.

    > [!div class="mx-imgBorder"]
    > ![Unlock Card @ no__t-1

1. Angi **maksimal** egenskap for **glide** kontrollen til 10 000.

    > [!div class="mx-imgBorder"]
    > ![Max-egenskap i avansert-fanen @ no__t-1

    **Glide** kontrollen viser en mer nøyaktig verdi.

    > [!div class="mx-imgBorder"]
    > 0Slider-område: @no__t 0 – 10000 @ no__t-0

## <a name="next-steps"></a>Neste trinn

Nå som du har en grunnleggende forståelse av hvordan du genererer en app og tilpasser et galleri, et skjema og et kort, kan du [bygge din egen app fra grunnen av](data-platform-create-app-scratch.md).