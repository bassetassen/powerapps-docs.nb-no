---
title: Tilpass et kort | Microsoft Docs
description: Endre standardkontrollen som vises i et kort, i et Detaljer- eller Rediger-skjema i PowerApps
author: AFTOwen
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 03/18/2018
ms.author: anneta
ms.openlocfilehash: 56a46493ef15eff7d65d19f12affb2a58dbba0b6
ms.sourcegitcommit: dfa0e1a7981814e15e6ca4720e2a5f930e859db1
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 07/13/2018
ms.locfileid: "39023440"
---
# <a name="customize-a-card-in-powerapps"></a>Tilpass et kort i PowerApps
Utfør grunnleggende tilpasning (uten å låse opp et kort), for eksempel ved å endre kontrollen til kortet. Utfør avansert tilpasning ved å låse opp kortet og for eksempel legge til en kontroll som ikke er tilgjengelig for dette kortet som standard.

Hvis du vil ha en oversikt, kan du se [Forstå datakort](working-with-cards.md).

## <a name="prerequisites"></a>Forutsetninger

* Finn ut hvordan du [legger til og konfigurerer kontroller](add-configure-controls.md) i PowerApps.
* Du kan se gjennom dette emnet og få innblikk i generelle begreper, eller du kan følge det nøyaktig ved å fullføre prosedyrene i disse temaene:

  1. [Generere en app](data-platform-create-app.md).
  2. [Tilpasse galleriet i appen](customize-layout-sharepoint.md).
  3. [Tilpasse skjemaene i appen](customize-forms-sharepoint.md).

## <a name="customize-a-locked-card"></a>Tilpass et låst kort
I denne prosedyren bytter du ut en **[Tekstinndata](controls/control-text-input.md)**-kontroll med en **[Glidebryter](controls/control-slider.md)**-kontroll uten å låse opp kortet.

1. Logg deg på [PowerApps](http://web.powerapps.com).

    ![Hjemmesiden for PowerApps](./media/customize-card/sign-in.png)

1. Åpne appen som du genererte og tilpasset, velg **EditForm1**, og åpne deretter **Data**-ruten ved å velge **Kontoer** i ruten til høyre.

1. I listen over felt velger du Pil ned for å vise en liste over alternativer under **Antall ansatte**, og deretter velger du **Redigere glidebryter**.

    ![Rullegardinliste over alternativer for et tallkort](./media/customize-card/card-selector.png)

    Skjermbildet gjenspeiler endringen.

    ![EditForm1 med glidebryter](./media/customize-card/add-slider.png)

## <a name="unlock-and-customize-a-card"></a>Lås opp og tilpass et kort
I denne prosedyren må du låse opp et kort og deretter erstatte en **[Veksleknapp](controls/control-toggle.md)**-kontroll med en **[Avmerkingsboks](controls/control-check-box.md)**-kontroll.

1. Vis feltet **Send markedsføringsmateriell**i **EditForm1**.

    ![Vis feltet for Send markedsføringsmateriell](./media/customize-card/show-field.png)

2. Med dette kortet valgt klikker eller trykker du på **Avansert** nær toppen av den høyre ruten, og deretter klikker eller trykker du på Lås-ikonet for å låse opp kortet.

    ![Vis feltet for Send markedsføringsmateriell](./media/customize-card/unlock-card.png)

1. I kortet sletter du **Veksleknapp**-kontrollen, legger til en **Avmerkingsboks**-kontroll og gir den nye kontrollen navnet **chkMktg**.

    ![Erstatt veksleknapp med avmerkingsboks](./media/customize-card/add-checkbox.png)

1. Velg kortet som du nettopp har oppdatert.

    ![Velg kortet](./media/customize-card/select-card.png)

1. I ruten til høyre må du kontrollere at **Avansert**-fanen fremdeles vises, og deretter klikker eller trykker du på **Flere alternativer**.

    ![Flere alternativer-knappen](./media/customize-card/more-options.png)

1. Endre verdien av kortets **Oppdater**-egenskap til dette uttrykket:
<br>`chkMktg.Value`

1. Endre verdien av **Y**-egenskapen for feilmeldingen for dette kortet til dette uttrykket:<br>
`chkMktg.Y + chkMktg.Height`

    ![Velg feilmelding for det nye kortet](./media/customize-card/select-error.png)

1. Endre verdien for **Tekst**-egenskapen for **chkMktg** til **Ja**.

    Skjermbildet viser endringene, og feilene er løst.

    ![Siste skjermbilde med feilene løst](./media/customize-card/final-screen.png)

## <a name="next-steps"></a>Neste trinn
Nå som du har en grunnleggende forståelse av hvordan du genererer en app og tilpasser et galleri, et skjema og et kort, kan du [bygge din egen app fra grunnen av](data-platform-create-app-scratch.md).
