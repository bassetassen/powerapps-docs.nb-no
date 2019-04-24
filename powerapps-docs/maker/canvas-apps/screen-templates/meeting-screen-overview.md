---
title: Møte-skjermen malen | Microsoft Docs
description: Forstå hvordan møte-skjermen malen for lerret-apper fungerer, og Utvid skjermen for din egen brukstilfeller
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
ms.openlocfilehash: 24f04ff9ce95f603f5f7d4dc7d217146b9eebef8
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/23/2019
ms.locfileid: "61535992"
---
# <a name="overview-of-the-meeting-screen-template-for-canvas-apps"></a>Oversikt over møte-skjermen malen for lerretsapper

I en lerretsapp, kan du legge til en skjerm for møte som lar brukere opprette og sende møteforespørsler fra Office 365 Outlook-kontoene sine. Brukere kan søke etter deltakere i deres organisasjon og legge til eksterne e-postadresser. Hvis tenanten har møterom som er innebygd i Outlook, kan brukere velge en lokasjon, i tillegg.

Du kan også legge til andre malbaserte skjermer som viser ulike data fra Office 365, som [e-post](email-screen-overview.md), [personer](people-screen-overview.md) i en organisasjon, og en brukers [kalender](calendar-screen-overview.md).

Denne oversikten lærer du om funksjonene på høyt nivå av skjermen.

Hvis en nærmere titt på denne skjermen standard funksjonalitet, kan du se den [møte-skjermen referanse](meeting-screen-reference.md).

## <a name="prerequisite"></a>Forutsetning

Kjennskap til hvordan du legger til og konfigurerer skjermbilder og andre kontroller som du [oppretter en app i PowerApps](../data-platform-create-app-scratch.md).

## <a name="default-functionality"></a>Standard-funksjonalitet

Å legge til en skjerm for møte fra malen:

1. [Logg deg på](http://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) til PowerApps, og deretter opprette en app eller åpne en eksisterende app i PowerApps Studio.

    Dette emnet viser en telefonapp, men samme konsepter gjelder for en nettbrett-app.

1. På den **Hjem** -fanen på båndet, velg **ny skjerm** > **møte**.

  Når utfylt, begge fanene av skjermbildet møte se omtrent slik ut:

  ![Møte skjermen, begge kategorier](media/meeting-screen/meeting-screen-full-both.png)

Noen nyttige notater:

* Skjermbildet møte kan en appbruker til å opprette et møte i Outlook.
  Brukere kan søke etter og legge til deltakere og, du kan også legge til et møterom til møtet.
* Begynn å skrive navnet i tekstinndata-boksen under «Deltakere» for å søke etter en bruker i organisasjonen.
* Når du søker etter personer, returneres bare de øverste 15 resultatene.
* Hvis du vil legge til e-postadresser for deltakere utenfor organisasjonen, Skriv ut full, gyldig e-postadressen, og velg "+" ikonet som vises til høyre for e-postadressen.
* Hvis du vil opprette et møte, må du legge til minst én person som en deltaker, angi et emne, og velg et møtetidspunkt i den **tidsplan** fanen.
* Når du har sendt forespørselen møte, fjernes all informasjon for møtet.
* Den **OnSelect** setning i Send-ikonet (øverst i høyre hjørne) inneholder denne formelen:
    ```powerapps-dot
    Set( _myCalendarName, 
        LookUp( 'Office365'.CalendarGetTables().value, DisplayName = "Calendar" ).Name 
    );
    ```
* "Kalender" er standard visningsnavn for de fleste Office-brukeres kalendere, men organisasjonen kan variere. I så fall kan du endre "Kalender" til den riktige perioden for din organisasjon.
* Du får en feilmelding hvis du prøver å planlegge et møte som er passert, eller legge til mer enn 20 personer til et møte.

## <a name="next-steps"></a>Neste trinn

* [Vis referansedokumentasjon for denne skjermen](./meeting-screen-reference.md).
* [Finn ut mer om Office 365 Outlook connector](../connections/connection-office365-outlook.md).
* [Finn ut mer om Office 365-brukere connector](../connections/connection-office365-users.md).
