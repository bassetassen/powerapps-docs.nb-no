---
title: 'Figur-kontroller og ikon-kontroller: referanse | Microsoft Docs'
description: Informasjon, deriblant egenskaper og eksempler, om figur-kontroller og ikon-kontroller
documentationcenter: na
author: fikaradz
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: reference
ms.component: canvas
ms.date: 10/25/2016
ms.author: fikaradz
ms.openlocfilehash: 8b6ec4ac944e8527bda508f4f005361d681be8e0
ms.sourcegitcommit: 79b8842fb0f766a0476dae9a537a342c8d81d3b3
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 07/07/2018
ms.locfileid: "37899621"
---
# <a name="shape-controls-and-icon-controls-in-powerapps"></a>Figur-kontroller og ikon-kontroller i PowerApps
Grafikk som du kan konfigurere egenskaper for utseende og virkemåte for.

## <a name="description"></a>Beskrivelse
Disse kontrollene omfatter piler, geometriske former, handlingsikoner og symboler som du kan konfigurere egenskaper som fyll, størrelse og plassering for. Du kan også konfigurere kontrollenes **[OnSelect](properties-core.md)**-egenskaper, slik at appen reagerer hvis brukeren klikker eller trykker på kontrollen.

## <a name="key-properties"></a>Nøkkelegenskaper
**[Fyll](properties-color-border.md)** – bakgrunnsfargen på kontrollen.

**[OnSelect](properties-core.md)** – hvordan appen reagerer når brukeren klikker eller trykker på en kontroll.

## <a name="additional-properties"></a>Tilleggsegenskaper
**[AccessibleLabel](properties-accessibility.md)** – etikett for skjermlesere.

**[DisplayMode](properties-core.md)** – om kontrollen tillater brukerinndata (**Rediger**), bare viser data (**Vis**) eller er deaktivert (**Deaktivert**).

**[FocusedBorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje når kontrollen er fokusert.

**[FocusedBorderThickness](properties-color-border.md)** – fargen på kontrollens kantlinje når kontrollen er fokusert.

**[Høyde](properties-size-location.md)** – avstanden mellom kontrollens øvre og nedre kant.

**[HoverFill](properties-color-border.md)**  – bakgrunnsfargen for en kontroll når brukeren holder musepekeren på den.

**[PressedBorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje når brukeren trykker eller klikker på kontrollen.

**[PressedFill](properties-color-border.md)** – bakgrunnsfargen i en kontroll når brukeren trykker eller klikker på kontrollen.

**[TabIndex](properties-accessibility.md)** – navigasjonsrekkefølge for tastatur i forhold til andre kontroller.

**[Synlig](properties-core.md)** – om kontrollen vises eller skjules.

**[Bredde](properties-size-location.md)** – avstanden mellom kontrollens venstre og høyre kant.

**[X](properties-size-location.md)** – avstanden mellom kontrollens venstre kant og den venstre kanten til kontrollens overordnede beholder (eller skjermen, hvis det ikke finnes noen overordnet beholder).

**[Y](properties-size-location.md)** – avstanden mellom kontrollens øvre kant og den øvre kanten til kontrollens overordnede beholder (eller skjermen, hvis det ikke finnes noen overordnet beholder).

## <a name="related-functions"></a>Relaterte funksjoner

[**Navigate**( *ScreenName*, *ScreenTransition* )](../functions/function-navigate.md)

## <a name="example"></a>Eksempel

1. Gi standard **[Skjerm](control-screen.md)**-kontrollen navnet **Target**, legge til en **[Etikett](control-text-box.md)**-kontroll, og angi **[Tekst](properties-core.md)**-egenskapen til å vise **Target**.

    Lurer du på hvordan du [legger til og konfigurerer en kontroll](../add-configure-controls.md)?

2. Legge til en **[Skjerm](control-screen.md)**-kontroll, og gi den navnet **Source**.
3. Legg til en **Figur**-kontroll i **Source**, og angi **[OnSelect](properties-core.md)**-egenskapen som denne formelen:<br>**Navigate(Target, ScreenTransition.Fade)**
4. Trykk på F5, og klikk eller trykk på **Figur**-kontrollen.

    Skjermbildet **Target** vises.

5. (valgfritt) Trykk på Esc for å gå tilbake til standardarbeidsområdet, legge til en **Figur**-kontroll i **Target**, og angi **[OnSelect](properties-core.md)**-egenskapen til **Figur**-kontrollen som denne formelen:
   <br>**Navigate(Source, ScreenTransition.Fade)**


## <a name="accessibility-guidelines"></a>Retningslinjer for tilgjengelighet

### <a name="color-contrast"></a>Fargekontrast

Følgende gjelder bare for grafikk som skal brukes som knapper, og ikke bare som dekorasjon.

For ikoner:
* **[Farge](properties-color-border.md)** og **[Fyll](properties-color-border.md)**
* Andre [standardkrav for fargekontrast](../accessible-apps-color.md) gjelder (hvis den brukes som en knapp)

For figurer med kantlinjer:
* **[BorderColor](properties-color-border.md)** og fargen utenfor kontrollen
* **[FocusedBorderColor](properties-color-border.md)** og fargen utenfor kontrollen (hvis den brukes som en knapp)

For figurer uten kantlinjer:
* **[Fyll](properties-color-border.md)** og fargen utenfor kontrollen
* **[PressedFill](properties-color-border.md)** og fargen utenfor kontrollen (hvis den brukes som en knapp)
* **[HoverFill](properties-color-border.md)** og fargen utenfor kontrollen (hvis den brukes som en knapp)

### <a name="screen-reader-support"></a>Kundestøtte for skjermlesere
* **[AccessibleLabel](properties-accessibility.md)** må være til stede hvis grafikken brukes som en knapp eller på andre måter ikke bare er ment som dekorasjon.
* **[AccessibleLabel](properties-accessibility.md)** må være tom eller den tomme strengen **«»** hvis grafikken utelukkende er ment som dekorasjon. Dette gjør at skjermlesere ignorerer grafikken.
* **[AccessibleLabel](properties-accessibility.md)** kan være tom eller den tomme strengen **«»** hvis grafikken inneholder overflødig informasjon.

    Dette kan eksempelvis være et **Innstillinger**-ikon med tilhørende **[AccessibleLabel](properties-accessibility.md)** satt til **Innstillinger**. Dette ikonet brukes ikke som en knapp. Det er ved siden av en **[etikett](control-text-box.md)** som også sier **Innstillinger**. Skjermlesere leser ikonet som **Innstillinger**, og etiketten som **Innstillinger** på nytt. Dette er unødvendig detaljert. I dette tilfellet trenger ikke ikonet en **[AccessibleLabel](properties-accessibility.md)**.

    > [!IMPORTANT]
    > Skjermlesere leser alltid ikoner eller figurer som har **[TabIndex](properties-accessibility.md)**-verdier på null eller større, selv om **[AccessibleLabel](properties-accessibility.md)** er tom. Dette er fordi de gjengis som knapper. Hvis ingen **[AccessibleLabel](properties-accessibility.md)** er angitt, leser skjermlesere ganske enkelt grafikken som **knapp**.

### <a name="keyboard-support"></a>Tastaturstøtte
* **[TabIndex](properties-accessibility.md)**-verdien må være null eller større hvis grafikken brukes som en knapp. Dette gjør at tastaturbrukere får muligheten til å navigere til den.
* Fokusindikatorer må være klart synlige hvis grafikken brukes som en knapp. Bruk **[FocusedBorderColor](properties-color-border.md)** og **[FocusedBorderThickness](properties-color-border.md)** for å oppnå dette.

    > [!NOTE]
  > Når  **[TabIndex](properties-accessibility.md)**-verdien er null eller større, gjengis figuren eller ikonet som en knapp. Det finnes ingen endring i utseendet, men skjermlesere identifiserer bildet som en knapp. Når **[TabIndex](properties-accessibility.md)**-verdien er mindre enn null, identifiseres ikonet eller figuren som et bilde.
