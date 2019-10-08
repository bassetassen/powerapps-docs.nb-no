---
title: Mal for møte visning | Microsoft Docs
description: Forstå hvordan malen for møte skjermen for lerret apper fungerer, og Utvid skjermen for dine egne bruks tilfeller
author: emcoope-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 12/30/2018
ms.author: emcoope
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: c53857acfdcb44faa26b2ec3e04b904e25c09aee
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/07/2019
ms.locfileid: "71995642"
ms.PowerAppsDecimalTransform: true
---
# <a name="overview-of-the-meeting-screen-template-for-canvas-apps"></a>Oversikt over malen for møte skjermen for lerret apper

Legg til en møte skjerm i en lerret-app som lar brukere opprette og sende møte forespørsler fra Office-365 Outlook-kontoene. Brukere kan søke etter deltakere i organisasjonen og legge til eksterne e-postadresser. Hvis leieren har møterom som er innebygd i Outlook, kan brukerne også velge en plassering.

Du kan også legge til andre mal BAS ert skjermer som viser ulike data fra Office 365, for eksempel [e-post](email-screen-overview.md), [personer](people-screen-overview.md) i en organisasjon og en brukers [Kalender](calendar-screen-overview.md).

Denne oversikten lærer deg om skjermens høyeste nivå funksjonalitet.

Hvis du vil ha en dypere innsikt i denne skjermens standard funksjon, kan du se [referanse til møte skjermen](meeting-screen-reference.md).

## <a name="prerequisite"></a>Nødvendig

Kjennskap til hvordan du legger til og konfigurerer skjermer og andre kontroller mens du [oppretter en app i powerapps](../data-platform-create-app-scratch.md).

## <a name="default-functionality"></a>Standard funksjonalitet

Slik legger du til en møte skjerm fra malen:

1. [Logg deg](http://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) på powerapps, og opprett deretter en app eller åpne en eksisterende app i PowerApps Studio.

    Dette emnet viser en telefon app, men de samme begrepene gjelder for en tavle-app.

1. På **hjem** -fanen på båndet velger du **ny skjerm** > **møte**.

  Når de er fylt ut, ser begge fanene til møte skjermen lik dette:

  ![Møte skjerm, begge kategorier](media/meeting-screen/meeting-screen-full-both.png)

Noen nyttige notater:

* Med møte skjermen kan en app-bruker opprette et møte i Outlook.
  Brukere kan søke etter og legge til deltakere og legge til et møte rom i møtet.
* Hvis du vil søke etter en bruker i organisasjonen, begynner du å skrive inn navnet i tekst inn data-boksen under deltakere.
* Når du søker etter personer, returneres bare de 15 høyeste resultatene.
* Hvis du vil legge til e-postadresser for deltakere utenfor organisasjonen, skriver du inn den fullstendige, gyldige e-postadressen og velger +-ikonet som vises til høyre for e-postadressen.
* Hvis du vil opprette et møte, må du legge til minst én person som deltaker, oppgi et emne og velge et møte tids punkt i **tids plan** -fanen.
* Når du har sendt møte innkallelsen, fjernes all informasjon om dette møtet.
* **OnSelect** -setningen til Send-ikonet (hjørnet øverst til høyre) inneholder denne formelen:
    ```powerapps-comma
    Set( _myCalendarName; 
        LookUp( 'Office365'.CalendarGetTables().value; DisplayName = "Calendar" ).Name 
    );;
    ```
* «Kalender» er standard visnings navn for de fleste Office-brukerens kalendere, men organisasjonen kan være forskjellig. I så fall kan du endre «kalender» til ønsket vilkår for organisasjonen.
* Du får en feil melding hvis du prøver å planlegge et møte som forekommer tidligere, eller legge til mer enn 20 personer i et møte.

## <a name="next-steps"></a>Neste trinn

* [Vis referanse dokumentasjonen for dette skjerm bildet](./meeting-screen-reference.md).
* [Les mer om Office 365 Outlook Connector](../connections/connection-office365-outlook.md).
* [Finn ut mer om koblingen til Office 365-brukere](../connections/connection-office365-users.md).
