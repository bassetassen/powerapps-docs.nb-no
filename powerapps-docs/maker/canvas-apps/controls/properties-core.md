---
title: Kjerneegenskaper | Microsoft Docs
description: Referanseinformasjon om egenskapene Deaktivert, Synlig og ReadOnly
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 10/25/2016
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 16065dc29d74655cbede25cea20148b343b790e6
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/24/2018
ms.locfileid: "42854011"
---
# <a name="core-properties-in-powerapps"></a>Kjerneegenskaper i PowerApps
Konfigurer hvorvidt brukeren kan se og samhandle med en kontroll.

### <a name="properties"></a>Egenskaper
**Default** – startverdien for en kontroll før den endres av brukeren.

* Gjelder kontrollene **[Kort](control-card.md)**, **[Avmerkingsboks](control-check-box.md)**, **[Rullegardin](control-drop-down.md)**, **[Galleri](control-gallery.md)**, **[Listeboks](control-list-box.md)**, **[Radio](control-radio.md)**, **[Vurdering](control-rating.md)**, **[Glidebryter](control-slider.md)**, **[Tekstinndata](control-text-input.md)** og **[Veksleknapp](control-toggle.md)**.

**DelayOutput** – angis som sann for å forsinke en handling ved tekstinndata.

* Gjelder kontrollene **[Tekstinndata](control-text-input.md)** og **[Kort](control-card.md)**

**DisplayMode** – verdiene kan være **Rediger, Vis,** eller **Deaktivert**. Konfigurerer om kontrollen tillater brukerinndata (**Rediger**), bare viser data (**Vis**) eller er Deaktivert (**Deaktivert**).  I **Vis**-modus viser inndatakontroller som **[Tekstinndata](control-text-input.md)**, **[Rullegardin](control-drop-down.md)** og **[Datovelger](control-date-picker.md)** bare tekstverdien og gjengir ikke eventuelle interaktive elementer eller dekorasjoner.  Dette gjør dem egnet til å vises i skjemaer eller som lesbare utdata.

* Gjelder kontrollene **[Legg til bilde](control-add-picture.md)**, **[Lyd](control-audio-video.md)**, **[Knapp](control-button.md)**, **[Kamera](control-camera.md)**, **[Avmerkingsboks](control-check-box.md)**, **[Stolpediagram](control-column-line-chart.md)**, **[Datovelger](control-date-picker.md)**, **[Rullegardin](control-drop-down.md)**, **[Eksporter](control-export-import.md)**, **[Galleri](control-gallery.md)**, **[HTML-tekst](control-html-text.md)**, **[Ikon](control-shapes-icons.md)**, **[Bilde](control-image.md)**, **[Importer](control-export-import.md)**, **[Etikett](control-text-box.md)**, **[Linjediagram](control-column-line-chart.md)**, **[Listeboks](control-list-box.md)**, **[Mikrofon](control-microphone.md)**, **[PDF-visningsprogram](control-pdf-viewer.md)**, **[Penneinndata](control-pen-input.md)**, **[Sektordiagram](control-pie-chart.md)**, **[Radio](control-radio.md)**, **[Vurdering](control-rating.md)**, **[Figur](control-shapes-icons.md)**, **[Glidebryter](control-slider.md)**, **[Tekstinndata](control-text-input.md)**, **[Tidtaker](control-timer.md)**, **[Veksleknapp](control-toggle.md)** og **[Video](control-audio-video.md)**.

**Elementer** – kilden til dataene som vises i en kontroll, for eksempel et galleri, en liste eller et diagram.

* Gjelder kontrollene **[Stolpediagram](control-column-line-chart.md)**, **[Rullegardin](control-drop-down.md)**, **[Galleri](control-gallery.md)**, **[Linjediagram](control-column-line-chart.md)**, **[Listeboks](control-list-box.md)**, **[Sektordiagram](control-pie-chart.md)** og **[Radio](control-radio.md)**.

**OnChange** – hvordan appen reagerer når brukeren endrer verdien for en kontroll (for eksempel ved å justere en glidebryter).

* Gjelder kontrollene **[Legg til bilde](control-add-picture.md)**, **[Rullegardin](control-drop-down.md)**, **[Listeboks](control-list-box.md)**, **[Radio](control-radio.md)**, **[Vurdering](control-rating.md)**, **[Glidebryter](control-slider.md)**, **[Tekstinndata](control-text-input.md)** og **[Veksleknapp](control-toggle.md)**.

**OnSelect** – hvordan appen reagerer når brukeren klikker eller trykker på en kontroll.

* Gjelder kontrollene **[Legg til bilde](control-add-picture.md)**, **[Knapp](control-button.md)**, **[Kamera](control-camera.md)**, **[Avmerkingsboks](control-check-box.md)**, **[Stolpediagram](control-column-line-chart.md)**, **[Datovelger](control-date-picker.md)**, **[Rullegardin](control-drop-down.md)**, **[Eksporter](control-export-import.md)**, **[HTML-tekst](control-html-text.md)**, **[Ikon](control-shapes-icons.md)**, **[Bilde](control-image.md)**, **[Import](control-export-import.md)**, **[Etikett](control-text-box.md)**, **[Linjediagram](control-column-line-chart.md)**, **[Listeboks](control-list-box.md)**, **[Mikrofon](control-microphone.md)**, **[PDF-visningsprogram](control-pdf-viewer.md)**, **[Penneinndata](control-pen-input.md)**, **[Sektordiagram](control-pie-chart.md)**, **[Radio](control-radio.md)**, **[Vurdering](control-rating.md)**, **[Figur](control-shapes-icons.md)**, **[Glidebryter](control-slider.md)**, **[Tekstinndata](control-text-input.md)**, **[Tidtaker](control-timer.md)** og **[Veksleknapp](control-toggle.md)**.

**Tilbakestill** – hvorvidt en kontroll tilbakestilles til standardverdien.  Se også **[Tilbakestill](../functions/function-reset.md)**-funksjonen.

* Gjelder kontrollene **[Lyd](control-audio-video.md)**, **[Avmerkingsboks](control-check-box.md)**, **[Rullegardin](control-drop-down.md)**, **[Listeboks](control-list-box.md)**, **[Mikrofon](control-microphone.md)**, **[Radio](control-radio.md)**, **[Vurdering](control-rating.md)**, **[Glidebryter](control-slider.md)**, **[Tekstinndata](control-text-input.md)**, **[Tidtaker](control-timer.md)**, **[Veksleknapp](control-toggle.md)** og **[Video](control-audio-video.md)**.

**Tekst** – Tekst som vises på en kontroll eller som brukeren skriver inn i en kontroll.

* Gjelder kontrollene **[Legg til bilde](control-add-picture.md)**, **[Knapp](control-button.md)**, **[Avmerkingsboks](control-check-box.md)**, **[Eksporter](control-export-import.md)**, **[Importer](control-export-import.md)**, **[Etikett](control-text-box.md)**, **[Tekstinndata](control-text-input.md)** og **[Tidtaker](control-timer.md)**.

**Verktøytips** – Forklarende tekst som vises når brukeren holder pekeren over en kontroll.

* Gjelder kontrollene **[Lyd](control-audio-video.md)**, **[Knapp](control-button.md)**, **[Kamera](control-camera.md)**, **[Avmerkingsboks](control-check-box.md)**, **[Rullegardin](control-drop-down.md)**, **[HTML-tekst](control-html-text.md)**, **[Bilde](control-image.md)**, **[Etikett](control-text-box.md)**, **[Listeboks](control-list-box.md)**, **[Mikrofon](control-microphone.md)**, **[PDF-visningsprogram](control-pdf-viewer.md)**, **[Penneinndata](control-pen-input.md)**, **[Radio](control-radio.md)**, **[Vurdering](control-rating.md)**, **[Glidebryter](control-slider.md)**, **[Tekstinndata](control-text-input.md)**, **[Tidtaker](control-timer.md)**, **[Veksleknapp](control-toggle.md)** og **[Video](control-audio-video.md)**.

**Verdi** – Verdien til en inndatakontroll.

* Gjelder kontrollene **[Avmerkingsboks](control-check-box.md)**, **[Radio](control-radio.md)**, **[Glidebryter](control-slider.md)** og **[Veksleknapp](control-toggle.md)**.

**Synlig** – om en kontroll vises eller er skjult.

* Gjelder kontrollene **[Legg til bilde](control-add-picture.md)**, **[Lyd](control-audio-video.md)**, **[Knapp](control-button.md)**, **[Kamera](control-camera.md)**, **[Kort](control-card.md)**, **[Avmerkingsboks](control-check-box.md)**, **[Stolpediagram](control-column-line-chart.md)**, **[Datovelger](control-date-picker.md)**, **[Visningsskjema](control-form-detail.md)**, **[Rullegardin](control-drop-down.md)**, **[Redigeringsskjema](control-form-detail.md)**, **[Eksporter](control-export-import.md)**, **[Galleri](control-gallery.md)**, **[HTML-tekst](control-html-text.md)**, **[Ikon](control-shapes-icons.md)**, **[Bilde](control-image.md)**, **[Importer](control-export-import.md)**, **[Etikett](control-text-box.md)**, **[Linjediagram](control-column-line-chart.md)**, **[Listeboks](control-list-box.md)**, **[Mikrofon](control-microphone.md)**, **[PDF-visningsprogram](control-pdf-viewer.md)**, **[Penneinndata](control-pen-input.md)**, **[Sektordiagram](control-pie-chart.md)**, **[Radio](control-radio.md)**, **[Vurdering](control-rating.md)**, **[Figur](control-shapes-icons.md)**, **[Glidebryter](control-slider.md)**, **[Tekstinndata](control-text-input.md)**, **[Tidtaker](control-timer.md)**, **[Veksleknapp](control-toggle.md)** og **[Video](control-audio-video.md)**.

