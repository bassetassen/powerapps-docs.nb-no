---
title: Split-funksjonen | Microsoft Docs
description: Referanseinformasjon for Split-funksjonen i PowerApps, inkludert syntaks og eksempler
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta anneta
ms.date: 08/28/2017
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: b8f8dc0d354dd17fedd16524fed0f358b70839d4
ms.sourcegitcommit: f5013108140276b3d66a9dce13a061df89609d26
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 01/24/2019
ms.locfileid: "57798402"
---
# <a name="split-function-in-powerapps"></a>Split-funksjonen i PowerApps
Deler opp en tekststreng i en tabell med delstrenger.

## <a name="description"></a>Beskrivelse
**Split**-funksjonen deler opp en tekststreng i en tabell med delstrenger.  Bruk **Split** til å bryte opp lister som er delt opp med semikolon, datoer som bruker en skråstrek mellom datoelementene, og i andre situasjoner hvor det er brukt et tydelig skilletegn.  

En streng for skilletegn brukes til å bryte teksten opp.  Skilletegnet kan være null, ett eller flere tegn som er satt sammen som helhet i tekststrengen.  Å bruke en null-lengde eller en *tom* streng resulterer at i alle tegn brytes opp, atskilt.  De samsvarende skilletegnene returneres ikke i resultatet.  Hvis det ikke blir funnet noen treff for skilletegn, returneres hele tekststrengen som ett enkelt resultat.

Bruk **[Concat](function-concatenate.md)**-funksjonen til å sette sammen strengen (uten skilletegn). Bruk den **[MatchAll](function-ismatch.md)** funksjonen til å trekke ut deler av en tekststreng ved hjelp av et vanlig uttrykk, som du kan bruke til å dele en streng (i enkelte tilfeller). 

## <a name="syntax"></a>Syntaks
**Split**( *Text*, *Separator* )

* *Text* – obligatorisk.  Tekst som skal brytes opp.
* *Separator* – obligatorisk.  Skilletegn som skal brukes i oppdeling av strengen.  Kan være null, ett eller flere tegn.

## <a name="examples"></a>Eksempler

| Formel | Beskrivelse | Resultat |
| --- | --- | --- |
| **Split( "Apples,&nbsp;Oranges,&nbsp;Bananas", "," )** |Deler forskjellig frukt fra hverandre, basert på kommaseparatoren.  Delingen utføres basert på bare kommaet og ikke mellomrommet etter det, noe som resulterer i et mellomrom foran "&nbsp;Oranges" og "&nbsp;Bananas". |<style> img { max-width: none } </style> ![](media/function-split/fruit1.png) |
| **TrimEnds( Split( "Apples,&nbsp;Oranges,&nbsp;Bananas", "," ) )** |Samme som i forrige eksempel, men i dette tilfellet fjernes mellomrommet av [ **TrimEnds**-funksjonen](function-trim.md), som virker på enkeltkolonnetabellen som produseres av **Del**. Vi kunne også brukt skilletegnet **",&nbsp;"** som inkluderer mellomrommet etter kommaet, men dette ville ikke ha fungert ordentlig hvis der ikke var noe mellomrom eller hvis der var to mellomrom. |<style> img { max-width: none; } </style> ![](media/function-split/fruit2.png) |
| **Split( "08/28/17", "/" )** |Deler datoene fra hverandre ved hjelp av en skråstrek som skilletegn. |<style> img { max-width: none; } </style> ![](media/function-split/date.png) |
| **Split( "Hello,&nbsp;World", "," )** |Deler ordene fra hverandre, ved hjelp av et komma som skilletegn.  Det andre resultatet starter med et mellomrom siden dette var tegnet rett etter kommaet. |<style> img { max-width: none } </style> ![](media/function-split/comma.png) |
| **Split( "Hello,&nbsp;World", "o" )** |Deler opp strengen ved hjelp av tegnet «o» som skilletegn. |<style> img { max-width: none; } </style> ![](media/function-split/o.png) |
| **Split( "Hello,&nbsp;World", "l" )** |Deler opp strengen ved hjelp av enkelttegnet "l" som skilletegn. Siden det ikke var noen tegn mellom de to **l**-ene i **Hello**, ble en *tom* verdi returnert. |<style> img { max-width: none; } </style> ![](media/function-split/l.png) |
| **Split( "Hello,&nbsp;World", "ll" )** |Deler opp strengen ved hjelp av det doble tegnet «ll» som skilletegn. |<style> img { max-width: none } </style> ![](media/function-split/ll.png) |
| **Split( "Hello,&nbsp;World", "%" )** |Deler opp strengen ved hjelp av prosenttegnet som skilletegn. Siden dette skilletegnet ikke vises i strengen, returneres hele strengen som ett resultat. |<style> img { max-width: none } </style> ![](media/function-split/percent.png) |
| **Split( "Hello,&nbsp;World", "" )** |Deler opp strengen ved hjelp av en tom streng som skilletegn (null tegn). Dette vil bryte strengen ved hvert tegn. |<style> img { max-width: none } </style> ![](media/function-split/none.png) |

