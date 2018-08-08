---
title: Generer en lerretsapp fra en SharePoint-liste | Microsoft Docs
description: Generer en lerretsapp med tre skjermer for å behandle elementer fra en SharePoint-liste, enten området er lokalt eller ligger i skyen.
author: AFTOwen
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 03/18/2018
ms.author: anneta
ms.openlocfilehash: 9230c96c1b1c5e07ea5129f73a8edd95772aad84
ms.sourcegitcommit: e3f5a2bef64085d02aec82e62ff94ae8a4d01d24
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/02/2018
ms.locfileid: "39471424"
---
# <a name="generate-a-canvas-app-from-within-sharepoint-by-using-powerapps"></a>Generer en lerretsapp fra SharePoint ved hjelp av PowerApps

Med PowerApps kan du automatisk generere en lerretsapp som gjør at brukerne kan behandle oppføringer i en egendefinert SharePoint Online-liste. Appen har tre skjermer, der brukerne kan gjøre følgende:

* bla gjennom alle postene i listen (**BrowseScreen1**)
* vise alle felt for en bestemt post (**DetailsScreen1**)
* opprette og redigere en post (**EditScreen1**)

Hvis du fra kommandolinjen i SharePoint Online oppretter en app basert på en egendefinert liste, vises appen som en visning av den aktuelle listen. Du kan også kjøre appen på iOS- og Android-enheter, og i nettlesere.

> [!IMPORTANT]
> PowerApps støtter ikke alle typer SharePoint-data. Hvis du vil ha mer informasjon, kan du se [Kjente problemer](connections/connection-sharepoint-online.md#known-issues).

## <a name="generate-an-app"></a>Å generere en app
1. Åpne en egendefinert liste i SharePoint Online, og trykk eller klikk på **PowerApps** på kommandolinjen. Deretter trykker eller klikker du på **Opprett en app**.

    ![Opprette en app](./media/generate-app-from-sharepoint-list-interface/generate-new-app.png)

2. I panelet som vises, skriver du inn navn på appen og trykker eller klikker på **Opprett**.

    ![Gi navn til appen](./media/generate-app-from-sharepoint-list-interface/app-name.png)

    En ny fane vises i nettleseren som viser appen som du genererte automatisk ved hjelp av SharePoint-listen. Appen vises i PowerApps Studio, der du kan tilpasse den.

    ![Standardapp](./media/generate-app-from-sharepoint-list-interface/default-app.png)  
3. Klikk eller trykk på nettleserfanen for SharePoint-listen, og klikk eller trykk på **Åpne**.

> [!NOTE]
> Du må kanskje laste inn nettleservinduet på nytt (for eksempel ved å trykke F5) for å åpne appen.

Appen åpnes i en egen nettleserfane.

## <a name="manage-the-app"></a>Administrere appen
![Kommandolinje](./media/generate-app-from-sharepoint-list-interface/command-bar.png)

* Hvis du trykker eller klikker på **Rediger i PowerApps**, åpnes appen i en egen nettleserfane der du kan oppdatere appen i PowerApps Studio.

* Hvis du trykker eller klikker på **Gjør denne visningen offentlig**, vil andre personer i organisasjonen kunne se den. Standardinnstillingen er at det er bare du som kan se visningene du lager. Hvis du vil gi andre lov til å redigere appen, må du [dele den med dem](share-app.md), og deretter gi dem **tillatelse til å redigere**.

* Hvis du trykker eller klikker på **Fjern denne visningen**, fjerner du visningen fra SharePoint, men appen blir liggende i PowerApps med mindre du [sletter den](delete-app.md).

## <a name="next-steps"></a>Neste trinn
* Tilpass standardverdiene for [galleri](customize-layout-sharepoint.md), [skjemaer](customize-forms-sharepoint.md) og [kort](customize-card.md).
