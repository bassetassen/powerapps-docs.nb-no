---
title: Hurtiginnføring – å generere en app fra Common Data Service for apper | Microsoft Docs
description: I denne hurtiginnføringen skal du generere en app automatisk i PowerApps for å behandle data i Common Data Service for apper
author: AFTOwen
manager: kvivek
ms.service: powerapps
ms.topic: quickstart
ms.custom: canvas
ms.reviewer: ''
ms.date: 05/06/2018
ms.author: anneta
ms.openlocfilehash: 3481bd697e29855a075598975e26d14121a49a0a
ms.sourcegitcommit: 0e9af8cace2bdc04750f4c5a70a3c4af8e3d2292
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 07/22/2018
ms.locfileid: "39195362"
---
# <a name="quickstart-generate-an-app-from-common-data-service-for-apps-in-powerapps"></a>Hurtiginnføring: å generere en app fra Common Data Service for apper i PowerApps

I denne hurtiginnføringen skal du bruke Microsoft PowerApps til å automatisk generere en app basert på en liste over eksempelkontoer i [Common Data Service (CDS) for apper](../common-data-service/data-platform-intro.md). I denne appen kan du bla gjennom alle kontoene, vise detaljer for en enkelt konto og opprette, oppdatere eller slette en konto.

Hvis du ikke er registrert for PowerApps, kan du [registrere deg gratis](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) før du begynner.

## <a name="prerequisites"></a>Forutsetninger
Hvis du ønsker å følge med i denne hurtiginnføringen, må du [bytte til et miljø](working-with-environments.md) der en database i CDS for apper har blitt opprettet, inneholder data og tillater oppdateringer. Hvis det ikke finnes et slikt miljø og du har administratorrettigheter, kan du [opprette et miljø](../../administrator/environments-administration.md#create-an-environment) som oppfyller dette kravet.

## <a name="generate-an-app"></a>Å generere en app
1. Logg deg på [PowerApps](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc), og (om nødvendig) bytt miljøer som angitt tidligere i dette emnet.

    ![Hjemmesiden for PowerApps](./media/data-platform-create-app/sign-in.png)

1. Under **Lag apper som disse** holder du pekeren over **Begynn fra data**, og deretter velger du **Lag denne appen**.

    ![Alternativ for å opprette en app](./media/data-platform-create-app/make-this-app.png)

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
I denne hurtiginnføringen opprettet du en app for å behandle eksempeldata om kontoer i Common Data Service for apper. Som et påfølgende trinn kan du tilpasse galleriet og andre elementer for den standard nettleserskjermen for bedre å imøtegå dine behov.

> [!div class="nextstepaction"]
> [Å tilpasse et galleri](customize-layout-sharepoint.md).
