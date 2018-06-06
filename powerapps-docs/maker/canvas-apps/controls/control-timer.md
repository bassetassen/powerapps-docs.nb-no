---
title: 'Tidtaker-kontroll: referanse | Microsoft Docs'
description: Informasjon, inkludert egenskaper og eksempler, om tidtaker-kontrollen
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
ms.openlocfilehash: 008c992ad3452c1844064335a51593c222fb1ac1
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/22/2018
ms.locfileid: "30996252"
---
# <a name="timer-control-in-powerapps"></a>Tidtaker-kontrollen i PowerApps
En kontroll som kan finne ut hvordan appen responderer etter en viss tid har passert.

## <a name="description"></a>Beskrivelse
Tidtakere kan for eksempel bestemme hvor lenge en kontroll skal vises, eller endre andre egenskaper for en kontroll etter en viss tid har passert.

Vær oppmerksom på at du må forhåndsvise appen for at tidtakeren kan kjøre i utformeren.  Dette gjør at brukeren kan konfigurere tidtakeren i utformeren uten tidsbegrensninger.

## <a name="key-properties"></a>Nøkkelegenskaper
**Varighet** – hvor lenge en tidtaker kjører i millisekunder.  Det finnes ingen maksimumsverdi.

**OnTimerEnd** – hvordan en app svarer når en tidtaker har kjørt ferdig.

**Gjenta** – om en tidtaker automatisk starter på nytt når den har kjørt ferdig.

## <a name="additional-properties"></a>Tilleggsegenskaper
**[Align](properties-text.md)** – plasseringen av teksten i forhold til den vannrette midten av kontrollen.

**Autopause** – om et lyd- eller videoklipp pauser automatisk hvis brukeren navigerer til en annen skjerm.

**Autostart** – om en lyd- eller videokontroll automatisk begynner å spille av et klipp når brukeren navigerer til skjermen som inneholder denne kontrollen.

**[BorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje.

**[BorderStyle](properties-color-border.md)** – om kontrollens kantlinje er **Heltrukket**, **Stiplet**, **Prikket** eller **Ingen**.

**[BorderThickness](properties-color-border.md)** – tykkelsen til kontrollens kantlinje.

**[Color](properties-color-border.md)**  – fargen på teksten i kontrollen.

**[DisplayMode](properties-core.md)** – om kontrollen tillater brukerinndata (**Edit**), bare viser data (**View**) eller er deaktivert (**Disabled**).

**[DisabledBorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje hvis kontrollens **[DisplayMode](properties-core.md)**-egenskap er angitt som **Disabled**.

**[DisabledColor](properties-color-border.md)** – fargen på kontrollens kantlinje hvis kontrollens **[DisplayMode](properties-core.md)**-egenskap er angitt som **Disabled**.

**[DisabledFill](properties-color-border.md)** – bakgrunnsfargen på en kontroll hvis **[DisplayMode](properties-core.md)**-egenskapen er angitt som **Deaktivert**.

**[Fill](properties-color-border.md)** – Bakgrunnsfargen på kontrollen.

**[Font](properties-text.md)**  – navnet på skriftserien som teksten vises i.

**[FontWeight](properties-text.md)** – tykkelsen på teksten i en kontroll: **Fet**, **Halvfet**, **Normal** eller **Lysere**.

**[Height](properties-size-location.md)** – avstanden mellom kontrollens øvre og nedre kant.

**[HoverBorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje når brukeren holder musepekeren på denne kontrollen.

**[HoverColor](properties-color-border.md)** – fargen på en tekst i en kontroll når brukeren holder musepekeren på den.

**[HoverFill](properties-color-border.md)**  – bakgrunnsfargen for en kontroll når brukeren holder musepekeren på den.

**[Italic](properties-text.md)** – om teksten i en kontroll er kursiv.

**[OnSelect](properties-core.md)** – hvordan appen reagerer når brukeren klikker eller trykker på en kontroll.

**OnTimerStart** – hvordan en app reagerer når en tidtaker begynner å kjøre.

**[PressedBorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje når brukeren trykker eller klikker på kontrollen.

**[PressedColor](properties-color-border.md)** – fargen på teksten i en kontroll når brukeren trykker eller klikker på kontrollen.

**[PressedFill](properties-color-border.md)** – bakgrunnsfargen i en kontroll når brukeren trykker eller klikker på kontrollen.

**[Tilbakestill](properties-core.md)** – om en kontroll tilbakestilles til standardverdien.

**[Size](properties-text.md)** – skriftstørrelsen på teksten som vises på en kontroll.

**Start** – om et lyd- eller videoklipp spilles av.

**[Strikethrough](properties-text.md)** – om det vises en linje gjennom teksten som vises på en kontroll.

**[Text](properties-core.md)** – tekst som vises på en kontroll, eller som brukeren skriver inn i en kontroll.

**[Verktøytips](properties-core.md)** – forklarende tekst, som vises når brukeren holder pekeren over en kontroll.

**[Underline](properties-text.md)** – om det vises en linje under teksten som vises på en kontroll.

**[Visible](properties-core.md)** – om kontrollen vises eller skjules.

**[Width](properties-size-location.md)** – avstanden mellom venstrekanten og høyrekanten på en kontroll.

**[X](properties-size-location.md)** – avstanden mellom kontrollens venstre kant og den venstre kanten til kontrollens overordnede beholder (eller skjermen, hvis det ikke finnes noen overordnet beholder).

**[Y](properties-size-location.md)** – avstanden mellom kontrollens øvre kant og den øvre kanten til kontrollens overordnede beholder (eller skjermen, hvis det ikke finnes noen overordnet beholder).

## <a name="related-functions"></a>Relaterte funksjoner
[**Oppdater**(*DataSource*)](../functions/function-refresh.md)

## <a name="examples"></a>Eksempler
### <a name="show-a-countdown"></a>Vis en nedtelling
1. Legg til en tidtaker og gi den navnet **Nedtelling**.

    Vet du ikke hvordan du [legger til, gir navn til og konfigurerer en kontroll](../add-configure-controls.md)?
2. Angi tidtakerens **Varighet**-egenskap til **10000**, og **Gjenta**- og **Autostart**-egenskapene til **sann**.
3. (valgfritt) Gjør det enklere å lese av tidtakeren ved å angi **[Høyde](properties-size-location.md)**-egenskapen for tidtakeren til **160**, **[Bredde](properties-size-location.md)**-egenskapen til **600**, og **[Størrelse](properties-text.md)**-egenskapen til **60**.
4. Legg til en etikett og angi **[Tekst](properties-core.md)**-egenskapen til denne formelen:
   <br>**"Number of seconds remaining: " & RoundUp(10-Countdown.Value/1000, 0)**

    Vil du ha mer informasjon om **[RoundUp](../functions/function-round.md)**-funksjonen, eller [andre funksjoner](../formula-reference.md)?

    Etiketten viser hvor mange sekunder som gjenstår før tidtakeren startes på nytt.
5. (valgfritt) Angi tidtakerens **[Synlig](properties-core.md)**-egenskap til **usann**.

### <a name="animate-a-control"></a>Å animere en kontroll
1. Legg til en tidtaker, og gi den navnet **Varselinntoning**.

    Vet du ikke hvordan du [legger til, gir navn til og konfigurerer en kontroll](../add-configure-controls.md)?
2. Angi tidtakerens **Varighet**-egenskap til **5000**, og **Gjenta**- og **Autostart**-egenskapene til **sann**.
3. (valgfritt) Gjør det enklere å lese av tidtakeren ved å angi **[Høyde](properties-size-location.md)**-egenskapen for tidtakeren til **160**, **[Bredde](properties-size-location.md)**-egenskapen til **600**, og **[Størrelse](properties-text.md)**-egenskapen til **60**.
4. Legg til en etikett, og sett **[Tekst](properties-core.md)**-egenskapen til å vise **Velkommen!** og angi **[farge](properties-color-border.md)**-egenskapen til denne formelen:
   <br>**ColorFade(Color.BlueViolet, FadeIn.Value/5000)**

    Vil du ha mer informasjon om **[ColorFade](../functions/function-colors.md)**-funksjonen eller [andre funksjoner](../formula-reference.md)?

    Teksten i etiketten tones til hvit, returnerer til full intensitet og gjentar prosessen.
5. (valgfritt) Angi tidtakerens **[Synlig](properties-core.md)**-egenskap til **usann**.
