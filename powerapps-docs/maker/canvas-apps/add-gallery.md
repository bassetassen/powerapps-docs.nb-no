---
title: Vis en liste over elementer i en lerretsapp | Microsoft Docs
description: Bruk et galleri for å vise en liste over elementer i lerretsappen, og filtrer listen ved å angi et kriterium.
author: emcoope-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 09/28/2017
ms.author: emcoope
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 3df6227ed33c5154e1e5dd700e6a87c3e8305f01
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/07/2019
ms.locfileid: "71987581"
---
# <a name="show-a-list-of-items-in-powerapps"></a>Vis en liste over elementer i PowerApps

Vis en liste over elementer fra en datakilde ved å legge til en **[Galleri](controls/control-gallery.md)** -kontroll i lerretsappen. Dette emnet bruker Excel som datakilde. Filtrer listen ved å konfigurere **Galleri**-kontrollen, for å vise bare elementene som samsvarer med filterkriteriet i en **[Tekstinndata](controls/control-text-input.md)** -kontroll.

## <a name="prerequisites"></a>Forutsetninger

- Finn ut hvordan du [legger til og konfigurerer en kontroll](add-configure-controls.md) i PowerApps.

- Konfigurering av eksempeldataene:
    1. Last ned [denne Excel-filen](https://az787822.vo.msecnd.net/documentation/get-started-from-data/FlooringEstimates.xlsx), som inneholder eksempeldata for denne opplæringen.

    2. Last opp Excel-filen til en [skylagringstjeneste](connections/cloud-storage-blob-connections.md), for eksempel OneDrive for Business.

- Åpne en tom app:
    1. [Logg deg på PowerApps](http://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc).

    1. Under **Lag din egen app** velger du **Lerretsapp fra tom**.

    1. Angi et navn for appen, velg **Telefon**, og velg deretter **Opprett**.

    1. Hvis dialogboksen **Velkommen til PowerApps Studio** vises, klikker eller trykker du på **Hopp over**.

    1. [Legg til en tilkobling](add-data-connection.md) i **FlooringEstimates**-tabellen i Excel-filen.

## <a name="add-a-gallery-to-a-blank-screen"></a>Legg til et galleri på en tom skjerm

1. Velg **Galleri**på **Sett inn** -fanen, og velg deretter **Loddrett**.

    ![Legg til loddrett galleri](./media/add-gallery/gallery-dropdown.png)

1. Åpne **elementer** -listen på **Egenskaper** -fanen i ruten til høyre, og velg deretter **gulv beregning**.

    ![Gulv beregning](./media/add-gallery/select-layout.png)

1. valg fritt Velg et annet alternativ i listen **Oppsett** .

## <a name="add-a-gallery-in-a-screen"></a>Legg til et galleri på en skjerm

1. På **hjem** -fanen velger du **ny skjerm**@no__t**liste skjerm**.

    En skjerm som inneholder en **Galleri** -kontroll og andre kontroller, for eksempel et søke felt, vises.

1. Angi galleriets **Element**-egenskap til `FlooringEstimates`.

    **Galleri**-kontrollen viser eksempeldataene.

    ![Vis data](./media/add-gallery/show-data-default.png)

## <a name="add-a-control-to-the-gallery-control"></a>Legg til en kontroll i Galleri-kontrollen
Før du utfører andre tilpasninger, må du sørge for at oppsettet for **Galleri** kontrollen Sams varer best med det du ønsker. Derfra kan du endre **Galleri** malen ytterligere, som bestemmer hvordan alle dataene i **Galleri** kontrollen vises.

1. Velg malen ved å klikke eller trykke nær bunnen av **Galleri** -kontrollen, og deretter velge blyant ikonet i hjørnet øverst til venstre.

    ![Rediger galleri-mal](./media/add-gallery/edit-item.png)

2. Mens malen fortsatt er merket, kan du legge til en **[Etikett](controls/control-text-box.md)** -kontroll, og deretter flytte og endre størrelsen på den slik at den ikke overlapper med andre kontroller i malen.

    ![Å legge til en etikett](./media/add-gallery/add-text-box.png)

3. Velg galleriet, og velg deretter **Rediger** ved siden av **felt** på **Egenskaper** -fanen i ruten til høyre.

4. Velg etiketten som du har lagt til tidligere i denne prosedyren, og åpne deretter listen som er uthevet i **Data**-ruten.

    ![Åpne rullegardinliste](./media/add-gallery/open-dropdown.png)

5. Klikk eller trykk på **Pris** i denne listen.

    **Galleri**-kontrollen viser de nye verdiene.

    ![Det endelige galleriet](./media/add-gallery/final-gallery.png)

## <a name="filter-and-sort-a-gallery"></a>Filtrer og Sorter et galleri
**[Elementer](controls/properties-core.md)** -egenskapen for en **Galleri**-kontroll bestemmer hvilke elementer den viser. I denne prosedyren må du konfigurere denne egenskapen slik at den også bestemmer hvilke poster som vises basert på filter vilkår, og i hvilken rekkefølge.

![Søke boks-og sorterings ikon](./media/add-gallery/text-search-box.png)

1. Angi **[Elementer](controls/properties-core.md)** -egenskapen for **Galleri**-kontrollen til denne formelen:

    ```powerapps-dot
    Sort
        (If
            (IsBlank(TextSearchBox1.Text),
            FlooringEstimates,
            Filter(
                FlooringEstimates,
                TextSearchBox1.Text in Text(Name)
            )
        ),
        Name,
        If(
            SortDescending1,
            SortOrder.Descending,
            SortOrder.Ascending
        )
    )
    ```

    Hvis du vil ha mer informasjon om funksjonene i denne formelen, kan du se [formelreferansen](formula-reference.md).

1. Dobbelt klikk på søke boksen, og skriv deretter inn en del av eller hele produkt navnet.

    Bare elementer som oppfyller filter kriteriet, vises.

1. Når du trykker på Alt-tasten, velger du Sorter-ikonet én eller flere ganger for å bytte sorterings rekkefølge.

    Postene veksler mellom stigende og synkende alfabetisk rekkefølge basert på produkt navnet.

## <a name="highlight-the-selected-item"></a>Merk det valgte elementet
Angi **Galleri** -kontrollens **TemplateFill** -egenskap til en formel som ligner på dette eksemplet, men du kan angi forskjellige farger hvis du vil:

**If(ThisItem.IsSelected, LightCyan, White)**

## <a name="change-the-default-selection"></a>Endring av standardutvalget
Angi **Galleri**-kontrollens **Standard**-egenskap til posten du vil merke som standard. Du kan for eksempel angi det femte elementet i **FlooringEstimates** -data kilden:

**Last(FirstN(FlooringEstimates, 5))**

I dette eksemplet angir du det første elementet i **Hardwood**-kategorien for **FlooringEstimates**-datakilden:

**First(Filter(FlooringEstimates, Category = "Hardwood"))**

## <a name="next-steps"></a>Neste trinn
Finn ut hvordan du arbeider med [skjemaer](working-with-forms.md) og [formler](working-with-formulas.md).
