---
title: Funksjonen Sort og SortByColumns | Microsoft Docs
description: Referanseinformasjon, inkludert syntaks og eksempler for funksjonene Sort og SortByColumns i PowerApps
documentationcenter: na
author: gregli-msft
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: reference
ms.component: canvas
ms.date: 04/26/2016
ms.author: gregli
ms.openlocfilehash: 6ba2186e7f6618cdaa6eef8073e5f3897628ae8f
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/04/2018
ms.locfileid: "31838221"
---
# <a name="sort-and-sortbycolumns-functions-in-powerapps"></a>Funksjonene Sort og SortByColumns i PowerApps
Sorterer en [tabell](../working-with-tables.md).

## <a name="description"></a>Beskrivelse
**Sort**-funksjonen sorterer en tabell basert på en formel.  

Formelen evalueres for hver [post](../working-with-tables.md#records) i tabellen, og resultatene brukes til å sortere tabellen.  Formelen må resultere i et tall, en streng eller en boolsk verdi. Den kan ikke resultere i en tabell eller en post.

[!INCLUDE [record-scope](../../../includes/record-scope.md)]

Hvis du vil sortere først etter én kolonne og deretter etter en annen, må du bygge inn en **Sort**-formel i en annen. Du kan for eksempel bruke denne formelen til å sortere en **Kontakter**-tabell først etter en **Etternavn**-kolonne og deretter etter en **Fornavn**-kolonne:  **Sort( Sort( Contacts, LastName ), FirstName )**

**SortByColumns**-funksjonen kan også brukes til å sortere en tabell basert på én eller flere kolonner.

Parameterlisten for **SortByColumns** inneholder navnene på kolonnene du vil sortere etter, og sorteringsretningen per kolonne.  Sorteringen utføres i samme rekkefølge som parameterne (sortert etter den første kolonnen, og deretter den andre og så videre).  Kolonnenavn er angitt som strenger, som krever doble anførselstegn hvis de er direkte inkludert i parameterlisten.  For eksempel: **SortByColumns( CustomerTable, "LastName" )**.

Du kan kombinere **SortByColumns** med en **[rullegardin](../controls/control-drop-down.md)**- eller **[listeboks](../controls/control-list-box.md)**-kontroll, slik at brukerne kan velge hvilken kolonne de vil sortere etter.

I tillegg til stigende eller synkende sortering kan **SortByColumns** sortere basert på en enkeltkolonnetabell med verdier.  Du kan for eksempel sortere poster basert på navnet på en ukedag ved å oppgi **[ "Monday", "Tuesday", "Wednesday", "Thursday", "Friday", "Saturday", "Sunday" ]** som sorteringsrekkefølge.  Alle poster som inneholder **Monday** (mandag) kommer først, etterfulgt av **Tuesday** (tirsdag) og så videre.  Poster som ble funnet, som ikke vises i sorteringstabellen, plasseres på slutten av listen.

[Tabeller](../working-with-tables.md) er en verdi i PowerApps, akkurat som en streng eller et tall.  De kan sendes til og returneres fra funksjoner.  **Sort** og **SortByColumn** endrer ikke tabeller, i stedet brukes en tabell som et argument og en ny tabell som er sortert, returneres.  Se [Arbeide med tabeller](../working-with-tables.md) for mer informasjon.

[!INCLUDE [delegation](../../../includes/delegation.md)]

## <a name="syntax"></a>Syntaks
**Sort**( *Table*, *Formula* [, *SortOrder* ] )

* *Table* – obligatorisk. Tabell som skal sorteres.
* *Formula* – obligatorisk. Denne formelen evalueres for hver post i tabellen, og resultatene brukes til å sortere tabellen.  Du kan referere til kolonner i tabellen.
* *SortOrder* – valgfritt. Angi **SortOrder.Descending** for å sortere tabellen i synkende rekkefølge. **SortOrder.Ascending** er standardverdien.

**SortByColumns**( *Table*, *ColumnName1* [, *SortOrder1*, *ColumnName2*, *SortOrder2*, ... ] )

* *Table* – obligatorisk. Tabell som skal sorteres.
* *ColumnName(s)* – obligatorisk. Kolonnenavnene som skal sorteres etter, som strenger.
* *SortOrder(s)* – valgfritt.  **SortOrder.Ascending** eller **SortOrder.Descending**.  **SortOrder.Ascending** er standard.  Hvis flere *ColumnNames* leveres, må alle unntatt den siste kolonnen inneholde en *SortOrder*.
  
    > [!NOTE]
> Du må spesifisere hvert mellomrom med **«\_x0020\_»** for SharePoint- og Excel-datakilder som inneholder kolonnenavn med mellomrom. Du kan for eksempel angi **«ColumnName»** som **«Column_x0020_Name»**.

**SortByColumns**( *Table*, *ColumnName*, *SortOrderTable* )

* *Table* – obligatorisk. Tabell som skal sorteres.
* *ColumnName* – obligatorisk. Kolonnenavnet som skal sorteres etter, som strenger.
* *SortOrderTable* – obligatorisk.  Enkeltkolonnetabell av verdiene som skal sorteres etter.
  
    > [!NOTE]
> Du må spesifisere hvert mellomrom med **«\_x0020\_»** for SharePoint- og Excel-datakilder som inneholder kolonnenavn med mellomrom. Du kan for eksempel angi **«ColumnName»** som **«Column_x0020_Name»**.

## <a name="examples"></a>Eksempler
Vi bruker [datakilden](../working-with-data-sources.md) **IceCream**, som inneholder dataene i denne tabellen, for eksemplene nedenfor:

![](media/function-sort/icecream.png)

| Formel | Beskrivelse | Resultat |
| --- | --- | --- |
| **Sort( IceCream, Flavor )**<br><br>**SortByColumns( IceCream, "Flavor" )** |Sorterer **IceCream** etter **Flavor**-kolonnen. **Flavor**-kolonnen inneholder strenger, så tabellen er sortert alfabetisk. Sorteringsrekkefølgen er stigende som standard. |<style> img { max-width: none; } </style> ![](media/function-sort/icecream-flavor.png) |
| **Sort( IceCream, Quantity )**<br><br>**SortByColumns( IceCream, "Quantity" )** |Sorterer **IceCream** etter **Quantity**-kolonnen.  **Quantity**-kolonnen inneholder tall, så tabellen er sortert numerisk.  Sorteringsrekkefølgen er stigende som standard. |![](media/function-sort/icecream-quantity-asc.png) |
| **Sort( IceCream, Quantity, SortOrder.Descending )**<br><br>**SortByColumns( IceCream, "Quantity", SortOrder.Descending )** |Sorterer **IceCream** etter **Quantity**-kolonnen.  **Quantity**-kolonnen inneholder tall, så sorteringen er numerisk.  Sorteringsrekkefølgen er angitt som synkende. |![](media/function-sort/icecream-quantity-desc.png) |
| **Sort( IceCream, Quantity + OnOrder )** |Sorterer **IceCream** med summen av **Quantity**- og **OnOrder**-kolonnene enkeltvis for hver post. Summen er et tall, så tabellen er sortert numerisk.  Sorteringsrekkefølgen er stigende som standard.  Fordi vi sorterer ved hjelp av en formel og ikke etter rå kolonneverdier, finnes det ingen tilsvarende med bruk av **SortByColumns**. |![](media/function-sort/icecream-total.png) |
| **Sort( Sort( IceCream, OnOrder ), Quantity )**<br><br>**SortByColumns( IceCream, "OnOrder", Ascending, "Quantity", Ascending )** |Sorterer **IceCream** først etter **OnOrder**-kolonnen og deretter etter **Quantity**-kolonnen.  Vær oppmerksom på at "Pistachio" var plassert over "Vanilla" i den første sorteringen, basert på **OnOrder**, og deretter ble de flyttet sammen til sine riktige plasseringer basert på **Quantity**. |![](media/function-sort/icecream-onorder-quantity.png) |
| **SortByColumns( IceCream, "Flavor", [&nbsp;"Pistachio",&nbsp;"Strawberry"&nbsp;] )** |Sorterer **IceCream** etter **Flavor**-kolonnen basert på enkeltkolonnetabellen som inneholder Pistachio og Strawberry.  Poster som har "Pistachio" for **Flavor** vises først i resultatet, etterfulgt av poster som inneholder "Strawberry".  Verdier i **Flavor**-kolonnen som ikke er et treff, for eksempel "Vanilla", vises etter elementene som samsvarte. |![](media/function-sort/icecream-onflavor-sorttable.png) |

### <a name="step-by-step"></a>Trinn for trinn
Hvis du vil kjøre disse eksemplene selv, kan du opprette datakilden **IceCream** som en [samling](../working-with-data-sources.md#collections):

1. Legg til en knapp, og angi **[OnSelect](../controls/properties-core.md)**-egenskapen til denne formelen:<br>**ClearCollect( IceCream, { Flavor: "Chocolate", Quantity: 100, OnOrder: 150 }, { Flavor:  "Vanilla", Quantity: 200, OnOrder: 20 }, { Flavor: "Strawberry", Quantity: 300, OnOrder: 0 }, { Flavor: "Mint Chocolate", Quantity: 60, OnOrder: 100 }, { Flavor: "Pistachio", Quantity: 200, OnOrder: 10 } )**
2. Forhåndsvis appen, velg knappen og trykk deretter på ESC for å gå tilbake til standard arbeidsområde.
3. Velg **Samlinger** på **Fil**-menyen for å vise samlingen som du nettopp opprettet, og trykk deretter på ESC for å gå tilbake til standard arbeidsområde.

#### <a name="sort"></a>Sorter
1. Legg til en ny knapp, og angi **[OnSelect](../controls/properties-core.md)**-egenskapen til denne formelen:<br>
   **ClearCollect( SortByFlavor, Sort( IceCream, Flavor ) )**
   
     Formelen over oppretter en annen samling, kalt **SortByFlavor**, som inneholder de samme dataene som **Ice Cream**. Den nye samlingen inneholder imidlertid dataene sortert alfabetisk etter **Flavor**-kolonnen i stigende rekkefølge.
2. Trykk på F5, velg den nye knappen, og trykk deretter på ESC.
3. Velg **Samlinger** på **Fil**-menyen for å vise begge samlingene, og trykk deretter på ESC for å gå tilbake til standard arbeidsområde.
4. Gjenta de forrige tre trinnene, men endre navnet på samlingen du vil opprette, og erstatt **Sort**-formelen med en annen formel fra en tabell med eksemplene tidligere i denne delen som bruker **Sort**.

#### <a name="sortbycolumns"></a>SortByColumns
1. Legg til en ny knapp, og angi **[OnSelect](../controls/properties-core.md)**-egenskapen til denne formelen:<br>
   **ClearCollect( SortByQuantity, SortByColumns( IceCream, "Quantity", Ascending, "Flavor", Descending ) )**
   
     Formelen over oppretter en tredje samling, kalt **SortByQuantity**, som inneholder de samme dataene som **Ice Cream**. Den nye samlingen inneholder imidlertid dataene sortert numerisk etter **Quanity**-kolonnen i stigende rekkefølge, og deretter etter **Flavor**-kolonnen i synkende rekkefølge.
2. Trykk på F5, velg den nye knappen, og trykk deretter på ESC.
3. Velg **Samlinger** på **Fil**-menyen for å vise de tre samlingene, og trykk deretter på ESC for å gå tilbake til standard arbeidsområde.
4. Gjenta de forrige tre trinnene, men endre navnet på samlingen du vil opprette, og erstatt **SortByColumns**-formelen med en annen formel fra en tabell med eksemplene tidligere i denne delen som bruker **SortByColumns**.

