---
title: Funksjonene DateAdd, DateDiff og TimeZoneOffset | Microsoft Docs
description: Referanseinformasjon for funksjonene DateAdd, DateDiff og TimeZoneOffset i PowerApps, inkludert syntaks og eksempler
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 05/23/2017
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 8108dbc1c78ba57e989f7bebeb8bd0f42f696360
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/07/2019
ms.locfileid: "71985136"
ms.PowerAppsDecimalTransform: true
---
# <a name="dateadd-datediff-and-timezoneoffset-functions-in-powerapps"></a>Funksjonene DateAdd, DateDiff og TimeZoneOffset i PowerApps
Legger til eller finner differansen i dato/klokkeslett-verdiene og konverterer mellom lokal tid og UTC.

## <a name="description"></a>Beskrivelse
**DateAdd**-funksjonen legger til et antall enheter i en dato/klokkeslett-verdi. Resultatet er en ny dato/klokkeslett-verdi. Du kan også trekke fra et antall enheter i en dato/klokkeslett-verdi ved å angi en negativ verdi.

**DateDiff**-funksjonen returnerer differansen mellom to dato/klokkeslett-verdier. Resultatet er et antall enheter.

For begge funksjonene kan enhetene være **Milliseconds**, **Seconds**, **Minutes**, **Hours**, **Days**, **Months**, **Quarters** eller **Years**.  Begge funksjonene bruker som standard **Days** som enheter.

**TimeZoneOffset**-funksjonen returnerer antall minutter mellom brukerens lokaltid og UTC (universaltid).   

Du kan bruke **DateAdd** sammen med **TimeZoneOffset** til å konvertere mellom brukerens lokaltid og UTC (universaltid).  Når du legger til **TimeZoneOffset** konverteres lokaltid til UTC, og når du trekker fra differansen (legger til med motsatt fortegn), konverteres UTC til lokaltid.

Se også [data typene date, time og datetime](/data-types#date-time-and-datetime) og [arbeide med datoer og klokkeslett](../show-text-dates-times.md) for mer informasjon.

## <a name="syntax"></a>Syntaks
**DateAdd**( *DateTime*; *Addition* [; *Units* ] )

* *DateTime* – obligatorisk. Dato/klokkeslett-verdier som funksjonen skal arbeide med.
* *Addition* – obligatorisk. Tall, i *Units*, som skal legges til *DateTime*.
* *Units* – valgfritt. Typen *enheter* som skal legges til: **Millisekunder**, **sekunder**, **minutter**, **timer**, **dager**, **måneder**, **kvartaler**eller **år**.  Hvis enheten ikke er angitt, brukes **Days**.

**DateDiff**( *StartDateTime*; *EndDateTime* [; *Units* ] )

* *StartDateTime* – obligatorisk. Dato/klokkeslett-verdi for starttid.
* *EndDateTime* – obligatorisk. Dato/klokkeslett-verdi for sluttid.
* *Units* – valgfritt. Typen *enheter* som skal legges til: **Millisekunder**, **sekunder**, **minutter**, **timer**, **dager**, **måneder**, **kvartaler**eller **år**.  Hvis enheten ikke er angitt, brukes **Days**.

**TimeZoneOffset**( [ *DateTime* ] )

* *DateTime* – valgfritt.  Dato/klokkeslett-verdien som tidsforskjellen skal returneres for.  Som standard brukes gjeldende dato/klokkeslett.

## <a name="examples"></a>Eksempler
I alle disse eksemplene antas det at gjeldende dato og klokkeslett er **15. juli 2013 kl. 13:02**.

### <a name="simple-dateadd"></a>Enkel DateAdd

| Formel | Beskrivelse | Resultat |
| --- | --- | --- |
| **Text( DateAdd( Now(); 3 );<br>"dd-mm-yyyy hh:mm" )** |Legger til tre dager (standardenheter) til gjeldende dato og klokkeslett. |"18-07-2013 13:02" |
| **Text( DateAdd( Now(); 4; Hours );<br>"dd-mm-yyyy hh:mm" )** |Legg til fire timer til gjeldende dato og klokkeslett. |"15-07-2013 17:02" |
| **Text( DateAdd( Today(); 1; Months );<br>"dd-mm-yyyy hh:mm" )** |Legger til én måned til gjeldende dato, uten klokkeslett, ettersom **Today** ikke returnerer noen klokkeslett-komponent. |"15-08-2013 00:00" |
| **Text( DateAdd( Now(); &#8209;;30; Minutes );<br>"dd-mm-yyyy hh:mm" )** |Trekker fra 30 minutter fra gjeldende dato og klokkeslett. |"15-07-2013 12:32" |

### <a name="simple-datediff"></a>Enkel DateDiff

| Formel | Beskrivelse | Resultat |
| --- | --- | --- |
| **DateDiff( Now(); DateValue("1/1/2014") )** |Returnerer differansen mellom de to enhetene i standardenheten **Days** |170 |
| **DateDiff( Now(); DateValue("1/1/2014"); Months )** |Returnerer differansen mellom de to verdiene i **Months** |6 |
| **DateDiff( Now(); Today(); Minutes )** |Returnerer differansen mellom gjeldende dato/klokkeslett og gjeldende dato (uten klokkeslett) i minutter.  Siden **Now** er senere enn **Today**, vil resultatet være negativt. |–782 |

### <a name="converting-to-utc"></a>Slik konverterer du til UTC
Hvis du vil konvertere til UTC, (Coordinated Universal Time), kan du legge til **TimeZoneOffset** for det gitte klokkeslettet.  

Anta for eksempel at gjeldende dato og klokkeslett er **15. juli 2013 kl. 13:02** i tidssonen Stillehavskysten (PDT, UTC–7).  For å fastslå gjeldende klokkeslett i UTC, bruker du følgende:

* **DateAdd (Now(); TimeZoneOffset(); Minutes)**

**TimeZoneOffset** bruker gjeldende klokkeslett som standard, så du ikke trenger å sende det som et argument.

Hvis du vil se resultatet, kan du bruke **Text**-funksjonen med formatet *dd-mm-åååå tt:mm*, som vil returnere **15-07-2013 20:02**.

### <a name="converting-from-utc"></a>Slik konverterer du fra UTC
Hvis du vil konvertere fra UTC, trekker du fra **TimeZoneOffset** (ved å legge den til med motsatt fortegn) fra det gitte klokkeslettet.

Anta for eksempel at UTC-datoen og klokkeslettet **15. juli 2013 kl. 20:02** er lagret i en variabel med navnet **StartTime**. Hvis du vil justere tidspunktet for brukerens tidssone, bruker du følgende:

* **DateAdd (Start Time, &minus;TimeZoneOffset (Start Time), minutter)**

Legg merke til minustegnet før **TimeZoneOffset** for å trekke fra forskyvningen i stedet for å legge den til.

Hvis du vil se resultatet, kan du bruke **Text**-funksjonen med formatet *dd-mm-åååå tt:mm*, som vil returnere **15-07-2013 13:02**.

