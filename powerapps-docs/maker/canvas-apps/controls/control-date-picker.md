---
title: 'Datovelger-kontrollen: referanse | Microsoft Docs'
description: Informasjon, inkludert egenskaper og eksempler, om Datovelger-kontrollen
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
ms.openlocfilehash: 90f18c4b490564bc098046831ea932db13fce05d
ms.sourcegitcommit: 4ed29d83e90a2ecbb2f5e9ec5578e47a293a55ab
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/23/2019
ms.locfileid: "63321711"
ms.PowerAppsDecimalTransform: true
---
# <a name="date-picker-control-in-powerapps"></a>Datovelger-kontrollen i PowerApps
En kontroll som brukeren kan klikke eller trykk på for å angi en dato.

## <a name="description"></a>Beskrivelse
Hvis du legger til en **Datovelger**-kontroll i stedet for en **[Tekstinndata](control-text-input.md)**-kontroll, kan du forsikre deg om at brukeren angir en dato i riktig format.

## <a name="key-properties"></a>Nøkkelegenskaper
**DefaultDate** – startverdien for en datokontroll, med mindre brukeren endrer den.

**SelectedDate** – datoen som er nå er valgt i en datokontroll.

**Format** – tekstformatet som kontrollen viser datoen i og brukeren angir datoen i. Du kan angi denne egenskapen som **ShortDate** (standard) eller **LongDate** for å formatere datoer basert på **Språk**-egenskapen til denne kontrollen. Du kan også angi denne egenskapen som et uttrykk, for eksempel **yyyy/mm/dd** hvis du vil bruke samme format, uansett språk. For eksempel:

* Kontrollen viser **12/31/2017** hvis brukeren klikker på den siste dagen i 2017, **Format**-egenskapen er angitt som **ShortDate** og **Språk**-egenskapen er angitt som **en-us**.
* Kontrollen viser **dimanche 31 decembre 2017** hvis brukeren klikker eller trykker på den siste dagen i 2017, **Format**-egenskapen er angitt som **LongDate** og **Språk**-egenskapen er angitt som **fr-fr**.

**Språk** – angir språket som brukes til å formatere datoer, inklusive navnet på månedene. Hvis denne egenskapen ikke er angitt, bestemmes språket av brukerens enhetsinnstillinger.

## <a name="additional-properties"></a>Tilleggsegenskaper
**[AccessibleLabel](properties-accessibility.md)** – etikett for skjermlesere.

**[BorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje.

**[BorderStyle](properties-color-border.md)** – om kontrollens kantlinje er satt til **Heltrukket**, **Stiplet**, **Prikket** eller **Ingen**.

**[BorderThickness](properties-color-border.md)** – tykkelsen til kontrollens kantlinje.

**[Farge](properties-color-border.md)** – fargen på teksten i kontrollen.

**[DisplayMode](properties-core.md)** – om kontrollen tillater brukerinndata (Rediger), viser kun data (Vis) eller er deaktivert (Deaktivert).

**[DisabledBorderColor](properties-color-border.md)**  – fargen på kontrollens kantlinje hvis kontrollens **[DisplayMode](properties-core.md)**-egenskapen er angitt som **Deaktivert**.

**[DisabledColor](properties-color-border.md)** – fargen på kontrollens tekst hvis kontrollens **[DisplayMode](properties-core.md)**-egenskap er angitt som **Deaktivert**.

**[DisabledFill](properties-color-border.md)** – bakgrunnsfargen på en kontroll hvis **[DisplayMode](properties-core.md)**-egenskapen er angitt som **Deaktivert**.

**EndYear** – det siste året som brukeren kan angi verdien for i en datovelger-kontroll.

**[Fyll](properties-color-border.md)** – bakgrunnsfargen på kontrollen.

**[FocusedBorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje når kontrollen er fokusert.

**[FocusedBorderThickness](properties-color-border.md)** – fargen på kontrollens kantlinje når kontrollen er fokusert.

**[Skrift](properties-text.md)** – navnet på skriftserien som teksten vises i.

**[FontWeight](properties-text.md)**  – vekten på teksten i en kontroll: **Fet**, **Halvfet**, **Normal**, eller **lysere**.

**[Høyde](properties-size-location.md)** – avstanden mellom kontrollens øvre og nedre kant.

**IconFill** – forgrunnsfargen til datovelgerikonet.

**IconBackground** – bakgrunnsfargen til datovelgerikonet.

**[Kursiv](properties-text.md)** – om teksten i en kontroll er i kursiv.

**[OnSelect](properties-core.md)** – hvordan appen reagerer når brukeren klikker eller trykker på en kontroll.

**[PaddingBottom](properties-size-location.md)** – avstanden mellom teksten i en kontroll og den nederste kanten av kontrollen.

**[PaddingLeft](properties-size-location.md)** – avstanden mellom teksten i en kontroll og den venstre kanten av kontrollen.

**[PaddingRight](properties-size-location.md)** – avstanden mellom teksten i en kontroll og den høyre kanten av kontrollen.

**[PaddingTop](properties-size-location.md)** – avstanden mellom teksten i en kontroll og den øverste kanten av kontrollen.

**[Størrelse](properties-text.md)** – skriftstørrelsen på teksten som vises på en kontroll.

**StartYear** – det første året som brukeren kan angi verdien for i en datovelger-kontroll.

**[TabIndex](properties-accessibility.md)** – navigasjonsrekkefølge for tastatur i forhold til andre kontroller.

**[Synlig](properties-core.md)** – om kontrollen vises eller skjules.

**[Bredde](properties-size-location.md)** – avstanden mellom kontrollens venstre og høyre kant.

**[X](properties-size-location.md)** – avstanden mellom kontrollens venstre kant og den venstre kanten til kontrollens overordnede beholder (eller skjermen, hvis det ikke finnes noen overordnet beholder).

**[Y](properties-size-location.md)** – avstanden mellom kontrollens øvre kant og den øvre kanten til kontrollens overordnede beholder (eller skjermen, hvis det ikke finnes noen overordnet beholder).

## <a name="related-functions"></a>Relaterte funksjoner
**[Year](../functions/function-datetime-parts.md)**( *DateTimeValue* )

## <a name="example"></a>Eksempel
1. Legg til en **Datovelger**-kontroll, og gi den navnet **Deadline**.

    Vet du ikke hvordan du [legger til, gir navn til og konfigurerer en kontroll](../add-configure-controls.md)?
2. Legg til en **[Etikett](control-text-box.md)**-kontroll, og angi **[Tekst](properties-core.md)**-egenskapen som denne formelen:
   <br>**DateDiff(Today(); Deadline.SelectedDate) & " days to go!"**

    Vil du ha mer informasjon om **[DateDiff](../functions/function-dateadd-datediff.md)**-funksjonen eller [andre funksjoner](../formula-reference.md)?
3. Trykk på F5, velg en dato i **Deadline**, og klikk eller trykk på **OK**.

    **[Etikett](control-text-box.md)**-kontrollen viser antall dager mellom dagens dato og datoen du valgte.
4. Trykk på ESC for å gå tilbake til standardarbeidsområdet.


## <a name="accessibility-guidelines"></a>Retningslinjer for tilgjengelighet
### <a name="color-contrast"></a>Fargekontrast
* [Standardkrav for fargekontrast](../accessible-apps-color.md) gjelder.

### <a name="screen-reader-support"></a>Kundestøtte for skjermlesere
* **[AccessibleLabel](properties-accessibility.md)** bør vises.

### <a name="keyboard-support"></a>Tastaturstøtte
* **[TabIndex](properties-accessibility.md)** må være null eller større, slik at tastaturbrukere kan navigere til den.
* Fokusindikatorer må være godt synlige. Bruk **[FocusedBorderColor](properties-color-border.md)** og **[FocusedBorderThickness](properties-color-border.md)** for å oppnå dette.

> [!TIP]
> Når kalenderen er åpen, trykker du **siden opp** og **PgDn** til å navigere mellom måneder og **SKIFT + PGUP** og **SKIFT + PGDN** til navigere mellom år.
