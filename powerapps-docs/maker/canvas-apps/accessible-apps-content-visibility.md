---
title: Vis eller Skjul innhold fra hjelpefunksjoner i lerret-apper | Microsoft Docs
description: Teknikker for å vise innhold bare for innholdsformidling eller bare for brukere av skjermleseren bare for lerretsapper
author: tahoon-ms
ms.service: powerapps
ms.topic: article
ms.custom: canvas
ms.date: 10/22/2018
ms.author: tahoon
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: c680767bc6a56f0596eba03dd555c1c9a0205346
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/23/2019
ms.locfileid: "61550092"
---
# <a name="show-or-hide-content-from-assistive-technologies-for-canvas-apps"></a>Vis eller Skjul innhold fra hjelpeteknologi for lerretsapper

Alle brukere skal kunne få tilgang til alt innhold i de fleste tilfeller, men du vil kanskje noen ganger vise innhold bare for innholdsformidling eller bare for skjermleseren brukere. Du kan for eksempel vil bare skjermleseren brukere tilgang til beskrivelser av diagrammet trender som er tydelig for innholdsformidling. Du kan også hende du vil skjule et ikon fra Skjermleser brukere hvis en tilstøtende etikett beskriver den. En annen beskrivelse-ikonet er overflødig.

## <a name="hide-content-from-all-users"></a>Skjul innhold fra alle brukere

* Angi **[Visible](controls/properties-core.md)** til USANN.

## <a name="hide-content-from-sighted-users-and-show-it-to-screen-reader-users"></a>Skjul innhold fra innholdsformidling og Vis den til skjermleseren brukere

Bruk en av følgende måter:

* Angi **[størrelsen](controls/properties-text.md)** til 0.
* Angi **[bredde](controls/properties-size-location.md)** og **[høyde](controls/properties-size-location.md)** til 1.
* Angi  **[X](controls/properties-size-location.md)**,  **[Y](controls/properties-size-location.md)**, eller begge egenskapene slik at kontrollen er utenfor skjermen.
* Angi **[farge](controls/properties-color-border.md)** og relaterte egenskaper til gjennomsiktig.
* Plassere et rektangel **[figur](controls/control-shapes-icons.md)** over innholdet, og sett **[Fyll](controls/properties-color-border.md)** til samme farge som for bakgrunnen på skjermen.

> [!NOTE]
> Brukere kan fortsatt bruke et tastatur å få tilgang til en interaktiv kontroll, slik som en  **[knappen](controls/control-button.md)**, selv om du skjule den ved hjelp av en av metodene i den forrige listen. Angi **[TabIndex](controls/properties-accessibility.md)** til-1 Hvis du vil hindre brukere fra å få tilgang til kontrollen ved å trykke på Tab-tasten.

## <a name="hide-content-from-screen-reader-users-and-show-it-to-sighted-users"></a>Skjul innhold fra skjermleseren brukere og Vis den til innholdsformidling

* For  **[bilde](controls/control-image.md)**,  **[ikonet](controls/control-shapes-icons.md)**, og **[figur](controls/control-shapes-icons.md)** kontroller, angi **[AccessibleLabel](controls/properties-accessibility.md)** til den tomme strengen "".

## <a name="next-steps"></a>Neste trinn

Finn ut mer om [egenskaper for tilgjengelighet](controls/properties-accessibility.md) av kontroller i lerret-apper.
