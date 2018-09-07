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
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 4d75fcd4c0605e295c1e61c5232ba747203d1647
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/24/2018
ms.locfileid: "42854151"
---
# <a name="accessibility-properties-in-powerapps"></a>Egenskaper for tilgjengelighet i PowerApps
Konfigurasjon av egenskaper som tilbyr alternative måter å arbeide interaktivt med kontroller som er egnet for brukere med funksjonshemninger på.

### <a name="properties"></a>Egenskaper
**AccessibleLabel** – etikett for skjermlesere. En tom verdi for kontroller av typen Bilde, Ikon og Figur gjør dem usynlige for skjermleseren og fører til at de behandles som dekorasjoner.

**TabIndex** – navigasjonsrekkefølge for tastatur i forhold til andre kontroller.

Standardverdien er null og angir standard tabulatorrekkefølge basert på kontrollens XY-koordinater.  Hvis du angir en verdi som er høyere enn null, flyttes kontrollens plass i tabulatorrekkefølgen foran alle kontroller med standardverdiene.  En kontroll med tabulatorindeks-verdien 2 vil stå foran en med tabulatorindeks-verdier på 3 eller høyere ved bruk av tabulator.

Merk at beholdere som Figur- og Galleri-kontroller alltid vil tabulere gjennom alle elementene i beholderen før de fortsetter til kontroller utenfor beholderen.  Beholderens plass i tabulatorrekkefølgen er plassen angitt av den laveste tabulatorindeks-verdien til en underordnet kontroll.

Hvis du angir Tabulatorindeks som -1, deaktiveres tabulatortilgang til kontrollen. Dette gjør Bilder, Ikoner og Figurer til ikke-interaktive elementer.
