---
title: Koble til Common Data Service | Microsoft Docs
description: Lær hvordan du kobler til Common Data Service-og bruker den for å bygge apper i PowerApps.
author: aftowen
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: ''
ms.date: 04/22/2019
ms.author: anneta
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: c521fd5961bc9b8d940a374383baca1aeef0cbe4
ms.sourcegitcommit: 93096dfa1aadba77159db1e5922f3d5528eecb7a
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 05/21/2019
ms.locfileid: "65986422"
---
# <a name="connect-to-common-data-service"></a>Koble til Common Data Service

Du kan lagre forretningsdataene i Common Data Service-sikkert og bygge rike apper i PowerApps slik at brukere kan administrere disse dataene. Du kan også integrere dataene i løsninger som inkluderer Microsoft Flow, Power BI og data fra Dynamics 365.

Som standard kobler Common Data Service-koblingen til data i appen din gjeldende environmnent. Hvis appen din flytter til et annet miljø, kobles koblingen til data i det nye miljøet. Dette fungerer bra for en app ved hjelp av et enkelt miljø eller en app som følger en ALM-prosess for å flytte fra utvikling til testing til produksjon.

Når du legger til en datakilde med Common Data Service-koblingen, kan du endre miljøet, og velg deretter én eller flere enheter. Som standard appen kobles til data i det gjeldende miljøet, og viser Brukergrensesnittet **(gjeldende)** over listen over enheter.

> [!div class="mx-imgBorder"]
> ![Standardmiljø](media/connection-common-data-service/common-data-service-connection-change-environment.png)

Hvis du velger **endre**, kan du angi et annet miljø til å hente data fra den i stedet for eller i tillegg til det gjeldende miljøet.

> [!div class="mx-imgBorder"]
> ![Andre miljøer](media/connection-common-data-service/common-data-service-connection-select-environment.png)

Navnet på det valgte miljøet vises under søkeboksen.

> [!div class="mx-imgBorder"]
> ![Nye miljøer](media/connection-common-data-service/common-data-service-connection-after-change-environment.png)

Common Data Service-koblingen er kraftigere enn til Dynamics 365-koblingen, og nærmer seg funksjonen paritetskontroll.

Mer informasjon: [Hva er Common Data Service?](../../common-data-service/data-platform-intro.md)
