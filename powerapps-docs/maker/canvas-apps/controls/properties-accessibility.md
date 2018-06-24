---
title: Egenskaper for tilgjengelighet | Microsoft Docs
description: Referanseinformasjon om egenskaper som Tabulatorindeks, Verktøytips
documentationcenter: na
author: fikaradz
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: reference
ms.component: canvas
ms.date: 01/26/2017
ms.author: fikaradz
ms.openlocfilehash: 94d15ff14ccd57ccc392eae47b6c10d6cec50bb1
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/04/2018
ms.locfileid: "31825215"
---
# <a name="accessibility-properties-in-powerapps"></a>Egenskaper for tilgjengelighet i PowerApps
Konfigurasjon av egenskaper som tilbyr alternative måter å arbeide interaktivt med kontroller som er egnet for brukere med funksjonshemninger på.

### <a name="properties"></a>Egenskaper
**AccessibleLabel** – etikett for skjermlesere. En tom verdi for kontroller av typen Bilde, Ikon og Figur gjør dem usynlige for skjermleseren og fører til at de behandles som dekorasjoner.

**TabIndex** – navigasjonsrekkefølge for tastatur i forhold til andre kontroller.

Standardverdien er null og angir standard tabulatorrekkefølge basert på kontrollens XY-koordinater.  Hvis du angir en verdi som er høyere enn null, flyttes kontrollens plass i tabulatorrekkefølgen foran alle kontroller med standardverdiene.  En kontroll med tabulatorindeks-verdien 2 vil stå foran en med tabulatorindeks-verdier på 3 eller høyere ved bruk av tabulator.

Merk at beholdere som Figur- og Galleri-kontroller alltid vil tabulere gjennom alle elementene i beholderen før de fortsetter til kontroller utenfor beholderen.  Beholderens plass i tabulatorrekkefølgen er plassen angitt av den laveste tabulatorindeks-verdien til en underordnet kontroll.

Hvis du angir Tabulatorindeks som -1, deaktiveres tabulatortilgang til kontrollen. Dette gjør Bilder, Ikoner og Figurer til ikke-interaktive elementer.
