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
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 3fd93ce6cf9703e9e9fbf69c5826213d9aa78e02
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/24/2018
ms.locfileid: "42863572"
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

