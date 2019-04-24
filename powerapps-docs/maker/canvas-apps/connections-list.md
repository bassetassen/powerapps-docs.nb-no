---
title: Oversikt over koblinger for lerretsapper | Microsoft Docs
description: Oversikt over alle tilgjengelige tilkoblinger du kan bruke til å utvikle lerretsapper
author: lancedMicrosoft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 08/28/2017
ms.author: lanced
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 29de71e413a83a1c0939796f7b65bd42d4aca3c4
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/23/2019
ms.locfileid: "61556651"
---
# <a name="overview-of-canvas-app-connectors-for-powerapps"></a>Oversikt over lerretsappkoblinger for PowerApps
Dataene er i kjernen for de fleste apper, inkludert de du oppretter i PowerApps. Dataene er lagret i en *datakilde*, og du importerer disse dataene inn i appen ved å opprette en *tilkobling*. Tilkoblingen bruker en bestemt *tilkobling* for å kommunisere med datakilden. PowerApps har koblinger for mange populære tjenester og lokale datakilder, inkludert SharePoint, SQL Server, Office 365, Salesforce og Twitter. Hvis du vil komme i gang med å legge til data i en lerretsapp, kan du se [Legg til en datatilkobling i PowerApps](add-data-connection.md).

En kobling kan inneholde **tabeller** med data eller **handlinger**. Noen koblinger inneholder bare tabeller, noen inneholder bare handlinger, og noen inneholder begge. Koblingen kan også være enten en standardkobling eller egendefinert kobling.

## <a name="tables"></a>Tabeller

Hvis koblingen inneholder tabeller, legger du til datakilden. Deretter velger du tabellen i datakilden som du ønsker å administrere. PowerApps henter både tabelldata fra appen og oppdateringsdata fra datakilden. Du kan for eksempel legge til en datakilde som inneholder en tabell med navn **Leksjoner**. Deretter angir du **Elementer**-egenskapen til en kontroll, som et galleri eller skjema, til denne verdien i formellinjen:

 ![Elementer-egenskapen for vanlig datakilde](./media/connections-list/ItemPropertyPlain.png)

Du kan angi dataene som appen henter ved å tilpasse **Elementer**-egenskapen for kontrollen som viser deg dataene. Hvis vi fortsetter fra forrige eksempel, kan du sortere eller filtrere dataene i **Leksjoner**-tabellen ved bruk av navnet som et argument for **Søk**- og **SortByColumn**-funksjonene. I denne grafikken angis formelen som **Elementer**-egenskapen er angitt til, og den spesifiserer at dataene sorteres og filtreres basert på teksten i **TextSearchBox1**. 

 ![Elementer-egenskapen for utvidet datakilde](./media/connections-list/ItemPropertyExpanded.png)

Hvis du vil ha mer informasjon om hvordan du tilpasser formelen med tabeller, kan du se disse emnene:

  [Å forstå datakilder i PowerApps](working-with-data-sources.md)<br> 
  [Å generere en app fra Excel-data](get-started-create-from-data.md)<br> 
  [Å opprette en app fra grunnen av](get-started-create-from-blank.md)<br>
  [Slik fungerer tabeller og poster i PowerApps](working-with-tables.md)

  > [!NOTE]
  > Hvis du vil koble til data i en Excel-arbeidsbok, må den være lagret i en skylagringstjeneste som OneDrive. Hvis du vil ha mer informasjon, kan du se [Å koble til lagring i skyen fra PowerApps](connections/cloud-storage-blob-connections.md).

## <a name="actions"></a>Handlinger

Hvis koblingen inneholder handlinger, må du fremdeles velge datakildene som før. I stedet for å velge en tabell som neste trinn kan du heller koble til en kontroll i en handling manuelt, ved å redigere **Elementer**-egenskapen til kontrollen som viser dataene. Formelen som du angir **Elementer**-egenskapen for, angir handlingen som henter dataene. Appen henter for eksempel ikke data hvis du kobler til Yammer, og deretter angir **Elementer**-egenskapen til navnet på datakilden. Hvis du vil fylle ut en kontroll med data, angir du en handling som **GetMessagesInGroup(5033622).messages**.

![Elementer-egenskapen for handling-datakilde](./media/connections-list/ItemPropertyAction.png)

Hvis du må håndtere egendefinerte dataoppdateringer for handlingskoblinger, bygger du en formel som inkluderer **Patch**-funksjonen. Identifiser handlingen og feltene som du skal binde til handlingen, i formelen.  

Hvis du vil ha mer informasjon om hvordan du tilpasser formelen for tilpassede oppdateringer, kan du se disse emnene:

[Patch](functions/function-patch.md)<br>[Collect](functions/function-clear-collect-clearcollect.md)<br>[Update](functions/function-update-updateif.md)

> [!NOTE]
>  **PowerApps fungerer ikke med dynamisk skjema**. Det dynamiske skjemaet for uttrykket refererer til muligheten for at den samme handlingen kan returnere en annen tabell med forskjellige kolonner. Betingelser som kan føre til kolonnene i tabellene som er forskjellige inkluderer inndataparameterne handling, brukeren eller rollen som utfører handlingen og gruppe der brukeren arbeider, blant annet. For eksempel kan SQL Server-lagrede prosedyrer returnere forskjellige kolonner hvis med forskjellige inndata. Connector-dokumentasjonen for handlinger med dynamisk skjema, viser **utdataene fra denne operasjonen er dynamiske.** som returverdi. I motsetning Microsoft Flow fungerer med dynamisk skjema og kan gi en arbeid-rundt for ditt scenario.

## <a name="popular-connectors"></a>Populære koblinger

Denne tabellen inneholder koblinger til mer informasjon om våre mest populære koblinger. Hvis du vil ha en fullstendig liste over koblinger, kan du se [Alle koblinger](https://docs.microsoft.com/connectors/).

| &nbsp; | &nbsp; | &nbsp; | &nbsp; | &nbsp; |
| --- | --- | --- | --- | --- |
| ![Common Data Service](./media/connections-list/cdm.png) |[**Common Data Service**](../common-data-service/data-platform-intro.md) |&nbsp; |![Office 365 Outlook](./media/connections-list/office365.png) |[**Office 365 Outlook**](connections/connection-office365-outlook.md) |
| ![SharePoint](./media/connections-list/sharepoint.png) |[**SharePoint**](connections/connection-sharepoint-online.md) |&nbsp; |![Excel](./media/connections-list/excel.png) |[**Excel**](connections/connection-excel.md) |
| ![SQL Server](./media/connections-list/sql.png) |[**SQL Server**](connections/connection-azure-sqldatabase.md) |&nbsp; |![OneDrive for Business](./media/connections-list/onedrive.png) |[**OneDrive for Business**](connections/cloud-storage-blob-connections.md) |
| ![Dynamics 365](./media/connections-list/dynamics-365.png) |[**Dynamics 365**](connections/connection-dynamics-crmonline.md) |&nbsp; |![OneDrive](./media/connections-list/onedrive.png) |[**OneDrive**](connections/cloud-storage-blob-connections.md) |
| ![Office 365-brukere](./media/connections-list/office365.png) |[**Office 365-brukere**](connections/connection-office365-users.md) |&nbsp; |![Dropbox](./media/connections-list/dropbox.png) |[**Dropbox**](connections/cloud-storage-blob-connections.md) |

## <a name="standard-and-custom-connectors"></a>Standardkoblinger og egendefinerte koblinger
PowerApps inneholder *standardkoblinger* for mange vanlig brukte datakilder, som de som ble nevnt ovenfor. Hvis PowerApps har en standard kobling for datakildetypen du ønsker å bruke, må du bruke den koblingen. Hvis du ønsker å koble til andre datakildetyper, for eksempel en tjeneste som du har opprettet, kan du se [Registrer og bruk egendefinerte koblinger](../canvas-apps/register-custom-api.md).

## <a name="all-standard-connectors"></a>Alle standardkoblinger
Se [Referanse for Microsoft-kobling](https://docs.microsoft.com/connectors/) for en liste over alle standardkoblingene. Premium-koblinger krever PowerApps-abonnement 1 eller 2. Hvis du vil ha mer informasjon, kan du se [PowerApps-abonnementer](https://powerapps.microsoft.com/pricing/).

Du kan stille spørsmål om en bestemt kobling i [PowerApps-forumene](https://powerusers.microsoft.com/t5/PowerApps-Community/ct-p/PowerApps1), og du kan foreslå koblinger som kan legges til eller andre forbedringer i [PowerApps Ideas](https://powerusers.microsoft.com/t5/PowerApps-Ideas/idb-p/PowerAppsIdeas).
