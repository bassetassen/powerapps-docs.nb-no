---
title: Slik fungerer formler for virkemåte i en lerretsapp | Microsoft Docs
description: Referanseinformasjon om hvordan du arbeider med former for virkemåte, som endrer tilstanden til en lerretsapp i PowerApps
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 11/10/2015
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 546c19dd0bc767758fcf854e383be0f075717525
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/07/2019
ms.locfileid: "71988019"
ms.PowerAppsDecimalTransform: true
---
# <a name="understand-behavior-formulas-for-canvas-apps-in-powerapps"></a>Slik fungerer formler for virkemåte i lerretsapper i PowerApps

De fleste formler beregner en verdi.  Omberegning skjer automatisk når verdiene endres, akkurat som i et Excel-regneark.  Du kan for eksempel vise en verdi i en **[Etikett](controls/control-text-box.md)** -kontroll i rødt hvis verdien er mindre enn null. Hvis ikke, er den svart. Så du kan angi f.eks. angi **[Color](controls/properties-color-border.md)** -egenskapen for kontrollen til denne formelen:

**If( Value(TextBox1.Text) >= 0; Color.Black; Color.Red )**

Hva betyr det når brukeren velger en **[Knapp](controls/control-button.md)** -kontroll i denne sammenhengen?  Ingen verdi er endret, så det er ikke noe nytt å beregne. Excel har ingenting som tilsvarer en **[Knapp](controls/control-button.md)** -kontroll.  

Ved å velge en **[Knapp](controls/control-button.md)** -kontroll starter brukeren en sekvens med handlinger eller virkemåter, som vil endre tilstanden til appen:

* Endre skjermen som vises: Funksjonene **[bak](functions/function-navigate.md)** og **[navigere](functions/function-navigate.md)** .
* Kontroller et [signal](functions/signals.md): **[Aktivere](functions/function-enable-disable.md)** og **[deaktivere](functions/function-enable-disable.md)** funksjoner.
* Oppdater, Oppdater eller fjern elementer i en [data kilde](working-with-data-sources.md): **[Oppdatering](functions/function-refresh.md)** , **[oppdatering](functions/function-update-updateif.md)** , **[UpdateIf](functions/function-update-updateif.md)** , **[patch](functions/function-patch.md)** , **[Remove](functions/function-remove-removeif.md)** , **[RemoveIf](functions/function-remove-removeif.md)** functions.
* Oppdater en [kontekst variabel](working-with-variables.md#use-a-context-variable):  **[UpdateContext](functions/function-updatecontext.md)** -funksjonen.
* Opprett, Oppdater eller fjern elementer i en [samling](working-with-data-sources.md#collections):  Funksjonene **[samle](functions/function-clear-collect-clearcollect.md)** , **[Clear](functions/function-clear-collect-clearcollect.md)** , **[ClearCollect](functions/function-clear-collect-clearcollect.md)** .

Fordi disse funksjonene endrer tilstanden til appen kan de ikke automatisk omberegnes. Du kan bruke dem i formlene for egenskapene **[OnSelect](controls/properties-core.md)** , **[OnVisible](controls/control-screen.md)** , **[OnHidden](controls/control-screen.md)**  og andre **On...** , som kalles virkemåteformler.

### <a name="more-than-one-action"></a>Mer enn én handling
Bruk semikolon til å opprette en liste over handlinger som skal utføres. Du kan for eksempel oppdatere en kontekstvariabel, og deretter gå tilbake til forrige skjermbilde:

* **UpdateContext ({x: 1});; Tilbake ()**

Handlinger utføres i rekkefølgen de vises i formelen.  Den neste funksjonen starter ikke før den gjeldende funksjonen er fullført. Hvis det oppstår en feil, kan kanskje ikke etterfølgende funksjoner starte.

