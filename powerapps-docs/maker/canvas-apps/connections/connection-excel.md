---
title: Oversikt over Excel-tilkobling | Microsoft Docs
description: Vis og oppdater data i Excel ved å lage arbeidsboken i en skylagringskonto, og deretter få tilgang på dataen fra appen din.
author: lancedMicrosoft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.date: 10/02/2016
ms.author: lanced
ms.reviewer: tapanm
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 565f751017bc8c145c34058bd4dd57d047127d45
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/07/2019
ms.locfileid: "71987190"
---
# <a name="connect-to-excel-from-powerapps"></a>Å koble til Excel fra PowerApps
![Excel](./media/connection-excel/excelicon.png)

Excel er en *type* tilkobling. Slik viser du Excel-data i appen din:

1. [Formater Excel-dataen som en tabell](https://support.office.com/article/Create-an-Excel-table-in-a-worksheet-E81AA349-B006-4F8A-9806-5AF9DF0AC664).
2. Lagre Excel-filen i en skylagringskonto som Box, Dropbox, Google Drive, OneDrive og OneDrive for Business.
3. [Koble til skylagringskontoen](../add-manage-connections.md), og legg deretter til Excel-tabellen som datakilde.
4. Vis denne informasjonen i appen ved [å generere appen automatisk](../get-started-create-from-data.md) eller ved legge til og konfigurere for eksempel en **Galleri**-kontroll.

> [!NOTE]
> Når du kobler til Excel-tabellen fra PowerApps, vil PowerApps opprette en kolonne kalt **\_PowerAppsId_** , med en unik ID for hver rad i Excel-tabellen.

[Oversikt over skylagring-tilkoblingen](cloud-storage-blob-connections.md) viser deg hvordan du legger til tilkoblingen, legger til en Excel-tabell som datakilde, og bruker Excel-dataen i appen din.

Se [liste over tilkoblinger for PowerApps](../connections-list.md) for informasjon om hvordan du kobler til andre typer data.

### <a name="known-limitations"></a>Kjente begrensninger
Hvis du vil ha informasjon om hvordan du deler Excel-data innad i organisasjonen, kan du [se gjennom disse begrensningene](cloud-storage-blob-connections.md#sharing-excel-tables).

