---
title: 'Stolpediagram-kontroll og Linjediagram-kontroll: referanse | Microsoft Docs'
description: Informasjon, deriblant egenskaper og eksempler, om Stolpediagram-kontroller og Linjediagram-kontroller
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
ms.openlocfilehash: 039b267394ef6be5e3038fa0b07149f69fee6a51
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/22/2018
ms.locfileid: "30996242"
---
# <a name="column-chart-and-line-chart-controls-in-powerapps"></a>Stolpediagram- og Linjediagram-kontroller i PowerApps
Kontroller som viser data som grafer med x- og y-akser.

## <a name="description"></a>Beskrivelse
Som standard består **Stolpediagram**-kontroller og **Linjediagram**-kontroller av flere kontroller som er gruppert sammen. Disse kontrollene viser en tittel, data og en forklaring.

## <a name="key-properties"></a>Nøkkelegenskaper
**[Elementer](properties-core.md)** – kilden til dataene som vises i en kontroll, for eksempel et galleri, en liste eller et diagram.

**NumberOfSeries** – hvor mange kolonner med data som gjenspeiles i et stolpediagram eller linjediagram.

## <a name="all-properties"></a>Alle egenskaper
**[Kantlinjefarge](properties-color-border.md)** – fargen på kontrollens kantlinje.

**[BorderStyle](properties-color-border.md)** – om kontrollens kantlinje er satt til **Heltrukket**, **Stiplet**, **Prikket** eller **Ingen**.

**[BorderThickness](properties-color-border.md)** – tykkelsen til kontrollens kantlinje.

**[Farge](properties-color-border.md)** – fargen på teksten i kontrollen.

**[DisplayMode](properties-core.md)** – om kontrollen tillater brukerinndata (**Rediger**), bare viser data (**Vis**) eller er deaktivert (**Deaktivert**).

**[DisabledBorderColor](properties-color-border.md)**  – fargen på kontrollens kantlinje hvis kontrollens **[DisplayMode](properties-core.md)**-egenskapen er angitt som **Deaktivert**.

**[Skrift](properties-text.md)**  – navnet på skriftserien som teksten vises i.

**GridStyle** – om et stolpe- eller linjediagram viser x-aksen, y-aksen, begge eller ingen av delene.

**[Høyde](properties-size-location.md)** – avstanden mellom kontrollens øvre og nedre kant.

**[HoverBorderColor](properties-color-border.md)**  – fargen på kontrollens kantlinje når brukeren holder musepekeren på denne kontrollen.

**ItemColorSet** – fargen på hvert datapunkt i et diagram.

**ItemsGap** – avstanden mellom kolonner i et stolpediagram.

* **ItemsGap**-egenskapen er tilgjengelig for **Stolpediagram**-kontrollen, men ikke for **Linjediagram**-kontrollen.

**Markers** – om et kolonne- eller stolpediagram viser verdien for hvert datapunkt.

**MarkerSuffix** – teksten som vises etter hver verdi i et stolpediagram hvor **Markers**-egenskapen er angitt som **sann**.

* **MarkerSuffix**-egenskapen er tilgjengelig for **Stolpediagram**-kontrollen, men ikke for **Linjediagram**-kontrollen.

**MinimumBarWidth** – den smaleste mulige bredden på kolonner i et stolpediagram.

* **MinimumBarWidth**-egenskapen er tilgjengelig for **Stolpediagram**-kontrollen, men ikke for **Linjediagram**-kontrollen.

**[OnSelect](properties-core.md)** – hvordan appen responderer når brukeren klikker eller trykker på en kontroll.

**[PaddingBottom](properties-size-location.md)** – avstanden mellom teksten i en kontroll og den nederste kanten av kontrollen.

**[PaddingLeft](properties-size-location.md)** – avstanden mellom teksten i en kontroll og den venstre kanten av kontrollen.

**[PaddingRight](properties-size-location.md)** – avstanden mellom teksten i en kontroll og den høyre kanten av kontrollen.

**[PaddingTop](properties-size-location.md)** – avstanden mellom teksten i en kontroll og den øverste kanten av kontrollen.

**[PressedBorderColor](properties-color-border.md)**  – fargen på kontrollens kantlinje når brukeren trykker eller klikker på kontrollen.

**SeriesAxisMax** – den maksimale verdien for y-aksen til et stolpe- eller linjediagram.

* **SeriesAxisMax**-egenskapen er tilgjengelig for **Stolpediagram**-kontrollen, men ikke for **Linjediagram**-kontrollen.

**SeriesAxisMin** – et tall som angir den minste verdien av y-aksen for et stolpediagram.

* **SeriesAxisMin**-egenskapen er tilgjengelig for **Stolpediagram**-kontrollen, men ikke for **Linjediagram**-kontrollen.

**[Størrelse](properties-text.md)** – skriftstørrelsen på teksten som vises på en kontroll.

**[Synlig](properties-core.md)** – om kontrollen vises eller skjules.

**[Bredde](properties-size-location.md)** – avstanden mellom kontrollens venstre og høyre kant.

**[X](properties-size-location.md)** – avstanden mellom kontrollens venstre kant og den venstre kanten til kontrollens overordnede beholder (eller skjermen, hvis det ikke finnes noen overordnet beholder).

**XLabelAngle** – vinkelen til etikettene under x-aksen i et stolpe- eller linjediagram.

**[Y](properties-size-location.md)** – avstanden mellom kontrollens øvre kant og den øvre kanten til kontrollens overordnede beholder (eller skjermen, hvis det ikke finnes noen overordnet beholder).

**YAxisMax** – den maksimale verdien for y-aksen til et linjediagram.

* **YAxisMax**-egenskapen er tilgjengelig for **Stolpediagram**-kontrollen, men ikke for **Linjediagram**-kontrollen.

**YAxisMin** – den minste verdien for y-aksen til et linjediagram.

* **YAxisMin**-egenskapen er tilgjengelig for **Stolpediagram**-kontrollen, men ikke for **Linjediagram**-kontrollen.

**YLabelAngle** – vinkelen til etikettene ved siden av y-aksen i et stolpe- eller linjediagram.

## <a name="related-functions"></a>Relaterte funksjoner
[**Max**( *DataSource*, *ColumnName* )](../functions/function-aggregates.md)

## <a name="example"></a>Eksempel
1. Legg til en **[Knapp](control-button.md)**, og angi **[OnSelect](properties-core.md)**-egenskapen til denne formelen:<br>
   **Collect(Revenue, {Year:"2013", Europa:24000, Ganymede:22300, Callisto:21200}, {Year:"2014", Europa:26500, Ganymede:25700, Callisto:24700},{Year:"2014", Europa:27900, Ganymede:28300, Callisto:25600})**
   
    Lurer du på hvordan du [legger til og konfigurerer en kontroll](../add-configure-controls.md)?
   
    Vil du ha mer informasjon om **[Collect](../functions/function-clear-collect-clearcollect.md)**-funksjonen eller [andre funksjoner](../formula-reference.md)?
2. Trykk på F5, klikk eller trykk på **[Knapp](control-button.md)**, og trykk deretter på ESC for å gå tilbake til standardarbeidsområdet.
3. Legg til en **Stolpediagram**-kontroll eller en **Linjediagram**-kontroll, angi kontrollens **[Elementer](properties-core.md)**-egenskap til **Omsetning**, og angi **NumberOfSeries**-egenskapen som **3**.
   
    Kontrollen viser omsetningsdata for hvert produkt over tre år.

