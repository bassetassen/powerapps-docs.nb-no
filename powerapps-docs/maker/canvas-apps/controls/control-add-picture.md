---
title: 'Legg til bilde-kontrollen: referanse | Microsoft Docs'
description: Informasjon om Legg til bilde-kontrollen, inkludert egenskaper og eksempler
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
ms.openlocfilehash: 6a7c60755f5623803d20bec4ec9881108b1116c6
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/22/2018
ms.locfileid: "30996292"
---
# <a name="add-picture-control-in-powerapps"></a>Legg til bilde-kontrollen i PowerApps
Tar et bilde eller laster inn bilder fra den lokale enheten.

## <a name="description"></a>Beskrivelse
Med denne kontrollen kan brukere ta bilder eller laste opp bildefiler fra enheten og oppdatere datakilden med dette innholdet. På en mobil enhet får brukeren se enhetens valgdialog for å velge mellom å ta et bilde eller velge et som allerede finnes.

Denne kontrollen er en sammensatt kontroll og består av to kontroller.  Trykk én gang for å velge den ytre kontrollen som viser bildet som er lastet inn.  Trykk én gang til for å velge den indre etikettkontrollen.

## <a name="outer-control-properties"></a>Den ytre kontrollens egenskaper
Disse egenskapene gjelder for den ytre kontrollen.

**[BorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje.

**[BorderStyle](properties-color-border.md)** – om kontrollens kantlinje er **Heltrukket**, **Stiplet**, **Prikket** eller **Ingen**.

**[BorderThickness](properties-color-border.md)** – tykkelsen til kontrollens kantlinje.

**[DisplayMode](properties-core.md)** – om kontrollen tillater brukerinndata (**Edit**), bare viser data (**View**) eller er deaktivert (**Disabled**).

**[DisabledBorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje hvis kontrollens **[DisplayMode](properties-core.md)**-egenskap er angitt som **Disabled**.

**[DisabledFill](properties-color-border.md)** – bakgrunnsfargen på en kontroll hvis **[DisplayMode](properties-core.md)**-egenskapen er angitt som **Deaktivert**.

**Feil** – Hvis det oppstår et problem ved opplasting av et bildet, består denne egenskapen av en streng med en tilhørende feilmelding.

**[Fill](properties-color-border.md)** – Bakgrunnsfargen på kontrollen.

**[Height](properties-size-location.md)** – avstanden mellom kontrollens øvre og nedre kant.

**[HoverBorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje når brukeren holder musepekeren på denne kontrollen.

**[HoverFill](properties-color-border.md)**  – bakgrunnsfargen for en kontroll når brukeren holder musepekeren på den.

**Media** – en identifikator for klippet som spilles av en lyd- eller videokontroll.

**[OnSelect](properties-core.md)** – hvordan appen reagerer når brukeren klikker eller trykker på en kontroll.

**[PressedBorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje når brukeren trykker eller klikker på kontrollen.

**[PressedFill](properties-color-border.md)** – bakgrunnsfargen i en kontroll når brukeren trykker eller klikker på kontrollen.

**[Visible](properties-core.md)** – om kontrollen vises eller skjules.

**[Width](properties-size-location.md)** – avstanden mellom venstrekanten og høyrekanten på en kontroll.

**[X](properties-size-location.md)** – avstanden mellom kontrollens venstre kant og den venstre kanten til kontrollens overordnede beholder (eller skjermen, hvis det ikke finnes noen overordnet beholder).

**[Y](properties-size-location.md)** – avstanden mellom kontrollens øvre kant og den øvre kanten til kontrollens overordnede beholder (eller skjermen, hvis det ikke finnes noen overordnet beholder).

## <a name="inner-text-properties"></a>Den indre tekstens egenskaper
Disse egenskapene gjelder den indre etiketten, som har standardteksten «Tap or click to add a picture».  Trykk på**Legg til bilde**-kontrollen én gang for å velge denne indre kontrollen, og trykk deretter én gang til.

**[Align](properties-text.md)** – plasseringen av teksten i forhold til den vannrette midten av kontrollen.

**[Color](properties-color-border.md)**  – fargen på teksten i kontrollen.

**[DisabledColor](properties-color-border.md)** – fargen på kontrollens kantlinje hvis kontrollens **[DisplayMode](properties-core.md)**-egenskap er angitt som **Disabled**.

**[Font](properties-text.md)**  – navnet på skriftserien som teksten vises i.

**[FontWeight](properties-text.md)** – tykkelsen på teksten i en kontroll: **Fet**, **Halvfet**, **Normal** eller **Lysere**.

**[HoverColor](properties-color-border.md)** – fargen på en tekst i en kontroll når brukeren holder musepekeren på den.

**[Italic](properties-text.md)** – om teksten i en kontroll er kursiv.

**[OnChange](properties-core.md)** – hvordan appen reagerer når brukeren endrer verdien på en kontroll (ved å for eksempel justere en glidebryter).

**[Padding](properties-size-location.md)**  – avstanden mellom teksten på en import eller eksport-knapp og kantene av denne knappen.

**[PressedColor](properties-color-border.md)** – fargen på teksten i en kontroll når brukeren trykker eller klikker på kontrollen.

**[Size](properties-text.md)** – skriftstørrelsen på teksten som vises på en kontroll.

**[Strikethrough](properties-text.md)** – om det vises en linje gjennom teksten som vises på en kontroll.

**[Text](properties-core.md)** – tekst som vises på en kontroll, eller som brukeren skriver inn i en kontroll.

**[Underline](properties-text.md)** – om det vises en linje under teksten som vises på en kontroll.

**[VerticalAlign](properties-text.md)** – plasseringen av tekst i en kontroll i forhold til det vertikale midtpunktet i kontrollen.

## <a name="related-functions"></a>Relaterte funksjoner
[**Patch**( *DataSource*, *BaseRecord*, *ChangeRecord* )](../functions/function-patch.md)

## <a name="example"></a>Eksempel
### <a name="add-images-to-an-image-gallery-control"></a>Legg til bilder i en Bildegalleri-kontroll
1. Legg til en **Legg til bilde**-kontroll, og trippelklikk på den.
   
    Vet du ikke hvordan du [legger til, gir navn til og konfigurerer en kontroll](../add-configure-controls.md)?
2. Klikk eller trykk på en bildefil i **Åpne**-dialogboksen, og klikk eller trykk på **Åpne**.
3. Legg til en **[Knapp](control-button.md)**-kontroll, flytt den under **Legg til bilde**-kontrollen, og angi **[OnSelect](properties-core.md)**-egenskapen til **[Knapp](control-button.md)**-kontrollen som denne formelen:<br>
   **Collect(MyPix, AddMediaButton1.Media)**
   
    Vil du ha mer informasjon om **[Collect](../functions/function-clear-collect-clearcollect.md)**-funksjonen eller [andre funksjoner](../formula-reference.md)?
4. Legg til en **Bildegalleri**-kontroll, og angi **[Items](properties-core.md)**-egenskapen som **MyPix**.
5. Trykk på F5, og klikk eller trykk på **[Knapp](control-button.md)**-kontrollen.
   
    Bildet fra **Legg til bilde**-kontrollen vises i **Bildegalleri**-kontrollen. Hvis bildet ditt ikke har samme størrelsesforhold som **[Bilde](control-image.md)**-kontrollen i **Bildegalleri**-kontrollen, kan du angi **[ImagePosition](properties-visual.md)**-egenskapen til **[Bilde](control-image.md)**-kontrollen som **Fit**.
6. Klikk eller trykk på **Legg til bilde**-kontrollen, klikk eller trykk på en annen bildefil, klikk eller trykk på **Åpne**, og klikk eller trykk på **[Knapp](control-button.md)**-kontrollen som du har lagt til.
   
    Det andre bildet vises i **Bildegalleri**-kontrollen.
7. (valgfritt) Gjenta forrige trinn én eller flere ganger, og gå deretter tilbake til standardarbeidsområdet ved å trykke på Esc.

Bruk **[SaveData](../functions/function-savedata-loaddata.md)**-funksjonen til å lagre bildene lokalt eller **[Patch](../functions/function-patch.md)**-funksjonen til å lagre dem til en datakilde.

