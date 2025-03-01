---
title: Len-funksjonen | Microsoft Docs
description: Referanseinformasjon, herunder syntaks og eksempler, for Len-funksjonen i PowerApps
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 11/07/2015
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 967d83286cd179177cfbb5558f1fc3484a332875
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/07/2019
ms.locfileid: "71984594"
ms.PowerAppsDecimalTransform: true
---
# <a name="len-function-in-powerapps"></a>Len-funksjonen i PowerApps
Returnerer lengden på en tekststreng.

## <a name="description"></a>Beskrivelse
Hvis du angir en enkelt streng som argument, er returverdien lengden i et tallformat.  Hvis du angir en [enkeltkolonnetabell](../working-with-tables.md) som inneholder strenger, vil returverdien være en enkeltkolonnetabell som inneholder lengden på hver streng. Hvis du har en flerkolonnetabell, kan du gjøre den om til en enkeltkolonnetabell, som beskrevet i [arbeid med tabeller](../working-with-tables.md).

Hvis du angir en [tom](function-isblank-isempty.md) streng, returnerer **len** 0.

## <a name="syntax"></a>Syntaks
**Len**( *String* )

* *String* – obligatorisk. Strengen som skal måles.

**Len**( *SingleColumnTable* )

* *SingleColumnTable* – obligatorisk. En enkeltkolonnetabell med strenger som skal måles.

## <a name="examples"></a>Eksempler
### <a name="single-string"></a>Enkelt streng
I eksemplene i denne delen er [datakilden](../working-with-data-sources.md) en kontroll for innskriving av tekst som heter **Forfatter**, og som inneholder strengen «E. E. Cummings».

| Formel | Beskrivelse | Resultat |
| --- | --- | --- |
| **Len( Author.Text )** |Måler lengden på strengen i **Forfatter**-kontrollen. |14 |
| **Len( "" )** |Måler lengden på en tom streng. |0 |

### <a name="single-column-table"></a>Tabell med én kolonne
Datakilden for det første eksemplet i denne delen heter **Personer** og inneholder disse dataene:

![](media/function-len/people-table.png)

| Formel | Beskrivelse | Resultat |
| --- | --- | --- |
| **Len( ShowColumns(&nbsp;People;&nbsp;"Address"&nbsp;) )** |I **Adresse** [-kolonnen](../working-with-tables.md#columns) av **Personer**-tabellen:<br><ul><li>Måler lengden på hver streng.</li><li>Returnerer en tabell med én kolonne som inneholder lengden på hver streng.</li> |<style> img { max-width: none } </style> ![](media/function-len/people-table-len.png) |
| **Len( [ "Hello"; "to the"; "World"; "" ] )** |I **[Verdi](function-value.md)** -kolonnen i den linjebundne tabellen:<br><ul><li>Måler lengden på hver streng.</li><li>Returnerer en tabell med én kolonne som inneholder lengden på hver streng.</li> |![](media/function-len/people-table-len-inline.png) |

