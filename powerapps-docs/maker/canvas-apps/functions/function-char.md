---
title: Char-funksjonen | Microsoft Docs
description: Referanseinformasjon for Char-funksjonen i PowerApps, inkludert syntaks og eksempler
services: ''
suite: powerapps
documentationcenter: na
author: gregli-msft
manager: anneta
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 11/07/2015
ms.author: gregli
ms.openlocfilehash: 7ce510840845b1a1df2d590c4f3ffdddfc5bfb9c
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/22/2018
ms.locfileid: "30997007"
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

