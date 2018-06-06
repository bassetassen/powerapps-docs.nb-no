---
title: 'Tekstinndata-kontrollen: referanse | Microsoft Docs'
description: Informasjon om tekstinndata-kontrollen, inkludert egenskaper og eksempler
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
ms.openlocfilehash: 4082034d843765025bb6e40cab83705582417d51
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/22/2018
ms.locfileid: "30997117"
---
# <a name="text-input-control-in-powerapps"></a>Tekstinndata-kontrollen i PowerApps
En boks som brukeren kan skrive inn tekst, tall og andre data i.

## <a name="description"></a>Beskrivelse
Brukeren kan angi data ved å skrive inn i en kontroll for tekstinndata. Avhengig av hvordan du konfigurerer appen, blir dataene kanskje lagt til i en datakilde, brukt til å beregne en midlertidig verdi eller tatt med på en annen måte.

## <a name="key-properties"></a>Nøkkelegenskaper
**[Default](properties-core.md)** – startverdien for en kontroll før den er endret av brukeren.

**[Text](properties-core.md)**  – tekst som vises på en kontroll, eller som brukeren skriver inn i en kontroll.

## <a name="additional-properties"></a>Tilleggsegenskaper
**[Align](properties-text.md)**  – plasseringen av teksten i forhold til den vannrette midten av kontrollen.

**[BorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje.

**[BorderStyle](properties-color-border.md)** – om kontrollens kantlinje er **Heltrukket**, **Stiplet**, **Prikket** eller **Ingen**.

**[BorderThickness](properties-color-border.md)** – tykkelsen til kontrollens kantlinje.

**[FocusedBorderThickness](properties-color-border.md)**  – tykkelsen på kontrollens kantlinje når den har tastaturfokus.

**Fjern** – om en tekstinndata-kontroll viser en X som brukeren kan berøre eller klikke på for å fjerne innholdet i den aktuelle kontrollen.

**[Color](properties-color-border.md)** – fargen på teksten i en kontroll.

**DelayOutput** – når den er satt til sann, blir brukerinndata registrert etter et halvt sekunds forsinkelse.  Nyttig for å forsinke dyre operasjoner inntil brukeren fullfører innsetting av tekst (det vil si for filtrering når inndata brukes i andre formler).

**[DisplayMode](properties-core.md)** – om kontrollen tillater brukerinndata (**Edit**), bare viser data (**View**) eller er deaktivert (**Disabled**).

**[DisabledBorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje hvis kontrollens **[DisplayMode](properties-core.md)**-egenskap er angitt som **Disabled**.

**[DisabledColor](properties-color-border.md)** – fargen på kontrollens tekst hvis kontrollens **[DisplayMode](properties-core.md)**-egenskap er angitt som **Deaktivert**.

**[DisabledFill](properties-color-border.md)** – bakgrunnsfargen på en kontroll hvis **[DisplayMode](properties-core.md)**-egenskapen er angitt som **Deaktivert**.

**[Fill](properties-color-border.md)** – bakgrunnsfargen på kontrollen.

**[Font](properties-text.md)**  – navnet på skriftserien som teksten vises i.

**[FontWeight](properties-text.md)**  – tykkelsen på teksten i en kontroll: **Fet**, **Halvfet**, **Normal** eller **Lysere**.

**Format** – om brukerinndataene er begrenset til bare tall eller kan være en hvilken som helst tekst.

**[Height](properties-size-location.md)** – avstanden mellom kontrollens øvre og nedre kant.

**HintText** – lys grå tekst som vises i en tekstinndata-kontroll hvis den er tom.

**[HoverBorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje når brukeren holder musepekeren på denne kontrollen.

**[HoverColor](properties-color-border.md)** – fargen på en teksten i en kontroll når brukeren holder musepekeren over den.

**[HoverFill](properties-color-border.md)**  – bakgrunnsfargen for en kontroll når brukeren holder musepekeren over den.

**[Italic](properties-text.md)** – om teksten i en kontroll er i kursiv.

**[LineHeight](properties-text.md)** – avstanden mellom, for eksempel, linjer med tekst eller elementer i en liste.

**MaxLength** – antall tegn som brukeren kan skrive inn i en kontroll for tekstinndata.

**Mode** – kontrollen er i modus for **SingleLine**, **MultiLine** eller **Password**.

**[OnChange](properties-core.md)** – hvordan appen reagerer når brukeren endrer verdien på en kontroll (ved å for eksempel justere en glidebryter).

**[OnSelect](properties-core.md)** – hvordan appen reagerer når brukeren klikker eller trykker på en kontroll.

**[PaddingBottom](properties-size-location.md)** – avstanden mellom teksten i en kontroll og den nederste kanten av kontrollen.

**[PaddingLeft](properties-size-location.md)** – avstanden mellom teksten i en kontroll og den venstre kanten av kontrollen.

**[PaddingRight](properties-size-location.md)** – avstanden mellom teksten i en kontroll og den høyre kanten av kontrollen.

**[PaddingTop](properties-size-location.md)** – avstanden mellom teksten i en kontroll og den øverste kanten av kontrollen.

**[PressedBorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje når brukeren trykker eller klikker på kontrollen.

**[PressedColor](properties-color-border.md)** – fargen på teksten i en kontroll når brukeren trykker eller klikker på kontrollen.

**[PressedFill](properties-color-border.md)** – bakgrunnsfargen i en kontroll når brukeren trykker eller klikker på kontrollen.

**[RadiusBottomLeft](properties-size-location.md)** – i hvilken grad hjørnet nederst til venstre i en kontroll avrundes.

**[RadiusBottomRight](properties-size-location.md)**  – i hvilken grad hjørnet nederst til høyre i en kontroll avrundes.

**[RadiusTopLeft](properties-size-location.md)** – i hvilken grad hjørnet øverst til venstre i en kontroll avrundes.

**[RadiusTopRight](properties-size-location.md)** – i hvilken grad hjørnet øverst til høyre av en kontroll avrundes.

**[Reset](properties-core.md)** – om en kontroll tilbakestilles til standardverdien.

**[Size](properties-text.md)** – skriftstørrelsen på teksten som vises på en kontroll.

**[Strikethrough](properties-text.md)** – om det vises en linje gjennom teksten som vises på en kontroll.

**[TabIndex](properties-accessibility.md)** – tilpasser kategorirekkefølgen ved kjøretid når den ikke er angitt som null.

**[Tooltip](properties-core.md)** – forklarende tekst som vises når brukeren holder pekeren over en kontroll.

**[Underline](properties-text.md)** – om det vises en linje under teksten som vises på en kontroll.

**[Visible](properties-core.md)** – om kontrollen vises eller skjules.

**[Width](properties-size-location.md)** – avstanden mellom venstrekanten og høyrekanten til en kontroll.

**[X](properties-size-location.md)** – avstanden mellom kontrollens venstre kant og den venstre kanten til kontrollens overordnede beholder (eller skjermen, hvis det ikke finnes noen overordnet beholder).

**[Y](properties-size-location.md)** – avstanden mellom kontrollens øvre kant og den øvre kanten til kontrollens overordnede beholder (eller skjermen, hvis det ikke finnes noen overordnet beholder).

## <a name="related-functions"></a>Relaterte funksjoner
[**DateTimeValue**( *String* )](../functions/function-datevalue-timevalue.md)

## <a name="examples"></a>Eksempler
### <a name="collect-data"></a>Samle inn data
1. Legg til to kontroller for tekstinndata, og gi dem navnene **inputFirst** og **inputLast**.
   
    Vet du ikke hvordan du [legger til, gir navn til og konfigurerer en kontroll](../add-configure-controls.md)?
2. Legg til en knapp, angi **[Text](properties-core.md)**-egenskapen til **Legg til**, og angi **[OnSelect](properties-core.md)**-egenskapen til denne formelen:<br>
   **Collect(Names, {FirstName:inputFirst.Text, LastName:inputLast.Text})**
   
    Vil du ha mer informasjon om **[Collect](../functions/function-clear-collect-clearcollect.md)**-funksjonen eller [andre funksjoner](../formula-reference.md)?
3. Legg til et tekstgalleri i stående/loddrett retning, angi **[Items](properties-core.md)** til **Navn**, og angi **[Text](properties-core.md)**-egenskapen til **Subtitle1** til **ThisItem.FirstName**.
4. (valgfritt) I malgalleriet sletter du den nederste etiketten, kalt **Body1**, og angir **[TemplateSize](control-gallery.md)**-egenskapen for galleriet til **80**.
5. Trykk på F5, skriv inn en tekststreng til **inputFirst** og **inputLast**, og klikk eller trykk deretter på **Legg til**-knappen.
6. (valgfritt) Legg til flere navn i samlingen, og trykk deretter på ESC for å gå tilbake til standardarbeidsområdet.

### <a name="prompt-for-a-password"></a>Be om et passord
1. Legg til en kontroll for inndatatekst, gi den navnet **inputPassword**, og angi **Modus**-egenskapen til **Password**.
2. Legg til en etikett, og angi **[Text](properties-core.md)**-egenskapen til denne formelen:<br>
   **If(inputPassword.Text = "P@ssw0rd", "Access granted", "Access denied")**
   
    Vil du ha mer informasjon om **[Hvis](../functions/function-if.md)**-funksjonen eller [andre funksjoner](../formula-reference.md)?
3. Trykk på F5, og skriv deretter **P@ssw0rd** i **inputPassword**.
   
    Når du er ferdig å skrive inn passordet, viser ikke etiketten meldingen **Ingen tilgang** lenger. Den viser deretter **Tilgang innvilget**.
4. Trykk på Esc for å gå tilbake til standardarbeidsområdet.
5. (valgfritt) Legg til en kontroll, for eksempel en pil, konfigurer den til å navigere til en annen skjerm, og vis den bare etter at brukeren skriver inn passordet.
6. (valgfritt) Legg til en knapp, konfigurer **[Text](properties-core.md)**-egenskapen til å vise **Logg på**, legg til en tidtaker og deaktiver kontrollen for inndatatekst for en gitt tid hvis brukeren skriver inn feil passord og deretter klikker eller trykker på **Logg på**-knappen.

