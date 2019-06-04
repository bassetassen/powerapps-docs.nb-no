---
title: 'Figur-kontroller og ikon-kontroller: referanse | Microsoft Docs'
description: Informasjon, deriblant egenskaper og eksempler, om figur-kontroller og ikon-kontroller
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
ms.openlocfilehash: 88e0a74d2c25d1d2f5f571f4d1850417d1aab9ca
ms.sourcegitcommit: 4ed29d83e90a2ecbb2f5e9ec5578e47a293a55ab
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/23/2019
ms.locfileid: "63318423"
ms.PowerAppsDecimalTransform: true
---
# <a name="shape-controls-and-icon-controls-in-powerapps"></a>Figur-kontroller og ikon-kontroller i PowerApps
Grafikk som du kan konfigurere egenskaper for utseende og virkemåte for.

## <a name="description"></a>Beskrivelse
Disse kontrollene omfatter piler, geometriske former, handlingsikoner og symboler som du kan konfigurere egenskaper som fyll, størrelse og plassering for. Du kan også konfigurere sine **[OnSelect](properties-core.md)** egenskapen slik at appen reagerer Hvis brukeren velger kontrollen.

## <a name="key-properties-icons-and-shapes"></a>Nøkkelegenskapene (ikoner og figurer)
**[Fyll](properties-color-border.md)** – bakgrunnsfargen på kontrollen.

**[OnSelect](properties-core.md)**  – hvordan appen reagerer når brukeren velger en kontroll.

## <a name="key-properties-icons-only"></a>Nøkkelegenskapene (bare ikoner)

**Ikonet** -typen for ikonet for å vise (for eksempel **ArrowDown** eller **ShoppingCart**). 

**Rotasjon** -antallet grader for rotering ikonet. 

**Farge** – fargen på ikonet etter navn eller RGBA verdier.

## <a name="additional-properties"></a>Tilleggsegenskaper
**[AccessibleLabel](properties-accessibility.md)** – etikett for skjermlesere.

**[DisplayMode](properties-core.md)** – om kontrollen tillater brukerinndata (**Rediger**), bare viser data (**Vis**) eller er deaktivert (**Deaktivert**).

**[FocusedBorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje når kontrollen er fokusert.

**[FocusedBorderThickness](properties-color-border.md)** – fargen på kontrollens kantlinje når kontrollen er fokusert.

**[Høyde](properties-size-location.md)** – avstanden mellom kontrollens øvre og nedre kant.

**[HoverFill](properties-color-border.md)** – bakgrunnsfargen for en kontroll når brukeren holder musepekeren over den.

**[PressedBorderColor](properties-color-border.md)**  – fargen på kontrollens kantlinje når brukeren velger denne kontrollen.

**[PressedFill](properties-color-border.md)**  – bakgrunnsfargen for en kontroll når brukeren velger denne kontrollen.

**[TabIndex](properties-accessibility.md)** – navigasjonsrekkefølge for tastatur i forhold til andre kontroller.

**[Synlig](properties-core.md)** – om kontrollen vises eller skjules.

**[Bredde](properties-size-location.md)** – avstanden mellom kontrollens venstre og høyre kant.

**[X](properties-size-location.md)** – avstanden mellom kontrollens venstre kant og den venstre kanten til kontrollens overordnede beholder (eller skjermen, hvis det ikke finnes noen overordnet beholder).

**[Y](properties-size-location.md)** – avstanden mellom kontrollens øvre kant og den øvre kanten til kontrollens overordnede beholder (eller skjermen, hvis det ikke finnes noen overordnet beholder).

## <a name="related-functions"></a>Relaterte funksjoner

[**Navigate**( *ScreenName*; *ScreenTransition* )](../functions/function-navigate.md)

## <a name="example"></a>Eksempel

1. Gi standard **[Skjerm](control-screen.md)** -kontrollen navnet **Target**, legge til en **[Etikett](control-text-box.md)** -kontroll, og angi **[Tekst](properties-core.md)** -egenskapen til å vise **Target**.

    Lurer du på hvordan du [legger til og konfigurerer en kontroll](../add-configure-controls.md)?

1. Legge til en **[Skjerm](control-screen.md)** -kontroll, og gi den navnet **Source**.

1. Legg til en **Figur**-kontroll i **Source**, og angi **[OnSelect](properties-core.md)** -egenskapen som denne formelen:

  `Navigate(Target; ScreenTransition.Fade)`
  
1. Trykk på F5, og velg deretter den **figur** kontroll.

    Skjermbildet **Target** vises.

1. (valgfritt) Trykk på Esc for å gå tilbake til standardarbeidsområdet, legge til en **Figur**-kontroll i **Target**, og angi **[OnSelect](properties-core.md)** -egenskapen til **Figur**-kontrollen som denne formelen:

  `Navigate(Source; ScreenTransition.Fade)`

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
- **[AccessibleLabel](properties-accessibility.md)**  må være satt til en ikke-tom streng hvis grafikken brukes som en knapp eller er ikke bare for dekorasjon.

- **[AccessibleLabel](properties-accessibility.md)**  må være tom eller den tomme strengen **""** Hvis grafikken inneholder overflødig informasjon eller er bare for dekorasjon. Denne verdien gjør at skjermlesere ignorerer grafikken.

Du kan for eksempel angi den **[AccessibleLabel](properties-accessibility.md)** -egenskapen for en **innstillinger** ikonet for å **innstillinger**. Dette ikonet er ikke brukes som en knapp. Det er ved siden en **[etikett](control-text-box.md)** som også sier **innstillinger**. Skjermlesere leser både ikon- og etiketten som **innstillinger**, som er overflødig. I dette tilfellet trenger ikke ikonet en  **[AccessibleLabel](properties-accessibility.md)** .

> [!IMPORTANT]
> Skjermlesere leser lese en ikonet eller figuren som **knappen** hvis den **[AccessibleLabel](properties-accessibility.md)** er satt til en tom streng og **[TabIndex ](properties-accessibility.md)** er satt til null eller større. Slike ikoner eller figurer gjengis som knapper. 

### <a name="keyboard-support"></a>Tastaturstøtte
- **[TabIndex](properties-accessibility.md)**  må være null eller større hvis grafikken brukes som en knapp. Hvis du setter denne verdien for et ikon eller en figur, kan tastaturbrukere navigere til den.

- Fokusindikatorer må være klart synlige hvis grafikken brukes som en knapp. Bruk **[FocusedBorderColor](properties-color-border.md)** og **[FocusedBorderThickness](properties-color-border.md)** å oppnå dette resultatet.

    > [!NOTE]
    > Når  **[TabIndex](properties-accessibility.md)** -verdien er null eller større, gjengis figuren eller ikonet som en knapp. Endre ikke utseendet, men skjermlesere identifiserer bildet som en knapp. Når **[TabIndex](properties-accessibility.md)** -verdien er mindre enn null, identifiseres ikonet eller figuren som et bilde.
