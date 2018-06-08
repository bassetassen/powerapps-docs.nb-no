---
title: Funksjonene Now, Today og IsToday | Microsoft Docs
description: Referanseinformasjon for Now-, Today- og IsToday-funksjonene i PowerApps, inkludert syntaks og eksempler
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
ms.openlocfilehash: 410e9be47b4356a97292eb5de17c5dc10885fae3
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/04/2018
ms.locfileid: "31829144"
---
# <a name="now-today-and-istoday-functions-in-powerapps"></a>Funksjonene for Now, Today, og IsToday i PowerApps
Returnerer gjeldende dato og klokkeslett, og tester om en dato/klokkeslett-verdi er i dag.

## <a name="description"></a>Beskrivelse
**Now**-funksjonen returnerer gjeldende dato og klokkeslett som en dato/klokkeslett-verdi.

**Today**-funksjonen returnerer gjeldende dato og klokkeslett som en dato/klokkeslett-verdi. Klokkeslettdelen er midnatt. **Today** har samme verdi hele døgnet, fra midnatt i dag til midnatt i morgen.

**IsToday**-funksjonen tester om en dato/klokkeslett-verdi er mellom midnatt i dag og midnatt i morgen. Denne funksjonen returnerer en boolsk **SANN**- eller **USANN**-verdi.

Alle disse funksjonene fungerer med lokal tid for gjeldende bruker.

Hvis du vil ha mer informasjon, kan du se [slik arbeider du med datoer og klokkeslett](../show-text-dates-times.md).

## <a name="syntax"></a>Syntaks
**Now**()

**Today**()

**IsToday**( *DateTime* )

* *DateTime* – nødvendig.  Dato/klokkeslett-verdien som skal testes.

## <a name="examples"></a>Eksempler
Gjeldende klokkeslett for eksemplene i denne delen er **3:59 AM** den **12. feb. 2015**, og språket er **EN-US**.

| Formel | Beskrivelse | Resultat |
| --- | --- | --- |
| **Text( Now(), "mm/dd/yyyy hh:mm:ss" )** |Henter gjeldende dato og klokkeslett, og viser dem som en streng. |«02/12/2015 03:59:00» |
| **Text( Today(), "mm/dd/yyyy hh:mm:ss" )** |Henter bare gjeldende dato, lar klokkeslettdelen stå som midnatt, og viser dette som en streng. |«02/12/2015 00:00:00» |
| **IsToday( Now() )** |Tester om gjeldende dato og klokkeslett er mellom midnatt i dag og midnatt i morgen. |**SANN** |
| **IsToday( Today() )** |Tester om gjeldende dato er mellom midnatt i dag og midnatt i morgen. |**SANN** |
| **Text( DateAdd( Now(), 12 ), "mm/dd/yyyy hh:mm:ss" )** |Henter gjeldende dato og klokkeslett, legger 12 dager til resultatet, og viser det som en streng. |«02/24/2015 03:59:00» |
| **Text( DateAdd( Today(), 12 ), "mm/dd/yyyy hh:mm:ss" )** |Henter gjeldende dato, legger 12 dager til resultatet, og viser det som en streng. |«24/02/2015 00:00:00» |
| **IsToday( DateAdd( Now(), 12 ) )** |Tester om gjeldende dato og klokkeslett, pluss 12 dager, er mellom midnatt i dag og midnatt i morgen. |**USANN** |
| **IsToday( DateAdd( Today(), 12 ) )** |Tester om gjeldende dato, pluss 12 dager, er mellom midnatt i dag og midnatt i morgen. |**USANN** |

