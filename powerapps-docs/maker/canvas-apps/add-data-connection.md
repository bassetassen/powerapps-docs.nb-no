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
ms.openlocfilehash: bf53c71a5dfbbfecbf6a094f26c9866e7f94f84d
ms.sourcegitcommit: e3f5a2bef64085d02aec82e62ff94ae8a4d01d24
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/02/2018
ms.locfileid: "39471056"
---
# <a name="add-a-data-connection-to-a-canvas-app-in-powerapps"></a>Legg til en datatilkobling i en lerretsapp i PowerApps

Legg til en datatilkobling i en eksisterende lerretsapp eller i en app du oppretter fra grunnen av, i PowerApps. Appen kan koble til SharePoint, Salesforce, OneDrive eller [mange andre datakilder](connections-list.md).

Det [neste trinnet](#next-steps) etter denne artikkelen er å vise og behandle data fra datakilden i appen din, som i disse eksemplene:

* Koble til OneDrive, og behandle data i en Excel-arbeidsbok i appen din.
* Koble til Twilio, og send en SMS-melding fra appen din.
* Koble til SQL Server, og oppdater en tabell fra appen din.

## <a name="prerequisites"></a>Forutsetninger

[Registrer deg](../signup-for-powerapps.md) for PowerApps, og deretter [logger du deg på](http://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) ved å angi samme legitimasjon som du brukte til å registrere deg.

## <a name="add-a-data-source"></a>Å legge til en datakilde
1. Hold pekeren over flisen **Start fra grunnen av** på **Hjem**-fanen, og velg deretter **Opprett denne appen.**

    ![Å opprette en app fra grunnen av](./media/add-data-connection/blank-app-tile.png)

1. Hvis dialogboksen **Velkommen til PowerApps Studio** vises, klikker eller trykker du på **Hopp over**.

3. Klikk eller trykk på **Koble til data** i midtruten.

4. Hvis listen over tilkoblinger i **Data**-ruten inneholder tilkoblingen du ønsker, kan du velge den for å legge den til i appen. Ellers hopper du til neste trinn.

    ![Å legge til en datakilde](./media/add-data-connection/choose-existing-connections.png)

5. Velg **Ny tilkobling** for å vise en liste over koblinger.

    ![Legg til en tilkobling](./media/add-data-connection/new-connection.png)

6. Rull gjennom listen over tilkoblinger til du ser tilkoblingstypen du ønsker å opprette (for eksempel **Office 365 Outlook**), og velg den.

    ![Å velge en tilkobling](./media/add-data-connection/choose-connection.png)

7. Velg **Opprett** for å både opprette tilkoblingen og legge den til i appen din.

    Noen koblinger, for eksempel **Office 365 Outlook**, krever ingen flere trinn, og du kan vise data fra dem umiddelbart. Andre koblinger anmoder deg om å angi legitimasjon, et bestemt datasett, eller om å utføre andre trinn. [SharePoint](connections/connection-sharepoint-online.md) og [SQL Server](connections/connection-azure-sqldatabase.md) krever for eksempel tilleggsinformasjon før du kan bruke dem.

## <a name="add-another-data-source"></a>Å legge til en annen datakilde
1. Legg til en kontroll hvor du vil legge til en datakilde.

    Kontrollen må ha en **Elementer**-egenskap, som gallerier og listebokser har, eller en **Element**-egenskap, som et skjema har.

1. I **Data**-ruten (som åpnes automatisk), åpner du listen under **Datakilde**, og deretter velger du **Legg til en datakilde**.

1. Følg fremgangsmåten, fra og med trinn 4.

## <a name="identify-or-change-a-data-source"></a>Å identifisere eller endre en datakilde
Hvis du oppdaterer en app, må du kanskje identifisere eller endre kilden til dataene som vises i et galleri, et skjema eller en annen kontroll. Du må for eksempel kanskje identifisere en datakilde når du oppdaterer en app som noen andre har opprettet, eller som du har opprettet for lenge siden.

1. Velg kontrollen du vil identifisere eller endre datakilden for.

    Du kan for eksempel velge et galleri (ikke en kontroll i galleriet) ved å klikke eller trykke på det i den hierarkiske listen over skjermer og kontroller nær venstre kant.

    Navnet på datakilden vises i **Egenskaper**-fanen på flisen i ruten til høyre.

2. Velg datakilden for å endre den, eller for å vise mer informasjon om den.

    ![Datarute](./media/add-data-connection/data-pane.png)

3. Hvis du vil endre datakilden, åpner du listen over datakilder, og deretter velger eller oppretter du en annen kilde.

     ![Datarute](./media/add-data-connection/datasource-list.png)

## <a name="next-steps"></a>Neste trinn
* Hvis du vil vise og oppdatere data i en datakilde, for eksempel Excel, SharePoint eller SQL Server, kan du [legge til et galleri](add-gallery.md) og [legge til et skjema](add-form.md).
* Hvis du vil bruke data i andre kilder, kan du bruke spesifikke funksjoner for kobling, for eksempel i [Office 365 Outlook](connections/connection-office365-outlook.md), [Twitter](connections/connection-twitter.md) og [Microsoft Translator](connections/connection-microsoft-translator.md).
