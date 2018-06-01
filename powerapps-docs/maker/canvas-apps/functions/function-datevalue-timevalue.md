---
title: Funksjonene DateValue, TimeValue og DateTimeValue | Microsoft Docs
description: Referanseinformasjon, inkludert syntaks og eksempler, for funksjonene DateValue, TimeValue og DateTimeValue i PowerApps
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
ms.openlocfilehash: 9fd392666fd79ec1342e736fe772416d435c0b77
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/22/2018
ms.locfileid: "30996387"
---
# <a name="datevalue-timevalue-and-datetimevalue-functions-in-powerapps"></a>Funksjonene DateValue, TimeValue og DateTimeValue i PowerApps
Konverterer en dato, et klokkeslett eller begge deler i en streng til en dato/klokkeslett-verdi.

## <a name="description"></a>Beskrivelse
**DateValue**-funksjonen konverterer en datostreng (for eksempel "10/01/2014") til en dato/klokkeslett-verdi.

**TimeValue**-funksjonen konverterer en tidsstreng (for eksempel "12:15 PM") til en dato/klokkeslett-verdi.

**DateTimeValue**-funksjonen konverterer en dato- og tidsstreng (for eksempel "January 10, 2013 12:13 AM") til en dato/klokkeslett-verdi.

**DateValue**-funksjonen ignorerer all informasjon om klokkeslett i datostrengen, og **TimeValue**-funksjonen ignorerer all datoinformasjon i klokkeslettstrengen.

Som standard brukes språket til nåværende bruker, men du kan overstyre dette for å påse at strengene tolkes riktig. For eksempel tolkes "10/1/1920" som 1.<sup>oktober</sup> i engelsk språkmodus og som 10.<sup>januar</sup> i fransk språkmodus.

Datoer må være i ett av disse formatene:

* MM/DD/ÅÅÅÅ
* DD/MM/ÅÅÅÅ
* DD Måned ÅÅÅÅ
* Måned DD, ÅÅÅÅ

Se funksjonene **[Date](function-date-time.md)**  og **[Time](function-date-time.md)** for å konvertere fra de numeriske verdiene dato, måned, år, time, minutt og sekund.

Se også [Slik arbeider du med datoer og klokkeslett](../show-text-dates-times.md) for mer informasjon.

Hvis du vil konvertere tall, kan du se **[Value](function-value.md)**-funksjonen.

## <a name="syntax"></a>Syntaks
**DateValue**( *String* [, *Language* ])<br>**DateTimeValue**( *String* [, *Language* ])<br>**TimeValue**( *String* [, *Language* ])

* *String* – obligatorisk.  En tekststreng som inneholder en dato, et klokkeslett eller en kombinasjon av dato og klokkeslett.
* *Language* – valgfritt.  En språklinje, av den typen som returneres av de to første tegnene i **[Language](function-language.md)**-funksjonen.  Hvis språk ikke er angitt, brukes språket for den nåværende brukeren.  

## <a name="examples"></a>Eksempler
### <a name="datevalue"></a>DateValue
Hvis du for eksempel skriver inn **10/11/2014** i en kontroll for tekstinndata med navnet **Startdato**, og deretter angir **[Tekst](../controls/properties-core.md)**-egenskapen for en etikett til denne funksjonen:

* **Text(DateValue(Startdate.Text), DateTimeFormat.LongDate)**
  
    Etiketten viser **Lørdag 11. oktober, 2014** hvis datamaskinen er konfigurert med **engelsk** som nasjonal innstilling.
  
    > [!NOTE]
> Du kan bruke flere alternativer i tillegg til **LongDateTime**, med **DateTimeFormat**-parameteren. Hvis du vil vise en liste over disse alternativene, skriver du inn parameteren i funksjonsboksen, etterfulgt av et utropstegn.
* **Text(DateValue(Startdate.Text, "fr"), DateTimeFormat.LongDate)**
  
    Etiketten viser **Mandag 10. november 2014**.

Hvis du gjorde det samme for **20. oktober 2014**:

* **DateDiff(DateValue(Startdate.Text), Today())**
  
    Hvis datamaskinen er konfigurert med **engelsk** som språk, viser etiketten **9**, som angir antall dager mellom 11. oktober og 20. oktober. **[DateDiff](function-dateadd-datediff.md)**-funksjonen kan også vise differansen i måneder, kvartaler eller år.

### <a name="datetimevalue"></a>DateTimeValue
Hvis du skriver inn **10/11/2014 1:50:24.765 PM** i en kontroll for tekstinndata med navnet **Start**, og deretter angir **[Tekst](../controls/properties-core.md)**-egenskapen for en etikett til denne funksjonen:

* **Text(DateTimeValue(Start.Text), DateTimeFormat.LongDateTime)**
  
    Etiketten viser **Lørdag 11 oktober 2014 1:50:24 PM** hvis datamaskinen er konfigurert med «engelsk» som nasjonal innstilling.
  
    > [!NOTE]
> Du kan bruke flere alternativer i tillegg til **LongDateTime**, med **DateTimeFormat**-parameteren. Hvis du vil vise en liste over disse alternativene, skriver du inn parameteren i funksjonsboksen, etterfulgt av et utropstegn.
* **Text(DateTimeValue(Start.Text, "fr"), DateTimeFormat.LongDateTime)**
  
    Etiketten viser **Mandag 10. november 2014 1:50:24 PM**.
* **Text(DateTimeValue(Start.Text), "dddd, mmmm dd, yyyy hh:mm:ss.fff AM/PM")**
  
    Etiketten viser **Lørdag 11.oktober 2014 01:50:24:765 PM** hvis datamaskinen er konfigurert med **engelsk** som nasjonal innstilling.
  
    Alternativt kan du angi **hh:m:ss.f** eller **hh:mm:ss.ff** for å runde av tiden til nærmeste tidels eller hundredels sekund.

### <a name="timevalue"></a>TimeValue
Navngi en kontroll for tekstinndata som **FinishedAt**, og angi **[Tekst](../controls/properties-core.md)**-egenskapen for en etikett til denne funksjonen:

**If(TimeValue(FinishedAt.Text)<TimeValue("5:00:00.000 PM"), «You made it!», «Too late!»)**

* Hvis du skriver inn **4:59:59.999 PM** i **FinishedAt**-kontrollen, viser etiketten «You made it!»
* Hvis du skriver inn **5:00:00.000 PM** i **FinishedAt**-kontrollen, viser etiketten «Too late!»

