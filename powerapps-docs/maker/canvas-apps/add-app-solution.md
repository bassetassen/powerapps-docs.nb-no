---
title: Opprett en lerret-app i en løsning | Microsoft Docs
description: Opprett en lerret-app i en løsning i PowerApps, slik at du kan distribuere appen til et annet miljø
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
ms.openlocfilehash: 3703fc5e36b38c7894300bc2074453716ddd9946
ms.sourcegitcommit: 60fd1792430b9f3da08ec161cb2277506d795e3a
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/01/2019
ms.locfileid: "71705097"
---
# <a name="create-a-canvas-app-from-within-a-solution"></a>Opprett en lerret-app fra en løsning

Opprett en app fra en løsning hvis du for eksempel vil distribuere appen til et annet miljø. Løsninger kan bare inneholde apper, men også egen definerte enheter, alternativ sett og andre komponenter. Du kan raskt tilpasse et miljø på en rekke måter ved å opprette apper og andre komponenter i en løsning, eksportere løsningen og deretter importere den til et annet miljø.

Hvis du vil ha mer informasjon om løsninger, kan du se [løsninger-oversikt](../common-data-service/solutions-overview.md).

## <a name="prerequisite"></a>Nødvendig

Hvis du vil følge trinnene i dette emnet, må du bytte til et miljø som inneholder en Common Data Service-database.

## <a name="create-a-solution"></a>Opprett en løsning

Du kan hoppe over denne prosedyren hvis du allerede har en løsning der du vil opprette en app, eller som du vil koble til en app.

1. [Logg deg](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) på powerapps, og (om nødvendig) Bytt til det aktuelle miljøet:

    - Hvis du vil opprette en app fra en løsning, må du bytte til et hvilket som helst miljø som inneholder en Common Data Service-database.
    - Hvis du vil koble en eksisterende app til en løsning, kan du bytte til miljøet som inneholder appen.

1. Velg **løsninger**i det venstre navigasjons feltet.

    > [!div class="mx-imgBorder"]
    > ![Valg for løsninger i det venstre]navigasjons feltet(./media/add-app-solution/left-nav.png "løsninger i navigasjons feltet til venstre")

1. I banneret under tittel linjen velger du **ny løsning**.

    > [!div class="mx-imgBorder"]
    > Alternativet ![New-Solution i](./media/add-app-solution/banner-new-solution.png "alternativet nytt-løsnings alternativ") i banneret

1. Angi et visnings navn, en utgiver og en versjon for løsningen i vinduet som vises.

    > [!div class="mx-imgBorder"]
    > ![Alternativer for nye løsnings](./media/add-app-solution/configure-new-solution.png "Alternativer for en ny løsning")

    Et navn (uten mellomrom) vil bli generert automatisk basert på visnings navnet du angir, men du kan tilpasse det genererte navnet hvis du vil. Du kan angi standard utgiveren for miljøet ditt og **1,0** for versjonen hvis du ikke har bestemte behov i disse områdene.

1. Velg **Lagre og Lukk**nær hjørnet øverst til venstre.

    > [!div class="mx-imgBorder"]
    > ![Lagre en ny løsning](./media/add-app-solution/save-new-solution.png "Lagre en ny løsning")

## <a name="create-a-canvas-app-in-a-solution"></a>Opprett en lerret-app i en løsning

Du kan opprette en tom lerret-app i en løsning. Du kan ikke automatisk generere en app med tre skjermer eller tilpasse en mal eller eksempel-app fra en løsning.

1. [Logg deg](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) på powerapps.

1. Bytt om nødvendig til miljøet som inneholder løsningen der du vil opprette en lerret-app.

1. Velg **løsninger**i det venstre navigasjons feltet.

    > [!div class="mx-imgBorder"]
    > ![Valg for løsninger i det venstre]navigasjons feltet(./media/add-app-solution/left-nav.png "løsninger i navigasjons feltet til venstre")

1. I listen over løsninger velger du løsningen der du vil opprette en lerret-app.

1. I banneret under tittel linjen velger du **ny** > **app** > -**lerret-appen**, og deretter velger du form faktoren (telefon eller nett brett) for appen du vil opprette.

    > [!div class="mx-imgBorder"]
    > ![Alternativer for å opprette en app i et løsnings](./media/add-app-solution/new-option.png "Alternativer for å opprette en app i en løsning")

    PowerApps Studio åpnes med et tomt lerret i en annen nett leser kategori.

1. Opprett appen (eller foreta minst én endring), og lagre endringene.

1. Velg **ferdig** i nett leser fanen der du valgte løsningen, for å oppdatere listen over komponenter i løsningen.

    > [!div class="mx-imgBorder"]
    > ![Ferdig]knapp(./media/add-app-solution/done-button.png "fullført knapp")

    Den nye appen vises i listen over komponenter for løsningen. Hvis du lagrer endringer i appen, vil de gjenspeiles i versjonen som er i løsningen.

## <a name="link-an-existing-canvas-app-to-a-solution"></a>Koble en eksisterende lerret-app til en løsning

Hvis du vil koble en app til en løsning, må begge være i samme miljø, og appen må være opprettet fra en løsning.

1. [Logg deg](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) på powerapps.

1. Bytt om nødvendig til miljøet som inneholder løsningen du vil koble til en app.

1. Velg **løsninger**i det venstre navigasjons feltet.

    > [!div class="mx-imgBorder"]
    > ![Valg for løsninger i det venstre]navigasjons feltet(./media/add-app-solution/left-nav.png "løsninger i navigasjons feltet til venstre")

1. I listen over løsninger velger du løsningen du vil koble til en app.

1. I banneret under tittel linjen velger du **Legg til eksisterende** > **app** > -**lerrets app**.

    > [!div class="mx-imgBorder"]
    > ![Banner alternativer for å koble til et eksisterende program](./media/add-app-solution/add-existing.png "banner alternativer for å koble til en eksisterende app")

    En liste over lerrets apper som ble opprettet i en løsning i dette miljøet vises.

1. Velg appen du vil koble til løsningen, i listen over apper, og velg deretter **Legg til**.

    > [!div class="mx-imgBorder"]
    > ![Legg til knapp](./media/add-app-solution/add-button.png "Legg til") knapp

## <a name="known-limitations"></a>Kjente begrensninger

Hvis du vil ha informasjon om kjente begrensninger, kan du se [bruke løsninger i powerapps](../common-data-service/use-solution-explorer.md#known-limitations). 

## <a name="next-steps"></a>Neste trinn

- Opprett eller koble flere apper og [andre komponenter](../common-data-service/use-solution-explorer.md), som for eksempel enheter, flyter og instrument bord, til løsningen din.
- [Eksporter løsningen](../common-data-service/import-update-export-solutions.md) slik at du kan distribuere den til et annet miljø, på AppSource, og så videre.
