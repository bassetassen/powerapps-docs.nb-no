---
title: 'Tekstinndata-kontroll: referanse | Microsoft Docs'
description: Informasjon om tekstinndata-kontrollen, inkludert egenskaper og eksempler
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
ms.openlocfilehash: a46635276f6598cf0591dc21ae5aeb855b6667c1
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/23/2019
ms.locfileid: "61560483"
ms.PowerAppsDecimalTransform: true
---
# <a name="text-input-control-in-powerapps"></a>Tekstinndata-kontroll i PowerApps
En boks som brukeren kan skrive inn tekst, tall og andre data i.

## <a name="description"></a>Beskrivelse
Brukeren kan angi data ved å skrive inn i en kontroll for tekstinndata. Avhengig av hvordan du konfigurerer appen, blir dataene kanskje lagt til i en datakilde, brukt til å beregne en midlertidig verdi eller tatt med på en annen måte.

## <a name="key-properties"></a>Nøkkelegenskaper
**[Standard](properties-core.md)** – startverdien for en kontroll før den er endret av brukeren.

**[Text](properties-core.md)**  – tekst som vises på en kontroll, eller som brukeren skriver inn i en kontroll.

## <a name="additional-properties"></a>Tilleggsegenskaper
**[AccessibleLabel](properties-accessibility.md)** – etikett for skjermlesere.

**[Juster](properties-text.md)** – plasseringen av teksten i forhold til den vannrette midten av kontrollen.

**[BorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje.

**[BorderStyle](properties-color-border.md)** – om kontrollens kantlinje er satt til **Heltrukket**, **Stiplet**, **Prikket** eller **Ingen**.

**[BorderThickness](properties-color-border.md)** – tykkelsen til kontrollens kantlinje.

**Fjern** – om en tekstinndata-kontroll viser en X som brukeren kan berøre eller klikke på for å fjerne innholdet i den aktuelle kontrollen.

**[Color](properties-color-border.md)** – fargen på teksten i en kontroll.

**DelayOutput** – når den er satt til sann, blir brukerinndata registrert etter et halvt sekunds forsinkelse.  Nyttig for å forsinke dyre operasjoner inntil brukeren fullfører innsetting av tekst (det vil si for filtrering når inndata brukes i andre formler).

**[DisplayMode](properties-core.md)** – om kontrollen tillater brukerinndata (**Redigere**), bare viser data (**Vis**) eller er deaktivert (**Deaktivert**).

**[DisabledBorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje hvis kontrollens **[DisplayMode](properties-core.md)**-egenskap er angitt til **Deaktivert**.

**[DisabledColor](properties-color-border.md)** – fargen på kontrollens tekst hvis kontrollens **[DisplayMode](properties-core.md)**-egenskap er angitt som **Deaktivert**.

**[DisabledFill](properties-color-border.md)** – bakgrunnsfargen på en kontroll hvis **[DisplayMode](properties-core.md)**-egenskapen er angitt som **Deaktivert**.

**[Fyll](properties-color-border.md)** – bakgrunnsfargen på kontrollen.

**[FocusedBorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje når kontrollen er fokusert.

**[FocusedBorderThickness](properties-color-border.md)** – fargen på kontrollens kantlinje når kontrollen er fokusert.

**[Skrift](properties-text.md)** – navnet på skriftserien som teksten vises i.

**[FontWeight](properties-text.md)**  – vekten på teksten i en kontroll: **Fet**, **Halvfet**, **Normal**, eller **lysere**.

**Format** – om brukerinndataene er begrenset til bare tall eller kan være en hvilken som helst tekst.

**[Height](properties-size-location.md)** – avstanden mellom kontrollens øvre og nedre kant.

**HintText** – lys grå tekst som vises i en tekstinndata-kontroll hvis den er tom.

**[HoverBorderColor](properties-color-border.md)**  – fargen på kontrollens kantlinje når brukeren holder musepekeren over denne kontrollen.

**[HoverColor](properties-color-border.md)** – Fargen på teksten i en kontroll når brukeren holder musepekeren over den.

**[HoverFill](properties-color-border.md)** – bakgrunnsfargen for en kontroll når brukeren holder musepekeren over den.

**[Kursiv](properties-text.md)** – om teksten i en kontroll er i kursiv.

**[LineHeight](properties-text.md)** – avstanden mellom linjer med tekst, elementer i en liste eller lignende.

**MaxLength** – antall tegn som brukeren kan skrive inn i en Tekstinndata-kontroll.

**Mode** – kontrollen er i modus for **SingleLine**, **MultiLine** eller **Password**.

**[OnChange](properties-core.md)** – hvordan appen reagerer når brukeren endrer verdien på en kontroll (ved å for eksempel justere en glidebryter).

**[OnSelect](properties-core.md)** – hvordan appen responderer når brukeren klikker eller trykker på en kontroll.

**[PaddingBottom](properties-size-location.md)** – avstanden mellom teksten i en kontroll og den nederste kanten av kontrollen.

**[PaddingLeft](properties-size-location.md)** – avstanden mellom teksten i en kontroll og den venstre kanten av kontrollen.

**[PaddingRight](properties-size-location.md)** – avstanden mellom teksten i en kontroll og den høyre kanten av kontrollen.

**[PaddingTop](properties-size-location.md)** – avstanden mellom teksten i en kontroll og den øverste kanten av kontrollen.

**[PressedBorderColor](properties-color-border.md)**  – fargen på kontrollens kantlinje når brukeren trykker eller klikker på kontrollen.

**[PressedColor](properties-color-border.md)** – fargen på teksten i en kontroll når brukeren trykker eller klikker på kontrollen.

**[PressedFill](properties-color-border.md)** – bakgrunnsfargen i en kontroll når brukeren trykker eller klikker på kontrollen.

**[RadiusBottomLeft](properties-size-location.md)** – i hvilken grad hjørnet nederst til venstre i en kontroll avrundes.

**[RadiusBottomRight](properties-size-location.md)**  – i hvilken grad hjørnet nederst til høyre i en kontroll avrundes.

**[RadiusTopLeft](properties-size-location.md)** – i hvilken grad hjørnet øverst til venstre i en kontroll avrundes.

**[RadiusTopRight](properties-size-location.md)** – i hvilken grad hjørnet øverst til høyre av en kontroll avrundes.

**[Reset](properties-core.md)** – om en kontroll tilbakestilles til standardverdien.

**[Størrelse](properties-text.md)** – skriftstørrelsen på teksten som vises på en kontroll.

**[Strikethrough](properties-text.md)** – om det vises en linje gjennom teksten som vises på en kontroll.

**[TabIndex](properties-accessibility.md)** – navigasjonsrekkefølge for tastatur i forhold til andre kontroller.

**[Verktøytips](properties-core.md)** – forklarende tekst som vises når brukeren holder pekeren over en kontroll.

**[Underline](properties-text.md)** – om det vises en linje under teksten som vises på en kontroll.

**[Synlig](properties-core.md)** – om kontrollen vises eller skjules.

**[Bredde](properties-size-location.md)** – avstanden mellom kontrollens venstre og høyre kant.

**[X](properties-size-location.md)** – avstanden mellom kontrollens venstre kant og den venstre kanten til kontrollens overordnede beholder (eller skjermen, hvis det ikke finnes noen overordnet beholder).

**[Y](properties-size-location.md)** – avstanden mellom kontrollens øvre kant og den øvre kanten til kontrollens overordnede beholder (eller skjermen, hvis det ikke finnes noen overordnet beholder).

## <a name="related-functions"></a>Relaterte funksjoner
[**DateTimeValue**( *String* )](../functions/function-datevalue-timevalue.md)

## <a name="examples"></a>Eksempler
### <a name="collect-data"></a>Innsamling av data
1. Legg til to kontroller for tekstinndata, og gi dem navnene **inputFirst** og **inputLast**.
   
    Vet du ikke hvordan du [legger til, gir navn til og konfigurerer en kontroll](../add-configure-controls.md)?
2. Legg til en knapp, angi **[Text](properties-core.md)**-egenskapen til **Legg til**, og angi **[OnSelect](properties-core.md)**-egenskapen til denne formelen:<br>
   **Collect(Names; {FirstName:inputFirst.Text; LastName:inputLast.Text})**
   
    Vil du ha mer informasjon om **[Collect](../functions/function-clear-collect-clearcollect.md)**-funksjonen eller [andre funksjoner](../formula-reference.md)?
3. Legg til et tekstgalleri i stående/loddrett retning, angi **[Items](properties-core.md)** til **Navn**, og angi **[Text](properties-core.md)**-egenskapen til **Subtitle1** til **ThisItem.FirstName**.
4. (valgfritt) I malgalleriet sletter du den nederste etiketten, kalt **Body1**, og angir **[TemplateSize](control-gallery.md)**-egenskapen for galleriet til **80**.
5. Trykk på F5, skriv inn en tekststreng til **inputFirst** og **inputLast**, og klikk eller trykk deretter på **Legg til**-knappen.
6. (valgfritt) Legg til flere navn i samlingen, og trykk deretter på ESC for å gå tilbake til standardarbeidsområdet.

### <a name="prompt-for-a-password"></a>Å be om et passord

1. Legg til en kontroll for inndatatekst, gi den navnet **inputPassword**, og angi **Modus**-egenskapen til **Passord**.

1. Legg til en etikett, og angi **[Text](properties-core.md)**-egenskapen til denne formelen:<br>
   **If(inputPassword.Text = "P@ssw0rd"; "Access granted"; "Access denied")**

    Vil du ha mer informasjon om **[If](../functions/function-if.md)**-funksjonen eller [andre funksjoner](../formula-reference.md)?

1. Trykk på F5, og skriv deretter **P@ssw0rd** i **inputPassword**.

    Når du er ferdig å skrive inn passordet, viser ikke etiketten meldingen **Ingen tilgang** lenger. Den viser deretter **Tilgang innvilget**.

1. Trykk på ESC for å gå tilbake til standardarbeidsområdet.

1. (valgfritt) Legg til en kontroll, for eksempel en pil, konfigurer den til å navigere til en annen skjerm, og vis den bare etter at brukeren skriver inn passordet.

1. (valgfritt) Legg til en knapp, konfigurer **[Text](properties-core.md)**-egenskapen til å vise **Logg på**, legg til en tidtaker og deaktiver kontrollen for inndatatekst for en gitt tid hvis brukeren skriver inn feil passord og deretter klikker eller trykker på **Logg på**-knappen.


## <a name="accessibility-guidelines"></a>Retningslinjer for tilgjengelighet
### <a name="color-contrast"></a>Fargekontrast
* [Standardkrav for fargekontrast](../accessible-apps-color.md) gjelder.

### <a name="screen-reader-support"></a>Kundestøtte for skjermlesere
* **[AccessibleLabel](properties-accessibility.md)** bør vises.

### <a name="keyboard-support"></a>Tastaturstøtte
* **[TabIndex](properties-accessibility.md)** må være null eller større, slik at tastaturbrukere kan navigere til den.
* Fokusindikatorer må være godt synlige. Bruk **[FocusedBorderColor](properties-color-border.md)** og **[FocusedBorderThickness](properties-color-border.md)** for å oppnå dette.
 
