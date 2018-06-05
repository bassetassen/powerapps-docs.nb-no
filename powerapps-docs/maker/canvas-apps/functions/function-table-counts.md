---
title: Funksjonene Count, CountA, CountIf og CountRows | Microsoft Docs
description: Referanseinformasjon, inkludert syntaks og et eksempel for funksjonene Count og CountA i PowerApps
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
ms.date: 11/07/2015
ms.author: gregli
ms.openlocfilehash: 7849a666f7c4d2639f09f6197974467bbc7f43cc
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/22/2018
ms.locfileid: "30996072"
---
# <a name="count-counta-countif-and-countrows-functions-in-powerapps"></a>Funksjonene Count, CountA, CountIf og CountRows i PowerApps
Teller alle [poster](../working-with-tables.md#records) i en [tabell](../working-with-tables.md), eller teller alle poster som oppfyller en betingelse.

## <a name="description"></a>Beskrivelse
**Count**-funksjonen teller hvor mange poster som inneholder et tall i en tabell med én kolonne.

**CountA**-funksjonen teller antall poster som ikke er *tomme* i en tabell med én kolonne. Denne funksjonen inkluderer [tom](function-isblank-isempty.md) tekst («») i tellingen.

**CountIf**-funksjonen teller hvor mange poster i en tabell som er **sanne** for en logisk formel.  Formelen kan referere til [kolonner](../working-with-tables.md#columns) i tabellen.

**CountRows**-funksjonen teller nummererte poster i en tabell.

Hver av disse funksjonene returnerer et tall.

[!INCLUDE [delegation-no](../../../includes/delegation-no.md)]

## <a name="syntax"></a>Syntaks
**Count**( *SingleColumnTable* )<br>
**CountA**( *SingleColumnTable* )

* *SingleColumnTable* – nødvendig.  Kolonne med poster som skal telles.  

**CountIf**( *Table*, *LogicalFormula* )

* *Tabell* – obligatorisk.  En tabell med poster som skal telles.
* *LogicalFormula* – obligatorisk.  Formelen som skal evalueres for hver post i tabellen.  Postene som returneres som **sann** for denne formelen, blir talt.  Formelen kan referere til kolonner i tabellen.

**CountRows**( *tabell* )

* *Tabell* – obligatorisk.  En tabell med poster som skal telles.

## <a name="example"></a>Eksempel
1. Importer eller opprett en [samling](../working-with-data-sources.md#collections) kalt **Beholdning**, som den første underprosedyren i [Vis bilder og tekst i et galleri](../show-images-text-gallery-sort-filter.md) beskriver.
2. Legg til en etikett, og angi **[Tekst](../controls/properties-core.md)**-egenskapen til denne formelen:
   
    **CountIf(Inventory, UnitsInStock < 30)**
   
    Etiketten viser **2**, fordi to av produktene (Ganymedes og Callisto) har færre enn 30 enheter på lager.
3. Legg til en annen etikett, og angi **[Tekst](../controls/properties-core.md)**-egenskapen til denne formelen:
   
    **CountA(Inventory.UnitsInStock)**
   
    Etiketten viser **5**, som er antallet ikke-tomme celler i **UnitsInStock**-kolonnen.
4. Legg til en annen etikett, og angi **[Tekst](../controls/properties-core.md)**-egenskapen til denne formelen:
   
    **CountRows(Inventory)**
   
    Etiketten viser **5**, fordi samlingen inneholder fem rader.

