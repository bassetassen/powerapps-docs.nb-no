---
title: 'Vekslekontroll: referanse | Microsoft Docs'
description: Informasjon, inkludert egenskaper og eksempler, om vekslekontrollen
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
ms.openlocfilehash: dac1f8ea99746f04d2d3305e279a4bc5faf67903
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/22/2018
ms.locfileid: "30996337"
---
# <a name="toggle-control-in-powerapps"></a>Vekslekontrollen i PowerApps
En kontroll som brukeren kan slå på eller av ved å flytte håndtaket.

## <a name="description"></a>Beskrivelse
En veksleknapp er utformet for nylige GUI-er, men det fungerer på samme måte som en avmerkingsboks.

## <a name="key-properties"></a>Nøkkelegenskaper
**[Standard](properties-core.md)** – startverdien for en kontroll før den er endret av brukeren.

**[Verdi](properties-core.md)** – verdien til en inndatakontroll.

## <a name="additional-properties"></a>Tilleggsegenskaper
**[BorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje.

**[BorderStyle](properties-color-border.md)** – om kontrollens kantlinje er satt til **Heltrukket**, **Stiplet**, **Prikket** eller **Ingen**.

**[BorderThickness](properties-color-border.md)** – tykkelsen til kontrollens kantlinje.

**[FocusedBorderThickness](properties-color-border.md)**  – tykkelsen på kontrollens kantlinje når den har tastaturfokus.

**[DisplayMode](properties-core.md)** – om kontrollen tillater brukerinndata (**Rediger**), bare viser data (**Vis**) eller er deaktivert (**Deaktivert**).

**[DisabledBorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje hvis kontrollens **[DisplayMode](properties-core.md)**-egenskap er angitt til **Deaktivert**.

**FalseFill** – aktiver/deaktiver fyllfargen når veksleknappen er slått av.

**FalseHoverFill** – aktiver/deaktiver pekerfølsomheten for fyllfargen når veksleknappen er slått av.

**FalseText** – teksten som vises når veksleknappen er deaktivert.

**[Fyll](properties-color-border.md)** – bakgrunnsfargen på kontrollen.

**[Høyde](properties-size-location.md)** – avstanden mellom kontrollerens øvre og nedre kant.

**[HoverBorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje når brukeren holder musepekeren på denne kontrollen.

**[OnChange](properties-core.md)** – hvordan appen reagerer når brukeren endrer verdien på en kontroll (ved å for eksempel justere en glidebryter).

**OnCheck** – hvordan en app reagerer når verdien til en avmerkingsboks eller en veksleknapp endres til **sann**.

**[OnSelect](properties-core.md)** – hvordan appen reagerer når brukeren klikker eller trykker på en kontroll.

**OnUncheck** – hvordan en app reagerer når verdien til en avmerkingsboks eller en veksleknapp endres til **usann**.

**[PressedBorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje når brukeren trykker eller klikker på kontrollen.

**RailFill** – bakgrunnsfargen for rektangelet i vekslekontrollen når verdien er **usann**, eller fargen på linjen til høyre i håndtaket i en glidebryter.

**RailHoverFill** – når du holder musepekeren over en vekslekontroll eller glidebryter, bakgrunnsfargen for rektangelet i en vekslekontroll når verdien er **usann** eller fargen på linjen til høyre for håndtaket i en glidebryter.

**[Tilbakestill](properties-core.md)** – om en kontroll tilbakestilles til standardverdien.

**ShowLabel** – om en tekstetikett vises ved siden av vekslekontrollen.

**[TabIndex](properties-accessibility.md)** – tilpasser fanerekkefølgen for kontroller ved kjøretid når den er angitt som en annen verdi enn null.

**TextPosition** – om etiketten er til venstre eller høyre for vekslekontrollen.

**[Verktøytips](properties-core.md)** – forklarende tekst som vises når brukeren holder pekeren over en kontroll.

**TrueFill** – aktiver/deaktiver fyllfarge når veksleknappen er aktivert.

**TrueHoverFill** – aktiver/deaktiver pekerfølsomheten for fyllfarge når veksleknappen er slått på.

**TrueText** – teksten som vises når veksleknappen er aktivert.

**ValueFill** – bakgrunnsfargen for rektangelet i vekslekontrollen når verdien er **sann**, eller fargen på linjen til venstre for håndtaket i en glidebryter.

**ValueHoverFill** – når du holder musepekeren over en vekslekontroll eller en glidebryter, bakgrunnsfargen for rektangelet i en vekslekontroll når verdien er **sann** eller fargen på linjen til venstre for håndtaket i en glidebryter.

**[Synlig](properties-core.md)** – om kontrollen vises eller skjules.

**[Bredde](properties-size-location.md)** – avstanden mellom venstrekanten og høyrekanten til en kontroll.

**[X](properties-size-location.md)** – avstanden mellom kontrollens venstre kant og den venstre kanten til kontrollens overordnede beholder (eller skjermen, hvis det ikke finnes noen overordnet beholder).

**[Y](properties-size-location.md)** – avstanden mellom kontrollens øvre kant og den øvre kanten til kontrollens overordnede beholder (eller skjermen, hvis det ikke finnes noen overordnet beholder).

## <a name="related-functions"></a>Relaterte funksjoner
[**Hvis**( *Betingelse*, *Resultat* )](../functions/function-if.md)

## <a name="example"></a>Eksempel
1. Legg til en veksleknapp, og gi den navnet **MemberDiscount**.

    Vet du ikke hvordan du [legger til, gir navn til og konfigurerer en kontroll](../add-configure-controls.md)?
2. Legg til en etikett og angi **[Tekst](properties-core.md)**-egenskapen til denne formelen:
   <br>**Hvis (MemberDiscount.Value = sann, «pris: USD 75», «pris: USD 100»)**

    Vil du ha mer informasjon om **[Hvis](../functions/function-if.md)**-funksjonen eller [andre funksjoner](../formula-reference.md)?
3. Trykk på F5, og endre verdien for **MemberDiscount**.

    Etiketten viser en annen pris, avhengig av om **MemberDiscount** er aktivert eller deaktivert.
4. Trykk på ESC for å gå tilbake til standardarbeidsområdet.
