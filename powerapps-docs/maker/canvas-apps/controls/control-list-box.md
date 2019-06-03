---
title: 'Liste-kontrollen: referanse | Microsoft Docs'
description: Informasjon om Liste-kontrollen, inkludert egenskaper og eksempler
author: fikaradz
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 10/25/2016
ms.author: fikaradz
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: a7128ace53cc1e0754eb7247282b2ecae7642672
ms.sourcegitcommit: 8d0ba2ec0c97be91d1350180dd6881c14dec8f2d
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 05/10/2019
ms.locfileid: "65517413"
---
# <a name="list-box-control-in-powerapps"></a>Liste-kontrollen i PowerApps
En liste der brukeren kan velge ett eller flere elementer.

## <a name="description"></a>Beskrivelse
**Liste**-kontrollen viser alltid alle de tilgjengelige valgene (i motsetning til en **[Rullegardin](control-drop-down.md)** -kontroll), og brukeren kan velge mer enn ett element om gangen (i motsetning til en **[Radio](control-radio.md)** -kontroll).

## <a name="key-properties"></a>Nøkkelegenskaper
**[Standard](properties-core.md)** – startverdien for en kontroll før den er endret av brukeren.

**[Elementer](properties-core.md)** – kilden til dataene som vises i en kontroll, for eksempel et galleri, en liste eller et diagram.

**Valgte** – dataposten som representerer det valgte elementet.

Når du legger til et galleri, eller en liste, viser egenskapslisten **Elementer** som standard. På denne måten kan du enkelt angi dataene som den nye kontrollen skal vise. Du kan for eksempel angi **Elementer**-egenskapen for et galleri til **Konto**-tabellen i Salesforce, en tabell med navn **Beholdning** som du opprettet i Excel og lastet opp i skyen, eller en SharePoint-liste med navn **ConferenceSpeakers**.

## <a name="additional-properties"></a>Tilleggsegenskaper
**[AccessibleLabel](properties-accessibility.md)** – etikett for skjermlesere.

**[BorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje.

**[BorderStyle](properties-color-border.md)** – om kontrollens kantlinje er satt til **Heltrukket**, **Stiplet**, **Prikket** eller **Ingen**.

**[BorderThickness](properties-color-border.md)** – tykkelsen til kontrollens kantlinje.

**[Farge](properties-color-border.md)** – fargen på teksten i kontrollen.

**[DisplayMode](properties-core.md)** – om kontrollen tillater brukerinndata (**Rediger**), bare viser data (**Vis**) eller er deaktivert (**Deaktivert**).

**[DisabledBorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje hvis kontrollens **[DisplayMode](properties-core.md)** -egenskap er angitt til **Deaktivert**.

**[DisabledColor](properties-color-border.md)** – fargen på kontrollens tekst hvis kontrollens **[DisplayMode](properties-core.md)** -egenskap er angitt som **Deaktivert**.

**[DisabledFill](properties-color-border.md)** – bakgrunnsfargen på en kontroll hvis **[DisplayMode](properties-core.md)** -egenskapen er angitt som **Deaktivert**.

**[Fyll](properties-color-border.md)** – bakgrunnsfargen på kontrollen.

**[FocusedBorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje når kontrollen er fokusert.

**[FocusedBorderThickness](properties-color-border.md)** – fargen på kontrollens kantlinje når kontrollen er fokusert.

**[Skrift](properties-text.md)** – navnet på skriftserien som teksten vises i.

**[FontWeight](properties-text.md)**  – vekten på teksten i en kontroll: **Fet**, **Halvfet**, **Normal**, eller **lysere**.

**[Høyde](properties-size-location.md)** – avstanden mellom kontrollens øvre og nedre kant.

**[HoverBorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje når brukeren holder musepekeren på denne kontrollen.

**[HoverColor](properties-color-border.md)** – Fargen på teksten i en kontroll når brukeren holder musepekeren over den.

**[HoverFill](properties-color-border.md)** – bakgrunnsfargen for en kontroll når brukeren holder musepekeren over den.

**[Kursiv](properties-text.md)** – om teksten i en kontroll er i kursiv.

**ItemPaddingLeft** – avstanden mellom teksten i en liste og venstre kant.

**[LineHeight](properties-text.md)** – avstanden mellom linjer med tekst, elementer i en liste eller lignende.

**[OnChange](properties-core.md)** – hvordan appen reagerer når brukeren endrer verdien på en kontroll (ved å for eksempel justere en glidebryter).

**[OnSelect](properties-core.md)** – hvordan appen responderer når brukeren klikker eller trykker på en kontroll.

**[PaddingBottom](properties-size-location.md)** – avstanden mellom teksten i en kontroll og den nederste kanten av kontrollen.

**[PaddingLeft](properties-size-location.md)** – avstanden mellom teksten i en kontroll og den venstre kanten av kontrollen.

**[PaddingRight](properties-size-location.md)** – avstanden mellom teksten i en kontroll og den høyre kanten av kontrollen.

**[PaddingTop](properties-size-location.md)** – avstanden mellom teksten i en kontroll og den øverste kanten av kontrollen.

**[PressedBorderColor](properties-color-border.md)**  – fargen på kontrollens kantlinje når brukeren trykker eller klikker på kontrollen.

**[PressedColor](properties-color-border.md)** – fargen på teksten i en kontroll når brukeren trykker eller klikker på kontrollen.

**[PressedFill](properties-color-border.md)** – bakgrunnsfargen på teksten i en kontroll når brukeren trykker eller klikker på kontrollen.

**[Tilbakestill](properties-core.md)** – om en kontroll tilbakestilles til standardverdien.

**SelectedText (avskrevet)** – en strengverdi som representerer det valgte elementet.

**[SelectionColor](properties-color-border.md)** – tekstfargen for et merket element, elementer i en liste eller fargen på markeringsverktøyet i en pennekontroll.

**[SelectionFill](properties-color-border.md)** – bakgrunnsfargen for et merket element eller elementer i en liste eller et merket område til en pennekontroll.

**SelectMultiple** – om en bruker kan velge mer enn ett element i en liste.

**[Størrelse](properties-text.md)** – skriftstørrelsen på teksten som vises på en kontroll.

**[Strikethrough](properties-text.md)** – om det vises en linje gjennom teksten som vises på en kontroll.

**[TabIndex](properties-accessibility.md)** – navigasjonsrekkefølge for tastatur i forhold til andre kontroller.

**[Verktøytips](properties-core.md)** – forklarende tekst som vises når brukeren holder pekeren over en kontroll.

**[Underline](properties-text.md)** – om det vises en linje under teksten som vises på en kontroll.

**[Synlig](properties-core.md)** – om kontrollen vises eller skjules.

**[Bredde](properties-size-location.md)** – avstanden mellom kontrollens venstre og høyre kant.

**[X](properties-size-location.md)** – avstanden mellom kontrollens venstre kant og den venstre kanten til kontrollens overordnede beholder (eller skjermen, hvis det ikke finnes noen overordnet beholder).

**[Y](properties-size-location.md)** – avstanden mellom kontrollens øvre kant og den øvre kanten til kontrollens overordnede beholder (eller skjermen, hvis det ikke finnes noen overordnet beholder).

## <a name="related-functions"></a>Relaterte funksjoner
[**Distinct**( *DataSource*, *ColumnName* )](../functions/function-distinct.md)

## <a name="example"></a>Eksempel
1. Legg til en **Liste**-kontroll, gi den navnet **CategoryList**, og angi **[Elementer](properties-core.md)** -egenskapen som denne formelen:<br>
   **["Carpet","Hardwood","Tile"]**
   
    Vet du ikke hvordan du [legger til, gir navn til og konfigurerer en kontroll](../add-configure-controls.md)?
   
    ![Gulvbeleggkategorier i en liste](./media/control-list-box/category-listbox.png)
2. Legg til tre **[Rullegardin](control-drop-down.md)** -kontroller, flytt dem under **CategoryList**, og gi dem navnene **CarpetList**, **HardwoodList** og **TileList**.
3. Angi **[Elementer](properties-core.md)** -egenskapen til hver av **[Rullegardin](control-drop-down.md)** -kontrollene til en av disse verdiene:
   
   * CarpetList: **["Caserta Stone Beige","Ageless Beauty Clay", "Lush II Tundra"]**
   * HardwoodList: **["Golden Teak","Natural Hickory", "Victoria Mahogany"]**
   * TileList: **["Honey Onyx Marble","Indian Autumn Slate", "Panaria Vitality Ceramic"]**
     
     ![Navn på gulvbelegg i rullegardinlister](./media/control-list-box/flooring-names.png)
4. Angi **[Synlig](properties-core.md)** -egenskapen til hver **[Rullegardin](control-drop-down.md)** -kontroll som en av disse verdiene:
   
   * CarpetList: **Hvis ("Carpet" i CategoryList.SelectedItems.Value, true)**
   * HardwoodList: **Hvis ("Hardwood" i CategoryList.SelectedItems.Value, true)**
   * TileList: **Hvis ("Flisen» i CategoryList.SelectedItems.Value, true)**
     
     Vil du ha mer informasjon om **[If](../functions/function-if.md)** -funksjonen eller [andre funksjoner](../formula-reference.md)?
5. Trykk på F5, og velg deretter ett eller flere elementer i **CategoryList**.
   
    Den riktige **[Rullegardin](control-drop-down.md)** -kontrollen eller -kontrollene vises basert på valget eller valgene.
   
    ![Navn på gulvbelegg i rullegardinlister](./media/control-list-box/selected-lists.png)
6. (valgfritt) Trykk på ESC for å gå tilbake til standardarbeidsområdet.


## <a name="accessibility-guidelines"></a>Retningslinjer for tilgjengelighet
### <a name="color-contrast"></a>Fargekontrast
Det må være tilstrekkelig fargekontrast mellom:
* **SelectionColor** og **SelectionFill**
* **SelectionFill** og **[Fyll](properties-color-border.md)**
* **[HoverFill](properties-color-border.md)** og **[Fyll](properties-color-border.md)**
* **[PressedFill](properties-color-border.md)** og **[Fyll](properties-color-border.md)**

Dette er i tillegg til [kravene for standard fargekontrast](../accessible-apps-color.md).

### <a name="screen-reader-support"></a>Kundestøtte for skjermlesere
* **[AccessibleLabel](properties-accessibility.md)** bør vises.

### <a name="keyboard-support"></a>Tastaturstøtte
* **[TabIndex](properties-accessibility.md)** må være null eller større, slik at tastaturbrukere kan navigere til den.
* Fokusindikatorer må være godt synlige. Bruk **[FocusedBorderColor](properties-color-border.md)** og **[FocusedBorderThickness](properties-color-border.md)** for å oppnå dette.

    > [!NOTE]
  > TAB navigerer til eller bort fra **listeboksen**. Piltastene navigerer innholdet i **listeboksen**.
