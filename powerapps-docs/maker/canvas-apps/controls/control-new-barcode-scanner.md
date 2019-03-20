---
title: 'Strekkodeleser kontrollen: referanse | Microsoft Docs'
description: Informasjon, inkludert egenskaper og eksempler, om strekkodeleser kontrollen
author: fikaradz
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.date: 11/25/2018
ms.author: fikaradz
ms.reviewer: anneta
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 961f8908014ef9cd85eadacb97a7c1dfc7e52b25
ms.sourcegitcommit: eef2d6d9a9c7f5c8a44b9734817f59dc0eac3ecf
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 02/07/2019
ms.locfileid: "57801001"
---
# <a name="barcode-scanner-control-for-canvas-apps"></a>Strekkodeleser kontrollen for lerretsapper

Skanner strekkoder, QR-koder og data-matrisen koder på en Android eller iOS-enhet. Støttes ikke i en nettleser.

## <a name="description"></a>Beskrivelse

Den åpner en opprinnelig skanner på en Android eller iOS-enhet. Skanneren oppdager automatisk en strekkode, en QR-kode eller en data-matrise-kode når i visningen. Kontrollen støtter ikke skanning i en nettleser.

Kontrollen støtter QR-koder, data matrise-koder og disse typer strekkoder:

- UPC A
- UPC E
- EAN 8
- EAN 13
- CODE 39
- KODE 128
- ITF
- PDF 417

## <a name="key-properties"></a>Nøkkelegenskaper

**Verdien** – utdata-egenskapen som inneholder tekstverdien til koden som er skannet sist.

**Tekst** -teksten som vises på knappen som aktiverer skanneren.

**OnScan** – hvordan en app reagerer når en strekkode er er skannet.

## <a name="additional-properties"></a>Tilleggsegenskaper

**[BorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje.

**[BorderStyle](properties-color-border.md)** – om kontrollens kantlinje er satt til **Heltrukket**, **Stiplet**, **Prikket** eller **Ingen**.

**[BorderThickness](properties-color-border.md)** – tykkelsen til kontrollens kantlinje.

**[DisplayMode](properties-core.md)** – om kontrollen tillater brukerinndata (**Rediger**), bare viser data (**Vis**) eller er deaktivert (**Deaktivert**).

**FlashlightEnabled** - om lommelykt aktiveres automatisk når skanneren er åpnet.

**[Høyde](properties-size-location.md)**  – høyden på knappen som aktiverer skanneren.

**[Verktøytips](properties-core.md)** – forklarende tekst som vises når brukeren holder pekeren over en kontroll.

**Typen** -typen som ble oppdaget i søket som lyktes sist.

**[Synlig](properties-core.md)** – om kontrollen vises eller skjules.

**[Bredde](properties-size-location.md)**  – bredden på knappen som aktiverer skanneren.

**[X](properties-size-location.md)** – avstanden mellom kontrollens venstre kant og den venstre kanten til kontrollens overordnede beholder (eller skjermen, hvis det ikke finnes noen overordnet beholder).

**[Y](properties-size-location.md)** – avstanden mellom kontrollens øvre kant og den øvre kanten til kontrollens overordnede beholder (eller skjermen, hvis det ikke finnes noen overordnet beholder).
