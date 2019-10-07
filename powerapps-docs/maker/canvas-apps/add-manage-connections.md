---
title: Legg til og administrer tilkoblinger fra lerretsapper | Microsoft Docs
description: Legg til, slett og oppdater tilkoblinger fra lerretsapper til datakilder, blant annet SharePoint, SQL Server og OneDrive for Business
author: lancedMicrosoft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 03/09/2017
ms.author: lanced
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: ad7f01da3217faa1cd4c55b1d33acd03953434f5
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/07/2019
ms.locfileid: "71987331"
---
# <a name="manage-canvas-app-connections-in-powerapps"></a>Administrer tilkoblinger til lerretsapper i PowerApps
På [powerapps.com](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) kan du opprette tilkobling til en eller flere datakilder, slette en tilkobling eller oppdatere legitimasjon.

Lerretsappens datatilkobling kan kobles til SharePoint, SQL Server, Office 365, OneDrive for Business, Salesforce, Excel og mange andre [datakilder](connections-list.md).

Det neste trinnet etter denne artikkelen er å vise og administrere data fra datakilden i appen din, som i eksemplene under:

* Koble til OneDrive for Business, og administrer data i en Excel-arbeidsbok i appen din.
* Oppdater en liste på et SharePoint-område.
* Koble til SQL Server, og oppdater en tabell fra appen din.
* Send e-post i Office 365.
* Send en tweet.
* Koble til Twilio, og send en SMS-melding fra appen din.

## <a name="prerequisites"></a>Forutsetninger
1. [Registrer deg](../signup-for-powerapps.md) for PowerApps.
2. Logg deg på [powerapps.com](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) med samme legitimasjon som du brukte til å registrere deg.

## <a name="background-on-data-connections"></a>Bakgrunn på datatilkoblinger
De fleste PowerApps-apper bruker ekstern informasjon kalt **datakilder**, som oppbevares i skytjenester. Et vanlig eksempel er en tabell i en Excel-fil lagret i OneDrive for Business. Apper får tilgang til disse datakildene ved hjelp av **Tilkoblinger**.

Den vanligste datakilden er tabellen, som du kan bruke til å hente og lagre informasjon. Du kan bruke tilkoblinger til datakilder for å lese og skrive data i Microsoft Excel-arbeidsbøker, SharePoint-lister, SQL-tabeller og mange andre formater, som kan lagres i skytjenester som OneDrive for Business, DropBox, SQL Server, osv.

Det finnes andre typer data kilder som ikke er tabeller, for eksempel e-post, kalendere, Twitter og varslinger.

Ved bruk av kontrollene **[Galleri](controls/control-gallery.md)** , **[Visningsskjema](controls/control-form-detail.md)** og **[Redigeringsskjema](controls/control-form-detail.md)** , er det enkelt å oppdatere en app som leser og skriver data fra en datakilde. Les artikkelen [Forstå dataskjemaer](working-with-forms.md) for å komme i gang.

I tillegg til å opprette og administrere tilkoblinger på [powerapps.com](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc), oppretter du også tilkoblinger når du utfører disse oppgavene:

* Automatisk genererer en [app fra data](app-from-sharepoint.md), som for eksempel en egendefinert SharePoint-liste.
* Oppdaterer en eksisterende app, eller oppretter en fra bunnen av som beskrevet i [å legge til en tilkobling](add-data-connection.md).
* Åpner en app som er opprettet av en annen bruker og [delt med deg](share-app.md).

> [!NOTE]
> Hvis du ønsker å bruke PowerApps Studio i stedet, kan du åpne **Fil**-menyen og klikke eller trykke på **Tilkoblinger**, så åpnes [powerapps.com](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) slik at du kan opprette eller administrere tilkoblinger der.

## <a name="create-a-new-connection"></a>Å opprette en ny tilkobling
1. Hvis du ikke allerede har gjort det, logger du deg på [powerapps.com](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc).
2. Klikk eller trykk på **Tilkoblinger** i venstre navigasjonsfelt.
   
    ![Å administrere tilkoblinger](./media/add-manage-connections/open-connections.png)
3. Klikk eller trykk på **Ny tilkobling** i hjørnet øverst til høyre.
   
    ![Å legge til tilkoblinger](./media/add-manage-connections/add-connection.png)
4. Klikk eller trykk på en kobling i listen som vises, og deretter følg ledeteksten.
   
   ![Å legge til tilkoblinger](./media/add-manage-connections/choose-connection.png)
5. Klikk eller trykk på **Opprett**-knappen.
   
   ![Å legge til tilkoblinger](./media/add-manage-connections/create-connection.png)
6. Følg lederteksten. Noen koblinger ber deg om å angi legitimasjon, angi et bestemt datasett eller utføre andre trinn. Andre, for eksempel **Microsoft Translator**, ber ikke om det.
   
   Disse koblingene krever ytterligere informasjon før du kan bruke dem.
   
   * [SharePoint](connections/connection-sharepoint-online.md)
   * [SQL Server](connections/connection-azure-sqldatabase.md)

Den nye koblingen vises under **Tilkoblinger**, og du kan [legge den til en app](add-data-connection.md).

## <a name="update-or-delete-a-connection"></a>Å oppdatere eller slette en tilkobling
Finn tilkoblingen du vil oppdatere eller slette i listen over tilkoblinger, og klikk eller trykk deretter på ellipsen (3-punkt-symbol) til høyre for tilkoblingen.

![Å oppdatere tilkobling](./media/add-manage-connections/auth-or-delete.png)

* Hvis du vil oppdatere legitimasjonen for en tilkobling, kan du klikke eller trykk på nøkkelikonet, og deretter angi legitimasjonen for den tilkoblingen.
* Hvis du vil slette tilkoblingen, klikker eller trykker du på papirkurv-ikonet.
* Klikk eller trykk på informasjon-ikonet for å se tilkoblings detaljene.

