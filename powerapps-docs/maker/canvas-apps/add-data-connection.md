---
title: Legg til en datatilkobling i en lerretsapp | Microsoft Docs
description: Legg til en datatilkobling i en eksisterende lerretsapp eller en tom app
author: lancedMicrosoft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 04/06/2018
ms.author: lanced
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 2ce09240aa30c1f98926fb109a57f63c230e8d4b
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/07/2019
ms.locfileid: "71987644"
---
# <a name="add-a-data-connection-to-a-canvas-app-in-powerapps"></a>Legg til en datatilkobling i en lerretsapp i PowerApps

Legg til en datatilkobling i en eksisterende lerretsapp eller i en app du oppretter fra grunnen av, i PowerApps. Appen kan koble til SharePoint, Common Data Service, Salesforce, OneDrive eller [mange andre data kilder](connections-list.md).

Det [neste trinnet](#next-steps) etter denne artikkelen er å vise og behandle data fra datakilden i appen din, som i disse eksemplene:

* Koble til OneDrive, og behandle data i en Excel-arbeidsbok i appen din.
* Koble til Twilio, og send en SMS-melding fra appen din.
* Koble til Common Data Service, og Oppdater en enhet fra appen.
* Koble til SQL Server, og oppdater en tabell fra appen din.

## <a name="prerequisites"></a>Forutsetninger

[Registrer deg](../signup-for-powerapps.md) for PowerApps, og deretter [logger du deg på](http://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) ved å angi samme legitimasjon som du brukte til å registrere deg.

## <a name="open-a-blank-app"></a>Å åpne en tom app

1. Velg **lerrets app fra tomt**på **hjem** -fanen.

1. Angi et navn for appen, og velg deretter **Opprett**.

1. Hvis dialogboksen **Velkommen til PowerApps Studio** vises, klikker eller trykker du på **Hopp over**.

## <a name="add-data-source"></a>Å legge til en datakilde

1. Velg **Koble til data** i den midtre ruten for å åpne **data** -ruten.

    Hvis dette var en eksisterende app og skjermen allerede inneholdt en kontroll, velger du **vis** > **data kilder** for å åpne den samme ruten.

1. Velg **Legg til data kilde**.

1. Hvis listen over tilkoblinger inkluderer den du ønsker, kan du velge den for å legge den til i appen. Ellers hopper du til neste trinn.

    ![Velg en eksisterende tilkobling](./media/add-data-connection/choose-existing-connection.png)

1. Velg **ny tilkobling** for å vise en liste over tilkoblinger.

    ![Legg til en tilkobling](./media/add-data-connection/add-connection.png)

1. Skriv eller lim inn de første bokstavene i tilkoblingen du ønsker i søke feltet, og velg deretter tilkoblingen når den vises.

    ![Søk etter en tilkobling](./media/add-data-connection/search-connections.png)

1. Velg **Opprett** for å både opprette tilkoblingen og legge den til i appen din.

    Noen koblinger, for eksempel **Office 365 Outlook**, krever ingen flere trinn, og du kan vise data fra dem umiddelbart. Andre koblinger anmoder deg om å angi legitimasjon, et bestemt datasett, eller om å utføre andre trinn. [SharePoint](connections/connection-sharepoint-online.md) og [SQL Server](connections/connection-azure-sqldatabase.md) krever for eksempel tilleggsinformasjon før du kan bruke dem. Med [Common data service](connections/connection-common-data-service.md)kan du endre miljøet før du velger en enhet.

## <a name="identify-or-change-a-data-source"></a>Å identifisere eller endre en datakilde
Hvis du oppdaterer en app, må du kanskje identifisere eller endre kilden til dataene som vises i et galleri, et skjema eller en annen kontroll. Det kan for eksempel hende at du må identifisere en data kilde når du oppdaterer en app som noen andre har opprettet, eller som du har opprettet for lenge siden.

1. Velg kontrollen, for eksempel et galleri, som du vil identifisere eller endre data kilden for.

    Navnet på datakilden vises i **Egenskaper**-fanen på flisen i ruten til høyre.

    ![Identifiser en tilkobling](./media/add-data-connection/identify-connection.png)

1. Hvis du vil vise mer informasjon om data kilden eller endre den, velger du pil ned ved siden av navnet.

    Mer informasjon om den gjeldende data kilden vises, og du kan velge eller opprette en annen kilde.

    ![Endre en tilkobling](./media/add-data-connection/change-connection.png)

## <a name="next-steps"></a>Neste trinn

* Hvis du vil vise og oppdatere data i en kilde, for eksempel Excel, SharePoint, Common Data Service eller SQL Server, kan du [legge til et galleri](add-gallery.md)og [legge til et skjema](add-form.md).
* Hvis du vil bruke data i andre kilder, kan du bruke spesifikke funksjoner for kobling, for eksempel i [Office 365 Outlook](connections/connection-office365-outlook.md), [Twitter](connections/connection-twitter.md) og [Microsoft Translator](connections/connection-microsoft-translator.md).
