---
title: Vis, Rediger eller Legg til en post i en lerret-app | Microsoft Docs
description: Bruk et lerretsappskjema til å vise, redigere eller legge til en post fra en tabell i datakilden.
author: emcoope-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 10/06/2017
ms.author: emcoope
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: ed7493dcc9c2ef5f0b84052a11dbadb0947af38e
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/07/2019
ms.locfileid: "71994122"
ms.PowerAppsDecimalTransform: true
---
# <a name="show-edit-or-add-a-record-in-a-canvas-app"></a>Vise, redigere eller legge til en post i en lerret-app

Legg til og Konfigurer en **[visnings](controls/control-form-detail.md)** skjema-kontroll i en lerret-app for å vise alle feltene i en post, du kan også legge til og konfigurere en **[redigerings](controls/control-form-detail.md)** skjema-kontroll for å redigere et felt i en post, legge til en post og lagre endringene i en data kilde.

## <a name="prerequisites"></a>Forutsetninger

- Finn ut hvordan du [legger til og konfigurerer en kontroll](add-configure-controls.md) i PowerApps.
- Last ned [denne Excel-filen](https://az787822.vo.msecnd.net/documentation/get-started-from-data/FlooringEstimates.xlsx), som inneholder eksempeldata for denne opplæringen.
- Last opp Excel-filen til en [skylagringstjeneste](connections/cloud-storage-blob-connections.md), for eksempel OneDrive for Business.
- Opprett eller åpne en app for telefoner, og [Legg til en tilkobling](add-data-connection.md) i **FlooringEstimates** -tabellen i Excel-filen.

    Du kan legge til et skjema i en tavle-app, men det Sams varer ikke med dette emnet, fordi skjemaet har tre kolonner som standard.

- Hvis du åpner en eksisterende app, kan du [legge til en skjerm](add-screen-context-variables.md) i den.

## <a name="add-a-form-and-show-data"></a>Å legge til et skjema og vise data
1. Legg til en **[rulle gardin](controls/control-drop-down.md)** -kontroll på en tom skjerm, og gi den navnet **ChooseProduct**.

    > [!NOTE]
   > Hvis du ikke er sikker på hvordan du legger til en kontroll, gir nytt navn til den eller angir en egenskap, kan du se [Å legge til og konfigurere kontroller](add-configure-controls.md).

1. På **Egenskaper** -fanen i ruten til høyre angir du **elementer** til `FlooringEstimates` og **verdi** til `Name`.

    ![Angi skjemaets element-egenskap](./media/add-form/items-property.png)

    Listen viser navnene på gulvprodukter fra datakilden.

1. Legg til en **redigerings** skjema-kontroll, Flytt den under **ChooseProduct**, og endre størrelsen på skjemaet slik at det dekker meste parten av skjermen.

    ![Å legge til et skjema](./media/add-form/add-a-form.png)

    > [!NOTE]
   > Dette emnet beskriver **redigerings** skjema-kontrollen, men lignende prinsipper gjelder for **visnings** skjema-kontrollen.

1. Angi skjemaets **[DataSource](controls/control-form-detail.md)** -egenskap til **FlooringEstimates** og **[element](controls/control-form-detail.md)** -egenskapen til denne formelen:

    `First(Filter(FlooringEstimates; Name=ChooseProduct.Selected.Value))`

   Denne formelen angir at posten brukeren velger i **ChooseProduct**, skal vises når du har konfigurert skjemaet ferdig.

1. Velg **Rediger felt**på **Egenskaper** -fanen i ruten til høyre.

    ![Rediger felt](./media/add-form/edit-fields.png)

1. I **Felter**-ruten velger du **Legg til felt**, merker av for hvert felt, og deretter velger du **Legg til**.

    ![Legg til felt](./media/add-form/add-fields.png)

1. Velg ellipsen (...) ved siden av **Legg til felt**, velg **Skjul alle**, og dra deretter **navnet** til toppen av listen.

    ![Flytt felt](./media/add-form/move-field.png)

    **Redigerings** skjema-kontrollen gjenspeiler endringen.

    ![Vis skjema](./media/add-form/show-form1.png)

## <a name="set-the-card-type-for-a-field"></a>Å angi korttypen for et felt
1. Utvid **pris** -feltet i **felt** -ruten ved å velge pil ned.

1. Åpne **kontroll type** -listen, og velg deretter **Rediger glidebryter**.

    ![Rediger glidebryter](./media/add-form/edit-slider.png)

    I skjemaet viser **pris** -feltet en **Glidebryter** i stedet for en **tekst inn data** -kontroll.

1. valg fritt Følg den samme prosessen for å endre kontrollen for **Oversikt** -feltet til en **Rediger tekst** -kontroll for flere linjer.

## <a name="edit-form-only-save-changes"></a>(Bare for redigeringsskjema) Lagre endringer

1. Gi nytt navn til skjemaet **EditForm**.

1. Legg til en **[Knapp](controls/control-button.md)** , og angi **[OnSelect](controls/properties-core.md)** -egenskapen til denne formelen:

   `SubmitForm(EditForm)`

1. Trykk på F5 for å åpne forhånds visning, endre navnet på et produkt, og velg deretter knappen du opprettet.

    **[SubmitForm](functions/function-form.md)** -funksjonen lagrer endringene i data kilden.

1. valg fritt Lukk forhånds visning ved å trykke på ESC (eller ved å velge Lukk-ikonet i hjørnet øverst til høyre).

## <a name="next-steps"></a>Neste trinn
Finn ut mer om hvordan du arbeider med [skjemaer](working-with-forms.md) og [formler](working-with-formulas.md).
