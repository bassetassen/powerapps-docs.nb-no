---
title: 'Kontroll for PDF-visningsprogram: referanse | Microsoft Docs'
description: Informasjon, inkludert egenskaper og eksempler, om kontrollen for PDF-visningsprogrammet
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
ms.openlocfilehash: c3ed17faae5963f71531b2fdc2ef9b08ee2569cc
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/22/2018
ms.locfileid: "30996367"
---
# <a name="pdf-viewer-control-experimental-in-powerapps"></a>Kontroll for PDF-visningsprogram (eksperimentell) i PowerApps
En eksperimentell kontroll som viser innholdet i en PDF-fil.

## <a name="description"></a>Beskrivelse
Vis tekst, grafikk og annet innhold i en PDF-fil ved å legge til denne typen kontroll, og sette inn den tilhørende **dokument**-egenskapen til nettadressen, omsluttet av doble anførselstegn, av filen som du vil vise.

## <a name="limitations"></a>Begrensninger
Vær oppmerksom på at på grunn av sikkerhetsarkitekturen til PowerApps, støtter PDF-visningsprogrammet bare HTTPS-koblinger og ikke HTTP.  
Hvis PDF-dokumentet ligger på en server med restriktive CORS-innstillinger, vil du kanskje ikke kunne vise det i appen din.  Hvis du vil løse dette problemet, må serveren som er vert for PDF-dokumenter tillate forespørsler på tvers av utgaver (CORS) som kommer fra powerapps.com.

I tilfelle dokumentet ikke kan åpnes i PowerApps, vises alternativet for å åpne dokumentet i en ekstern nettleser til sluttbrukeren.  Dette alternativet er også tilgjengelig i systemmenyen for alle eksterne dokumenter.

## <a name="key-properties"></a>Nøkkelegenskaper
**Dokument** – nettadressen, omsluttet av doble anførselstegn, for en PDF-fil.

## <a name="additional-properties"></a>Tilleggsegenskaper
**ActualZoom** – den faktiske zoomingen for kontrollen, hvor zoomingen som er forespurt kan skille seg fra **Zoom**-egenskapen.

**[BorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje.

**[BorderStyle](properties-color-border.md)** – om kontrollens kantlinje er **Heltrukket**, **Stiplet**, **Prikket** eller **Ingen**.

**[BorderThickness](properties-color-border.md)** – tykkelsen på kontrollens kantlinje.

**CurrentFindText** – det gjeldende søkeordet som er i bruk.

**CurrentPage** – nummeret på siden i en PDF-fil som faktisk vises.

**[DisplayMode](properties-core.md)** – hvorvidt kontrollen tillater brukerinndata (**Rediger**), bare viser data (**Vis**) eller er deaktivert (**Deaktivert**).

**[DisabledBorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje hvis kontrollens **[DisplayMode](properties-core.md)**-egenskap er angitt til **Deaktivert**.

**[Fyll](properties-color-border.md)** – bakgrunnsfargen på en kontroll.

**FindNext** – finner neste forekomst av **FindText** i dokumentet.

**FindPrevious** – finner forrige forekomst av **FindText** i dokumentet.

**FindText** – søkeordet det skal søkes etter i dokumentet.

**[Høyde](properties-size-location.md)** – avstanden mellom den øvre og nedre kanten til en kontroll.

**[HoverBorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje når brukeren holder musepekeren på denne kontrollen.

**[OnSelect](properties-core.md)** – hvordan appen reagerer når brukeren klikker eller trykker på en kontroll.

**OnStateChange** – hvordan en app svarer når statusen for kontrollen endres.

**[PaddingBottom](properties-size-location.md)** – avstanden mellom teksten i en kontroll og den nederste kanten av kontrollen.

**[PaddingLeft](properties-size-location.md)** – avstanden mellom teksten i en kontroll og den venstre kanten av kontrollen.

**[PaddingRight](properties-size-location.md)** – avstanden mellom teksten i en kontroll og den høyre kanten av kontrollen.

**[PaddingTop](properties-size-location.md)** – avstanden mellom teksten i en kontroll og den øverste kanten av kontrollen.

**Side** – nummeret på siden som du vil vise.

**PageCount** – antall sider i et dokument.

**[PressedBorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje når brukeren trykker eller klikker på kontrollen.

**ShowControls** – om en lyd- eller videoavspiller for eksempel viser en avspillingsknapp og en glidebryter for volum, og om en pennekontroll for eksempel viser ikoner for tegning, sletting og fjerning.

**[Verktøytips](properties-core.md)** – forklarende tekst som vises når brukeren holder pekeren over en kontroll.

**[Synlig](properties-core.md)** – om kontrollen vises eller skjules.

**[Bredde](properties-size-location.md)** – avstanden mellom kontrollens venstre og høyre kant.

**[X](properties-size-location.md)** – avstanden mellom kontrollens venstre kant og den venstre kanten til kontrollens overordnede beholder (eller skjermen, hvis det ikke finnes noen overordnet beholder).

**[Y](properties-size-location.md)** – avstanden mellom kontrollens øvre kant og den øvre kanten til kontrollens overordnede beholder (eller skjermen, hvis det ikke finnes noen overordnet beholder).

**Zoom** – hvor mye et bilde fra et kamera prosentvis forstørres eller hvor mye som vises i et PDF-visningsprogram.

## <a name="example"></a>Eksempel
* Legg til en kontroll for et **PDF-visningsprogram**, og angi **Dokument**-egenskapen til nettadressen, omsluttet av doble anførselstegn for en PDF-fil som i dette eksemplet:<br>
  **"http://www.who.int/gho/publications/world_health_statistics/EN_WHS2015_TOC.pdf?ua=1"**

    Kontrollen viser PDF-filen.

    Lurer du på hvordan du [legger til og konfigurerer en kontroll](../add-configure-controls.md)?
