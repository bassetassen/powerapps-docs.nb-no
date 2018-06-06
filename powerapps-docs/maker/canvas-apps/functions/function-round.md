---
title: Round-, RoundDown- og RoundUp-funksjonene | Microsoft Docs
description: Referanseinformasjon for funksjonene Round, RoundDown og RoundUp i PowerApps, inkludert syntaks
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
ms.openlocfilehash: cfb0e8351b1e51a07962e08b2894d02203b274c7
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/22/2018
ms.locfileid: "30997012"
---
# <a name="round-rounddown-and-roundup-functions-in-powerapps"></a>Round-, RoundDown- og RoundUp-funksjoner i PowerApps
Avrunder et tall.

## <a name="description"></a>Beskrivelse
**Round-**, **RoundDown-** og **RoundUp-** funksjonene avrunder et tall til det angitte antallet desimaler:

* **Round** runder opp hvis det neste sifferet er 5 eller høyere. I motsatt fall runder funksjonen ned.
* **RoundDown** runder alltid ned til det forrige lavere tallet.
* **RoundUp** runder alltid opp til det neste høyere tallet.

Hvis du sender ett enkelt tall, er returverdien den avrundede versjonen av dette tallet.  Hvis du angir en [enkeltkolonnetabell](../working-with-tables.md) som inneholder tall, vil returverdien være en enkeltkolonnetabell med avrundede tall. Hvis du har en flerkolonnetabell, kan du gjøre den om til en enkeltkolonnetabell, som beskrevet i [arbeide med tabeller](../working-with-tables.md).

## <a name="syntax"></a>Syntaks
**Round**( *Number*, *DecimalPlaces* )<br>**RoundDown**( *Number*, *DecimalPlaces* )<br>**RoundUp**( *Number*, *DecimalPlaces* )

* *Number* – obligatorisk. Tallet som skal avrundes.
* *DecimalPlaces* – obligatorisk.  Antall plasser til høyre for desimaltegnet å runde av til.  Bruk 0 til å runde av til et heltall.  

