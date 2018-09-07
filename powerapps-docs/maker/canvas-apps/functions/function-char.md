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
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: aec27b788fff8434cfdc4e0e130487f718a42aa6
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/24/2018
ms.locfileid: "42826369"
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

