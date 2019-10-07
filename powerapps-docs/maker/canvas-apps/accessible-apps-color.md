---
title: Tilgjengelige farger i lerretsapper | Microsoft Docs
description: Retningslinjer for fargekontrast for lerretsapper i PowerApps
author: tahoon
manager: kvivek
ms.service: powerapps
ms.topic: article
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 04/23/2018
ms.author: tahoon
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: f704b96150b0021b7170fc095cc6561cd3aac908
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/07/2019
ms.locfileid: "71987775"
---
# <a name="accessible-colors-for-canvas-apps-in-powerapps"></a>Tilgjengelige farger for lerretsapper i PowerApps
Fargene som brukes i en lerretsapp, skal være tilpasset for fargeblinde og svaksynte brukere. Alle PowerApps-temaer er tilpassede som standard. Følg disse retningslinjene for å sikre at fargene forblir tilgjengelige når du endrer dem i et program. Det finnes flere verktøy tilgjengelige på nettet som kan hjelpe deg med å oppdage problemer knyttet til fargekontrast.

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
> I [WCAG 2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/visual-audio-contrast-contrast.html)-standarden gjelder kontrastkrav bare for tekst. Hvis du vil ha bedre tilgjengelighet, kan du vurdere det kommende [WCAG 2.1-retningslinjer for kontrast](https://www.w3.org/TR/WCAG21/#non-text-contrast) for viktige komponenter, som ikonknapper, i brukergrensesnittet. Et forhold på minst 3:1 anbefales for disse komponentene. Retnings linjene som er beskrevet i denne delen, er **valg frie** for WCAG 2,0-samsvar.

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
Hvis et bilde viser viktig informasjon, kan det være en god idé å sjekke det for kontrastproblemer. Dette gjelder for kontroller der et bilde kan vises: **[Lyd](controls/control-audio-video.md)** , **[bilde](controls/control-image.md)** , **[mikrofon](controls/control-microphone.md)** og **[video](controls/control-audio-video.md)** .

Når det gjelder videoinnhold, bør du vurdere å sjekke det for kontrastproblemer. Du kan alternativt, eller i tillegg, tilby [teksting for hørselshemmede](controls/control-audio-video.md), som beskriver videoen.

## <a name="provide-other-visual-cues"></a>Gi andre visuelle indikatorer
Sørg for at appen ikke bruker bare farge til å formidle informasjon. For eksempel, brukere med rød-grønn fargeblindhet kan ikke skille mellom en rød feilmelding og en grønn suksessmelding.

Ekstra hjelpemidler, som et **[ikon](controls/control-shapes-icons.md)** eller tekststiler som **[kursiv](controls/properties-text.md)** og **[understreking](controls/properties-text.md)** , kan bidra til å formidle betydning.

## <a name="next-steps"></a>Neste trinn
Finn ut mer om [egenskaper for tilgjengelighet](controls/properties-accessibility.md) i PowerApps-kontroller, og prøv å [bruke Tilgjengelighetskontrollen](accessibility-checker.md).
