---
title: Round-, RoundDown- og RoundUp-funksjonene | Microsoft Docs
description: Referanseinformasjon for funksjonene Round, RoundDown og RoundUp i PowerApps, inkludert syntaks
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
ms.openlocfilehash: 8d96b9362047113bda332ab7e7e36c8d5cea0666
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/23/2019
ms.locfileid: "61520517"
ms.PowerAppsDecimalTransform: true
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
**Round**( *Number*; *DecimalPlaces* )<br>**RoundDown**( *Number*; *DecimalPlaces* )<br>**RoundUp**( *Number*; *DecimalPlaces* )

* *Number* – obligatorisk. Tallet som skal avrundes.
* *DecimalPlaces* – obligatorisk.  Antall plasser til høyre for desimaltegnet å runde av til.  Bruk 0 til å runde av til et heltall.  

