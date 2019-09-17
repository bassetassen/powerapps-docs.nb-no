---
title: Distinct-funksjonen | Microsoft Docs
description: Referanseinformasjon, inkludert syntaks og eksempler for Distinct-funksjonen i PowerApps
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 09/14/2019
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 98fd1b67d4835969ac01b1ce63155bc81ed36630
ms.sourcegitcommit: 5899d37e38ed7111d5a9d9f3561449782702a5e9
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 09/17/2019
ms.locfileid: "71038095"
---
# <a name="distinct-function-in-powerapps"></a>Distinct-funksjonen i PowerApps
Oppsummerer [postene](../working-with-tables.md#records) i en [tabell](../working-with-tables.md) uten duplikater.

## <a name="description"></a>Beskrivelse
**DISTINCT** -funksjonen evaluerer en formel på tvers av hver post i en tabell, og returnerer en tabell med én kolonne med like verdier fjernet.  Navnet på kolonnen er **resultat**.  

[!INCLUDE [record-scope](../../../includes/record-scope.md)]

[!INCLUDE [delegation-no-one](../../../includes/delegation-no-one.md)]

## <a name="syntax"></a>Syntaks
**Distinct**( *Table*, *Formula* )

* *Table* – obligatorisk.  Tabellen funksjonen skal evaluere på tvers av.
* *Formula* – obligatorisk.  Formelen som skal evalueres for hver post.

## <a name="example"></a>Eksempel

1. Sett inn en [**knapp**](../controls/control-button.md) -kontroll, og angi **OnSelect** -egenskapen til denne formelen.

    ```powerapps-dot
    ClearCollect( CityPopulations,
        { City: "London",    Country: "United Kingdom", Population: 8615000 },
        { City: "Berlin",    Country: "Germany",        Population: 3562000 },
        { City: "Madrid",    Country: "Spain",          Population: 3165000 },
        { City: "Hamburg",   Country: "Germany",        Population: 1760000 },
        { City: "Barcelona", Country: "Spain",          Population: 1602000 },
        { City: "Munich",    Country: "Germany",        Population: 1494000 }
    );
    ```

1. Velg knappen mens du holder nede Alt-tasten.

    Formelen er evaluatd og **CityPopulations** -samlingen opprettes, som du kan vise ved å velge **CityPopulations** i formel linjen:

    > [!div class="mx-imgBorder"]
    > ![CityPopulations-samling vist i resultat visning](media/function-distinct/citypopulations-create.png)

1. Sett inn en [**data tabell**](../controls/control-data-table.md) -kontroll, og angi **elementer** -egenskapen til denne formelen:

    ```powerapps-dot
    Distinct( CityPopulations, Country )
    ```

    Du kan vise resultatet av denne formelen på formel linjen ved å velge hele formelen:

    > [!div class="mx-imgBorder"]
    > ![Utdata fra DISTINCT-funksjonen som vises i resultat visning](media/function-distinct/citypopulations-distinct.png)

1. Bruk **Rediger felt** -koblingen i egenskaps ruten for data tabellen for å legge til **resultat** Kol onnen:

    > [!div class="mx-imgBorder"]
    > ![Utdata fra DISTINCT-funksjonen som vises i data tabell](media/function-distinct/citypopulations-datatable.png)

1. Sett inn en [**etikett**](../controls/control-text-box.md) -kontroll, og angi **tekst** -egenskapen til formelen:

    ```powerapps-dot
    First( Sort( Distinct( CityPopulations, Country ), Result ) ).Result
    ```

    Denne formelen sorterer resultatene fra **DISTINCT** med [**sort**](function-sort.md) -funksjonen, tar den første posten fra resultat tabellen med den [**første**](function-first-last.md) funksjonen, og trekker ut **resultat** feltet for å bare motta lands navnet.

    > [!div class="mx-imgBorder"]
    > ![Utdata fra DISTINCT-funksjonen som viser det første landet etter navn](media/function-distinct/citypopulations-first.png)

     
