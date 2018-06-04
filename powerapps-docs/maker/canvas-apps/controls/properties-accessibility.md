---
title: Egenskaper for tilgjengelighet | Microsoft Docs
description: Referanseinformasjon om egenskaper som Tabulatorindeks, Verktøytips
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
ms.date: 01/26/2017
ms.author: fikaradz
ms.openlocfilehash: d35b4bc7a6e479ce47ad0a0b841a6ed9ccfd1a52
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/22/2018
ms.locfileid: "30996232"
---
# <a name="accessibility-properties-in-powerapps"></a>Egenskaper for tilgjengelighet i PowerApps
Konfigurasjon av egenskaper som tilbyr alternative måter å arbeide interaktivt med kontroller som er egnet for brukere med funksjonshemninger på.

### <a name="properties"></a>Egenskaper
**AccessiblityLabel** – beskrivelse av kontrollen som skal leses opp av skjermlesere.   En tom verdi for kontroller av typen Bilde, Ikon og Figur gjør dem usynlige for skjermleseren og fører til at de behandles som dekorasjoner.

* Dette gjelder kontrollene **[Lyd](control-audio-video.md)**, **[Knapp](control-button.md)**, **[Kamera](control-camera.md)**, **[Avmerkingsboks](control-check-box.md)**, **[Rullegardin](control-drop-down.md)**, **[HTML-tekst](control-html-text.md)**,  **[Bilde](control-image.md)**, **[Etikett](control-text-box.md)**, **[Listeboks](control-list-box.md)**, **[Mikrofon](control-microphone.md)**, **[PDF-visningsprogram](control-pdf-viewer.md)**,  **[Penneinndata](control-pen-input.md)**, **[Radio](control-radio.md)**, **[Vurdering](control-rating.md)**, **[Glidebryter](control-slider.md)** ,  **[Tekstinndata](control-text-input.md)**, **[Tidtaker](control-timer.md)**, **[Veksleknapp](control-toggle.md)** og **[Video](control-audio-video.md)**.

**Tabulatorindeks** – tilpasser kategorirekkefølgen ved kjøretid.

Standardverdien er null og angir standard tabulatorrekkefølge basert på kontrollens XY-koordinater.  Hvis du angir en verdi som er høyere enn null, flyttes kontrollens plass i tabulatorrekkefølgen foran alle kontroller med standardverdiene.  En kontroll med tabulatorindeks-verdien 2 vil stå foran en med tabulatorindeks-verdier på 3 eller høyere ved bruk av tabulator.

Merk at beholdere som Figur- og Galleri-kontroller alltid vil tabulere gjennom alle elementene i beholderen før de fortsetter til kontroller utenfor beholderen.  Beholderens plass i tabulatorrekkefølgen er plassen angitt av den laveste tabulatorindeks-verdien til en underordnet kontroll.

Hvis du angir Tabulatorindeks som -1, deaktiveres tabulatortilgang til kontrollen. Dette gjør Bilder, Ikoner og Figurer til ikke-interaktive elementer.

* Dette gjelde kontrollene **[Knapp](control-button.md)**, **[Datovelger](control-date-picker.md)**,  **[Rullegardin](control-drop-down.md)**, **[Bilde](control-image.md)**, **[Importer](control-export-import.md)**,  **[Listeboks](control-list-box.md)**, **[Radio](control-radio.md)**, **[Vurdering](control-rating.md)**, **[Glidebryter](control-slider.md)**, **[Tekstinndata](control-text-input.md)** og **[Veksleknapp](control-toggle.md)**.
