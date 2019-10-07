---
title: 'Figur-kontroller og ikon-kontroller: referanse | Microsoft Docs'
description: Informasjon, deriblant egenskaper og eksempler, om figur-kontroller og ikon-kontroller
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
ms.openlocfilehash: 46f1974b5ff32cf21d1e9f24c15362c24b44fbe3
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/07/2019
ms.locfileid: "71986326"
---
# <a name="shape-controls-and-icon-controls-in-powerapps"></a>Figur-kontroller og ikon-kontroller i PowerApps
Grafikk som du kan konfigurere egenskaper for utseende og virkemåte for.

## <a name="description"></a>Beskrivelse
Disse kontrollene omfatter piler, geometriske former, handlingsikoner og symboler som du kan konfigurere egenskaper som fyll, størrelse og plassering for. Du kan også konfigurere **[OnSelect](properties-core.md)** -egenskapen slik at appen reagerer hvis brukeren velger kontrollen.

## <a name="key-properties-icons-and-shapes"></a>Nøkkel egenskaper (ikoner og figurer)
**[Fyll](properties-color-border.md)** – bakgrunnsfargen på kontrollen.

**[OnSelect](properties-core.md)** – hvordan appen reagerer når brukeren velger en kontroll.

## <a name="key-properties-icons-only"></a>Nøkkel egenskaper (bare ikoner)

**Ikon** -typen ikon som skal vises (for eksempel **ArrowDown** eller **ShoppingCart**). 

**Rotasjon** – antallet grader som skal roteres ikonet. 

**Farge** – fargen på ikonet med navn-eller RGBA-verdier.

## <a name="additional-properties"></a>Tilleggsegenskaper
**[AccessibleLabel](properties-accessibility.md)** – etikett for skjermlesere.

**[DisplayMode](properties-core.md)** – om kontrollen tillater brukerinndata (**Rediger**), bare viser data (**Vis**) eller er deaktivert (**Deaktivert**).

**[FocusedBorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje når kontrollen er fokusert.

**[FocusedBorderThickness](properties-color-border.md)** – fargen på kontrollens kantlinje når kontrollen er fokusert.

**[Høyde](properties-size-location.md)** – avstanden mellom kontrollens øvre og nedre kant.

**[HoverFill](properties-color-border.md)** – bakgrunnsfargen for en kontroll når brukeren holder musepekeren over den.

**[PressedBorderColor](properties-color-border.md)** – fargen på kontrollens kant linje når brukeren velger kontrollen.

**[PressedFill](properties-color-border.md)** – bakgrunns fargen for en kontroll når brukeren velger denne kontrollen.

**[TabIndex](properties-accessibility.md)** – navigasjonsrekkefølge for tastatur i forhold til andre kontroller.

**[Synlig](properties-core.md)** – om kontrollen vises eller skjules.

**[Bredde](properties-size-location.md)** – avstanden mellom kontrollens venstre og høyre kant.

**[X](properties-size-location.md)** – avstanden mellom kontrollens venstre kant og den venstre kanten til kontrollens overordnede beholder (eller skjermen, hvis det ikke finnes noen overordnet beholder).

**[Y](properties-size-location.md)** – avstanden mellom kontrollens øvre kant og den øvre kanten til kontrollens overordnede beholder (eller skjermen, hvis det ikke finnes noen overordnet beholder).

## <a name="related-functions"></a>Relaterte funksjoner

[**Navigate**( *ScreenName*, *ScreenTransition* )](../functions/function-navigate.md)

## <a name="example"></a>Eksempel

1. Gi standard **[Skjerm](control-screen.md)** -kontrollen navnet **Target**, legge til en **[Etikett](control-text-box.md)** -kontroll, og angi **[Tekst](properties-core.md)** -egenskapen til å vise **Target**.

    Lurer du på hvordan du [legger til og konfigurerer en kontroll](../add-configure-controls.md)?

1. Legge til en **[Skjerm](control-screen.md)** -kontroll, og gi den navnet **Source**.

1. Legg til en **Figur**-kontroll i **Source**, og angi **[OnSelect](properties-core.md)** -egenskapen som denne formelen:

  `Navigate(Target, ScreenTransition.Fade)`
  
1. Trykk på F5, og velg deretter **form** -kontrollen.

    Skjermbildet **Target** vises.

1. (valgfritt) Trykk på Esc for å gå tilbake til standardarbeidsområdet, legge til en **Figur**-kontroll i **Target**, og angi **[OnSelect](properties-core.md)** -egenskapen til **Figur**-kontrollen som denne formelen:

  `Navigate(Source, ScreenTransition.Fade)`

## <a name="accessibility-guidelines"></a>Retningslinjer for tilgjengelighet

### <a name="color-contrast"></a>Fargekontrast

Følgende gjelder bare for grafikk som skal brukes som knapper, og ikke bare som dekorasjon.

For ikoner:
- **[Farge](properties-color-border.md)** og **[Fyll](properties-color-border.md)**
- Andre [standardkrav for fargekontrast](../accessible-apps-color.md) gjelder (hvis den brukes som en knapp)

For figurer med kantlinjer:
- **[BorderColor](properties-color-border.md)** og fargen utenfor kontrollen
- **[FocusedBorderColor](properties-color-border.md)** og fargen utenfor kontrollen (hvis den brukes som en knapp)

For figurer uten kantlinjer:
- **[Fyll](properties-color-border.md)** og fargen utenfor kontrollen
- **[PressedFill](properties-color-border.md)** og fargen utenfor kontrollen (hvis den brukes som en knapp)
- **[HoverFill](properties-color-border.md)** og fargen utenfor kontrollen (hvis den brukes som en knapp)

### <a name="screen-reader-support"></a>Støtte for skjermleser
- **[AccessibleLabel](properties-accessibility.md)** må settes til en streng som ikke er tom, Hvis grafikken brukes som en knapp eller ellers ikke bare er for dekorasjon.

- **[AccessibleLabel](properties-accessibility.md)** må være tom eller den tomme strengen **«»** Hvis grafikken inneholder overflødig informasjon eller er rent for dekorasjon. Denne verdien gjør at skjerm lesere ignorerer grafikken.

Du kan for eksempel angi **[AccessibleLabel](properties-accessibility.md)** -egenskapen for et **Innstillinger** -ikon til **Innstillinger**. Dette ikonet brukes ikke som en knapp. Det er ved siden av en **[etikett](control-text-box.md)** som også sier **Innstillinger**. Skjerm lesere leser både ikonet og etiketten som **Innstillinger**, noe som ikke nødvendigvis er detaljert. I dette tilfellet trenger ikke ikonet et **[AccessibleLabel](properties-accessibility.md)** .

> [!IMPORTANT]
> Skjerm lesere leser et ikon eller en figur som **knapp** Hvis **[AccessibleLabel](properties-accessibility.md)** er satt til en tom streng, og **[TabIndex](properties-accessibility.md)** er satt til null eller større. Slike ikoner eller figurer gjengis som knapper. 

### <a name="keyboard-support"></a>Tastaturstøtte
- **[TabIndex](properties-accessibility.md)** må være null eller større Hvis grafikken brukes som en knapp. Hvis du angir denne verdien for et ikon eller en figur, kan tastatur brukere navigere til den.

- Fokus indikatorer må være klart synlige Hvis grafikken brukes som en knapp. Bruk **[FocusedBorderColor](properties-color-border.md)** og **[FocusedBorderThickness](properties-color-border.md)** for å oppnå dette resultatet.

    > [!NOTE]
    > Når  **[TabIndex](properties-accessibility.md)** -verdien er null eller større, gjengis figuren eller ikonet som en knapp. Utseendet endres ikke, men skjerm lesere identifiserer bildet som en knapp riktig. Når **[TabIndex](properties-accessibility.md)** -verdien er mindre enn null, identifiseres ikonet eller figuren som et bilde.
