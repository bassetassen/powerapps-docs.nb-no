---
title: Generer en lerret-app fra Common Data Service | Microsoft Docs
description: Generer en lerret-app automatisk i PowerApps for å behandle data i Common Data Service
author: tapanm-msft
manager: kvivek
ms.service: powerapps
ms.topic: quickstart
ms.custom: canvas
ms.reviewer: ''
ms.date: 05/06/2018
ms.author: tapanm
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: f9dedc515ee130a950c1dc12793751d43aa3804f
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/07/2019
ms.locfileid: "71993093"
---
# <a name="generate-a-canvas-app-from-common-data-service-in-powerapps"></a>Generer en lerret-app fra Common Data Service i PowerApps

I PowerApps kan du automatisk generere en lerret-app basert på en liste over eksempel kontoer i [Common data service](../common-data-service/data-platform-intro.md). I denne appen kan du bla gjennom alle kontoene, vise detaljer for en enkelt konto og opprette, oppdatere eller slette en konto.

Hvis du ikke er registrert for PowerApps, kan du [registrere deg gratis](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) før du begynner.

## <a name="prerequisites"></a>Forutsetninger

Hvis du vil følge denne hurtig innføringen, må du være tilordnet sikkerhets rollen [Environment Maker](https://docs.microsoft.com/power-platform/admin/database-security#predefined-security-roles) , og du må [bytte til et miljø](working-with-environments.md) der en database i Common data service er opprettet, inneholde data og tillate oppdateringer. Hvis det ikke finnes et slikt miljø og du har administratorrettigheter, kan du [opprette et miljø](https://docs.microsoft.com/power-platform/admin/environments-administration#create-an-environment) som oppfyller dette kravet.

## <a name="generate-an-app"></a>Å generere en app

1. Logg deg på [PowerApps](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc), og (om nødvendig) bytt miljøer som angitt tidligere i dette emnet.

1. Hold pekeren over **Begynn fra data** under **Lag din egen app**, og velg deretter **Lag denne appen**.

    ![Alternativ for å opprette en app](./media/data-platform-create-app/start-from-data.png)

1. På flisen **Common Data Service** velger du **Telefonoppsett**.

    ![Tilkoblingsflis](./media/data-platform-create-app/connection-tile.png)

1. Velg **Kontoer** og deretter **Koble til** under **Velg en tabell**.

1. Hvis dialogboksen **Velkommen til PowerApps Studio** vises, klikker eller trykker du på **Hopp over**.

Appen åpnes så i nettleserskjermen, som viser en liste over kontoer i en kontroll kalt et galleri. Nær toppen av skjermen viser en tittellinje ikoner for oppdatering av data i galleriet, alfabetisk sortering av data i galleriet og tilføying av data til galleriet. Under tittellinjen gir en søkeboks muligheten til å filtrere dataene i galleriet, basert på teksten du skriver eller limer inn. 

Som standard viser galleriet en e-postadresse, en by og et kontonavn. Som du ser i [Neste trinn](data-platform-create-app.md#next-steps) kan du tilpasse galleriet for å endre hvordan data vises, og du kan til og med vise andre typer data.

![Bla gjennom-skjerm](./media/data-platform-create-app/browse-screen.png)

## <a name="save-the-app"></a>Å lagre appen
Du vil sannsynligvis gjøre flere endringer før du bruker denne appen eller deler den med andre. Som en anbefalt fremgangsmåte lagrer du arbeidet ditt så langt, før du fortsetter.

1. Velg **Fil**-fanen nær hjørnet øverst til venstre.

1. Angi appnavnet til **AppGen** på **Appinnstillinger**-siden, endre bakgrunnsfargen til rød, og endre ikonet til en hake.

    ![Appinnstillinger-siden](./media/data-platform-create-app/app-settings.png)

1. Nær venstre kant velger du **Lagre**, og deretter velger du **Lagre** i nedre venstre hjørne.

## <a name="next-steps"></a>Neste trinn
I denne hurtig innføringen opprettet du en app for å behandle eksempel data om kontoer i Common Data Service. Som et påfølgende trinn kan du tilpasse galleriet og andre elementer for den standard nettleserskjermen for bedre å imøtegå dine behov.

> [!div class="nextstepaction"]
> [Å tilpasse et galleri](customize-layout-sharepoint.md).
