---
title: Egenskaper for farge og kantlinje | Microsoft Docs
description: Referanseinformasjon om egenskaper som BorderColor, HoverBorderColor og PressedBorderColor
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 10/25/2016
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 528dc54fe18971ff8971b4d0d7e87c3bf3c5367a
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/07/2019
ms.locfileid: "71986037"
---
# <a name="color-and-border-properties-in-powerapps"></a>Egenskaper for farge og kantlinje i PowerApps

## <a name="overview"></a>Oversikt

Konfigurere stilen for en kontroll basert på hvordan brukeren samhandler med den.

Du kan angi farger på mange måter:

- [**Farge**](../functions/function-colors.md) opplisting: Angi farge navn fra gjennom gripende stilark, som i disse eksemplene:

  - **Color.Red**
  - **Color.Indigo**

- [**ColorValue**](../functions/function-colors.md) -funksjon: Angi tekst strenger som farge navn fra gjennom gripende stilark og heksadesimal kode-notasjon ( **#** ), som i disse eksemplene:

  - **ColorValue ("AliceBlue")**
  - **ColorValue( "#ff00ff" )**

- [**ColorFade**](../functions/function-colors.md) -funksjon: Angi hvor nedtonet en farge er, fra helt svart (-100%) til full hvit (100%), som i dette eksemplet:

  - **ColorFade (farge. rød, 50%)**

- [**RGBA**](../functions/function-colors.md) -funksjon: Angi de røde, grønne og blå komponentene i en farge fra 0 til 255, og angi en alfa kanal fra 0% (helt gjennomsiktig) til 100% (fullstendig ugjennomsiktig), som i dette eksemplet:

  - **RGBA (255, 0, 255, 25%)**

Farge egenskaper kan også referere til andre farge egenskaper. **Etikett. PressedColor** kan for eksempel være angitt til formelen **Label1. Color**, som automatisk overlapper en endring fra én egenskap til en annen.

## <a name="normal"></a>Normal

Disse egenskapene iverksettes vanligvis når brukeren ikke samhandler med kontrollen.

**BorderColor** – fargen på kontrollens kantlinje.

- Gjelder kontrollene **[Legg til bilde](control-add-picture.md)** , **[Lyd](control-audio-video.md)** , **[Knapp](control-button.md)** , **[Kamera](control-camera.md)** , **[Kort](control-card.md)** , **[Avmerkingsboks](control-check-box.md)** , **[Stolpediagram](control-column-line-chart.md)** , **[Datovelger](control-date-picker.md)** , **[Visningsskjema](control-form-detail.md)** , **[Rullegardin](control-drop-down.md)** , **[Redigeringsskjema](control-form-detail.md)** , **[Eksporter](control-export-import.md)** , **[Galleri](control-gallery.md)** , **[HTML-tekst](control-html-text.md)** , **[Bilde](control-image.md)** , **[Importer](control-export-import.md)** , **[Etikett](control-text-box.md)** , **[Linjediagram](control-column-line-chart.md)** , **[Listeboks](control-list-box.md)** , **[Mikrofon](control-microphone.md)** , **[PDF-visningsprogram](control-pdf-viewer.md)** , **[Penneinndata](control-pen-input.md)** , **[Sektordiagram](control-pie-chart.md)** , **[Radio](control-radio.md)** , **[Vurdering](control-rating.md)** , **[Glidebryter](control-slider.md)** , **[Tekstinndata](control-text-input.md)** , **[Tidtaker](control-timer.md)** , **[Veksleknapp](control-toggle.md)** og **[Video](control-audio-video.md)** .

**BorderStyle** – hvorvidt kontrollens kantlinje er satt til **Heltrukket**, **Stiplet**, **Prikket** eller **Ingen**.

- Gjelder kontrollene **[Legg til bilde](control-add-picture.md)** , **[Lyd](control-audio-video.md)** , **[Knapp](control-button.md)** , **[Kamera](control-camera.md)** , **[Kort](control-card.md)** , **[Avmerkingsboks](control-check-box.md)** , **[Stolpediagram](control-column-line-chart.md)** , **[Datovelger](control-date-picker.md)** , **[Visningsskjema](control-form-detail.md)** , **[Rullegardin](control-drop-down.md)** , **[Redigeringsskjema](control-form-detail.md)** , **[Eksporter](control-export-import.md)** , **[Galleri](control-gallery.md)** , **[HTML-tekst](control-html-text.md)** , **[Bilde](control-image.md)** , **[Importer](control-export-import.md)** , **[Etikett](control-text-box.md)** , **[Linjediagram](control-column-line-chart.md)** , **[Listeboks](control-list-box.md)** , **[Mikrofon](control-microphone.md)** , **[PDF-visningsprogram](control-pdf-viewer.md)** , **[Penneinndata](control-pen-input.md)** , **[Sektordiagram](control-pie-chart.md)** , **[Radio](control-radio.md)** , **[Vurdering](control-rating.md)** , **[Glidebryter](control-slider.md)** , **[Tekstinndata](control-text-input.md)** , **[Tidtaker](control-timer.md)** , **[Veksleknapp](control-toggle.md)** og **[Video](control-audio-video.md)** .

**BorderThickness** – tykkelsen til kontrollens kantlinje.

- Gjelder kontrollene **[Legg til bilde](control-add-picture.md)** , **[Lyd](control-audio-video.md)** , **[Knapp](control-button.md)** , **[Kamera](control-camera.md)** , **[Kort](control-card.md)** , **[Avmerkingsboks](control-check-box.md)** , **[Stolpediagram](control-column-line-chart.md)** , **[Datovelger](control-date-picker.md)** , **[Visningsskjema](control-form-detail.md)** , **[Rullegardin](control-drop-down.md)** , **[Redigeringsskjema](control-form-detail.md)** , **[Eksporter](control-export-import.md)** , **[Galleri](control-gallery.md)** , **[HTML-tekst](control-html-text.md)** , **[Bilde](control-image.md)** , **[Importer](control-export-import.md)** , **[Etikett](control-text-box.md)** , **[Linjediagram](control-column-line-chart.md)** , **[Listeboks](control-list-box.md)** , **[Mikrofon](control-microphone.md)** , **[PDF-visningsprogram](control-pdf-viewer.md)** , **[Penneinndata](control-pen-input.md)** , **[Sektordiagram](control-pie-chart.md)** , **[Radio](control-radio.md)** , **[Vurdering](control-rating.md)** , **[Glidebryter](control-slider.md)** , **[Tekstinndata](control-text-input.md)** , **[Tidtaker](control-timer.md)** , **[Veksleknapp](control-toggle.md)** og **[Video](control-audio-video.md)** .

**Farge** – fargen på teksten i kontrollen.

- Gjelder kontrollene **[Legg til bilde](control-add-picture.md)** , **[Knapp](control-button.md)** , **[Avmerkingsboks](control-check-box.md)** , **[Stolpediagram](control-column-line-chart.md)** , **[Datovelger](control-date-picker.md)** , **[Rullegardin](control-drop-down.md)** , **[Eksporter](control-export-import.md)** , **[HTML-tekst](control-html-text.md)** , **[Importer](control-export-import.md)** , **[Etikett](control-text-box.md)** , **[Linjediagram](control-column-line-chart.md)** , **[Listeboks](control-list-box.md)** , **[Mikrofon](control-microphone.md)** , **[Penneinndata](control-pen-input.md)** , **[Sektordiagram](control-pie-chart.md)** , **[Radio](control-radio.md)** , **[Tekstinndata](control-text-input.md)** og **[Tidtaker](control-timer.md)** .

**Fyll** – bakgrunnsfargen på kontrollen.

- Gjelder kontrollene **[Legg til bilde](control-add-picture.md)** , **[Lyd](control-audio-video.md)** , **[Knapp](control-button.md)** , **[Kort](control-card.md)** , **[Avmerkingsboks](control-check-box.md)** , **[Datovelger](control-date-picker.md)** , **[Visningsskjema](control-form-detail.md)** , **[Rullegardin](control-drop-down.md)** , **[Redigeringsskjema](control-form-detail.md)** , **[Eksporter](control-export-import.md)** , **[Galleri](control-gallery.md)** , **[HTML-tekst](control-html-text.md)** , **[Ikon](control-shapes-icons.md)** , **[Bilde](control-image.md)** , **[Importer](control-export-import.md)** , **[Etikett](control-text-box.md)** , **[Listeboks](control-list-box.md)** , **[Mikrofon](control-microphone.md)** , **[PDF-visningsprogram](control-pdf-viewer.md)** , **[Penneinndata](control-pen-input.md)** , **[Radio](control-radio.md)** , **[Vurdering](control-rating.md)** , **[Skjerm](control-screen.md)** , **[Figur](control-shapes-icons.md)** , **[Tekstinndata](control-text-input.md)** , **[Tidtaker](control-timer.md)** , **[Veksleknapp](control-toggle.md)** og **[Video](control-audio-video.md)** .

## <a name="focused"></a>Fokusert

Disse egenskapene er aktivert når kontrollen er fokusert.

**FocusedBorderColor** – fargen på kontrollens kantlinje når kontrollen har fokus.

**FocusedBorderThickness** – tykkelsen på kantlinjen for en kontroll når den har fokus.

- Gjelder kontrollene **[Legg til bilde](control-add-picture.md)** , **[Vedlegg](control-attachments.md)** , **[Lyd](control-audio-video.md)** , **[Knapp](control-button.md)** , **[Kamera](control-camera.md)** , **[Avmerkingsboks](control-check-box.md)** , **[Kombinasjonsboks](control-combo-box.md)** , **[Datotvelger](control-date-picker.md)** , **[Rullegardinliste](control-drop-down.md)** , **[Eksporter](control-export-import.md)** , **[Galleri](control-gallery.md)** , **[Ikon](control-shapes-icons.md)** , **[Bilde](control-image.md)** , **[Importer](control-export-import.md)** , **[Etikett](control-text-box.md)** , **[Listeboks](control-list-box.md)** , **[Mikrofon](control-microphone.md)** , **[Radio](control-radio.md)** , **[Vurderinger](control-rating.md)** , **[Figur](control-shapes-icons.md)** , **[Glidebryter](control-slider.md)** , **[Tekstinndata](control-text-input.md)** , **[Tidtaker](control-timer.md)** , **[Veksleknapp](control-toggle.md)** , **[Video](control-audio-video.md)** .

## <a name="disabled"></a>Deaktivert

Disse egenskapene er aktivert når kontrollen er deaktivert.  En kontroll kan bli deaktivert hvis **[Deaktiver](properties-core.md)** -egenskapen er satt til *sann*.

**DisabledBorderColor** – fargen på kontrollens kantlinje hvis kontrollens **[DisplayMode](properties-core.md)** -egenskap er angitt som **Deaktivert**.

- Gjelder kontrollene **[Legg til bilde](control-add-picture.md)** , **[Knapp](control-button.md)** , **[Avmerkingsboks](control-check-box.md)** , **[Stolpediagram](control-column-line-chart.md)** , **[Datovelger](control-date-picker.md)** , **[Rullegardin](control-drop-down.md)** , **[Eksporter](control-export-import.md)** , **[HTML-tekst](control-html-text.md)** , **[Bilde](control-image.md)** , **[Importer](control-export-import.md)** , **[Etikett](control-text-box.md)** , **[Linjediagram](control-column-line-chart.md)** , **[Listeboks](control-list-box.md)** , **[Mikrofon](control-microphone.md)** , **[PDF-visningsprogram](control-pdf-viewer.md)** , **[Sektordiagram](control-pie-chart.md)** , **[Radio](control-radio.md)** , **[Glidebryter](control-slider.md)** , **[Tekstinndata](control-text-input.md)** , **[Tidtaker](control-timer.md)** , **[Veksleknapp](control-toggle.md)** .

**DisabledColor** – fargen på kontrollens tekst hvis kontrollens **[DisplayMode](properties-core.md)** -egenskap er angitt som **Deaktivert**.

- Gjelder kontrollene **[Legg til bilde](control-add-picture.md)** , **[Knapp](control-button.md)** , **[Avmerkingsboks](control-check-box.md)** , **[Datovelger](control-date-picker.md)** , **[Rullegardin](control-drop-down.md)** , **[Eksporter](control-export-import.md)** , **[Importer](control-export-import.md)** , **[Etikett](control-text-box.md)** , **[Listeboks](control-list-box.md)** , **[Mikrofon](control-microphone.md)** , **[Radio](control-radio.md)** og **[Tekstinndata](control-text-input.md)** og **[Tidtaker](control-timer.md)** .

**DisabledFill** – bakgrunnsfargen på kontrollens tekst hvis kontrollens **[DisplayMode](properties-core.md)** -egenskap er angitt som **Deaktivert**.

- Gjelder kontrollene **[Legg til bilde](control-add-picture.md)** , **[Knapp](control-button.md)** , **[Avmerkingsboks](control-check-box.md)** , **[Datovelger](control-date-picker.md)** , **[Rullegardin](control-drop-down.md)** , **[Eksporter](control-export-import.md)** , **[HTML-tekst](control-html-text.md)** , **[Bilde](control-image.md)** , **[Importer](control-export-import.md)** , **[Etikett](control-text-box.md)** , **[Listeboks](control-list-box.md)** , **[Mikrofon](control-microphone.md)** , **[Radio](control-radio.md)** , **[Tekstinndata](control-text-input.md)** og **[Tidtaker](control-timer.md)** .

## <a name="hover"></a>Beveg pekeren

Disse egenskapene er i kraft når brukeren beveger musepekeren over kontrollen.

**HoverBorderColor** – fargen på kontrollens kantlinje når brukeren holder musepekeren over denne kontrollen.

- Gjelder kontrollene **[Legg til bilde](control-add-picture.md)** , **[Knapp](control-button.md)** , **[Avmerkingsboks](control-check-box.md)** , **[Stolpediagram](control-column-line-chart.md)** , **[Rullegardin](control-drop-down.md)** , **[Eksporter](control-export-import.md)** , **[HTML-tekst](control-html-text.md)** , **[Bilde](control-image.md)** , **[Importer](control-export-import.md)** , **[Etikett](control-text-box.md)** , **[Linjediagram](control-column-line-chart.md)** , **[Listeboks](control-list-box.md)** , **[Mikrofon](control-microphone.md)** , **[PDF-visningsprogram](control-pdf-viewer.md)** , **[Sektordiagram](control-pie-chart.md)** , **[Glidebryter](control-slider.md)** , **[Tekstinndata](control-text-input.md)** , **[Tidtaker](control-timer.md)** og **[Veksleknapp](control-toggle.md)** .

**HoverColor** – fargen på en teksten i en kontroll når brukeren holder musepekeren over den.

- Gjelder kontrollene **[Legg til bilde](control-add-picture.md)** , **[Knapp](control-button.md)** , **[Avmerkingsboks](control-check-box.md)** , **[Rullegardin](control-drop-down.md)** , **[Eksporter](control-export-import.md)** , **[Importer](control-export-import.md)** , **[Etikett](control-text-box.md)** , **[Listeboks](control-list-box.md)** , **[Mikrofon](control-microphone.md)** , **[Radio](control-radio.md)** , **[Tekstinndata](control-text-input.md)** og **[Tidtaker](control-timer.md)** .

**HoverFill** – bakgrunnsfargen for en kontroll når brukeren holder musepekeren over den.

- Gjelder kontrollene **[Legg til bilde](control-add-picture.md)** , **[Knapp](control-button.md)** , **[Avmerkingsboks](control-check-box.md)** , **[Rullegardin](control-drop-down.md)** , **[Eksporter](control-export-import.md)** , **[Ikon](control-shapes-icons.md)** , **[Bilde](control-image.md)** , **[Importer](control-export-import.md)** , **[Etikett](control-text-box.md)** , **[Listeboks](control-list-box.md)** , **[Mikrofon](control-microphone.md)** , **[Radio](control-radio.md)** , **[Figur](control-shapes-icons.md)** , **[Tekstinndata](control-text-input.md)** og **[Tidtaker](control-timer.md)** .

## <a name="pressed"></a>Trykket

Disse egenskapene er i kraft når en knapp eller bildekontroll er trykket ned.

**PressedBorderColor** – fargen på kontrollens kantlinje når brukeren trykker eller klikker på kontrollen.

- Gjelder kontrollene **[Legg til bilde](control-add-picture.md)** , **[Knapp](control-button.md)** , **[Avmerkingsboks](control-check-box.md)** , **[Stolpediagram](control-column-line-chart.md)** , **[Rullegardin](control-drop-down.md)** , **[Eksporter](control-export-import.md)** , **[Ikon](control-shapes-icons.md)** , **[Bilde](control-image.md)** , **[Importer](control-export-import.md)** , **[Etikett](control-text-box.md)** , **[Linjediagram](control-column-line-chart.md)** , **[Listeboks](control-list-box.md)** , **[Mikrofon](control-microphone.md)** , **[PDF-visningsprogram](control-pdf-viewer.md)** , **[Sektordiagram](control-pie-chart.md)** , **[Figur](control-shapes-icons.md)** , **[Glidebryter](control-slider.md)** , **[Tekstinndata](control-text-input.md)** , **[Tidtaker](control-timer.md)** og **[Veksleknapp](control-toggle.md)** .

**PressedColor** – fargen på teksten i en kontroll når brukeren trykker eller klikker på kontrollen.

- Gjelder kontrollene **[Legg til bilde](control-add-picture.md)** , **[Knapp](control-button.md)** , **[Avmerkingsboks](control-check-box.md)** , **[Rullegardin](control-drop-down.md)** , **[Eksporter](control-export-import.md)** , **[Importer](control-export-import.md)** , **[Etikett](control-text-box.md)** , **[Listeboks](control-list-box.md)** , **[Mikrofon](control-microphone.md)** , **[Radio](control-radio.md)** , **[Tekstinndata](control-text-input.md)** og **[Tidtaker](control-timer.md)** .

**PressedFil** – bakgrunnsfargen i en kontroll når brukeren trykker eller klikker på kontrollen.

- Gjelder kontrollene **[Legg til bilde](control-add-picture.md)** , **[Knapp](control-button.md)** , **[Avmerkingsboks](control-check-box.md)** , **[Rullegardin](control-drop-down.md)** , **[Eksporter](control-export-import.md)** , **[Bilde](control-image.md)** , **[Importer](control-export-import.md)** , **[Etikett](control-text-box.md)** , **[Listeboks](control-list-box.md)** , **[Mikrofon](control-microphone.md)** , **[Radio](control-radio.md)** , **[Tekstinndata](control-text-input.md)** og **[Tidtaker](control-timer.md)** .

## <a name="selection"></a>Utvalg

Disse egenskapene er i kraft når brukeren velger et element i en kontroll.

**SelectionColor** – tekstfargen for et merket element, elementer i en liste eller fargen på markeringsverktøyet i en pennekontroll.

- Gjelder for kontrollene **[Rullegardin](control-drop-down.md)** , **[Listeboks](control-list-box.md)** og **[Penneinndata](control-pen-input.md)** .

**SelectionFill** – bakgrunnsfargen for et merket element eller elementer i en liste eller et merket område for en pennekontroll.

- Gjelder for kontrollene **[Rullegardin](control-drop-down.md)** og **[Listeboks](control-list-box.md)** .