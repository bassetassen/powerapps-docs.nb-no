---
title: Funksjonene Count, CountA, CountIf og CountRows | Microsoft Docs
description: Referanse informasjon, inkludert syntaks og et eksempel på funksjonene Count, ANTALLA, antall og CountRows i PowerApps
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 11/07/2015
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 70950a52050226a25270be7531f4589671f0d46f
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/07/2019
ms.locfileid: "71983889"
ms.PowerAppsDecimalTransform: true
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

**CountIf**( *Table*; *LogicalFormula* )

* *Tabell* – obligatorisk.  En tabell med poster som skal telles.
* *LogicalFormula* – obligatorisk.  Formelen som skal evalueres for hver post i tabellen.  Postene som returneres som **sann** for denne formelen, blir talt.  Formelen kan referere til kolonner i tabellen.

**CountRows**( *tabell* )

* *Tabell* – obligatorisk.  En tabell med poster som skal telles.

## <a name="example"></a>Eksempel
1. Importer eller opprett en [samling](../working-with-data-sources.md#collections) kalt **Beholdning**, som den første underprosedyren i [Vis bilder og tekst i et galleri](../show-images-text-gallery-sort-filter.md) beskriver.
2. Legg til en etikett, og angi **[Tekst](../controls/properties-core.md)** -egenskapen til denne formelen:
   
    **CountIf(Inventory; UnitsInStock < 30)**
   
    Etiketten viser **2**, fordi to av produktene (Ganymedes og Callisto) har færre enn 30 enheter på lager.
3. Legg til en annen etikett, og angi **[Tekst](../controls/properties-core.md)** -egenskapen til denne formelen:
   
    **CountA(Inventory.UnitsInStock)**
   
    Etiketten viser **5**, som er antallet ikke-tomme celler i **UnitsInStock**-kolonnen.
4. Legg til en annen etikett, og angi **[Tekst](../controls/properties-core.md)** -egenskapen til denne formelen:
   
    **CountRows(Inventory)**
   
    Etiketten viser **5**, fordi samlingen inneholder fem rader.

