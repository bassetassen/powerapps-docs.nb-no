---
title: Shuffle-funksjonen| Microsoft Docs
description: Referanseinformasjon for Shuffle-funksjonen i PowerApps, inkludert syntaks og eksempel
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 11/07/2015
ms.author: gregli
ms.openlocfilehash: 39307e9c7b3de7bfae151709827c409fcc7087ad
ms.sourcegitcommit: dfa0e1a7981814e15e6ca4720e2a5f930e859db1
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 07/13/2018
ms.locfileid: "39014240"
---
# <a name="shuffle-function-in-powerapps"></a>Shuffle-funksjonen i PowerApps
Omorganiserer tilfeldig [postene](../working-with-tables.md#records) i en [tabell](../working-with-tables.md).

## <a name="description"></a>Beskrivelse
**Shuffle**-funksjonen omorganiserer postene i en tabell.

**Shuffle** returnerer en tabell som har samme [kolonner](../working-with-tables.md#columns) og antall rader som argumentet.

## <a name="syntax"></a>Syntaks
**Shuffle**( *Table* )

* *Tabell* – obligatorisk.  Tabell som skal omorganiseres tilfeldig.

## <a name="example"></a>Eksempel
Hvis du har lagret informasjon om spillkort i en [samling](../working-with-data-sources.md#collections) ved navn **Stokk**, vil denne formelen returnere en kopi av samlingen etter at den har blitt omorganisert tilfeldig.

**Shuffle(Deck)**

