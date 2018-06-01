---
title: Len-funksjonen | Microsoft Docs
description: Referanseinformasjon, herunder syntaks og eksempler, for Len-funksjonen i PowerApps
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
ms.openlocfilehash: 06f8e7a80adc7a2175f2da7ab98fb1966d8cf015
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/22/2018
ms.locfileid: "30996287"
---
# <a name="len-function-in-powerapps"></a>Len-funksjonen i PowerApps
Returnerer lengden på en tekststreng.

## <a name="description"></a>Beskrivelse
Hvis du angir en enkelt streng som argument, er returverdien lengden i et tallformat.  Hvis du angir en [enkeltkolonnetabell](../working-with-tables.md) som inneholder strenger, vil returverdien være en enkeltkolonnetabell som inneholder lengden på hver streng. Hvis du har en flerkolonnetabell, kan du gjøre den om til en enkeltkolonnetabell, som beskrevet i [arbeide med tabeller](../working-with-tables.md).

Hvis du angir en [tom](function-isblank-isempty.md) streng, returnerer **lengde** 0.

## <a name="syntax"></a>Syntaks
**Lengde**( *streng* )

* *Streng* – obligatorisk. Strengen som skal måles.

**Len**( *SingleColumnTable* )

* *SingleColumnTable* – obligatorisk. En enkeltkolonnetabell med strenger som skal måles.

## <a name="examples"></a>Eksempler
### <a name="single-string"></a>Enkelt streng
I eksemplene i denne delen, er [datakilden](../working-with-data-sources.md) en kontroll for innskriving av tekst som heter **Forfatter**, og som inneholder strengen «E. E. Cummings».

| Formel | Beskrivelse | Resultat |
| --- | --- | --- |
| **Len (Author.Text)** |Måler lengden på strengen i **Forfatter**-kontrollen. |14 |
| **Lengde («»)** |Måler lengden på en tom streng. |0 |

### <a name="single-column-table"></a>Tabell med én kolonne
Datakilden for det første eksemplet i denne delen heter **Personer** og inneholder disse dataene:

![](media/function-len/people-table.png)

| Formel | Beskrivelse | Resultat |
| --- | --- | --- |
| **Len (ShowColumns (&nbsp;Personer,&nbsp;«Adresse»&nbsp;))** |I **Adresse** [-kolonnen](../working-with-tables.md#columns) av **Personer**-tabellen:<br><ul><li>Måler lengden på hver streng.</li><li>Returnerer en tabell med én kolonne som inneholder lengden på hver streng.</li> |<style> img { max-width: none } </style> ![](media/function-len/people-table-len.png) |
| **Len ([«Hei», «til», «verden», «»])** |I **[Verdi](function-value.md)** kolonnen i den linjebundne tabellen:<br><ul><li>Måler lengden på hver streng.</li><li>Returnerer en tabell med én kolonne som inneholder lengden på hver streng.</li> |![](media/function-len/people-table-len-inline.png) |

