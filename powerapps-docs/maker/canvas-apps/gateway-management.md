---
title: Administrer en lokal datagateway | Microsoft Docs
description: Administrere en lokal datagateway og tilhørende tilkoblinger
author: archnair
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 10/30/2016
ms.author: archanan
ms.openlocfilehash: e7dc9a2386d75a6f03744286b7ed265a8d385370
ms.sourcegitcommit: dfa0e1a7981814e15e6ca4720e2a5f930e859db1
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 07/13/2018
ms.locfileid: "39018541"
---
# <a name="manage-an-on-premises-data-gateway-in-powerapps"></a>Administrer en lokal datagateway i PowerApps
Installer en lokal datagateway for å overføre data på en rask og sikker måte mellom PowerApps og en datakilde som ikke er i skyen, for eksempel en lokal SQL Server-database eller et lokalt SharePoint-område. Vis alle gatewayer som du har administratortillatelser til, og behandle tillatelser og tilkoblinger for disse gatewayene.

Med en gateway kan du koble til lokale data over disse tilkoblingene:

* SharePoint
* SQL Server
* Oracle
* Informix
* Filsystem
* DB2

## <a name="prerequisites"></a>Forutsetninger
* Brukernavnet og passordet du brukte til å [registrere](../signup-for-powerapps.md) deg for PowerApps.
* Administrative tillatelser på en gateway. (Du har disse tillatelsene som standard for hver gateway som du installerer, og en administrator for en annen gateway kan gi deg disse tillatelsene for nettopp den gatewayen.)
* En lisens som støtter tilgang til lokale data ved hjelp av en lokal gateway. Hvis du vil ha mer informasjon, kan du se inndelingen Tilkobling på [prissiden](https://powerapps.microsoft.com/pricing/).
* Gatewayer og lokale tilkoblinger kan bare opprettes og brukes i brukerens [standardmiljø](working-with-environments.md).

## <a name="install-a-gateway"></a>Installer en gateway
1. Klikk eller trykk på **Gatewayer** i det venstre navigasjonsfeltet i [powerapps.com](https://web.powerapps.com).

    ![Gatewayer i venstre navigasjonsfelt](./media/gateway-management/manage-gateway.png)

2. Hvis du ikke har administrative tillatelser for en gateway, klikker eller trykker du på [Installere en gateway nå](http://go.microsoft.com/fwlink/?LinkID=820931) (eller **Ny Gateway** i øvre høyre hjørne), og deretter følger du instruksjonene i veiviseren som vises.

    ![Installasjon av gatewayer](./media/gateway-management/no-gateway-installed.png)

    Hvis du vil ha mer informasjon om hvordan du installerer en gateway, kan du se [Forstå lokale datagatewayer](gateway-reference.md).

## <a name="view-and-manage-gateway-permissions"></a>Vis og administrer gatewaytillatelser
1. Klikk eller trykk på **gatewayer** i det venstre navigasjonsfeltet i [powerapps.com](https://web.powerapps.com), og deretter klikker eller trykker du på en gateway.

2. Legg til en bruker i en gateway ved å klikke eller trykke på **Brukere**, angi en bruker eller gruppe, og deretter angi et tilgangsnivå:

   * **Kan bruke**: Brukere som kan opprette tilkoblinger på gatewayen for å bruke på apper og flyter, men som ikke kan dele gatewayen. Bruk denne tillatelsen for brukere som vil kjøre apper, men ikke dele dem.
   * **Kan bruke og dele**: Brukere som kan opprette en tilkobling på gatewayen for å bruke på apper og flyter, og dele gatewayen automatisk når de deler en app. Bruk denne tillatelsen for brukere som trenger å dele apper med andre brukere eller med organisasjonen.
   * **Administrator**: Administratorer som har full kontroll over gatewayen, inkludert det å legge til brukere, angi tillatelser, opprette tilkoblinger til alle tilgjengelige datakilder og slette gatewayen.

For tillatelsesnivåene **Kan bruke** og **Kan bruke og dele** må du velge datakildene som brukeren kan koble til, over gatewayen.

## <a name="view-and-manage-gateway-connections"></a>Vis og administrer gateway-tilkoblinger
1. Klikk eller trykk på **gatewayer** i det venstre navigasjonsfeltet i [powerapps.com](https://web.powerapps.com), og klikk eller trykk deretter på en gateway.

2. Klikk eller trykk på **Tilkoblinger**, og deretter klikker eller trykker du på en tilkobling for å vise detaljene, redigere innstillingene eller slette den.

3. Hvis du vil dele en tilkobling, klikker eller trykker du på **Del**, og deretter legger du til eller fjerner brukere.

    > [!NOTE]
   > Du kan bare dele enkelte typer tilkoblinger, for eksempel SQL Server. Du finner mer informasjon i [Ressurser for deling av apper](share-app-resources.md).

Hvis du vil ha mer informasjon om hvordan du administrerer en tilkobling, kan du se [Behandle tilkoblingene dine](add-manage-connections.md).

## <a name="troubleshooting-and-advanced-configuration"></a>Feilsøking og avansert konfigurasjon
Hvis du vil ha mer informasjon om feilsøking av problemer med gatewayer eller konfigurere gateway-tjenesten for nettverket, kan du se [Forstå lokale datagatewayer](gateway-reference.md).

## <a name="next-steps"></a>Neste trinn
* Opprett en app som kobler til en lokal datakilde, for eksempel [SQL Server](connections/connection-azure-sqldatabase.md) eller [SharePoint](connections/connection-sharepoint-online.md).
* [Del en app](share-app.md) som kobler til en lokal datakilde.
