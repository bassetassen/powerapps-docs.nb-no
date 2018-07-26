---
title: Å slette en egendefinert enhet | Microsoft Docs
description: Trinnvise instruksjoner for hvordan du sletter en egendefinert enhet og fjerner alle data i PowerApps
author: clwesene
manager: kfile
ms.service: powerapps
ms.component: cds
ms.topic: conceptual
ms.date: 03/21/2018
ms.author: clwesene
ms.openlocfilehash: b17da30916b06b5b76b16cc6bf9758b988549f6f
ms.sourcegitcommit: 0b051bba173353d7ceda3b60921e7e009eb00709
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 07/24/2018
ms.locfileid: "39218652"
---
# <a name="delete-a-custom-entity"></a>Å slette en egendefinert enhet
Du kan slette egendefinerte enheter, men ikke standardenheter.

1. Utvid **Data**-delen på [powerapps.com](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc), og trykk eller klikk på **Enheter** i venstre navigasjonsrute.

    ![Enhetsdetaljer](./media/data-platform-cds-create-entity/entitylist.png "Enhetsliste")

2. Du sletter enheten ved å klikke eller trykke på den på listen over enheter og deretter klikke eller trykke på alternativet **Slett enhet** på kommandolinjen.

3. Klikk eller trykk på **Slett** i dialogboksen som åpnes, for å slette enheten.

>[!NOTE]
>Når du sletter en enhet, sletter du både enhetsdefinisjonen og alle data som enheten inneholder. Du kan ikke gjenopprette enhetene og dataene i dem når de er slettet.

>[!NOTE]
>Apper og flyter kan bli ødelagt hvis du sletter en enhet som er brukt i dem.

>[!NOTE]
>Hvis enhet A har [oppslagsfelt](data-platform-entity-lookup.md) med forbindelse til enhet B, må du kanskje slette enhet B før du kan slette enhet A.

