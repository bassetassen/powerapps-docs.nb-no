---
title: Datakilder som kan delegeres, i lerretsapper | Microsoft Docs
description: Liste over alle støttede datakilder som kan delegeres, i lerretsapper
author: lancedMicrosoft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 08/15/2017
ms.author: lanced
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 98931d4692a61839e0530682bd2d40258c07b7df
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/24/2018
ms.locfileid: "42825767"
---
# <a name="delegable-data-sources-in-canvas-apps"></a>Datakilder som kan delegeres, i lerretsapper
Som beskrevet i detalj i artikkelen [Forstå delegering](delegation-overview.md), handler delegering om at PowerApps delegerer behandlingen av data til datakilden i stedet for å flytte data til lerretsappen for å behandles lokalt.

Delegering støttes for bare tabelldatakilder. Denne listen viser tabelldatakilder og om de støtter delegering, med detaljer i neste del.

* Common Data Service – **Ja**
* SharePoint – **Ja**
* SQL Server – **Ja**
* Dynamics 365 – **Ja**
* Salesforce – **Ja**
* Dynamics 365 for Operations – ikke ennå
* Dynamics 365 for Financials – ikke ennå
* Dynamics NAV – ikke ennå
* Google Sheets – ikke ennå

Det legges til både tabelldatakilder og delegeringsstøtte for disse kontinuerlig.

Dette dokumentet viser gjeldende status for støttet delegering for hver enkelt datakilde.

## <a name="prerequisites"></a>Forutsetninger

* Gjør deg kjent med artikkelen [Forstå delegering](delegation-overview.md)

## <a name="list-of-data-sources-and-supported-delegation"></a>Liste over datakilder og støttet delegering
Denne listen over datakilder og funksjoner og predikater som kan delegeres, oppdateres regelmessig for å gjenspeile gjeldende status for støtte for delegering i PowerApps.

### <a name="top-level-delegable-functions"></a>Funksjoner på øverste nivå som kan delegeres

| &nbsp; | Common Data Service | SharePoint | SQL Server | Dynamics 365 | Salesforce |
| --- | --- | --- | --- | --- | --- |
| Gjennomsnitt |Nei |Nei |Ja |Nei |Nei |
| Filter |Ja |Ja |Ja |Ja |Ja |
| LookUp |Ja |Ja |Ja |Ja |Ja |
| maks |Nei |Nei |Ja |Nei |Nei |
| Min. |Nei |Nei |Ja |Nei |Nei |
| Søk |Ja<sup>1</sup> |Nei |Ja |Ja |Ja |
| Sorter |Ja |Ja |Ja |Ja |Ja |
| SortByColumns |Ja |Ja |Ja |Ja |Ja |
| Sum |Nei |Nei |Ja |Nei |Nei |

<sup>1</sup>Bare for strengfelt

### <a name="filter-and-lookup-delegable-predicates"></a>Filtrer og slå opp for predikater som kan delegeres

| &nbsp; | Common Data Service | SharePoint | SQL Server | Dynamics 365 | Salesforce |
| --- | --- | --- | --- | --- | --- |
| Ikke |Ja |Nei |Ja |Ja |Ja |
| IsBlank |Nei |Nei |Ja |Ja |Nei |
| TrimEnds |Nei |Nei |Ja |Nei |Nei |
| Len |Nei |Nei |Ja |Nei |Nei |
| +, - |Nei |Nei |Ja |Nei |Nei |
| <, <=, =, <>, >, >= |Ja |Ja (bare =) |Ja |Ja |Ja |
| And (&&), Or (&#124;&#124;), Not (!) |Ja<sup>2</sup> |Yes (except Not(!)) |Ja |Ja |Ja |
| i |Nei |Nei |Ja |Nei |Ja |
| StartsWith |Nei |Ja |Nei |Nei |Nei |

<sup>2</sup>Bare for operatorer. Funksjonene And, Or og Not er ikke delegert.
