---
title: Funksjonene Date og Time| Microsoft Docs
description: Referanseinformasjon for funksjonene Date og Time i PowerApps, inkludert syntaks og eksempler
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
ms.openlocfilehash: 869c0fcff6e519281e527c832305d74f2e7fd78f
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/24/2018
ms.locfileid: "42864103"
---
# <a name="date-and-time-functions-in-powerapps"></a>Funksjonene Date og Time i PowerApps
Konverterer dato- og klokkeslettkomponenter til en dato/klokkeslett-verdi.

## <a name="description"></a>Beskrivelse
**Date** -funksjonen konverterer separate verdier for år, måned og dag til en dato/klokkeslett-verdi.  Klokkeslettdelen er midnatt.

* Hvis Year er fra og med 0 til og med 1899, legger funksjonen den verdien sammen med 1900 for å beregne året.  **70** blir **1970**.
* Hvis Month er mindre enn 1 eller mer enn 12, vil det antallet måneder trekkes fra eller legges til fra begynnelsen av det angitte året.
* Hvis Day er større enn antall dager i den angitte måneden, legger funksjonen til det antallet dager fra den første dagen i måneden og returnerer den tilsvarende datoen fra en påfølgende måned.  Hvis Day er mindre enn 1, trekker funksjonen så mange dager, pluss 1, fra den første dagen i den angitte måneden.

**Time**-funksjonen konverterer separate verdier for timer, minutter og sekunder til en dato/klokkeslett-verdi.  Resultatet har ingen tilknyttet dato.

Se funksjonene **[DateValue](function-datevalue-timevalue.md)**,  **[tidsverdi](function-datevalue-timevalue.md)**, og **[DateTimeValue](function-datevalue-timevalue.md)** for informasjon om hvordan du konverterer en streng til en verdi.  

Se også [Slik arbeider du med datoer og klokkeslett](../show-text-dates-times.md) hvis du vil ha mer informasjon.

## <a name="syntax"></a>Syntaks
**Date**( *Year*, *Month*, *Day* )

* *Year* – obligatorisk.  Tall som er større enn 1899, tolkes som absolutte (1980 tolkes som 1980). Tall fra 0 til og med 1899 tolkes som relative til 1900. (For eksempel tolkes 80 som 1980.)
* *Month* – obligatorisk.  Et tall fra 1 til 12.
* *Day* – obligatorisk. Et tall fra 1 til 31.

**Time**( *Hour*, *Minute*, *Second* )

* *Hour* – obligatorisk.  Et tall fra 0 (kl. 00:00) til 23 (kl. 23:00).
* *Minute* – obligatorisk. Et tall fra 0 til 59.
* *Second* – obligatorisk. Et tall fra 0 til 59.

## <a name="examples"></a>Eksempler
### <a name="date"></a>Dato
Hvis en bruker har skrevet inn **1979** i en kontroll for tekstinndata med navnet **HireYear**, **3** i en kontroll for tekstinndata med navnet **HireMonth** og **17** i en kontroll for tekstinndata med navnet **HireDay**, returnerer denne funksjonen **17/3/1979**:

**Date(Value(HireYear.Text), Value(HireMonth.Text), Value(HireDay.Text))**

### <a name="time"></a>Time
Hvis en bruker har skrevet inn **14** i en kontroll for tekstinndata med navnet **BirthHour**, **50** i en kontroll for tekstinndata med navnet **BirthMinute** og **24** i en kontroll for tekstinndata med navnet **BirthSecond**, returnerer denne funksjonen **02:50:24 p**.

**Text(Time(Value(BirthHour.Text), Value(BirthMinute.Text), Value(BirthSecond.Text)), "hh:mm:ss a/p")**

