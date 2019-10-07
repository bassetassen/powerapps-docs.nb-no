---
title: 'Redigeringskontroll for rik tekst: referanse | Microsoft Docs'
description: Informasjon om redigeringskontrollen for rik tekst, inkludert egenskaper og eksempler
author: fikaradz
manager: kvivek
ms.service: powerapps
ms.topic: article
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 05/24/2018
ms.author: fikaradz
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: c6b94f636ebf6d373c3fc2117b589116b5a4a2fd
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/07/2019
ms.locfileid: "71986354"
---
# <a name="rich-text-editor-control-in-powerapps"></a>Redigerings kontroll for rik tekst i PowerApps
Gjør at slutt brukere kan formatere tekst i et redigerings område for WYSIWYG.  Utdataformatet er HTML.

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


## <a name="accessibility-guidelines"></a>Retningslinjer for tilgjengelighet
### <a name="screen-reader-support"></a>Kundestøtte for skjermlesere
* **[AccessibleLabel](properties-accessibility.md)** bør vises.

### <a name="keyboard-support"></a>Tastaturstøtte
* **[TabIndex](properties-accessibility.md)** må være null eller større, slik at tastaturbrukere kan navigere til den.

> [!TIP]
> Bruk **alt + 0** mens redigerings programmet fokuserer på å finne ut mer om andre hurtig taster.