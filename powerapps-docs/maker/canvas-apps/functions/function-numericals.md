---
title: Funksjonene Abs, Exp, Ln, Power, and Sqrt | Microsoft Docs
description: Referanseinformasjon for funksjonene Abs og Sqrt og de øvrige funksjonene i PowerApps, inkludert syntaks og eksempler
documentationcenter: na
author: gregli-msft
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: reference
ms.component: canvas
ms.date: 09/13/2016
ms.author: gregli
ms.openlocfilehash: 15d458142bc1077b1bf55ae6e358c826f813ecb2
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/04/2018
ms.locfileid: "31829514"
---
# <a name="abs-exp-ln-power-and-sqrt-functions-in-powerapps"></a>Funksjonene Abs, Exp, Ln, Power og Sqrt i PowerApps
Beregner absolutte verdier, naturlige logaritmer, kvadratrøtter og resultater av å heve *e* eller et annet tall til angitte potenser.

## <a name="description"></a>Beskrivelse
**Abs**-funksjonen returnerer den ikke-negative verdien for argumentet sitt. Hvis tallet er negativt, returnerer **Abs** den positive ekvivalenten.

**Exp**-funksjonen returnerer *e* opphøyd i potensen for argumentet sitt.  Det transcendente tallet *e* begynner med 2.7182818...

**Ln**-funksjonen returnerer den naturlige logaritmen (grunntall *e*) for argumentet sitt.

**Power**-funksjonen returnerer et tall opphøyd i en potens.  Det er det samme som å bruke [**^** operatoren](operators.md).

**Sqrt**-funksjonen returnerer tallet som, når det er multiplisert med seg selv, er lik argumentet sitt.

Hvis du sender et enkelt tall, er returverdien et enkelt resultat basert på funksjonen som er brukt.  Hvis du angir en [enkeltkolonnetabell](../working-with-tables.md) som inneholder tall, vil returverdien være en enkeltkolonnetabell med resultater, ett resultat for hver post i argumentets tabell. Hvis du har en flerkolonnetabell, kan du gjøre den om til en enkeltkolonnetabell, som beskrevet i [Å arbeide med tabeller](../working-with-tables.md).  

Hvis et argument resulterte i en underliggende verdi, er resultatet *tom*.  Dette kan for eksempel skje med kvadratrøttene og logaritmene for negative tall.

## <a name="syntax"></a>Syntaks
**Abs**( *Number* )<br>**Exp**( *Number* )<br>**Ln**( *Number* )<br>**Sqrt**( *Number* )

* *Number* – obligatorisk. Nummeret som funksjonen skal arbeide med.

**Power**( *Base*, *Exponent* )

* *Base* – obligatorisk. Grunntallet som skal opphøyes.
* *Exponent* – obligatorisk. Eksponenten som grunntallet blir opphøyd med.

**Abs**( *SingleColumnTable* )<br>**Exp**( *SingleColumnTable* )<br>**Ln**( *SingleColumnTable* )<br>**Sqrt**( *SingleColumnTable* )

* *SingleColumnTable* – obligatorisk. En tabell med én kolonne med tall som funksjonen skal arbeide med.

## <a name="examples"></a>Eksempler
### <a name="single-number"></a>Heltall
| Formel | Beskrivelse | Resultat |
| --- | --- | --- |
| **Abs( -55 )** |Returnerer tallet uten minustegnet. |55 |
| **Exp( 2 )** |Returnerer *e* opphøyd i potensen av 2, eller *e* \* *e*. |7.389056... |
| **Ln( 100 )** |Returnerer den naturlige logaritmen (grunntall *e*) for tallet 100. |4.605170... |
| **Power( 5, 3 )** |Returnerer 5 opphøyd i potensen av 3, eller 5 \* 5 \* 5. |125 |
| **Sqrt( 9 )** |Returnerer tallet som, når det er multiplisert med seg selv, resulterer i 9. |3 |

### <a name="single-column-table"></a>Tabell med én kolonne
Eksemplet i denne delen bruker en [datakilde](../working-with-data-sources.md) med navnet **ValueTable** som inneholder følgende data:

![](media/function-numericals/values.png)

| Formel | Beskrivelse | Resultat |
| --- | --- | --- |
| **Abs(&nbsp;ValueTable&nbsp;)** |Returnerer den absolutte verdien for hvert tall i tabellen. |<style> img { max-width: none } </style> ![](media/function-numericals/values-abs.png) |
| **Exp(&nbsp;ValueTable&nbsp;)** |Returnerer *e* opphøyd i potensen av hvert tall i tabellen. |<style> img { max-width: none } </style> ![](media/function-numericals/values-exp.png) |
| **Ln(&nbsp;ValueTable&nbsp;)** |Returnerer den naturlige logaritmen for hvert tall i tabellen. |<style> img { max-width: none } </style> ![](media/function-numericals/values-ln.png) |
| **Sqrt(&nbsp;ValueTable&nbsp;)** |Returnerer kvadratroten for hvert tall i tabellen |![](media/function-numericals/values-sqrt.png) |

### <a name="step-by-step-example"></a>Trinnvis veiledning – eksempel
1. Legg til en **[Tekstinndata](../controls/control-text-input.md)**-kontroll, og gi den navnet **Kilde**.
2. Legg til en **Etikett**-kontroll, og angi **[Tekst](../controls/properties-core.md)**-egenskapen til denne formelen:
   <br>
   **Sqrt( Value( Source.Text ) )**
3. Skriv inn et tall i **Kilde**, og bekreft at **Etikett**-kontrollen viser kvadratroten av tallet du skrev inn.

