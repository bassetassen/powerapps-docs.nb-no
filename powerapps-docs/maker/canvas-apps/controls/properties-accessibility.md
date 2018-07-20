---
title: Egenskaper for tilgjengelighet | Microsoft Docs
description: Referanseinformasjon om egenskaper som Tabulatorindeks, Verktøytips
author: fikaradz
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 01/26/2017
ms.author: fikaradz
ms.openlocfilehash: 59cc231dfc461a2301de90a7a995ec2ec82790cb
ms.sourcegitcommit: dfa0e1a7981814e15e6ca4720e2a5f930e859db1
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 07/13/2018
ms.locfileid: "39022934"
---
# <a name="accessibility-properties-in-powerapps"></a>Egenskaper for tilgjengelighet i PowerApps
Konfigurasjon av egenskaper som tilbyr alternative måter å arbeide interaktivt med kontroller som er egnet for brukere med funksjonshemninger på.

### <a name="properties"></a>Egenskaper
**AccessibleLabel** – etikett for skjermlesere. En tom verdi for kontroller av typen Bilde, Ikon og Figur gjør dem usynlige for skjermleseren og fører til at de behandles som dekorasjoner.

**TabIndex** – navigasjonsrekkefølge for tastatur i forhold til andre kontroller.

Standardverdien er null og angir standard tabulatorrekkefølge basert på kontrollens XY-koordinater.  Hvis du angir en verdi som er høyere enn null, flyttes kontrollens plass i tabulatorrekkefølgen foran alle kontroller med standardverdiene.  En kontroll med tabulatorindeks-verdien 2 vil stå foran en med tabulatorindeks-verdier på 3 eller høyere ved bruk av tabulator.

Merk at beholdere som Figur- og Galleri-kontroller alltid vil tabulere gjennom alle elementene i beholderen før de fortsetter til kontroller utenfor beholderen.  Beholderens plass i tabulatorrekkefølgen er plassen angitt av den laveste tabulatorindeks-verdien til en underordnet kontroll.

Hvis du angir Tabulatorindeks som -1, deaktiveres tabulatortilgang til kontrollen. Dette gjør Bilder, Ikoner og Figurer til ikke-interaktive elementer.
