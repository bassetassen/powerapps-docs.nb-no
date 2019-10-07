---
title: Find-funksjonen | Microsoft Docs
description: Referanseinformasjon, herunder syntaks og eksempler for Find-funksjonen i PowerApps
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 11/07/2015
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: fbdd29ed1757301f076ab6bebea548fcd7a963cc
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/07/2019
ms.locfileid: "71984945"
---
# <a name="find-function-in-powerapps"></a>Find-funksjonen i PowerApps
Finner en tekststreng inni en annen tekststreng, hvis den finnes.

## <a name="description"></a>Beskrivelse
**Find**-funksjonen søker etter en tekststreng inni en annen tekststreng og skiller mellom store og små bokstaver. Hvis du ikke vil skille mellom store og små bokstaver, må du først bruke **[Lower](function-lower-upper-proper.md)** -funksjonen på argumentene.

**Find** returnerer startposisjonen til tekststrengen som ble funnet.  Posisjon 1 er det første tegnet i tekststrengen. **Find** returnerer *tom* hvis tekststrengen du søker i ikke inneholder tekststrengen du søker etter.

## <a name="syntax"></a>Syntaks
**Find**( *FindString*, *WithinString* [, *StartingPosition* ] )

* *FindString* – obligatorisk.  Tekststrengen du vil finne.
* *WithinString* – obligatorisk.  Tekststrengen som inneholder tekststrengen du vil finne.
* *StartingPosition* – valgfritt.  Startposisjonen du vil starte søket fra.  Posisjon 1 er det første tegnet i tekststrengen.

