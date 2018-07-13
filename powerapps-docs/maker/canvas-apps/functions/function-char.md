---
title: Char-funksjonen | Microsoft Docs
description: Referanseinformasjon for Char-funksjonen i PowerApps, inkludert syntaks og eksempler
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
ms.openlocfilehash: b5d63b26498b94943f5340d9f57f3255390c7c94
ms.sourcegitcommit: 79b8842fb0f766a0476dae9a537a342c8d81d3b3
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 07/07/2018
ms.locfileid: "37895987"
---
# <a name="char-function-in-powerapps"></a>Char-funksjonen i PowerApps
Oversetter en tegnkode til en streng.

## <a name="description"></a>Beskrivelse
**Char**-funksjonen returnerer en streng, som inneholder riktig ASCII-tegn for din plattform.

## <a name="syntax"></a>Syntaks
**Char**( *CharacterCode* )

* *CharacterCode* – nødvendig. ASCII-karakterkode å oversette.

## <a name="examples"></a>Eksempler

| Formel | Beskrivelse | Resultat |
| --- | --- | --- |
| **Char (65)** |Returnerer tegnet som samsvarer med ASCII-koden 65. |A |
| **Char( 105 )** |Returnerer tegnet som samsvarer med ASCII-koden 105. |i |
| **Char( 35 )** |Returnerer tegnet som samsvarer med ASCII-koden 35. |# |

