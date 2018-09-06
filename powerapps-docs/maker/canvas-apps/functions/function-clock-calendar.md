---
title: Funksjonene Calendar og Clock | Microsoft Docs
description: Referanseinformasjon for funksjonene Calendar og Clock i PowerApps, inkludert syntaks og eksempler
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
ms.openlocfilehash: 6625df3f822462c86de1f720b7a310f5e516a6ca
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/24/2018
ms.locfileid: "42849875"
---
# <a name="calendar-and-clock-functions-in-powerapps"></a>Funksjonene Calendar og Clock i PowerApps
Henter informasjon om gjeldende nasjonale innstillinger for kalender og klokke.

## <a name="description"></a>Beskrivelse
Funksjonene **Calendar** og **Clock** er et sett med funksjoner som henter informasjon om gjeldende nasjonale innstillinger.

Du kan bruke disse funksjonene til å vise dato og klokkeslett på språket for gjeldende bruker.  Enkeltkolonnetabellene som returneres av funksjonene **Calendar** og **Clock**, kan brukes direkte med **[Element](../controls/properties-core.md)**-egenskapen til kontrollene Rullegardinliste og Listeboks.

| Funksjon | Beskrivelse |
| --- | --- |
| **Calendar.MonthsLong()** |Enkeltkolonnetabell som inneholder det fullstendige navnet for hver måned, begynner med «januar». |
| **Calendar.MonthsShort()** |Enkeltkolonnetabell som inneholder det forkortede navnet for hver måned, begynner med «jan» for januar. |
| **Calendar.WeekdaysLong()** |Enkeltkolonnetabell som inneholder det fullstendige navnet på hver ukedag, begynner med «søndag». |
| **Calendar.WeekdaysShort()** |Enkeltkolonnetabell som inneholder det forkortede navnet på hver ukedag, begynner med «søn» for søndag. |
| **Clock.AmPm()** |Enkeltkolonnetabell som inneholder den lange angivelsen med store bokstaver, «AM» og «PM».  Hvis språket bruker 24-timersklokke, vil tabellen være tom. |
| **Clock.AmPmShort()** |Enkeltkolonnetabell som inneholder den korte angivelsen med store bokstaver, «A» og «P».  Hvis språket bruker 24-timersklokke, vil tabellen være tom. |
| **Clock.IsClock24()** |Boolsk verdi som angir om en 24-timers klokke brukes for gjeldende nasjonale innstilling. |

Bruk **[Text](function-text.md)**-funksjonen til å formatere verdiene for dato og klokkeslett ved bruk av denne informasjonen.  **[Language](function-language.md)**-funksjonen returnerer gjeldende språk og områdekode.

## <a name="syntax"></a>Syntaks
**Calendar.MonthsLong**()

**Calendar.MonthsShort**()

**Calendar.WeekdaysLong**()

**Calendar.WeekdaysShort**()

**Clock.AmPm**()

**Clock.AmPmShort**()

**Clock.IsClock24**()

## <a name="examples"></a>Eksempler
1. Sett inn en rullegardinliste-kontroll.
2. Angi formelen for **[Element](../controls/properties-core.md)**-egenskaper til:
   
   * **Calendar.MonthsLong()**
3. Brukere av appen din kan nå velge en måned på sitt eget språk.  **MonthsLong** kan erstattes med hvilken som helst av enkeltkolonnetabellene som returneres av **Calendar** for å opprette velgere for ukedag og klokkeslett.

I USA, der **[Språk](function-language.md)** returnerer «en-US», returnerer **Kalender**-funksjonene følgende:

| Formel | Beskrivelse | Resultat |
| --- | --- | --- |
| **Calendar.MonthsLong()** |Returverdien inneholder det fullstendige navnet for hver måned, begynner med «januar». |[ «januar», «februar», «mars», «april», «mai», «juni», «juli», «august», «september», «oktober», «november», «desember» ] |
| **Calendar.MonthsShort()** |Returverdien inneholder det forkortede navnet for hver måned, begynner med «jan». |[ «jan», «feb», «mars», «apr», «mai», «juni», «juli», «aug», «sep», «okt», «nov», «des» ] |
| **Calendar.WeekdaysLong()** |Returverdien inneholder det fullstendige navnet på hver ukedag, begynner med «søndag». |[ «søndag», «mandag», «tirsdag», «onsdag», «torsdag», «fredag», «lørdag» ] |
| **Calendar.WeekdaysShort()** |Returverdien inneholder det forkortede navnet for hver ukedag, begynner med «søn». |[ «søn», «man», «tir», «ons», «tor», «fre», «lør» ] |
| **Clock.AmPm()** |Dette språket bruker en 12-timers klokke.  Den returnerte verdien inneholder den fullstendige angivelsen med store bokstaver, «AM» og «PM». |[ «AM», «PM» ] |
| **Clock.AmPmShort()** |Dette språket bruker en 12-timers klokke.  Den returnerte verdien inneholder den forkortede angivelsen med store bokstaver, «AM» og «PM». |[ «A», «P» ] |
| **Clock.IsClock24()** |Dette språket bruker en 12-timers klokke. |**usann** |

