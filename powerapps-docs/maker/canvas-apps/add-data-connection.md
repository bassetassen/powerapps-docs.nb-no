---
title: Slik legger du til en datatilkobling i en app | Microsoft Docs
description: Slik legger du til en datatilkobling i en eksisterende eller en tom app
services: ''
suite: powerapps
documentationcenter: na
author: archnair
manager: anneta
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/02/2017
ms.author: archanan
ms.openlocfilehash: 2134aa28f1b842614e1f4b82acaca2f100126120
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/22/2018
ms.locfileid: "30995957"
---
# <a name="add-a-data-connection-in-powerapps"></a>Slik legger du til en datatilkobling i PowerApps
I PowerApps kan du legge til en datatilkobling i en eksisterende app eller i en app som du oppretter fra grunnen av. I dette emnet bruker du PowerApps Studio, men du kan også bruke [powerapps.com](https://web.powerapps.com), som beskrives i emnet [Behandling av tilkoblinger](add-manage-connections.md).

Appens datatilkobling kan koble til SharePoint, Salesforce, OneDrive eller [én av mange andre datakilder](connections-list.md).

Det [neste trinnet](#next-steps) etter denne artikkelen er å vise og behandle data fra datakilden i appen din, som i disse eksemplene:

* Koble til OneDrive, og behandle data i en Excel-arbeidsbok i appen din.
* Koble til Twilio, og send en SMS-melding fra appen din.
* Koble til SQL Server, og oppdater en tabell fra appen din.

## <a name="prerequisites"></a>Forutsetninger
[Registrer deg](../signup-for-powerapps.md) for PowerApps, [installer](http://aka.ms/powerappsinstall) det, åpne det, og logg deg på ved å oppgi samme legitimasjon som du brukte til å registrere deg.

## <a name="background-on-data-connections"></a>Bakgrunn om datatilkoblinger
De fleste PowerApps-apper bruker ekstern informasjon kalt **datakilder**, som oppbevares i skytjenester. Et vanlig eksempel er en tabell i en Excel-fil lagret i OneDrive for Business. Apper får tilgang til disse datakildene ved hjelp av **Koblinger**.

De vanligste datakildene er tabeller, som du kan bruke til å hente og lagre informasjon. Du kan bruke koblinger til datakilder til å lese og skrive data i Microsoft Excel-arbeidsbøker, SharePoint-lister, SQL-tabeller og mange andre formater, som kan lagres i skytjenester som OneDrive for Business, DropBox, SQL Server osv.

Andre datakilder enn tabeller kan være e-post, kalendere, Twitter og varslinger.

Ved hjelp av kontrollene **[Galleri](controls/control-gallery.md)**, **[Visningsskjema](controls/control-form-detail.md)** og **[Redigeringsskjema](controls/control-form-detail.md)** er det enkelt å opprette en app som leser og skriver data fra en datakilde. Les artikkelen [Å forstå dataskjemaer](working-with-forms.md) for å komme i gang.

## <a name="add-a-connection"></a>Å legge til en tilkobling
1. Klikk eller trykk på **Ny** i **Fil**-menyen (nær den venstre kanten).

    ![Ny-alternativet i Fil-menyen](./media/add-data-connection/file-new.png)

2. Klikk eller trykk på **Telefonoppsett** i **Tom app**-flisen.

    ![Å opprette en app fra grunnen av](./media/add-data-connection/blank-app.png)

3. Klikk eller trykk på **Koble til data** i midtruten.

4. Hvis listen over tilkoblinger i **Data**-ruten inneholder tilkoblingen du ønsker, kan du klikke eller trykke på den for å legge den til i appen. Ellers hopper du til neste trinn.

    ![Å legge til en datakilde](./media/add-data-connection/choose-existing-connections.png)

5. Klikk eller trykk på **Ny tilkobling** for å vise en liste over koblinger.

    ![Å legge til en tilkobling](./media/add-data-connection/new-connection.png)

6. Rull gjennom listen over tilkoblinger til du ser tilkoblingstypen du ønsker å opprette (for eksempel **Office 365 Outlook**), og klikk eller trykk på den.

    ![Å velge en tilkobling](./media/add-data-connection/choose-connection.png)

7. Klikk eller trykk på **Opprett** for å både opprette tilkoblingen og legge den til i appen din.

    Noen koblinger, for eksempel **Microsoft Translator**, krever ingen flere trinn, og du kan vise data fra dem umiddelbart. Andre koblinger anmoder deg om å angi legitimasjon, et bestemt datasett, eller om å utføre andre trinn. [SharePoint](connections/connection-sharepoint-online.md) og [SQL Server](connections/connection-azure-sqldatabase.md) krever for eksempel tilleggsinformasjon før du kan bruke dem.

## <a name="view-or-change-a-data-source"></a>Å vise eller endre en datakilde
Hvis du oppdaterer en app, må du kanskje identifisere eller endre kilden til dataene som vises i et galleri, et skjema eller en annen kontroll som har en **Element**-egenskap. Det kan for eksempel være at du arbeider på en app som noen andre har opprettet, eller at du kanskje ønsker å minne deg selv på en datakilde som du har konfigurert for en stund siden.

1. Velg kontrollen du vil identifisere datakilden til.

    Du kan for eksempel velge et galleri (ikke en kontroll i galleriet) ved å klikke eller trykke på det i den hierarkiske listen over skjermer og kontroller nær venstre kant.

    Navnet på datakilden vises i **Egenskaper**-fanen på flisen i ruten til høyre.

    ![Datakilde på Egenskaper-fanen](./media/add-data-connection/properties-tab.png)

2. Klikk eller trykk på **Data** i ruten til høyre for å vise mer informasjon om datakilden eller bytte den ut.

    ![Datarute](./media/add-data-connection/data-pane.png)

3. Hvis du vil bytte ut datakilden, kan du klikke eller trykke på nedoverpilen ved siden av datakilden og deretter velge eller opprette en annen kilde.

## <a name="next-steps"></a>Neste trinn
* Hvis du vil vise og oppdatere data i en datakilde, for eksempel Excel, SharePoint eller SQL Server, kan du [legge til et galleri](add-gallery.md) og [legge til et skjema](add-form.md).
* Hvis du vil bruke data i andre kilder, kan du bruke spesifikke funksjoner for kobling, for eksempel i [Office 365 Outlook](connections/connection-office365-outlook.md), [Twitter](connections/connection-twitter.md) og [Microsoft Translator](connections/connection-microsoft-translator.md).
