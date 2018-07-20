---
title: Find-funksjonen | Microsoft Docs
description: Referanseinformasjon, herunder syntaks og eksempler for Find-funksjonen i PowerApps
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 11/07/2015
ms.author: gregli
ms.openlocfilehash: cd2028434fb9199595360ddafdb2e41d32e6cf3a
ms.sourcegitcommit: dfa0e1a7981814e15e6ca4720e2a5f930e859db1
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 07/13/2018
ms.locfileid: "39019530"
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

