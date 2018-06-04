---
title: 'Lyd- og videokontroller: referanse | Microsoft Docs'
description: Informasjon, deriblant egenskaper og eksempler, om lyd- og videokontroller
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
ms.openlocfilehash: 1661477ced59a678ac278dfcebe5e6f661c3e3f1
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/22/2018
ms.locfileid: "30996272"
---
# <a name="audio-and-video-controls-in-powerapps"></a>Lyd- og videokontroller i PowerApps
En kontroll som spiller av en lydfil, en videofil eller en video på YouTube.

## <a name="description"></a>Beskrivelse
En **lyd**kontroll spiller av et lydklipp fra en fil, et opptak fra en  **[mikrofon](control-microphone.md)**-kontroll eller lydsporet fra en videofil. En **video**kontroll spiller av et videoklipp fra en fil eller fra YouTube hvis du angir en nettadresse med valgfri teksting for hørselshemmede.

## <a name="key-properties"></a>Nøkkelegenskaper
**Loop** – hvorvidt et lyd- eller videoklipp automatisk starter på nytt så snart det er ferdig.

**Media** – en identifikator for klippet som spilles av via en lyd- eller videokontroll.

**ShowControls** – om en lyd- eller videoavspiller for eksempel viser en avspillingsknapp og en glidebryter for volum, og om en pennekontroll for eksempel viser ikoner for tegning, sletting og fjerning.

## <a name="additional-properties"></a>Tilleggsegenskaper
**AutoPause** – om et lyd- eller videoklipp stanses automatisk hvis brukeren navigerer til en annen skjerm.

**AutoStart** – om en lyd- eller videokontroll automatisk begynner å spille av et klipp når brukeren navigerer til skjermen som inneholder denne kontrollen.

**[Kantlinjefarge](properties-color-border.md)** – fargen på kontrollens kantlinje.

**[BorderStyle](properties-color-border.md)** – om kontrollens kantlinje er satt til **Heltrukket**, **Stiplet**, **Prikket** eller **Ingen**.

**[BorderThickness](properties-color-border.md)** – tykkelsen til kontrollens kantlinje.

**ClosedCaptionsUrl** – kun videokontroll.  Nettadresse for teksting for hørselshemmede i WebVTT-format.  Nettadresser for både video- og bildetekster må være HTTPS. Serveren der både video- og bildetekstfiler er lagret, må være aktivert for CORS.

**[DisplayMode](properties-core.md)** – om kontrollen tillater brukerinndata (**Rediger**), bare viser data (**Vis**) eller er deaktivert (**Deaktivert**).

**[Fyll](properties-color-border.md)** – bakgrunnsfargen på kontrollen.

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
3. Trykk på ESC for å gå tilbake til standardarbeidsområdet, legg til en **lyd**- eller **video**kontroll og angi kontrollens **Media**-egenskap til filen du har lagt til.

    Lurer du på hvordan du [legger til og konfigurerer en kontroll](../add-configure-controls.md)?
4. Trykk på F5, og spill deretter av klippet ved å klikke eller trykke på avspillingsknappen til kontrollen du har lagt til.

    > [!TIP]
> Avspillingsknappen for **video**kontrollen vises når du holder pekeren over kontrollen.
5. Trykk på ESC for å gå tilbake til standardarbeidsområdet.

### <a name="play-a-youtube-video"></a>Å spille av en YouTube-video
1. Legg til en **video**kontroll, og angi kontrollens **Media**-egenskap til nettadressen omsluttet av doble anførselstegn, til en YouTube-video.
2. Trykk på F5, og spill deretter av klippet ved å klikke eller trykke på avspillingsknappen til **video**kontrollen.
3. Trykk på ESC for å gå tilbake til standardarbeidsområdet.
