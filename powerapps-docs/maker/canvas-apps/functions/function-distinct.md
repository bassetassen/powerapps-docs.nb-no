---
title: Distinct-funksjonen | Microsoft Docs
description: Referanseinformasjon, inkludert syntaks og eksempler for Distinct-funksjonen i PowerApps
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 11/07/2015
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 17a2f2cfca16c5589f74ac434b36326037146b16
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/24/2018
ms.locfileid: "42843202"
---
# <a name="distinct-function-in-powerapps"></a>Distinct-funksjonen i PowerApps
Oppsummerer [postene](../working-with-tables.md#records) i en [tabell](../working-with-tables.md) uten duplikater.

## <a name="description"></a>Beskrivelse
**Distinct**-funksjonen evaluerer en formel på tvers av hver post i en tabell. **Distinct** returnerer en tabell med én kolonne som inneholder resultatene, der dupliserte verdier er fjernet.  

[!INCLUDE [record-scope](../../../includes/record-scope.md)]

## <a name="syntax"></a>Syntaks
**Distinct**( *Table*, *Formula* )

* *Table* – obligatorisk.  Tabellen funksjonen skal evaluere på tvers av.
* *Formula* – obligatorisk.  Formelen som skal evalueres for hver post.

## <a name="example"></a>Eksempel
Hvis du hadde en **Ansatte**-tabell som inneholdt en **Avdeling**-kolonne, ville denne funksjonen gi en liste over hvert unike avdelingsnavn i denne kolonnen, uansett hvor mange ganger hvert navn ble vist i kolonnen:

**Distinct(Employees, Department)**

