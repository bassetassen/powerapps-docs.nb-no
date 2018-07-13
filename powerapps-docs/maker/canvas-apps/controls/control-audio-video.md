---
title: 'Lyd- og videokontroller: referanse | Microsoft Docs'
description: Informasjon, deriblant egenskaper og eksempler, om lyd- og videokontroller
author: fikaradz
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.date: 10/25/2016
ms.author: fikaradz
ms.reviewer: anneta
ms.openlocfilehash: d4fbcafb7c566af224869ad0ce4233e580b20029
ms.sourcegitcommit: dfa0e1a7981814e15e6ca4720e2a5f930e859db1
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 07/13/2018
ms.locfileid: "39017368"
---
# <a name="audio-and-video-controls-in-powerapps"></a>Lyd- og videokontroller i PowerApps
En kontroll som spiller av en lydfil, en videofil eller en video på YouTube.

## <a name="description"></a>Beskrivelse
En **lyd**kontroll spiller av et lydklipp fra en fil, et opptak fra en  **[mikrofon](control-microphone.md)**-kontroll eller lydsporet fra en videofil.

En **video**-kontroll spiller av et videoklipp fra en fil eller fra YouTube eller Azure Media Services.  Teksting for hørselshemmede kan eventuelt vises når dette angis.

## <a name="key-properties"></a>Nøkkelegenskaper
**Loop** – hvorvidt et lyd- eller videoklipp automatisk starter på nytt så snart det er ferdig.

**Media** – en identifikator for klippet som spilles av via en lyd- eller videokontroll.

**ShowControls** – om en lyd- eller videoavspiller for eksempel viser en avspillingsknapp og en glidebryter for volum, og om en pennekontroll for eksempel viser ikoner for tegning, sletting og fjerning.

## <a name="additional-properties"></a>Tilleggsegenskaper
**[AccessibleLabel](properties-accessibility.md)** – etikett for skjermlesere. Bør være tittelen på video- eller lydklipp.

**AutoPause** – om et lyd- eller videoklipp stanses automatisk hvis brukeren navigerer til en annen skjerm.

**AutoStart** – om en lyd- eller videokontroll automatisk begynner å spille av et klipp når brukeren navigerer til skjermen som inneholder denne kontrollen.

**[BorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje.

**[BorderStyle](properties-color-border.md)** – om kontrollens kantlinje er satt til **Heltrukket**, **Stiplet**, **Prikket** eller **Ingen**.

**[BorderThickness](properties-color-border.md)** – tykkelsen til kontrollens kantlinje.

**ClosedCaptionsUrl** – kun videokontroll.  Nettadresse for teksting for hørselshemmede i WebVTT-format.  Nettadresser for både video- og bildetekster må være HTTPS. Serveren der både video- og bildetekstfiler er lagret, må være aktivert for CORS.

**[DisplayMode](properties-core.md)** – om kontrollen tillater brukerinndata (**Rediger**), bare viser data (**Vis**) eller er deaktivert (**Deaktivert**).

**[Fyll](properties-color-border.md)** – bakgrunnsfargen på kontrollen.

**[FocusedBorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje når kontrollen er fokusert.

**[FocusedBorderThickness](properties-color-border.md)** – fargen på kontrollens kantlinje når kontrollen er fokusert.

**[Høyde](properties-size-location.md)** – avstanden mellom kontrollens øvre og nedre kant.

**[Bilde](properties-visual.md)** – navnet på bildet som vises i en bilde-, lyd- eller mikrofonkontroll.

**[ImagePosition](properties-visual.md)** – posisjonen (**Fyll**, **Tilpass**, **Strekk**, **Flis** eller **Midtstill**) til et bilde på en skjerm eller i en kontroll hvis skjermen eller kontrollen ikke har samme størrelse som bildet.

**OnEnd** – hvordan en app reagerer når avspillingen av et lyd- eller videoklipp er ferdig.

**OnPause** – hvordan en app reagerer når brukeren midlertidig stanser avspillingen av et klipp i en lyd- eller videokontroll.

**OnStart** – hvordan appen reagerer når brukeren starter et opptak med en mikrofonkontroll.

**Midlertidig stanset** – *Sann* hvis en kontroll for medieavspilling er midlertidig stanset, *usann* hvis ikke.

**[Tilbakestill](properties-core.md)** – om en kontroll tilbakestilles til standardverdien.

**Start** – om et lyd- eller videoklipp spilles av.

**StartTime** – hvor lang tid det tar fra lyd- eller videoklippet startes til avspillingen av klippet starter.

**Tid** – mediakontrollens gjeldende posisjon.

**[TabIndex](properties-accessibility.md)** – navigasjonsrekkefølge for tastatur i forhold til andre kontroller.

**[Verktøytips](properties-core.md)** – forklarende tekst som vises når brukeren holder pekeren over en kontroll.

**[Synlig](properties-core.md)** – om kontrollen vises eller skjules.

**[Bredde](properties-size-location.md)** – avstanden mellom kontrollens venstre og høyre kant.

**[X](properties-size-location.md)** – avstanden mellom kontrollens venstre kant og den venstre kanten til kontrollens overordnede beholder (eller skjermen, hvis det ikke finnes noen overordnet beholder).

**[Y](properties-size-location.md)** – avstanden mellom kontrollens øvre kant og den øvre kanten til kontrollens overordnede beholder (eller skjermen, hvis det ikke finnes noen overordnet beholder).

## <a name="related-functions"></a>Relaterte funksjoner
[**First**( *TableName* )](../functions/function-first-last.md)

## <a name="examples"></a>Eksempler
### <a name="play-an-audio-or-video-file"></a>Spill av en lyd- eller videofil
1. Klikk eller trykk på **Media** på **Fil**-menyen, klikk eller trykk på **Videoer** eller **Lyd**, og klikk eller trykk deretter på **Bla gjennom**.
2. Bla til filen du vil bruke, klikk eller trykk på den og klikk eller trykk deretter på **Åpne**.
3. Trykk på Esc for å gå tilbake til standardarbeidsområdet, legge til en **lyd**- eller **video**kontroll, og angi kontrollens **Media**-egenskap til den filen du har lagt til.

    Lurer du på hvordan du [legger til og konfigurerer en kontroll](../add-configure-controls.md)?
4. Trykk på F5, og spill deretter av klippet ved å klikke eller trykke på avspillingsknappen til kontrollen du har lagt til.

    > [!TIP]
   > Avspillingsknappen for **video**kontrollen vises når du holder pekeren over kontrollen.
5. Trykk på ESC for å gå tilbake til standardarbeidsområdet.

### <a name="play-a-youtube-video"></a>Å spille av en YouTube-video
1. Legg til en **video**-kontroll, og angi kontrollens **Media**-egenskap til nettadressen omsluttet av doble anførselstegn.
2. Trykk på F5, og spill deretter av klippet ved å klikke eller trykke på avspillingsknappen til **video**kontrollen du har lagt til.
3. Trykk på ESC for å gå tilbake til standardarbeidsområdet.

### <a name="play-a-video-from-azure-media-services"></a>Spill av en video fra Azure Media Services
1. Når videoene er publisert på AMS, kan du kopiere manifest-nettadressen. Start endepunktet for direkteavspillingen for tjenesten, hvis det ikke allerede er gjort.
1. Legg til en **video**-kontroll, og angi kontrollens **media**-egenskap til nettadressen for AMS-videoen, omsluttet av doble anførselstegn.
2. Trykk på F5, og spill deretter av klippet ved å klikke eller trykke på avspillingsknappen til **video**kontrollen du har lagt til.
3. Trykk på ESC for å gå tilbake til standardarbeidsområdet.


## <a name="accessibility-guidelines"></a>Retningslinjer for tilgjengelighet
### <a name="audio-and-video-alternatives"></a>Lyd- og videoalternativer
* **ShowControls** må være sann for at brukerne skal kunne høre eller se multimedia i sitt eget tempo. Dette gjør også at brukere kan veksle mellom teksting for hørselshemmede og fullskjermmodus på videospillere.
* Teksting for hørselshemmede må være angitt for videoer.
  *  Bruk redigeringsverktøy som leveres av YouTube til å legge til bildetekster for YouTube-videoer.
  *  Opprett bildetekster i WebVTT-format for andre videoer, last dem opp og angi **ClosedCaptionsUrl** til området for nettadressen. Det finnes flere begrensninger. En server/servere som er vert for videoer og bildetekster må være CORS-aktivert og betjene dem ved hjelp av en HTTPS-protokoll. Underteksting fungerer ikke i Internet Explorer.
* Vurder å ta med en lyd- eller videoutskrift ved hjelp av én av disse metodene:
  1. Plasser teksten i en **[etikett](control-text-box.md)**, og plasser den deretter ved siden av multimediaspilleren. Du kan også opprette en **[knapp](control-button.md)** for å veksle visningen av teksten.
  2. Plasser teksten i en annen skjerm. Opprett en **[knapp](control-button.md)** som navigerer til skjermen, og plasser knappen ved siden av multimediaspilleren.
  3. Hvis beskrivelsen er kort, kan den plasseres i **[AccessibleLabel](properties-accessibility.md)**.

### <a name="color-contrast"></a>Fargekontrast
Det må være tilstrekkelig fargekontrast mellom:
* **[FocusedBorderColor](properties-color-border.md)** og den ytre fargen
* **[Bilde](properties-visual.md)** og multimediaspiller-kontrollene (hvis aktuelt)
* **[Fyll](properties-color-border.md)** og multimediaspiller-kontrollene (hvis aktuelt)

Angi teksting for hørselshemmede og/eller utskrift hvis videoinnholdet har problemer knyttet til fargekontrast.

### <a name="screen-reader-support"></a>Kundestøtte for skjermlesere
* **[AccessibleLabel](properties-accessibility.md)** bør vises.

### <a name="keyboard-support"></a>Tastaturstøtte
* **[TabIndex](properties-accessibility.md)** må være null eller større, slik at tastaturbrukere kan navigere til den.
* Fokusindikatorer må være godt synlige. Bruk **[FocusedBorderColor](properties-color-border.md)** og **[FocusedBorderThickness](properties-color-border.md)** for å oppnå dette.
* **AutoStart** bør være usann fordi det kan være vanskelig for tastaturbrukere å stoppe avspillingen raskt.
