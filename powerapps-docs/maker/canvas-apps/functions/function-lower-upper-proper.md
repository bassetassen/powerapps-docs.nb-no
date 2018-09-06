---
title: Funksjonene Lower, Upper og Proper| Microsoft Docs
description: Referanseinformasjon for funksjonene Lower, Upper og Proper i PowerApps, inkludert syntaks og eksempler
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
ms.openlocfilehash: 72e1bd234a9cbccc24cf35723ee10bacd175b278
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/24/2018
ms.locfileid: "42865835"
---
# <a name="lower-upper-and-proper-functions-in-powerapps"></a>Funksjonene Lower, Upper og Proper i PowerApps
Konverterer bokstaver i en tekststreng slik at alle bokstavene blir små, alle blir store eller det blir en blanding av små og store bokstaver.

## <a name="description"></a>Beskrivelse
Funksjonene **Lower**, **Upper** og **Proper** konverterer små/store bokstaver i strenger.

* **Lower** konverterer alle store bokstaver til små bokstaver.
* **Upper** konverterer alle små bokstaver til store bokstaver.
* **Proper** konverterer den første bokstaven i hvert ord til en stor bokstav, og konverterer andre store bokstaver til små bokstaver.

Alle tre funksjonene ignorerer tegn som ikke er bokstaver.

Hvis du angir en enkelt streng, er returverdien den konverterte versjonen av strengen.  Hvis du angir en [enkeltkolonnetabell](../working-with-tables.md) som inneholder strenger, vil returverdien være en enkeltkolonnetabell med konverterte strenger. Hvis du har en flerkolonnetabell, kan du gjøre den om til en enkeltkolonnetabell, som beskrevet i [arbeid med tabeller](../working-with-tables.md).

## <a name="syntax"></a>Syntaks
**Lower**( *String* )<br>**Upper**( *String* )<br>**Proper**( *String* )

* *String* – obligatorisk. Strengen som skal konverteres.

**Lower**( *SingleColumnTable* )<br>**Upper**( *SingleColumnTable* )<br>**Proper**( *SingleColumnTable* )

* *SingleColumnTable* – obligatorisk. En enkeltkolonnetabell med strenger som skal konverteres.

## <a name="examples"></a>Eksempler
### <a name="single-string"></a>Enkelt streng
Eksemplene i denne delen bruker en kontroll for innskriving av tekst, kalt **Forfatter**, som sin [datakilde](../working-with-data-sources.md). Kontrollen inneholder strengen «E. E. CummINGS».

| Formel | Beskrivelse | Resultat |
| --- | --- | --- |
| **Lower(&nbsp;Author.Text&nbsp;)** |Konverterer alle store bokstaver i strengen til små bokstaver. |«e. e. cummings» |
| **Upper(&nbsp;Author.Text&nbsp;)** |Konverterer alle små bokstaver i strengen til store bokstaver. |«E. E. CUMMINGS» |
| **Proper(&nbsp;Author.Text&nbsp;)** |Konverterer den første bokstaven i hvert ord til store bokstaver hvis de er små, og konverterer alle store bokstaver til små bokstaver. |«E. E. Cummings» |

### <a name="single-column-table"></a>Tabell med én kolonne
Eksemplene i denne delen konverterer strenger fra **Adresse** [-kolonnen](../working-with-tables.md#columns) i **Personer**-datakilden, som inneholder disse dataene:

![](media/function-lower-upper-proper/people-table.png)

Hver formel returnerer en tabell med én kolonne som inneholder de konverterte strengene.

| Formel | Beskrivelse | Resultat |
| --- | --- | --- |
| **Lower( ShowColumns(&nbsp;People,&nbsp;"Address"&nbsp;) )** |Konverterer alle små bokstaver til store bokstaver. |<style> img { max-width:none; } </style> ![](media/function-lower-upper-proper/people-table-lower.png) |
| **Upper( ShowColumns(&nbsp;People,&nbsp;"Address"&nbsp;) )** |Konverterer alle små bokstaver til store bokstaver. |![](media/function-lower-upper-proper/people-table-upper.png) |
| **Upper( ShowColumns(&nbsp;People,&nbsp;"Address"&nbsp;) )** |Konverterer den første bokstaven i hvert ord til store bokstaver hvis de er små, og konverterer alle andre store bokstaver til små bokstaver. |![](media/function-lower-upper-proper/people-table-proper.png) |

### <a name="step-by-step-example"></a>Trinnvis veiledning – eksempel
1. Legg til en **[Tekstinndata](../controls/control-text-input.md)**-kontroll, og gi den navnet **Source**.
2. Legg til en etikett og angi **[Tekst](../controls/properties-core.md)**-egenskapen til denne formelen:<br>**Proper(Source.Text)**
3. Trykk på F5, og skriv deretter **VI ER BEST!** i **kilde**-boksen.<br>Etiketten viser **Vi er best!**

