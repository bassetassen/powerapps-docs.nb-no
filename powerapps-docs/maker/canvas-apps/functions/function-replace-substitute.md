---
title: Funksjonene Replace og Substitute | Microsoft Docs
description: Referanseinformasjon for funksjonene Replace og Substitute i PowerApps, inkludert syntaks og eksempler
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 12/02/2018
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: fca1953402c87ca13bc3560b827cde03a47a8e92
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/23/2019
ms.locfileid: "61551610"
---
# <a name="replace-and-substitute-functions-in-powerapps"></a>Funksjonene Replace og Substitute i PowerApps
Erstatt en del av en tekststreng med en annen streng.

## <a name="description"></a>Beskrivelse
**Replace**-funksjonen identifiserer teksten du vil erstatte basert på startposisjon og lengde.  

**Substitute**-funksjonen identifiserer teksten du vil erstatte ved å sammenligne en streng. Hvis mer enn ett treff blir funnet, kan du erstatte all dem eller angi en erstatte.

Hvis du angir en enkelt streng, er returverdien den endrede strengen. Hvis du angir en [enkeltkolonnetabell](../working-with-tables.md) som inneholder strenger, vil returverdien være en enkeltkolonnetabell med endrede strenger. Hvis du har en flerkolonnetabell, kan du gjøre den om til en enkeltkolonnetabell, som beskrevet i [arbeid med tabeller](../working-with-tables.md).

## <a name="syntax"></a>Syntaks
**Replace**( *String*, *StartingPosition*, *NumberOfCharacters*, *NewString* )

* *String* – obligatorisk. Strengen det skal arbeides i.
* *StartingPosition* – obligatorisk. Tegnplassering hvor erstatningen skal begynne. Det første tegnet i *String* er i posisjon 1.
* *NumberOfCharacters* – obligatorisk. Antallet tegn som skal erstattes i *String*.
* *NewString* – obligatorisk. Erstatningsstrengen. Antall tegn i dette argumentet kan være forskjellig fra *NumberOfCharacters*-argumentet.

**Substitute**( *String*, *OldString*, *NewString* [, *InstanceNumber* ] )

* *String* – obligatorisk. Strengen det skal arbeides i.
* *OldString* – obligatorisk. Strengen som skal erstattes.
* *NewString* – obligatorisk. Erstatningsstrengen. *OldString* og *NewString* kan ha forskjellig lengde.
* *InstanceNumber* – valgfritt. Bruk dette argumentet til å angi hvilken forekomst av *OldString* erstatte Hvis *streng* inneholder mer enn én forekomst. Hvis du ikke angir dette argumentet, erstattes alle forekomster.

**Replace**( *SingleColumnTable*, *StartingPosition*, *NumberOfCharacters*, *NewString* )

* *SingleColumnTable* – obligatorisk. En enkeltkolonnetabell med strenger som det skal arbeides i.
* *StartingPosition* – obligatorisk. Tegnplassering hvor erstatningen skal begynne.  Det første tegnet i hver streng i tabellen er i posisjon 1.
* *NumberOfCharacters* – obligatorisk. Antall tegn som skal erstattes i hver streng.
* *NewString* – obligatorisk.  Erstatningsstrengen. Antall tegn i dette argumentet kan være forskjellig fra *NumberOfCharacters*-argumentet.

**Substitute**( *SingleColumnTable*, *OldString*, *NewString* [, *InstanceNumber* ] )

* *SingleColumnTable* – obligatorisk. En enkeltkolonnetabell med strenger som det skal arbeides i.
* *OldString* – obligatorisk.  Strengen som skal erstattes.
* *NewString* – obligatorisk.  Erstatningsstrengen. *OldString* og *NewString* kan ha forskjellig lengde.
* *InstanceNumber* – valgfritt. Bruk dette argumentet til å angi hvilken forekomst av *OldString* erstatte Hvis *streng* inneholder mer enn én forekomst. Hvis du ikke angir dette argumentet, erstattes alle forekomster.

## <a name="examples"></a>Eksempler

| Formel | Beskrivelse | Resultat |
|---------|-------------|--------|
| **Replace( "abcdefghijk",&nbsp;6,&nbsp;5,&nbsp;"*" )** | Erstatter fem tegn i «abcdefghijk» med ett enkelt "*" tegn, begynner med det sjette tegnet ("f"). | «abcde * k» |
| **Erstatt (&nbsp;«2019»,&nbsp;3,&nbsp;2,&nbsp;"20"&nbsp;)** | Erstatter de to siste tegnene i "2019" med "20". | "2020" |
| **Replace(&nbsp;"123456",&nbsp;1,&nbsp;3,&nbsp;"_"&nbsp;)** | Erstatter de tre første tegnene i "123456" med et enkelt "_"-tegn. | "_456" | 
| **SUBSTITUTE (&nbsp;«salg&nbsp;Data»,&nbsp;«Salg»,&nbsp;«Koste»&nbsp;)** | Erstatter strengen «Kostnadene» for «Salg». | «Koste Data» | 
| **SUBSTITUTE («kvartal&nbsp;1,&nbsp;2018 ","1","2", 1)** | Erstatter bare den første forekomsten av "1" med "2" fordi det fjerde argumentet (*InstanceNumber*) leveres med 1. |  «Kvartal 2, 2018» |
| **SUBSTITUTE («kvartal&nbsp;1,&nbsp;2011 ","1","2", 3).** | Erstatter bare den tredje forekomsten av "1" med "2" fordi det fjerde argumentet (*InstanceNumber*) er angitt med en 3. | «Kvartal 1, 2012» |
| **SUBSTITUTE («kvartal&nbsp;1,&nbsp;2011 ","1","2")** | Erstatter alle forekomster av "1" med "2" fordi det fjerde argumentet (*InstanceNumber*) er ikke angitt. | «Kvartal 2, 2022» |
| **Erstatt (<br>[&nbsp;"kvartal&nbsp;1,&nbsp;2018»,<br>" kvartal&nbsp;2,&nbsp;2011",<br>" kvartal&nbsp;4,&nbsp;2019"],<br>9, 1, "3")** | Erstatter det niende tegnet i hver post i tabellen én kolonne med "3". | [&nbsp;"Kvartal&nbsp;3,&nbsp;2018",<br>«Kvartal&nbsp;3,&nbsp;2011»,<br>«Kvartal&nbsp;3,&nbsp;2019 "&nbsp;] |
| **SUBSTITUTE ( <br>[&nbsp;"kvartal&nbsp;1,&nbsp;2018»,<br>" kvartal&nbsp;1,&nbsp;2011",<br>" Q1,&nbsp;2019"&nbsp;],<br>"1 ","3 ", 1)** | Fordi det fjerde argumentet (*InstanceNumber*) er angitt med verdien 1, erstatter bare den første forekomsten av "1" i hver post i tabellen én kolonne med "3". | [&nbsp;"Kvartal&nbsp;3,&nbsp;2018",<br>«Kvartal&nbsp;3,&nbsp;2011»,<br>"Q3,&nbsp;2019"&nbsp;] |
| **SUBSTITUTE ( <br>[&nbsp;"kvartal&nbsp;1,&nbsp;2018»,<br>" kvartal&nbsp;1,&nbsp;2011",<br>" Q1,&nbsp;2019"&nbsp;],<br>"1 ","3")** | Fordi det fjerde argumentet (*InstanceNumber*) er ikke oppgitt, erstatter alle forekomster av "1" i hver post i tabellen én kolonne med "3". | [&nbsp;"Kvartal&nbsp;3,&nbsp;2038",<br>«Kvartal&nbsp;3,&nbsp;2033»,<br>«3. KVARTAL –,&nbsp;2039 "&nbsp;] |  
 


