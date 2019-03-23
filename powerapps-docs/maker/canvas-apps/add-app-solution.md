---
title: Lage en lerretsapp i en løsning | Microsoft Docs
description: Lage en lerretsapp i en løsning i PowerApps, slik at du kan distribuere appen til et annet miljø
author: AFTOwen
manager: kvivek
ms.service: powerapps
ms.topic: article
ms.custom: canvas
ms.reviewer: ''
ms.date: 10/23/2018
ms.author: anneta
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: dcb6a9c69e602b739d58afde2242d18b60e6f477
ms.sourcegitcommit: 5b2b70c3fc7bcba5647d505a79276bbaad31c610
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/22/2019
ms.locfileid: "58356820"
---
# <a name="create-a-canvas-app-from-within-a-solution"></a>Lage en lerretsapp fra en løsning

Opprett en app fra i en løsning Hvis, for eksempel du vil distribuere appen til et annet miljø. Løsninger kan inneholde ikke bare apper, men også tilpassede entiteter alternativsett og andre komponenter. Du kan raskt tilpasse et miljø i en rekke måter ved å opprette apper og andre komponenter fra i en løsning, eksportere løsningen, og deretter importere den til et annet miljø.

Løsninger bygges på samme plattform som Dynamics 365 for Customer Engagement. Hvis du vil ha mer informasjon, se [oversikt over løsninger](../common-data-service/solutions-overview.md).

## <a name="prerequisite"></a>Forutsetning

For å følge trinnene i dette emnet, må du bytte til et miljø som inneholder en Common Data Service-database.

## <a name="create-a-solution"></a>Opprett en løsning

Du kan hoppe over denne fremgangsmåten hvis du allerede har en løsning i som du vil opprette en app eller til som du vil koble en app.

1. [Logg deg på](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) til PowerApps, og deretter (Hvis nødvendig) Bytt til det riktige miljøet:

    - Hvis du vil opprette en app fra i en løsning, kan du bytte til en hvilken som helst miljø som inneholder en Common Data Service-database.
    - Hvis du vil koble en eksisterende app til en løsning, kan du bytte til miljøet som inneholder appen.

1. I navigasjonsfeltet til venstre velger du **løsninger**.

    > [!div class="mx-imgBorder"]
    > ![Alternativet løsninger i det venstre navigasjonsfeltet](./media/add-app-solution/left-nav.png "løsninger alternativ i navigasjonsfeltet til venstre")

1. Velg i banneret under tittellinjen, **ny løsning**.

    > [!div class="mx-imgBorder"]
    > ![Alternativet New-løsningen i banneret](./media/add-app-solution/banner-new-solution.png "alternativet New-løsningen i banneret")

1. I vinduet som vises, kan du angi et visningsnavn, en utgiver og en versjon for løsningen din.

    > [!div class="mx-imgBorder"]
    > ![Alternativer for en ny løsning](./media/add-app-solution/configure-new-solution.png "alternativer for en ny løsning")

    Et navn (ingen mellomrom) vil bli generert automatisk basert på visningsnavnet du angir, men du kan tilpasse det genererte navnet hvis du vil bruke. Du kan angi standardutgiveren for miljøet ditt og **1.0** for versjonen hvis du ikke har bestemte behov i disse områdene.

1. Nær hjørnet øverst til venstre velger **lagre og Lukk**.

    > [!div class="mx-imgBorder"]
    > ![Lagre en ny løsning](./media/add-app-solution/save-new-solution.png "lagre en ny løsning")

## <a name="create-a-canvas-app-in-a-solution"></a>Lage en lerretsapp i en løsning

Du kan opprette et tomt lerret-app fra en løsning. Du kan ikke automatisk generere en app med tre skjermer eller tilpasse en mal eller et eksempel på app fra innsiden av en løsning.

1. [Logg deg på](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) til PowerApps.

1. Hvis det er nødvendig, bytte til miljøet som inneholder løsningen som du vil lage en lerretsapp.

1. I navigasjonsfeltet til venstre velger du **løsninger**.

    > [!div class="mx-imgBorder"]
    > ![Alternativet løsninger i det venstre navigasjonsfeltet](./media/add-app-solution/left-nav.png "løsninger alternativ i navigasjonsfeltet til venstre")

1. Velg løsningen som du vil lage en lerretsapp i listen over løsninger.

1. Velg i banneret under tittellinjen, **ny** > **App** > **lerretsapp**, og velg deretter formfaktor (telefon eller nettbrett) av appen som du vil opprette.

    > [!div class="mx-imgBorder"]
    > ![Alternativer for å opprette en app i en løsning](./media/add-app-solution/new-option.png "alternativer for å opprette en app i en løsning")

    PowerApps Studio åpner med et tomt lerret i en annen fane i nettleseren.

1. Opprette appen din (eller endre minst én), og lagre deretter endringene.

1. Velg på nettleserfanen der du valgte løsningen din, **ferdig** å oppdatere listen over komponenter i løsningen din.

    > [!div class="mx-imgBorder"]
    > ![Ferdig-knapp](./media/add-app-solution/done-button.png "ferdig-knapp")

    Den nye appen vises i listen over komponenter for denne løsningen. Hvis du lagrer endringer i appen din, vil de gjenspeiles i versjonen som er i løsningen.

## <a name="link-an-existing-canvas-app-to-a-solution"></a>Koble en eksisterende lerretsapp til en løsning

Hvis du vil koble en app til en løsning, begge må være i det samme miljøet, og appen må være opprettet fra i en løsning.

1. [Logg deg på](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) til PowerApps.

1. Hvis det er nødvendig, bytte til miljøet som inneholder løsningen som du vil koble en app.

1. I navigasjonsfeltet til venstre velger du **løsninger**.

    > [!div class="mx-imgBorder"]
    > ![Alternativet løsninger i det venstre navigasjonsfeltet](./media/add-app-solution/left-nav.png "løsninger alternativ i navigasjonsfeltet til venstre")

1. Velg løsningen som du vil koble en app i listen over løsninger.

1. Velg i banneret under tittellinjen, **Legg til eksisterende** > **App** > **lerretsapp**.

    > [!div class="mx-imgBorder"]
    > ![Banner alternativer for å koble en eksisterende app](./media/add-app-solution/add-existing.png "Banner alternativer for å koble en eksisterende app")

    Det vises en liste over lerret-apper som ble opprettet i en løsning i dette miljøet.

1. I listen over apper, kan du velge appen som du vil koble til løsningen, og velg deretter **Legg til**.

    > [!div class="mx-imgBorder"]
    > ![Legg til](./media/add-app-solution/add-button.png "Legg til-knappen")

## <a name="known-limitations"></a>Kjente begrensninger

For informasjon om kjente begrensninger, kan du se [Bruk løsninger i PowerApps](../common-data-service/use-solution-explorer.md#known-limitations). 

## <a name="next-steps"></a>Neste trinn

- Opprette eller koble flere apper og [andre komponenter](../common-data-service/use-solution-explorer.md), for eksempel enheter, flyter og instrumentbord, til løsningen din.
- [Eksporter løsningen din](../common-data-service/import-update-export-solutions.md) slik at du kan distribuere den til et annet miljø, på AppSource, og så videre.
