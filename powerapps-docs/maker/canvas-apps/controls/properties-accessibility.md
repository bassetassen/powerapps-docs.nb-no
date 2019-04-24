---
title: Egenskaper for tilgjengelighet for lerretsapper | Microsoft Docs
description: Referanseinformasjon om egenskaper som Tabulatorindeks og verktøytips
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
ms.openlocfilehash: 5fa8b6fecdf690114cbf6a0945f2dfec66b067c3
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/23/2019
ms.locfileid: "61560419"
---
# <a name="accessibility-properties-for-canvas-apps"></a>Egenskaper for tilgjengelighet for lerretsapper

Konfigurasjon av egenskaper som tilbyr alternative måter å arbeide interaktivt med kontroller som er egnet for brukere med funksjonshemninger på.

## <a name="properties"></a>Egenskaper

**AccessibleLabel** – etikett for skjermlesere. En tom verdi for kontroller av typen Bilde, Ikon og Figur gjør dem usynlige for skjermleseren og fører til at de behandles som dekorasjoner.

**Live** – hvordan bør skjermlesere lese opp endringer i innholdet. Bare tilgjengelig i den **[etikett](control-text-box.md)** kontroll.

* Når satt til **av**, skjermleseren ikke si endringer.
* Når satt til **Polite**, skjermleseren er ferdig med å snakke før kunngjøring eventuelle endringer som oppstod under skjermleseren ble snakke.
* Når satt til **Assertive**, skjermleseren avbryter seg selv for å informere om eventuelle endringer som oppstod under skjermleseren ble snakke.

Lær hvordan du [kunngjøre dynamiske endringer med live områder](../accessible-apps-live-regions.md).

**TabIndex** – navigasjonsrekkefølge for tastatur i forhold til andre kontroller.

Standardverdien er null og angir standard tabulatorrekkefølge basert på kontrollens XY-koordinater.  Hvis du angir en verdi som er høyere enn null, flyttes kontrollens plass i tabulatorrekkefølgen foran alle kontroller med standardverdiene.  En kontroll med tabulatorindeks-verdien 2 vil stå foran en med tabulatorindeks-verdier på 3 eller høyere ved bruk av tabulator.

Merk at beholdere som Figur- og Galleri-kontroller alltid vil tabulere gjennom alle elementene i beholderen før de fortsetter til kontroller utenfor beholderen.  Beholderens plass i tabulatorrekkefølgen er plassen angitt av den laveste tabulatorindeks-verdien til en underordnet kontroll.

Hvis du angir Tabulatorindeks som -1, deaktiveres tabulatortilgang til kontrollen. Dette gjør Bilder, Ikoner og Figurer til ikke-interaktive elementer.
