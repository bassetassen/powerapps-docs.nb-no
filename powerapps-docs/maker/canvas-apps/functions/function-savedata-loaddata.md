---
title: Funksjonene SaveData og LoadData| Microsoft Docs
description: Referanseinformasjon for funksjonene SaveData og LoadData i PowerApps, inkludert syntaks
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 01/31/2019
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: e716de7a3551e2195d3f3459540a6f68acb4fd51
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/07/2019
ms.locfileid: "71992276"
---
# <a name="savedata-and-loaddata-functions-in-powerapps"></a>Funksjonene SaveData og LoadData i PowerApps
Lagrer og laster inn en [samling](../working-with-data-sources.md#collections) på nytt.

## <a name="description"></a>Beskrivelse
**SaveData**-funksjonen lagrer en samling under et navn, for senere bruk.  

**LoadData**-funksjonen laster inn en samling på nytt ut fra navnet som tidligere ble lagret med **SaveData**. Du kan ikke bruke denne funksjonen til å laste inn en samling fra en annen kilde.  

Bruk disse funksjonene til å forbedre program oppstarts ytelsen ved å bufre data i **[appen. OnStart](../controls/control-screen.md#additional-properties)** formel ved første kjøring og deretter laste inn den lokale hurtig bufferen på nytt ved etterfølgende kjøringer. Du kan også bruke disse funksjonene til å legge til [enkle frakoblede funksjoner](../offline-apps.md) i appen din.

Du kan ikke bruke disse funksjonene i en nett leser, enten når du redigerer appen i PowerApps Studio eller når du kjører appen i web spilleren. Hvis du vil teste appen, kan du kjøre den i PowerApps Mobile på en iPhone-eller Android-enhet.

Disse funksjonene er begrenset av mengden tilgjengelig app-minne fordi de opererer på en samling i minnet. Tilgjengelig minne kan variere avhengig av enheten og operativ systemet, minnet som PowerApps-spilleren bruker, og kompleksiteten til appen i henhold til skjermer og kontroller. Hvis du lagrer mer enn noen få megabyte med data, kan du teste appen med forventede scenarioer på enhetene som du forventer at appen skal kjøre. Du bør vanligvis forvente å ha mellom 30 og 70 megabyte av tilgjengelig minne.  

**LoadData** oppretter ikke samlingen. Funksjonen fyller bare opp en eksisterende samling. Du må først opprette samlingen med riktige [kolonner](../working-with-tables.md#columns) ved hjelp av **[Collect](function-clear-collect-clearcollect.md)** . De lastede dataene legges til i samlingen. Bruk **[Clear](function-clear-collect-clearcollect.md)** -funksjonen først hvis du vil starte med en tom samling.

Dataene krypteres og lagres på en privat plassering på den lokale enheten, isolert fra andre brukere og andre apper.

## <a name="syntax"></a>Syntaks
**SaveData**( *Samling*, *Navn* )<br>**LoadData**( *Samling*, *Navn* [, *IgnoreNonexistentFile* ])

* *Samling* – obligatorisk.  Samlingen som skal lagres eller lastes inn.
* *Navn* – obligatorisk.  Navnet på lagringen. Du må bruke samme navn for å lagre og laste inn det samme settet med data. Navneområdet er ikke delt med andre apper eller brukere.
* *IgnoreNonexistentFile* – valgfritt. Boolsk (**sann**/**usann**) verdi som angir om **LoadData**-funksjonen skal vise eller ignorere feil når den ikke kan finne en samsvarende fil. Hvis du angir **usann**, vises feilene. Hvis du angir **sann**, ignoreres feilene, noe som er nyttig når du er frakoblet. **SaveData** kan opprette en fil hvis enheten er frakoblet (altså hvis **Connection.Connected**-statusen er **usann**).

## <a name="examples"></a>Eksempler

| Formel | Beskrivelse | Resultat |
| --- | --- | --- |
| @no__t – 0If (tilkobling. tilkoblet, ClearCollect (LocalTweets, Twitter. SearchTweet («PowerApps», {maxResults: 100})), LoadData (LocalTweets, "Tweeter", True)) ** |Hvis enheten er koblet til, lastes samlingen LocalTweets inn fra Twitter-tjenesten. Ellers lastes samlingen inn fra den lokale filbufferen. |Innholdet gjengis uansett enheten er tilkoblet eller frakoblet. |
| **SaveData(LocalTweets, «Tweeter»)** |Lagre samlingen LocalTweets som en lokal filbuffer på enheten. |Dataene lagres lokalt slik at **LoadData** kan laste det inn i en samling. |

