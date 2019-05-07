---
title: Utvikle lerretsapper som fungerer i frakoblet tilstand | Microsoft Docs
description: Utvikle lerretsapper som fungerer i frakoblet tilstand, slik at brukerne kan være produktive enten de er tilkoblet eller frakoblet.
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 01/31/2019
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: f9922c64769aeacd9b9b65cc3039b091ac7fe353
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/23/2019
ms.locfileid: "61538361"
ms.PowerAppsDecimalTransform: true
---
# <a name="develop-offline-capable-canvas-apps"></a>Utvikle lerretsapper som fungerer i frakoblet tilstand

Et av de vanligste scenarioene du opplever som utvikler av mobilapper, er å gjøre det mulig for brukerne å være produktive der det er begrensede tilkoblingsmuligheter, eller ingen tilkobling i det hele tatt. PowerApps har et sett med funksjoner og virkemåter som hjelper deg å utvikle lerretsapper som fungerer i frakoblet tilstand. du kan:

* Start PowerApps Mobile når du er frakoblet.
* Kjør apper du utvikler når du er frakoblet.
* Fastslå når en app er frakoblet, tilkoblet, eller bruker en forbruksmålt tilkobling ved bruk av [Tilkobling](../canvas-apps/functions/signals.md#connection)-signalobjektet.
* Bruk [samlinger](../canvas-apps/create-update-collection.md) og nyttefunksjoner som [LoadData og SaveData](../canvas-apps/functions/function-savedata-loaddata.md) for grunnleggende datalagring når du er frakoblet.

## <a name="limitations"></a>Begrensninger

**LoadData** og **SaveData** kombinere for å danne en enkel mekanisme for å lagre små mengder med data på en lokal enhet. Ved å bruke disse funksjonene, kan du legge til enkle frakoblede funksjoner appen din.  

Disse funksjonene er begrenset av mengden minne tilgjengelig app fordi de fungerer på en samling i minnet. Tilgjengelig minne kan variere avhengig av enheten, operativsystemet, minnet som bruker PowerApps Mobile og kompleksiteten til appen når det gjelder skjermer og kontroller. Hvis du lagrer mer enn et par MB med data, kan du teste appen din med forventede scenarier på enheter som du forventer at den skal kjøres. Du bør generelt forvente å ha mellom 30 og 70 MB tilgjengelig minne.  

Funksjonene også løse ikke automatisk flettekonflikter når en enhet returnerer til tilkobling fra frakoblet – konfigurasjonen på hvilke data lagres og hvordan du håndterer ny tilkobling er opptil maker når du skriver inn uttrykk.

Vi jobber for å utvide mulighetene for frakoblede scenarioer. Kom tilbake hit og les [PowerApps-bloggen](https://powerapps.microsoft.com/blog/) for oppdateringer når de blir tilgjengelige.

## <a name="how-to-build-offline-capable-apps"></a>Å bygge apper som fungerer i frakoblet tilstand

Det første du må tenke på i frakoblede scenarioer, er hvordan appene arbeider med data. Apper i PowerApps får tilgang til data hovedsaklig gjennom et sett med [koblinger](../canvas-apps/connections-list.md) i plattformen, som SharePoint, Office 365 og Common Data Service. Du kan også bygge egendefinerte koblinger som lar appene få tilgang til en tjeneste med et avslappende endepunkt. Dette kan være Web API eller en tjeneste som Azure Functions. Alle disse koblingene bruker HTTPS over Internett, noe som betyr at brukerne må være tilkoblet for å få tilgang til dataene og eventuelle andre funksjoner som er inkludert i tjenesten.

![PowerApps-app med koblinger](./media/offline-apps/online-app.png)

### <a name="handling-offline-data"></a>Å håndtere data i frakoblet modus
Én av de mest interessante aspektene med PowerApps er dets funksjons- og formelsett. Du kan bruk dem til å filtrere, søke etter, sortere, samle og manipulere data på en konsekvent måte, uavhengig av datakilden. Kilder varierer fra samler i appen, til SharePoint-lister, SQL-databaser og Common Data Service. Med denne konsekventheten kan du enkelt ta i bruk en app på en annen måte for å bruke en annen serverdel. Enda viktigere er at det du kan bruke de lokale samlingene for dataadministrasjon med nesten ingen endringer i applogikken. Lokale samlinger er faktisk den primære mekanismen for å håndtere data i frakoblet modus.

## <a name="building-an-offline-twitter-app"></a>Å bygge en Twitter-app som fungerer i frakoblet modus
Hvis du ønsker å fokusere på de frakoblede aspektene til apputvikling, skal vi vise deg et enkelt scenario knyttet til Twitter. Vi skal bygge en app som lar deg lese Twitter-innlegg og sende tweets mens du er i frakoblet modus. Når appen kobles til Internett, sender appen tweetene og laster inn de lokale dataene på nytt.

Appen gjør følgende på et høyt nivå:

1. Ved oppstart av appen (basert på **OnVisible**-egenskapen til den første skjermen):

   * Hvis enheten er koblet til Internett, får vi direkte tilgang til Twitter-koblingen for å hente data, og fyller ut en samling med disse dataene.
   * Hvis enheten er i frakoblet modus, laster vi dataene fra en lokal mellomlagringsfil ved bruk av [LoadData](../canvas-apps/functions/function-savedata-loaddata.md).
   * Brukeren kan sende tweets – hvis brukeren er koblet til Internett, kommuniserer vi direkte med Twitter og oppdaterer det lokale mellomlageret.
2. Hvert femte minutt, hvis koblet til Internett:

   * Vi legger inn tweets som finnes i det lokale mellomlageret.
   * Vi oppdaterer det lokale mellomlageret og lagrer det ved bruk av [SaveData](../canvas-apps/functions/function-savedata-loaddata.md).

### <a name="step-1-create-a-new-phone-app"></a>Trinn 1: Opprette en ny telefonapp
1. Å åpne PowerApps Studio.
2. Klikk eller trykk på **Ny** > **Tom app** > **Telefonoppsett**.

    ![Tom app – telefonoppsett](./media/offline-apps/blank-app.png)

### <a name="step-2-add-a-twitter-connection"></a>Trinn 2: Å legge til en Twitter-tilkobling

1. Klikk eller trykk på **Innhold** > **Datakilder**, og velg deretter **Legg til datakilde** på **Datakilder**-panelet.

2. Klikk eller trykk på **Ny forbindelse**, velg **Twitter** og klikk eller trykk på **Opprett**.

3. Skriv inn legitimasjonen din, og opprett tilkoblingen.

    ![Å legge til en Twitter-tilkobling](./media/offline-apps/twitter-connection.png)

### <a name="step-3-load-tweets-into-a-localtweets-collection-on-app-startup"></a>Trinn 3: Laste inn tweets i en LocalTweets-samling ved oppstart av appen
Velg **OnVisible**-egenskapen for **Screen1** i appen, og kopier inn følgende formel:

```powerapps-comma
If( Connection.Connected;
    ClearCollect( LocalTweets; Twitter.SearchTweet( "PowerApps"; {maxResults: 100} ) );;
        UpdateContext( {statusText: "Online data"} );
    LoadData(LocalTweets; "Tweets"; true);;
        UpdateContext( {statusText: "Local data"} )
);;
LoadData( LocalTweetsToPost; "LocalTweets"; true );;
SaveData( LocalTweets; "Tweets" )
```

![Formel for å laste inn tweets](./media/offline-apps/load-tweets.png)

Denne formelen kontrollerer om enheten er koblet til Internett:

* Hvis enheten er koblet til Internett, laster den inn en **LocalTweets**-samling med opptil 100 tweets med søkeordet «PowerApps».
* Hvis enheten er i frakoblet modus, laster den inn det lokale mellomlageret fra en fil som heter «Tweets», hvis den er tilgjengelig.

### <a name="step-4-add-a-gallery-and-bind-it-to-the-localtweets-collection"></a>Trinn 4: Legge til et galleri og binde det til LocalTweets-samlingen

1. Sett inn et nytt galleri med fleksibel høyde: **Sett inn** > **galleriet** > **tomt, fleksibel høyde**.

2. Angi **Elementer**-egenskapen til **LocalTweets**.

3. Legg til fire **Etikett**-kontroller for å vise dataene fra hver tweet, og angi **Tekst**-egenskapen til:
   * **ThisItem.TweetText**
   * **ThisItem.UserDetails.FullName & " \@" & ThisItem.UserDetails.UserName**
   * **"RT: " & ThisItem.RetweetCount**
   * **Text(DateTimeValue(ThisItem.CreatedAtIso); DateTimeFormat.ShortDateTime)**
4. Legg til en **Bilde**-kontroll, og angi **Bilde**-egenskapen til **ThisItem.UserDetails.ProfileImageUrl**.

### <a name="step-5-add-a-connection-status-label"></a>Trinn 5: Legg til en statusetikett for
Sett inn en ny **Etikett**-kontroll, og angi **Tekst**-egenskapen til denne formelen:

```If( Connection.Connected; "Connected"; "Offline" )```

Denne formelen kontrollerer om enheten er koblet til Internett. Hvis den er det, er teksten i etiketten «Tilkoblet». Ellers er den «Frakoblet».

### <a name="step-6-add-a-text-input-to-compose-new-tweets"></a>Trinn 6: Legg til en tekstinndata for å opprette nye tweeets

1. Sett inn en ny **Tekstinndata**-kontroll med navn «NewTweetTextInput».

2. Angi **Reset**-egenskapen til tekstinndataen til **resetNewTweet**.

### <a name="step-7-add-a-button-to-post-the-tweet"></a>Trinn 7: Legg til en knapp for å publisere tweet
1. Legg til en **Knapp**-kontroll, og angi **Tekst**-egenskapen til «Tweet».
2. Angi knappens **OnSelect**-egenskap til følgende formel:

    ```powerapps-comma
    If( Connection.Connected;
        Twitter.Tweet( ""; {tweetText: NewTweetTextInput.Text} );
        Collect( LocalTweetsToPost; {tweetText: NewTweetTextInput.Text} );;
            SaveData( LocalTweetsToPost; "LocalTweetsToPost" )
    );;
    UpdateContext( {resetNewTweet: true} );;
    UpdateContext( {resetNewTweet: false} )
    ```  

Denne formelen kontrollerer om enheten er koblet til Internett:

* Hvis enheten er koblet til Internett, publiseres tweetene umiddelbart.
* Hvis en enhet er i frakoblet modus, fanger den opp tweeten i en **LocalTweetsToPost**-samling, og lagrer den i appen.

Deretter tilbakestiller formelen teksten i tekstboksen.

### <a name="step-8-add-a-timer-to-check-for-tweets-every-five-minutes"></a>Trinn 8: Legg til en tidtaker som ser etter tweets hvert femte minutt
Legg til en ny **Tidtaker**-kontroll:

* Angi **Varighet**-egenskapen til 300000.

* Angi **AutoStart**-egenskapen til sann.

* Angi **OnTimerEnd** til følgende formel:

    ```powerapps-comma
    If( Connection.Connected;
        ForAll( LocalTweetsToPost; Twitter.Tweet( ""; {tweetText: tweetText} ) );;
        Clear( LocalTweetsToPost);;
        Collect( LocalTweetsToPost; {tweetText: NewTweetTextInput.Text} );;
        SaveData( LocalTweetsToPost; "LocalTweetsToPost" );;
        UpdateContext( {statusText: "Online data"} )
    )
    ```

Denne formelen kontrollerer om enheten er koblet til Internett. Hvis den er det, publiserer appen alle tweetene i **LocalTweetsToPost**-samlingen. Deretter fjerner den samlingen.

Nå som appen er ferdig, kan vi se hvordan det ser ut før vi fortsetter til testing. Til venstre ser vi at appen er tilkoblet, og til høyre er den i frakoblet modus, med én tweet som er klar til å publiseres når den kobles til Internett igjen.

![Ferdig app med tilkoblet og frakoblet modus](./media/offline-apps/finished-app.png)

## <a name="testing-the-app"></a>Å teste appen
Bruk følgende trinn for å teste appen:

1. Kjør PowerApps på en mobil enhet når du er koblet til Internett. Du må kjøre en app minst én gang mens du er koblet til Internett, slik at du kan laste ned appen til enheten.
2. Start Twitter-appen.
3. Legg merke til at tweetene er lastet inn og at statusen viser **Tilkoblet**.
4. Lukk PowerApps helt.
5. Sett enheten over i flymodus for å sikre at den er i frakoblet modus.
6. Kjør PowerApps. Du kan nå kjøre Twitter-appen i frakoblet modus, og du har tilgang til apper som du har kjørt tidligere på denne enheten mens du var tilkoblet Internett (det vil si, PowerApps skjuler apper som ikke har blitt lastet ned til enheten).
7. Kjør appen på nytt.
8. Legg merke til hvordan tilkoblingstilstanden blir riktig oppdatert, og statusen er **Frakoblet**.
9. Skriv en ny tweet. Den lagres lokalt i **LocalTweetsToPost**-samlingen.
10. Avslutt flymodus. Etter at tidtakeren utløser, publiserer appen tweeten.

Vi håper at denne artikkelen gir deg et inntrykk av funksjonene som PowerApps har for å bygge frakoblede apper. Gi oss som alltid dine tilbakemeldinger i [forumet](https://powerusers.microsoft.com/t5/PowerApps-Forum/bd-p/PowerAppsForum1), og del dine eksempler på frakoblede apper i [PowerApps-fellesskapsbloggen](https://powerusers.microsoft.com/t5/PowerApps-Community-Blog/bg-p/PowerAppsBlog).

