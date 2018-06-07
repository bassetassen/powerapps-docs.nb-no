---
title: Funksjonene AddColumns, DropColumns, RenameColumns og ShowColumns | Microsoft Docs
description: Referanseinformasjon, inkludert syntaks og eksempler, for funksjonene AddColumns, DropColumns, RenameColumns og ShowColumns i PowerApps
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
ms.openlocfilehash: 0b7fe4d8e0b9129be126985bbb49cc5ffecbcd44
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/22/2018
ms.locfileid: "30997087"
---
# <a name="addcolumns-dropcolumns-renamecolumns-and-showcolumns-functions-in-powerapps"></a>Funksjonene AddColumns, DropColumns, RenameColumns og ShowColumns i PowerApps
Former en [tabell](../working-with-tables.md) ved å legge til, slippe, gi nytt navn til og velge dens [kolonner](../working-with-tables.md#columns).

## <a name="overview"></a>Oversikt
Disse funksjonene former en tabell ved å justere kolonnene:

* Reduser en tabell som inneholder flere kolonner ned til en enkeltkolonne for bruk med enkeltkolonne-funksjoner, for eksempel **[lavere](function-lower-upper-proper.md)** eller **[Abs](function-numericals.md)**.  
* Legg til en beregnet kolonne i en tabell (for eksempel en **Total Price**-kolonne som viser resultatet av å multiplisere **Quantity** med **Unit Price**).
* Endre navnet til en kolonne til noe mer meningsfylt. Dette vises til brukere eller brukes i formler.

En tabell er en verdi i PowerApps, akkurat som en streng eller et tall.  Du kan angi en tabell som et argument i en formel, og funksjoner kan returnere en tabell som et resultat. Funksjonene som dette emnet beskriver, endrer ikke en tabell. I stedet tar de en tabell som et argument og returnerer en ny tabell med en transformering som er brukt.  Se [Arbeide med tabeller](../working-with-tables.md) for mer informasjon.  

Du kan ikke endre kolonnene i en [datakilden](../working-with-data-sources.md) ved hjelp av disse funksjonene. Du må endre dataene i kilden. Du kan legge til kolonner i en [samling](../working-with-data-sources.md#collections) med **[Collect](function-clear-collect-clearcollect.md)**-funksjonen.  Se [arbeide med datakilder](../working-with-data-sources.md) for mer informasjon.  

## <a name="description"></a>Beskrivelse
Funksjonen **AddColumns** legger til en kolonne i en tabell, og en formel definerer verdiene i kolonnen. Eksisterende kolonner forblir uendret.

Formelen evalueres for hver post i tabellen.
[!INCLUDE [record-scope](../../../includes/record-scope.md)]

Funksjonen **DropColumns** utelukker kolonner fra en tabell.  Alle andre kolonner forblir uendret. **DropColumns** utelukker kolonner, og **ShowColumns** inkluderer kolonner.

Funksjonen **RenameColumns** gir nytt navn til kolonner i en tabell. Alle andre kolonner beholder de opprinnelige navnene.

Funksjonen **ShowColumns** inkluderer kolonner i en tabell og utelukker alle andre kolonner. Du kan bruke **ShowColumns** til å opprette en enkeltkolonnetabell fra en flerkolonnetabell.  **ShowColumns** inneholder kolonner, og **DropColumns** utelukker kolonner.  

Resultatet er en ny tabell med transformasjonen som brukes for alle disse funksjonene.  Den opprinnelige tabellen er ikke endret.

[!INCLUDE [delegation-no](../../../includes/delegation-no.md)]

## <a name="syntax"></a>Syntaks
**AddColumns**( *Table*, *ColumnName1*, *Formula1* [, *ColumnName2*, *Formula2*, ... ] )

* *Table* – obligatorisk.  Tabell til å arbeide på.
* *ColumnName(s)* – obligatorisk. Navn på kolonnen(e) som skal legges til.  Du må angi en streng (for eksempel **"Name"** inkludert anførselstegn) for dette argumentet.
* *Formula(s)* – obligatorisk.  Formlene som skal evalueres for hver post. Resultatet er lagt til som verdien for den tilsvarende nye kolonnen. Du kan referere til andre kolonner i tabellen i denne formelen.

**DropColumns**( *Table*, *ColumnName1* [, *ColumnName2*, ... ] )

* *Table* – obligatorisk.  Tabell til å arbeide på.
* *ColumnName(s)* – obligatorisk. Navn på kolonnen(e) som skal slippes. Du må angi en streng (for eksempel **"Name"** inkludert anførselstegn) for dette argumentet.

**RenameColumns**( *Table*, *OldColumneName*, *NewColumnName* )

* *Table* – obligatorisk.  Tabell til å arbeide på.
* *OldColumnName* – obligatorisk. Navnet på kolonnen som skal få nytt navn. Dette navnet må være en streng (for eksempel **"Name"** med doble anførselstegn inkludert).
* *NewColumnName* – obligatorisk. Erstatningsnavn. Du må angi en streng (for eksempel **"Name"** inkludert doble anførselstegn) for dette argumentet.

**ShowColumns**( *Table*, *ColumnName1* [, *ColumnName2*, ... ] )

* *Table* – obligatorisk.  Tabell til å arbeide på.
* *ColumnName(s)* – obligatorisk. Navn på kolonnen(e) som skal inkluderes. Du må angi en streng (for eksempel **"Name"** inkludert anførselstegn) for dette argumentet.

## <a name="examples"></a>Eksempler
Eksemplene i denne delen bruker **IceCreamSales**-datakilden, som inneholder dataene i denne tabellen:

![](media/function-table-shaping/icecream.png)

Ingen av disse eksemplene endrer **IceCreamSales**-datakilden. Hver funksjon transformerer verdien for datakilden som en tabell, og returnerer verdien som et resultat.

| Formel | Beskrivelse | Resultat |
| --- | --- | --- |
| **AddColumns( IceCreamSales, "Revenue", UnitPrice * QuantitySold )** |Legger til en **Revenue**-kolonne til resultatet.  For hver post evalueres **UnitPrice * QuantitySold**, og resultatet plasseres i den nye kolonnen. |<style> img { max-width: none } </style> ![](media/function-table-shaping/icecream-add-revenue.png) |
| **DropColumns( IceCreamSales, "UnitPrice" )** |Utelater **UnitPrice**-kolonnen fra resultatet. Bruk denne funksjonen til å utelate kolonner, og bruk **ShowColumns** til å inkludere dem. |![](media/function-table-shaping/icecream-drop-price.png) |
| **ShowColumns( IceCreamSales, "Flavor" )** |Inkluderer bare **Flavor**-kolonnen i resultatet. Bruk denne funksjonen til å inkludere kolonner, og bruk **DropColumns** til å utelate dem. |![](media/function-table-shaping/icecream-select-flavor.png) |
| **RenameColumns( IceCreamSales, "UnitPrice", "Price")** |Gir nytt navn til **UnitPrice**-kolonnen i resultatet. |![](media/function-table-shaping/icecream-rename-price.png) |
| **DropColumns(<br>RenameColumns(<br>AddColumns( IceCreamSales, "Revenue",<br>UnitPrice * QuantitySold ),<br>"UnitPrice", "Price" ),<br>"Quantity" )** |Utfører transformeringene av den følgende tabellen i rekkefølge fra innsiden av formelen: <ol><li>Legger til en **Revenue**-kolonne basert på per post-beregningen av **UnitPrice * Quantity**.<li>Endrer navnet **UnitPrice** til **Price**.<li>Utelater **Quantity**-kolonnen.</ol>  Vær oppmerksom på at rekkefølgen er viktig. For eksempel kan vi ikke beregne med **UnitPrice** når den har fått nytt navn. |![](media/function-table-shaping/icecream-all-transforms.png) |

### <a name="step-by-step"></a>Trinn for trinn
1. Importer eller opprett en samling kalt **Beholdning** som den første underprosedyren i [Vis bilder og tekst i et galleri](../show-images-text-gallery-sort-filter.md) beskriver.
2. Legg til en knapp, og angi **[OnSelect](../controls/properties-core.md)**-egenskapen til denne formelen:
   
    **ClearCollect(Inventory2, RenameColumns(Inventory, "ProductName", "JacketID"))**
3. Trykk på F5, velg knappen som du nettopp opprettet, og trykk deretter på ESC for å gå tilbake til utformingsområdet.
4. Velg **Samlinger** på **Fil**-menyen.
5. Bekreft at du har opprettet en samling kalt **Inventory2**. Den nye samlingen inneholder den samme informasjonen som **Inventory** bortsett fra at kolonnen med navnet **ProductName** i **Inventory** heter **JacketID** i **Beholdning2**.

