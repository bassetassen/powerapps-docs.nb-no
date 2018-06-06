---
title: 'Hurtigstart: Slik sletter du egendefinerte enheter og fjerner data | Microsoft Docs'
description: 'Hurtigstart: Slette egendefinerte enheter og fjerne alle data'
services: powerapps
documentationcenter: na
author: clwesene
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 3/21/2018
ms.author: clwesene
ms.openlocfilehash: 399d3e8bac215df7612ac12d922dfe644dc59f96
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/22/2018
ms.locfileid: "30997322"
---
# <a name="quickstart-delete-a-custom-entity"></a>Hurtigstart: Slette egendefinerte enheter
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

