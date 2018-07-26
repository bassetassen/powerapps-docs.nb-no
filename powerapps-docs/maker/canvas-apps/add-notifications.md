---
title: Sende et push-varsel i Microsoft Docs
description: Finn ut hvordan du sender opprinnelige push-varsler til en app i PowerApps.
author: jamesol-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 08/08/2017
ms.author: jamesol
ms.openlocfilehash: f9b606246b0b1114aec1bec2fc2767b518215148
ms.sourcegitcommit: 0e9af8cace2bdc04750f4c5a70a3c4af8e3d2292
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 07/22/2018
ms.locfileid: "39195569"
---
# <a name="send-a-push-notification-in-powerapps"></a>Send et push-varsel i PowerApps
Push-varsler brukes hovedsakelig i mobilapper for forbruker- og forretningsscenarioer for å engasjere brukere og hjelpe dem med å prioritere viktige oppgaver. I PowerApps kan du sende varsler ved å bruke PowerApps Notification-koblingen. Du kan sende opprinnelige push-varsler til alle apper du lager i PowerApps. Vi har planer om å legge til flere typer varsler i fremtiden.

![Eksempel på hvordan et push-varsel ser ut](./media/add-notifications/pic1-notification-screenshot.png)

Legg til push-varsler i appen hvis:

* brukerne dine har behov for øyeblikkelig informasjon
* brukerne må fullføre viktige oppgaver ved å bruke appen din i en forhåndslastet kontekst
* du ønsker å engasjere brukerne dine med bestemte intervaller, eller hvis du har behov for at brukerne åpner appen i en bestemt kontekst

> [!NOTE]
> For å motta push-varsler må brukeren ha åpnet appen i PowerApps Mobile én gang eller hentet appen fra AppSource i [Dynamics 365](https://home.dynamics.com/).

## <a name="before-you-start"></a>Før du starter
Legg til en PowerApps Notification-tilkobling i en app der du har **Bidragsyter**-tillatelse. Hvis du ikke allerede har en app, kan du raskt [lage en app fra en mal](get-started-test-drive.md) og som standard ha den nødvendige tillatelsen. Både den allerede nevnte opplæringen og denne opplæringen bruker en app som er basert på Case Management-malen.

## <a name="send-a-notification-from-a-flow"></a>Å sende et varsel fra en flyt
> [!NOTE]
> På det nåværende tidspunktet kan du sende et push-varsel du utløser fra en flyt til kun én bruker eller sikkerhetsgruppe om gangen.

1. Opprett en utløser i [Microsoft Flow](https://flow.microsoft.com), som angir når push-varselet skal sendes.

    Du ønsker for eksempel kanskje å sende et varsel når en post legges til i **Saks**-enheten i Common Data Service.

    ![Skjermbilde av oppretting av en flyt med en Common Data Service-utløser](./media/add-notifications/pic4-step1-flowupdated.png)
2. Opprett en handling for flyten ved å bruke **PowerApps Notification**-koblingen, og angi **App-ID** for appen du vil sende varsler til.

    Du kan også gi nytt navn til tilkoblingen for å gjenspeile scenarioet.

    ![Skjermbilde av oppretting av en kobling til PowerApps som vil motta disse push-varslene](./media/add-notifications/pic5-step2-create-connection.jpg)
3. (valgfritt) Send parametre til appen når den åpnes (etter at brukeren har trykket på push-varselet).

    I eksemplet vårt sender vi feltene **Saks-ID** og **Opprinnelig eier** for den valgte kontakten.

    ![Skjermbilde av sending av valgfrie parametre til push-varselet](./media/add-notifications/pic6-step3-configure-notif.jpg)

## <a name="send-a-notification-from-an-app"></a>Send et varsel fra en app
Du kan sende et push-varsel fra en app til en annen, eller til den samme appen.

1. Åpne [PowerApps](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc), og gå til appen du ønsker å sende push-varsler til.
2. Kopier **App-ID** for denne appen under fanen**Detaljer**.

    ![Hent App-ID](./media/add-notifications/grab-id.png)
3. Under fanen **Tilkoblinger** oppretter du en tilkobling til PowerApps Notifications-koblingen og limer inn app-ID-en du kopierte i forrige trinn.

    ![Opprett tilkobling](./media/add-notifications/create-connection.png)
4. Legg til tilkoblingen i utløserappen.

    I eksemplet vårt bruker vi den samme appen som utløserapp. Brukeren som overfører saken på nytt, utløser også et push-varsel til den nye sakseieren.

    ![Legg til en tilkobling](./media/add-notifications/add-connection.png)
5. Kall opp **SendPushNotification**-metoden fra push-varseltilkoblingen.

    I eksemplet vårt utløser vi dette varselet ved å bruke **OnSuccess**-egenskapen i et skjema.

    ![PowerApps-formel](./media/add-notifications/powerapps-function.png)

## <a name="load-a-specific-page-and-context-when-a-user-taps-the-notification"></a>Last inn en bestemt side og kontekst når brukeren trykker på varselet
### <a name="pass-parameters"></a>Send parametre
Push-varselet kan sende bestemte parametre til appen. Bruk for eksempel *Param("CaseID")* for å lese **CaseID**-verdien. Denne parameteren kan raskt identifiseres ved å legge til en **Etikett**-kontroll i appen. Angi**Tekst**-egenskapen for denne kontrollen til **Param("CaseID")**. Hvis brukeren åpner appen fra listen **Alle apper**, er verdien tom. Hvis brukeren åpner appen fra en annen plassering på enheten, er verdien utfylt med**Saks-ID**-verdien.

### <a name="set-the-start-page"></a>Å angi startside
Du kan for eksempel angi at appen skal åpne siden **Saksdetaljer** når du åpner appen:

1. Legg til en **Tidtaker**-kontroll, og angi **OnTimerEnd**-egenskapen for denne kontrollen i denne formelen:
   <br>**Navigate(EditCase, ScreenTransition.None)**
2. (valgfritt) Skjul **Tidtaker**-kontrollen ved å angi kontrollens egenskap for **Synlighet** som **usann**.
3. Angi**OnVisible**-egenskapen for skjermbildet til **Timer.Start()**.

> [!TIP]
> Det er en god ide å opprette en unik førsteside for varselet i appen:
> 
> 1. Opprett en tom side som appen ikke allerede åpner, legg til en **Tekstinndata**-kontroll og angi kontrollens **timer.Duration**-verdi.
> 2. Når du oppretter appen, angir du en verdi for tidtakeren som ikke er null. Når du er klar til å publisere appen, angir du verdien til **0** for umiddelbart å utløse tidtakeren.

## <a name="syntax"></a>Syntaks

| Navn | Beskrivelse |
| --- | --- |
| SendPushNotification |Sender et push-varsel til appen som er angitt i tilkoblingsinnstillingene for varselet. |

### <a name="parameters"></a>Parametere

| Navn | Type | Beskrivelse |
| --- | --- | --- |
| mottakere |Strengmatrise, obligatorisk |En liste over: <ul> <li>e-postadresser for brukere eller sikkerhetsgrupper</li> <li>objekt-ID-er for brukere eller sikkerhetsgrupper i Azure Active Directory</li></ul> |
| melding |Streng, obligatorisk |Meldingsteksten i push-varselet. |
| openApp |Boolsk, valgfritt |Hvorvidt en app skal åpnes når brukeren trykker på push-varselet. |
| params |Parametere, valgfritt |Nøkkelverdiparametere som skal sendes med varselet. Disse kan behandles ytterligere i appen for å åpne en bestemt side og laste inn en bestemt tilstand. |

### <a name="sample-formulas"></a>Eksempler på formler
Send et enkelt varsel.

```
PowerAppsNotification.SendPushNotification(
{
  recipients: [""f60ccf6f-7579-4f92-967c-2920473c966b", 72f988bf-86f1-41af-91ab-2d7cd011db47],
  message: "A new case was assigned to you."
 }
)
```

Send et varsel som åpner en app og sender bestemte parametere.

```
PowerAppsNotification.SendPushNotification(
{
  recipients:["email1@contoso.com", "email2@contoso.com"],
  message:"message in the notif toast",
  params:Table({key:"notificationKey", value:"The value for notificationKey"}),
  openApp:true
 }
)
```

## <a name="known-limitations"></a>Kjente begrensninger
* På nåværende tidspunkt vises ikke varsler i PowerApps Mobile for Windows Phone.
* På nåværende tidspunkt leverer vi ikke push-varsler for brukere som kjører apper bare i en nettleser.
* Varsler viser det generiske PowerApps-ikonet i stedet for et bestemt appikon.
* Når du bruker Microsoft Flow, kan du sende push-varsler bare til én mottaker om gangen.

Du finner referanseinformasjon under [Referanse for PowerApps-varsler](https://docs.microsoft.com/connectors/powerappsnotification/).

