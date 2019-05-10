---
title: 'Rullegardinkontroll: referanse | Microsoft Docs'
description: Informasjon om Rullegardin-kontrollen, inkludert egenskaper og eksempler
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
ms.openlocfilehash: 02e8477873adad476c65e513a470e027aee5cd5c
ms.sourcegitcommit: 8d0ba2ec0c97be91d1350180dd6881c14dec8f2d
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 05/10/2019
ms.locfileid: "65517398"
---
# <a name="drop-down-control-in-powerapps"></a>Rullegardin-kontrollen i PowerApps
En liste som viser bare det første elementet, med mindre brukeren åpner det.

## <a name="description"></a>Beskrivelse
En **rullegardin**-kontroll sparer skjermplass, spesielt når listen inneholder mange valg. Kontrollen tar opp bare én linje med mindre brukeren velger vinkeltegnet for å vise flere valg.  Kontrollen viser maksimalt 500 elementer.

## <a name="key-properties"></a>Nøkkelegenskaper
**[Standard](properties-core.md)** – startverdien for en kontroll før brukeren angir en annen verdi.

**[Elementer](properties-core.md)**  – kilden til data som inneholder elementer som vises i kontrollen. Hvis kilden har flere kolonner, setter du kontrollens **Verdi**-egenskap til datakolonnen du vil vise.
  
**Verdi** – kolonnen med data du vil vise i kontrollen (for eksempel hvis en datakilde har flere kolonner).

**Valgte** – dataposten som representerer det valgte elementet.

**AllowEmptySelection** – om kontrollen viser et tomt valg hvis ingen elementer er valgt. App-brukere kan også fjerne deres valgene ved å velge det tomme elementet.

## <a name="additional-properties"></a>Tilleggsegenskaper
**[AccessibleLabel](properties-accessibility.md)** – etikett for skjermlesere.

**[BorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje.

**[BorderStyle](properties-color-border.md)** – om kontrollens kantlinje er satt til **Heltrukket**, **Stiplet**, **Prikket** eller **Ingen**.

**[BorderThickness](properties-color-border.md)** – tykkelsen til kontrollens kantlinje.

**ChevronBackground** – fargen bak den nedovervendte pilen i en rullegardinliste.

**ChevronFill** – fargen på den nedovervendte pilen i en rullegardinliste.

**[Farge](properties-color-border.md)** – fargen på teksten i kontrollen.

**[DisplayMode](properties-core.md)** – om kontrollen tillater brukerinndata (**Rediger**), bare viser data (**Vis**) eller er deaktivert (**Deaktivert**).

**[DisabledBorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje hvis kontrollens **[DisplayMode](properties-core.md)**-egenskap er angitt til **Deaktivert**.

**[DisabledColor](properties-color-border.md)** – fargen på kontrollens tekst hvis kontrollens **[DisplayMode](properties-core.md)**-egenskap er angitt som **Deaktivert**.

**[DisabledFill](properties-color-border.md)** – bakgrunnsfargen på en kontroll hvis **[DisplayMode](properties-core.md)**-egenskapen er angitt som **Deaktivert**.

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

**[SelectionFill](properties-color-border.md)** – bakgrunnsfargen for et merket element eller merkede elementer i en liste eller et merket område for en pennekontroll.

**[Størrelse](properties-text.md)** – skriftstørrelsen på teksten som vises på en kontroll.

**[Strikethrough](properties-text.md)** – om det vises en linje gjennom teksten som vises på en kontroll.

**[TabIndex](properties-accessibility.md)** – navigasjonsrekkefølge for tastatur i forhold til andre kontroller.

**[Verktøytips](properties-core.md)** – forklarende tekst som vises når brukeren holder pekeren over en kontroll.

**[Underline](properties-text.md)** – om det vises en linje under teksten som vises på en kontroll.

**[Synlig](properties-core.md)** – om kontrollen vises eller skjules.

**[Bredde](properties-size-location.md)** – avstanden mellom kontrollens venstre og høyre kant.

**[X](properties-size-location.md)** – avstanden mellom kontrollens venstre kant og den venstre kanten til kontrollens overordnede beholder (eller skjermen, hvis det ikke finnes noen overordnet beholder).

**[Y](properties-size-location.md)** – avstanden mellom kontrollens øvre kant og den øvre kanten til kontrollens overordnede beholder (eller skjermen, hvis det ikke finnes noen overordnet beholder).

## <a name="example"></a>Eksempel

### <a name="simple-list"></a>Enkel liste

1. Legg til en **Rullegardin**-kontroll, og sett **[Elementer](properties-core.md)**-egenskapen til dette uttrykket:

    `["Seattle", "Tokyo", "London", "Johannesburg", "Rio de Janeiro"]`

    Vet du ikke hvordan du [legger til, gir navn til og konfigurerer en kontroll](../add-configure-controls.md)?

1. Vis elementene i listen ved å velge pil ned for kontrollen mens du holder nede Alt-tasten.

### <a name="list-from-a-data-source"></a>Liste fra en datakilde
Prinsippene i denne prosedyren gjelder noen [datakilden som inneholder tabellene](../connections-list.md#tables) , men, for å følge disse trinnene nøyaktig, må du åpne et miljø som en Common Data Service-database er opprettet og eksempeldata dataene som er lagt til.

1. [Åpne en tom app](../data-platform-create-app-scratch.md#open-a-blank-app), og [spesifiser deretter **Kontoer**-enheten](../data-platform-create-app-scratch.md#specify-an-entity).

1. Legg til en **Rullegardin**-kontroll, og sett **[Elementer](properties-core.md)**-egenskapen til denne formelen:

    `Distinct(Accounts, address1_city)`

    Denne formelen viser alle byene i **Kontoer** enheten. Hvis mer enn én post har samme by, skjuler **[Distinkt](../functions/function-distinct.md)**-funksjonen dupliseringen i rullegardinkontrollen din.

1. (valgfritt) Endre navnet på **Rullegardin**-kontrollen til **Byer**, legg til en loddrett **Galleri**-kontroll, og sett **[Elementer](properties-core.md)**-egenskapen for galleriet til denne formelen:

    `Filter(Accounts, address1_city = Cities.Selected.Value)`

    Denne **[Filter](../functions/function-filter-lookup.md)**-funksjonen viser bare de oppføringene i **Kontoer**-enheten der byen samsvarer med den valgte verdien i **Byer**-kontrollen.

## <a name="accessibility-guidelines"></a>Retningslinjer for tilgjengelighet
### <a name="color-contrast"></a>Fargekontrast
Det må være tilstrekkelig fargekontrast mellom:
* **ChevronFill** og **ChevronBackground**
* **ChevronHoverFill** og **ChevronHoverBackground**
* **SelectionColor** og **SelectionFill**
* **SelectionFill** og **[Fyll](properties-color-border.md)**

Dette er i tillegg til [kravene for standard fargekontrast](../accessible-apps-color.md).

### <a name="screen-reader-support"></a>Kundestøtte for skjermlesere
* **[AccessibleLabel](properties-accessibility.md)** bør vises.

### <a name="keyboard-support"></a>Tastaturstøtte
* **[TabIndex](properties-accessibility.md)** må være null eller større, slik at tastaturbrukere kan navigere til den.
* Fokusindikatorer må være godt synlige. Bruk **[FocusedBorderColor](properties-color-border.md)** og **[FocusedBorderThickness](properties-color-border.md)** for å oppnå dette.
