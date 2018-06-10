---
title: Find-funksjonen | Microsoft Docs
description: Referanseinformasjon, herunder syntaks og eksempler for Find-funksjonen i PowerApps
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
ms.openlocfilehash: 8e95f03c934e0989269ff9ec21b432f609cb13ad
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/04/2018
ms.locfileid: "31826089"
---
# <a name="find-function-in-powerapps"></a>Find-funksjonen i PowerApps
Finner en tekststreng inni en annen tekststreng, hvis den finnes.

## <a name="description"></a>Beskrivelse
**Find**-funksjonen søker etter en tekststreng inni en annen tekststreng og skiller mellom store og små bokstaver. Hvis du ikke vil skille mellom store og små bokstaver, må du først bruke **[Lower](function-lower-upper-proper.md)**-funksjonen på argumentene.

**Find** returnerer startposisjonen til tekststrengen som ble funnet.  Posisjon 1 er det første tegnet i tekststrengen. **Find** returnerer *tom* hvis tekststrengen du søker i ikke inneholder tekststrengen du søker etter.

## <a name="syntax"></a>Syntaks
**Find**( *FindString*, *WithinString* [, *StartingPosition* ] )

* *FindString* – obligatorisk.  Tekststrengen du vil finne.
* *WithinString* – obligatorisk.  Tekststrengen som inneholder tekststrengen du vil finne.
* *StartingPosition* – valgfritt.  Startposisjonen du vil starte søket fra.  Posisjon 1 er det første tegnet i tekststrengen.

