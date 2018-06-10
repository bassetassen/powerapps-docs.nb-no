---
title: 'Sektordiagram-kontrollen: referanse | Microsoft Docs'
description: Informasjon om Sektordiagram-kontrollen, inkludert egenskaper og eksempler
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
ms.openlocfilehash: 1388eac45e5086f677cb83c8db9593fe01a9819f
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/22/2018
ms.locfileid: "30995992"
---
# <a name="pie-chart-control-in-powerapps"></a>Sektordiagram-kontrollen i PowerApps
En kontroll som viser relative verdier sammenlignet med hverandre.

## <a name="description"></a>Beskrivelse
Legg til en **sektordiagram**-kontroll hvis du vil vise relative data fra en tabell som inneholder etikettene i kolonnen lengst til venstre og verdiene i den andre kolonnen fra venstre.

## <a name="key-properties"></a>Nøkkelegenskaper
**[Elementer](properties-core.md)** – kilden til dataene som vises i en kontroll, for eksempel et galleri, en liste eller et diagram.

**ShowLabels** – angir om sektordiagrammet skal vise verdien hver av sektorene representerer.

## <a name="additional-properties"></a>Tilleggsegenskaper
**[BorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje.

**[BorderStyle](properties-color-border.md)** – Om kontrollens kantlinje er satt til **Heltrukket**, **Stiplet**, **Prikket** eller **Ingen**.

**[BorderThickness](properties-color-border.md)** – tykkelsen til kontrollens kantlinje.

**[Farge](properties-color-border.md)** – fargen på teksten i kontrollen.

**[DisplayMode](properties-core.md)** – om kontrollen tillater brukerinndata (**Rediger**), bare viser data (**Vis**) eller er deaktivert (**Deaktivert**).

**[DisabledBorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje hvis kontrollens **[DisplayMode](properties-core.md)**-egenskap er angitt som **Deaktivert**.

**Explode** – avstanden mellom stykker i et sektordiagram.

**[Skrift](properties-text.md)**  – navnet på skriftserien som teksten vises i.

**[Høyde](properties-size-location.md)** – avstanden mellom kontrollens øvre og nedre kant.

**[HoverBorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje når brukeren holder musepekeren på denne kontrollen.

**ItemBorderColor** – fargen på kantlinjen rundt hver sektor i et sektordiagram.

**ItemBorderThickness** – tykkelsen på kantlinjen rundt hver sektor i et sektordiagram.

**ItemColorSet** – fargen på hvert datapunkt i et diagram.

**LabelPosition** – plasseringen av etikettene i et sektordiagram i forhold til sektorene.

**[OnSelect](properties-core.md)** – hvordan appen reagerer når brukeren klikker eller trykker på en kontroll.

**[PressedBorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje når brukeren trykker eller klikker på kontrollen.

**[Størrelse](properties-text.md)** – skriftstørrelsen på teksten som vises på en kontroll.

**[Synlig](properties-core.md)** – om kontrollen vises eller skjules.

**[Bredde](properties-size-location.md)** – avstanden mellom kontrollens venstre og høyre kant.

**[X](properties-size-location.md)** – avstanden mellom kontrollens venstre kant og den venstre kanten til kontrollens overordnede beholder (eller skjermen, hvis det ikke finnes noen overordnet beholder).

**[Y](properties-size-location.md)** – avstanden mellom kontrollens øvre kant og den øvre kanten til kontrollens overordnede beholder (eller skjermen, hvis det ikke finnes noen overordnet beholder).

## <a name="related-functions"></a>Relaterte funksjoner
[**Max**( *DataSource*, *ColumnName* )](../functions/function-aggregates.md)

## <a name="example"></a>Eksempel
1. Legg til en **[Knapp](control-button.md)**, og angi **[OnSelect](properties-core.md)**-egenskapen til denne formelen:<br>
   **Collect(Revenue2015, {Product:"Europa", Revenue:27000}, {Product:"Ganymede", Revenue:26300}, {Product:"Callisto", Revenue:29200})**
   
    Lurer du på hvordan du [legger til og konfigurerer en kontroll](../add-configure-controls.md)?
   
    Vil du ha mer informasjon om **[Collect](../functions/function-clear-collect-clearcollect.md)**-funksjonen eller [andre funksjoner](../formula-reference.md)?
2. Trykk på F5, klikk eller trykk på **[Knapp](control-button.md)**, og trykk deretter på ESC for å gå tilbake til standardarbeidsområdet.
3. Legg til en **sektordiagram**-kontroll, og angi **[Elementer](properties-core.md)**-egenskapen som **Revenue2015**.
   
    **Sektordiagram**-kontrollen viser omsetningsdata for hvert produkt i forhold til de andre produktene.

