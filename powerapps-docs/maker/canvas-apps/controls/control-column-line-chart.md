---
title: 'Stolpediagram-kontroll og Linjediagram-kontroll: referanse | Microsoft Docs'
description: Informasjon, deriblant egenskaper og eksempler, om Stolpediagram-kontroller og Linjediagram-kontroller
author: fikaradz
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.date: 10/25/2016
ms.author: fikaradz
ms.reviewer: anneta
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 9c290d28db7ae35d33f4ceb2cd56c3a3ad79b01c
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/23/2019
ms.locfileid: "61559384"
---
# <a name="column-chart-and-line-chart-controls-in-powerapps"></a>Stolpediagram- og Linjediagram-kontroller i PowerApps
Kontroller som viser data som grafer med x- og y-akser.

## <a name="description"></a>Beskrivelse
**Stolpediagram** og **Linjediagram** er grupperte kontroller. Hver gruppe inneholder tre kontroller: En **[Etikett](control-text-box.md)** for tittelen, en for diagramgrafikken, og en for **Forklaring**.

## <a name="chart-key-properties"></a>Nøkkelegenskaper for diagram
**[Elementer](properties-core.md)** – kilden til dataene som vises i en kontroll, for eksempel et galleri, en liste eller et diagram.

**NumberOfSeries** – hvor mange kolonner med data som gjenspeiles i et stolpediagram eller linjediagram.

## <a name="additional-chart-properties"></a>Egenskaper for flere diagram
**[BorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje.

**[BorderStyle](properties-color-border.md)** – om kontrollens kantlinje er satt til **Heltrukket**, **Stiplet**, **Prikket** eller **Ingen**.

**[BorderThickness](properties-color-border.md)** – tykkelsen til kontrollens kantlinje.

**[Farge](properties-color-border.md)** – fargen på teksten i kontrollen.

**[DisabledBorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje hvis kontrollens **[DisplayMode](properties-core.md)**-egenskap er angitt til **Deaktivert**.

**[DisplayMode](properties-core.md)** – om kontrollen tillater brukerinndata (**Rediger**), bare viser data (**Vis**) eller er deaktivert (**Deaktivert**).

**[Skrift](properties-text.md)** – navnet på skriftserien som teksten vises i.

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

**[TabIndex](properties-accessibility.md)** – navigasjonsrekkefølge for tastatur i forhold til andre kontroller.

**[Synlig](properties-core.md)** – om kontrollen vises eller skjules.

**[Bredde](properties-size-location.md)** – avstanden mellom kontrollens venstre og høyre kant.

**[X](properties-size-location.md)** – avstanden mellom kontrollens venstre kant og den venstre kanten til kontrollens overordnede beholder (eller skjermen, hvis det ikke finnes noen overordnet beholder).

**XLabelAngle** – vinkelen til etikettene under x-aksen i et stolpe- eller linjediagram.

**[Y](properties-size-location.md)** – avstanden mellom kontrollens øvre kant og den øvre kanten til kontrollens overordnede beholder (eller skjermen, hvis det ikke finnes noen overordnet beholder).

**YAxisMax** – den maksimale verdien for y-aksen til et linjediagram.

* **YAxisMax**-egenskapen er tilgjengelig for **Linjediagram**-kontrollen, men ikke for **Stolpediagram**-kontrollen.

**YAxisMin** – den minste verdien for y-aksen til et linjediagram.

* **YAxisMin**-egenskapen er tilgjengelig for **Linjediagram**-kontrollen, men ikke for **Stolpediagram**-kontrollen.

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


## <a name="accessibility-guidelines"></a>Retningslinjer for tilgjengelighet
### <a name="color-contrast"></a>Fargekontrast
Det må være tilstrekkelig fargekontrast mellom:
* hvert element i **ItemColorSet**
* hvert element i **ItemColorSet** og bakgrunnsfargen
* **[Farge](properties-color-border.md)** og bakgrunnsfarge

### <a name="screen-reader-support"></a>Kundestøtte for skjermlesere
* Det må være en **[etikett](control-text-box.md)** rett før diagramgrafikken, som skal fungere som tittelen.
* Vurder å legge til et sammendrag av diagramgrafikken. For eksempel «linjediagrammet viser en stadig økning i salg mellom mars og august dette året».

    > [!NOTE]
  > Diagramgrafikk og **Forklaring** er skjult for brukere av skjermleseren. Som et alternativ presenteres en tabellform av dataene for dem. De kan også se gjennom knapper som velger dataene i diagrammet.

### <a name="low-vision-support"></a>Støtte for nedsatt syn
* Det må være en **forklaring** hvis mer enn én dataserie vises.
* Du bør vurdere å angi **GridStyle** til GridStyle.All, som viser begge akser. Dette hjelper alle brukere å bestemme nøyaktig omfang for dataene.
* For **Stolpediagram** bør du vurdere å angi **Indikatorer** til **sann**. Dette hjelper brukere med nedsatt syn å bestemme verdien for en kolonne.

### <a name="keyboard-support"></a>Tastaturstøtte
* **[TabIndex](properties-accessibility.md)** må være null eller større, slik at tastaturbrukere kan navigere til den.

    > [!NOTE]
  > Når tastaturbrukere navigerer til diagrammet, kan de gå gjennom knappene som velger dataene i diagrammet.
