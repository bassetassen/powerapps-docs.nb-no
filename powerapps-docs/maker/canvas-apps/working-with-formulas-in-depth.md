---
title: Forstå virkemåten for formler | Microsoft Docs
description: Referanseinformasjon for å arbeide med virkemåten for formler
services: ''
suite: powerapps
documentationcenter: na
author: gregli-msft
manager: anneta
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 11/10/2015
ms.author: gregli
ms.openlocfilehash: 7bb0d9f3db9353511e8a5ed85f016049a96f7dae
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/22/2018
ms.locfileid: "30997382"
---
# <a name="understand-behavior-formulas-in-powerapps"></a>Forstå virkemåten for formler i PowerApps

De fleste formler beregner en verdi.  Som i et Excel-regneark, skjer omberegning automatisk når verdiene endres.  Du kan for eksempel vise en verdi i en **[Etikett](controls/control-text-box.md)**-kontroll i rødt hvis verdien er mindre enn null. Hvis ikke, er den svart. Så du kan angi f.eks. angi **[Color](controls/properties-color-border.md)**-egenskapen for kontrollen til denne formelen:
<br>**If( Value(TextBox1.Text) >= 0, Color.Black, Color.Red )**

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

Handlinger utføres i rekkefølgen de vises i formelen.  Den neste funksjonen starter ikke før den gjeldende funksjonen er fullført. Hvis det oppstår en feil, kan etterfølgende funksjoner ikke starte.

