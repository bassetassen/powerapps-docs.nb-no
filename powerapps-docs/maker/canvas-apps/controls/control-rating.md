---
title: 'Vurdering-kontrollen: referanse | Microsoft Docs'
description: Informasjon om Vurdering-kontrollen, inkludert egenskaper og eksempler
author: fikaradz
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 10/25/2016
ms.author: fikaradz
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 774b5294f9d03564caa658a04aff0f682a7bb43f
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/07/2019
ms.locfileid: "71993336"
---
# <a name="rating-control-in-powerapps"></a>Vurdering-kontrollen i PowerApps
En kontroll som lar brukere angi en verdi mellom 1 og et maksimalt antall som du angir.

## <a name="description"></a>Beskrivelse
I denne kontrollen kan brukeren for eksempel angi hvor mye de likte noe ved å velge et bestemt antall stjerner.

## <a name="key-properties"></a>Nøkkelegenskaper
**[Default](properties-core.md)** – Startverdien for en kontroll før den endres av brukeren.

**Max** – Den maksimale verdien brukeren kan angi for en glidebryter eller en vurdering.

## <a name="additional-properties"></a>Tilleggsegenskaper
**[AccessibleLabel](properties-accessibility.md)** – etikett for skjermlesere.

**[BorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje.

**[BorderStyle](properties-color-border.md)** – om kontrollens kantlinje er satt til **Heltrukket**, **Stiplet**, **Prikket** eller **Ingen**.

**[BorderThickness](properties-color-border.md)** – tykkelsen til kontrollens kantlinje.

**[DisplayMode](properties-core.md)** – om kontrollen tillater brukerinndata (**Rediger**), bare viser data (**Vis**) eller er deaktivert (**Deaktivert**).

**[Fyll](properties-color-border.md)** – bakgrunnsfargen på kontrollen.

**[FocusedBorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje når kontrollen er fokusert.

**[FocusedBorderThickness](properties-color-border.md)** – fargen på kontrollens kantlinje når kontrollen er fokusert.

**[Høyde](properties-size-location.md)** – avstanden mellom kontrollens øvre og nedre kant.

**[OnChange](properties-core.md)** – Hvordan appen reagerer når brukeren endrer verdien på en kontroll (ved å for eksempel justere en glidebryter).

**[OnSelect](properties-core.md)** – Hvordan appen responderer når brukeren klikker eller trykker på en kontroll.

**RatingFill** – Fargen på stjerner i en kontroll for vurdering.

**ReadOnly** – Hvorvidt en bruker kan endre verdien til en glidebryter eller vurderingskontroll.

**[Reset](properties-core.md)** – Hvorvidt en kontroll tilbakestilles til standardverdien.

**ShowValue** – Om glidebryterens eller vurderingens verdi vises når en bruker endrer verdien eller holder musepekeren over kontrollen.

**[TabIndex](properties-accessibility.md)** – navigasjonsrekkefølge for tastatur i forhold til andre kontroller.

**[Verktøytips](properties-core.md)** – forklarende tekst som vises når brukeren holder pekeren over en kontroll.

**[Synlig](properties-core.md)** – om kontrollen vises eller skjules.

**[Bredde](properties-size-location.md)** – avstanden mellom kontrollens venstre og høyre kant.

**[X](properties-size-location.md)** – avstanden mellom kontrollens venstre kant og den venstre kanten til kontrollens overordnede beholder (eller skjermen, hvis det ikke finnes noen overordnet beholder).

**[Y](properties-size-location.md)** – avstanden mellom kontrollens øvre kant og den øvre kanten til kontrollens overordnede beholder (eller skjermen, hvis det ikke finnes noen overordnet beholder).

## <a name="related-functions"></a>Relaterte funksjoner
[**Average**( *Value1*, *Value2,* ... )](../functions/function-aggregates.md)

## <a name="example"></a>Eksempel
1. Legge til en **Vurdering**-kontroll, og gi den navnet **Quantitative**.
   
    Vet du ikke hvordan du [legger til, gir navn til og konfigurerer en kontroll](../add-configure-controls.md)?
2. Legg til en **[Tekstinndata](control-text-input.md)** -kontroll, gi den navnet **Qualitative**, og flytte den under **Vurdering**-kontrollen.
3. Angi **[Default](properties-core.md)** -egenskapen til **[Tekstinndata](control-text-input.md)** -kontrollen som **""** , og angi kontrollens **HintText** som denne formelen:
   <br>**If(Quantitative.Value > 3, "What did you especially like?", "How might we do better?")**
   
    Vil du ha mer informasjon om **[If](../functions/function-if.md)** -funksjonen eller [andre funksjoner](../formula-reference.md)?
4. Trykk på F5, og klikk eller trykk på fire eller fem stjerner i **Vurdering**-kontrollen.
   
    Tipsteksten i **[Tekstinndata](control-text-input.md)** -kontrollen endres slik at den gjenspeiler den høye vurderingen.
5. Klikk eller trykk på færre enn fire stjerner i **Quantitative**.
   
    Tipsteksten i **[Tekstinndata](control-text-input.md)** -kontrollen endres slik at den gjenspeiler den lave vurderingen.
6. Trykk på ESC for å gå tilbake til standardarbeidsområdet.


## <a name="accessibility-guidelines"></a>Retningslinjer for tilgjengelighet
### <a name="color-contrast"></a>Fargekontrast
Det må være tilstrekkelig fargekontrast mellom:
* **RatingFill** og  **[Fyll](properties-color-border.md)**

Dette er i tillegg til [kravene for standard fargekontrast](../accessible-apps-color.md).

### <a name="screen-reader-support"></a>Kundestøtte for skjermlesere
* **[AccessibleLabel](properties-accessibility.md)** bør vises.

    > [!NOTE]
  > Skjermlesere bruker **Vurdering**-kontrollen som alternativknapper.

### <a name="keyboard-support"></a>Tastaturstøtte
* **[TabIndex](properties-accessibility.md)** må være null eller større, slik at tastaturbrukere kan navigere til den.
* Fokusindikatorer må være godt synlige. Bruk **[FocusedBorderColor](properties-color-border.md)** og **[FocusedBorderThickness](properties-color-border.md)** for å oppnå dette.
* Vurder å bruke en annen kontroll hvis det er for mange stjerner. Det kan være kjedelig å navigere med et tastatur, og vanskelig å merke/velge nøyaktig med en berøringsskjerm.

    > [!NOTE]
  > De samme tastatursamhandlingene for alternativknapper kan brukes for **Vurdering**.
