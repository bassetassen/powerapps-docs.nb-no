---
title: Funksjonene Replace og Substitute | Microsoft Docs
description: Referanseinformasjon for funksjonene Replace og Substitute i PowerApps, inkludert syntaks og eksempler
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 12/02/2018
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: ff0e016f6ab1ad4f66651ccd3cfa2711f1d85a38
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/07/2019
ms.locfileid: "71992383"
---
# <a name="replace-and-substitute-functions-in-powerapps"></a>Funksjonene Replace og Substitute i PowerApps
Erstatt en del av en tekststreng med en annen streng.

## <a name="description"></a>Beskrivelse
**Replace**-funksjonen identifiserer teksten du vil erstatte basert på startposisjon og lengde.  

**Substitute**-funksjonen identifiserer teksten du vil erstatte ved å sammenligne en streng. Hvis det finnes mer enn ett treff, kan du erstatte alle eller angi en som skal erstattes.

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
* *InstanceNumber* – valgfritt. Bruk dette argumentet til å angi hvilken forekomst av *OldString* som skal erstattes hvis *strengen* inneholder mer enn én forekomst. Hvis du ikke angir dette argumentet, blir alle forekomster erstattet.

**Replace**( *SingleColumnTable*, *StartingPosition*, *NumberOfCharacters*, *NewString* )

* *SingleColumnTable* – obligatorisk. En enkeltkolonnetabell med strenger som det skal arbeides i.
* *StartingPosition* – obligatorisk. Tegnplassering hvor erstatningen skal begynne.  Det første tegnet i hver streng i tabellen er i posisjon 1.
* *NumberOfCharacters* – obligatorisk. Antall tegn som skal erstattes i hver streng.
* *NewString* – obligatorisk.  Erstatningsstrengen. Antall tegn i dette argumentet kan være forskjellig fra *NumberOfCharacters*-argumentet.

**Substitute**( *SingleColumnTable*, *OldString*, *NewString* [, *InstanceNumber* ] )

* *SingleColumnTable* – obligatorisk. En enkeltkolonnetabell med strenger som det skal arbeides i.
* *OldString* – obligatorisk.  Strengen som skal erstattes.
* *NewString* – obligatorisk.  Erstatningsstrengen. *OldString* og *NewString* kan ha forskjellig lengde.
* *InstanceNumber* – valgfritt. Bruk dette argumentet til å angi hvilken forekomst av *OldString* som skal erstattes hvis *strengen* inneholder mer enn én forekomst. Hvis du ikke angir dette argumentet, blir alle forekomster erstattet.

## <a name="examples"></a>Eksempler

| Formel | Beskrivelse | Resultat |
|---------|-------------|--------|
| **Replace ("abcdefghijk", @no__t – 16, &nbsp;5, &nbsp; "*")** | Erstatter fem tegn i «abcdefghijk» med ett enkelt "*"-tegn, med start fra det sjette tegnet ("f"). | "abcde * k" |
| **Replace (&nbsp; "2019", &nbsp;3, &nbsp;2, &nbsp; "20" &nbsp;)** | Erstatter de to siste tegnene i "2019" med "20". | "2020" |
| **Replace (&nbsp; "123456", &nbsp;1, &nbsp;3, &nbsp; "_" &nbsp;)** | Erstatter de tre første tegnene i "123456" med ett enkelt "_"-tegn. | "_456" | 
| **Erstatt (&nbsp; "salg @ no__t-2Data", &nbsp; "salg", &nbsp; "kostnad" &nbsp;)** | Erstatter strengen «kostnad» for salg. | "Kostnads data" | 
| **Substitute ("kvartal @ no__t-11, &nbsp;2018", "1", "2", 1)** | Erstatter bare den første forekomsten av "1" med "2" fordi det fjerde argumentet (*InstanceNumber*) leveres med 1. |  "Kvartal 2, 2018" |
| **Substitute ("kvartal @ no__t-11, &nbsp;2011", "1", "2", 3)** | Erstatter bare den tredje forekomsten av "1" med "2" fordi det fjerde argumentet (*InstanceNumber*) leveres med en 3. | "Kvartal 1, 2012" |
| **Substitute ("kvartal @ no__t-11, &nbsp;2011", "1", "2")** | Erstatter alle forekomster av "1" med "2" fordi det fjerde argumentet (*InstanceNumber*) ikke er angitt. | "Kvartal 2, 2022" |
| **Replace (<br> [&nbsp; "kvartal @ no__t-31, &nbsp;2018", <br> "kvartal @ no__t-62, &nbsp;2011", <br> "kvartal @ no__t-94, 02019"], 19, 1, "3")** | Erstatter det niende tegnet i hver post i en tabell med én kolonne med «3». | [&nbsp; "kvartal @ no__t-13, &nbsp;2018",<br>"Kvartal @ no__t-03, &nbsp;2011",<br>"Kvartal @ no__t-03, &nbsp;2019" &nbsp;] |
| **Substitute (<br> [@no__t – 2» @ no__t-31, &nbsp;2018», <br> "kvartal @ no__t-61, &nbsp;2011", <br> "Q1, &nbsp;2019" 0], 1 "1", "3", 1)** | Fordi det fjerde argumentet (*InstanceNumber*) leveres med verdien 1, erstattes bare den første forekomsten av «1» i hver post i en tabell med én kolonne med «3». | [@no__t – 0 "kvartal @ no__t-13, &nbsp;2018",<br>"Kvartal @ no__t-03, &nbsp;2011",<br>«Q3, &nbsp;2019 "&nbsp;] |
| **Substitute (<br> [&nbsp;» @ no__t-31, &nbsp;2018», <br> "kvartal @ no__t-61, &nbsp;2011", <br> "Q1, &nbsp;2019" 0], 1 "1", "3")** | Fordi det fjerde argumentet (*InstanceNumber*) ikke er angitt, erstattes alle forekomster av «1» i hver post i en tabell med én kolonne med «3». | [@no__t – 0 "kvartal @ no__t-13, &nbsp;2038",<br>"Kvartal @ no__t-03, &nbsp;2033",<br>«Q3, &nbsp;2039 "&nbsp;] |  
 


