---
title: Oversikt over koblinger | Microsoft Docs
description: Oversikt over alle tilgjengelige tilkoblinger du kan bruke til å utvikle apper
author: lancedMicrosoft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 08/28/2017
ms.author: lanced
ms.openlocfilehash: 15da6ed2ce6b44c17645ac11d1b049b95e157703
ms.sourcegitcommit: 47be38a23c96ba7478fd777065f5db41181af40b
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 07/20/2018
ms.locfileid: "39164752"
---
# <a name="overview-of-connectors-for-powerapps"></a>Oversikt over koblinger for PowerApps
Dataene er i kjernen for de fleste apper, inkludert de du oppretter i PowerApps. Dataene er lagret i en *datakilde*, og du importerer disse dataene inn i appen ved å opprette en *tilkobling*. Tilkoblingen bruker en bestemt *tilkobling* for å kommunisere med datakilden. PowerApps har koblinger for mange populære tjenester og lokale datakilder, inkludert SharePoint, SQL Server, Office 365, Salesforce, Twitter og mer. Hvis du vil komme i gang med å legge til data til en app, kan du se [Å legge til en datatilkobling i PowerApps](add-data-connection.md).

Tabellen nedenfor inneholder koblinger til mer informasjon om våre mest populære koblinger. Hvis du vil ha en fullstendig liste over koblinger, kan du se [Alle koblinger](#all-connectors).

| &nbsp; | &nbsp; | &nbsp; | &nbsp; | &nbsp; |
| --- | --- | --- | --- | --- |
| ![Common Data Service](./media/connections-list/cdm.png) |[**Common Data Service**](../common-data-service/data-platform-intro.md) |&nbsp; |![Office 365 Outlook](./media/connections-list/office365.png) |[**Office 365 Outlook**](connections/connection-office365-outlook.md) |
| ![SharePoint](./media/connections-list/sharepoint.png) |[**SharePoint**](connections/connection-sharepoint-online.md) |&nbsp; |![Excel](./media/connections-list/excel.png) |[**Excel**](connections/connection-excel.md) |
| ![SQL Server](./media/connections-list/sql.png) |[**SQL Server**](connections/connection-azure-sqldatabase.md) |&nbsp; |![OneDrive for Business](./media/connections-list/onedrive.png) |[**OneDrive for Business**](connections/cloud-storage-blob-connections.md) |
| ![Dynamics 365](./media/connections-list/dynamics-365.png) |[**Dynamics 365**](connections/connection-dynamics-crmonline.md) |&nbsp; |![OneDrive](./media/connections-list/onedrive.png) |[**OneDrive**](connections/cloud-storage-blob-connections.md) |
| ![Office 365-brukere](./media/connections-list/office365.png) |[**Office 365-brukere**](connections/connection-office365-users.md) |&nbsp; |![Dropbox](./media/connections-list/dropbox.png) |[**Dropbox**](connections/cloud-storage-blob-connections.md) |

## <a name="types-of-connectors"></a>Typer koblinger
PowerApps har to typer koblinger: *standardkoblinger*, som de som er oppført ovenfor, og *egendefinerte koblinger*. Hvis du kobler til en datakilde som PowerApps støtter med en standardkobling, kan du bruke denne koblingen. Hvis du trenger å koble til en annen kilde, for eksempel en tjeneste som du har opprettet, kan du se [Registrere og bruke egendefinerte koblinger](../canvas-apps/register-custom-api.md).

Standardkoblinger fungerer annerledes, avhengig av hvilken type datakilde de kobler seg til og hvordan dataene returneres av datakilden:

* Noen koblinger er kompatible med datakilder i tabellform, for eksempel SharePoint, SQL Server og Excel. Når du arbeider med disse datakildene, returneres dataene til PowerApps som en tabell. PowerApps bruker sine egen funksjoner, for eksempel [Patch()](functions/function-patch.md), [Collect()](functions/function-clear-collect-clearcollect.md), [Update()](functions/function-update-updateif.md) og så videre, for å samhandle med dataene. Tabelldata er også enkle å bruke i skjemaer og gallerier, der et felt i en tabell vises som et felt i et galleri eller et skjema. Hvis du vil ha mer informasjon, kan du se følgende artikler:

    [Å forstå datakilder i PowerApps](working-with-data-sources.md)

    [Å generere en app fra Excel-data](get-started-create-from-data.md)

    [Å opprette en app fra grunnen av](get-started-create-from-blank.md)

    > [!NOTE]
  > Hvis du vil koble til data i Excel, må arbeidsboken være lagret i en skylagringstjeneste som OneDrive. Hvis du vil ha mer informasjon, kan du se [Å koble til lagring i skyen fra PowerApps](connections/cloud-storage-blob-connections.md).

* Andre koblinger fungerer med funksjonsbaserte datakilder, for eksempel Twitter, Facebook og Office 365 Outlook. Når du arbeider med disse datakildene, returneres dataene til PowerApps basert på bestemte funksjonsanrop i den underliggende tjenesten. Med Twitter-koblingen ringer du for eksempel opp `Twitter.MyFollowers()` for å returnere en liste over følgerene dine. Du kan fortsatt bruke disse dataene i et skjema eller galleri, men det krever litt mer arbeid enn med tabelldata. Hvis du vil ha mer informasjon, kan du se [Å koble til Twitter fra PowerApps](connections/connection-twitter.md).

## <a name="all-connectors"></a>Alle koblinger
Se [Referanse for Microsoft-kobling](https://docs.microsoft.com/connectors/) for en liste over alle koblingene våre. Premium-koblinger krever PowerApps-abonnement 1 eller 2. Hvis du vil ha mer informasjon, kan du se [PowerApps-abonnementer](https://powerapps.microsoft.com/pricing/).


Hvis du har spørsmål om en bestemt kobling, kan du bruke [PowerApps-foraene](https://powerusers.microsoft.com/t5/PowerApps-Community/ct-p/PowerApps1). Hvis du har en idé for en ny kobling eller et forslag til forbedringer, kan du bruke [Ideer for PowerApps](https://powerusers.microsoft.com/t5/PowerApps-Ideas/idb-p/PowerAppsIdeas).
