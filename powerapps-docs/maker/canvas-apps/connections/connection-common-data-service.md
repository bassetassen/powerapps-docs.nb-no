---
title: Koble til Common Data Service | Microsoft Docs
description: Finn ut hvordan du kobler til Common Data Service og bruker den til å utvikle apper i PowerApps.
author: tapanm-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: ''
ms.date: 04/22/2019
ms.author: tapanm
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: fcadc4d214494380f50f712e453554d41d08eabe
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/07/2019
ms.locfileid: "71994013"
---
# <a name="connect-to-common-data-service"></a>Koble til Common Data Service

Du kan lagre forretnings dataene på en sikker måte i Common Data Service og bygge rike apper i PowerApps, slik at brukerne kan administrere disse dataene. Du kan også integrere dataene i løsninger som inkluderer Microsoft Flow, Power BI og data fra Dynamics 365.

Som standard kobler Common Data Service-koblingen til data i appens gjeldende miljø. Hvis appen flyttes til et annet miljø, kobles koblingen til data i det nye miljøet. Denne virke måten fungerer bra for en app som bruker et enkelt miljø eller en app som følger en ALM-prosess for flytting av utvikling til testing til produksjon.

Når du legger til en data kilde med Common Data Service koblingen, kan du endre miljøet og deretter velge én eller flere enheter. Som standard kobles appen til data i gjeldende miljø, og bruker grensesnittet viser **(gjeldende)** over listen over enheter.

> [!div class="mx-imgBorder"]
> ![Default-miljø @ no__t-1

Hvis du velger **endre**, kan du angi et annet miljø for å hente data fra dem i stedet for eller i tillegg til det gjeldende miljøet.

> [!div class="mx-imgBorder"]
> @no__t miljøer i 0Other @ no__t-1

Navnet på det valgte miljøet vises under søke boksen.

> [!div class="mx-imgBorder"]
> @no__t miljøer i 0New @ no__t-1

Common Data Service koblingen er mer robust enn Dynamics 365-koblingen og nærmer seg funksjons paritet.

Mer informasjon: [Hva er Common Data Service?](../../common-data-service/data-platform-intro.md)
