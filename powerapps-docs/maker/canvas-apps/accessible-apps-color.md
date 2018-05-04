---
title: Tilgjengelige farger i PowerApps | Microsoft Docs
description: Retningslinjer for fargekontrast i PowerApps
services: ''
suite: powerapps
documentationcenter: na
author: tahoon
manager: anneta
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 04/23/2018
ms.author: tahoon
ms.openlocfilehash: 37e456cab861b438ee07804d6b131ed6b22d56b9
ms.sourcegitcommit: 8bd4c700969d0fd42950581e03fd5ccbb5273584
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/26/2018
---
# <a name="accessible-colors-in-powerapps"></a>Tilgjengelige farger i PowerApps
Fargene som brukes i en app, skal være tilpasset for fargeblinde og svaksynte brukere. Alle PowerApps-temaer er tilpassede som standard. Følg disse retningslinjene for å sikre at fargene forblir tilgjengelige når du endrer dem i et program.

## <a name="minimum-contrast-for-text"></a>Minimum kontrast for tekst
* Teksten og bakgrunnen må ha en kontrast på minst 4,5:1
* Stor tekst må ha en kontrast på minst 3:1
* Deaktivert tekst har ingen krav til kontrast

I praksis betyr dette at alle interaktive kontroller må ha nok fargekontrast mellom:
* **[Farge](controls/properties-color-border.md)** og **[Fyll](controls/properties-color-border.md)**
* **[TrykketFarge](controls/properties-color-border.md)** og **[TrykketFyll](controls/properties-color-border.md)**
* **[Pekefarge](controls/properties-color-border.md)** og **[Pekefyll](controls/properties-color-border.md)**

## <a name="minimum-contrast-for-non-text"></a>Minimumkontrast for annet enn tekst

> [!NOTE]
> I [WCAG 2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/visual-audio-contrast-contrast.html)-standarden gjelder kontrastkrav bare for tekst. Hvis du vil ha bedre tilgjengelighet, kan du vurdere det kommende [WCAG 2.1-retningslinjer for kontrast](https://www.w3.org/TR/WCAG21/#non-text-contrast) for viktige komponenter, som ikonknapper, i brukergrensesnittet. Et forhold på minst 3:1 anbefales for disse komponentene. Retningslinjene beskrevet i denne delen, er **valgfrie** for samsvar med WCAG 2.0.

### <a name="user-interface-components"></a>Komponenter i brukergrensesnittet
Alle interaktive kontroller må ha nok fargekontrast mellom:
* **[FokusertGrenseFarge](controls/properties-color-border.md)** og farge utenfor kontrollen

Ekstra sjekk av fargekontrast gjelder for kontroller der hele området er interaktivt eller informativt. For eksempel en **[knapp](controls/control-button.md)** eller et **[ikon](controls/control-shapes-icons.md)** som brukes som en knapp. Dette sikrer at grensene for kontrollen er tydelige og at brukerne vet hvor de kan klikke eller trykke.

Hvis det er en kantlinje for slike kontroller, skal det være tilstrekkelig fargekontrast mellom:
* **[GrenseFarge](controls/properties-color-border.md)** og farge utenfor kontrollen
* **[TrykketGrenseFarge](controls/properties-color-border.md)** og farge utenfor kontrollen
* **[PekeGrenseFarge](controls/properties-color-border.md)** og farge utenfor kontrollen

Hvis det ikke er en kantlinje, skal det være tilstrekkelig fargekontrast mellom:
* **[Fyll](controls/properties-color-border.md)** og farge utenfor kontrollen
* **[TrykketFyll](controls/properties-color-border.md)** og farge utenfor kontrollen
* **[Pekefyll](controls/properties-color-border.md)** og farge utenfor kontrollen

### <a name="graphical-objects"></a>Grafiske objekter
Hvis et bilde viser viktig informasjon, kan det være en god idé å sjekke det for kontrastproblemer. Dette gjelder for kontroller der et bilde kan vises: **[Lyd](controls/control-audio-video.md)**, **[Bilde](controls/control-image.md)**, **[Mikrofon](controls/control-microphone.md)**, og **[Video](controls/control-audio-video.md)**.

Når det gjelder videoinnhold, bør du vurdere å sjekke det for kontrastproblemer. Du kan alternativt, eller i tillegg, tilby [teksting for hørselshemmede](controls/control-audio-video.md), som beskriver videoen.

## <a name="provide-other-visual-cues"></a>Gi andre visuelle indikatorer
Sørg for at appen ikke bruker bare farge til å formidle informasjon. For eksempel, brukere med rød-grønn fargeblindhet kan ikke skille mellom en rød feilmelding og en grønn suksessmelding.

Ekstra hjelpemidler, som et **[ikon](controls/control-shapes-icons.md)** eller tekststiler som **[kursiv](controls/properties-text.md)** og **[understreking](controls/properties-text.md)**, kan bidra til å formidle betydning.

## <a name="next-steps"></a>Neste trinn
Finn ut mer om [egenskaper for tilgjengelighet](controls/properties-accessibility.md) i PowerApps-kontrollene.