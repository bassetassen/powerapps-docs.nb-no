---
title: Å forstå formler for virkemåte | Microsoft Docs
description: Referanseinformasjon for å arbeide med formler for virkemåte
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
ms.sourcegitcommit: 6afca7cb4234d3a60111c5950e7855106ff97e56
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 01/23/2018
ms.locfileid: "30986492"
---
# <a name="understand-behavior-formulas-in-powerapps"></a>Å forstå formler for virkemåte i PowerApps

De fleste formler beregner en verdi.  Omberegning skjer automatisk når verdiene endres, akkurat som i et Excel-regneark.  Du kan for eksempel vise en verdi i en **[Etikett](controls/control-text-box.md)**-kontroll i rødt, hvis verdien er mindre enn null, men ellers er den svart. Du kan dermed angi **[Farge](controls/properties-color-border.md)**-egenskapen for kontrollen til denne formelen:
<br>**If( Value(TextBox1.Text) >= 0, Color.Black, Color.Red )**

Hva betyr det når brukeren velger en **[Knapp](controls/control-button.md)**-kontroll i denne sammenhengen?  Ingen verdi er endret, slik at det ikke er noe nytt å beregne. Excel har ingenting som tilsvarer en **[Knapp](controls/control-button.md)**-kontroll.  

Ved å velge en **[Knapp](controls/control-button.md)**-kontroll starter brukeren en sekvens med handlinger eller virkemåter, som vil endre tilstanden til appen:

* Endre skjermbildet som vises: **[Tilbake](functions/function-navigate.md)**- og **[Naviger](functions/function-navigate.md)**-funksjonene.
* Kontroller et [signal](functions/signals.md): **[Aktivere](functions/function-enable-disable.md)**- og **[Deaktivere](functions/function-enable-disable.md)**-funksjoner.
* Oppdater, oppdatere eller fjerne elementer i en [datakilden](working-with-data-sources.md): Funksjonene **[Refresh](functions/function-refresh.md)**, **[Update](functions/function-update-updateif.md)**, **[UpdateIf](functions/function-update-updateif.md)**, **[Patch](functions/function-patch.md)**, **[Remove](functions/function-remove-removeif.md)**, **[RemoveIf](functions/function-remove-removeif.md)**.
* Oppdater en [kontekstvariabel](working-with-variables.md#create-a-context-variable):  **[UpdateContext](functions/function-updatecontext.md)**-funksjon.
* Opprette, oppdatere eller fjerne elementer i en [samling](working-with-data-sources.md#collections): Funksjonene **[Collect](functions/function-clear-collect-clearcollect.md)**, **[Clear](functions/function-clear-collect-clearcollect.md)**, **[ClearCollect](functions/function-clear-collect-clearcollect.md)**.

Fordi disse funksjonene endrer tilstanden til appen kan de ikke automatisk omberegnes. Du kan bruke dem i formlene for **[OnSelect](controls/properties-core.md)**, **[OnVisible](controls/control-screen.md)**, **[OnHidden](controls/control-screen.md)**, og andre **On...** -egenskaper, som kalles formler for virkemåte.

### <a name="more-than-one-action"></a>Mer enn én handling
Bruk semikolon til å opprette en liste over handlinger som skal utføres. Du kan for eksempel oppdatere en kontekstvariabel, og deretter gå tilbake til forrige skjermbilde:

* **UpdateContext( { x: 1 } ); Back()**

Handlinger er utført i rekkefølgen som de vises i formelen.  Den neste funksjonen starter ikke før den gjeldende funksjonen er fullført. Hvis det oppstår en feil, kan kanskje ikke etterfølgende funksjoner starte.

