---
title: Char-funksjonen | Microsoft Docs
description: Referanseinformasjon for Char-funksjonen i PowerApps, inkludert syntaks og eksempler
dauthor: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 11/07/2015
ms.author: gregli
ms.openlocfilehash: 9c701527fb02613332cfa5bc542681f8c119f3b3
ms.sourcegitcommit: dfa0e1a7981814e15e6ca4720e2a5f930e859db1
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 07/13/2018
ms.locfileid: "39014562"
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

