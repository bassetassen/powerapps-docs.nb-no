---
title: Å vise elementer med ulike høyder i et galleri | Microsoft Docs
description: Legg til og konfigurer et galleri med fleksibel høyde for å automatisk tilpasse til mengden med innhold i hvert element for galleriet
author: fikaradz
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 04/01/2017
ms.author: fikaradz
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: b724bff09e02a3f69166b3c3357833804c8172b6
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/23/2019
ms.locfileid: "61554789"
---
# <a name="show-items-of-different-heights-in-a-powerapps-gallery"></a>Å vise elementer med ulike høyder i et galleri for PowerApps
Hvis forskjellige elementer i datasettet inneholder forskjellige mengder med data i samme felt, kan du vise elementer som inneholder flere data i sin helhet, uten å legge til en tom plass etter elementer som inneholder færre data. Legg til og konfigurer en gallerikontroll for **fleksibel høyde**, slik at du kan:

* Konfigurere **Etikett**-kontroller til å utvide eller krympe basert på innholdet.
* Plassere hver kontroll, slik at den automatisk vises bare under kontrollen over den.

I denne opplæringen viser du data om gulvleggingsprodukter i en gallerikontroll for **Fleksibel høyde**. Bildet av hvert produkt vises fem piksler under en oversikt, uavhengig om oversikten inneholder fem eller to linjer med tekst.

![Endelig app](./media/gallery-dynamic-sizing/dynamic-app.png)

**Foreslått lesing**

Hvis du aldri har lagt til kontroller i et galleri, følger du fremgangsmåten i [Vis en liste over elementer](add-gallery.md) før du fortsetter i dette emnet.

## <a name="add-data-to-a-blank-app"></a>Å legge til data i en tom app
1. Last ned [denne Excel-filen](https://az787822.vo.msecnd.net/documentation/get-started-from-data/FlooringEstimates.xlsx), som inneholder navn, oversikter og koblinger til bilder av gulvleggingsprodukter.

    ![Gulvleggingsprodukter](./media/gallery-dynamic-sizing/flooring-products.png)

2. Last opp Excel-filen til en skylagringskonto, for eksempel OneDrive, Dropbox eller Google Drive.

3. Klikk eller trykk på **Ny** på **Fil**-menyen i PowerApps Studio.

4. Klikk eller trykk på **Telefonoppsett** på **Tom app**-flisen.

    ![Nytt alternativ på Fil-menyen](./media/gallery-dynamic-sizing/blank-app.png)

5. Legg til en kobling til **FlooringEstimates**-tabellen i Excel-filen.

    Hvis du vil ha mer informasjon, kan du se [Å legge til en kobling](add-data-connection.md).

## <a name="add-data-to-a-gallery"></a>Å legge til data i et galleri
1. Klikk eller trykk på **Galleri** på **Sett inn**-fanen, og klikk eller trykk på **Fleksibel høyde**.

    ![Å legge til et galleri](./media/gallery-dynamic-sizing/add-flexible.png)
2. Endre størrelsen på galleriet for å fylle hele skjermen.

3. Angi galleriets **[Elementer](controls/properties-core.md)** -egenskap til **FlooringEstimates**.

## <a name="show-the-product-names"></a>Vis produktnavnene
1. Klikk eller trykk på blyantikonet for å velge gallerimalen i øvre venstre hjørne i galleriet.

    ![Blyantikon](./media/gallery-dynamic-sizing/edit-template.png)

2. Hvis du velger gallerimalen, kan du legge til en **[Etikett](controls/control-text-box.md)** -kontroll til den.

3. Angi **Text**-egenskapen for **Etikett**-kontrollen til dette uttrykket:<br>
   **ThisItem.Name**

    ![Legg til en etikett](./media/gallery-dynamic-sizing/add-text-box.png)

## <a name="show-the-product-overviews"></a>Vis produktoversiktene
1. Merk gallerimalen, legg til en annen **Etikett**-kontroll, og flytt den under den første **etikett**-kontrollen.  

2. Angi **Text**-egenskapen for den andre **Etikett**-kontrollen til dette uttrykket:<br> **ThisItem.Overview**

3. Når den andre **Etikett**-kontrollen er merket, kan du klikke eller trykke på navneskilt-ikonet på **Innhold**-fanen, og gi nytt navn til kontrollen til **OverviewText**.

    ![Gi nytt navn til etikett](./media/gallery-dynamic-sizing/rename-text-box.png)

4. Angi **AutoHeight**-egenskapen for **OverviewText**-boksen til **sann**.

    Dette trinnet sikrer at boksen vokser eller krymper for å passe til innholdet.

      ![Automatisk høyde på tekst](./media/gallery-dynamic-sizing/autoheight-text.png)

## <a name="show-the-product-images"></a>Vis produktbildene
1. Endre størrelsen på malen, slik at den blir to ganger så høy som den var.

    Du kan legge til kontroller til malen på en enklere måte når du bygger appen, og denne endringen påvirker ikke hvordan appen ser ut når den kjøres.

2. Merk gallerimalen, legg til en **[Bilde](controls/control-image.md)** -kontroll, og flytt den under **OverviewText**-boksen.

3. Forsikre deg om at **Image**-egenskapen for **Bilde**-kontrollen er satt til dette uttrykket:<br>
    **ThisItem.Image**

4. Angi **[Y](controls/properties-core.md)** -egenskapen for **Bilde**-kontrollen basert på plasseringen og størrelsen på **OverviewText**-boksen, som i dette uttrykket:
   <br>**OverviewText.Y + OverviewText.Height + 5**

    ![Endelig app](./media/gallery-dynamic-sizing/final-app.png)

Bruk det samme begrepet hvis du vil legge til flere kontroller: Angi **Y**-egenskapen for hver kontroll basert på egenskapene **Y** og **Height** for kontrollen over den.

## <a name="next-steps"></a>Neste trinn
Finn ut mer om hvordan du arbeider med en [galleri](working-with-forms.md)-kontroll og [formler](working-with-formulas.md).
