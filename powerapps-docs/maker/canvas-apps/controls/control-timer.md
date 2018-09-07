---
title: 'Tidtaker-kontroll: referanse | Microsoft Docs'
description: Informasjon, inkludert egenskaper og eksempler, om tidtaker-kontrollen
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
ms.openlocfilehash: 9497d257372181323a920bd2c1098601021e4f79
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/24/2018
ms.locfileid: "42863671"
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

**AutoStart** – om en lyd- eller videokontroll automatisk begynner å spille av et klipp når brukeren navigerer til skjermen som inneholder denne kontrollen.

**[BorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje.

**[BorderStyle](properties-color-border.md)** – om kontrollens kantlinje er satt til **Heltrukket**, **Stiplet**, **Prikket** eller **Ingen**.

**[BorderThickness](properties-color-border.md)** – tykkelsen til kontrollens kantlinje.

**[Farge](properties-color-border.md)** – fargen på teksten i kontrollen.

**[DisplayMode](properties-core.md)** – om kontrollen tillater brukerinndata (**Rediger**), bare viser data (**Vis**) eller er deaktivert (**Deaktivert**).

**[DisabledBorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje hvis kontrollens **[DisplayMode](properties-core.md)**-egenskap er angitt til **Deaktivert**.

**[DisabledColor](properties-color-border.md)** – fargen på kontrollens tekst hvis kontrollens **[DisplayMode](properties-core.md)**-egenskap er angitt som **Deaktivert**.

**[DisabledFill](properties-color-border.md)** – bakgrunnsfargen på en kontroll hvis **[DisplayMode](properties-core.md)**-egenskapen er angitt som **Deaktivert**.

**[Fyll](properties-color-border.md)** – bakgrunnsfargen på kontrollen.

**[FocusedBorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje når kontrollen er fokusert.

**[FocusedBorderThickness](properties-color-border.md)** – fargen på kontrollens kantlinje når kontrollen er fokusert.

**[Skrift](properties-text.md)** – navnet på skriftserien som teksten vises i.

**[FontWeight](properties-text.md)** – tykkelsen på teksten i en kontroll: **Fet**, **Halvfet**, **Normal** eller **Lysere**.

**[Høyde](properties-size-location.md)** – avstanden mellom kontrollens øvre og nedre kant.

**[HoverBorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje når brukeren holder musepekeren på denne kontrollen.

**[HoverColor](properties-color-border.md)** – Fargen på teksten i en kontroll når brukeren holder musepekeren over den.

**[HoverFill](properties-color-border.md)** – bakgrunnsfargen for en kontroll når brukeren holder musepekeren over den.

**[Italic](properties-text.md)** – om teksten i en kontroll er kursiv.

**[OnSelect](properties-core.md)** – hvordan appen reagerer når brukeren klikker eller trykker på en kontroll.

**OnTimerStart** – hvordan en app reagerer når en tidtaker begynner å kjøre.

**[PressedBorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje når brukeren trykker eller klikker på kontrollen.

**[PressedColor](properties-color-border.md)** – fargen på teksten i en kontroll når brukeren trykker eller klikker på kontrollen.

**[PressedFill](properties-color-border.md)** – bakgrunnsfargen på teksten i en kontroll når brukeren trykker eller klikker på kontrollen.

**[Tilbakestill](properties-core.md)** – om en kontroll tilbakestilles til standardverdien.

**[Size](properties-text.md)** – skriftstørrelsen på teksten som vises på en kontroll.

**Start** – om et lyd- eller videoklipp spilles av.

**[Strikethrough](properties-text.md)** – om det vises en linje gjennom teksten som vises på en kontroll.

**[TabIndex](properties-accessibility.md)** – navigasjonsrekkefølge for tastatur i forhold til andre kontroller.

**[Text](properties-core.md)**  – Tekst som vises på en kontroll eller som brukeren skriver inn i en kontroll.

**[Verktøytips](properties-core.md)** – forklarende tekst, som vises når brukeren holder pekeren over en kontroll.

**[Underline](properties-text.md)** – om det vises en linje under teksten som vises på en kontroll.

**[Synlig](properties-core.md)** – om kontrollen vises eller skjules.

**[Bredde](properties-size-location.md)** – avstanden mellom kontrollens venstre og høyre kant.

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

### <a name="animate-a-control"></a>Å animere en kontroll
1. Legg til en tidtaker, og gi den navnet **Varselinntoning**.

    Vet du ikke hvordan du [legger til, gir navn til og konfigurerer en kontroll](../add-configure-controls.md)?
2. Angi tidtakerens **varighet** til **5000**, **Gjenta**-egenskapen til **sann** og **[Tekst](properties-core.md)**-egenskapen til **Veksle animasjon**.
3. (valgfritt) Gjør det enklere å lese av tidtakeren ved å angi **[Høyde](properties-size-location.md)**-egenskapen for tidtakeren til **160**, **[Bredde](properties-size-location.md)**-egenskapen til **600**, og **[Størrelse](properties-text.md)**-egenskapen til **60**.
4. Legg til en etikett, og sett **[Tekst](properties-core.md)**-egenskapen til å vise **Velkommen!** og angi **[farge](properties-color-border.md)**-egenskapen til denne formelen:
   <br>**ColorFade(Color.BlueViolet, FadeIn.Value/5000)**

    Vil du ha mer informasjon om **[ColorFade](../functions/function-colors.md)**-funksjonen eller [andre funksjoner](../formula-reference.md)?

5. Velg at knappen for tidtakeren skal starte eller stoppe animasjonen. Teksten i etiketten tones til hvit, returnerer til full intensitet og gjentar prosessen.


## <a name="accessibility-guidelines"></a>Retningslinjer for tilgjengelighet
De samme retningslinjene for **[Knapp](control-button.md)** gjelder, fordi **Tidtaker** er bare en spesialknapp.

> [!IMPORTANT]
> Å kontrollere **tidtakeren** uten direkte brukermedvirkning er ikke støttet for tilgjengelighet. En tidtaker kan eksempelvis skjules visuelt ved å plassere andre kontroller ovenfor eller sette **[Synlig](properties-core.md)**-egenskapen til **usann**. Tidtakeren starter automatisk når en skjerm vises, og etter en stund utfører den noen handlinger automatisk. Det er for øyeblikket ingen generell måte å gjøre dette scenarioet tilgjengelig på.

Andre retningslinjer for tilgjengelighet er som følger.

### <a name="timing"></a>Tidsberegning
Hvis en **tidtaker** er startet eller stoppet automatisk, bør du overveie hvorvidt brukerne har tilstrekkelig med tid til å lese og bruke innholdet. Brukere av tastatur og skjermleser kan trenge mer tid til å respondere på en planlagt hendelse.

Alle disse strategiene vil fungere:
* Tillat brukere å avbryte den planlagte hendelsen
* Tillat brukere å justere tidsbegrensningen før den begynner
* Advar 20 sekunder før tidsgrensen utløper, og tilby en fremgangsmåte for å utvide grensen på en enkel måte

Noen scenarioer er fritatt fra disse kravene. Finn ut mer i [WCAG 2.0-retningslinjen for tidsbegrensninger](https://www.w3.org/TR/WCAG20/#time-limits).

### <a name="screen-reader-support"></a>Kundestøtte for skjermlesere
* **[Tekst](properties-core.md)** må foreligge.
* Ikke bruk **[Tekst](properties-core.md)** for tidssensitiv og viktig informasjon. Brukere av skjermleseren vil ikke bli varslet om endringer i **[Tekst](properties-core.md)**.

    > [!NOTE]
  > Skjermlesere leser opp hvor lang tid som er brukt hvert 5. sekund. Tidtakeren **[Tekst](properties-core.md)** vil imidlertid ikke bli inkludert i opplesingen.

* Vurder å legge til en **[Etikett](control-text-box.md)** for å vise hvor lang tid som er brukt. Bruk tidtakerens **[Tekst](properties-core.md)** for å instruere brukeren om å starte eller stoppe tidtakeren.
