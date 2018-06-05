---
title: Distinct-funksjonen | Microsoft Docs
description: Referanseinformasjon, inkludert syntaks og eksempler for Distinct-funksjonen i PowerApps
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
ms.openlocfilehash: 820ae85b99e0a8bab8ff2cf8308540336dee60af
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/22/2018
ms.locfileid: "30996042"
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

