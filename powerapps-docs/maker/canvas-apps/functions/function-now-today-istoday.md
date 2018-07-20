---
title: Funksjonene Now, Today og IsToday | Microsoft Docs
description: Referanseinformasjon for Now-, Today- og IsToday-funksjonene i PowerApps, inkludert syntaks og eksempler
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 06/09/2018
ms.author: gregli
ms.openlocfilehash: 7b0b046c4c18f2f0bbbb8afd63a33aca2c46b340
ms.sourcegitcommit: dfa0e1a7981814e15e6ca4720e2a5f930e859db1
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 07/13/2018
ms.locfileid: "39014309"
---
# <a name="now-today-and-istoday-functions-in-powerapps"></a>Funksjonene for Now, Today, og IsToday i PowerApps
Returnerer gjeldende dato og klokkeslett, og tester om en dato/klokkeslett-verdi er i dag.

## <a name="description"></a>Beskrivelse
**Now**-funksjonen returnerer gjeldende dato og klokkeslett som en dato/klokkeslett-verdi.

**Today**-funksjonen returnerer gjeldende dato og klokkeslett som en dato/klokkeslett-verdi. Klokkeslettdelen er midnatt. **Today** har samme verdi hele døgnet, fra midnatt i dag til midnatt i morgen.

**IsToday**-funksjonen tester om en dato/klokkeslett-verdi er mellom midnatt i dag og midnatt i morgen. Denne funksjonen returnerer en boolsk (**SANN** eller **USANN**) verdi.

Alle disse funksjonene fungerer med lokal tid for gjeldende bruker.

Hvis du vil ha mer informasjon, kan du se [Slik arbeider du med datoer og klokkeslett](../show-text-dates-times.md).

## <a name="volatile-functions"></a>Flyktige funksjoner
**NOW** og **TODAY** er flyktige funksjoner.  Hver gang en av disse funksjonene evalueres returnerer den en annen verdi.  

En flyktig funksjon returnerer en annen verdi når den brukes i en formel for dataflyt, hvis formelen den viser, ser ut til å være evaluert på nytt.  Hvis ingenting annet endres i formelen, vil den ha samme verdi i hele kjøringen av appen.

En etikett med **Label1.Text = Now()** vil for eksempel ikke endres mens appen er aktiv.  Å bare lukke og åpne appen vil resultere i en ny verdi.

Funksjonen vil evalueres på nytt hvis det er en del av en formel der noe annet er endret.  Hvis vi for eksempel endrer eksemplet til å omfatte en glidebryter med **Label1.Text = DateAdd(Now(), Slider1.Value, minutter)**, blir gjeldende klokkeslett hentet hver gang verdien for glidebryteren endres og etikettens tekstegenskapen evalueres på nytt.

Når de brukes i en [virkemåteformel](../working-with-formulas-in-depth.md), blir flyktige funksjoner evaluert hver gang virkemåteformelen evalueres.  Nedenfor finner du et eksempel.

## <a name="syntax"></a>Syntaks
**Now**()

**Today**()

**IsToday**( *DateTime* )

* *DateTime* – nødvendig.  Dato/klokkeslett-verdien som skal testes.

## <a name="examples"></a>Eksempler
Gjeldende klokkeslett for eksemplene i denne delen er **3:59 AM** den **12. feb. 2015**, og språket er **EN-US**.

| Formel | Beskrivelse | Resultat |
| --- | --- | --- |
| **Text( Now(), "mm/dd/yyyy hh:mm:ss" )** |Henter gjeldende dato og klokkeslett, og viser dem som en streng. |«02/12/2015 03:59:00» |
| **Text( Today(), "mm/dd/yyyy hh:mm:ss" )** |Henter bare gjeldende dato, lar klokkeslettdelen stå som midnatt, og viser dette som en streng. |«02/12/2015 00:00:00» |
| **IsToday( Now() )** |Tester om gjeldende dato og klokkeslett er mellom midnatt i dag og midnatt i morgen. |**SANN** |
| **IsToday( Today() )** |Tester om gjeldende dato er mellom midnatt i dag og midnatt i morgen. |**SANN** |
| **Text( DateAdd( Now(), 12 ), "mm/dd/yyyy hh:mm:ss" )** |Henter gjeldende dato og klokkeslett, legger 12 dager til resultatet, og viser det som en streng. |«02/24/2015 03:59:00» |
| **Text( DateAdd( Today(), 12 ), "mm/dd/yyyy hh:mm:ss" )** |Henter gjeldende dato, legger 12 dager til resultatet, og viser det som en streng. |«24/02/2015 00:00:00» |
| **IsToday( DateAdd( Now(), 12 ) )** |Tester om gjeldende dato og klokkeslett, pluss 12 dager, er mellom midnatt i dag og midnatt i morgen. |**USANN** |
| **IsToday( DateAdd( Today(), 12 ) )** |Tester om gjeldende dato, pluss 12 dager, er mellom midnatt i dag og midnatt i morgen. |**usann** |

#### <a name="display-a-clock-that-updates-in-real-time"></a>Vis en klokke som oppdateres i sanntid

1. Legg til en **[Tidtaker](../controls/control-timer.md)**-kontroll, angi egenskapen for **Varighet** til **1000**, og angi deretter **Gjenta**-egenskapen til **SANN**.

    Tidtakeren kjøres i ett sekund, startes automatisk på nytt og fortsetter dette mønstret. 

1. Angi egenskapen for **OnTimerEnd** til denne formelen:

    **Set( CurrentTime, Now() )**

    Når tidtakeren starter på nytt (etter et sekund), angir formelen den globale variabelen **CurrentTime** til gjeldende verdi for **Now**-funksjonen.

    ![En skjerm som inneholder en tidtakerkontroll med formelen OnTimerEnd = (CurrentTime, Now())](media/function-now-today-istoday/now-set-currenttime.png)

1. Legg til en **[Etikett](../controls/control-text-box.md)**, og angi **Tekst**-egenskapen til denne formelen:

    **Text( CurrentTime, LongTime24 )**

    Bruk **[Text](function-text.md)**-funksjonen til å formatere datoen og klokkeslettet slik du ønsker, eller angi denne egenskapen til bare **CurrentTime** for å vise timer og minutter, men ikke sekunder.

    ![En skjerm som viser en etikett med Tekst-egenskapen satt til Text( CurrentTime, LongTime24)](media/function-now-today-istoday/now-use-currenttime.png)

1. Forhåndsvis appen ved å trykke på F5, og start deretter tidtakeren ved å klikke eller trykke på den.

    Etiketten viser kontinuerlig det gjeldende klokkeslettet, helt ned til sekundet.

    ![Fire skjermer som viser fire tidsverdier (13:50:22, 13:50:45, 13:51:03 og 13:51:25)](media/function-now-today-istoday/now-four-times.png)

1. Angi tidtakerens egenskap for **AutoStart** til **SANN** og **Synlig**-egenskapen til **USANN**.

    Tidtakeren er usynlig og starter automatisk.

1. Angi skjermens **[OnStart](../controls/control-screen.md)**-egenskap slik at variabelen **CurrentTime** har en gyldig verdi, som i dette eksemplet:

    **Set(CurrentTime, Now())**

    Etiketten vises så snart appen starter (før tidtakeren kjører et fullstendig sekund).
