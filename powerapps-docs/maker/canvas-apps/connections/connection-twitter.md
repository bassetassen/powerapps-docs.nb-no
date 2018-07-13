---
title: Oversikt over Twitter-tilkobling | Microsoft Docs
description: Slik kobler man til Twitter, går gjennom noen eksempler, og ser alle funksjonene
author: lancedMicrosoft
ms.service: powerapps
ms.topic: reference
ms.component: canvas
ms.date: 07/12/2017
ms.author: lanced
ms.openlocfilehash: 33bfc61200d10ca50b80e31fec2bef62044e4be7
ms.sourcegitcommit: 79b8842fb0f766a0476dae9a537a342c8d81d3b3
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 07/07/2018
ms.locfileid: "37899644"
---
# <a name="connect-to-twitter-from-powerapps"></a>Å koble til Twitter fra PowerApps
![Twitter](./media/connection-twitter/twittericon.png)

Med Twitter kan du legge ut og motta tweets, vise tidslinje, venner og følgere fra Twitter-kontoen din.

Du kan vise denne informasjonen i en etikett i appen. Du kan for eksempel legge til en inndata-tekstboks, be brukeren om å skrive inn tekst, og deretter legge til en knapp som «legger ut» tweeten. Du kan bruke lignende metoder for å få eller søke etter en tweet, og deretter vise teksten i en etikett eller Galleri-kontrollen i appen.

Dette emnet viser deg hvordan du oppretter Twitter-tilkoblingen og bruker Twitter-tilkoblingen i en app. Her finner du også en oversikt over de tilgjengelige funksjonene.

[!INCLUDE [connection-requirements](../../../includes/connection-requirements.md)]

## <a name="connect-to-twitter"></a>Å koble til Twitter
1. Åpne PowerApps, velg **Ny**, og opprett en **Tom app**. Velg oppsett for telefon eller nettbrett. Oppsettet for nettbrett gir deg et større arbeidsområde:  

   ![Å åpne en tom app](./media/connection-twitter/blank-app.png)
2. Klikk eller trykk på **Data**-fanen i den høyre ruten, og klikk eller trykk på **Legg til datakilde**.
3. Velg **Ny tilkobling**, og velg deretter **Twitter**:  

    ![Å koble til Twitter](./media/connection-twitter/addconnection.png)

    ![Å koble til Twitter](./media/connection-twitter/add-twitter.png)
4. Velg **Koble til**, oppgi påloggingsinformasjonen for Twitter, og velg deretter **Godkjenn app**.
5. Velg **Legg til datakilde**. Tilkoblingen din vises under **Datakilde**:  
    ![Å lukke Alternativer-ruten](./media/connection-twitter/twitterdatasource.png)

Twitter-tilkobling er opprettet og lagt til i appen din. Den er nå klar til å brukes.

## <a name="use-the-twitter-connection-in-your-app"></a>Å bruke Twitter-tilkoblingen i appen
### <a name="show-a-timeline"></a>Å vise en tidslinje
1. Velg **Galleri** på menyen **Sett inn**, og legg til noen av **Med tekst**-galleriene.
2. La oss ta en titt på noen tidslinjer:  

   * Hvis du vil vise tidslinjen til den gjeldende brukeren, angir du galleriets **[Element](../controls/properties-core.md)**-egenskap til følgende formler:

       `Twitter.HomeTimeline().TweetText`  
       `Twitter.HomeTimeline({maxResults:3}).TweetText`  
   * Hvis du vil vise tidslinjen til en annen bruker, angir du galleriets **[Element](../controls/properties-core.md)**-egenskap til følgende formel:  

       `Twitter.UserTimeline( *TwitterHandle* ).TweetText`

       Angi et Twitter-brukernavn i doble anførselstegn eller tilsvarende verdi. Skriv for eksempel inn `"satyanadella"` eller `"powerapps"` direkte i formeluttrykket.
   * Legg til en Tekstinndata-kontroll med navn **Tweep**, og angi standardegenskapen til `Tweep.Text`. Skriv inn et Twitter-brukernavn i tekstboksen Tweep `satyanadella` (uten anførselstegn og uten @-symbolet).

       Angi Elementer-egenskapen i Galleri-kontrollen til følgende formel:  

       `Twitter.UserTimeline(Tweep.Text, {maxResults:5}).TweetText`

       Galleri-kontrollen viser automatisk tweetene til Twitter-brukernavnet du skrev inn.

     > [!TIP]
     > Noen av disse formlene bruker argumentet **maxResults** for å vise *antallet* siste tweets på en tidslinje.
3. Angi galleriets **Element**-egenskap til `Twitter.HomeTimeline()`.

    Når galleriet er valgt, viser den høyre ruten alternativene for galleriet.
4. Velg **TweetText** fra den første listen, velg **TweetedBy** fra den andre listen, og velg **CreatedAt** fra den tredje listen.

    Galleriet viser nå verdiene til egenskapene du velger.

### <a name="show-followers"></a>Å vise følgere
1. La oss vise noen følgere ved bruk av et **Med tekst**-galleri:  

   * Hvis du vil vise følgerne til den gjeldende brukeren, angir du galleriets **[Element](../controls/properties-core.md)**-egenskap til følgende formel:  

       `Twitter.MyFollowers()`  
       `Twitter.MyFollowers({maxResults:3})`
   * Hvis du vil vise følgerne til andre brukere, angir du galleriets **[Element](../controls/properties-core.md)**-egenskap til følgende formel:  

       `Twitter.Followers( *TwitterHandle* )`

       Angi et Twitter-brukernavn i doble anførselstegn eller tilsvarende verdi. Skriv for eksempel inn `"satyanadella"` eller `"powerapps"` direkte i formeluttrykket.
   * Legg til en Tekstinndata-kontroll med navn **Tweep**, og angi standardegenskapen til `Tweep.Text`. Skriv inn et Twitter-brukernavn i tekstboksen Tweep `satyanadella` (uten anførselstegn og uten @-symbolet).

       Angi Elementer-egenskapen i Galleri-kontrollen til følgende formel:  

       `Twitter.Followers(Tweep.Text, {maxResults:5})`

       Galleri-kontrollen viser automatisk hvem som følger Twitter-brukernavnet du skrev inn.

     > [!TIP]
     > Noen av disse formlene bruker argumentet **maxResults** for å vise *antallet* siste tweets på en tidslinje.
2. Angi galleriets **Element**-egenskap til `Twitter.MyFollowers()`.

    Når galleriet er valgt, viser den høyre ruten alternativene for galleriet.
3. Velg **UserName** fra den andre listen, og velg **FullName** fra den tredje listen.

    Galleriet viser nå verdiene til egenskapene du velger.

### <a name="show-followed-users"></a>Å vise brukere med følgere
1. La oss vise noen brukere med følgere ved bruk av et **Med tekst**-galleri:  

   * Hvis du vil vise følgerne til den gjeldende brukeren, angir du galleriets **[Element](../controls/properties-core.md)**-egenskap til følgende formel:  

       `Twitter.MyFollowing()`  
       `Twitter.MyFollowing({maxResults:3})`
   * Hvis du vil vise følgerne til den gjeldende brukeren, angir du galleriets **[Element](../controls/properties-core.md)**-egenskap til følgende formel:

       `Twitter.Following( *TwitterHandle* )`

       Angi et Twitter-brukernavn i doble anførselstegn eller tilsvarende verdi. Skriv for eksempel inn `"satyanadella"` eller `"powerapps"` direkte i formeluttrykket.
   * Legg til en Tekstinndata-kontroll med navn **Tweep**, og angi standardegenskapen til `Tweep.Text`. Skriv inn et Twitter-brukernavn i tekstboksen Tweep `satyanadella` (uten anførselstegn og uten @-symbolet).

       Angi Elementer-egenskapen i Galleri-kontrollen til følgende formel:  

       `Twitter.Following(Tweep.Text, {maxResults:5})`

       Galleri-kontrollen viser automatisk de andre brukernavnene du følger.

     Når galleriet er valgt, viser den høyre ruten alternativene for galleriet.
2. Velg **Beskrivelse** fra **Body1**-listen, **UserName** fra **Heading1**-listen og **FullName** fra **Subtitle1**-listen.

    Galleriet viser nå verdiene til egenskapene du velger.

### <a name="show-information-about-a-user"></a>Å vise informasjon om en bruker
Legg til en etikett, og angi **[Tekst](../controls/properties-core.md)**-egenskapen til én av disse formlene:  

* `twitter.User( *TwitterHandle* ).Description`
* `twitter.User( *TwitterHandle* ).FullName`
* `twitter.User( *TwitterHandle* ).Location`
* `twitter.User( *TwitterHandle* ).UserName`
* `twitter.User( *TwitterHandle* ).FollowersCount`
* `twitter.User( *TwitterHandle* ).FriendsCount`
* `twitter.User( *TwitterHandle* ).Id`
* `twitter.User( *TwitterHandle* ).StatusesCount`

Angi et Twitter-brukernavn i doble anførselstegn eller tilsvarende verdi. Skriv for eksempel inn `"satyanadella"` eller `"powerapps"` direkte i formeluttrykket.

Du kan alternativt bruke en Tekstinndata-kontroll for å skrive inn et Twitter-brukernavn, akkurat som vi har gjort i dette emnet.

### <a name="search-tweets"></a>Å søke i tweets
1. Angi **[Element](../controls/properties-core.md)**-egenskapen ved bruk av et **Med tekst**-galleri, til den følgende formelen:  

    `Twitter.SearchTweet( *SearchTerm* ).TweetText`

    Angi en *SearchTerm* i doble anførselstegn eller tilsvarende verdi. Skriv for eksempel inn `"PowerApps"` eller `"microsoft"` direkte i formeluttrykket.

    Du kan alternativt bruke en **Tekstinndata**-kontroll for å skrive inn et Twitter-brukernavn, akkurat som vi har gjort i dette emnet.

    > [!TIP]
   > Vis de fem første resultatene ved bruk av maxResults:  

    `Twitter.SearchTweet(SearchTerm.Text, {maxResults:5}).TweetText`
2. Angi galleriets **Element**-egenskap til `Twitter.SearchTweet(SearchTerm.Text, {maxResults:5})`.

    Når galleriet er valgt, viser den høyre ruten alternativene for galleriet.
3. Velg **TweetText** fra den første listen, velg **TweetedBy** fra den andre listen, og velg **CreatedAt** fra den tredje listen.

    Galleriet viser nå verdiene til egenskapene du velger.

### <a name="send-a-tweet"></a>Slik sender man en tweet
1. Legg til en Tekstinndata-kontroll, og endre deretter navnet til **MyTweet**.
2. Legg til en knapp, og angi deretter **[OnSelect](../controls/properties-core.md)**-egenskapen til følgende formel:  
    `Twitter.Tweet({tweetText: MyTweet.Text})`
3. Trykk på F5, eller velg forhåndsvisningsknappen (![](./media/connection-twitter/preview.png)). Skriv inn tekst i **MyTweet**, og velg deretter knappen for å tweete ut teksten du skrev inn.
4. Trykk på ESC for å gå tilbake til standardarbeidsområdet.

## <a name="view-the-available-functions"></a>Se de tilgjengelige funksjonene
Denne tilkoblingen har følgende funksjoner:

| Funksjonsnavn | Beskrivelse |
| --- | --- |
| [UserTimeline](connection-twitter.md#usertimeline) |Denne handlingen henter en samling av de siste tweetene som ble lagt ut av den angitte brukeren |
| [HomeTimeline](connection-twitter.md#hometimeline) |Denne handlingen henter de siste tweetene og re-tweets på innlegg fra meg og mine følgere |
| [SearchTweet](connection-twitter.md#searchtweet) |Denne handlingen henter en samling av relevante tweets som samsvarer med en angitt spørring |
| [Følgere](connection-twitter.md#followers) |Denne handlingen henter brukere som følger den angitte brukeren |
| [MyFollowers](connection-twitter.md#myfollowers) |Denne handlingen henter brukere som følger meg |
| [Følger](connection-twitter.md#following) |Denne handlingen henter brukere som den angitte brukeren følger |
| [MyFollowing](connection-twitter.md#myfollowing) |Denne handlingen henter brukere som jeg følger |
| [Bruker](connection-twitter.md#user) |Denne handlingen henter detaljer om den angitte brukeren (for eksempel brukernavn, beskrivelse, følgere, telling og så videre) |
| [Tweet](connection-twitter.md#tweet) |Tweet |
| [OnNewTweet](connection-twitter.md#onnewtweet) |Utløser en arbeidsflyt når en ny tweet legges ut som samsvarer med søket |

### <a name="usertimeline"></a>UserTimeline
Denne handlingen henter brukerens tidslinje, og henter en samling av de siste tweetene som ble lagt ut av den angitte brukeren

#### <a name="input-properties"></a>Inndataegenskaper

| Navn | Datatype | Kreves | Beskrivelse |
| --- | --- | --- | --- |
| userName |streng |ja |Twitter-brukernavn |
| maxResults |heltall |nei |Maksimalt antall tweets som skal hentes, for eksempel {maxResults:5} |

#### <a name="output-properties"></a>Utdataegenskaper

| Egenskapsnavn | Datatype | Kreves | Beskrivelse |
| --- | --- | --- | --- |
| TweetText |streng |Ja | |
| TweetId |streng |Nei | |
| CreatedAt |streng |Nei | |
| RetweetCount |heltall |Ja | |
| TweetedBy |streng |Ja | |
| MediaUrls |matrise |Nei | |

### <a name="hometimeline"></a>HomeTimeline
Denne handlingen henter tidslinjen for Hjem, og henter de siste tweetene og re-tweets på innlegg fra meg og mine følgere

#### <a name="input-properties"></a>Inndataegenskaper

| Navn | Datatype | Kreves | Beskrivelse |
| --- | --- | --- | --- |
| maxResults |heltall |nei |Maksimalt antall tweets som skal hentes, for eksempel {maxResults:5} |

#### <a name="output-properties"></a>Utdataegenskaper

| Egenskapsnavn | Datatype | Kreves | Beskrivelse |
| --- | --- | --- | --- |
| TweetText |streng |Ja | |
| TweetId |streng |Nei | |
| CreatedAt |streng |Nei | |
| RetweetCount |heltall |Ja | |
| TweetedBy |streng |Ja | |
| MediaUrls |matrise |Nei | |

### <a name="searchtweet"></a>SearchTweet
Denne handlingen søker i tweets, og henter en samling av relevante tweet som samsvarer med en angitt spørring

#### <a name="input-properties"></a>Inndataegenskaper

| Navn | Datatype | Kreves | Beskrivelse |
| --- | --- | --- | --- |
| searchQuery |streng |ja |Spørringstekst (du kan bruke spørringsoperatorer som støttes av Twitter: http://www.twitter.com/search) |
| maxResults |heltall |nei |Maksimalt antall tweets som skal hentes, for eksempel {maxResults:5} |

#### <a name="output-properties"></a>Utdataegenskaper

| Egenskapsnavn | Datatype | Kreves | Beskrivelse |
| --- | --- | --- | --- |
| TweetText |streng |Ja | |
| TweetId |streng |Nei | |
| CreatedAt |streng |Nei | |
| RetweetCount |heltall |Ja | |
| TweetedBy |streng |Ja | |
| MediaUrls |matrise |Nei | |

### <a name="followers"></a>Følgere
Denne handlingen henter brukere som følger den angitte brukeren

#### <a name="input-properties"></a>Inndataegenskaper

| Navn | Datatype | Kreves | Beskrivelse |
| --- | --- | --- | --- |
| userName |streng |ja |Brukerens Twitter-brukernavn |
| maxResults |heltall |nei |Maksimalt antall brukere som skal hentes, for eksempel {maxResults:5} |

#### <a name="output-properties"></a>Utdataegenskaper

| Egenskapsnavn | Datatype | Kreves | Beskrivelse |
| --- | --- | --- | --- |
| FullName |streng |Ja | |
| Plassering |streng |Ja | |
| ID |heltall |Nei | |
| UserName |streng |Ja | |
| FollowersCount |heltall |Nei | |
| Beskrivelse |streng |Ja | |
| StatusesCount |heltall |Nei | |
| FriendsCount |heltall |Nei | |

### <a name="myfollowers"></a>MyFollowers
Denne handlingen henter brukere som følger meg

#### <a name="input-properties"></a>Inndataegenskaper

| Navn | Datatype | Kreves | Beskrivelse |
| --- | --- | --- | --- |
| maxResults |heltall |nei |Maksimalt antall brukere som skal hentes, for eksempel {maxResults:5} |

#### <a name="output-properties"></a>Utdataegenskaper

| Egenskapsnavn | Datatype | Kreves | Beskrivelse |
| --- | --- | --- | --- |
| FullName |streng |Ja | |
| Plassering |streng |Ja | |
| ID |heltall |Nei | |
| UserName |streng |Ja | |
| FollowersCount |heltall |Nei | |
| Beskrivelse |streng |Ja | |
| StatusesCount |heltall |Nei | |
| FriendsCount |heltall |Nei | |

### <a name="following"></a>Følger
Denne handlingen henter brukere som den angitte brukeren følger

#### <a name="input-properties"></a>Inndataegenskaper

| Navn | Datatype | Kreves | Beskrivelse |
| --- | --- | --- | --- |
| userName |streng |ja |Brukerens Twitter-brukernavn |
| maxResults |heltall |nei |Maksimalt antall brukere som skal hentes, for eksempel {maxResults:5} |

#### <a name="output-properties"></a>Utdataegenskaper

| Egenskapsnavn | Datatype | Kreves | Beskrivelse |
| --- | --- | --- | --- |
| FullName |streng |Ja | |
| Plassering |streng |Ja | |
| ID |heltall |Nei | |
| UserName |streng |Ja | |
| FollowersCount |heltall |Nei | |
| Beskrivelse |streng |Ja | |
| StatusesCount |heltall |Nei | |
| FriendsCount |heltall |Nei | |

### <a name="myfollowing"></a>MyFollowing
Denne handlingen henter brukere som jeg følger

#### <a name="input-properties"></a>Inndataegenskaper

| Navn | Datatype | Kreves | Beskrivelse |
| --- | --- | --- | --- |
| maxResults |heltall |nei |Maksimalt antall brukere som skal hentes, for eksempel {maxResults:5} |

#### <a name="output-properties"></a>Utdataegenskaper

| Egenskapsnavn | Datatype | Kreves | Beskrivelse |
| --- | --- | --- | --- |
| FullName |streng |Ja | |
| Plassering |streng |Ja | |
| ID |heltall |Nei | |
| UserName |streng |Ja | |
| FollowersCount |heltall |Nei | |
| Beskrivelse |streng |Ja | |
| StatusesCount |heltall |Nei | |
| FriendsCount |heltall |Nei | |

### <a name="user"></a>Bruker
Denne handlingen henter detaljer om den angitte brukeren (for eksempel brukernavn, beskrivelse, følgere, telling og så videre)

#### <a name="input-properties"></a>Inndataegenskaper

| Navn | Datatype | Kreves | Beskrivelse |
| --- | --- | --- | --- |
| userName |streng |ja |Brukerens Twitter-brukernavn |

#### <a name="output-properties"></a>Utdataegenskaper

| Egenskapsnavn | Datatype | Kreves | Beskrivelse |
| --- | --- | --- | --- |
| FullName |streng |Ja | |
| Plassering |streng |Ja | |
| ID |heltall |Nei | |
| UserName |streng |Ja | |
| FollowersCount |heltall |Nei | |
| Beskrivelse |streng |Ja | |
| StatusesCount |heltall |Nei | |
| FriendsCount |heltall |Nei | |

### <a name="tweet"></a>Tweet
Denne handlingen legger ut en ny tweet

#### <a name="input-properties"></a>Inndataegenskaper

| Navn | Datatype | Kreves | Beskrivelse |
| --- | --- | --- | --- |
| tweetText |streng |nei |Tekst som skal legges ut, for eksempel {tweetText:"hello"} |
| body |streng |nei |Medier som skal legges ut |

#### <a name="output-properties"></a>Utdataegenskaper

| Egenskapsnavn | Datatype | Kreves | Beskrivelse |
| --- | --- | --- | --- |
| TweetId |streng |Ja | |

### <a name="onnewtweet"></a>OnNewTweet
Når en ny tweet legges ut, utløses det en arbeidsflyt som samsvarer med søket

#### <a name="input-properties"></a>Inndataegenskaper

| Navn | Datatype | Kreves | Beskrivelse |
| --- | --- | --- | --- |
| searchQuery |streng |ja |Spørringstekst (du kan bruke spørringsoperatorer som støttes av Twitter: http://www.twitter.com/search) |

#### <a name="output-properties"></a>Utdataegenskaper

| Egenskapsnavn | Datatype | Kreves | Beskrivelse |
| --- | --- | --- | --- |
| verdi |matrise |Nei | |

## <a name="helpful-links"></a>Nyttige koblinger
Se alle [tilgjengelige tilkoblinger](../connections-list.md).  
Finn ut hvordan du [legger til tilkoblinger](../add-manage-connections.md) i appene dine.

