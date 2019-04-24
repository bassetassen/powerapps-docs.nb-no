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
ms.openlocfilehash: 1e41ec8d228e62c22354d77777a8390bfd442f8c
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/23/2019
ms.locfileid: "61543969"
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

## <a name="accessibility-guidelines"></a>Retningslinjer for tilgjengelighet
De samme retningslinjene for den **[knappen](control-button.md)** kontrollen gjelder den **strekkodeleser** kontrollen fordi det er en knapp som starter søket.

### <a name="visual-alternatives"></a>Visuelle alternativer
* Strekkodeleseren er en knapp som ikke viser resultatet søk. Vurder å som viser resultatet søk med en **[etikett](control-text-box.md)** kontroll. Angi etikettens **[tekst](properties-core.md)** egenskapen til strekkodeleserens **verdien** egenskapen. Angi etikettens **[Live](properties-accessibility.md)** egenskapen til **Polite** slik at skjermleseren brukere blir varslet om endringer. Denne endringen blir skannet verdien som er tilgjengelig for alle, uavhengig av muligheten til visual.

* Brukere som har visual og motor funksjonshemninger foretrekker ikke å peke kameraet på en strekkode. Vurder å legge til en annen form for inndata, som en **[tekstinndata](control-text-input.md)** kontroll, for brukere å angi strekkoder.
