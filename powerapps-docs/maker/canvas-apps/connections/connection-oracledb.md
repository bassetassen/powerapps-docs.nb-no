---
title: Koble til Oracle Database | Microsoft Docs
description: Finn ut hvordan du kobler til Oracle Database og bruker den til å bygge apper i PowerApps.
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
ms.date: 04/14/2017
ms.author: archanan
ms.openlocfilehash: dd55314461b2ba4769e50275837dc6fd897fedcc
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/22/2018
ms.locfileid: "30996282"
---
# <a name="connect-to-an-oracle-database-from-powerapps"></a>Koble til en Oracle Database fra PowerApps
Vis tabeller og opprett, les, oppdater og slett tabellrader i en Oracle Database etter at du har opprettet en tilkobling og bygget en app i PowerApps. Tilkobling til Oracle Database støtter full delegering av filtrering, sortering og andre funksjoner, men ikke utløsere eller lagrede prosedyrer.

## <a name="prerequisites"></a>Forutsetninger
* Oracle 9 og senere
* Oracle-klientprogramvare 8.1.7 og senere
* Installasjon av en lokal datagateway
* Installasjon av Oracle-klient-SDK

### <a name="install-an-on-premises-data-gateway"></a>Installer en lokal datagateway
Hvis du vil installere en gateway, følger du fremgangsmåten i [denne opplæringen](../gateway-management.md).

En lokal datagateway fungerer som en bro som gir rask og sikker dataoverføring mellom lokale data (data som ikke er i skyen) og Power BI, Microsoft Flow, Logic Apps og PowerApps-tjenester. Du kan bruke samme gateway med flere tjenester og flere datakilder. Hvis du vil ha mer informasjon, kan du se [Forstå gatewayer](../gateway-reference.md).

### <a name="install-oracle-client"></a>Installere Oracle-klient
Installer [64-biters ODAC 12c Release 4 (12.1.0.2.4) for Windows x64](http://www.oracle.com/technetwork/database/windows/downloads/index-090165.html) på samme datamaskin som den lokale datagatewayen. Ellers vil det vises en feil hvis du prøver å opprette eller bruke tilkoblingen, som beskrevet i listen over kjente problemer.

## <a name="create-an-app-from-a-table-in-an-oracle-database"></a>Opprett en app fra en tabell i en Oracle Database
1. Klikk eller trykk på **Ny** på **Fil**-menyen (nær venstre kant) i PowerApps Studio.
   
   ![Nytt alternativ](./media/connection-oracledb/new-app.png)
2. Klikk eller trykk på pilen under **Start med dataene dine**.
   
      Det vises en liste over tilkoblinger som du allerede har.
3. Klikk eller trykk på **Ny tilkobling**.
   
   ![Ny tilkobling](./media/connection-oracledb/new-connection.png)
4. Klikk eller trykk på **Oracle Database** på listen over tilkoblinger.
   
   ![Ny database](./media/connection-oracledb/oracle-db.png)
5. Angi navnet på en Oracle-server, et brukernavn og et passord.
   
    Angi en server i dette formatet hvis det kreves en SID:<br>
    *Servernavn*/*SID*
   
   ![Tilkoblingsparametere](./media/connection-oracledb/connection-params.png)
6. Klikk eller trykk på gatewayen du vil bruke, eller installer en.
   
    Hvis gatewayen ikke vises etter at du har installert den, kan du klikke på **Oppdater gatewaylisten**.
   
   ![Ny gateway](./media/connection-oracledb/choose-gateway.png)
7. Klikk eller trykk på **Opprett** for å opprette tilkoblingen.
   
   ![Nyhet](./media/connection-oracledb/create-button.png)
8. Klikk eller trykk på **standard**datasettet.
   
   ![Nyhet](./media/connection-oracledb/choose-dataset.png)
9. Klikk eller trykk på tabellen du vil bruke, i listen over tabeller.
   
   ![Nyhet](./media/connection-oracledb/choose-table.png)
10. Klikk på **Koble til** for å opprette appen.
    
    ![Nyhet](./media/connection-oracledb/connect-button.png)

PowerApps oppretter en app som inneholder tre skjermbilder og viser data fra tabellen du har valgt:

* **BrowseScreen1**, som lister opp alle poster i tabellen.
* **DetailScreen1**, som gir mer informasjon om én enkelt post.
* **EditScreen1**, hvor brukere kan oppdatere en post eller opprette en ny post.

![Nyhet](./media/connection-oracledb/afd-app.png)

## <a name="next-steps"></a>Neste trinn
* Hvis du vil lagre appen som du nettopp har generert, trykker du på Ctrl-S.
* Hvis du vil tilpasse **BrowseScreen1** (som vises som standard), kan du se [Tilpasse et oppsett](../customize-layout-sharepoint.md).
* Hvis du vil tilpasse **DetailsScreen1** eller **EditScreen1**, kan du se [Tilpasse et skjema](../customize-forms-sharepoint.md).

## <a name="known-issues-tips-and-troubleshooting"></a>Kjente problemer, tips og feilsøking
1. Kan ikke nå gatewayen.
   
    Denne feilen oppstår hvis den lokale datagatewayen ikke kan koble til skyen. Hvis du vil kontrollere statusen for gatewayen, kan du logge inn på powerapps.microsoft.com, klikke eller trykke på **Gatewayer** og deretter klikke eller trykke på gatewayen du vil bruke.
   
    Kontroller at gatewayen kjører og kan koble til Internett. Unngå å installere gatewayen på en datamaskin som kan bli slått av eller gå i hvilemodus. Du kan også prøve å starte den lokale datagateway-tjenesten (PBIEgwService) på nytt.
2. System.Data.OracleClient krever Oracle-klientprogramvare versjon 8.1.7 eller høyere.
   
    Denne feilen oppstår hvis Oracle-klient-SDK ikke er installert på den samme datamaskinen som den lokale datagatewayen. For å løse dette problemet kan du [installere den offisielle leverandøren](https://go.microsoft.com/fwlink/p/?LinkID=272376).
3. Tabellen [Tablename] definerer ingen nøkkelkolonner.
   
    Denne feilen oppstår hvis du kobler til en tabell som ikke har en primærnøkkel, som tilkoblingen til Oracle Database krever.
4. I skrivende stund støttes ikke lagrede prosedyrer, tabeller med sammensatte nøkler og nestede objekttyper i tabeller.

