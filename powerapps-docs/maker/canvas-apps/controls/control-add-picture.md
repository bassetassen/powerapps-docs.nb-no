---
title: 'Legg til bilde-kontrollen: referanse | Microsoft Docs'
description: Informasjon om Legg til bilde-kontrollen, inkludert egenskaper og eksempler
author: fikaradz
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.date: 10/25/2016
ms.author: fikaradz
ms.reviewer: tapanm
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 81c96c7a2a23a770acfcc1936147a3b466f8c86d
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/07/2019
ms.locfileid: "71993870"
ms.PowerAppsDecimalTransform: true
---
# <a name="add-picture-control-in-powerapps"></a>Legg til bilde-kontrollen i PowerApps
Tar et bilde eller laster inn bilder fra den lokale enheten.

## <a name="description"></a>Beskrivelse
Med denne kontrollen kan brukere ta bilder eller laste opp bildefiler fra enheten og oppdatere datakilden med dette innholdet. På en mobil enhet får brukeren se enhetens valgdialog for å velge mellom å ta et bilde eller velge et som allerede finnes.

Denne kontrollen er en gruppert kontroll som inneholder to kontroller: Ett **Bilde** og én **Legg til medier-knapp**. **Bilde**-kontrollen viser det opplastede bildet eller en plassholder hvis det ikke er lastet opp noe bilde. **Legg til medier-knappen** ber deg om å laste opp et bilde.

Se [Kontrollreferanse for bilde](control-image.md) for **Bilde**-egenskaper.

## <a name="add-media-button-properties"></a>Å legge til egenskaper for media-knapp
**[AccessibleLabel](properties-accessibility.md)** – etikett for skjermlesere. Skal beskrive formålet med å legge til et bilde.

**[Juster](properties-text.md)** – plasseringen av teksten i forhold til den vannrette midten av kontrollen.

**[BorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje.

**[BorderStyle](properties-color-border.md)** – om kontrollens kantlinje er satt til **Heltrukket**, **Stiplet**, **Prikket** eller **Ingen**.

**[BorderThickness](properties-color-border.md)** – tykkelsen til kontrollens kantlinje.

**ChangePictureText** – teksten som vises på knappen når et bilde er lastet opp.

**[Farge](properties-color-border.md)** – fargen på teksten i kontrollen.

**[DisabledBorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje hvis kontrollens **[DisplayMode](properties-core.md)** -egenskap er angitt til **Deaktivert**.

**[DisabledColor](properties-color-border.md)** – fargen på kontrollens tekst hvis kontrollens **[DisplayMode](properties-core.md)** -egenskap er angitt som **Deaktivert**.

**[DisabledFill](properties-color-border.md)** – bakgrunnsfargen på en kontroll hvis **[DisplayMode](properties-core.md)** -egenskapen er angitt som **Deaktivert**.

**[DisplayMode](properties-core.md)** – om kontrollen tillater brukerinndata (**Rediger**), bare viser data (**Vis**) eller er deaktivert (**Deaktivert**).

**Feil** – Hvis det oppstår et problem ved opplasting av et bildet, består denne egenskapen av en streng med en tilhørende feilmelding.

**[Fyll](properties-color-border.md)** – bakgrunnsfargen på kontrollen.

**[FocusedBorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje når kontrollen er fokusert.

**[FocusedBorderThickness](properties-color-border.md)** – fargen på kontrollens kantlinje når kontrollen er fokusert.

**[Skrift](properties-text.md)** – navnet på skriftserien som teksten vises i.

**[FontWeight](properties-text.md)** – tykkelsen på teksten i en kontroll: **Fet**, **halvfet**, **Normal**eller **lysere**.

**[Høyde](properties-size-location.md)** – avstanden mellom kontrollens øvre og nedre kant.

**[HoverBorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje når brukeren holder musepekeren på denne kontrollen.

**[HoverColor](properties-color-border.md)** – Fargen på teksten i en kontroll når brukeren holder musepekeren over den.

**[HoverFill](properties-color-border.md)** – bakgrunnsfargen for en kontroll når brukeren holder musepekeren over den.

**[Kursiv](properties-text.md)** – om teksten i en kontroll er i kursiv.

**Media** – En identifikator for klippet som spilles av en lyd- eller videokontroll.

**[OnChange](properties-core.md)** – hvordan appen reagerer når brukeren endrer verdien på en kontroll (ved å for eksempel justere en glidebryter).

**[OnSelect](properties-core.md)** – hvordan appen responderer når brukeren klikker eller trykker på en kontroll.

**[Padding](properties-size-location.md)**  – avstanden mellom teksten på en import- eller eksportknapp og kantene på denne knappen.

**[PressedBorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje når brukeren trykker eller klikker på kontrollen.

**[PressedColor](properties-color-border.md)** – fargen på teksten i en kontroll når brukeren trykker eller klikker på kontrollen.

**[PressedFill](properties-color-border.md)** – bakgrunnsfargen på teksten i en kontroll når brukeren trykker eller klikker på kontrollen.

**[Tilbakestill](properties-core.md)** – om en kontroll tilbakestilles til standardverdien.

**[Størrelse](properties-text.md)** – skriftstørrelsen på teksten som vises på en kontroll.

**[Strikethrough](properties-text.md)** – om det vises en linje gjennom teksten som vises på en kontroll.

**[TabIndex](properties-accessibility.md)** – navigasjonsrekkefølge for tastatur i forhold til andre kontroller.

**[Tekst](properties-core.md)** – teksten som vises på knappen når et bilde ikke er lastet opp.

**[Verktøytips](properties-core.md)** – forklarende tekst som vises når brukeren holder pekeren over en kontroll.

**[Underline](properties-text.md)**  – Hvorvidt det vises en linje under teksten som vises på en kontroll.

**[VerticalAlign](properties-text.md)** – plasseringen av tekst i en kontroll i forhold til det vertikale midtpunktet i kontrollen.

**[Visible](properties-core.md)** – om kontrollen vises eller skjules.

**[Bredde](properties-size-location.md)** – avstanden mellom kontrollens venstre og høyre kant.

**[X](properties-size-location.md)** – avstanden mellom kontrollens venstre kant og den venstre kanten til kontrollens overordnede beholder (eller skjermen, hvis det ikke finnes noen overordnet beholder).

**[Y](properties-size-location.md)** – avstanden mellom kontrollens øvre kant og den øvre kanten til kontrollens overordnede beholder (eller skjermen, hvis det ikke finnes noen overordnet beholder).

## <a name="related-functions"></a>Relaterte funksjoner
[**Patch**( *DataSource*; *BaseRecord*; *ChangeRecord* )](../functions/function-patch.md)

## <a name="examples"></a>Eksempler
### <a name="add-images-to-an-image-gallery-control"></a>Legg til bilder i en Bildegalleri-kontroll
1. Legg til en **Legg til bilde**-kontroll, og trippelklikk på den.
   
    Vet du ikke hvordan du [legger til, gir navn til og konfigurerer en kontroll](../add-configure-controls.md)?
2. Klikk eller trykk på en bildefil i **Åpne**-dialogboksen, og klikk eller trykk på **Åpne**.
3. Legg til en **[Knapp](control-button.md)** -kontroll, flytt den under **Legg til bilde**-kontrollen, og angi **[OnSelect](properties-core.md)** -egenskapen til **[Knapp](control-button.md)** -kontrollen som denne formelen:<br>
   **Collect(MyPix; AddMediaButton1.Media)**
   
    Vil du ha mer informasjon om **[Collect](../functions/function-clear-collect-clearcollect.md)** -funksjonen eller [andre funksjoner](../formula-reference.md)?
4. Legg til en **Bildegalleri**-kontroll, og angi **[Items](properties-core.md)** -egenskapen som **MyPix**.
5. Trykk på F5, og klikk eller trykk på **[Knapp](control-button.md)** -kontrollen.
   
    Bildet fra **Legg til bilde**-kontrollen vises i **Bildegalleri**-kontrollen. Hvis bildet ditt ikke har samme størrelsesforhold som **[Bilde](control-image.md)** -kontrollen i **Bildegalleri**-kontrollen, kan du angi **[ImagePosition](properties-visual.md)** -egenskapen til **[Bilde](control-image.md)** -kontrollen som **Fit**.
6. Klikk eller trykk på **Legg til bilde**-kontrollen, klikk eller trykk på en annen bildefil, klikk eller trykk på **Åpne**, og klikk eller trykk på **[Knapp](control-button.md)** -kontrollen som du har lagt til.
   
    Det andre bildet vises i **Bildegalleri**-kontrollen.
7. (valgfritt) Gjenta forrige trinn én eller flere ganger, og gå deretter tilbake til standardarbeidsområdet ved å trykke på Esc.

Bruk **[SaveData](../functions/function-savedata-loaddata.md)** -funksjonen til å lagre bildene lokalt eller **[Patch](../functions/function-patch.md)** -funksjonen til å lagre dem til en datakilde.


## <a name="accessibility-guidelines"></a>Retningslinjer for tilgjengelighet
De samme retningslinjene for **[Knapp](control-button.md)** og **[Bilde](control-image.md)** gjelder. Vurder i tillegg følgende:

### <a name="color-contrast"></a>Fargekontrast
* **Legg til medier-knapp** må ha tilstrekkelig kontrast mellom teksten og bakgrunnen. Siden det opplastede bildet kan ha mange ulike farger, kan du bruke et ugjennomsiktig  **[fyll](properties-color-border.md)** på **Legg til medier-knappen** for å sikre konsekvent kontrast.

### <a name="screen-reader-support"></a>Kundestøtte for skjermlesere
* **Legg til medier-knapp** må ha **Tekst** og **ChangePictureText** som ber brukeren om å legge til eller endre et bilde.

### <a name="keyboard-support"></a>Tastaturstøtte
* **Legg til medier-knapp** må ha **[TabIndex](properties-accessibility.md)**  lik null eller større slik at tastaturbrukere kan navigere til den.
* **Legg til medier-knapp** må ha godt synlige fokusindikatorer. Bruk **[FocusedBorderColor](properties-color-border.md)** og **[FocusedBorderThickness](properties-color-border.md)** for å oppnå dette.
 
