---
title: Bruk av Cognitive Services i PowerApps | Microsoft Docs
description: Utvikle en grunnleggende app som bruker API for tekstanalyse i Microsoft Cognitive Services til å analysere tekst.
services: ''
suite: powerapps
documentationcenter: na
author: mgblythe
manager: anneta
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 12/08/2017
ms.author: mblythe
ms.openlocfilehash: 2e82feb9df4121b24ffd1f5cad7669c6aa58c8e8
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/22/2018
ms.locfileid: "30996197"
---
# <a name="use-cognitive-services-in-powerapps"></a>Bruk av Cognitive Services i PowerApps
Denne artikkelen viser hvordan du kan utvikle en grunnleggende app som bruker [API for tekstanalyse i Microsoft Cognitive Services](https://docs.microsoft.com/azure/cognitive-services/text-analytics/overview) til å analysere tekst. Vi viser deg hvordan du konfigurerer API-en for tekstanalyse og kobler til ved hjelp av [Tekstanalyse-koblingen](https://docs.microsoft.com/connectors/cognitiveservicestextanalytics/). Deretter viser vi hvordan du oppretter en app som utfører et oppkall til API-en.

> [!NOTE]
> Hvis du er ny på utvikling av apper i PowerApps, anbefaler vi at du leser [Oppretting av en app fra bunnen av](get-started-create-from-blank.md) før du går nærmere inn på denne artikkelen.

## <a name="introduction-to-microsoft-cognitive-services"></a>Innføring i Microsoft Cognitive Services
Microsoft Cognitive Services er et sett med API-er, SDK-er og tjenester som er tilgjengelige for å gjøre programmene dine mer intelligente, engasjerende og lettere å finne. Disse tjenestene hjelper deg å legge til intelligente funksjoner, for eksempel gjenkjenning av følelser og gjenkjenning for video; ansikt-, tale- og visuell gjenkjenning samt språkforståelse, i programmene.

Vi fokuserer på språkforståelse i denne artikkelen, og bruker API-en for tekstanalyse. Denne API-en gjør det mulig å gjenkjenne sentiment, nøkkeluttrykk, emner og språk fra teksten. La oss komme i gang ved å prøve ut en demonstrasjon av API-en, og deretter registrere en forhåndsversjon.

### <a name="try-out-the-text-analytics-api"></a>Prøv API-en for tekstanalyse
API-en har en demonstrasjon på nettet. Du kan se hvordan det fungerer, og se hvilken JSON tjenesten returnerer.

1. Gå til siden [API for tekstanalyse](https://azure.microsoft.com/services/cognitive-services/text-analytics/).

2. Bruk eksempelteksten i delen **Se i praksis**, eller angi din egen tekst. Klikk eller trykk på **Analyser**. 
   
    ![Demonstrasjon av API for tekstanalyse](./media/cognitive-services-api/text-analytics-demo.png)

3. Siden viser formaterte resultater på **Analysert tekst**-fanen og JSON-svaret på **JSON**-fanen. [JSON](http://json.org/) er en måte å representere data på, i dette tilfellet data som returneres av API-en for tekstanalyse.

## <a name="sign-up-for-the-text-analytics-api"></a>Registrer deg for API-en for tekstanalyse
API-en er tilgjengelig i gratis prøveversjon, og den er tilknyttet et Azure-abonnement. Du administrerer API-en gjennom Azure-portalen.

1. Hvis du ikke har et Azure-abonnement allerede, kan du [registrere deg for et gratis abonnement](https://azure.microsoft.com/free/).

2. Logg deg på Azure-kontoen.

3. Gå til [Opprett Cognitive Services-bladet](https://go.microsoft.com/fwlink/?LinkId=761108) i Azure-portalen.

4. Angi informasjon for API-en for tekstanalyse, slik som i bildet nedenfor. Velg **F0** (gratis)-prisnivået.
   
    ![Opprett API for tekstanalyse](./media/cognitive-services-api/azure-create.png)

5. Klikk eller trykk på **Opprett** i hjørnet nederst til venstre.

6. Klikk eller trykk på API-en du nettopp har opprettet, på **Instrumentbordet**.
   
    ![Azure-instrumentbordet](./media/cognitive-services-api/azure-dashboard.png)

7. Klikk eller trykk på **Nøkler**.
   
    ![Azure-menyen](./media/cognitive-services-api/azure-menu-keys.png)

8. Kopier én av nøklene til høyre på skjermen. Du bruker denne nøkkelen senere når du oppretter en tilkobling til API-en.
   
    ![API-nøkler](./media/cognitive-services-api/azure-keys.png)

## <a name="build-the-app"></a>Utvikling av appen
Nå som API-en for tekstanalyse er oppe og går, kobler du til fra PowerApps og utvikler en app som kaller API-en. Dette er én enkelt skjermapp som har en funksjonalitet som ligner på demonstrasjonen på siden API for tekstanalyse. La oss komme i gang med å utvikle denne.

### <a name="create-the-app-and-add-a-connection"></a>Opprette appen og legge til en tilkobling
Først må du opprette en tom telefonapp og legge til en tilkobling med **Tekstanalyse**-koblingen. Hvis du trenger mer informasjon om disse oppgavene, kan du se [Oppretting av en app fra bunnen av ](get-started-create-from-blank.md)og [Administrering av tilkoblinger i PowerApps](add-manage-connections.md).

1. Velg **Start med en tom app** > ![Telefonapp-ikon](./media/cognitive-services-api/icon-phone-app.png) (telefon) > **Lag denne appen**, i [web.powerapps.com](https://web.powerapps.com).

    ![Starte med en tom app](./media/cognitive-services-api/start-from-blank.png)

2. I den midterste ruten i PowerApps Studio velger du **koble til data**.

3. Klikk eller trykk på **Ny tilkobling** > **Tekstanalyse** på **Data**-panelet.

4. Kopier nøkkelen til **Kontonøkkel**, og klikk eller trykk deretter på **Opprett**.
   
    ![Tekstanalyse-kobling](./media/cognitive-services-api/create-connection-ta.png)

### <a name="add-controls-to-the-app"></a>Legge til kontroller i appen
Det neste trinnet i oppretting av appen er å legge til alle kontrollene. Når jeg utvikler apper, legger jeg vanligvis til formler i kontrollene etter hvert, men i dette tilfellet skal vi fokusere på kontrollene først og deretter legge til noen formler i neste del. Bildet nedenfor viser appen med alle kontrollene.

![Ferdigstilt app](./media/cognitive-services-api/finished-app-no-data.png)

Følg fremgangsmåten nedenfor for å opprette denne skjermen. Hvis et kontrollnavn er angitt, brukes dette navnet i en formel i neste del.

1. Klikk eller trykk på **Ny skjerm** på **Hjem-fanen**, og klikk eller trykk deretter på **Skjerm som kan rulles**. 

2. Velg **[Tittel]** på **Screen2**, og endre den til **Tekstanalyse**.

3. Legg til en **Etikett**-kontroll for den innledende teksten.

4. Legg til en **Tekstinndata**-kontroll, slik at du kan angi teksten som skal analyseres. Gi kontrollen navnet **tiTextToAnalyze**. Appen skal nå se ut som på følgende bilde.
   
    ![App med tittel, undertittel og tekstinndata](./media/cognitive-services-api/partial-app-step1.png)

5. Legg til tre **Avmerkingsboks**-kontroller, slik at du kan velge hvilke API-operasjoner som skal utføres. Gi kontrollene navnene **chkLanguage**, **chkPhrases** og **chkSentiment**.

6. Legg til en knapp, slik at du kan utføre et oppkall til API-en etter du har valgt hvilke operasjoner som skal utføres. Appen skal nå se ut som på følgende bilde.
   
    ![App med avmerkingsbokser og knapp](./media/cognitive-services-api/partial-app-step2.png)

7. Legg til tre **Etikett**-kontroller. De første to inneholder resultater fra språk- og sentiment-API-oppkall. Den tredje er bare en introduksjon for galleriet nederst på skjermen.

8. Legg til en kontroll for **Tomt loddrett galleri**, og legg deretter til en **Etikett**-kontroll i galleriet. Galleriet inneholder resultater fra nøkkeluttrykk-API-oppkallet. Appen skal nå se ut som på følgende bilde.
   
    ![App med etiketter og galleri](./media/cognitive-services-api/partial-app-step3.png)

9. Velg **Screen1** > ellipse (**. . .**) > **Slett** (du trenger ikke denne skjermen i appen).

Vi lar appen være enkel å bruke, så vi kan fokusere på oppkall til API-en for tekstanalyse, men du kan legge til ting som logikk for å vise og skjule kontroller som er basert på hvilke avmerkingsbokser som er merket, feilhåndtering hvis brukeren ikke velger et alternativ osv.

### <a name="add-logic-to-make-the-right-api-calls"></a>Legge til logikk for å lage riktige API-oppkall
Du har nå en flott app, men den kan ikke gjøre noe ennå. Dette fikser du om litt. Før vi går nærmere inn på detaljer må vi sette oss inn i hvilket mønster appen følger:

1. Appen utfører bestemte API-oppkall basert på avmerkingsboksene i appen. Når du klikker eller trykker på **Analysere tekst**, utfører appen 1, 2 eller 3 API-oppkall.

2. Appen lagrer data som API-en returnerer i tre forskjellige [samlinger](working-with-variables.md#create-a-collection): **languageCollect**, **sentimentCollect** og **phrasesCollect**.

3. Appen oppdaterer **Tekst**-egenskapen for to av etikettene og **Elementer**-egenskapen for galleriet, basert på hva som er i de tre samlingene.

Med dette som bakgrunn kan vi legge til formelen for **OnSelect**-egenskapen for knappen. Det er her det spennende skjer.

```
If(chkLanguage.Value=true,

        ClearCollect(languageCollect, TextAnalytics.DetectLanguage({numberOfLanguagesToDetect:1, text:tiTextToAnalyze.Text}).detectedLanguages.name)

);

If(chkPhrases.Value=true,

        ClearCollect(phrasesCollect, TextAnalytics.KeyPhrases({language:"en", text:tiTextToAnalyze.Text}).keyPhrases)

);

If(chkSentiment.Value=true,

        ClearCollect(sentimentCollect, TextAnalytics.DetectSentiment({language:"en", text:tiTextToAnalyze.Text}).score)

)
```

Det foregår mye på en gang her, så la oss dele det opp:

* **If**-utrykk er enkle – hvis en bestemt avmerkingsboks er merket, utføres API-oppkall for denne operasjonen.

* Angi riktige parametere i hvert oppkall:

  * Angi **tiTextToAnalyze.Text** som inndatatekst i alle tre oppkall.

  * **numberOfLanguagesToDetect** programmeres som 1 i **DetectLanguage()**, men du kan sende denne parameteren basert på logikk i appen.

  * **Språk** programmeres som «en» i **KeyPhrases()** og **DetectSentiment()**, men du kan sende denne parameteren basert på logikk i appen. Du kan for eksempel identifisere språket først, og deretter angi parameteren basert på hva som returneres av **DetectLanguage()**.

* For hvert oppkall som utføres, legger du til resultatet i riktig samling:

    * For **languageCollect** legger du til **navnet** på språket som ble identifisert i teksten.

    * For **phrasesCollect** legger du til **keyPhrases** som ble identifisert i teksten.

    * For **sentimentCollect** legger du til en sentiment-**poengsum** for teksten, som er en verdi på 0-1, der 1 er 100 % positiv.

### <a name="display-the-results-of-the-api-calls"></a>Visning av resultater for API-oppkall
Hvis du vil vise resultatene for API-oppkall, må det refereres til riktig samling i hver kontroll:

1. Angi **Tekst**-egenskapen for språketiketten til: `"The language detected is " & First(languageCollect).name`.
   
    **First()**-funksjonen returnerer den første (og i dette tilfelle den eneste) posten i **languageCollect**, og appen viser **navnet** (det eneste feltet) som er tilknyttet denne posten.

2. Angi **Tekst**-egenskapen for sentimentetiketten til: `"The sentiment score is " & Round(First(sentimentCollect.Value).Value, 3)\*100 & "% positive."`.
   
    Denne formelen bruker også **First()**-funksjonen, henter **Verdien** (0-1) fra den første og eneste posten og formaterer den deretter som en prosentdel.

3. Angi **Elementer**-egenskapen for nøkkeluttrykkgalleriet til: `phrasesCollect`.
   
    Du arbeider nå med et galleri, slik at du ikke trenger **First()**-funksjonen til å trekke ut en enkeltverdi. Du refererer til samlingen, og galleriet viser nøkkeluttrykkene som en liste.

## <a name="run-the-app"></a>Kjør appen

Nå som appen er ferdigstilt, kan du kjøre den for å se hvordan den fungerer. Klikk eller trykk på Kjør-knappen i øvre høyre hjørne ![Kjør appen](./media/cognitive-services-api/icon-run-app.png). I det følgende bildet er alle tre alternativene merket, og teksten er den samme som standardteksten på siden API for tekstanalyse.

![Ferdigstilt app med data](./media/cognitive-services-api/finished-app.png)

Hvis du sammenligner utdataene for denne appen med siden API for tekstanalyse i begynnelsen av denne artikkelen, ser du at resultatene er de samme.

Vi håper at du nå forstår litt mer om API-en for tekstanalyse, og at du har hatt nytte av å se hvordan du kan bygge den inn i en app. Fortell oss om det er andre Cognitive Services (eller andre tjenester generelt) du vil vi skal fokusere på i artiklene våre. Som alltid ønsker vi tilbakemeldinger og spørsmål i kommentarfeltet.

