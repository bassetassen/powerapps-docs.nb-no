---
title: Funksjonene First, FirstN, Last og LastN | Microsoft Docs
description: Referanseinformasjon, inkludert syntaks og eksempler for funksjonene First, FirstN, Last og LastN i PowerApps
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 11/07/2015
ms.author: gregli
ms.openlocfilehash: 3d94a3a250041ec7524460640f0bca4351ddcacf
ms.sourcegitcommit: dfa0e1a7981814e15e6ca4720e2a5f930e859db1
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 07/13/2018
ms.locfileid: "39021117"
---
# <a name="first-firstn-last-and-lastn-functions-in-powerapps"></a>Funksjonene First, FirstN, Last og LastN i PowerApps
Returnerer den første eller siste gruppen av [poster](../working-with-tables.md#records) i en tabell.

## <a name="description"></a>Beskrivelse
**First**-funksjonen returnerer den første posten i en [tabell](../working-with-tables.md).

**FirstN**-funksjonen returnerer den første gruppen av poster i en tabeller. Det andre argumentet angir hvor mange poster den skal returnere.

**Last**-funksjonen returnerer den siste posten i en tabell.

**LastN**-funksjonen returnerer den siste gruppen av poster i en tabell. Det andre argumentet angir hvor mange poster den skal returnere.

**First** og **Last** returner én post.  **FirstN** og **LastN** returnerer en tabell, selv om du angir bare én post.

[!INCLUDE [delegation-no](../../../includes/delegation-no.md)]

## <a name="syntax"></a>Syntaks
**First**( *Tabell* )<br>**Last**( *Tabell* )

* *Tabell* – obligatorisk. Tabellen funksjonen skal arbeide med.

**FirstN**( *Table* [, *NumberOfRecords* ] )<br>**LastN**( *Table* [, *NumberOfRecords* ] )

* *Tabell* – obligatorisk. Tabellen funksjonen skal arbeide med.
* *NumberOfRecords* – valgfritt.  Antall poster funksjonen skal returnere. Hvis du ikke angir dette argumentet, returnerer funksjonen én post.

## <a name="examples"></a>Eksempler
Denne formelen returnerer den første posten fra en tabell kalt **Ansatte**:<br>
**First(Employees)**

Denne formelen returnerer de siste 15 postene fra en tabell kalt **Employees**:<br>
**LastN(Employees, 15)**

