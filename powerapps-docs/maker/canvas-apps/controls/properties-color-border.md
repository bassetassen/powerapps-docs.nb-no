---
title: Egenskaper for farge og kantlinje | Microsoft Docs
description: Referanseinformasjon om egenskaper som BorderColor, HoverBorderColor og PressedBorderColor
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
ms.openlocfilehash: 2f17dd975a5b8320f4b67688ab986c4e8cc98514
ms.sourcegitcommit: 21163a6d77b784f4864fce4695776c9b4652cb29
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 05/26/2019
ms.locfileid: "66225150"
---
# <a name="color-and-border-properties-in-powerapps"></a>Egenskaper for farge og kantlinje i PowerApps

## <a name="overview"></a>Oversikt

Konfigurere stilen for en kontroll basert på hvordan brukeren samhandler med den.

Du kan angi farger på mange måter:

- [**Farge** ](../functions/function-colors.md) opplistingen: Angi fargenavn fra gjennomgripende stilark, som i disse eksemplene:

  - **Color.Red**
  - **Color.Indigo**

- [**ColorValue** ](../functions/function-colors.md) funksjonen: Angi tekststrenger som for eksempel fargenavn fra gjennomgripende stilark og hex-kode notasjon (**#**), som i disse eksemplene:

  - **ColorValue («skifergrå»)**
  - **ColorValue( "#ff00ff" )**

- [**ColorFade** ](../functions/function-colors.md) funksjonen: Angi hvordan med. en farge er, fra fullstendig svart (-100%) til fullstendig hvit (100%), som i dette eksemplet:

  - **ColorFade (Color.Red, 50%)**

- [**RGBA** ](../functions/function-colors.md) funksjonen: Angi røde, grønne og blå komponentene i en farge fra 0 til 255, og angi en alfa kanal fra 0% (helt gjennomsiktig) til 100% (helt ugjennomsiktig), som i dette eksemplet:

  - **RGBA (255, 0, 255, 25%)**

Fargeegenskaper for kan også referere til andre fargeegenskaper. For eksempel **Label.PressedColor** kan være satt til formelen **Label1.Color**, automatisk gjennomgripende en endring fra én egenskap til en annen.

## <a name="normal"></a>Normal

Disse egenskapene iverksettes vanligvis når brukeren ikke samhandler med kontrollen.

**BorderColor** – fargen på kontrollens kantlinje.

- Gjelder kontrollene **[Legg til bilde](control-add-picture.md)**, **[Lyd](control-audio-video.md)**, **[Knapp](control-button.md)**, **[Kamera](control-camera.md)**, **[Kort](control-card.md)**, **[Avmerkingsboks](control-check-box.md)**, **[Stolpediagram](control-column-line-chart.md)**, **[Datovelger](control-date-picker.md)**, **[Visningsskjema](control-form-detail.md)**, **[Rullegardin](control-drop-down.md)**, **[Redigeringsskjema](control-form-detail.md)**, **[Eksporter](control-export-import.md)**, **[Galleri](control-gallery.md)**, **[HTML-tekst](control-html-text.md)**, **[Bilde](control-image.md)**, **[Importer](control-export-import.md)**, **[Etikett](control-text-box.md)**, **[Linjediagram](control-column-line-chart.md)**, **[Listeboks](control-list-box.md)**, **[Mikrofon](control-microphone.md)**, **[PDF-visningsprogram](control-pdf-viewer.md)**, **[Penneinndata](control-pen-input.md)**, **[Sektordiagram](control-pie-chart.md)**, **[Radio](control-radio.md)**, **[Vurdering](control-rating.md)**, **[Glidebryter](control-slider.md)**, **[Tekstinndata](control-text-input.md)**, **[Tidtaker](control-timer.md)**, **[Veksleknapp](control-toggle.md)** og **[Video](control-audio-video.md)**.

**BorderStyle** – hvorvidt kontrollens kantlinje er satt til **Heltrukket**, **Stiplet**, **Prikket** eller **Ingen**.

- Gjelder kontrollene **[Legg til bilde](control-add-picture.md)**, **[Lyd](control-audio-video.md)**, **[Knapp](control-button.md)**, **[Kamera](control-camera.md)**, **[Kort](control-card.md)**, **[Avmerkingsboks](control-check-box.md)**, **[Stolpediagram](control-column-line-chart.md)**, **[Datovelger](control-date-picker.md)**, **[Visningsskjema](control-form-detail.md)**, **[Rullegardin](control-drop-down.md)**, **[Redigeringsskjema](control-form-detail.md)**, **[Eksporter](control-export-import.md)**, **[Galleri](control-gallery.md)**, **[HTML-tekst](control-html-text.md)**, **[Bilde](control-image.md)**, **[Importer](control-export-import.md)**, **[Etikett](control-text-box.md)**, **[Linjediagram](control-column-line-chart.md)**, **[Listeboks](control-list-box.md)**, **[Mikrofon](control-microphone.md)**, **[PDF-visningsprogram](control-pdf-viewer.md)**, **[Penneinndata](control-pen-input.md)**, **[Sektordiagram](control-pie-chart.md)**, **[Radio](control-radio.md)**, **[Vurdering](control-rating.md)**, **[Glidebryter](control-slider.md)**, **[Tekstinndata](control-text-input.md)**, **[Tidtaker](control-timer.md)**, **[Veksleknapp](control-toggle.md)** og **[Video](control-audio-video.md)**.

**BorderThickness** – tykkelsen til kontrollens kantlinje.

- Gjelder kontrollene **[Legg til bilde](control-add-picture.md)**, **[Lyd](control-audio-video.md)**, **[Knapp](control-button.md)**, **[Kamera](control-camera.md)**, **[Kort](control-card.md)**, **[Avmerkingsboks](control-check-box.md)**, **[Stolpediagram](control-column-line-chart.md)**, **[Datovelger](control-date-picker.md)**, **[Visningsskjema](control-form-detail.md)**, **[Rullegardin](control-drop-down.md)**, **[Redigeringsskjema](control-form-detail.md)**, **[Eksporter](control-export-import.md)**, **[Galleri](control-gallery.md)**, **[HTML-tekst](control-html-text.md)**, **[Bilde](control-image.md)**, **[Importer](control-export-import.md)**, **[Etikett](control-text-box.md)**, **[Linjediagram](control-column-line-chart.md)**, **[Listeboks](control-list-box.md)**, **[Mikrofon](control-microphone.md)**, **[PDF-visningsprogram](control-pdf-viewer.md)**, **[Penneinndata](control-pen-input.md)**, **[Sektordiagram](control-pie-chart.md)**, **[Radio](control-radio.md)**, **[Vurdering](control-rating.md)**, **[Glidebryter](control-slider.md)**, **[Tekstinndata](control-text-input.md)**, **[Tidtaker](control-timer.md)**, **[Veksleknapp](control-toggle.md)** og **[Video](control-audio-video.md)**.

**Farge** – fargen på teksten i kontrollen.

- Gjelder kontrollene **[Legg til bilde](control-add-picture.md)**, **[Knapp](control-button.md)**, **[Avmerkingsboks](control-check-box.md)**, **[Stolpediagram](control-column-line-chart.md)**, **[Datovelger](control-date-picker.md)**, **[Rullegardin](control-drop-down.md)**, **[Eksporter](control-export-import.md)**, **[HTML-tekst](control-html-text.md)**, **[Importer](control-export-import.md)**, **[Etikett](control-text-box.md)**, **[Linjediagram](control-column-line-chart.md)**, **[Listeboks](control-list-box.md)**, **[Mikrofon](control-microphone.md)**, **[Penneinndata](control-pen-input.md)**, **[Sektordiagram](control-pie-chart.md)**, **[Radio](control-radio.md)**, **[Tekstinndata](control-text-input.md)** og **[Tidtaker](control-timer.md)**.

**Fyll** – bakgrunnsfargen på kontrollen.

- Gjelder kontrollene **[Legg til bilde](control-add-picture.md)**, **[Lyd](control-audio-video.md)**, **[Knapp](control-button.md)**, **[Kort](control-card.md)**, **[Avmerkingsboks](control-check-box.md)**, **[Datovelger](control-date-picker.md)**, **[Visningsskjema](control-form-detail.md)**, **[Rullegardin](control-drop-down.md)**, **[Redigeringsskjema](control-form-detail.md)**, **[Eksporter](control-export-import.md)**, **[Galleri](control-gallery.md)**, **[HTML-tekst](control-html-text.md)**, **[Ikon](control-shapes-icons.md)**, **[Bilde](control-image.md)**, **[Importer](control-export-import.md)**, **[Etikett](control-text-box.md)**, **[Listeboks](control-list-box.md)**, **[Mikrofon](control-microphone.md)**, **[PDF-visningsprogram](control-pdf-viewer.md)**, **[Penneinndata](control-pen-input.md)**, **[Radio](control-radio.md)**, **[Vurdering](control-rating.md)**, **[Skjerm](control-screen.md)**, **[Figur](control-shapes-icons.md)**, **[Tekstinndata](control-text-input.md)**, **[Tidtaker](control-timer.md)**, **[Veksleknapp](control-toggle.md)** og **[Video](control-audio-video.md)**.

## <a name="focused"></a>Fokusert

Disse egenskapene er aktivert når kontrollen er fokusert.

**FocusedBorderColor** – fargen på kontrollens kantlinje når kontrollen har fokus.

**FocusedBorderThickness** – tykkelsen på kantlinjen for en kontroll når den har fokus.

- Gjelder kontrollene **[Legg til bilde](control-add-picture.md)**, **[Vedlegg](control-attachments.md)**, **[Lyd](control-audio-video.md)**, **[Knapp](control-button.md)**, **[Kamera](control-camera.md)**, **[Avmerkingsboks](control-check-box.md)**, **[Kombinasjonsboks](control-combo-box.md)**, **[Datotvelger](control-date-picker.md)**, **[Rullegardinliste](control-drop-down.md)**, **[Eksporter](control-export-import.md)**, **[Galleri](control-gallery.md)**, **[Ikon](control-shapes-icons.md)**, **[Bilde](control-image.md)**, **[Importer](control-export-import.md)**, **[Etikett](control-text-box.md)**, **[Listeboks](control-list-box.md)**, **[Mikrofon](control-microphone.md)**, **[Radio](control-radio.md)**, **[Vurderinger](control-rating.md)**, **[Figur](control-shapes-icons.md)**, **[Glidebryter](control-slider.md)**, **[Tekstinndata](control-text-input.md)**, **[Tidtaker](control-timer.md)**, **[Veksleknapp](control-toggle.md)**, **[Video](control-audio-video.md)**.

## <a name="disabled"></a>Deaktivert

Disse egenskapene er aktivert når kontrollen er deaktivert.  En kontroll kan bli deaktivert hvis **[Deaktiver](properties-core.md)** -egenskapen er satt til *sann*.

**DisabledBorderColor** – fargen på kontrollens kantlinje hvis kontrollens **[DisplayMode](properties-core.md)**-egenskap er angitt som **Deaktivert**.

- Gjelder kontrollene **[Legg til bilde](control-add-picture.md)**, **[Knapp](control-button.md)**, **[Avmerkingsboks](control-check-box.md)**, **[Stolpediagram](control-column-line-chart.md)**, **[Datovelger](control-date-picker.md)**, **[Rullegardin](control-drop-down.md)**, **[Eksporter](control-export-import.md)**, **[HTML-tekst](control-html-text.md)**, **[Bilde](control-image.md)**, **[Importer](control-export-import.md)**, **[Etikett](control-text-box.md)**, **[Linjediagram](control-column-line-chart.md)**, **[Listeboks](control-list-box.md)**, **[Mikrofon](control-microphone.md)**, **[PDF-visningsprogram](control-pdf-viewer.md)**, **[Sektordiagram](control-pie-chart.md)**, **[Radio](control-radio.md)**, **[Glidebryter](control-slider.md)**, **[Tekstinndata](control-text-input.md)**, **[Tidtaker](control-timer.md)**, **[Veksleknapp](control-toggle.md)**.

**DisabledColor** – fargen på kontrollens tekst hvis kontrollens **[DisplayMode](properties-core.md)**-egenskap er angitt som **Deaktivert**.

- Gjelder kontrollene **[Legg til bilde](control-add-picture.md)**, **[Knapp](control-button.md)**, **[Avmerkingsboks](control-check-box.md)**, **[Datovelger](control-date-picker.md)**, **[Rullegardin](control-drop-down.md)**, **[Eksporter](control-export-import.md)**, **[Importer](control-export-import.md)**, **[Etikett](control-text-box.md)**, **[Listeboks](control-list-box.md)**, **[Mikrofon](control-microphone.md)**, **[Radio](control-radio.md)** og **[Tekstinndata](control-text-input.md)** og **[Tidtaker](control-timer.md)**.

**DisabledFill** – bakgrunnsfargen på kontrollens tekst hvis kontrollens **[DisplayMode](properties-core.md)**-egenskap er angitt som **Deaktivert**.

- Gjelder kontrollene **[Legg til bilde](control-add-picture.md)**, **[Knapp](control-button.md)**, **[Avmerkingsboks](control-check-box.md)**, **[Datovelger](control-date-picker.md)**, **[Rullegardin](control-drop-down.md)**, **[Eksporter](control-export-import.md)**, **[HTML-tekst](control-html-text.md)**, **[Bilde](control-image.md)**, **[Importer](control-export-import.md)**, **[Etikett](control-text-box.md)**, **[Listeboks](control-list-box.md)**, **[Mikrofon](control-microphone.md)**, **[Radio](control-radio.md)**, **[Tekstinndata](control-text-input.md)** og **[Tidtaker](control-timer.md)**.

## <a name="hover"></a>Beveg pekeren

Disse egenskapene er i kraft når brukeren beveger musepekeren over kontrollen.

**HoverBorderColor** – fargen på kontrollens kantlinje når brukeren holder musepekeren over denne kontrollen.

- Gjelder kontrollene **[Legg til bilde](control-add-picture.md)**, **[Knapp](control-button.md)**, **[Avmerkingsboks](control-check-box.md)**, **[Stolpediagram](control-column-line-chart.md)**, **[Rullegardin](control-drop-down.md)**, **[Eksporter](control-export-import.md)**, **[HTML-tekst](control-html-text.md)**, **[Bilde](control-image.md)**, **[Importer](control-export-import.md)**, **[Etikett](control-text-box.md)**, **[Linjediagram](control-column-line-chart.md)**, **[Listeboks](control-list-box.md)**, **[Mikrofon](control-microphone.md)**, **[PDF-visningsprogram](control-pdf-viewer.md)**, **[Sektordiagram](control-pie-chart.md)**, **[Glidebryter](control-slider.md)**, **[Tekstinndata](control-text-input.md)**, **[Tidtaker](control-timer.md)** og **[Veksleknapp](control-toggle.md)**.

**HoverColor** – fargen på en teksten i en kontroll når brukeren holder musepekeren over den.

- Gjelder kontrollene **[Legg til bilde](control-add-picture.md)**, **[Knapp](control-button.md)**, **[Avmerkingsboks](control-check-box.md)**, **[Rullegardin](control-drop-down.md)**, **[Eksporter](control-export-import.md)**, **[Importer](control-export-import.md)**, **[Etikett](control-text-box.md)**, **[Listeboks](control-list-box.md)**, **[Mikrofon](control-microphone.md)**, **[Radio](control-radio.md)**, **[Tekstinndata](control-text-input.md)** og **[Tidtaker](control-timer.md)**.

**HoverFill** – bakgrunnsfargen for en kontroll når brukeren holder musepekeren over den.

- Gjelder kontrollene **[Legg til bilde](control-add-picture.md)**, **[Knapp](control-button.md)**, **[Avmerkingsboks](control-check-box.md)**, **[Rullegardin](control-drop-down.md)**, **[Eksporter](control-export-import.md)**, **[Ikon](control-shapes-icons.md)**, **[Bilde](control-image.md)**, **[Importer](control-export-import.md)**, **[Etikett](control-text-box.md)**, **[Listeboks](control-list-box.md)**, **[Mikrofon](control-microphone.md)**, **[Radio](control-radio.md)**, **[Figur](control-shapes-icons.md)**, **[Tekstinndata](control-text-input.md)** og **[Tidtaker](control-timer.md)**.

## <a name="pressed"></a>Trykket

Disse egenskapene er i kraft når en knapp eller bildekontroll er trykket ned.

**PressedBorderColor** – fargen på kontrollens kantlinje når brukeren trykker eller klikker på kontrollen.

- Gjelder kontrollene **[Legg til bilde](control-add-picture.md)**, **[Knapp](control-button.md)**, **[Avmerkingsboks](control-check-box.md)**, **[Stolpediagram](control-column-line-chart.md)**, **[Rullegardin](control-drop-down.md)**, **[Eksporter](control-export-import.md)**, **[Ikon](control-shapes-icons.md)**, **[Bilde](control-image.md)**, **[Importer](control-export-import.md)**, **[Etikett](control-text-box.md)**, **[Linjediagram](control-column-line-chart.md)**, **[Listeboks](control-list-box.md)**, **[Mikrofon](control-microphone.md)**, **[PDF-visningsprogram](control-pdf-viewer.md)**, **[Sektordiagram](control-pie-chart.md)**, **[Figur](control-shapes-icons.md)**, **[Glidebryter](control-slider.md)**, **[Tekstinndata](control-text-input.md)**, **[Tidtaker](control-timer.md)** og **[Veksleknapp](control-toggle.md)**.

**PressedColor** – fargen på teksten i en kontroll når brukeren trykker eller klikker på kontrollen.

- Gjelder kontrollene **[Legg til bilde](control-add-picture.md)**, **[Knapp](control-button.md)**, **[Avmerkingsboks](control-check-box.md)**, **[Rullegardin](control-drop-down.md)**, **[Eksporter](control-export-import.md)**, **[Importer](control-export-import.md)**, **[Etikett](control-text-box.md)**, **[Listeboks](control-list-box.md)**, **[Mikrofon](control-microphone.md)**, **[Radio](control-radio.md)**, **[Tekstinndata](control-text-input.md)** og **[Tidtaker](control-timer.md)**.

**PressedFil** – bakgrunnsfargen i en kontroll når brukeren trykker eller klikker på kontrollen.

- Gjelder kontrollene **[Legg til bilde](control-add-picture.md)**, **[Knapp](control-button.md)**, **[Avmerkingsboks](control-check-box.md)**, **[Rullegardin](control-drop-down.md)**, **[Eksporter](control-export-import.md)**, **[Bilde](control-image.md)**, **[Importer](control-export-import.md)**, **[Etikett](control-text-box.md)**, **[Listeboks](control-list-box.md)**, **[Mikrofon](control-microphone.md)**, **[Radio](control-radio.md)**, **[Tekstinndata](control-text-input.md)** og **[Tidtaker](control-timer.md)**.

## <a name="selection"></a>Utvalg

Disse egenskapene er i kraft når brukeren velger et element i en kontroll.

**SelectionColor** – tekstfargen for et merket element, elementer i en liste eller fargen på markeringsverktøyet i en pennekontroll.

- Gjelder for kontrollene **[Rullegardin](control-drop-down.md)**, **[Listeboks](control-list-box.md)** og **[Penneinndata](control-pen-input.md)**.

**SelectionFill** – bakgrunnsfargen for et merket element eller elementer i en liste eller et merket område for en pennekontroll.

- Gjelder for kontrollene **[Rullegardin](control-drop-down.md)** og **[Listeboks](control-list-box.md)**.