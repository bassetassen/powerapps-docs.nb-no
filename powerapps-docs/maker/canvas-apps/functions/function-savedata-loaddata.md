---
title: Funksjonene SaveData og LoadData| Microsoft Docs
description: Referanseinformasjon for funksjonene SaveData og LoadData i PowerApps, inkludert syntaks
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
ms.openlocfilehash: 5aa9992b9371724c77bcc1d2baf439bb2d7b9dab
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/24/2018
ms.locfileid: "42864331"
---
# <a name="savedata-and-loaddata-functions-in-powerapps"></a>Funksjonene SaveData og LoadData i PowerApps
Lagrer og laster inn en [samling](../working-with-data-sources.md#collections) på nytt.

## <a name="description"></a>Beskrivelse
**SaveData**-funksjonen lagrer en samling under et navn, for senere bruk.  

**LoadData**-funksjonen laster inn en samling på nytt ut fra navnet som tidligere ble lagret med **SaveData**. Du kan ikke bruke denne funksjonen til å laste inn en samling fra en annen kilde.  

**LoadData** oppretter ikke samlingen. Funksjonen fyller bare opp en eksisterende samling. Du må først opprette samlingen med riktige [kolonner](../working-with-tables.md#columns) ved hjelp av **[Collect](function-clear-collect-clearcollect.md)**.

Dataene krypteres og lagres på en privat plassering på den lokale enheten, isolert fra andre brukere og andre apper.  

## <a name="syntax"></a>Syntaks
**SaveData**( *Samling*, *Navn* )<br>**LoadData**( *Samling*, *Navn* [, *IgnoreNonexistentFile* ])

* *Samling* – obligatorisk.  Samlingen som skal lagres eller lastes inn.
* *Navn* – obligatorisk.  Navnet på lagringen. Du må bruke samme navn for å lagre og laste inn det samme settet med data. Navneområdet er ikke delt med andre apper eller brukere.
* *IgnoreNonexistentFile* – valgfritt. Boolsk (**sann**/**usann**) verdi som angir om **LoadData**-funksjonen skal vise eller ignorere feil når den ikke kan finne en samsvarende fil. Hvis du angir **usann**, vises feilene. Hvis du angir **sann**, ignoreres feilene, noe som er nyttig når du er frakoblet. **SaveData** kan opprette en fil hvis enheten er frakoblet (altså hvis **Connection.Connected**-statusen er **usann**).

## <a name="examples"></a>Eksempler

| Formel | Beskrivelse | Resultat |
| --- | --- | --- |
| **Hvis(Tilkobling.Tilkoblet, ClearCollect(LocalTweets, Twitter.SearchTweet(«PowerApps», {maxResults: 100})),LoadData(LocalTweets, «Tweeter», sann))** |Hvis enheten er koblet til, lastes samlingen LocalTweets inn fra Twitter-tjenesten. Ellers lastes samlingen inn fra den lokale filbufferen. |Innholdet gjengis uansett enheten er tilkoblet eller frakoblet. |
| **SaveData(LocalTweets, «Tweeter»)** |Lagre samlingen LocalTweets som en lokal filbuffer på enheten. |Dataene lagres lokalt slik at **LoadData** kan laste det inn i en samling. |

