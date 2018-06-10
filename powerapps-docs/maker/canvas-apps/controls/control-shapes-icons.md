---
title: 'Figur-kontroller og ikon-kontroller: referanse | Microsoft Docs'
description: Informasjon, deriblant egenskaper og eksempler, om figur-kontroller og ikon-kontroller
services: ''
suite: powerapps
documentationcenter: na
author: fikaradz
manager: anneta
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/25/2016
ms.author: fikaradz
ms.openlocfilehash: 7a71695460453816dd5c63dad8477cb7ccc703d7
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/22/2018
ms.locfileid: "30995947"
---
# <a name="shape-controls-and-icon-controls-in-powerapps"></a>Figur-kontroller og ikon-kontroller i PowerApps
Grafikk som du kan konfigurere egenskaper for utseende og virkemåte for.

## <a name="description"></a>Beskrivelse
Disse kontrollene omfatter piler, geometriske former, handlingsikoner og symboler som du kan konfigurere egenskaper som fyll, størrelse og plassering for. Du kan også konfigurere kontrollenes **[OnSelect](properties-core.md)**-egenskaper, slik at appen reagerer hvis brukeren klikker eller trykker på kontrollen.

## <a name="key-properties"></a>Nøkkelegenskaper
**[Fyll](properties-color-border.md)** – bakgrunnsfargen på kontrollen.

**[OnSelect](properties-core.md)** – hvordan appen reagerer når brukeren klikker eller trykker på en kontroll.

## <a name="additional-properties"></a>Tilleggsegenskaper
**[DisplayMode](properties-core.md)** – om kontrollen tillater brukerinndata (**Rediger**), viser kun data (**Vis**) eller er deaktivert (**Deaktivert**).

**[Høyde](properties-size-location.md)** – avstanden mellom kontrollens øvre og nedre kant.

**[HoverFill](properties-color-border.md)**  – bakgrunnsfargen for en kontroll når brukeren holder musepekeren på den.

**[PressedBorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje når brukeren trykker eller klikker på kontrollen.

**[FocusedBorderThickness](properties-color-border.md)**  – tykkelsen på kontrollens kantlinje når den har tastaturfokus.

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
3. Legg til en **Figur**-kontroll i **Source**, og angi **[OnSelect](properties-core.md)**-egenskapen som denne formelen:
   <br>**Navigate(Target, ScreenTransition.Fade)**
4. Trykk på F5, og klikk eller trykk på **Figur**-kontrollen.
   
    Skjermbildet **Target** vises.
5. (valgfritt) Trykk på Esc for å gå tilbake til standardarbeidsområdet, legge til en **Figur**-kontroll i **Target**, og angi **[OnSelect](properties-core.md)**-egenskapen til **Figur**-kontrollen som denne formelen:
   <br>**Navigate(Source, ScreenTransition.Fade)**

