---
title: Å legge til og åpne en app i Microsoft Teams | Microsoft Docs
description: Lær hvordan du legger til en app i en Microsoft Teams-kanal, slik at personer du har delt appen med, kan åpne den i denne kanalen.
author: mgblythe
manager: kvivek
ms.service: powerapps
ms.component: pa-user
ms.topic: quickstart
ms.date: 01/18/2018
ms.author: matp
ms.custom: ''
ms.reviewer: ''
ms.assetid: ''
search.audienceType:
- enduser
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: 0e98f22c3dc0f66893e0cc027488ced5d1dd3535
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/24/2018
ms.locfileid: "42850465"
---
# <a name="add-an-app-to-microsoft-teams"></a>Legg til en app i Microsoft Teams

Microsoft Teams er et chat-basert samarbeidsplattform som er bygd på Office 365-teknologier. Du kan tilpasse Teams-opplevelsen ved å legge til PowerApps-lerretapper i gruppene i Teams. I dette emnet kan du lære hvordan du legger til eksempelappen Produktpresentasjon i en Teams-kanal, og deretter åpner appen fra denne kanalen. 

![App som er innebygd i Microsoft Teams](./media/open-app-embedded-in-teams/embedded-app.png)

Hvis du ikke er registrert for PowerApps, kan du [registrere deg gratis](https://web.powerapps.com/signup?redirect=marketing&email=) før du begynner.

## <a name="prerequisites"></a>Forutsetninger

Du trenger et [Office 365-abonnement ](https://signup.microsoft.com/Signup?OfferId=467eab54-127b-42d3-b046-3844b860bebf&dl=O365_BUSINESS_PREMIUM&ali=1) og en [kanal i Teams](https://www.youtube.com/watch?v=he2f1quaR7M) for å følge denne prosedyren.

## <a name="sign-in-to-powerapps"></a>Å logge deg på PowerApps

Å logge deg på PowerApps på [https://web.powerapps.com](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc).

## <a name="add-an-app"></a>Å legge til en app

1. Velg en gruppe og en kanal for dette teamet i Microsoft Teams. I dette eksemplet er det **Generelt**-kanalen under **Forretningsutvikling**-gruppen.

    ![](./media/open-app-embedded-in-teams/teams-select-channel.png)

2. Velg **+** for å legge til en fane.

    ![](./media/open-app-embedded-in-teams/teams-add-tab.png)

3. Velg **PowerApps** i dialogboksen **Legg til en fane**.

    ![](./media/open-app-embedded-in-teams/add-a-tab.png)

4. Velg **Eksempelapper** > **Produktpresentasjon** > **Lagre**.

    ![](./media/open-app-embedded-in-teams/select-an-app.png)

    Appen er nå tilgjengelig for bruk i kanalen.

    ![](./media/open-app-embedded-in-teams/app-in-channel.png)

> [!NOTE]
> Du må [dele](../maker/canvas-apps/share-app.md) dine egne apper før du legger dem til Teams (eksempelapper deles som standard).

## <a name="open-an-app"></a>Å åpne en app

1. I Microsoft Teams velger du gruppen og kanalen som inneholder appen.

    ![](./media/open-app-embedded-in-teams/teams-select-channel.png)

2. Velg **Produktpresentasjon**-fanen.

    ![](./media/open-app-embedded-in-teams/open-tab.png)

    Appen åpnes i kanalen.

    ![](./media/open-app-embedded-in-teams/app-in-channel.png)

## <a name="known-issues"></a>Kjente problemer

I skrivebordsprogrammet for Microsoft Teams:

* Apper må laste inn innhold som bilder og PDF-filer via en sikker (https)-tilkobling.
* Ikke alle sensorer, for eksempel **Akselerasjon**, **Kompass** og **Plassering**, støttes.
* Bare disse lydformatene støttes: AAC, H264, OGG Vorbis og WAV.

## <a name="clean-up-resources"></a>Å rydde opp i ressurser

Hvis du vil fjerne appen fra kanalen, kan du velge **Produktpresentasjon**-fanen > **Fjern**.

## <a name="next-steps"></a>Neste trinn

I dette emnet har du lagt til eksempelappen Produktpresentasjon i en Teams-kanal, og deretter åpnet appen fra denne kanalen. Hvis du vil lære mer om PowerApps, kan du fortsette til PowerApps-opplæringen.

> [!div class="nextstepaction"]
> [PowerApps-opplæring](../maker/canvas-apps/get-started-create-from-blank.md)
