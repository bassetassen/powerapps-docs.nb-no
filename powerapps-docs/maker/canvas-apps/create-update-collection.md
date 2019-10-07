---
title: Opprette og oppdatere en samling i en lerret-app | Microsoft Docs
description: Opprett en samling i en lerret-app, Legg til elementer i samlingen, og Fjern én eller alle elementer fra den
author: tapanm-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 01/28/2019
ms.author: tapanm
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 375c4f19ed7715eed662c8456c539d5590c9f1ec
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/07/2019
ms.locfileid: "71993199"
---
# <a name="create-and-update-a-collection-in-a-canvas-app"></a>Opprette og oppdatere en samling i en lerret-app

Bruk en samling til å lagre data som brukere kan administrere i appen. En samling er en gruppe elementer som ligner, for eksempel produkter i en produkt liste. Hvis du vil ha mer informasjon om forskjellige typer variabler som samlinger: [Forstå variabler for lerretet](working-with-variables.md).

## <a name="prerequisites"></a>Forutsetninger

- [Registrer deg](../signup-for-powerapps.md) for PowerApps, og deretter [logger du deg på](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) ved å angi samme legitimasjon som du brukte til å registrere deg.
- Opprett en app eller åpne en eksisterende app i PowerApps.
- Finn ut hvordan du [konfigurerer en kontroll](add-configure-controls.md) i PowerApps.

## <a name="create-a-multicolumn-collection"></a>Å opprette en samling med én kolonne

1. Legg til en **tekst inn data** -kontroll i PowerApps Studio.

    ![Sett inn en tekst inn data-kontroll](./media/create-update-collection/add-textbox.png)

1. Gi nytt navn til kontrollen ved å velge ellipsen i den venstre navigasjons ruten, velge **gi nytt navn**, og deretter skrive inn **Varenavn**.

    ![Gi nytt navn til en kontroll](./media/create-update-collection/rename-textbox.png)

1. Legg til en **rulle gardin** -kontroll.

    ![Legg til rulle gardin liste](./media/create-update-collection/add-dropdown.png)

1. Gi nytt navn til **rulle** gardin kontroll **fargene**, og kontroller at **element** -egenskapen er valgt i egenskaps listen.

    ![Elementer-egenskaper](./media/create-update-collection/items-property.png)

1. Erstatt **DropDownSample** med dette uttrykket i formel linjen:

    `["Red","Green","Blue"]`

1. Legg til en **knapp** -kontroll, angi **tekst** -egenskapen til **Legg**til, og angi **OnSelect** -egenskapen til denne formelen:

    ```powerapps-dot
    Collect(
        ProductList,
        {
            Product: ProductName.Text,
            Color: Colors.Selected.Value
        }
    )
    ```

1. Trykk på F5, Skriv inn tekst i **produkt navn**, Velg et alternativ i **farger**, og velg deretter **Legg til**.

    ![Forhånds visning av appen](./media/create-update-collection/preview-add.png)

1. Gjenta det forrige trinnet minst to ganger, og trykk deretter på ESC.

1. Velg **samlinger** på **fil** -menyen for å vise samlingen du opprettet.

    ![Vis samling](./media/create-update-collection/show-collection.png)

## <a name="show-a-collection"></a>Vis en samling

1. Legg til en loddrett **Galleri** -kontroll.

    ![Å legge til et loddrett galleri](./media/create-update-collection/add-gallery.png)

1. Angi **element** -egenskapen for galleriet til **ProductList**.

1. I **data** -ruten angir du under Tittel feltet til **farge**, og deretter angir du Tittel-feltet til **produkt**.

    ![Angi element-egenskapen for galleriet, og endre feltene som vises](./media/create-update-collection/configure-gallery.png)

1. Lukk **data** -ruten, Velg galleriet, og angi deretter **Oppsett** -feltet til **Tittel og under tittel**.

    ![Angi element-egenskapen for galleriet, og endre feltene som vises](./media/create-update-collection/change-layout.png)

    Skjermen likner dette eksemplet:

    ![Eksempel på første skjerm](./media/create-update-collection/screen-example1.png)

## <a name="remove-one-or-all-items"></a>Fjern ett eller alle elementer

1. Velg Galleri malen ved å klikke eller trykke nær bunnen av galleriet, og deretter klikke eller trykke på blyant ikonet nær hjørnet øverst til venstre.

    ![Velg Galleri mal](./media/create-update-collection/select-template.png)

1. Legg til et **papir kurv** ikon i Galleri malen.

    ![Legg til kurve-ikon](./media/create-update-collection/trash-icon.png)

1. Angi **OnSelect** -egenskapen for ikonet til denne formelen:

    `Remove(ProductList, ThisItem)`

1. Utenfor galleriet, Legg til en knapp, angi **tekst** -egenskapen til **«Fjern»** , og angi **OnSelect** -egenskapen til denne formelen:

    `Clear(ProductList)`

1. Velg **papir kurv** ikonet for et element når du holder nede Alt-tasten for å fjerne elementet fra samlingen, eller velg **Slett** -knappen for å fjerne alle elementer fra samlingen.

## <a name="put-a-sharepoint-list-into-a-collection"></a>Legge til en SharePoint-liste i en samling

1. [Opprett en tilkobling til en SharePoint-liste](connections/connection-sharepoint-online.md#create-a-connection).

1. Legg til en knapp, og angi **[OnSelect](controls/properties-core.md)** -egenskapen til denne funksjonen, noe som erstatter *ListName* med navnet på SharePoint-listen:<br>

    `Collect(MySPCollection, ListName)`

    Denne funksjonen oppretter en samling som heter **MySPCollection**, og som inneholder de samme dataene som SharePoint-listen.

1. Velg knappen mens du holder nede ALT.

1. valg fritt Hvis du vil forhånds vise samlingen du opprettet, velger du **samlinger** på **fil** -menyen.

Hvis du vil ha informasjon om hvordan du viser data fra en SharePoint-liste (for eksempel datoer, valg og personer) i et galleri: [Vis liste Kol onner i et galleri](connections/connection-sharepoint-online.md#show-list-columns-in-a-gallery). Hvis du vil ha informasjon om hvordan du viser data i et skjema (med rulle gardin lister, dato velgere og person velgere): [Rediger skjema-og visnings skjema kontroller](controls/control-form-detail.md).

## <a name="next-steps"></a>Neste trinn

- Se gjennom [Referanse emnet](functions/function-clear-collect-clearcollect.md) for **Collect** -funksjonen.
- Lær hvordan du kan forme data i en samling ved hjelp av funksjonene [AddColumns, DropColumns, RenameColumns og ShowColumns](functions/function-table-shaping.md) .
