---
title: Behandling av policyer for hindring av datatap (DLP) | Microsoft Docs
description: Gjennomgang av hvordan du behandler policyer for hindring av datatap for PowerApps.
author: manasmams
manager: kvivek
ms.service: powerapps
ms.component: pa-admin
ms.topic: conceptual
ms.date: 03/21/2018
ms.author: manasma
search.audienceType:
- admin
search.app:
- D365CE
- PowerApps
- Powerplatform
ms.openlocfilehash: 4faa8a4cc58b138eec4e7dfe8d35b927faf905b7
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/24/2018
ms.locfileid: "42837166"
---
# <a name="manage-data-loss-prevention-dlp-policies"></a>Behandle policyer for hindring av datatap
Organisasjonens data er kritiske for bedriftens suksess. Dataene skal være lett tilgjengelige ved beslutningstakinger, men de skal være beskyttet slik at de ikke er delt med målgrupper som ikke burde ha tilgang. Hvis du vil beskytte disse dataene, kan du i PowerApps opprette og håndheve DLP-policyene, som angir hvilke forbrukerkoblinger bestemte forretningsdata kan deles med. En organisasjon som bruker PowerApps ønsker nok for eksempel ikke at forretningsdataene deres som er lagret i SharePoint skal publiseres automatisk til Twitter-feeden.

Hvis du vil opprette, redigere eller slette DLP-policyer, må du ha enten miljøadministrator-tillatelser eller tenantadministrator-tillatelser for Azure Active Directory. Hvis du vil ha mer informasjon, kan du se [Miljøadministrasjon i PowerApps](environments-administration.md).

Hvis du vil ha instruksjoner om hvordan du oppretter en DLP-policy, kan du se [Opprett en policy for hindring av datatap (DLP)](create-dlp-policy.md).

## <a name="find-a-dlp-policy"></a>Å finne en DLP-policy
1. Logg deg på administrasjonssenteret på [https://admin.powerapps.com]([https://admin.powerapps.com).
2. Klikk eller trykk på **Datapolicyer** i navigasjonsruten. Hvis du har en lang liste med policyer, bruker du **Søk**-boksen for å finne bestemte DLP-policyer.

    ![](./media/prevent-data-loss/data-policies.png)

## <a name="edit-a-dlp-policy"></a>Å redigere en DLP-policy
1. Klikk eller trykk på blyantikonet ved siden av policyen du vil redigere, i listen over Policyer for hindring av tap av data.

    ![Logg på](./media/prevent-data-loss/3.png)
2. Foreta endringene, og deretter klikker eller trykker du på **Lagre policy**.

    > [!NOTE]
    > Miljømessige DLP-policyer kan ikke overstyre DLP-policyer som omfatter hele tenanten.
    >
    >

    Hvis du vil se gjennom endringene, finner du DLP-policyen i listen over policyer for hindring av tap av data, og klikker eller trykker på den for å se gjennom egenskapene.

## <a name="delete-a-dlp-policy"></a>Å slette en DLP-policy
1. Klikk eller trykk på papirkurv-ikonet ved siden av policyen du vil slette, i listen over Policyer for hindring av tap av data.

    ![Logg på](./media/prevent-data-loss/3-delete.png)
4. Klikk eller trykk på dialogboksen **Slett**.

    Policyen er slettet, og vil ikke lenger vises i listen over policyer for hindring av tap av data.

## <a name="next-steps"></a>Neste trinn
* [Finn ut mer om miljøer](environments-administration.md)
* [Å finne ut mer om Microsoft PowerApps](../maker/canvas-apps/getting-started.md)
