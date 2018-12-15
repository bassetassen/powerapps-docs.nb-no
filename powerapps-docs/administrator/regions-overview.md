---
title: Oversikt over områder | Microsoft Docs
description: Finn ut om områder i PowerApps
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
ms.openlocfilehash: a3ea651fd507bb257a3b778be4421454197733b9
ms.sourcegitcommit: eec10beaee913e01fe488c839661b20bbb1e1cfc
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 12/13/2018
ms.locfileid: "53329279"
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

Opprett og bruk miljøet i området Europa hvis brukerne er i Europa, for optimal ytelse. Opprett og bruk miljøet i USA, hvis brukerne er i USA.

> [!NOTE]
> Lokale datagatewayer er ikke tilgjengelige i India-området, eller i egendefinerte miljøer. Du må opprette gatewayer i standardmiljøet.

