---
title: 'Mikrofon-kontrollen: referanse | Microsoft Docs'
description: Informasjon om Mikrofon-kontrollen, inkludert egenskaper og eksempler
author: fikaradz
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 10/25/2016
ms.author: fikaradz
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 915f5c15af06914cf10a749bf8d995926fd1bf2f
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/07/2019
ms.locfileid: "71993406"
---
# <a name="microphone-control-in-powerapps"></a>Mikrofon-kontrollen i PowerApps
En kontroll som gjør at brukere av appen kan spille inn lyder via enheten.

## <a name="description"></a>Beskrivelse
App-brukerne kan opprette lydopptak hvis enheten der appen kjøres har en mikrofon.

Lyd er lagret i 3gp-format i Android, AAC-format i iOS og OGG-format i nettlesere.

## <a name="key-properties"></a>Nøkkelegenskaper
**Mic** – ID-nummeret til mikrofonen som appen bruker for enheter med mer enn én mikrofon.

**OnStop** – hvordan appen reagerer når brukeren stopper et opptak med en mikrofon-kontroll.

## <a name="additional-properties"></a>Tilleggsegenskaper
**[AccessibleLabel](properties-accessibility.md)** – etikett for skjermlesere. Bør beskrive formålet med mikrofonen.

**[BorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje.

**[BorderStyle](properties-color-border.md)** – om kontrollens kantlinje er satt til **Heltrukket**, **Stiplet**, **Prikket** eller **Ingen**.

**[BorderThickness](properties-color-border.md)** – tykkelsen til kontrollens kantlinje.

**[Farge](properties-color-border.md)** – fargen på teksten i kontrollen.

**[DisplayMode](properties-core.md)** – om kontrollen tillater brukerinndata (**Rediger**), bare viser data (**Vis**) eller er deaktivert (**Deaktivert**).

**[DisabledBorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje hvis kontrollens **[DisplayMode](properties-core.md)** -egenskap er angitt til **Deaktivert**.

**[DisabledColor](properties-color-border.md)** – fargen på kontrollens tekst hvis kontrollens **[DisplayMode](properties-core.md)** -egenskap er angitt som **Deaktivert**.

**[DisabledFill](properties-color-border.md)** – bakgrunnsfargen på en kontroll hvis **[DisplayMode](properties-core.md)** -egenskapen er angitt som **Deaktivert**.

**[Fyll](properties-color-border.md)** – bakgrunnsfargen på kontrollen.

**[FocusedBorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje når kontrollen er fokusert.

**[FocusedBorderThickness](properties-color-border.md)** – fargen på kontrollens kantlinje når kontrollen er fokusert.

**[Høyde](properties-size-location.md)** – avstanden mellom kontrollens øvre og nedre kant.

**[HoverBorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje når brukeren holder musepekeren på denne kontrollen.

**[HoverColor](properties-color-border.md)** – Fargen på teksten i en kontroll når brukeren holder musepekeren over den.

**[HoverFill](properties-color-border.md)**  – bakgrunnsfargen for en kontroll når brukeren holder musepekeren på den.

**[Bilde](properties-visual.md)** – navnet på bildet som vises i en bilde-, lyd- eller mikrofonkontroll.

**[ImagePosition](properties-visual.md)** – plasseringen (**Fyll**, **Tilpass**, **Strekk**, **Fylle side ved side** eller **Midtstill**) til et bilde på en skjerm eller en kontroll hvis det ikke har samme størrelse som bildet.

**[OnSelect](properties-core.md)** – hvordan appen reagerer når brukeren klikker eller trykker på en kontroll.

**OnStart** – hvordan appen reagerer når brukeren starter et opptak med en mikrofon-kontroll.

**[PressedBorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje når brukeren trykker eller klikker på kontrollen.

**[PressedColor](properties-color-border.md)** – fargen på teksten i en kontroll når brukeren trykker eller klikker på kontrollen.

**[PressedFill](properties-color-border.md)** – bakgrunnsfargen på teksten i en kontroll når brukeren trykker eller klikker på kontrollen.

**[Tilbakestill](properties-core.md)** – om en kontroll tilbakestilles til standardverdien.

**[TabIndex](properties-accessibility.md)** – navigasjonsrekkefølge for tastatur i forhold til andre kontroller.

**[Verktøytips](properties-core.md)** – forklarende tekst som vises når brukeren holder pekeren over en kontroll.

**[Synlig](properties-core.md)** – om kontrollen vises eller skjules.

**[Bredde](properties-size-location.md)** – avstanden mellom kontrollens venstre og høyre kant.

**[X](properties-size-location.md)** – avstanden mellom kontrollens venstre kant og den venstre kanten til kontrollens overordnede beholder (eller skjermen, hvis det ikke finnes noen overordnet beholder).

**[Y](properties-size-location.md)** – avstanden mellom kontrollens øvre kant og den øvre kanten til kontrollens overordnede beholder (eller skjermen, hvis det ikke finnes noen overordnet beholder).

## <a name="related-functions"></a>Relaterte funksjoner
[**Patch**( *DataSource*, *BaseRecord*, *ChangeRecord* )](../functions/function-patch.md)

## <a name="example"></a>Eksempel
### <a name="add-sounds-to-a-custom-gallery-control"></a>Å legge til lyd i en Egendefinert galleri-kontroll
1. Legg til en **mikrofon**, gi den navnet **MyMic**, og angi **OnStop**-egenskapen som denne formelen:<br>
   **Collect(MySounds, MyMic.Audio)**

    Vet du ikke hvordan du [legger til, gir navn til og konfigurerer en kontroll](../add-configure-controls.md)?

    Vil du ha mer informasjon om **[Collect](../functions/function-clear-collect-clearcollect.md)** -funksjonen eller [andre funksjoner](../formula-reference.md)?
2. Legg til en **Egendefinert galleri**-kontroll, flytt den under **MyMic**, og angi **[Elementer](properties-core.md)** -egenskapen for **Egendefinert galleri**-kontrollen til **MySounds**.
3. Legg til en **[Lyd](control-audio-video.md)** -kontroll i malen for **Egendefinert galleri**-kontrollen, og angi **Media**-egenskapen som **ThisItem.Url**.
4. Trykk på F5, klikk eller trykk på **MyMic** for å starte innspillingen, og klikk eller trykk deretter på den på nytt for å stoppe innspillingen.
5. Klikk eller trykk på avspillingsknappen i **[Lyd](control-audio-video.md)** -kontrollen i **Egendefinert galleri**-kontrollen for å spille av innspillingen.
6. Legg til så mange innspillinger du vil, og gå tilbake til standardarbeidsområdet ved å trykke på Esc.
7. (valgfritt) Legg til en **[Knapp](control-button.md)** -kontroll i malen for **Egendefinert galleri**-kontrollen. Angi **[OnSelect](properties-core.md)** -egenskapen som **Remove(MySounds, ThisItem)** , trykk på F5, og fjern en innspilling ved å klikke eller trykke på den tilhørende **Knapp**-kontroll.

Bruk **[SaveData](../functions/function-savedata-loaddata.md)** -funksjonen til å lagre bildene lokalt eller **[Patch](../functions/function-patch.md)** -funksjonen til å oppdatere en datakilde.


## <a name="accessibility-guidelines"></a>Retningslinjer for tilgjengelighet
De samme retningslinjene for **[Knapp](control-button.md)**  gjelder fordi **Mikrofon** er bare en spesialknapp. Vurder i tillegg følgende:

### <a name="audio-alternatives"></a>Alternativer for lyd
* Vurder å legge til en alternativ form for inndata for brukere med talefunksjonshemninger eller som ikke har en mikrofon. Legg for eksempel til **[Tekstinndata](control-text-input.md)** for å la brukere skrive inn tekst.

### <a name="color-contrast"></a>Fargekontrast
Det må være tilstrekkelig fargekontrast mellom:
* **[Bilde](properties-visual.md)** og knappeteksten og -ikonet (hvis aktuelt)

Dette er i tillegg til [kravene for standard fargekontrast](../accessible-apps-color.md).

### <a name="screen-reader-support"></a>Kundestøtte for skjermlesere
* **[AccessibleLabel](properties-accessibility.md)** bør vises.
