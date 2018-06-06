---
title: Value-funksjonen| Microsoft Docs
description: Referanseinformasjon, inkludert syntaks, for Value-funksjonen i PowerApps
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
ms.openlocfilehash: ce377c87347b2ee027271b94eb623a58d7f58bd1
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/22/2018
ms.locfileid: "30997347"
---
# <a name="value-function-in-powerapps"></a>Value-funksjonen i PowerApps
Konverterer en tekststreng til et tall.

## <a name="description"></a>Beskrivelse
**Value**-funksjonen konverterer en streng med tekst som inneholder talltegn til en tallverdi. Bruk denne funksjonen når du trenger å utføre beregninger på tall som ble angitt som tekst av en bruker.

Forskjellige språk tolker **,** og **.** på forskjellige måter.  Som standard tolkes teksten på språket for den gjeldende brukeren.  Du kan angi språket som skal brukes, med en språkkode ved hjelp av de samme språkkodene som returneres av **[Language](function-language.md)**-funksjonen.

Merknader på formatet for strengen:

* Strengen kan ha valutasymbolet for gjeldende språk som prefiks.  Valutasymbolet ignoreres.  Valutasymboler for andre språk blir ikke ignorert.
* Strengen kan inneholde et prosenttegn (**%**) på slutten. Dette indikerer at det er en prosent.  Nummeret blir delt med 100 før det returneres.  Prosenter og valutasymboler kan ikke blandes.
* Strengen kan være i vitenskapelig notasjon, med 12 x 10<sup>3</sup> uttrykt som "12e3".

Hvis tallet ikke er i riktig format, returneres **verdien** som *tom*.

Hvis du vil konvertere verdier for dato og klokkeslett, kan du bruke funksjonene [**DateValue**](function-datevalue-timevalue.md), [**TimeValue**](function-datevalue-timevalue.md) eller [**DateTimeValue**](function-datevalue-timevalue.md).

## <a name="syntax"></a>Syntaks
**Value**( *String* [, *LanguageTag* ] )

* *String* – obligatorisk. Strengen som skal konverteres til en numerisk verdi.
* *LanguageTag* – valgfritt.  Språkkode der du vil dele opp strengen.  Hvis ikke angitt, brukes språket for den gjeldende brukeren.

## <a name="examples"></a>Eksempler
Brukeren som kjører disse formlene befinner seg i USA og har valgt engelsk som språket sitt.  **Language**-funksjonen returnerer en-US.

| Formel | Beskrivelse | Resultat |
| --- | --- | --- |
| **Value( "123.456" )** |Standardspråket for «en-US» brukes og bruker et punktum som desimaltegn. |123.456 |
| **Value( "123.456", "es-ES" )** |«es-ES» er språkkoden for spansk i Spania.  Et punktum er tusenskilletegnet i Spania. |123456 |
| **Value( "123,456" )** |Standardspråket for «en-US» brukes og bruker et komma som tusenskilletegn. |123456 |
| **Value( "123,456", "es-ES" )** |«es-ES» er språkkoden for spansk i Spania.  Et komma er desimalskilletegnet i Spania. |123.456 |
| **Value( "12.34%" )** |Prosenttegnet på slutten av strengen indikerer at dette er en prosent. |0.1234 |
| **Value( "$ 12.34" )** |Valutasymbolet for gjeldende språk blir ignorert. |12.34 |
| **Value( "24e3" )** |Vitenskapelig notasjon for 12 x 10<sup>3</sup>. |24000 |

