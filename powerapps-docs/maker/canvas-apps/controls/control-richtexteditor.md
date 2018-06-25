---
title: 'Redigeringskontroll for rik tekst: referanse | Microsoft Docs'
description: Informasjon om redigeringskontrollen for rik tekst, inkludert egenskaper og eksempler
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
ms.date: 05/24/2018
ms.author: fikaradz
ms.openlocfilehash: 36fa317a4611c72ab4d2f6ce09e176b14b688a55
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/04/2018
ms.locfileid: "34585093"
---
# <a name="rich-text-editor-control-experimental-in-powerapps"></a>Redigeringskontrollen for rik tekst (eksperimentell) i PowerApps
En eksperimentell kontroll som gjør at sluttbrukere kan formatere teksten i et WYSIWYG-redigeringsområde.  Utdataformatet er HTML.

## <a name="description"></a>Beskrivelse
Kontrollen for **redigeringsprogrammet for rik tekst** gir appbrukeren et WYSIWYG-redigeringsområde for formatering av tekst.  Kontrollens inn- og utdataformat er HTML.

Kontrollen tillater at man kan bruke kopiert rik tekst (dvs. fra nettleser eller Word) og lime den inn i kontrollen.  

Kontrollens tiltenkte bruk er å formatere tekst, og det garanteres ikke at man beholder integriteten til HTML-inndataene.  Alle skript, stiler, objekt og andre potensielt skadelige koder fjernes av redigeringsprogrammet.  Dette betyr at hvis rik tekst ble opprettet utenfor PowerApps, ser den kanskje ikke ut slik den ser ut i produktet den ble opprettet i.

Støttede funksjoner inkluderer for øyeblikket:
- Fet, kursiv, understreking
- Tekstfarge, uthevingsfarge
- Tekststørrelse
- Nummererte lister, punktlister
- Hyperkoblinger
- Fjern formatering

Hvis du vil bruke kontrollen i et skjema, velger du kortet «Rediger flerlinjet tekst», og tilpasser den ved å sette inn RTE-kontrollen.

## <a name="limitations"></a>Begrensninger
Den gjeldende versjonen av kontrollen er eksperimentell på grunn av følgende midlertidige begrensninger:
- Kontrollen har begrensede funksjoner for formatering av tekst.  

- Kontrollen er hovedsakelig beregnet for bruk i nettlesere på store skjermer.  Å bruke kontrollen på en mobiltelefon kan det være en frustrerende opplevelse.

- Kjente problemer i redigeringsopplevelsen når du bruker Windows Studio- eller Edge-nettleseren.  Gjeldende anbefaling er å bruke web studio i Chrome.


## <a name="key-properties"></a>Nøkkelegenskaper
**[Standard](properties-core.md)** – inndata-egenskapen for den første tekstverdien vises i redigeringsprogrammet.

**HtmlText** – utdata-egenskapen for den resulterende for rike teksten i HTML-format.



## <a name="additional-properties"></a>Tilleggsegenskaper
**[AccessibleLabel](properties-accessibility.md)** – etikett for skjermlesere. Skal beskrive formålet med vedleggene.

**[DisplayMode](properties-core.md)** – om kontrollen tillater tillegging og sletting av filer (**Rediger**), bare viser data (**Vis**) eller er deaktivert (**Deaktivert**).

**[Høyde](properties-size-location.md)** – avstanden mellom kontrollens øvre og nedre kant.

**[TabIndex](properties-accessibility.md)** – navigasjonsrekkefølge for tastatur i forhold til andre kontroller.

**[Synlig](properties-core.md)** – om kontrollen er synlig eller skjult.

**[Bredde](properties-size-location.md)** – avstanden mellom kontrollens venstre og høyre kant.

**[X](properties-size-location.md)** – avstanden mellom kontrollens venstre kant og den venstre kanten til kontrollens overordnede beholder (eller skjermen, hvis det ikke finnes noen overordnet beholder).

**[Y](properties-size-location.md)** – avstanden mellom kontrollens øvre kant og den øvre kanten til kontrollens overordnede beholder (eller skjermen, hvis det ikke finnes noen overordnet beholder).
