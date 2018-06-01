---
title: Oversikt over koblinger | Microsoft Docs
description: Oversikt over alle tilgjengelige tilkoblinger du kan bruke til å utvikle apper
services: ''
suite: powerapps
documentationcenter: ''
author: archnair
manager: anneta
editor: ''
tags: ''
ms.service: powerapps
ms.workload: na
ms.tgt_pltfrm: na
ms.devlang: na
ms.topic: article
ms.date: 08/28/2017
ms.author: archanan
ms.openlocfilehash: aff9e09ea92376c19067fbbc99dc1a9d8ccb0f99
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/22/2018
ms.locfileid: "30996187"
---
# <a name="overview-of-connectors-for-powerapps"></a>Oversikt over koblinger for PowerApps
Dataene er i kjernen for de fleste apper, inkludert de du oppretter i PowerApps. Dataene er lagret i en *datakilde*, og du importerer disse dataene inn i appen ved å opprette en *tilkobling*. Tilkoblingen bruker en bestemt *tilkobling* for å kommunisere med datakilden. PowerApps har koblinger for mange populære tjenester og lokale datakilder, inkludert SharePoint, SQL Server, Office 365, Salesforce, Twitter og mer. Hvis du vil komme i gang med å legge til data til en app, kan du se [Legge til en datatilkobling i PowerApps](add-data-connection.md).

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
> Hvis du vil koble til data i Excel, må arbeidsboken være lagret i en skylagringstjeneste som OneDrive. Hvis du vil ha mer informasjon, kan du se [Koble til lagring i skyen fra PowerApps](connections/cloud-storage-blob-connections.md).

* Andre koblinger fungerer med funksjonsbaserte datakilder, for eksempel Twitter, Facebook og Office 365 Outlook. Når du arbeider med disse datakildene, returneres dataene til PowerApps basert på bestemte funksjonsanrop i den underliggende tjenesten. Med Twitter-koblingen ringer du for eksempel opp `Twitter.MyFollowers()` for å returnere en liste over følgerene dine. Du kan fortsatt bruke disse dataene i et skjema eller galleri, men det krever litt mer arbeid enn med tabelldata. Hvis du vil ha mer informasjon, kan du se [Koble til Twitter fra PowerApps](connections/connection-twitter.md).

## <a name="all-connectors"></a>Alle koblinger
Tabellen nedenfor viser alle våre koblinger. Hvis du vil ha mer informasjon om hver kobling, kan du se [Microsoft Connector-referanse](https://docs.microsoft.com/connectors/). Premium-koblinger krever PowerApps Plan 1 eller Plan 2. Hvis du vil ha mer informasjon, kan du se [PowerApps-planer](https://powerapps.microsoft.com/pricing/).

| &nbsp; | &nbsp; |
| --- | --- |
| Planlegging av 10to8-avtaler<br>Act!<br>Adobe Creative Cloud ![Premium-kobling](./media/connections-list/premium.png)<br>Adobe Sign<br>Amazon Redshift ![Premium-kobling](./media/connections-list/premium.png)<br>Apache Impala ![Premium-kobling](./media/connections-list/premium.png)<br>appFigures<br>Godkjenninger<br>Asana<br>AWeber ![Premium-kobling](./media/connections-list/premium.png)<br>Azure AD<br>Azure Application Insights<br>Azure Automation<br>Azure Blob Storage<br>Azure Cosmos DB<br>Azure Data Lake<br>Azure Event Grid<br>Azure Event Grid Publish<br>Azure File Storage<br>Azure Log Analytics<br>Azure Log Analytics-datainnsamling<br>Azure Queues<br>Ressursbehandling<br>Azure Table Storage<br>Basecamp 2<br>Basecamp 3<br>Benchmark Email ![Premium-kobling](./media/connections-list/premium.png)<br>Bing-kart<br>Bing-søk<br>Bitbucket ![Premium-kobling](./media/connections-list/premium.png)<br>Bitly<br>Bizzy (H3 Solutions, Inc.)<br>Blogger<br>Box<br>bttn<br>Buffer<br>Calendly ![Premium-kobling](./media/connections-list/premium.png)<br>Campfire<br>Capsule CRM ![Premium-kobling](./media/connections-list/premium.png)<br>Chatter ![Premium-kobling](./media/connections-list/premium.png)<br>Cognito Forms<br>Common Data Service ![Premium-kobling](./media/connections-list/premium.png)<br>API for visuelt innhold<br>Content Conversion<br>Content Moderator<br>DB2 ![Premium-kobling](./media/connections-list/premium.png)<br>Disqus<br>DocFusion365 – SP ![Premium-kobling](./media/connections-list/premium.png)<br>DocuSign ![Premium-kobling](./media/connections-list/premium.png)<br>Dropbox<br>Dynamics 365<br>Dynamics 365 for Financials<br>Dynamics 365 for Operations<br>Dynamics NAV<br>Easy Redmine ![Premium-kobling](./media/connections-list/premium.png)<br>Elastic Forms<br>Event Hubs<br>Eventbrite ![Premium-kobling](./media/connections-list/premium.png)<br>Excel<br>Ansikts-API<br>Facebook<br>Filsystem<br>Flic<br>FlowForma ![Premium-kobling](./media/connections-list/premium.png)<br>FreshBooks ![Premium-kobling](./media/connections-list/premium.png)<br>Freshdesk<br>Freshservice ![Premium-kobling](./media/connections-list/premium.png)<br>FTP<br>GitHub<br>Gmail<br>Google-kalender<br>Google Contacts<br>Google Drive<br>Google Sheets<br>Google Tasks<br>GoToMeeting ![Premium-kobling](./media/connections-list/premium.png)<br>GoToTraining ![Premium-kobling](./media/connections-list/premium.png)<br>GoToWebinar ![Premium-kobling](./media/connections-list/premium.png)<br>Harvest ![Premium-kobling](./media/connections-list/premium.png)<br>HelloSign ![Premium-kobling](./media/connections-list/premium.png)<br>HipChat<br>HTTP med Azure AD ![Premium-kobling](./media/connections-list/premium.png)<br>Informix ![Premium-kobling](./media/connections-list/premium.png)<br>Infusionsoft ![Premium-kobling](./media/connections-list/premium.png) |Inoreader<br>Insightly<br>Instagram<br>Instapaper<br>Intercom<br>JIRA ![Premium-kobling](./media/connections-list/premium.png)<br>JotForm ![Premium-kobling](./media/connections-list/premium.png)<br>LeanKit ![Premium-kobling](./media/connections-list/premium.png)<br>LinkedIn<br>LiveChat ![Premium-kobling](./media/connections-list/premium.png)<br>Language Understanding Intelligent Service (LUIS)<br>Post<br>MailChimp ![Premium-kobling](./media/connections-list/premium.png)<br>Mandrill ![Premium-kobling](./media/connections-list/premium.png)<br>Middels<br>Microsoft Forms<br>Microsoft StaffHub<br>Microsoft Teams<br>Microsoft Translator<br>MSN Vær<br>Muhimbi PDF<br>MySQL ![Premium-kobling](./media/connections-list/premium.png)<br>Nexmo ![Premium-kobling](./media/connections-list/premium.png)<br>Varslinger<br>Office 365 Bookings<br>Office 365 Grupper<br>Office 365 Outlook<br>Office 365-brukere<br>Office 365 Video<br>OneDrive<br>OneDrive for Business<br>OneNote (bedrift)<br>Oracle Database ![Premium-kobling](./media/connections-list/premium.png)<br>Outlook Customer Manager<br>Outlook-oppgaver<br>Outlook.com<br>PagerDuty<br>Parserr<br>Paylocity ![Premium-kobling](./media/connections-list/premium.png)<br>Pinterest<br>Pipedrive ![Premium-kobling](./media/connections-list/premium.png)<br>Pitney Bowes-datavalidering ![Premium-kobling](./media/connections-list/premium.png)<br>Pivotal-sporing<br>Planner<br>Plivo ![Premium-kobling](./media/connections-list/premium.png)<br>PostgreSQL ![Premium-kobling](./media/connections-list/premium.png)<br>Power BI<br>PowerApps-varsel ![Premium-kobling](./media/connections-list/premium.png)<br>Project Online<br>Redmine<br>RSS<br>Salesforce ![Premium-kobling](./media/connections-list/premium.png)<br>SendGrid<br>Service Bus<br>SFTP<br>SharePoint<br>Skype for Business<br>Slack<br>SmartSheet<br>SMTP<br>SparkPost<br>SQL Server<br>Stripe ![Premium-kobling](./media/connections-list/premium.png)<br>SurveyMonkey ![Premium-kobling](./media/connections-list/premium.png)<br>Teamarbeid-prosjekter ![Premium-kobling](./media/connections-list/premium.png)<br>Teradata ![Premium-kobling](./media/connections-list/premium.png)<br>Tekstanalyser<br>Todoist<br>Toodledo<br>Trello<br>Twilio<br>Twitter<br>TypeForm<br>UserVoice ![Premium-kobling](./media/connections-list/premium.png)<br>Video Indexer<br>Vimeo<br>Visual Studio Team Services<br>WebMerge<br>WordPress<br>Wunderlist<br>Yammer<br>YouTube<br>Zendesk ![Premium-kobling](./media/connections-list/premium.png) |

Hvis du har spørsmål om en bestemt kobling, kan du bruke [PowerApps-foraene](https://powerusers.microsoft.com/t5/PowerApps-Community/ct-p/PowerApps1). Hvis du har en idé for en ny kobling eller et forslag til forbedringer, kan du bruke [Ideer for PowerApps](https://powerusers.microsoft.com/t5/PowerApps-Ideas/idb-p/PowerAppsIdeas).
