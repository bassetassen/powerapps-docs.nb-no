---
title: 'Strek kode-skanner kontroll: referanse | Microsoft Docs'
description: Informasjon, deriblant egenskaper og eksempler, om strek kode-skanner kontrollen
author: fikaradz
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.date: 11/25/2018
ms.author: fikaradz
ms.reviewer: tapanm
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 56d8ca116b4b683d7096ef08f550dfa11c32d3c6
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/07/2019
ms.locfileid: "71986433"
---
# <a name="barcode-scanner-control-for-canvas-apps"></a>Strek kode – skanner kontroll for lerret apper

Skanner strek koder, QR-koder og data matriseskjerm på en Android-eller iOS-enhet. Støttes ikke i en nett leser.

## <a name="description"></a>Beskrivelse

Kontrollen åpner en opprinnelig skanner på en Android-eller iOS-enhet. Skanneren registrerer automatisk en strek kode, en QR-kode eller en data kode i visning. Kontrollen støtter ikke skanning i en nett leser.

Kontrollen støtter QR-koder, data matriseskjerm og disse typene strek koder:

- UPC A
- UPC E
- EAN 8
- EAN 13
- KODE 39
- KODE 128
- ITF
- PDF 417

## <a name="key-properties"></a>Nøkkelegenskaper

**Verdi** – egenskapen output som inneholder tekst verdien til koden som ble skannet sist.

**Tekst** tekst som vises på knappen som aktiverer skanneren.

**OnScan** – hvordan en app reagerer når en strek kode blir skannet.

## <a name="additional-properties"></a>Tilleggsegenskaper

**[BorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje.

**[BorderStyle](properties-color-border.md)** – om kontrollens kantlinje er satt til **Heltrukket**, **Stiplet**, **Prikket** eller **Ingen**.

**[BorderThickness](properties-color-border.md)** – tykkelsen til kontrollens kantlinje.

**[DisplayMode](properties-core.md)** – om kontrollen tillater brukerinndata (**Rediger**), bare viser data (**Vis**) eller er deaktivert (**Deaktivert**).

**FlashlightEnabled** – om flashlight er aktivert automatisk når skanneren åpnes.

**[Høyde](properties-size-location.md)** – høyden på knappen som aktiverer skanneren.

**PreferFrontCamera** – om det front kameraet, når tilgjengelig, brukes til skanning.

**[Verktøytips](properties-core.md)** – forklarende tekst som vises når brukeren holder pekeren over en kontroll.

**Type** -kode typen som ble oppdaget i søket som ble utført sist.

**[Synlig](properties-core.md)** – om kontrollen vises eller skjules.

**[Bredde](properties-size-location.md)** – bredden på knappen som aktiverer skanneren.

**[X](properties-size-location.md)** – avstanden mellom kontrollens venstre kant og den venstre kanten til kontrollens overordnede beholder (eller skjermen, hvis det ikke finnes noen overordnet beholder).

**[Y](properties-size-location.md)** – avstanden mellom kontrollens øvre kant og den øvre kanten til kontrollens overordnede beholder (eller skjermen, hvis det ikke finnes noen overordnet beholder).

## <a name="accessibility-guidelines"></a>Retningslinjer for tilgjengelighet
De samme retnings linjene for **[knapp](control-button.md)** -kontrollen gjelder for **Strekkode skanner** kontrollen, fordi det er en knapp som starter søket.

### <a name="visual-alternatives"></a>Visuelle alternativer
* Strek kode skanneren er en knapp som ikke viser skanne resultatet. Vurder å vise skanne resultatet med en **[etikett](control-text-box.md)** -kontroll. Angi etikettens **[tekst](properties-core.md)** -egenskap til **verdi** for egenskapen for strek kode skanneren. Angi etikettens **[direkte](properties-accessibility.md)** egenskap til **Polite** , slik at brukere av skjerm leseren varsles om endringer. Denne endringen gjør den skannede verdien tilgjengelig for alle, uavhengig av visuell evne.

* Brukere som har visuelle hemminger og motor funksjons hemninger, foretrekker kanskje ikke å peke kameraet på en strek kode. Vurder å legge til en annen form for inn data, for eksempel en **[tekst inn data](control-text-input.md)** -kontroll, der brukere kan angi strek koder.
