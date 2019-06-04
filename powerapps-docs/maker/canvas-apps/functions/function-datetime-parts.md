---
title: Funksjonene Day, Month, Year, Hour, Minute, Second og Weekday | Microsoft Docs
description: Referanseinformasjon, blant annet syntaks og eksempler, for funksjonene Day, Month, Year, Hour, Minute, Second og Weekday i PowerApps
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 10/25/2016
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: ab824432833614ba5b2002375a79e7899a8d7277
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/23/2019
ms.locfileid: "61551265"
ms.PowerAppsDecimalTransform: true
---
# <a name="day-month-year-hour-minute-second-and-weekday-functions-in-powerapps"></a>Funksjonene Day, Month, Year, Hour, Minute, Second og Weekday i PowerApps
Returnerer enkeltkomponenter for en dato/klokkeslett-verdi.

## <a name="description"></a>Beskrivelse
**Day**-funksjonen returnerer dagskomponenten for en dato/klokkeslett-verdi fra 1 til 31.

**Month**-funksjonen returnerer månedskomponenten for en dato/klokkeslett-verdi fra 1 til 12.

**Year**-funksjonen returnerer årskomponenten for en dato/klokkeslett-verdi som begynner med 1900.

**Hour**-funksjonen returnerer timekomponenten for en dato/klokkeslett-verdi fra 0 (00:00) til 23 (23:00).

**Minute**-funksjonen returnerer minuttkomponenten for en dato/klokkeslett-verdi fra 0 til 59.

**Second**-funksjonen returnerer sekundkomponenten for en dato/klokkeslett-verdi fra 0 til 59.

**Weekday**-funksjonen returnerer ukedagen for en dato/klokkeslett-verdi.  Som standard returneres resultatet i området 1 (søndag) til 7 (lørdag).  Du kan angi et annet område med en Microsoft Excel Weekday-funksjonskode eller en StartOfWeek-opplistingsverdi:

| Excel-kode | StartOfWeek-opplisting | Beskrivelse |
| --- | --- | --- |
| **1**, **17** |**StartOfWeek.Sunday** |Tallene 1 (søndag) til og med 7 (lørdag).  Standard. |
| **2**, **11** |**StartOfWeek.Monday** |Tallene 1 (mandag) til og med 7 (søndag). |
| **3** |**StartOfWeek.MondayZero** |Tallene 0 (mandag) til og med 6 (søndag). |
| **12** |**StartOfWeek.Tuesday** |Tallene 1 (tirsdag) til og med 7 (mandag). |
| **13** |**StartOfWeek.Wednesday** |Tallene 1 (onsdag) til og med 7 (tirsdag). |
| **14** |**StartOfWeek.Thursday** |Tallene 1 (torsdag) til og med 7 (onsdag). |
| **15** |**StartOfWeek.Friday** |Tallene 1 (fredag) til og med 7 (torsdag). |
| **16** |**StartOfWeek.Saturday** |Tallene 1 (lørdag) til og med 7 (fredag). |

Alle funksjoner returnerer et tall.

Hvis du vil ha mer informasjon, kan du se [Slik arbeider du med datoer og klokkeslett](../show-text-dates-times.md).

## <a name="syntax"></a>Syntaks
**Day**( *DateTime* )<br>**Month**( *DateTime* )<br>**Year**( *DateTime* )<br>**Hour**( *DateTime* )<br>**Minute**( *DateTime* )<br>**Second**( *DateTime* )

* *DateTime* – obligatorisk.  Dato/klokkeslett-verdi til å arbeide på.  

**Weekday**( *DateTime* [; *WeekdayFirst* ] )<br>

* *DateTime* – obligatorisk.  Dato/klokkeslett-verdi til å arbeide på. 
* *WeekdayFirst* – valgfritt.  Excel-kode som angir hvilken dag som starter uken.  Hvis ikke angitt, brukes 1 (søndag først).

## <a name="examples"></a>Eksempler
I følgende eksempel er gjeldende klokkeslett **15:59:37** **torsdag 09. april 2015**.

| Formel | Beskrivelse | Resultat |
| --- | --- | --- |
| **Year(&nbsp;Now()&nbsp;)** |Returnerer årskomponenten for gjeldende dato og klokkeslett. |2015 |
| **Month(&nbsp;Now()&nbsp;)** |Returnerer månedskomponenten for gjeldende dato og klokkeslett. |4 |
| **Day(&nbsp;Now()&nbsp;)** |Returnerer dagskomponenten for gjeldende dato og klokkeslett. |9 |
| **Hour(&nbsp;Now()&nbsp;)** |Returnerer timekomponenten for gjeldende dato og klokkeslett. |15 |
| **Minute(&nbsp;Now()&nbsp;)** |Returnerer minuttkomponenten for gjeldende dato og klokkeslett. |59 |
| **Second(&nbsp;Now()&nbsp;)** |Returnerer minuttkomponenten for gjeldende dato og klokkeslett. |37 |
| **Weekday(&nbsp;Now()&nbsp;)** |Returnerer ukedagkomponenten for gjeldende dato og klokkeslett, ved å bruke søndag som standard start på uken. |5 |
| **Weekday(&nbsp;Now();&nbsp;14&nbsp;)** |Returnerer ukedagkomponenten for gjeldende dato og klokkeslett, ved å bruke en Excel-kode til å angi torsdag som start på uken. |1 |
| **Weekday(&nbsp;Now();&nbsp;StartOfWeek.Wednesday&nbsp;)** |Returnerer ukedagkomponenten for gjeldende dato og klokkeslett, ved å bruke en **StartOfWeek**-opplisting til å angi onsdag som start på uken. |2 |

