---
title: Shuffle-funksjonen| Microsoft Docs
description: Referanseinformasjon for Shuffle-funksjonen i PowerApps, inkludert syntaks og eksempel
documentationcenter: na
author: gregli-msft
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: reference
ms.component: canvas
ms.date: 11/07/2015
ms.author: gregli
ms.openlocfilehash: 6d981c410b22dd9db52cdf077a00e6eaae83be75
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/04/2018
ms.locfileid: "31827371"
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

