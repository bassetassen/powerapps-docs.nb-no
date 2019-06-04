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
ms.openlocfilehash: 8004a39e83ea3615ce8a77637a9f5c0271b67781
ms.sourcegitcommit: 157ab15738e2d0d1bf9097bbb7b9e3d9c29a4015
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 05/28/2019
ms.locfileid: "66265784"
ms.PowerAppsDecimalTransform: true
---
# <a name="develop-offline-capable-canvas-apps"></a>Utvikle lerretsapper som fungerer i frakoblet tilstand

Mobile brukere trenger ofte å være produktive, selv når de har begrenset eller ingen tilkobling. Når du bygger en lerret-app, kan du utføre disse oppgavene:

- Åpne PowerApps Mobile, og kjøre apper når du er frakoblet.
- Fastslå når en app er frakoblet, tilkoblet, eller bruker en forbruksmålt tilkobling ved bruk av [Tilkobling](../canvas-apps/functions/signals.md#connection)-signalobjektet.
- Bruk [samlinger](../canvas-apps/create-update-collection.md) og nyttefunksjoner som [LoadData og SaveData](../canvas-apps/functions/function-savedata-loaddata.md) for grunnleggende datalagring når du er frakoblet.

## <a name="limitations"></a>Begrensninger

**LoadData** og **SaveData** kombinere for å danne en enkel mekanisme for å lagre små mengder med data på en lokal enhet. Ved å bruke disse funksjonene, kan du legge til enkle frakoblede funksjoner appen din.

Disse funksjonene er begrenset av mengden minne tilgjengelig app fordi de fungerer på en samling i minnet. Tilgjengelig minne kan variere avhengig av enheten, operativsystemet, minnet som bruker PowerApps Mobile og kompleksiteten til appen når det gjelder skjermer og kontroller. Hvis du lagrer mer enn et par MB med data, kan du teste appen din med forventede scenarier på enheter som du forventer at den skal kjøres. Du får vanligvis 30 – 70 MB tilgjengelig minne.

Funksjonene også løse ikke automatisk flettekonflikter når en enhet kommer online. Konfigurasjon for hvilke data lagres og hvordan du håndtere ny tilkobling er opptil produsenten når du skriver inn uttrykk.

Etter oppdateringer på frakoblede funksjoner, gå tilbake til dette emnet, og abonnere på den [PowerApps-bloggen](https://powerapps.microsoft.com/blog/).

## <a name="overview"></a>Oversikt

Når du utformer frakoblede scenarioer, bør du først vurdere hvordan appene arbeider med data. Apper i PowerApps tilgang til data hovedsaklig gjennom et sett med [koblinger](../canvas-apps/connections-list.md) plattformen har, for eksempel SharePoint, Office 365 og Common Data Service. Du kan også bygge egendefinerte koblinger som lar appene få tilgang til en tjeneste med et avslappende endepunkt. Dette kan være Web API eller en tjeneste som Azure Functions. Alle disse koblingene bruker HTTPS over Internett, noe som betyr at brukerne må være tilkoblet for å få tilgang til dataene og eventuelle andre funksjoner som er inkludert i tjenesten.

![PowerApps-app med koblinger](./media/offline-apps/online-app.png)

### <a name="handling-offline-data"></a>Å håndtere data i frakoblet modus

I PowerApps, kan du filtrere, søke, sortere, samle og manipulere data på en konsekvent måte uavhengig av datakilden. Kilder varierer fra samler i appen til SharePoint-lister til SQL-databaser og Common Data Service. På grunn av denne konsekvens, kan du enkelt ta i bruk en app for å bruke en annen datakilde. Kanskje enda viktigere for frakoblede scenarioer, kan du bruke lokale samlingene for dataadministrasjon med nesten ingen endringer i applogikken. Lokale samlinger er faktisk den primære mekanismen for å håndtere data i frakoblet modus.

## <a name="build-an-offline-app"></a>Bygg en frakoblet app

Hvis du vil beholde fokus på de frakoblede aspektene til apputvikling, illustrerer dette emnet et enkelt scenario knyttet til Twitter. Du skal bygge en app som lar deg lese Twitter-innlegg og sende tweets mens du er i frakoblet modus. Når appen kobles til Internett, sender appen tweetene og laster inn de lokale dataene på nytt.

På et høyt nivå utfører appen disse oppgavene:

- Når brukeren åpner appen:

  - Hvis enheten er tilkoblet, henter data via Twitter-koblingen i appen, og fyller ut en samling med disse dataene.
  - Hvis enheten er frakoblet, appen laster inn dataene fra en lokal hurtigbufferfil ved hjelp av den [ **LoadData** ](../canvas-apps/functions/function-savedata-loaddata.md) funksjonen.
  - Brukeren kan sende tweets. Hvis appen er tilkoblet, legger inn tweets direkte med Twitter og oppdaterer det lokale mellomlageret.

- Hvert femte minutt mens appen er koblet til Internett:

  - Appen legger inn tweets i den lokale hurtigbufferen.
  - Appen oppdaterer det lokale mellomlageret og lagrer den ved hjelp av den [ **SaveData** ](../canvas-apps/functions/function-savedata-loaddata.md) funksjonen.

### <a name="step-1-add-twitter-to-a-blank-phone-app"></a>Trinn 1: Legg til Twitter til en tom telefonapp

1. I PowerApps Studio, velg **filen** > **ny**.
1. Velg **Telefonoppsett** på **Tom app**-flisen.
1. Velg **Datakilder** på **Vis**-fanen.
1. I den **Data** ruten velger **Legg til datakilde**.
1. Velg **ny tilkobling** > **Twitter** > **opprette**.
1. Angi legitimasjonen for opprette tilkoblingen og lukk deretter den **Data** ruten.

### <a name="step-2-collect-existing-tweets"></a>Trinn 2: Samle inn eksisterende tweeter

1. I den **trevisning** ruten velger **App**, og deretter angi dens **OnStart** egenskapen til denne formelen:

    ```powerapps-comma
    If( Connection.Connected;
        ClearCollect( LocalTweets; Twitter.SearchTweet( "PowerApps"; {maxResults: 10} ) );;
            Set( statusText; "Online data" );
        LoadData( LocalTweets; "LocalTweets"; true );;
            Set( statusText; "Local data" )
    );;
    SaveData( LocalTweets; "LocalTweets" );;
    ```

    > [!div class="mx-imgBorder"]
    > ![Formel for å laste inn tweets](./media/offline-apps/load-tweets.png)

1. I den **trevisning** ruten, Velg ellipse-menyen for den **App** objektet, og velg deretter **kjøre OnStart** til å kjøre denne formelen.

    > [!div class="mx-imgBorder"]
    > ![Kjør formel for å laste inn tweets](./media/offline-apps/load-tweets-run.png)

    > [!NOTE]
    > Den **LoadData** og **SaveData** funksjoner kan vise en feil i PowerApps Studio fordi nettlesere ikke støtter dem. Men skal de utføre vanligvis når du har distribuert denne appen til en enhet.

Denne formelen kontrollerer om enheten er koblet til Internett:

- Hvis enheten er tilkoblet, formelen laster opp til 10 tweets med søkeordet «PowerApps» inn i en **LocalTweets** samling.
- Hvis enheten er frakoblet, laster formelen det lokale mellomlageret fra en fil som heter «LocalTweets» Hvis det er tilgjengelig.

### <a name="step-3-show-tweets-in-a-gallery"></a>Trinn 3: Vis tweeter i et galleri

1. På den **Sett inn** fanen og velge **galleriet** > **tomt, fleksibel høyde**.

1. Angi den **elementer** -egenskapen for den [ **galleriet** ](controls/control-gallery.md) kontrollen til `LocalTweets`.

1. I gallerimalen, Legg til tre [ **etikett** ](controls/control-text-box.md) kontroller, og angi den **tekst** -egenskapen for hver etikett til én av disse verdiene:

    - `ThisItem.UserDetails.FullName & " (@" & ThisItem.UserDetails.UserName & ")"`
    - `Text(DateTimeValue(ThisItem.CreatedAtIso); DateTimeFormat.ShortDateTime)`
    - `ThisItem.TweetText`

1. Utheve teksten i den siste etiketten slik at galleriet ligner dette eksemplet.

    > [!div class="mx-imgBorder"]
    > ![Galleriet viser eksempel på tweeter](./media/offline-apps/tweet-gallery.png)

### <a name="step-4-show-connection-status"></a>Trinn 4: Vis tilkoblingsstatus for

1. Under galleriet, sette inn en etikett, og deretter angi dens **farge** egenskapen til **Red**.

1. Angi nyeste etikettens **tekst** egenskapen til denne formelen:

    `If( Connection.Connected; "Connected"; "Offline" )`

Denne formelen bestemmer om enheten er tilkoblet. Hvis det er, etiketten viser **tilkoblet**; Hvis ikke, den viser **frakoblet**.

### <a name="step-5-add-a-box-to-compose-tweets"></a>Trinn 5: Legg til en for å opprette tweeets

1. Under tilkoblingsstatus etiketten, Sett inn en [ **tekstinndata** ](controls/control-text-input.md) kontroll, og gi den nytt navn **NewTweetTextInput**.

1. Angi boksen innskriving av tekst **standard** egenskapen til `""`.

    > [!div class="mx-imgBorder"]
    > ![Galleriet over informasjon om statusen og tekstinndata-boksen](./media/offline-apps/status-input.png)

### <a name="step-6-add-a-button-to-post-the-tweet"></a>Trinn 6: Legg til en knapp for å publisere tweet

1. Under tekstinndata-boksen, kan du legge til en **knappen** kontroll, og angi dens **tekst** egenskapen til denne verdien:

    `"Tweet"`

1. Angi knappens **OnSelect** egenskapen til denne formelen:

    ```powerapps-comma
    If( Connection.Connected;
        Twitter.Tweet( ""; {tweetText: NewTweetTextInput.Text} );
        Collect( LocalTweetsToPost; {tweetText: NewTweetTextInput.Text} );;
            SaveData( LocalTweetsToPost; "LocalTweetsToPost" )
    );;
    Reset( NewTweetTextInput );;
    ```  

1. I den **OnStart** -egenskapen for den **App**, legge til en linje på slutten av formelen:

    ```powerapps-comma
    If( Connection.Connected;
        ClearCollect( LocalTweets; Twitter.SearchTweet( "PowerApps"; {maxResults: 100} ) );;
            Set( statusText; "Online data" );
        LoadData( LocalTweets; "LocalTweets"; true );;
            Set( statusText; "Local data" )
    );;
    SaveData( LocalTweets; "LocalTweets" );;
    LoadData( LocalTweetsToPost; "LocalTweetsToPost"; true );;  // added line
    ```

    > [!div class="mx-imgBorder"]
    > ![Kjør formel for å laste inn tweets med uncommented linje](./media/offline-apps/load-tweets-save.png)

Denne formelen bestemmer om enheten er koblet til Internett:

- Hvis enheten er tilkoblet, publiserer den tweeten umiddelbart.
- Hvis enheten er frakoblet, fanger den opp tweeten i en **LocalTweetsToPost** samling og lagrer den i enheten.

Deretter tilbakestiller formelen teksten i tekstinndata-boksen.

### <a name="step-7-check-for-new-tweets"></a>Trinn 7: Se etter nye tweeter

1. På høyre side av-knappen, kan du legge til en **tidtaker** kontroll.

    > [!div class="mx-imgBorder"]
    > ![Endelig apper](./media/offline-apps/final-app.png)

1. Angi tidtakerens **varighet** egenskapen til **300000**.

1. Angi tidtakerens **AutoStart** og **Gjenta** egenskaper til **SANN**.

1. Angi tidtakerens **OnTimerEnd** til denne formelen:

    ```powerapps-comma
    If( Connection.Connected;
        ForAll( LocalTweetsToPost; Twitter.Tweet( ""; {tweetText: tweetText} ) );;
        Clear( LocalTweetsToPost );;
        ClearCollect( LocalTweets; Twitter.SearchTweet( "PowerApps"; {maxResults: 10} ) );;
        SaveData( LocalTweets; "LocalTweets" );;
   )
    ```

Denne formelen bestemmer om enheten er tilkoblet. Hvis det er, appen alle tweetene i den **LocalTweetsToPost** samling og deretter fjerner samlingen.

## <a name="test-the-app"></a>Testing av appen

1. Åpne appen på en mobil enhet som er koblet til Internett.

    Eksisterende tweeter vises i galleriet, og statusen viser **tilkoblet**.

1. Koble enheten fra Internett ved å aktivere enhetens flymodus og deaktivering av wi-fi.

    Status for etiketten viser at appen er **frakoblet**.

1. Mens enheten er frakoblet, kan du skrive en tweet som inkluderer **PowerApps**, og velg deretter den **Tweet** knappen.

    Tweeten er lagret lokalt i den **LocalTweetsToPost** samling.

1. Koble enheten til Internett ved å deaktivere enhetens flymodus og aktivere wi-fi.

    Innen fem minutter publiserer appen tweeten, som vises i galleriet.

Vi håper at denne artikkelen gir deg et inntrykk av funksjonene som PowerApps har for å bygge frakoblede apper. Gi oss som alltid dine tilbakemeldinger i [forumet](https://powerusers.microsoft.com/t5/PowerApps-Forum/bd-p/PowerAppsForum1), og del dine eksempler på frakoblede apper i [PowerApps-fellesskapsbloggen](https://powerusers.microsoft.com/t5/PowerApps-Community-Blog/bg-p/PowerAppsBlog).