---
title: Oversikt over områder | Microsoft Docs
description: Finn ut om områder i PowerApps
author: manasmams
manager: kfile
ms.service: powerapps
ms.component: pa-admin
ms.topic: conceptual
ms.date: 03/21/2018
ms.author: manasma
ms.openlocfilehash: 818d751a45eee6d746d4f318a98169a771787d92
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/04/2018
ms.locfileid: "34445779"
---
# <a name="regions-overview-in-powerapps"></a>Oversikt over områder i PowerApps
## <a name="how-do-i-find-out-where-my-app-is-deployed"></a>Hvordan kan jeg finne ut hvor appen distribueres?
Appen er distribuert i området som er vert for miljøet. Hvis miljøet for eksempel er opprettet i Europa, er appen distribuert i datasentre i Europa.

Hvis du er administrator, kan du bestemme området for hvert miljø i administrasjonssenteret for PowerApps.

* Gå til [Administrasjonssenteret](https://admin.powerapps.com), og logg på med jobbkontoen din.
  
    I administrasjonssenteret er alle eksisterende miljøer oppført på **Miljøer**-fanen. Denne listen viser **området** der appen er distribuert:
  
   ![Miljøer-fanen](./media/regions-overview/environment-list.png)

## <a name="what-regions-are-available"></a>Hvilke områder er tilgjengelige?
* USA
* Canada
* Europa
* Asia
* Australia
* India
* Japan
* Storbritannia

## <a name="what-features-are-specific-to-a-given-region"></a>Hvilke funksjoner er spesifikke for et gitt område?
Miljøer kan opprettes i forskjellige områder, og er bundet til denne geografiske plasseringen. Når du oppretter en app i et miljø, blir appen distribuert til datasentre i denne geografiske plasseringen. Dette gjelder for alle elementene du oppretter i dette miljøet, inkludert databaser i Common Data Service, apper, tilkoblinger, gatewayer og egendefinerte koblinger.

Opprett og bruk miljøet i området Europa hvis brukerne er i Europa, for optimal ytelse. Opprett og bruk miljøet i USA hvis brukerne er i USA.

> [!NOTE]
> Du kan for øyeblikket bare opprette en database i et produksjons- eller prøveversjon-miljø, som er i samme region som Azure AD- eller Office 365-hjemområdet for tenanten. Vi arbeider for å aktivere oppretting av databaser i miljøer som er opprettet i en annen region enn din hjemplasseringen for tenanten din. Dessuten kan du for øyeblikket ikke opprette en database i standardmiljøet og et enkelt miljø (opprettet med PowerApps Community Plan).

> [!NOTE]
> Lokale datagatewayer er ikke tilgjengelige i India-området eller i egendefinerte miljøer. Du må opprette gatewayer i standardmiljøet.

