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
ms.openlocfilehash: 8b482972b7e209c8cca98aae44389c133d5d4dcf
ms.sourcegitcommit: dfa0e1a7981814e15e6ca4720e2a5f930e859db1
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 07/13/2018
ms.locfileid: "39020335"
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

