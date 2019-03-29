---
title: Vise, redigere eller legge til en post i en lerretsapp | Microsoft Docs
description: Bruk et lerretsappskjema til å vise, redigere eller legge til en post fra en tabell i datakilden.
author: emcoope-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 10/06/2017
ms.author: emcoope
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: e94aa48ed3fba1b4591e196e3b81d3fb0f76666f
ms.sourcegitcommit: 5c098a62f66a2f33418967fdce9363bd529e0fc1
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/28/2019
ms.locfileid: "58581028"
---
# <a name="show-edit-or-add-a-record-in-a-canvas-app"></a>Vise, redigere eller legge til en post i en lerretsapp

I en lerretsapp, legge til og konfigurere en **[skjerm](controls/control-form-detail.md)** skjema-kontrollen til å vise alle feltene i en post, du kan også legge til og konfigurere en **[Rediger](controls/control-form-detail.md)** skjema-kontrollen til å redigere et felt i en post, legge til en post, og lagre endringene tilbake til en datakilde.

## <a name="prerequisites"></a>Forutsetninger

- Finn ut hvordan du [legger til og konfigurerer en kontroll](add-configure-controls.md) i PowerApps.
- Last ned [denne Excel-filen](https://az787822.vo.msecnd.net/documentation/get-started-from-data/FlooringEstimates.xlsx), som inneholder eksempeldata for denne opplæringen.
- Last opp Excel-filen til en [skylagringstjeneste](connections/cloud-storage-blob-connections.md), for eksempel OneDrive for Business.
- Opprette eller åpne en app for telefoner, [legge til en tilkobling](add-data-connection.md) til den **FlooringEstimates** tabellen i Excel-filen.

    Du kan legge til et skjema i en nettbrett-app, men den vil ikke samsvarer med dette emnet fordi skjemaet har tre kolonner som standard.

- Hvis du åpner en eksisterende app, [legge til en skjerm](add-screen-context-variables.md) til den.

## <a name="add-a-form-and-show-data"></a>Å legge til et skjema og vise data
1. På en tom skjerm, kan du legge til en **[rullegardin](controls/control-drop-down.md)** kontroll, og gi den navnet **ChooseProduct**.

    > [!NOTE]
   > Hvis du ikke er sikker på hvordan du legger til en kontroll, gir nytt navn til den eller angir en egenskap, kan du se [Å legge til og konfigurere kontroller](add-configure-controls.md).

1. På den **Egenskaper** fanen i den høyre ruten, angi **elementer** til `FlooringEstimates` og **verdien** til `Name`.

    ![Angi skjemaets elementegenskaper](./media/add-form/items-property.png)

    Listen viser navnene på gulvprodukter fra datakilden.

1. Legg til en **Rediger** skjema-kontroll, Flytt den under **ChooseProduct**, og endre deretter størrelsen på skjemaet så det dekker mesteparten av skjermen.

    ![Å legge til et skjema](./media/add-form/add-a-form.png)

    > [!NOTE]
   > Dette emnet beskriver den **Rediger** skjema-kontrollen, men lignende prinsipper gjelder den **skjerm** skjema-kontroll.

1. Angi skjemaets **[DataSource](controls/control-form-detail.md)** egenskapen til **FlooringEstimates** og **[element](controls/control-form-detail.md)** egenskapen til Denne formelen:

    `First(Filter(FlooringEstimates, Name=ChooseProduct.Selected.Value))`

   Denne formelen angir at posten brukeren velger i **ChooseProduct**, skal vises når du har konfigurert skjemaet ferdig.

1. På den **Egenskaper** fanen i den høyre ruten, velg **Rediger felt**.

    ![Rediger felt](./media/add-form/edit-fields.png)

1. I **Felter**-ruten velger du **Legg til felt**, merker av for hvert felt, og deretter velger du **Legg til**.

    ![Legge til felt](./media/add-form/add-fields.png)

1. Velg ellipsen (...) ved siden **Legg til felt**, og velg **Skjul alle**, og dra deretter **navnet** til toppen av listen.

    ![Flytt felt](./media/add-form/move-field.png)

    Den **Rediger** skjema-kontrollen gjenspeiler endringen.

    ![Vis skjema](./media/add-form/show-form1.png)

## <a name="set-the-card-type-for-a-field"></a>Å angi korttypen for et felt
1. I den **felt** ruten, utvid den **pris** feltet ved å velge pil ned.

1. Åpne den **kontroll av typen** listen, og velg deretter **Rediger glidebryter**.

    ![Rediger glidebryter](./media/add-form/edit-slider.png)

    I skjemaet, den **pris** feltet viser en **glidebryteren** kontroll i stedet for en **tekstinndata** kontroll.

1. (valgfritt) Følger den samme prosessen for å endre kontrollen for den **oversikt over** feltet til en **Rediger tekst på flere linjer** kontroll.

## <a name="edit-form-only-save-changes"></a>(Bare for redigeringsskjema) Lagre endringer

1. Gi nytt navn til skjemaet **EditForm**.

1. Legg til en **[Knapp](controls/control-button.md)**, og angi **[OnSelect](controls/properties-core.md)**-egenskapen til denne formelen:

   `SubmitForm(EditForm)`

1. Trykk F5 for å åpne forhåndsvisning, endre navnet på et produkt, og velg deretter knappen som du opprettet.

    Den **[SubmitForm](functions/function-form.md)** funksjonen lagrer endringene til datakilden.

1. (valgfritt) Lukk forhåndsvisning ved å trykke på Esc (eller ved å velge Lukk-ikonet i hjørnet øverst til høyre).

## <a name="next-steps"></a>Neste trinn
Finn ut mer om hvordan du arbeider med [skjemaer](working-with-forms.md) og [formler](working-with-formulas.md).
