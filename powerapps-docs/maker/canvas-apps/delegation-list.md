---
title: Datakilder som kan delegeres | Microsoft Docs
description: Liste over alle støttede, delegerbare datakilder
services: ''
suite: powerapps
documentationcenter: na
author: archnair
manager: anneta
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 08/15/2017
ms.author: archanan
ms.openlocfilehash: e073c0a8c471dc8b863894e2d229b15b66b3ce60
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/22/2018
ms.locfileid: "30996317"
---
# <a name="delegable-data-sources"></a>Datakilder som kan delegeres
Som beskrevet i detalj i artikkelen [Forstå delegering](delegation-overview.md) er delegering der PowerApps vil delegere behandlingen av data til datakilden i stedet for å flytte data til appen for å behandles lokalt.

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
