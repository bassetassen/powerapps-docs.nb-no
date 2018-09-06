---
title: Slik fungerer formler for virkemåte i en lerretsapp | Microsoft Docs
description: Referanseinformasjon om hvordan du arbeider med former for virkemåte, som endrer tilstanden til en lerretsapp i PowerApps
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 11/10/2015
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: f7aed7812890482bb781e2d5ff7eac8c996b8837
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/24/2018
ms.locfileid: "42850421"
---
# <a name="understand-behavior-formulas-for-canvas-apps-in-powerapps"></a>Slik fungerer formler for virkemåte i lerretsapper i PowerApps

De fleste formler beregner en verdi.  Omberegning skjer automatisk når verdiene endres, akkurat som i et Excel-regneark.  Du kan for eksempel vise en verdi i en **[Etikett](controls/control-text-box.md)**-kontroll i rødt hvis verdien er mindre enn null. Hvis ikke, er den svart. Så du kan angi f.eks. angi **[Color](controls/properties-color-border.md)**-egenskapen for kontrollen til denne formelen:

**If( Value(TextBox1.Text) >= 0, Color.Black, Color.Red )**

Hva betyr det når brukeren velger en **[Knapp](controls/control-button.md)**-kontroll i denne sammenhengen?  Ingen verdi er endret, så det er ikke noe nytt å beregne. Excel har ingenting som tilsvarer en **[Knapp](controls/control-button.md)**-kontroll.  

Ved å velge en **[Knapp](controls/control-button.md)**-kontroll starter brukeren en sekvens med handlinger eller virkemåter, som vil endre tilstanden til appen:

* Endre skjermbildet som vises: Funksjonene **[Back](functions/function-navigate.md)** og **[Navigate](functions/function-navigate.md)**.
* Kontroller et [signal](functions/signals.md): **[Aktiver](functions/function-enable-disable.md)** og **[Deaktiver](functions/function-enable-disable.md)** funksjoner.
* Oppdater, oppdater eller fjern elementer i en [datakilde](working-with-data-sources.md): Funksjonene **[Refresh](functions/function-refresh.md)**, **[Update](functions/function-update-updateif.md)**, **[UpdateIf](functions/function-update-updateif.md)**, **[Path](functions/function-patch.md)**, **[Remove](functions/function-remove-removeif.md)**, **[RemoveIf](functions/function-remove-removeif.md)**.
* Oppdater en [kontekstvariabel](working-with-variables.md#create-a-context-variable): Funksjonen **[UpdateContext](functions/function-updatecontext.md)**.
* Opprett, oppdater eller fjern elementer i en [samling](working-with-data-sources.md#collections): Funksjonene **[Collect](functions/function-clear-collect-clearcollect.md)**, **[Clear](functions/function-clear-collect-clearcollect.md)**, **[ClearCollect](functions/function-clear-collect-clearcollect.md)**.

Fordi disse funksjonene endrer tilstanden til appen kan de ikke automatisk omberegnes. Du kan bruke dem i formlene for egenskapene **[OnSelect](controls/properties-core.md)**, **[OnVisible](controls/control-screen.md)**, **[OnHidden](controls/control-screen.md)**  og andre **On...**, som kalles virkemåteformler.

### <a name="more-than-one-action"></a>Mer enn én handling
Bruk semikolon til å opprette en liste over handlinger som skal utføres. Du kan for eksempel oppdatere en kontekstvariabel, og deretter gå tilbake til forrige skjermbilde:

* **UpdateContext( { x: 1 } ); Back()**

Handlinger utføres i rekkefølgen de vises i formelen.  Den neste funksjonen starter ikke før den gjeldende funksjonen er fullført. Hvis det oppstår en feil, kan kanskje ikke etterfølgende funksjoner starte.

