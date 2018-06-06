---
title: 'Bilde-kontroll: referanse | Microsoft Docs'
description: Informasjon om Bilde-kontrollen, inkludert egenskaper og eksempler
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
ms.openlocfilehash: 0ab25713976e9f89fa74b5f7664b13dca447841e
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/22/2018
ms.locfileid: "30996492"
---
# <a name="image-control-in-powerapps"></a>Bilde-kontroll i PowerApps
En kontroll som viser et bilde, for eksempel fra en lokal fil eller en datakilde.

## <a name="description"></a>Beskrivelse
Hvis du legger til én eller flere **Bilde**-kontroller i appen din, kan du vise enkeltbilder som ikke er en del av et datasett, eller du kan inkludere bilder fra poster i datakilder.

## <a name="key-properties"></a>Nøkkelegenskaper
**[Image](properties-visual.md)** – Navnet på bildet som vises i en bilde-, lyd- eller mikrofonkontroll.

## <a name="additional-properties"></a>Tilleggsegenskaper
**ApplyEXIFOrientation** – Hvorvidt retningen som er angitt i bildets innebygde EXIF-data automatisk skal brukes.

**AutoDisableOnSelect** – Deaktiverer kontrollen automatisk mens OnSelect-virkemåten kjøres.

**[BorderColor](properties-color-border.md)** – Fargen på kontrollens kantlinje.

**[BorderStyle](properties-color-border.md)** – Hvorvidt kontrollens kantlinje er satt til **Solid**, **Dashed**, **Dotted** eller **None**.

**[BorderThickness](properties-color-border.md)** – Tykkelsen på kontrollens kantlinje.

**[FocusedBorderThickness](properties-color-border.md)**  – Tykkelsen på kontrollens kantlinje når den har tastaturfokus.

**CalculateOriginalDimensions** – Aktiverer egenskapene **OriginalHeight** og **OriginalWidth**.

**[DisplayMode](properties-core.md)** – Hvorvidt kontrollen tillater brukerinndata (**Edit**), bare viser data (**View**) eller er deaktivert (**Disabled**).

**[DisabledBorderColor](properties-color-border.md)**  – Fargen på kontrollens kantlinje hvis kontrollens **[DisplayMode](properties-core.md)**-egenskap er angitt som **Disabled**.

**[DisabledFill](properties-color-border.md)** – Bakgrunnsfargen på en kontroll hvis kontrollens **[DisplayMode](properties-core.md)**-egenskap er angitt som **Disabled**.

**[Fill](properties-color-border.md)** – Bakgrunnsfargen på kontrollen.

**FlipHorizontal** – Hvorvidt bildet skal vendes vannrett før det blir vist.

**FlipVertical** – Hvorvidt bildet skal vendes loddrett før det blir vist.

**[Height](properties-size-location.md)** – Avstanden mellom kontrollens øvre og nedre kant.

**[HoverBorderColor](properties-color-border.md)**  – Fargen på kontrollens kantlinje når brukeren holder musepekeren på denne kontrollen.

**[HoverFill](properties-color-border.md)**  – Bakgrunnsfargen for en kontroll når brukeren holder musepekeren over den.

**[ImagePosition](properties-visual.md)** – Plasseringen (**Fill**, **Fit**, **Stretch**, **Tile** eller **Center**) til et bilde på et skjermbilde eller en kontroll hvis skjermbildet eller kontrollen ikke har samme størrelse som bildet.

**ImageRotation** – Hvordan bildet skal roteres før det vises.  Verdiene kan være none, clockwise (CW) 90 degrees, counter-clockwise (CCW) 90 degrees og clockwise 180 degrees.

**[OnSelect](properties-core.md)** – Hvordan appen responderer når brukeren klikker eller trykker på en kontroll.

**OriginalHeight** – Opprinnelig høyde på et bilde, aktivert med **CalculateOriginalDimensions**-egenskapen.

**OriginalWidth** – Opprinnelig bredde på et bilde, aktivert med **CalculateOriginalDimensions**-egenskapen.

**[PaddingBottom](properties-size-location.md)** – Avstanden mellom teksten i en kontroll og den nederste kanten av kontrollen.

**[PaddingLeft](properties-size-location.md)** – Avstanden mellom teksten i en kontroll og den venstre kanten av kontrollen.

**[PaddingRight](properties-size-location.md)** – Avstanden mellom teksten i en kontroll og den høyre kanten av kontrollen.

**[PaddingTop](properties-size-location.md)** – Avstanden mellom teksten i en kontroll og den øverste kanten av kontrollen.

**[PressedBorderColor](properties-color-border.md)**  – Fargen på kontrollens kantlinje når brukeren trykker eller klikker på kontrollen.

**[PressedFill](properties-color-border.md)** – Bakgrunnsfargen i en kontroll når brukeren trykker eller klikker på kontrollen.

**[RadiusBottomLeft](properties-size-location.md)** – I hvilken grad hjørnet nederst til venstre i en kontroll avrundes.

**[RadiusBottomRight](properties-size-location.md)**  – I hvilken grad hjørnet nederst til høyre i en kontroll avrundes.

**[RadiusTopLeft](properties-size-location.md)**  – I hvilken grad hjørnet øverst til venstre i en kontroll avrundes.

**[RadiusTopRight](properties-size-location.md)**  – I hvilken grad hjørnet øverst til høyre i en kontroll avrundes.

**[Tooltip](properties-core.md)** – Forklarende tekst som vises når brukeren holder pekeren over en kontroll.

**Transparency** – I hvor stor grad kontrollene bak et bilde forblir synlige.

**[Visible](properties-core.md)** – Hvorvidt kontrollen vises eller skjules.

**[Width](properties-size-location.md)** – Avstanden mellom kontrollens venstre og høyre kant.

**[X](properties-size-location.md)** – Avstanden mellom kontrollens venstre kant og den venstre kanten til kontrollens overordnede beholder (eller skjermbilde, hvis det ikke finnes noen overordnet beholder).

**[Y](properties-size-location.md)** – Avstanden mellom kontrollens øvre kant og den øvre kanten til kontrollens overordnede beholder (eller skjermbilde, hvis det ikke finnes noen overordnet beholder).

## <a name="related-functions"></a>Relaterte funksjoner
[**Remove**( *DataSource*, ThisItem )](../functions/function-remove-removeif.md)

## <a name="examples"></a>Eksempler
### <a name="show-an-image-from-a-local-file"></a>Vise et bilde fra en lokal fil
1. Klikk eller trykk på **Media** på **Fil**-fanen, og klikk eller trykk deretter på **Bla gjennom**.
2. Klikk eller trykk på bildefilen som du vil legge til, klikk eller trykk på **Åpne** og trykk deretter på Esc for å gå tilbake til standardarbeidsområdet.
3. Legg til en **Bilde**-kontroll, og angi **Image**-egenskapen til navnet på filen du la til.

    Vet du ikke hvordan du [legger til og konfigurerer en kontroll](../add-configure-controls.md)?

    **Bilde**-kontrollen viser bildet du har angitt.

### <a name="show-a-set-of-images-from-a-data-source"></a>Vise et sett med bilder fra en datakilde
1. Last ned denne [Excel-filen](https://pwrappssamples.blob.core.windows.net/samples/FlooringEstimates.xlsx), og lagre den på den lokale enheten.
2. Opprett eller åpne en app i PowerApps Studio, og klikk eller trykk på **Legg til en datakilde** i ruten til høyre.

    Hvis **Legg til en datakilde** ikke vises i den høyre ruten, kan du klikke eller trykke på et skjermbilde i navigasjonsfeltet til venstre.
3. Klikk eller trykk på **Legg til statiske data på appen**, klikk eller trykk på Excel-filen du lastet ned og klikk eller trykk deretter på **Åpne**.
4. Velg avmerkingsboksen for **Flooring Estimates**, og klikk eller trykk deretter på **Koble til**.
5. Legg til en **Galleri**-kontroll med bilder, og angi kontrollens **[Items](properties-core.md)**-egenskap til **FlooringEstimates**.

    Vet du ikke hvordan du [legger til og konfigurerer en kontroll](../add-configure-controls.md)?

    **Galleri**-kontrollen viser bilder av tepper, parkett og flisprodukter basert på koblinger i Excel-filen du lastet ned.
