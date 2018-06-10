---
title: Å generere en app i PowerApps for Common Data Service for apper (hurtiginnføring) | Microsoft Docs
description: Å generere en app automatisk i PowerApps for å behandle data i Common Data Service for apper
services: powerapps
documentationcenter: na
author: AFTOwen
manager: kfile
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/10/2018
ms.author: anneta
ms.openlocfilehash: 78429fc5d0220b5cc9e8dc726583c2e9e543f85a
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/22/2018
ms.locfileid: "30995892"
---
# <a name="quickstart-for-generating-an-app-in-powerapps-for-the-common-data-service-for-apps"></a>Hurtiginnføring om å generere en app i PowerApps for Common Data Service for apper

I denne hurtigveiledningen skal du bruke PowerApps til å automatisk generere din første app basert på en liste over eksempelkontoer i [Common Data Service for apper](../common-data-service/data-platform-intro.md). I denne appen kan du bla gjennom alle kontoene, vise detaljer for en enkelt konto og opprette, oppdatere eller slette en konto.

Hvis du ønsker å følge med i denne hurtiginnføringen, må du bytte til e [miljø](working-with-environments.md) der en database i Common Data Service har blitt opprettet og inneholder data. Hvis det ikke finnes et slikt miljø og du har administratorrettigheter, kan du [opprette et miljø](../../administrator/environments-administration.md#create-an-environment) som oppfyller dette kravet.

Hvis du ikke har en lisens for PowerApps, kan du [registrere deg gratis](../signup-for-powerapps.md).

## <a name="generate-an-app"></a>Å generere en app
1. Logg deg på [PowerApps](https://web.powerapps.com).

    ![Hjemmesiden for PowerApps](./media/data-platform-create-app/sign-in.png)

1. Under **Lag apper som disse**, holder du pekeren over **Begynn fra data**, og deretter velger du **Lag denne appen**.

    ![Alternativ for å opprette en app](./media/data-platform-create-app/make-this-app.png)

1. Velg pilen som peker til høyre under **Start med datene dine**.

    ![Pil-ikon](./media/data-platform-create-app/right-arrow.png)

1. Velg tilkoblingen til Common Data Service under **Tilkoblinger**.

1. Skriv inn**Kontoer** i søkeboksen (nær kanten til høyre), velg **Kontoer** under **Velg en tabell**, og velg deretter **Koble til**.

    ![Å velge en enhet](./media/data-platform-create-app/select-entity.png)

Etter noen minutter åpnes appen til Bla gjennom-skjermen, som viser en liste over kontoer. Nær toppen av skjermen viser en tittellinje ikoner for å oppdatere listen, sortere listen og opprette en konto. Under tittellinjen inneholder en søkeboks muligheten til å filtrere listen basert på teksten du skriver eller limer inn. 

Listen viser et bilde, en e-postadresse, et poststed og en ID for kontoen som standard. Men du kan egendefinere listen, som heter for galleri, for å vise andre typer data.

![Bla gjennom-skjermen](./media/data-platform-create-app/browse-screen.png)

## <a name="save-the-app"></a>Å lagre appen
Du vil sannsynligvis gjøre flere endringer før du bruker denne appen eller deler den med andre. Som en anbefalt fremgangsmåte lagrer du arbeidet ditt så langt, før du fortsetter.

1. Klikk eller trykk på **Fil**-fanen nær hjørnet øverst til venstre.

1. Angi appnavnet til **AppGen** på **Appinnstillinger**-siden, endre bakgrunnsfargen til rød, og endre ikonet til en hake.

    ![Appinnstillinger-siden](./media/data-platform-create-app/app-settings.png)

1. Klikk eller trykk på **Lagre** nær venstre kant.

## <a name="next-steps"></a>Neste trinn
I denne hurtiginnføringen opprettet du en app for å behandle eksempeldata om kontoer i Common Data Service for apper. Som neste trinn kan du egendefinere den standard Bla gjennom-skjermen slik at den passer dine behov.

> [!div class="nextstepaction"]
> [Å tilpasse en standard Bla gjennom-skjerm](customize-layout-sharepoint.md).
