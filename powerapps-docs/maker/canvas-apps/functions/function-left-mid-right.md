---
title: Funksjonene Left, Mid og Right | Microsoft Docs
description: Referanseinformasjon for funksjonene Left, Mid og Right i PowerApps, inkludert syntaks og eksempler
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
ms.openlocfilehash: 2cf54b1225578b2bb2bdefa8c0bd02dc0c9c0283
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/22/2018
ms.locfileid: "30996112"
---
# <a name="left-mid-and-right-functions-in-powerapps"></a>Funksjonene Left, Mid og Right i PowerApps
Trekker ut den venstre, midterste eller høyre delen av en tekststreng.

## <a name="description"></a>Beskrivelse
Funksjonene **Left**, **Mid** og **Right** returnerer en del av en streng.

* **Left** returnerer de første tegnene i en streng.
* **Mid** returnerer de midterste tegnene i en streng.
* **Right** returnerer de siste tegnene i en streng.

Hvis du angir en enkelt streng som et argument, returnerer funksjonen delen av strengen du har forespurt. Hvis du angir en [enkeltkolonnetabell](../working-with-tables.md) som inneholder strenger, returnerer funksjonen en enkeltkolonnetabell med delene du har forespurt av disse strengene. Hvis du har en flerkolonnetabell, kan du gjøre den om til en enkeltkolonnetabell, som beskrevet i [Å arbeide med tabeller](../working-with-tables.md).

Hvis startposisjonen er negativ eller utenfor slutten av strengen, returnerer **Mid***tom*.  Du kan kontrollere lengden på en streng ved hjelp av  **[Len](function-len.md)**-funksjonen. Hvis du ber om flere tegn enn strengen inneholder, returnerer funksjonen så mange tegn som mulig.

## <a name="syntax"></a>Syntaks
**Left**( *String*, *NumberOfCharacters* )<br>**Mid**( *String*, *StartingPosition*, *NumberOfCharacters* )<br>**Left**( *String*, *NumberOfCharacters* )

* *String* – obligatorisk. Strengen som resultatet skal trekkes ut fra.
* *StartingPosition* – obligatorisk ( bare **Mid**).  Startposisjonen.  Posisjon 1 er det første tegnet i tekststrengen.
* *NumberOfCharacters* – obligatorisk.  Antallet tegn som skal returneres.

**Left**( *SingleColumnTable*, *NumberOfCharacters* )<br>**Mid**( *SingleColumnTable*, *StartingPosition*, *NumberOfCharacters* )<br>**Right**( *SingleColumnTable*, *NumberOfCharacters* )

* *SingleColumnTable* – obligatorisk. En tabell med én kolonne med strenger som resultatene skal trekkes ut fra.
* *StartingPosition* – obligatorisk ( bare **Mid**).  Startposisjonen.  Posisjon 1 er det første tegnet i tekststrengen.
* *NumberOfCharacters* – obligatorisk.  Antallet tegn som skal returneres.

## <a name="examples"></a>Eksempler
### <a name="single-string"></a>Enkelt streng
Eksemplene i denne delen bruker en kontroll for innskriving av tekst som [datakilde](../working-with-data-sources.md). Kontrollen heter **Forfatter** og inneholder strengen «E. E. Cummings».

| Formel | Beskrivelse | Resultat |
| --- | --- | --- |
| **Left ( Author.Text, 5 )** |Trekker ut opptil fem tegn fra begynnelsen av strengen. |«E. E.» |
| **Mid( Author.Text, 7, 4 )** |Trekker ut opptil fire tegn, og starter med det sjuende tegnet fra strengen. |«Cumm» |
| **Right( Author.Text, 5 )** |Trekker ut opptil fem tegn fra slutten av strengen. |«mings» |

### <a name="single-column-table"></a>Tabell med én kolonne
Hvert eksempel i denne delen trekker ut strengene fra **Adresse** [-kolonnen](../working-with-tables.md#columns) for denne datakilden, kalt **Personer**, og returnerer en tabell med én kolonne som inneholder resultatene:

![](media/function-left-mid-right/people-table.png)

| Formel | Beskrivelse | Resultat |
| --- | --- | --- |
| **Left( ShowColumns(&nbsp;People,&nbsp;"Address"&nbsp;), 8 )** |Trekker ut de åtte første tegnene i hver streng. |<style> img { max-width: none } </style> ![](media/function-left-mid-right/people-table-left.png) |
| **Mid( ShowColumns(&nbsp;People,&nbsp;"Address"&nbsp;), 5, 7 )** |Trekker ut de midterste sju tegnene på hver streng, begynner med det femte tegnet. |![](media/function-left-mid-right/people-table-mid.png) |
| **Right( ShowColumns(&nbsp;People,&nbsp;"Address"&nbsp;), 7 )** |Trekker ut de sju siste tegnene i hver streng. |![](media/function-left-mid-right/people-table-right.png) |

### <a name="step-by-step-example"></a>Trinnvis veiledning – eksempel
1. Importer eller opprett en [samling](../working-with-data-sources.md#collections) kalt **Beholdning** og vis den i et galleri, som den første prosedyren i [Vis bilder og tekst i et galleri](../show-images-text-gallery-sort-filter.md) beskriver.
2. Angi **[Tekst](../controls/properties-core.md)**-egenskapen for etiketten nederst i galleriet til denne funksjonen:
   
    **Right(ThisItem.ProductName, 3)**
   
    Etiketten viser de tre siste tegnene i hvert produktnavn.

