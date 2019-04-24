---
title: Funksjonene Acos, Acot, Asin, Atan, Atan2, Cos, Cot, Degrees, Pi, Radians, Sin og Tan | Microsoft Docs
description: Referanseinformasjon for funksjonene Abs og Sqrt i PowerApps, inkludert syntaks og eksempler
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 09/13/2016
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 6eab89f436bc00ae0c447494607b5c1bb0cec875
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/23/2019
ms.locfileid: "61520001"
---
# <a name="acos-acot-asin-atan-atan2-cos-cot-degrees-pi-radians-sin-and-tan-functions-in-powerapps"></a>Funksjonene Acos, Acot, Asin, Atan, Atan2, Cos, Cot, Degrees, Pi, Radians, Sin og Tan i PowerApps
Beregner trigonometriske verdier.

## <a name="description"></a>Beskrivelse
### <a name="primary-functions"></a>Primære funksjoner
**Cos**-funksjonen returnerer cosinus til argumentet, en vinkel spesifisert i radianer.

**Cot**-funksjonen returnerer cotangens til argumentet, en vinkel spesifisert i radianer.

**Sin**-funksjonen returnerer sinus til argumentet, en vinkel spesifisert i radianer.

**Tan**-funksjonen returnerer tangensen til argumentet, en vinkel spesifisert i radianer.

### <a name="inverse-functions"></a>Inverse funksjoner
**Acos**-funksjonen returnerer arccosinusen, eller invers cosinus, til argumentet. Arccosinusen er vinkelen hvis cosinus er argumentet.  Den returnerte vinkelen er angitt i radianer i området 0 (null) til &pi;.

**Acot**-funksjonen returnerer prinsipalverdien til arccotangensen, eller invers cotangens, til argumentet.  Den returnerte vinkelen er angitt i radianer i området 0 (null) til &pi;.

**Asin**-funksjonen returnerer arcsinusen, eller invers sinus, til argumentet. Arcsinusen er vinkelen hvis sinus er argumentet.  Den returnerte vinkelen er angitt i radianer i området -&pi;/2 til &pi;/2.

**Atan**-funksjonen returnerer arctangensen, eller invers tangens, til argumentet. Arctangensen er vinkelen hvis tangens er argumentet. Den returnerte vinkelen er angitt i radianer i området -&pi;/2 til &pi;/2.

**Atan2**-funksjonen returnerer arctangensen, eller invers tangens, til de angitte*x*- og *y*-koordinatene som argumenter. Arctangensen er vinkelen fra *x*-aksen til en linje som inneholder origo (0,0) og et punkt med koordinater (*x*, *y*). Vinkelen er angitt i radianer mellom -&pi; og &pi;, ekskludert -&pi;.  Et positivt resultat representerer en vinkel mot klokken fra *x*-aksen, et negativt resultat representerer en vinkel med klokken.  **Atan2(&nbsp;*a*,&nbsp;*b*&nbsp;)** er lik **Atan(&nbsp;*b*/*a*&nbsp;)**, bortsett fra at ***a*** kan være lik 0 (null) med **Atan2**-funksjonen.

### <a name="helper-functions"></a>Hjelpefunksjoner
**Degrees**-funksjonen konverterer radianer til grader.  &pi; radianer er lik 180 grader.

**Pi**-funksjonen returnerer det transcendentale tallet&pi;, som begynner med 3,141592...

**Radians**-funksjonen konverterer grader til radianer.  

### <a name="notes"></a>Merknader
Hvis du sender et enkelt tall til disse funksjonene, er returverdien et enkelt resultat.  Hvis du angir en [enkeltkolonnetabell](../working-with-tables.md) som inneholder tall, vil returverdien være en enkeltkolonnetabell med resultater, ett resultat for hver post i argumentets tabell. Hvis du har en flerkolonnetabell, kan du gjøre den om til en enkeltkolonnetabell, som beskrevet i [Arbeid med tabeller](../working-with-tables.md).  

Hvis et argument resulterte i en underliggende verdi, ville resultatet være *tom*.  Dette kan skje når du for eksempel bruker inverse funksjoner med argumenter som er utenfor rekkevidde.

## <a name="syntax"></a>Syntaks
### <a name="primary-functions"></a>Primære funksjoner
**Cos**( *Radians* )<br>**Cot**( *Radians* )<br>**Sin**( *Radians* )<br>**Tan**( *Radians* )

* *Radians* – obligatorisk. Vinkelen som funksjonen skal arbeide med.

**Cos**( *SingleColumnTable* )<br>**Cot**( *SingleColumnTable* )<br>**Sin**( *SingleColumnTable* )<br>**Tan**( *SingleColumnTable* )

* *SingleColumnTable* – obligatorisk. En tabell med én kolonne med vinkler som funksjonen skal arbeide med.

### <a name="inverse-functions"></a>Inverse funksjoner
**Acos**( *Number* )<br>**Acot**( *Number* )<br>**Asin**( *Number* )<br>**Atan**( *Number* )

* *Number* – obligatorisk. Nummeret som funksjonen skal arbeide med.

**Acos**( *SingleColumnTable* )<br>**Acot**( *SingleColumnTable* )<br>**Asin**( *SingleColumnTable* )<br>**Atan**( *SingleColumnTable* )

* *SingleColumnTable* – obligatorisk. En tabell med én kolonne med tall som funksjonen skal arbeide med.

**Atan2**( *X*, *Y* )

* *X* – obligatorisk.  *X* – aksekoordinat.
* *Y* – obligatorisk.  *Y* – aksekoordinat.

### <a name="helper-functions"></a>Hjelpefunksjoner
**Degrees**( *Radians* )

* *Radians* – obligatorisk.  Vinkel i radianer som skal konverteres til grader.

**Pi**()

**Radians**( *Degrees* )

* *Degrees* – obligatorisk.  Vinkel i grader som skal konverteres til radianer.

## <a name="examples"></a>Eksempler
### <a name="single-number"></a>Heltall

| Formel | Beskrivelse | Resultat |
| --- | --- | --- |
| **Cos(&nbsp;1.047197&nbsp;)** |Returnerer cosinusen til 1,047197 radianer eller 60 grader. |0,5 |
| **Cot(&nbsp;Pi()/4&nbsp;)** |Returnerer cotangensen til 0,785398... radianer eller 45 grader. |1 |
| **Sin(&nbsp;Pi()/2&nbsp;)** |Returnerer sinusen til 1,570796... radianer eller 90 grader. |1 |
| **Tan(&nbsp;Radians(60)&nbsp;)** |Returnerer tangensen til 1,047197... radianer eller 60 grader. |1,732050... |
| **Acos(&nbsp;0.5&nbsp;)** |Returnerer arccosinusen til 0,5 i radianer. |1,047197... |
| **Acot(&nbsp;1&nbsp;)** |Returnerer arccotangensen til 1 i radianer. |0,785398... |
| **Asin(&nbsp;1&nbsp;)** |Returnerer arcsinusen til 1 i radianer. |1,570796... |
| **Atan(&nbsp;1.732050&nbsp;)** |Returnerer arctangensen til 1,732050 i radianer. |1,047197... |
| **Atan2(&nbsp;5,&nbsp;3&nbsp;)** |Returnerer arctangensen for vinkelen fra *x*-aksen til linjen som inneholder origo (0,0), og koordinaten (5,3) som er omtrent 31 grader. |0,540419... |
| **Atan2(&nbsp;4,&nbsp;4&nbsp;)** |Returnerer arctangensen for vinkelen fra *x*-aksen til linjen som inneholder origo (0,0), og koordinaten (4,4) som er nøyaktig &pi;/4 radianer eller 45 grader. |0,785398... |
| **Degrees(&nbsp;1.047197&nbsp;)** |Returnerer det tilsvarende antallet grader for 1,047197 radianer. |60 |
| **Pi()** |Returnerer det transcendentale tallet &pi;. |3,141592... |
| **Radians(&nbsp;15&nbsp;)** |Returnerer det tilsvarende antallet radianer for 15 grader. |0,261799... |

### <a name="single-column-table"></a>Tabell med én kolonne
Eksemplet i denne delen bruker en [datakilde](../working-with-data-sources.md) med navnet **ValueTable** og som inneholder følgende data.  Den siste posten i tabellen er &pi;/2 radianer eller 90 grader.

![](media/function-trig/values.png)

| Formel | Beskrivelse | Resultat |
| --- | --- | --- |
| **Cos(&nbsp;ValueTable&nbsp;)** |Returnerer cosinusen for hvert tall i tabellen. |<style> img { max-width: none } </style> ![](media/function-trig/values-cos.png) |
| **Cot(&nbsp;ValueTable&nbsp;)** |Returnerer contangensen for hvert tall i tabellen. |<style> img { max-width: none } </style> ![](media/function-trig/values-cot.png) |
| **Sin(&nbsp;ValueTable&nbsp;)** |Returnerer sinusen for hvert tall i tabellen. |<style> img { max-width: none } </style> ![](media/function-trig/values-sin.png) |
| **Tan(&nbsp;ValueTable&nbsp;)** |Returnerer tangensen for hvert tall i tabellen. |<style> img { max-width: none } </style> ![](media/function-trig/values-tan.png) |
| **Acos(&nbsp;ValueTable&nbsp;)** |Returnerer arccosinusen for hvert tall i tabellen. |<style> img { max-width: none } </style> ![](media/function-trig/values-acos.png) |
| **Acot(&nbsp;ValueTable&nbsp;)** |Returnerer arccotangensen for hvert tall i tabellen. |<style> img { max-width: none } </style> ![](media/function-trig/values-acot.png) |
| **Asin(&nbsp;ValueTable&nbsp;)** |Returnerer arcsinusen for hvert tall i tabellen. |<style> img { max-width: none } </style> ![](media/function-trig/values-asin.png) |
| **Atan(&nbsp;ValueTable&nbsp;)** |Returnerer arctangensen for hvert tall i tabellen. |<style> img { max-width: none } </style> ![](media/function-trig/values-atan.png) |
| **Degrees(&nbsp;ValueTable&nbsp;)** |Returnerer det tilsvarende antallet grader for hvert tall i tabellen, som antas å være vinkler i radianer. |<style> img { max-width: none } </style> ![](media/function-trig/values-degrees.png) |
| **Radians(&nbsp;ValueTable&nbsp;)** |Returnerer det tilsvarende antallet radianer for hvert tall i tabellen, som antas å være vinkler i grader. |<style> img { max-width: none } </style> ![](media/function-trig/values-radians.png) |

