---
title: Opprett og oppdater en samling i en lerretsapp | Microsoft Docs
description: Opprette en samling i en lerretsapp, legge til elementer i samlingen, og Fjern ett eller alle elementer fra den
author: aftowen
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 01/28/2019
ms.author: anneta
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 6089063e2478c95bb5bfbc5926608d85552cea40
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/23/2019
ms.locfileid: "61561731"
ms.PowerAppsDecimalTransform: true
---
# <a name="create-and-update-a-collection-in-a-canvas-app"></a>Opprett og oppdater en samling i en lerretsapp

Bruk en samling til å lagre data som brukere kan administrere i appen. En samling er en gruppe elementer som ligner, for eksempel produkter i en liste over produkter. Hvis du vil ha mer informasjon om ulike typer variabler som for eksempel samlinger: [Forstå lerretsapp variabler](working-with-variables.md).

## <a name="prerequisites"></a>Forutsetninger

- [Registrer deg](../signup-for-powerapps.md) for PowerApps, og deretter [logger du deg på](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) ved å angi samme legitimasjon som du brukte til å registrere deg.
- Opprett en app eller åpne en eksisterende app i PowerApps.
- Finn ut hvordan du [konfigurerer en kontroll](add-configure-controls.md) i PowerApps.

## <a name="create-a-multicolumn-collection"></a>Opprette en samling med flere kolonner

1. I PowerApps Studio, legge til en **tekstinndata** kontroll.

    ![Sett inn en tekstinndata-kontroll](./media/create-update-collection/add-textbox.png)

1. Gi nytt navn til kontrollen ved å velge ellipsen i den venstre navigasjonsruten, å velge **gi nytt navn til**, og deretter skrive inn **ProductName**.

    ![Gi nytt navn til en kontroll](./media/create-update-collection/rename-textbox.png)

1. Legg til en **rullegardin** kontroll.

    ![Legg til rullegardinlisten](./media/create-update-collection/add-dropdown.png)

1. Gi nytt navn til den **rullegardin** kontrollen **farger**, og forsikre deg om at den **elementer** egenskap er merket i egenskapslisten.

    ![Elementer-egenskaper](./media/create-update-collection/items-property.png)

1. I formellinjen erstatter **DropDownSample** med dette uttrykket:

    `["Red";"Green";"Blue"]`

1. Legg til en **knappen** kontroll, angi dens **tekst** egenskapen til **«Legg til»**, og angi dens **OnSelect** egenskapen til denne formelen:

    ```powerapps-comma
    Collect(
        ProductList;
        {
            Product: ProductName.Text;
            Color: Colors.Selected.Value
        }
    )
    ```

1. Trykk på F5, Skriv inn tekst i **ProductName**, velg et alternativ i **farger**, og velg deretter **Legg til**.

    ![Forhåndsvisning av appen](./media/create-update-collection/preview-add.png)

1. Gjenta det forrige trinnet minst to ganger, og trykk deretter på Esc.

1. På den **filen** menyen velger **samlinger** til å vise samlingen som du har opprettet.

    ![Vise samling](./media/create-update-collection/show-collection.png)

## <a name="show-a-collection"></a>Vis en samling

1. Legg til en loddrett **galleriet** kontroll.

    ![Å legge til et loddrett galleri](./media/create-update-collection/add-gallery.png)

1. Angi galleriets **elementer** egenskapen til **ProductList**.

1. I den **Data** ruten, setter du undertittel-feltet til **farge**, og angi tittel-feltet til **produktet**.

    ![Angi galleriets elementer-egenskapen, og endre feltene som den viser](./media/create-update-collection/configure-gallery.png)

1. Lukk den **Data** ruten, Velg galleriet, og angi deretter det **oppsett** feltet til **tittel og undertittel**.

    ![Angi galleriets elementer-egenskapen, og endre feltene som den viser](./media/create-update-collection/change-layout.png)

    Skjermen ligner dette eksemplet:

    ![Skjermen det første eksemplet](./media/create-update-collection/screen-example1.png)

## <a name="remove-one-or-all-items"></a>Fjern ett eller alle elementer

1. Velg gallerimalen ved å klikke eller trykke nær bunnen av galleriet og deretter klikke eller trykke på blyantikonet nær hjørnet øverst til venstre.

    ![Velg gallerimal](./media/create-update-collection/select-template.png)

1. Legg til en **Papirkurv** ikon i malgalleriet.

    ![Legg til Papirkurv-ikon](./media/create-update-collection/trash-icon.png)

1. Angi ikonets **OnSelect** egenskapen til denne formelen:

    `Remove(ProductList; ThisItem)`

1. Utenfor galleriet, Legg til en knapp, angi dens **tekst** egenskapen til **«Tøm»**, og angi dens **OnSelect** egenskapen til denne formelen:

    `Clear(ProductList)`

1. Mens du holder nede Alt-tasten, velg den **Papirkurv** ikonet for et element for å fjerne elementet fra samlingen, eller velg de **tydelig** for å fjerne alle elementer fra samlingen.

## <a name="put-a-sharepoint-list-into-a-collection"></a>Legge til en SharePoint-liste i en samling

1. [Opprett en tilkobling til en SharePoint-liste](connections/connection-sharepoint-online.md#create-a-connection).

1. Legg til en knapp, og angi **[OnSelect](controls/properties-core.md)**-egenskapen til denne funksjonen, noe som erstatter *ListName* med navnet på SharePoint-listen:<br>

    `Collect(MySPCollection; ListName)`

    Denne funksjonen oppretter en samling som heter **MySPCollection**, og som inneholder de samme dataene som SharePoint-listen.

1. Velg knappen mens du holder nede ALT.

1. (valgfritt) Hvis du vil forhåndsvise samlingen som du opprettet, kan du velge **samlinger** på den **filen** menyen.

Informasjon om hvordan du viser data fra en SharePoint-liste (for eksempel datoer, valg og personer) i et galleri: [Vis listen over kolonner i et galleri](connections/connection-sharepoint-online.md#show-list-columns-in-a-gallery). Informasjon om hvordan du viser data i et skjema (med rullegardinlister, datovelgere og personer plukkere): [Rediger visning kontroller for redigeringsskjema og](controls/control-form-detail.md).

## <a name="next-steps"></a>Neste trinn

- Se gjennom den [emnet referanse](functions/function-clear-collect-clearcollect.md) for den **samle inn** funksjonen.
- Finn ut hvordan du former dataene i en samling ved hjelp av den [AddColumns, DropColumns, RenameColumns og ShowColumns](functions/function-table-shaping.md) funksjoner.
