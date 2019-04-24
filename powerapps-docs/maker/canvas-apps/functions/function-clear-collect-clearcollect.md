---
title: Funksjonene Collect, Clear og ClearCollect | Microsoft Docs
description: Referanseinformasjon for funksjonene Collect, Clear og ClearCollect i PowerApps, inkludert syntaks og eksempler
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 11/01/2015
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 86d36af00d3c5aa825b01ed873150f94738a952c
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/23/2019
ms.locfileid: "61546575"
---
# <a name="collect-clear-and-clearcollect-functions-in-powerapps"></a>Funksjonene Collect, Clear og ClearCollect i PowerApps

Oppretter og tømmer [samlinger](../working-with-data-sources.md#collections) og legger til [poster](../working-with-tables.md#records) i valgt [datakilde](../working-with-data-sources.md).

## <a name="description"></a>Beskrivelse

### <a name="collect"></a>Collect

**Collect**-funksjonen legger til poster i en datakilde. Elementene som skal legges til, kan være:

- En enkelt verdi: Verdien som er plassert i den **[verdien](function-value.md)** feltet i en ny post.  Alle de andre egenskapene forblir [tomme](function-isblank-isempty.md).
- En post: Hver navngitt egenskap legges inn i den tilsvarende egenskapen til en ny post.  Alle de andre egenskapene forblir blanke.
- A [tabellen](../working-with-tables.md): Hver post i tabellen er lagt til som en separat post i datakilden som beskrevet ovenfor. Tabellen legges ikke inn som en nestet tabell i en post. Hvis du vil gjøre dette, må du sette inn tabellen i en post først.

Når funksjonen brukes med en samling, legges ekstra [kolonner](../working-with-tables.md#columns) til etter behov. Kolonnene for andre datakilder er fast for datakilden, og nye kolonner kan ikke legges til.  

Hvis datakilden ikke allerede finnes, oppretter funksjonen en samling.

Samlinger brukes noen ganger til å holde globale variabler eller til å lage en midlertidig kopi av en datakilde. PowerApps er basert på formler som automatisk beregnes på nytt når brukeren samhandler med en app. Samlinger har ikke denne fordelen, og hvis du bruker samlinger, kan det gjøre appen vanskeligere å opprette og forstå. Les om å [jobbe med variabler](../working-with-variables.md) før du bruker samlinger på denne måten.

Du kan også bruke **[Patch](function-patch.md)**-funksjonen til å opprette poster i en datakilde.

**Collect** returnerer den endrede datakilden som en tabell.  **Collect** kan bare brukes i en [formel for virkemåte](../working-with-formulas-in-depth.md).

### <a name="clear"></a>Clear

**Clear**-funksjonen sletter alle postene i en samling.  Kolonnene i samlingen blir værende.

Legg merke til at **Clear** bare fungerer på samlinger og ikke på andre datakilder.  Du kan bruke **[RemoveIf](function-remove-removeif.md)( *DataSource*, true)** til dette.  Vær forsiktig, ettersom dette vil fjerne alle postene som er lagret for datakilden, og kan påvirke andre brukere.

Du kan bruke **[Remove](function-remove-removeif.md)**-funksjonen til å fjerne poster selektivt.

**Clear** har ingen returverdi.  Funksjonen kan bare brukes i en formel for virkemåte.

### <a name="clearcollect"></a>ClearCollect

**ClearCollect**-funksjonen sletter alle poster fra en samling og legger deretter til et annet sett med poster i samme samling.  **ClearCollect** fungerer som en kombinasjon av **Clear** og deretter **Collect** i én enkelt funksjon.

**ClearCollect** returnerer den endrede samlingen som en tabell.  **ClearCollect** kan bare brukes i en formel for virkemåte.

## <a name="syntax"></a>Syntaks

**Collect**( *DataSource*, *Item*, ...)

* *DataSource* – obligatorisk. Datakilden som du vil legge til data i.  Hvis den ikke allerede finnes, opprettes en ny samling.
* *Item* – obligatorisk.  Én eller flere poster eller tabeller som skal legges til i datakilden.  

**Clear**( *Collection* )

* *Collection* – obligatorisk. Samlingen som du vil tømme.

**ClearCollect**( *Collection*, *Item*, ...)

* *Collection* – obligatorisk. Samlingen som du vil tømme og legge til data i.
* *Item* – obligatorisk.  Én eller flere poster eller tabeller som skal legges til i datakilden.  

## <a name="examples"></a>Eksempler

### <a name="clearing-and-adding-records-to-a-data-source"></a>Fjerne og legge til poster i en datakilde

I disse eksemplene tømmer du en samling som heter **IceCream**, og legger til data. Datakilden begynner med dette innholdet:

![Eksempel på datakilde](media/function-clear-collect-clearcollect/icecream.png)

| Formel | Beskrivelse | Resultat |
| --- | --- | --- |
| **ClearCollect( IceCream, {&nbsp;Flavor:&nbsp;"Strawberry",&nbsp;Quantity:&nbsp;300&nbsp;} )** |Fjerner alle dataene fra samlingen **IceCream** og legger til en post som inneholder et antall jordbæris. |<style> IMG {max bredde: none} </style> ![tabell med én post](media/function-clear-collect-clearcollect/icecream-clearcollect.png)<br><br>Datakilden **IceCream** har også blitt endret. |
| **Collect( IceCream, {&nbsp;Flavor:&nbsp;"Pistachio",&nbsp;Quantity:&nbsp;40&nbsp;}, {&nbsp;Flavor:&nbsp;"Orange",&nbsp;Quantity:&nbsp;200&nbsp;}  )** |Legger til to poster i **IceCream**-samlingen med et antall iskrem med pistasj- og appelsinsmak. |![Tabell med to poster](media/function-clear-collect-clearcollect/icecream-collect.png)<br><br>Datakilden **IceCream** har også blitt endret. |
| **Clear( IceCream )** |Fjerner alle postene fra **IceCream**-samlingen. |![Tom tabell](media/function-clear-collect-clearcollect/icecream-clear.png)<br><br>Datakilden **IceCream** har også blitt endret. |

Trinnvise eksempler på hvordan du oppretter en samling, kan du se [opprette og oppdatere en samling](../create-update-collection.md).
