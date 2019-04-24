---
title: Funksjonene SaveData og LoadData| Microsoft Docs
description: Referanseinformasjon for funksjonene SaveData og LoadData i PowerApps, inkludert syntaks
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 01/31/2019
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 3fb23fec6f6885a55b054889b90fed0c5efafd5e
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/23/2019
ms.locfileid: "61520494"
---
# <a name="savedata-and-loaddata-functions-in-powerapps"></a>Funksjonene SaveData og LoadData i PowerApps
Lagrer og laster inn en [samling](../working-with-data-sources.md#collections) på nytt.

## <a name="description"></a>Beskrivelse
**SaveData**-funksjonen lagrer en samling under et navn, for senere bruk.  

**LoadData**-funksjonen laster inn en samling på nytt ut fra navnet som tidligere ble lagret med **SaveData**. Du kan ikke bruke denne funksjonen til å laste inn en samling fra en annen kilde.  

Bruk disse funksjonene til å forbedre ytelsen for oppstart av appen ved å bufre data i den **[App.OnStart](../controls/control-screen.md#additional-properties)** formelen på en første kjøring og deretter laste inn den lokale hurtigbufferen ved senere kjøringer på nytt. Du kan også bruke disse funksjonene til å legge til [enkle frakoblede funksjoner](../offline-apps.md) i appen.

Du kan ikke bruke disse funksjonene i en nettleser, når du redigerer appen i PowerApps Studio, eller når du kjører appen i web-spiller. Hvis du vil teste appen din, kan du kjøre den i PowerApps Mobile på en iPhone eller Android-enheten.

Disse funksjonene er begrenset av mengden minne tilgjengelig app fordi de fungerer på en samling i minnet. Tilgjengelig minne kan variere avhengig av enheten og operativsystemet, minnet som bruker PowerApps-spiller og kompleksiteten til appen når det gjelder skjermer og kontroller. Hvis du lagrer mer enn et par MB med data, kan du teste appen din med forventede scenarier på enheter som du forventer at appen kan kjøre. Du bør generelt forvente å ha mellom 30 og 70 MB tilgjengelig minne.  

**LoadData** oppretter ikke samlingen. Funksjonen fyller bare opp en eksisterende samling. Du må først opprette samlingen med riktige [kolonner](../working-with-tables.md#columns) ved hjelp av **[Collect](function-clear-collect-clearcollect.md)**. Den innlastede data vil bli lagt til samlingen. Bruk den **[tydelig](function-clear-collect-clearcollect.md)** funksjonen først hvis du vil starte med en tom samling.

Dataene krypteres og lagres på en privat plassering på den lokale enheten, isolert fra andre brukere og andre apper.

## <a name="syntax"></a>Syntaks
**SaveData**( *Samling*, *Navn* )<br>**LoadData**( *Samling*, *Navn* [, *IgnoreNonexistentFile* ])

* *Samling* – obligatorisk.  Samlingen som skal lagres eller lastes inn.
* *Navn* – obligatorisk.  Navnet på lagringen. Du må bruke samme navn for å lagre og laste inn det samme settet med data. Navneområdet er ikke delt med andre apper eller brukere.
* *IgnoreNonexistentFile* – valgfritt. Boolsk (**sann**/**usann**) verdi som angir om **LoadData**-funksjonen skal vise eller ignorere feil når den ikke kan finne en samsvarende fil. Hvis du angir **usann**, vises feilene. Hvis du angir **sann**, ignoreres feilene, noe som er nyttig når du er frakoblet. **SaveData** kan opprette en fil hvis enheten er frakoblet (altså hvis **Connection.Connected**-statusen er **usann**).

## <a name="examples"></a>Eksempler

| Formel | Beskrivelse | Resultat |
| --- | --- | --- |
| **Hvis (tilkobling.tilkoblet, ClearCollect (LocalTweets, Twitter.SearchTweet («PowerApps», {maxResults: 100})), LoadData (LocalTweets, «Tweeter», SANN))** |Hvis enheten er koblet til, lastes samlingen LocalTweets inn fra Twitter-tjenesten. Ellers lastes samlingen inn fra den lokale filbufferen. |Innholdet gjengis uansett enheten er tilkoblet eller frakoblet. |
| **SaveData(LocalTweets, «Tweeter»)** |Lagre samlingen LocalTweets som en lokal filbuffer på enheten. |Dataene lagres lokalt slik at **LoadData** kan laste det inn i en samling. |

