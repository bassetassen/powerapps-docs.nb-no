---
title: Vis en liste over elementer i en lerretsapp | Microsoft Docs
description: Bruk et galleri for å vise en liste over elementer i lerretsappen, og filtrer listen ved å angi et kriterium.
author: emcoope-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 09/28/2017
ms.author: emcoope
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: f5daff973e3d6a90c6ca7748e0684a7a68c23226
ms.sourcegitcommit: 90245baddce9d92c3ce85b0537c1ac1cf26bf55a
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 01/26/2019
ms.locfileid: "57799023"
---
# <a name="show-a-list-of-items-in-powerapps"></a>Vis en liste over elementer i PowerApps

Vis en liste over elementer fra en datakilde ved å legge til en **[Galleri](controls/control-gallery.md)**-kontroll i lerretsappen. Dette emnet bruker Excel som datakilde. Filtrer listen ved å konfigurere **Galleri**-kontrollen, for å vise bare elementene som samsvarer med filterkriteriet i en **[Tekstinndata](controls/control-text-input.md)**-kontroll.

## <a name="prerequisites"></a>Forutsetninger

* Finn ut hvordan du [legger til og konfigurerer en kontroll](add-configure-controls.md) i PowerApps.

* Konfigurering av eksempeldataene:
    1. Last ned [denne Excel-filen](https://az787822.vo.msecnd.net/documentation/get-started-from-data/FlooringEstimates.xlsx), som inneholder eksempeldata for denne opplæringen.

    2. Last opp Excel-filen til en [skylagringstjeneste](connections/cloud-storage-blob-connections.md), for eksempel OneDrive for Business.

## <a name="add-a-gallery-control"></a>Legg til en Galleri-kontroll
1. Åpne PowerApps, og klikk eller trykk deretter på **Ny** nær venstre kant.

2. Klikk eller trykk på **Telefonoppsett** på **Tom app**-flisen.

3. I dialogboksen **Velkommen til PowerApps Studio** klikker eller trykker du på **Hopp over**.

4. [Legg til en tilkobling](add-data-connection.md) i **FlooringEstimates**-tabellen i Excel-filen.

5. (valgfritt) Legg til en **Galleri**-kontroll i standard-skjermbildet ved å klikke eller trykke på **Sett inn**-fanen, klikke eller trykke på **Galleri**, og deretter klikke eller trykke på en **Galleri**-kontroll som er uten innhold (tom), eller som inneholder et standardsett med kontroller.

    Disse alternativene inkluderer **Galleri**-kontrollene som ruller vannrett eller loddrett. Du kan også legge til en **Galleri**-kontroll som automatisk baserer størrelsen på mengden med innhold i hvert element.

    ![Legg til galleri](./media/add-gallery/gallery-dropdown.png)

6. Klikk eller trykk på **Nytt skjermbilde** på **Hjem**-fanen.

    Du kan legge til et skjermbilde som er tomt, et som ruller, som inneholder en **Galleri**-kontroll, eller som inneholder et skjema.

7. Klikk eller trykk på **Listeskjerm** for å legge til en skjerm som inneholder en **Galleri**-kontroll og andre kontroller, for eksempel et søkefelt.

    > [!NOTE]
   > Om du legger til en **Galleri**-kontroll i en ny eller eksisterende skjerm, kan du klikke eller trykke nær bunnen av **Galleri**-kontrollen for å merke den, klikke eller trykke på **Estimater for gulvlegging** i den høyre ruten, og klikke eller trykke på et annet oppsett i **Data**-ruten. La standardoppsettet være aktivert for denne opplæringen.

    ![Velg gallerioppsett](./media/add-gallery/select-layout.png)

8. Klikk eller trykk på **Galleri**-kontrollen i skjermbildet som du nettopp la til.

9. Klikk eller trykk på **CustomGallerySample** på **Egenskaper**-fanen i ruten til høyre.

10. Klikk eller trykk på **CustomGallerySample** og deretter på **FlooringEstimates** i **Data**-ruten.

    ![Velg datakilde](./media/add-gallery/choose-data.png)

    **Galleri**-kontrollen viser eksempeldataene.

    ![Vis data](./media/add-gallery/show-data-default.png)

    Du vil konfigurere sortering og søk senere i dette emnet.

## <a name="add-a-control-to-the-gallery-control"></a>Legg til en kontroll i Galleri-kontrollen
Før du gjør eventuelle tilpasninger, bestemmer du deg for et oppsett for **Galleri**-kontrollen. Det første settet med kontroller i en **Galleri**-kontroll er malen, som bestemmer hvordan alle dataene i **Galleri**-kontrollen vises.

1. Velg malen ved å klikke eller trykke nær bunnen av **Galleri**-kontrollen, og deretter klikker eller trykker du på blyantikonet øverst til venstre.

    ![Rediger galleri-mal](./media/add-gallery/edit-item.png)

2. Mens malen fortsatt er merket, kan du legge til en **[Etikett](controls/control-text-box.md)**-kontroll, og deretter flytte og endre størrelsen på den slik at den ikke overlapper med andre kontroller i malen.

    ![Legg til en etikett](./media/add-gallery/add-text-box.png)
3. Åpne **Data**-ruten ved å velge malen og deretter klikke eller trykke på **Estimater for gulvlegging** i ruten til høyre.

4. Velg etiketten som du har lagt til tidligere i denne prosedyren, og åpne deretter listen som er uthevet i **Data**-ruten.

    ![Åpne rullegardinliste](./media/add-gallery/open-dropdown.png)

5. Klikk eller trykk på **Pris** i denne listen.

    ![Endre bindingene for etikett](./media/add-gallery/change-binding.png)

    **Galleri**-kontrollen viser de nye verdiene.

    ![Det endelige galleriet](./media/add-gallery/final-gallery.png)

## <a name="filter-the-gallery-control"></a>Filtrer Galleri-kontrollen
**[Elementer](controls/properties-core.md)** -egenskapen for en **Galleri**-kontroll bestemmer hvilke elementer den viser. I denne prosedyren må du konfigurere denne egenskapen slik at **Galleri**-kontrollen viser kun elementer som inneholder navnet på produktet teksten i **TextSearchBox1**.

![Boks for tekstsøk](./media/add-gallery/text-search-box.png)

1. Velg **Galleri**-kontrollen ved å klikke eller trykke nær bunnen av denne kontrollen.

2. Angi **[Elementer](controls/properties-core.md)**-egenskapen for **Galleri**-kontrollen på **Avansert**-fanen til denne formelen:

    **If(IsBlank(TextSearchBox1.Text), FlooringEstimates, Filter(FlooringEstimates, TextSearchBox1.Text in Text(Name)))**

    Hvis du vil ha mer informasjon om funksjonene i denne formelen, kan du se [formelreferansen](formula-reference.md).

3. Skriv inn hele eller deler av et produktnavn i søkeboksen.

    **Galleri**-kontrollen viser bare elementer som oppfyller filterkriteriet.

## <a name="sort-the-gallery-control"></a>Sorter Galleri-kontrollen
**[Elementer](controls/properties-core.md)** -egenskapen for en **Galleri**-kontroll bestemmer rekkefølgen elementene vises i. I denne prosedyren må du konfigurere denne egenskapen slik at **Galleri**-kontrollen viser rekkefølgen av elementer, som angitt av **ImageSortUpDown1**.

![Bilde for sortering](./media/add-gallery/image-sorting.png)

1. Angi **[Elementer](controls/properties-core.md)**-egenskapen for **Galleri**-kontrollen til denne formelen:

    **Sort(If(IsBlank(TextSearchBox1.Text), FlooringEstimates, Filter(FlooringEstimates, TextSearchBox1.Text in Text(Name))), Name, If(SortDescending1, SortOrder.Descending, SortOrder.Ascending))**

2. Velg Sorter-ikonet for å endre sorteringsrekkefølgen for **Galleri**-kontrollen basert på navnene på produktene.

Hvis du vil sortere *og* filtrere **Galleri**-kontrollen:

* Erstatt begge forekomstene av *DataSource* i denne formelen med navnet på datakilden.

* Erstatt begge forekomstene av *ColumnName* med navnet på kolonnen du vil sortere og filtrere etter.

**Sort(If(IsBlank(TextSearchBox1.Text),** *DataSource*, **Filter(** *DataSource*, **TextSearchBox1.Text in Text(** *ColumnName* **))),** *ColumnName*, **If(SortDescending1, SortOrder.Descending, SortOrder.Ascending))**

## <a name="highlight-the-selected-item"></a>Merk det valgte elementet
Angi **Galleri**-kontrollens **TemplateFill**-egenskap til en formel som ligner på dette eksemplet:

**If(ThisItem.IsSelected, LightCyan, White)**

## <a name="change-the-default-selection"></a>Endring av standardutvalget
Angi **Galleri**-kontrollens **Standard**-egenskap til posten du vil merke som standard. Angi for eksempel at det femte elementet i datakilden **FlooringEstimates**:

**Last(FirstN(FlooringEstimates, 5))**

I dette eksemplet angir du det første elementet i **Hardwood**-kategorien for **FlooringEstimates**-datakilden:

**First(Filter(FlooringEstimates, Category = "Hardwood"))**

## <a name="next-steps"></a>Neste trinn
Finn ut hvordan du arbeider med [skjemaer](working-with-forms.md) og [formler](working-with-formulas.md).
