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
ms.openlocfilehash: 6ef9dc3a1c82fdee9927ffd533ed41386345eaf7
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/04/2018
ms.locfileid: "34167565"
---
# <a name="delete-a-custom-entity"></a>Slett en egendefinert enhet
Du kan slette egendefinerte enheter, men ikke standardenheter.

1. Utvid **Data**-delen på [powerapps.com](https://web.powerapps.com), og trykk eller klikk på **Enheter** i venstre navigasjonsrute.

    ![Enhetsdetaljer](./media/data-platform-cds-create-entity/entitylist.png "Enhetsliste")

2. Du sletter enheten ved å klikke eller trykke på den på listen over enheter og deretter klikke eller trykke på alternativet **Slett enhet** på kommandolinjen.

3. Klikk eller trykk på **Slett** i dialogboksen som åpnes, for å slette enheten.

>[!NOTE]
>Når du sletter en enhet, sletter du både enhetsdefinisjonen og alle data som enheten inneholder. Du kan ikke gjenopprette enhetene og dataene i dem når de er slettet.

>[!NOTE]
>Apper og flyter kan bli ødelagt hvis du sletter en enhet som er brukt i dem.

>[!NOTE]
>Hvis enhet A har [oppslagsfelt](data-platform-entity-lookup.md) med forbindelse til enhet B, må du kanskje slette enhet B før du kan slette enhet A.

