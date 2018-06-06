---
title: 'Vurdering-kontrollen: referanse | Microsoft Docs'
description: Informasjon om Vurdering-kontrollen, inkludert egenskaper og eksempler
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
ms.openlocfilehash: 4dd23b8c94ee4760e40b4513e7a88667f85c3a4b
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/22/2018
ms.locfileid: "30996277"
---
# <a name="rating-control-in-powerapps"></a>Vurdering-kontrollen i PowerApps
En kontroll som lar brukere angi en verdi mellom 1 og et maksimalt antall som du angir.

## <a name="description"></a>Beskrivelse
I denne kontrollen kan brukeren for eksempel angi hvor mye de likte noe ved å velge et bestemt antall stjerner.

## <a name="key-properties"></a>Nøkkelegenskaper
**[Default](properties-core.md)** – Startverdien for en kontroll før den endres av brukeren.

**Max** – Den maksimale verdien brukeren kan angi for en glidebryter eller en vurdering.

## <a name="additional-properties"></a>Tilleggsegenskaper
**[BorderColor](properties-color-border.md)** – Fargen på kontrollens kantlinje.

**[BorderStyle](properties-color-border.md)** – Hvorvidt kontrollens kantlinje er satt til **Solid**, **Dashed**, **Dotted** eller **None**.

**[BorderThickness](properties-color-border.md)** – Tykkelsen på kontrollens kantlinje.

**[FocusedBorderThickness](properties-color-border.md)**  – Tykkelsen på kontrollens kantlinje når den har tastaturfokus.

**[DisplayMode](properties-core.md)** – Hvorvidt kontrollen tillater brukerinndata (**Edit**), bare viser data (**View**) eller er deaktivert (**Disabled**).

**[Fill](properties-color-border.md)** – Bakgrunnsfargen på kontrollen.

**[Height](properties-size-location.md)** – Avstanden mellom kontrollens øvre og nedre kant.

**[OnChange](properties-core.md)** – Hvordan appen reagerer når brukeren endrer verdien på en kontroll (ved å for eksempel justere en glidebryter).

**[OnSelect](properties-core.md)** – Hvordan appen responderer når brukeren klikker eller trykker på en kontroll.

**RatingFill** – Fargen på stjerner i en kontroll for vurdering.

**ReadOnly** – Hvorvidt en bruker kan endre verdien til en glidebryter eller vurderingskontroll.

**[Reset](properties-core.md)** – Hvorvidt en kontroll tilbakestilles til standardverdien.

**ShowValue** – Hvorvidt verdien til glidebryteren eller vurderingen vises når en bruker endrer verdien eller holder musepekeren over kontrollen.

**[TabIndex](properties-accessibility.md)** – Tilpasser fanerekkefølgen for kontroller ved kjøretid når den er angitt som en annen verdi enn null.

**[Tooltip](properties-core.md)** – Forklarende tekst som vises når brukeren holder pekeren over en kontroll.

**[Visible](properties-core.md)** – Hvorvidt kontrollen vises eller skjules.

**[Width](properties-size-location.md)** – Avstanden mellom kontrollens venstre og høyre kant.

**[X](properties-size-location.md)** – Avstanden mellom kontrollens venstre kant og den venstre kanten til kontrollens overordnede beholder (eller skjermbilde, hvis det ikke finnes noen overordnet beholder).

**[Y](properties-size-location.md)** – Avstanden mellom kontrollens øvre kant og den øvre kanten til kontrollens overordnede beholder (eller skjermbilde, hvis det ikke finnes noen overordnet beholder).

## <a name="related-functions"></a>Relaterte funksjoner
[**Average**( *Value1*, *Value2,* ... )](../functions/function-aggregates.md)

## <a name="example"></a>Eksempel
1. Legge til en **Vurdering**-kontroll, og gi den navnet **Quantitative**.
   
    Vet du ikke hvordan du [legger til, gir navn til og konfigurerer en kontroll](../add-configure-controls.md)?
2. Legg til en **[Tekstinndata](control-text-input.md)**-kontroll, gi den navnet **Qualitative**, og flytte den under **Vurdering**-kontrollen.
3. Angi **[Default](properties-core.md)**-egenskapen til **[Tekstinndata](control-text-input.md)**-kontrollen som **""**, og angi kontrollens **HintText** som denne formelen:
   <br>**If(Quantitative.Value > 3, "What did you especially like?", "How might we do better?")**
   
    Vil du ha mer informasjon om **[If](../functions/function-if.md)**-funksjonen eller [andre funksjoner](../formula-reference.md)?
4. Trykk på F5, og klikk eller trykk på fire eller fem stjerner i **Vurdering**-kontrollen.
   
    Tipsteksten i **[Tekstinndata](control-text-input.md)**-kontrollen endres slik at den gjenspeiler den høye vurderingen.
5. Klikk eller trykk på færre enn fire stjerner i **Quantitative**.
   
    Tipsteksten i **[Tekstinndata](control-text-input.md)**-kontrollen endres slik at den gjenspeiler den lave vurderingen.
6. Trykk på Esc for å gå tilbake til standardarbeidsområdet.

