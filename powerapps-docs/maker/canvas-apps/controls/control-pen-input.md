---
title: 'Penneinndata-kontroll: referanse | Microsoft Docs'
description: Informasjon om Penneinndata-kontrollen, inkludert egenskaper og eksempler
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
ms.openlocfilehash: 7e5be9b68b501279329c23f9afe5d451487fa8d1
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/22/2018
ms.locfileid: "30996027"
---
# <a name="pen-input-control-in-powerapps"></a>Penneinndata-kontrollen i PowerApps
En kontroll hvor du kan tegne, viske ut og utheve områder i et bilde.

## <a name="description"></a>Beskrivelse
Du kan bruke denne kontrollen som en tavle og tegne diagrammer og håndskrive ord som kan konverteres til maskinskrevet tekst.

## <a name="key-properties"></a>Nøkkelegenskaper
**[Farge](properties-color-border.md)** – fargen på inndatastrøkene.

**Modus** – kontrollen er i **Tegne**- eller **Slette**-modus.  Valg av modus er avskrevet.

## <a name="additional-properties"></a>Tilleggsegenskaper
**[BorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje.

**[BorderStyle](properties-color-border.md)** – Om kontrollens kantlinje er satt til **Heltrukket**, **Stiplet**, **Prikket** eller **Ingen**.

**[BorderThickness](properties-color-border.md)** – tykkelsen til kontrollens kantlinje.

**[DisplayMode](properties-core.md)** – om kontrollen tillater brukerinndata (**Rediger**), bare viser data (**Vis**) eller er deaktivert (**Deaktivert**).

**[Fyll](properties-color-border.md)** – bakgrunnsfargen på kontrollen.

**[Høyde](properties-size-location.md)** – avstanden mellom kontrollens øvre og nedre kant.

**Input** – inndata.

**[OnSelect](properties-core.md)** – hvordan appen reagerer når brukeren klikker eller trykker på en kontroll.

**[SelectionColor](properties-color-border.md)** – tekstfargen for et merket element, elementer i en liste eller fargen på markeringsverktøyet i en pennekontroll.

**SelectionThickness** – tykkelsen på markeringsverktøyet for en penneinndata-kontroll.

**ShowControls** – om en lyd- eller videoavspiller viser, for eksempel en avspillingsknapp og en glidebryter for volum, og om en pennekontroll, for eksempel viser ikoner for tegning, sletting og fjerning.

**[Størrelse](properties-text.md)** – skriftstørrelsen på teksten som vises på en kontroll.

**[Verktøytips](properties-core.md)** – forklarende tekst som vises når brukeren holder pekeren over en kontroll.

**[Synlig](properties-core.md)** – om kontrollen vises eller skjules.

**[Bredde](properties-size-location.md)** – avstanden mellom kontrollens venstre og høyre kant.

**[X](properties-size-location.md)** – avstanden mellom kontrollens venstre kant og den venstre kanten til kontrollens overordnede beholder (eller skjermen, hvis det ikke finnes noen overordnet beholder).

**[Y](properties-size-location.md)** – avstanden mellom kontrollens øvre kant og den øvre kanten til kontrollens overordnede beholder (eller skjermen, hvis det ikke finnes noen overordnet beholder).

## <a name="related-functions"></a>Relaterte funksjoner
[**Collect**( *CollectionName*, *DatatoCollect* )](../functions/function-clear-collect-clearcollect.md)

## <a name="example"></a>Eksempel
### <a name="create-a-set-of-images"></a>Opprett et sett med bilder
1. Legg til en **Penneinndata**-kontroll, gi den navnet **MyDoodles**, og angi **ShowControls**-egenskapen som **sann**.
   
    Vet du ikke hvordan du [legger til, gir navn til og konfigurerer en kontroll](../add-configure-controls.md)?
2. Legg til en **[Knapp](control-button.md)**, flytt den under **MyDoodles**, og angi **[Text](properties-core.md)**-egenskapen for **[Knapp](control-button.md)**-kontrollen til å vise **Legg til**.
3. Angi **[OnSelect](properties-core.md)**-egenskapen til **[Knapp](control-button.md)**-kontrollen som denne formelen:<br>
   **Collect(Doodles, {Sketch:MyDoodles.Image})**
4. Legg til en **Bildegalleri**-kontroll, flytt den under **[Knapp](control-button.md)**-kontrollen, og reduserer bredden på **Bildegalleri**-kontrollen til den viser tre elementer.
5. Angi **Bildegalleri**-kontrollens **[Elementer](properties-core.md)**-egenskap til **Doodles**, og trykk på F5.
6. Tegn et bilde i **MyDoodles**, og klikk eller trykk på **[Knapp](control-button.md)**-kontrollen.
   
    Bildet du har tegnet, vises i **Bildegalleri**-kontrollen.
7. (valgfritt) Klikk eller trykk på ikonet i **Penneinndata**-kontrollen for å fjerne bildet du tegnet, tegne et annet bilde, og trykk eller trykk deretter på **[Knapp](control-button.md)**-kontrollen.
8. I **Bildegalleri**-kontrollen angir du **[OnSelect](properties-core.md)**-egenskapen til **[Bilde](control-image.md)**-kontrollen som denne formelen:<br>
   **Remove(Doodles, ThisItem)**
9. Du kan fjerne en tegning ved å klikke eller trykke på den i **Bildegalleri**-kontrollen.

Bruk **[SaveData](../functions/function-savedata-loaddata.md)**-funksjonen til å lagre tegningene lokalt eller **[Patch](../functions/function-patch.md)**-funksjonen til å lagre dem til en datakilde.

