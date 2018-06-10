---
title: 'Strekkodeleser-kontroll: referanse | Microsoft Docs'
description: Informasjon om Strekkodeleser-kontrollen, inkludert egenskaper og eksempler
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
ms.openlocfilehash: 264c360af0175b6a5dddd74306b32c7d1ecaef1d
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/22/2018
ms.locfileid: "30996077"
---
# <a name="barcode-scanner-control-experimental-in-powerapps"></a>Strekkodeleser-kontrollen (eksperimentell) i PowerApps
En eksperimentell kontroll som lar brukeren ta bilder ved hjelp av strekkodeleseren på enheten.

## <a name="description"></a>Beskrivelse
Hvis du legger til denne kontrollen, kan brukeren oppdatere en datakilde med ett eller flere bilder fra hvor som helst appen kjører.

## <a name="key-properties"></a>Nøkkelegenskaper
**Strekkodeleser** – på en enhet som har mer enn én strekkodeleser, den numeriske ID-en til strekkodeleseren som appen bruker.

## <a name="additional-properties"></a>Tilleggsegenskaper
**[BorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje.

**[BorderStyle](properties-color-border.md)** – Om kontrollens kantlinje er satt til **Heltrukket**, **Stiplet**, **Prikket** eller **Ingen**.

**[BorderThickness](properties-color-border.md)** – tykkelsen til kontrollens kantlinje.

**Lysstyrke** – hvor mye lys brukeren sannsynligvis oppfatter i et bilde.

**Kontrast** – hvor enkelt brukeren kan skille mellom lignende farger i et bilde.

**[DisplayMode](properties-core.md)** – om kontrollen tillater brukerinndata (**Rediger**), viser kun data (**Vis**) eller er deaktivert (**Deaktivert**).

**[Høyde](properties-size-location.md)** – avstanden mellom kontrollens øvre og nedre kant.

**[OnSelect](properties-core.md)** – hvordan appen reagerer når brukeren klikker eller trykker på en kontroll.

**OnStream** – hvordan appen svarer når **Strøm**-egenskapen oppdateres.

**Bilde** – bildet som brukeren tar.

**Strøm** – automatisk oppdatert bilde basert på **StreamRate**-egenskapen.

**StreamRate** – hvor ofte du vil oppdatere bildet på **Strøm**-egenskapen, i millisekunder.  Denne verdien kan være fra 100 (1/10 av et sekund) til 3 600 000 (1 time).

**[Verktøytips](properties-core.md)** – forklarende tekst som vises når brukeren holder pekeren over en kontroll.

**[Synlig](properties-core.md)** – om kontrollen vises eller skjules.

**[Bredde](properties-size-location.md)** – avstanden mellom kontrollens venstre og høyre kant.

**[X](properties-size-location.md)** – avstanden mellom kontrollens venstre kant og den venstre kanten til kontrollens overordnede beholder (eller skjermen, hvis det ikke finnes noen overordnet beholder).

**[Y](properties-size-location.md)** – avstanden mellom kontrollens øvre kant og den øvre kanten til kontrollens overordnede beholder (eller skjermen, hvis det ikke finnes noen overordnet beholder).

**Zoom** – Hvor mye et bilde fra en strekkodeleser prosentvis forstørres eller visningen av en fil i PDF-visningsprogram.

## <a name="related-functions"></a>Relaterte funksjoner
[**Patch**( *DataSource*, *BaseRecord*, *ChangeRecord* )](../functions/function-patch.md)

## <a name="example"></a>Eksempel
### <a name="add-photos-to-an-image-gallery-control"></a>Å legge til bilder i en Bildegalleri-kontroll
1. Legg til en **Strekkodeleser**-kontroll, gi den navnet **Mybarcode scanner**

    Vet du ikke hvordan du [legger til, gir navn til og konfigurerer en kontroll](../add-configure-controls.md)?
2. Legg til en **Etikett**-kontroll, og angi utmatingen til strekkodens verdi.  
3. Skann en strekkode av typen som er angitt under BarcodeType-egenskapen.
4. Etiketten skal vises de skannede strekkodene.
