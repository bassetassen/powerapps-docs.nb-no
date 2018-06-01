---
title: Finn en egenskap | Microsoft Docs
description: Finn egenskaper sortert etter kontroll, kategori eller alfabetisk.
services: ''
suite: powerapps
documentationcenter: na
author: gregli-msft
manager: anneta
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/17/2016
ms.author: gregli
ms.openlocfilehash: 11f3a29989057a3dc1a75c40877314596a62859d
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/22/2018
ms.locfileid: "30998012"
---
# <a name="controls-and-properties-in-powerapps"></a>Kontroller og egenskaper i PowerApps
Konfigurer utseendet og virkemåten til en kontroll ved å angi en av egenskapene for den. Hver kontrolltype har forskjellige egenskaper. Enkelte egenskaper, som **Height** og **Width** er tilgjengelig for nesten alle typer kontroller, men andre egenskaper som **CheckboxSize** er spesifikke for én type kontroll.

## <a name="controls"></a>Kontroller
**[Legg til bilde](controls/control-add-picture.md)** – laster inn bilder fra den lokale enheten, for opplasting til en datakilde.

**[Vedlegg](controls/control-attachments.md)** – last ned og opp filer fra den lokale enheten til en datakilde.

**[Lyd](controls/control-audio-video.md)** – spill av et lydklipp eller lyddelen av et videoklipp.

**[Strekkodeleser (eksperimentell)](controls/control-barcodescanner.md)** – skann en strekkode ved hjelp av en enhet som har et kamera.

**[Knapp](controls/control-button.md)** – samhandle med appen ved å klikke eller trykke.

**[Kamera](controls/control-camera.md)** – ta og lagre bilder i appen eller til en datakilde.

**[Kort](controls/control-card.md)** – vis og rediger ett enkelt felt for en oppføring i en **[Redigeringsskjema](controls/control-form-detail.md)**- eller **[Visningsskjema](controls/control-form-detail.md)**-kontroll.

**[Avmerkingsboks](controls/control-check-box.md)**  – merk av eller fjern et alternativ for å angi **sann** eller **usann**.

**[Stolpediagram](controls/control-column-line-chart.md)**  – vis verdier som loddrette stolper i forhold til to akser.

**[Kolonne](controls/control-column.md)** – leverer visningsopplevelsen for et enkelt felt i en [**Datatabell**](controls/control-data-table.md)-kontroll.

**[Kombinasjonsboks](controls/control-combo-box.md)** – en kontroll som gjør det mulig for brukere å foreta valg ut fra angitte valgmuligheter. Støtter søk og flervalg.

**[Datatabell](controls/control-data-table.md)** – vis data i et tabellformat.

**[Datovelger](controls/control-date-picker.md)** – angi en dato ved å klikke eller berøre.

**[Visningsskjema](controls/control-form-detail.md)** – vis poster i en datakilde ved hjelp av et skjema.

**[Rullegardin](controls/control-drop-down.md)** – vis det første elementet i en liste til et vinkeltegn er valgt.

**[Rediger skjema](controls/control-form-detail.md)** – rediger og opprett poster i en datakilde ved hjelp av et skjema.

**[Enhetsskjema](entity-form-control.md)** – eksperimentell funksjon: legg til dynamiske skjemaer der brukere kan vise, navigere og redigere relasjonelle data fra Common Data Service.

**[Eksporter](controls/control-export-import.md)** – eksporter data for bruk et annet sted i PowerApps.

**[Galleri](controls/control-gallery.md)** – vis en liste over poster som kan inneholde flere typer data.

**[HTML-tekst](controls/control-html-text.md)** – konverter HTML-koder automatisk.

**[Ikon](controls/control-shapes-icons.md)** – legg til tiltalende grafikk og visuelt engasjement.

**[Bilde](controls/control-image.md)** – en kontroll som viser et bilde, for eksempel fra en lokal fil eller en datakilde.

**[Importer](controls/control-export-import.md)** – importer data fra et annet sted i PowerApps.

**[Linjediagram](controls/control-column-line-chart.md)** – vis verdier som datapunkter i forhold til to akser.

**[Listeboks](controls/control-list-box.md)** – velg ett eller flere elementer i en liste.

**[Mikrofon](controls/control-microphone.md)** – spill inn og lagre lyder i appen eller til en datakilde.

**[Visningsprogram for PDF (eksperimentell)](controls/control-pdf-viewer.md)** – vis innholdet i en PDF-fil på Internett.

**[Penneinndata](controls/control-pen-input.md)** – tegn et bilde eller skriv inn tekst, og lagre inndataene i appen eller til en datakilde.

**[Sektordiagram](controls/control-pie-chart.md)** – vis hvordan verdier er relatert til hverandre.

**[Power BI-flis](controls/control-power-bi-tile.md)** – vis en Power BI-flis i en app.

**[Alternativknapp](controls/control-radio.md)** – vis alternativer som utelukker hverandre.

**[Vurdering](controls/control-rating.md)** – angi en verdi mellom 1 og et angitt tall.

**[Skjerm](controls/control-screen.md)** – vis og oppdater data om en bestemt aktivitet.

**[Figur](controls/control-shapes-icons.md)** – vis piler og geometriske former, for eksempel rektangler.

**[Glidebryter](controls/control-slider.md)** – angi en verdi ved å dra et håndtak.

**[Etikett](controls/control-text-box.md)** – en boks som viser data som tekst, tall, datoer eller valuta.

**[Tekstinndata](controls/control-text-input.md)** – et felt hvor brukere kan skrive tekst, tall og andre data.

**[Tidtaker](controls/control-timer.md)** – konfigurer appen til å svare etter en angitt tidsperiode.

**[Veksleknapp](controls/control-toggle.md)** – dra i et håndtak for å angi **sann** eller **usann**.

**[Video](controls/control-audio-video.md)** – spill av et videoklipp fra en lokal fil, en datakilde eller YouTube.

## <a name="common-properties-by-category"></a>Vanlige egenskaper etter kategori
**[Farge og kantlinje](controls/properties-color-border.md)** – konfigurer fargen og kantlinjen på en kontroll som kan endres når en bruker samhandler med den.

**[Kjerne](controls/properties-core.md)** – konfigurer hvorvidt brukeren kan se og samhandle med en kontroll.

**[Bilde](controls/properties-visual.md)** – konfigurer hvilket bilde som skal vises og hvordan det fyller kontrollen.

**[Størrelse og plassering](controls/properties-size-location.md)** – konfigurer hvor stor en kontroll (eller et element i en kontroll) er, og hvor den/det er i forhold til skjermen det vises på.

**[Tekst](controls/properties-text.md)** – konfigurer hvordan teksten vises i kontroller, for eksempel skriftegenskaper, justering, linjehøyde.  

## <a name="all-properties"></a>Alle egenskaper
### <a name="a"></a>A
**[ActualZoom](controls/control-pdf-viewer.md)** – den faktiske zoomingen for kontrollen, hvor zoomingen som er forespurt kan skille seg fra **Zoom**-egenskapen.  Gjelder for kontrollen for **[Visningsprogram for PDF](controls/control-pdf-viewer.md)**.

**[Juster](controls/properties-text.md)** – plasseringen av teksten i forhold til den vannrette midten av kontrollen.  Gjelder for mange kontroller.

**[AllItems](controls/control-gallery.md)** – alle elementene i et galleri, inkludert ekstra kontroll-verdier som er en del av malen i galleriet.  Gjelder for **[Gallery](controls/control-gallery.md)**-kontrollen.

**AutoDisableOnSelect** – deaktiverer kontrollen automatisk mens OnSelect-virkemåten kjøres.  Gjelder for kontrollene **[Knapp](controls/control-button.md)** og **[Bilde](controls/control-image.md)**.

**[AutoHeight](controls/properties-size-location.md)** – om en etikett automatisk øker i høyde hvis **[Text](controls/properties-core.md)**-egenskapen inneholder flere tegn enn kontrollen kan vise. Gjelder for **[Etikett](controls/control-text-box.md)**-kontrollen.

**AutoPause** – om et lyd- eller videoklipp stanses automatisk hvis brukeren navigerer til en annen skjerm.  Gjelder for kontrollene **[Lyd](controls/control-audio-video.md)**, **[Tidtaker](controls/control-timer.md)** og **[Video](controls/control-audio-video.md)**.

**AutoStart** – om en lyd- eller videokontroll automatisk begynner å spille av et klipp når brukeren navigerer til skjermen som inneholder denne kontrollen.  Gjelder for kontrollene **[Lyd](controls/control-audio-video.md)**, **[Tidtaker](controls/control-timer.md)** og **[Video](controls/control-audio-video.md)**.

### <a name="b"></a>B
**[BackgroundImage](controls/properties-visual.md)** – navnet på en bildefil som vises i bakgrunnen på en skjerm.  Gjelder for **[Skjerm](controls/control-screen.md)**-kontrollen.

**[BorderColor](controls/properties-color-border.md)** – fargen på kontrollens kantlinje.  Gjelder for mange kontroller.

**[BorderStyle](controls/properties-color-border.md)** – om kontrollens kantlinje er satt til **Heltrukket**, **Stiplet**, **Prikket** eller **Ingen**.  Gjelder for mange kontroller.

**[BorderThickness](controls/properties-color-border.md)** – tykkelsen til kontrollens kantlinje.  Gjelder for mange kontroller.

**[Brightness](controls/control-camera.md)** – hvor mye lys brukeren sannsynligvis oppfatter i et bilde.  Gjelder for **[Kamera](controls/control-camera.md)**-kontrollen.

### <a name="c"></a>C
**[CalculateOriginalDimensions](controls/control-image.md)** – aktiverer egenskapene **[OriginalHeight](controls/control-image.md)** og **[OriginalWidth](controls/control-image.md)**.  Gjelder for **[Bilde](controls/control-image.md)**-kontrollen.

**[Kamera](controls/control-camera.md)** – ID-nummeret til kameraet som appen bruker for enheter med mer enn ett kamera.  Gjelder for **[Kamera](controls/control-camera.md)**-kontrollen.

**[CheckboxBackgroundFill](controls/control-check-box.md)** – bakgrunnsfargen i boksen som omgir haken i en avmerkingsboks.  Gjelder for **[Avmerkingsboks](controls/control-check-box.md)**-kontrollen.

**[CheckboxBorderColor](controls/control-check-box.md)** – fargen på rammen som omgir haken i en avmerkingsboks-kontroll.  Gjelder for **[Avmerkingsboks](controls/control-check-box.md)**-kontrollen.

**[CheckboxSize](controls/control-check-box.md)** – bredden og høyden på boksen som omgir haken i en avmerkingsboks-kontroll.  Gjelder for **[Avmerkingsboks](controls/control-check-box.md)**-kontrollen.

**[CheckmarkFill](controls/control-check-box.md)** – fargen på haken i en avmerkingsboks-kontroll.  Gjelder for **[Avmerkingsboks](controls/control-check-box.md)**-kontrollen.

**[ChevronBackground](controls/control-drop-down.md)**  – fargen bak den nedovervendte pilen i en rullegardinliste.  Gjelder for **[Rullegardin](controls/control-drop-down.md)**-kontrollen.

**[ChevronFill](controls/control-drop-down.md)** – fargen på den nedovervendte pilen i en rullegardinliste.  Gjelder for **[Rullegardin](controls/control-drop-down.md)**-kontrollen.

**[Fjern](controls/control-text-input.md)** – om en tekstinndatakontroll viser en "X" som brukeren kan trykke eller klikke på for å fjerne innholdet i den aktuelle kontrollen.  Gjelder for **[Tekstinndata](controls/control-text-input.md)**-kontrollen.

**[Color](controls/properties-color-border.md)**  – fargen på teksten i kontrollen.  Gjelder for mange kontroller.

**[Contrast](controls/control-camera.md)** – hvor enkelt brukeren kan skille mellom lignende farger i et bilde.  Gjelder for **[Kamera](controls/control-camera.md)**-kontrollen.

**[CurrentFindText](controls/control-pdf-viewer.md)** – det gjeldende søkeordet som er i bruk.  Gjelder for kontrollen for **[Visningsprogram for PDF](controls/control-pdf-viewer.md)**.

**[CurrentPage](controls/control-pdf-viewer.md)** – nummeret på siden i en PDF-fil som faktisk vises.  Gjelder for kontrollen for **[Visningsprogram for PDF](controls/control-pdf-viewer.md)**.

### <a name="d"></a>D
**[Data](controls/control-export-import.md)** – navnet på en samling som du vil eksportere til en lokal fil.  Gjelder for **[Eksporter](controls/control-export-import.md)**-kontrollen.

**[DataField](controls/control-card.md)** – navnet på feltet i en post som dette kortet viser og redigerer.  Gjelder for **[Kort](controls/control-card.md)**-kontrollen.

**[DataSource](controls/control-form-detail.md)** – datakilden som inneholder posten brukeren vil vise, redigere eller opprette.  Gjelder for kontroller for **[Redigeringsskjema](controls/control-form-detail.md)** og **[Visningsskjema](controls/control-form-detail.md)**.

**[Default](controls/properties-core.md)** – startverdien for en kontroll før den er endret av brukeren.  Gjelder for mange kontroller.

**[DefaultDate](controls/control-date-picker.md)** – startverdien for en kontroll før den er endret av brukeren.  Gjelder for **[Datovelger](controls/control-date-picker.md)**-kontrollen.

**[DefaultMode](controls/control-form-detail.md)** – standardmodusen for en skjemakontroll, enten **Rediger**, **Ny** eller **Vis**.  Gjelder for **[Redigeringsskjema](controls/control-form-detail.md)**-kontrollen.

**[Retning](controls/control-gallery.md)** – om det første elementet i et galleri i liggende retning vises nær venstre eller høyre kant.  Gjelder for **[Gallery](controls/control-gallery.md)**-kontrollen.

**[Deaktivert](controls/properties-core.md)** – om brukeren kan samhandle med kontrollen.  Gjelder for mange kontroller.

**[DisabledBorderColor](controls/properties-color-border.md)** – fargen på kontrollens kantlinje hvis kontrollens **[Disabled](controls/properties-core.md)**-egenskap er angitt som **sann**.  Gjelder for mange kontroller.

**[DisabledColor](controls/properties-color-border.md)** – fargen på kontrollens tekst hvis kontrollens **[Disabled](controls/properties-core.md)**-egenskap er angitt som **sann**.  Gjelder for mange kontroller.

**[DisabledFill](controls/properties-color-border.md)** – bakgrunnsfargen på en kontroll hvis **[Disabled](controls/properties-core.md)**-egenskapen er angitt som **sann**.  Gjelder for mange kontroller.

**[DisplayName](controls/control-card.md)** – brukervennlig navn for et felt i en datakilde.  Gjelder for **[Kort](controls/control-card.md)**-kontrollen.

**[DisplayMode](controls/properties-core.md)** – verdiene kan være Rediger (Edit), Vis (View), eller Deaktivert (Disabled). Konfigurerer om kontrollen tillater brukerinndata (Edit), bare viser data (View) eller er deaktivert (Disabled).

**[Dokument](controls/control-pdf-viewer.md)** – nettadressen, omsluttet av doble anførselstegn, for en PDF-fil.  Gjelder for kontrollen for **[Visningsprogram for PDF](controls/control-pdf-viewer.md)**.

**[Varighet](controls/control-timer.md)** – hvor lenge en tidtaker kjører.  Gjelder for **[Tidtaker](controls/control-timer.md)**-kontrollen.

### <a name="e"></a>E
**[EndYear](controls/control-date-picker.md)** – det siste året som brukeren kan angi verdien for i en datovelger-kontroll.  Gjelder for **[Datovelger](controls/control-date-picker.md)**-kontrollen.

**Error** – betydningen av denne egenskapen er avhengig av kontrollen:

* **[Legg til bilde](controls/control-add-picture.md)**-kontrollen – hvis det oppstår et problem ved opplasting av et bilde, består denne egenskapen av en streng med en tilhørende feilmelding.
* **[Kort](controls/control-card.md)**-kontrollen – den brukervennlige feilmeldingen som vises for dette feltet når validering mislykkes.
* **[Redigeringsskjema](controls/control-form-detail.md)**-kontrollen – en brukervennlig feilmelding som vises for dette skjemaet når **[SubmitForm](functions/function-form.md)**-funksjonen mislykkes.

**[ErrorKind](controls/control-form-detail.md)** – hvis det oppstår en feil når **SubmitForm** kjører, viser dette typen feil som har oppstått.  Gjelder for kontroller for **[Redigeringsskjema](controls/control-form-detail.md)** og **[Visningsskjema](controls/control-form-detail.md)**.

**[Explode](controls/control-pie-chart.md)** – avstanden mellom stykker i et sektordiagram.  Gjelder for **[Sektordiagram](controls/control-pie-chart.md)**-kontrollen.

### <a name="f"></a>F
**[Fyll](controls/properties-color-border.md)** – bakgrunnsfargen på kontrollen.  Gjelder for mange kontroller.

**[FindNext](controls/control-pdf-viewer.md)** – finner neste forekomst av **FindText** i dokumentet.  Gjelder for kontrollen for **[Visningsprogram for PDF](controls/control-pdf-viewer.md)**.

**[FindPrevious](controls/control-pdf-viewer.md)** – finner forrige forekomst av **FindText** i dokumentet.  Gjelder for kontrollen for **[Visningsprogram for PDF](controls/control-pdf-viewer.md)**.

**[FindText](controls/control-pdf-viewer.md)** – søkeordet det skal søkes etter i dokumentet.  Gjelder for kontrollen for **[Visningsprogram for PDF](controls/control-pdf-viewer.md)**.

**[Font](controls/properties-text.md)**  – navnet på skriftserien som teksten vises i.  Gjelder for mange kontroller.

**[FontWeight](controls/properties-text.md)** – tykkelsen på teksten i en kontroll: **Fet**, **Halvfet**, **Normal** eller **Lysere**.  Gjelder for mange kontroller.

### <a name="g"></a>G
**[GridStyle](controls/control-column-line-chart.md)** – om et stolpe- eller linjediagram viser x-aksen, y-aksen, begge eller ingen av delene.  Gjelder for **[Stolpediagram](controls/control-column-line-chart.md)**- og **[Linjediagram](controls/control-column-line-chart.md)**-kontroller.

### <a name="h"></a>H
**[HandleActiveFill](controls/control-slider.md)** – fargen på håndtaket for en glidebryter mens brukeren endrer verdien.  Gjelder for **[Glidebryter](controls/control-slider.md)**-kontrollen.

**[HandleFill](controls/control-slider.md)** – fargen på håndtaket (elementet som endrer posisjon) i en veksleknapp eller glidebryter.  Gjelder for **[Glidebryter](controls/control-slider.md)**-kontrollen.

**[HandleHoverFill](controls/control-slider.md)** – fargen på håndtaket i en glidebryter når brukeren holder musepekeren på den.  Gjelder for **[Glidebryter](controls/control-slider.md)**-kontrollen.

**[Height](controls/properties-size-location.md)** – avstanden mellom kontrollens øvre og nedre kant.  Gjelder for mange kontroller.

**[HintText](controls/control-text-input.md)** – lys, grå tekst som vises i en kontroll for tekstinndata, hvis den er tom.  Gjelder for **[Tekstinndata](controls/control-text-input.md)**-kontrollen.

**[HoverBorderColor](controls/properties-color-border.md)** – fargen på kontrollens kantlinje når brukeren holder musepekeren over denne kontrollen.  Gjelder for mange kontroller.

**[HoverColor](controls/properties-color-border.md)** – fargen på en teksten i en kontroll når brukeren holder musepekeren over den.  Gjelder for mange kontroller.

**[HoverFill](controls/properties-color-border.md)** – bakgrunnsfargen for en kontroll når brukeren holder musepekeren over den.  Gjelder for mange kontroller.

**[HTMLText](controls/control-html-text.md)** – teksten som vises i en kontroll for HTML-tekst, og som kan inneholde HTML-koder.  Gjelder for **[HTML-tekst](controls/control-html-text.md)**-kontrollen.

### <a name="i"></a>I
**[Image](controls/properties-visual.md)** – navnet på bildet som vises i en bilde-, lyd- eller mikrofonkontroll.  Gjelder for kontrollene for **[Lyd](controls/control-audio-video.md)**, **[Bilde](controls/control-image.md)**, **[Mikrofon](controls/control-microphone.md)** og **[Video](controls/control-audio-video.md)**.

**[ImagePosition](controls/properties-visual.md)** – plasseringen (**Fyll**, **Tilpass**, **Strekk**, **Fylle side ved side** eller **Midtstill**) til et bilde på en skjerm eller en kontroll hvis det ikke har samme størrelse som bildet.  Gjelder for mange kontroller.

**[Input](controls/control-pen-input.md)** – inndata.  Gjelder for **[Penneinndata](controls/control-pen-input.md)**-kontrollen.

**[Italic](controls/properties-text.md)** – om teksten i en kontroll er i kursiv.  Gjelder for mange kontroller.

**[Item](controls/control-form-detail.md)** – posten i **DataSource** som brukeren vil vise eller redigere.  Gjelder for kontroller for **[Redigeringsskjema](controls/control-form-detail.md)** og **[Visningsskjema](controls/control-form-detail.md)**.

**[ItemBorderColor](controls/control-pie-chart.md)** – fargen på kantlinjen rundt hver sektor i et sektordiagram.  Gjelder for **[Sektordiagram](controls/control-pie-chart.md)**-kontrollen.

**[ItemBorderThickness](controls/control-pie-chart.md)** – tykkelsen på kantlinjen rundt hver sektor i et sektordiagram.  Gjelder for **[Sektordiagram](controls/control-pie-chart.md)**-kontrollen.

**ItemColorSet** – fargen på hvert datapunkt i et diagram.  Gjelder for kontrollene for **[Stolpediagram](controls/control-column-line-chart.md)**, **[Linjediagram](controls/control-column-line-chart.md)** og **[Sektordiagram](controls/control-pie-chart.md)**.

**[ItemPaddingLeft](controls/control-list-box.md)** – avstanden mellom teksten i en liste og venstre kant.  Gjelder for **[Listeboks](controls/control-list-box.md)**-kontrollen.

**[Items](controls/properties-core.md)** – kilden til dataene som vises i en kontroll, for eksempel et galleri, en liste eller et diagram.  Gjelder for mange kontroller.

**[ItemsGap](controls/control-column-line-chart.md)** – avstanden mellom kolonner i et stolpediagram.  Gjelder for **[Stolpediagram](controls/control-column-line-chart.md)**-kontrollen.

### <a name="l"></a>L
**[LabelPosition](controls/control-pie-chart.md)** – plasseringen av etikettene i et sektordiagram i forhold til sektorene.  Gjelder for **[Sektordiagram](controls/control-pie-chart.md)**-kontrollen.

**[LastSubmit](controls/control-form-detail.md)** – siste innsendte post, inkludert eventuelle servergenererte felt.  Gjelder for **[Redigeringsskjema](controls/control-form-detail.md)**-kontrollen.

**Layout** – om brukeren ruller gjennom et galleri eller justerer en glidebryteren fra topp til bunn (**loddrett**) eller fra venstre mot høyre (**vannrett**).  Gjelder for kontrollene **[Galleri](controls/control-gallery.md)** og **[Glidebryter](controls/control-slider.md)**.

**[LineHeight](controls/properties-text.md)** – avstanden mellom linjer med tekst, elementer i en liste eller lignende.  Gjelder kontrollene **[Listeboks](controls/control-list-box.md)**, **[Alternativknapp](controls/control-radio.md)**, **[Etikett](controls/control-text-box.md)** og **[Tekstinndata](controls/control-text-input.md)**.

**[Loop](controls/control-audio-video.md)** – om et lyd- eller videoklipp automatisk starter på nytt så snart det er ferdig.  Gjelder for kontrollene **[Lyd](controls/control-audio-video.md)** og **[Video](controls/control-audio-video.md)**.

### <a name="m"></a>M
**[Markers](controls/control-column-line-chart.md)** – om et kolonne- eller stolpediagram viser verdien for hvert datapunkt.  Gjelder for **[Stolpediagram](controls/control-column-line-chart.md)**- og **[Linjediagram](controls/control-column-line-chart.md)**-kontroller.

**[MarkerSuffix](controls/control-column-line-chart.md)** – teksten som vises etter hver verdi i et stolpediagram som har **[Markers](controls/control-column-line-chart.md)**-egenskapen er angitt som **sann**.  Gjelder for **[Stolpediagram](controls/control-column-line-chart.md)**-kontrollen.

**Max** – den maksimale verdien som brukeren kan angi for en glidebryter eller en vurdering.  Gjelder for kontrollene **[Vurdering](controls/control-rating.md)** og **[Glidebryter](controls/control-slider.md)**.

**[MaxLength](controls/control-text-input.md)** – antallet tegn som brukeren kan skrive inn i en kontroll for tekstinndata.  Gjelder for **[Tekstinndata](controls/control-text-input.md)**-kontrollen.

**Media** – en identifikator for klippet som spilles av en lyd- eller videokontroll.  Gjelder for kontrollene **[Legg til bilde](controls/control-add-picture.md)**, **[Lyd](controls/control-audio-video.md)** og **[Video](controls/control-audio-video.md)**.

**[Mic](controls/control-microphone.md)** – ID-nummeret til mikrofonen som appen bruker for enheter med mer enn én mikrofon.  Gjelder for **[Mikrofon](controls/control-microphone.md)**-kontrollen.

**[Min](controls/control-slider.md)** – minsteverdien som brukeren kan angi for en glidebryter.  Gjelder for **[Glidebryter](controls/control-slider.md)**-kontrollen.

**[MinimumBarWidth](controls/control-column-line-chart.md)** – den smaleste mulige bredden på kolonner i et stolpediagram.  Gjelder for **[Stolpediagram](controls/control-column-line-chart.md)**-kontrollen.

**Modus** – betydningen av denne egenskapen er avhengig av kontrollen:

* **[Redigeringsskjema](controls/control-form-detail.md)**-kontrollen – kontrollen er i **Rediger**- eller **Ny**-modus.
* **[Penneinndata](controls/control-pen-input.md)**-kontrollen – kontrollen er i **Tegn**-, **Slett**- eller **Velg**-modus.
* **[Tekstinndata](controls/control-text-input.md)**-kontrollen – kontrollen er i **SingleLine**-, **MultiLine**- eller **Passord**-modus.

### <a name="n"></a>N
**[NavigationStep](controls/control-gallery.md)** – hvor langt et galleri ruller hvis **[ShowNavigation](controls/control-gallery.md)**-egenskapen er satt til **sann**, og brukeren velger en navigasjonspil i en av endene av galleriet.  Gjelder for **[Gallery](controls/control-gallery.md)**-kontrollen.

**[NumberOfSeries](controls/control-column-line-chart.md)** – hvor mange kolonner med data som gjenspeiles i et stolpediagram eller linjediagram.  Gjelder for **[Stolpediagram](controls/control-column-line-chart.md)**- og **[Linjediagram](controls/control-column-line-chart.md)**-kontroller.

### <a name="o"></a>O
**[OnChange](controls/properties-core.md)** – hvordan appen reagerer når brukeren endrer verdien for en kontroll (for eksempel ved å justere en glidebryter).  Gjelder for mange kontroller.

**OnCheck** – hvordan en app reagerer når verdien til en avmerkingsboks eller en veksleknapp endres til **sann**.  Gjelder kontrollene **[Avmerkingsboks](controls/control-check-box.md)** og **[Veksleknapp](controls/control-toggle.md)**.

**[OnEnd](controls/control-audio-video.md)** – hvordan en app reagerer når et lyd- eller videoklipp er spilt av.  Gjelder for kontrollene **[Lyd](controls/control-audio-video.md)** og **[Video](controls/control-audio-video.md)**.

**[OnFailure](controls/control-form-detail.md)** – hvordan en app reagerer når en dataoperasjon mislykkes.  Gjelder for **[Redigeringsskjema](controls/control-form-detail.md)**-kontrollen.

**[OnHidden](controls/control-screen.md)** – hvordan en app reagerer når brukeren navigerer bort fra en skjerm.  Gjelder for **[Skjerm](controls/control-screen.md)**-kontrollen.

**[OnPause](controls/control-audio-video.md)** – hvordan en app reagerer når brukeren midlertidig stanser avspillingen av et klipp i en lyd- eller videokontroll.  Gjelder for kontrollene **[Lyd](controls/control-audio-video.md)** og **[Video](controls/control-audio-video.md)**.

**[OnReset](controls/control-form-detail.md)** – hvordan en app reagerer når en **[Redigeringsskjema](controls/control-form-detail.md)**-kontroll tilbakestilles.  Gjelder for **[Redigeringsskjema](controls/control-form-detail.md)**-kontrollen.

**[OnSelect](controls/properties-core.md)** – hvordan en app reagerer når en bruker trykker eller klikker på en kontroll.  Gjelder for mange kontroller.

**OnStart** – hvordan en app reagerer når brukeren åpner den eller begynner å ta opp med en mikrofon-kontroll. Gjelder for kontroller for **[Lyd](controls/control-audio-video.md)**, **[Mikrofon](controls/control-microphone.md)**, **[Skjerm](controls/control-screen.md)** og **[Video](controls/control-audio-video.md)**.

**[OnStateChange](controls/control-pdf-viewer.md)** – hvordan en app reagerer når statusen for kontrollen endres. Gjelder for kontrollen for **[Visningsprogram for PDF](controls/control-pdf-viewer.md)**.

**[OnStop](controls/control-microphone.md)** – hvordan appen reagerer når brukeren stopper et opptak med en mikrofon-kontroll. Gjelder for **[Mikrofon](controls/control-microphone.md)**-kontrollen.

**[OnStream](controls/control-camera.md)** – hvordan en app reagerer når **[Stream](controls/control-camera.md)**-egenskapen oppdateres.  Gjelder for **[Kamera](controls/control-camera.md)**-kontrollen.

**[OnSuccess](controls/control-form-detail.md)** – hvordan en app reagerer når en dataoperasjon er vellykket.  Gjelder for **[Redigeringsskjema](controls/control-form-detail.md)**-kontrollen.

**[OnTimerEnd](controls/control-timer.md)** – hvordan en app reagerer når en tidtaker er ferdig.  Gjelder for **[Tidtaker](controls/control-timer.md)**-kontrollen.

**[OnTimerStart](controls/control-timer.md)** – hvordan en app reagerer når en tidtaker starter.  Gjelder for **[Tidtaker](controls/control-timer.md)**-kontrollen.

**OnUncheck** – hvordan en app reagerer når verdien til en avmerkingsboks eller en veksleknapp endres til **usann**.  Gjelder kontrollene **[Avmerkingsboks](controls/control-check-box.md)** og **[Veksleknapp](controls/control-toggle.md)**.

**[OnVisible](controls/control-screen.md)** – hvordan en app reagerer når brukeren navigerer til en skjerm.  Gjelder for **[Skjerm](controls/control-screen.md)**-kontrollen.

**[OriginalHeight](controls/control-image.md)** – opprinnelig høyde på et bilde, aktivert med egenskapen **[CalculateOriginalDimensions](controls/control-image.md)**.  Gjelder for **[Bilde](controls/control-image.md)**-kontrollen.

**[OriginalWidth](controls/control-image.md)** – opprinnelig bredde på et bilde, aktivert med egenskapen **[CalculateOriginalDimensions](controls/control-image.md)**.  Gjelder for **[Bilde](controls/control-image.md)**-kontrollen.

**[Overflow](controls/control-text-box.md)** – om et rullefelt vises i en etikett hvis **[Wrap](controls/control-text-box.md)**-egenskapen er satt til **sann** og verdien av kontrollens **[Text](controls/properties-core.md)**-egenskap inneholder flere tegn enn kontrollen kan vise om gangen.  Gjelder for **[Etikett](controls/control-text-box.md)**-kontrollen.

### <a name="p"></a>P
**[Padding](controls/properties-size-location.md)**  – avstanden mellom teksten på en import- eller eksport-knapp og kantene på denne knappen.  Gjelder kontrollene **[Legg til bilde](controls/control-add-picture.md)**, **[Eksporter](controls/control-export-import.md)** og **[Importer](controls/control-export-import.md)**.

**[PaddingBottom](controls/properties-size-location.md)** – avstanden mellom teksten i en kontroll og den nederste kanten av kontrollen.  Gjelder for mange kontroller.

**[PaddingLeft](controls/properties-size-location.md)** – avstanden mellom teksten i en kontroll og den venstre kanten av kontrollen.  Gjelder for mange kontroller.

**[PaddingRight](controls/properties-size-location.md)** – avstanden mellom teksten i en kontroll og den høyre kanten av kontrollen.  Gjelder for mange kontroller.

**[PaddingTop](controls/properties-size-location.md)** – avstanden mellom teksten i en kontroll og den øverste kanten av kontrollen.  Gjelder for mange kontroller.

**[Page](controls/control-pdf-viewer.md)** – nummeret på siden du vil vise.  Gjelder for kontrollen for **[Visningsprogram for PDF](controls/control-pdf-viewer.md)**.

**[PageCount](controls/control-pdf-viewer.md)** – antall sider i et dokument.  Gjelder for kontrollen for **[Visningsprogram for PDF](controls/control-pdf-viewer.md)**.

**[Paused](controls/control-audio-video.md)** – *sann* hvis en kontroll for medieavspilling er midlertidig stanset, *usann* hvis ikke.  Gjelder for kontrollene **[Lyd](controls/control-audio-video.md)** og **[Video](controls/control-audio-video.md)**.

**[Photo](controls/control-camera.md)** – bildet som brukeren tar.  Gjelder for **[Kamera](controls/control-camera.md)**-kontrollen.

**[Pressed](controls/control-button.md)** – *sann* mens en kontroll trykkes på, *usann* hvis ikke.  Gjelder for **[Knapp](controls/control-button.md)**-kontrollen.

**[PressedBorderColor](controls/properties-color-border.md)** – fargen på kontrollens kantlinje når brukeren trykker eller klikker på kontrollen.  Gjelder for mange kontroller.

**[PressedColor](controls/properties-color-border.md)** – fargen på teksten i en kontroll når brukeren trykker eller klikker på kontrollen.  Gjelder for mange kontroller.

**[PressedFill](controls/properties-color-border.md)** – bakgrunnsfargen i en kontroll når brukeren trykker eller klikker på kontrollen.  Gjelder for mange kontroller.

### <a name="r"></a>R
**[RadioBackgroundFill](controls/control-radio.md)**  – bakgrunnsfargen i sirklene på en alternativknapp-kontroll.  Gjelder for **[Alternativknapp](controls/control-radio.md)**-kontrollen.

**[RadioBorderColor](controls/control-radio.md)**  – fargen på sirkelen for hvert alternativ i en alternativknapp-kontroll.  Gjelder for **[Alternativknapp](controls/control-radio.md)**-kontrollen.

**[RadioSelectionFill](controls/control-radio.md)**  – fargen som vises i sirkelen av det valgte alternativet i en alternativknapp-kontroll.  Gjelder for **[Alternativknapp](controls/control-radio.md)**-kontrollen.

**[RadioSize](controls/control-radio.md)**  – diameteren på sirklene i en alternativknapp-kontroll.  Gjelder for **[Alternativknapp](controls/control-radio.md)**-kontrollen.

**[RadiusBottomLeft](controls/properties-size-location.md)** – i hvilken grad hjørnet nederst til venstre av en kontroll avrundes.  Gjelder for mange kontroller.

**[RadiusBottomRight](controls/properties-size-location.md)** – i hvilken grad hjørnet nederst til høyre av en kontroll avrundes.  Gjelder for mange kontroller.

**[RadiusTopLeft](controls/properties-size-location.md)** – i hvilken grad hjørnet øverst til venstre av en kontroll avrundes.  Gjelder for mange kontroller.

**[RadiusTopRight](controls/properties-size-location.md)** – i hvilken grad hjørnet øverst til høyre av en kontroll avrundes.  Gjelder for mange kontroller.

**RailFill** – bakgrunnsfargen for rektangelet i vekslekontrollen når verdien er **usann**, eller fargen på linjen til høyre i håndtaket i en glidebryter.  Gjelder kontrollene **[Glidebryter](controls/control-slider.md)** og **[Veksleknapp](controls/control-toggle.md)**.

**RailHoverFill** – når du holder musepekeren over en veksleknappkontroll eller glidebryter, bakgrunnsfargen for rektangelet i en veksleknappkontroll når verdien er **usann** eller fargen på linjen til høyre for håndtaket i en glidebryter.  Gjelder kontrollene **[Glidebryter](controls/control-slider.md)** og **[Veksleknapp](controls/control-toggle.md)**.

**[RatingFill](controls/control-rating.md)** – fargen på stjerner i en kontroll for vurdering.  Gjelder for **[Vurdering](controls/control-rating.md)**-kontrollen.

**ReadOnly** – om en bruker kan endre verdien til en glidebryter eller vurderingkontroll.  Gjelder for kontrollene **[Vurdering](controls/control-rating.md)** og **[Glidebryter](controls/control-slider.md)**.

**[Repeat](controls/control-timer.md)** – om en tidtaker automatisk starter på nytt når den har kjørt ferdig.  Gjelder for **[Tidtaker](controls/control-timer.md)**-kontrollen.

**[Required](controls/control-card.md)** – om et kort, som redigerer feltet til en datakilde, må inneholde en verdi.  Gjelder for **[Kort](controls/control-card.md)**-kontrollen.

**[Reset](controls/properties-core.md)** – hvorvidt en kontroll tilbakestilles til standardverdien.  Gjelder for mange kontroller.  Se også **[Reset](functions/function-reset.md)**-funksjonen.

### <a name="s"></a>S
**Valgt** – det valgte elementet.  Gjelder for kontrollen for **[Rullegardin](controls/control-drop-down.md)** og **[Galleri](controls/control-gallery.md)**.

**[SelectedDate](controls/control-date-picker.md)** – datoen som er valgt i en datokontroll.  Gjelder for **[Datovelger](controls/control-date-picker.md)**-kontrollen.

**[SelectionColor](controls/properties-color-border.md)** – tekstfargen for et merket element, elementer i en liste eller fargen på markeringsverktøyet i en pennekontroll.  Gjelder for kontrollen for **[Rullegardin](controls/control-drop-down.md)**, **[Listeboks](controls/control-list-box.md)** og **[Penneinndata](controls/control-pen-input.md)**.

**[SelectionFill](controls/properties-color-border.md)** – bakgrunnsfargen for et merket element eller merkede elementer i en liste eller et merket område for en pennekontroll.  Gjelder for kontrollen for **[Rullegardin](controls/control-drop-down.md)** og **[Listeboks](controls/control-list-box.md)**.

**[SelectionThickness](controls/control-pen-input.md)** – tykkelsen på markeringsverktøyet for en penneinndata-kontroll.  Gjelder for **[Penneinndata](controls/control-pen-input.md)**-kontrollen.

**[SelectMultiple](controls/control-list-box.md)** – om en bruker kan velge mer enn ett element i en liste.  Gjelder for **[Listeboks](controls/control-list-box.md)**-kontrollen.

**[SeriesAxisMax](controls/control-column-line-chart.md)** – den maksimale verdien for y-aksen til et stolpe- eller linjediagram.  Gjelder for **[Stolpediagram](controls/control-column-line-chart.md)**-kontrollen.

**[SeriesAxisMin](controls/control-column-line-chart.md)** – den minste verdien av y-aksen for et stolpediagram.  Gjelder for **[Stolpediagram](controls/control-column-line-chart.md)**-kontrollen.

**ShowControls** – om en lyd- eller videoavspiller for eksempel viser en avspillingsknapp og en glidebryter for volum, og om en pennekontroll for eksempel viser ikoner for tegning, sletting og fjerning.  Gjelder for kontrollene for **[Lyd](controls/control-audio-video.md)**, **[Visningsprogram for PDF](controls/control-pdf-viewer.md)**, **[Penneinndata](controls/control-pen-input.md)** og **[Video](controls/control-audio-video.md)**.

**[ShowLabels](controls/control-pie-chart.md)** – angir om sektordiagrammet skal vise verdien hver av sektorene representerer.  Gjelder for **[Sektordiagram](controls/control-pie-chart.md)**-kontrollen.

**[ShowNavigation](controls/control-gallery.md)** – om det vises en pil i hver ende av et galleri, slik at en bruker kan bla gjennom elementene i galleriet ved å klikke eller trykke på en pil.  Gjelder for **[Gallery](controls/control-gallery.md)**-kontrollen.

**[ShowScrollbar](controls/control-gallery.md)** – om et rullefelt vises når brukeren beveger musepekeren over et galleri.  Gjelder for **[Gallery](controls/control-gallery.md)**-kontrollen.

**ShowValue** – om glidebryterens eller vurderingens verdi vises når en bruker endrer verdien eller holder musepekeren over kontrollen.  Gjelder for kontrollene **[Vurdering](controls/control-rating.md)** og **[Glidebryter](controls/control-slider.md)**.

**[Size](controls/properties-text.md)** – skriftstørrelsen på teksten som vises på en kontroll.  Gjelder for mange kontroller.

**[Snap](controls/control-gallery.md)** – om når en bruker ruller gjennom et galleri, den automatisk festes slik at det neste elementet vises i sin helhet.  Gjelder for **[Gallery](controls/control-gallery.md)**-kontrollen.

**Start** – om et lyd- eller videoklipp spilles av.  Gjelder for kontrollene **[Lyd](controls/control-audio-video.md)**, **[Tidtaker](controls/control-timer.md)** og **[Video](controls/control-audio-video.md)**.

**[StartTime](controls/control-audio-video.md)** – hvor lang tid det tar fra starten av lyd- eller videoklippet til klippet spilles av.  Gjelder for kontrollene **[Lyd](controls/control-audio-video.md)** og **[Video](controls/control-audio-video.md)**.

**[StartYear](controls/control-date-picker.md)** – det første året som brukeren kan angi verdien for i en datovelger-kontroll.  Gjelder for **[Datovelger](controls/control-date-picker.md)**-kontrollen.

**[Stream](controls/control-camera.md)** – automatisk oppdatert bilde basert på **[StreamRate](controls/control-camera.md)**-egenskapen.  Gjelder for **[Kamera](controls/control-camera.md)**-kontrollen.

**[StreamRate](controls/control-camera.md)** – hvor ofte du vil oppdatere bildet på **[Stream](controls/control-camera.md)**-egenskapen, i millisekunder.  Denne verdien kan være fra 100 (1/10 av et sekund) til 3 600 000 (1 time).  Gjelder for **[Kamera](controls/control-camera.md)**-kontrollen.

**[Strikethrough](controls/properties-text.md)** – om det vises en linje gjennom teksten som vises på en kontroll.  Gjelder for mange kontroller.

### <a name="t"></a>T
**[TemplateFill](controls/control-gallery.md)** – bakgrunnsfargen til et galleri.  Gjelder for **[Gallery](controls/control-gallery.md)**-kontrollen.

**[TemplatePadding](controls/control-gallery.md)** – avstanden mellom elementene i et galleri.  Gjelder for **[Gallery](controls/control-gallery.md)**-kontrollen.

**[TemplateSize](controls/control-gallery.md)** – høyden på malen for et galleri i vertikal/loddrett retning eller bredden til malen til et galleri i horisontal/vannrett retning.  Gjelder for **[Gallery](controls/control-gallery.md)**-kontrollen.

**[Text](controls/properties-core.md)** – tekst som vises på en kontroll eller som brukeren skriver inn i en kontroll.  Gjelder for mange kontroller.

**[Tid](controls/control-audio-video.md)** – mediakontrollens gjeldende posisjon.  Gjelder for kontrollene **[Lyd](controls/control-audio-video.md)** og **[Video](controls/control-audio-video.md)**.

**[Verktøytips](controls/properties-core.md)** – forklarende tekst som vises når brukeren holder pekeren over en kontroll.  Gjelder for mange kontroller.

**[Transition](controls/control-gallery.md)** – den visuelle effekten (**Pop**, **Push** eller **None**) når brukeren holder pekeren over et element i et galleri.  Gjelder for **[Gallery](controls/control-gallery.md)**-kontrollen.

**[Transparency](controls/control-image.md)** – i hvor stor grad kontrollene bak et bilde forblir synlige.  Gjelder for **[Bilde](controls/control-image.md)**-kontrollen.

### <a name="u"></a>U
**[Underline](controls/properties-text.md)** – om det vises en linje under teksten som vises på en kontroll.  Gjelder for mange kontroller.

**[Unsaved](controls/control-form-detail.md)** – sann hvis **[Redigeringsskjema](controls/control-form-detail.md)**-kontrollen inneholder brukerendringer som ikke er lagret.  Gjelder for **[Redigeringsskjema](controls/control-form-detail.md)**-kontrollen.

**[Oppdater](controls/control-card.md)** – verdien som skrives tilbake i datakilden for et felt.  Gjelder for **[Kort](controls/control-card.md)**-kontrollen.

**[Oppdateringer](controls/control-form-detail.md)** – verdiene som skrives tilbake til datakilden for en post som er lastet inn i en skjemakontroll.  Gjelder for **[Redigeringsskjema](controls/control-form-detail.md)**-kontrollen.

### <a name="v"></a>V
**Valid** – om kontrollene **[Kort](controls/control-card.md)** eller **[Redigeringsskjema](controls/control-form-detail.md)** inneholder gyldige oppføringer og er klare til å sendes til datakilden.  Gjelder for kontroller for **[Kort](controls/control-card.md)** og **[Redigeringsskjema](controls/control-form-detail.md)**.

**[Value](controls/properties-core.md)** – verdien til en inndatakontroll.  Gjelder kontrollene **[Avmerkingsboks](controls/control-check-box.md)**, **[Alternativknapp](controls/control-radio.md)**, **[Glidebryter](controls/control-slider.md)** og **[Veksleknapp](controls/control-toggle.md)**.

**ValueFill** – bakgrunnsfargen for rektangelet i vekslekontrollen når verdien er **sann**, eller fargen på linjen til venstre for håndtaket i en glidebryter.  Gjelder kontrollene **[Glidebryter](controls/control-slider.md)** og **[Veksleknapp](controls/control-toggle.md)**.

**ValueHoverFill** – når du holder musepekeren over en vekslekontroll eller en glidebryter, bakgrunnsfargen for rektangelet i en vekslekontroll når verdien er **sann** eller fargen på linjen til venstre for håndtaket i en glidebryter.  Gjelder kontrollene **[Glidebryter](controls/control-slider.md)** og **[Veksleknapp](controls/control-toggle.md)**.

**[VerticalAlign](controls/properties-text.md)**  – plasseringen av tekst på en kontroll i forhold til den loddrette midten av kontrollen.  Gjelder for mange kontroller.

**[Visible](controls/properties-core.md)** – om en kontroll vises eller er skjult.  Gjelder for mange kontroller.

### <a name="w"></a>W
**[Width](controls/properties-size-location.md)** – avstanden mellom venstrekanten og høyrekanten til en kontroll.  Gjelder for mange kontroller.

**[WidthFit](controls/properties-size-location.md)**  – om en kontroll automatisk utvides horisontalt for å fylle ut et tomt område i en beholderkontroll, f.eks. en **[Redigeringsskjema](controls/control-form-detail.md)**-kontroll. Hvis flere kort har denne egenskapen satt til **sann**, deles plassen mellom dem. Hvis du vil ha mer informasjon, kan du se [Forstå oppsett for dataskjema](working-with-form-layout.md).

**[Wrap](controls/control-text-box.md)** – om teksten som er for lang til å få plass i en etikett brytes til neste linje.  Gjelder for **[Etikett](controls/control-text-box.md)**-kontrollen.

**[WrapCount](controls/control-gallery.md)** – hvor mange poster som vises i hvert element i et galleri.  Gjelder for **[Gallery](controls/control-gallery.md)**-kontrollen.

### <a name="x"></a>X
**[X](controls/properties-size-location.md)** – avstanden mellom kontrollens venstre kant og den venstre kanten til kontrollens overordnede beholder (eller skjermen, hvis det ikke finnes noen overordnet beholder). Gjelder for mange kontroller. For en **[Kort](controls/control-card.md)**-kontroll i en beholder med flere kolonner, bestemmer denne egenskapen hvilken kolonne kortet skal vises i.

**[XLabelAngle](controls/control-column-line-chart.md)** – vinkelen til etikettene under x-aksen i et diagram for et stolpe- eller linjediagram.  Gjelder for **[Stolpediagram](controls/control-column-line-chart.md)**- og **[Linjediagram](controls/control-column-line-chart.md)**-kontroller.

### <a name="y"></a>Y
**[Y](controls/properties-size-location.md)** – avstanden mellom kontrollens øvre kant og den øvre kanten til kontrollens overordnede beholder (eller skjermen, hvis det ikke finnes noen overordnet beholder). Gjelder for mange kontroller. For en **[Kort](controls/control-card.md)**-kontroll i en beholder med flere rader, bestemmer denne egenskapen hvilken rad kortet skal vises i.

**[YAxisMax](controls/control-column-line-chart.md)** – den maksimale verdien for y-aksen til et linjediagram.  Gjelder for **[Linjediagram](controls/control-column-line-chart.md)**-kontrollen.

**[YAxisMin](controls/control-column-line-chart.md)** – den minste verdien for y-aksen til et linjediagram.  Gjelder for **[Linjediagram](controls/control-column-line-chart.md)**-kontrollen.

**[YLabelAngle](controls/control-column-line-chart.md)** – vinkelen til etikettene ved siden av y-aksen i et stolpe- eller linjediagram.  Gjelder for **[Stolpediagram](controls/control-column-line-chart.md)**- og **[Linjediagram](controls/control-column-line-chart.md)**-kontroller.

### <a name="z"></a>Z
**Zoom** – hvor mye et bilde fra et kamera prosentvis forstørres eller visningen av en fil i PDF-visningsprogram.  Gjelder for kontrollene for **[Kamera](controls/control-camera.md)** og **[Visningsprogram for PDF](controls/control-pdf-viewer.md)**.
