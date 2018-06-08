---
title: Opprett en tilkobling til SharePoint fra PowerApps | Microsoft Docs
description: På powerapps.com kan du opprette en tilkobling til SharePoint, som du kan bruke for å generere en app automatisk eller utvikle en fra bunnen av.
documentationcenter: na
author: aftowen
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: conceptual
ms.component: canvas
ms.date: 09/03/2016
ms.author: anneta
ms.openlocfilehash: 16c585f553373faee609683774e7938e8bd165f1
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/04/2018
ms.locfileid: "31824594"
---
# <a name="create-a-connection-to-sharepoint-from-powerapps"></a>Opprett en tilkobling til SharePoint fra PowerApps
Opprett en tilkobling enten til SharePoint Online eller SharePoint lokalt, slik at du kan generere en app automatisk eller utvikle en fra bunnen av.

Hvis du ikke allerede er kjent med PowerApps, kan du se [Introduksjon til PowerApps](getting-started.md).

I skrivende stund støtter PowerApps egendefinerte lister, men ikke biblioteker. I tillegg kan du vise data i enkelte typer kolonner, som for eksempel **Valg** og **Bilde**, men du kan ikke oppdatere de dataene. Hvis du vil ha mer informasjon, kan du se [Kjente problemer](connections/connection-sharepoint-online.md#known-issues).

## <a name="specify-a-sharepoint-connection"></a>Angi en SharePoint-tilkobling
1. Hvis du ikke allerede har registrert deg, kan du [registrere deg for PowerApps](../signup-for-powerapps.md).

2. Logg deg på [powerapps.com](https://web.powerapps.com) med samme legitimasjon som du brukte til å registrere deg.

3. Klikk eller trykk på **Behandle** i venstre navigasjonsfelt, og deretter klikker eller trykker du på **Tilkoblinger**.

    ![Nytt alternativ i Fil-menyen](./media/connect-to-sharepoint/manage-connections.png)

4. Klikk eller trykk på **Ny tilkobling** øverst til høyre.

    ![Ny tilkoblingsknapp](./media/connect-to-sharepoint/new-connection.png)

5. Klikk eller trykk på **SharePoint** i listen over tilkoblinger.

    ![Legg til en SharePoint-tilkobling](./media/connect-to-sharepoint/add-sp-portal.png)

6. Følg trinnene i én av disse prosedyrene, som vises senere i dette emnet:

   * [Koble til et SharePoint Online-område](connect-to-sharepoint.md#connect-to-a-sharepoint-online-site).
   * [Koble til et lokalt SharePoint-område](connect-to-sharepoint.md#connect-to-an-on-premises-sharepoint-site).

## <a name="connect-to-a-sharepoint-online-site"></a>Koble til et SharePoint Online-område
1. Klikk eller trykk på **Koble til direkte (skytjenester)**, og klikk eller trykk deretter på **Legg til tilkobling**.

    ![Velg SharePoint Online](./media/connect-to-sharepoint/choose-online.png)

2. Gå til [Neste trinn](connect-to-sharepoint.md#next-steps) på slutten av dette emnet.

## <a name="connect-to-an-on-premises-sharepoint-site"></a>Koble til et lokalt SharePoint-område
1. Klikk eller trykk på **Koble til ved bruk av lokal datagateway**.

    ![Velg lokal SharePoint](./media/connect-to-sharepoint/choose-onprem.png)

    > [!NOTE]
> Gatewayer og lokale tilkoblinger kan kun opprettes og brukes i brukerens [standardmiljø](working-with-environments.md).

2. Angi brukernavnet og passordet ditt.

    Hvis legitimasjonen din inkluderer et domenenavn, angir du den som *Domene/Alias*.

    ![Angi legitimasjonen din](./media/connect-to-sharepoint/specify-credentials.png)

3. Hvis du ikke har en lokal datagateway installert, kan du [installere en](gateway-reference.md), og deretter klikke eller trykke på ikonet for å oppdatere listen over gatewayer.

    ![Installer en gateway](./media/connect-to-sharepoint/install-gateway.png)

4. Klikk eller trykk på gatewayen du vil bruke under **Velg en gateway**, og klikk eller trykk deretter på **Legg til tilkobling**.

    ![Velg en gateway](./media/connect-to-sharepoint/choose-gateway.png)

## <a name="next-steps"></a>Neste trinn
* [Generer en app automatisk](app-from-sharepoint.md) basert på en liste du angir. Appen har som standard tre skjermbilder: ett for å bla gjennom poster, ett for å vise detaljer om en enkelt post, og ett for å opprette eller oppdatere en post.
* [Bygg en app fra bunnen av](get-started-create-from-blank.md). Dette emnet ble skrevet for Excel, men de samme prinsippene gjelder for SharePoint.
