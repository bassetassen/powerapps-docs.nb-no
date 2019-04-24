---
title: Personer-skjermen malen | Microsoft Docs
description: Forstå hvordan personer-skjermen malen for lerret-apper fungerer og hvordan du utvider skjermen for din egen brukstilfeller
author: emcoope-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 12/30/2018
ms.author: emcoope
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 85da6f5414cc25d1145f0fa8910e8c78bfb74533
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/23/2019
ms.locfileid: "61536158"
---
# <a name="overview-of-the-people-screen-template-for-canvas-apps"></a>Oversikt over personer-skjermen malen for lerretsapper

I en lerretsapp, kan du legge til en skjerm for personer som lar brukere søke etter personer i organisasjonen. Brukere kan søke etter, velg og legge til personer i en samling. Du kan endre hvilke typer data vises i galleriet Søk resultatet, Bruk valgene dine personer til å sende en e-post, og gjøre andre tilpasninger.

Du kan også legge til andre malbaserte skjermer som viser ulike data fra Office 365, som [e-post](email-screen-overview.md), en brukers [kalender](calendar-screen-overview.md), og [tilgjengelighet](meeting-screen-overview.md) personer kan brukere vil invitere til et møte.

Denne oversikten lærer deg:
> [!div class="checklist"]
> * Slik bruker du standard personer skjermen.
> * Hvordan du endrer skjermen.
> * Hvordan du integrerer skjermen i apper.

Hvis en nærmere titt på denne skjermen standard funksjonalitet, kan du se den [personer-skjermen referanse](people-screen-reference.md).

## <a name="prerequisite"></a>Forutsetning

Kjennskap til hvordan du legger til og konfigurerer skjermbilder og andre kontroller som du [oppretter en app i PowerApps](../data-platform-create-app-scratch.md).

## <a name="default-functionality"></a>Standard-funksjonalitet

Å legge til en skjerm for personer fra malen:

1. [Logg deg på](http://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) til PowerApps, og deretter opprette en app eller åpne en eksisterende app i PowerApps Studio.

    Dette emnet viser en telefonapp, men samme konsepter gjelder for en nettbrett-app.

1. På den **Hjem** -fanen på båndet, velg **ny skjerm** > **personer**.

    Som standard ser skjermen omtrent slik ut:

    ![Første personer skjermen tilstand](media/people-screen/people-screen-empty.png)

1. Velg tekstinndata-boksen øverst for å begynne å søke etter brukere, og Skriv inn en kollega navn. Resultatene vises under tekstinndata-boksen:

    ![personer skjermen Søk tilstand](media/people-screen/people-browse-gall-full.png)

1. Når du velger enkeltpersoner i søkeresultatene, legges de til den **MyPeople** samling. Søket stolpe inndataverdien er tilbakestilt, å avsløre samlingen av personer du har valgt:

    ![personer skjermen samling resultater](media/people-screen/people-people-gall-full.png)

## <a name="modify-the-screen"></a>Endre skjermen

Du kan endre standardfunksjonaliteten til denne skjermen ved [som viser ulike data for personer](people-screen-overview.md#show-different-data-for-people).

Hvis du vil endre skjermen ytterligere, kan du bruke den [personer-skjermen referanse](./people-screen-reference.md) som en veiledning.

### <a name="show-different-data-for-people"></a>Vis forskjellige data for personer

Denne skjermen bruker den [Office365Users.SearchUser](https://docs.microsoft.com/connectors/office365users/#searchuser) operasjonen til å søke etter brukere i din organisasjon. Den gir flere felt for hver hendelse utover hva, vises i den **UserBrowseGallery** kontroll. Legge til eller endre feltene i galleriet er en enkel prosess:

1. I den **UserBrowseGallery**, velg en etikett til å endre (eller Legg til en og holde dem valgt).

1. Med sin **tekst** egenskapen som er valgt, på formellinjen, erstatter innholdet med `ThisItem.`

    IntelliSense viser en liste over felt som du kan velge.

1. Velg feltet du vil bruke.

    Den **tekst** egenskapen bør oppdatere til `ThisItem.{FieldSelection}`.

## <a name="integrate-the-screen-into-an-app"></a>Integrere skjermen i en app

Skjermbildet personer er en kraftig gruppe av kontroller i seg selv, men det utfører vanligvis beste som en del av en større, mer allsidig app. Du kan integrere dette skjermbildet i en større app på en rekke måter, inkludert [ved hjelp av hurtigbufrede listen over personer](people-screen-overview.md#use-your-cached-list-of-people).

### <a name="use-your-cached-list-of-people"></a>Bruk bufrede listen over personer

Skjermbildet personer bufrer valgene dine personer i den **MyPeople** samling. Bør forretningsscenarioene kalle for en person-oppslag, må du vite hvordan du kan bruke denne samlingen. Her kan du gå gjennom hvordan du kobler denne skjermen til en skjerm med enkle e-post og send e-postmeldinger til brukere i den **MyPeople** samling. Du får også innsikt i hvordan de [e-post-skjermen](./email-screen-overview.md) fungerer.

1. Legg til Office 365 Outlook datakilden i appen ved å velge den **Vis** fanen, velge **datakilder** > **Legg til datakilde**, og ser etter kontoret 365 outlook connector. Du må kanskje velge **ny tilkobling** å finne den.
1. Når du setter inn skjermbildet personer, kan du sette inn en ny tom skjerm. I dette skjermbildet, kan du legge til et ikon for tilbake-pilen, to bokser for innskriving av tekst og en send-ikonet.
1. Gi nytt navn til skjermen for å **EmailScreen**, ikonet for tilbake-pilen til **BackIcon**, én innskriving av tekst for å **SubjectLine**, den andre til **MessageBody**, og send-ikonet til **SendIcon**.
1. Angi den **OnSelect** -egenskapen for **BackIcon** til `Back()`.
1. Angi den **OnSelect** -egenskapen for **SendIcon** til denne formelen:

    ```powerapps-dot
    Office365.SendEmail( 
        Concat( MyPeople, UserPrincipalName & ";" ), 
        SubjectLine.Text, 
        MessageBody.Text 
    )
    ```
    
    Her kan bruker du Outlook connector til å sende en e-post. Du sender den `Concat(MyPeople, UserPrincipalName & ";")` som listen over mottakere. Denne formelen Kjeder sammen alle e-postadressene i den **MyPeople** samlingen inn i en enkelt streng med semikolon, for å skille dem. Dette er ikke forskjellig fra å skrive ut en streng med e-postadresser atskilt med semikolon i "Til"-linjen i din foretrukne e-postklient.
    * Du kan overføre `SubjectLine.Text` som emne i meldingen, og `MessageBody.Text` som brødteksten i meldingen.
1. Sett inn på skjermbildet personer i hjørnet øverst til høyre i **e-post** ikonet.
   Endre ikonfarge til det passer deg.
1. Angi den **OnSelect** -egenskapen for den **SendIcon** til `Navigate( EmailScreen, None )`.

    Du har nå en app med to skjermer der du kan velge brukere, skriver en e-postmelding til dem, og deretter sende den. Du kan teste den ut, men vær forsiktig, da de appen sender e-postmeldinger til alle du legge til den **MyPeople** samling.

## <a name="next-steps"></a>Neste trinn

* [Vis referansedokumentasjon for denne skjermen](./people-screen-reference.md).
* [Finn ut mer om Office 365 Outlook connector](../connections/connection-office365-outlook.md).
* [Finn ut mer om Office 365-brukere connector](../connections/connection-office365-users.md).
