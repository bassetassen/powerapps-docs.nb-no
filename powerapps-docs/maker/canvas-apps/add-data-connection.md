---
title: Legg til en datatilkobling i en lerretsapp | Microsoft Docs
description: Legg til en datatilkobling i en eksisterende lerretsapp eller en tom app
author: lancedMicrosoft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 04/06/2018
ms.author: lanced
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 15f3f38dd4812ffcbebeeaab4d301f715c97e1d1
ms.sourcegitcommit: be110258910aa097b0065da1ee4ea1c40b7e1334
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 05/20/2019
ms.locfileid: "65922543"
---
# <a name="add-a-data-connection-to-a-canvas-app-in-powerapps"></a>Legg til en datatilkobling i en lerretsapp i PowerApps

Legg til en datatilkobling i en eksisterende lerretsapp eller i en app du oppretter fra grunnen av, i PowerApps. Appen kan koble til SharePoint, Common Data Service, Salesforce, OneDrive, eller [mange andre datakilder](connections-list.md).

Det [neste trinnet](#next-steps) etter denne artikkelen er å vise og behandle data fra datakilden i appen din, som i disse eksemplene:

* Koble til OneDrive, og behandle data i en Excel-arbeidsbok i appen din.
* Koble til Twilio, og send en SMS-melding fra appen din.
* Koble til Common Data Service, og oppdatere en enhet fra appen din.
* Koble til SQL Server, og oppdater en tabell fra appen din.

## <a name="prerequisites"></a>Forutsetninger

[Registrer deg](../signup-for-powerapps.md) for PowerApps, og deretter [logger du deg på](http://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) ved å angi samme legitimasjon som du brukte til å registrere deg.

## <a name="open-a-blank-app"></a>Å åpne en tom app

1. På den **Hjem** fanen og velge **lerretsapp fra tom**.

1. Angi et navn for appen din, og velg deretter **Opprett**.

1. Hvis dialogboksen **Velkommen til PowerApps Studio** vises, klikker eller trykker du på **Hopp over**.

## <a name="add-data-source"></a>Å legge til en datakilde

1. I den midtruten, velger du **koble til data** å åpne den **Data** ruten.

    Hvis dette er en eksisterende app, og skjermbildet som allerede finnes en kontroll, velger **Vis** > **datakilder** å åpne den samme ruten.

1. Velg **Legg til datakilde**.

1. Hvis listen over tilkoblinger inneholder tilkoblingen du ønsker, kan du velge den for å legge den til appen. Ellers hopper du til neste trinn.

    ![Velg en eksisterende tilkobling](./media/add-data-connection/choose-existing-connection.png)

1. Velg **ny tilkobling** til å vise en liste over tilkoblinger.

    ![Legg til en tilkobling](./media/add-data-connection/add-connection.png)

1. I søkefeltet, skriver du inn eller lime inn de første bokstavene i tilkoblingen du ønsker, og velg deretter tilkoblingen når den vises.

    ![Søk etter en tilkobling](./media/add-data-connection/search-connections.png)

1. Velg **Opprett** for å både opprette tilkoblingen og legge den til i appen din.

    Noen koblinger, for eksempel **Office 365 Outlook**, krever ingen flere trinn, og du kan vise data fra dem umiddelbart. Andre koblinger anmoder deg om å angi legitimasjon, et bestemt datasett, eller om å utføre andre trinn. [SharePoint](connections/connection-sharepoint-online.md) og [SQL Server](connections/connection-azure-sqldatabase.md) krever for eksempel tilleggsinformasjon før du kan bruke dem. Med [Common Data Service-](connections/connection-common-data-service.md), kan du endre miljøet før du velger en enhet.

## <a name="identify-or-change-a-data-source"></a>Å identifisere eller endre en datakilde
Hvis du oppdaterer en app, må du kanskje identifisere eller endre kilden til dataene som vises i et galleri, et skjema eller en annen kontroll. Du må for eksempel kanskje identifisere en datakilde som du oppdaterer en app som noen andre har opprettet, eller som du opprettet for lenge siden.

1. Velg en kontroll, for eksempel et galleri, som du vil identifisere eller endre datakilden.

    Navnet på datakilden vises i **Egenskaper**-fanen på flisen i ruten til høyre.

    ![Identifisere en tilkobling](./media/add-data-connection/identify-connection.png)

1. Å vise mer informasjon om datakilden eller endre den, velger du pil ned ved siden av navnet.

    Hvis du vil ha mer informasjon om gjeldende datakilden vises, og du kan velge eller opprette en annen kilde.

    ![Endre en tilkobling](./media/add-data-connection/change-connection.png)

## <a name="next-steps"></a>Neste trinn

* Vise og oppdatere data i en datakilde, for eksempel Excel, SharePoint, Common Data Service-eller SQL Server, [legge til et galleri](add-gallery.md), og [legge til et skjema](add-form.md).
* Hvis du vil bruke data i andre kilder, kan du bruke spesifikke funksjoner for kobling, for eksempel i [Office 365 Outlook](connections/connection-office365-outlook.md), [Twitter](connections/connection-twitter.md) og [Microsoft Translator](connections/connection-microsoft-translator.md).
