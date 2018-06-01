---
title: Oversikt over områder | Microsoft Docs
description: 'Områder i PowerApps: hvor apper er distribuert, tilgjengelig områder og funksjoner som er spesifikke for et område'
services: ''
suite: powerapps
documentationcenter: na
author: skjerland
manager: anneta
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 05/04/2017
ms.author: sharik
ms.openlocfilehash: 114aa01bd745ed501e209e314e75904751aad3f5
ms.sourcegitcommit: 6afca7cb4234d3a60111c5950e7855106ff97e56
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 01/23/2018
ms.locfileid: "30986387"
---
# <a name="regions-overview-in-powerapps"></a>Oversikt over områder i PowerApps
## <a name="how-do-i-find-out-where-my-app-is-deployed"></a>Hvordan kan jeg finne ut hvor appen distribueres?
Appen er distribuert i området som er vert for miljøet. Hvis miljøet for eksempel er opprettet i Europa, er appen distribuert i datasentre i Europa.

Hvis du er administrator, kan du bestemme området for hvert miljø i administrasjonssenteret for PowerApps.

* Gå til [Administrasjonssenteret](https://admin.powerapps.com), og Logg på med jobbkontoen din.
  
    I administrasjonssenteret er alle eksisterende miljøer oppført på **Miljøer**-fanen. Denne listen viser **Området** der appen er distribuert:
  
   ![Miljøer-fanen](./media/regions-overview/environment-list.png)

## <a name="what-regions-are-available"></a>Hvilke områder er tilgjengelige?
* USA
* Canada
* Europa
* Asia
* Australia
* India
* Japan

## <a name="what-features-are-specific-to-a-given-region"></a>Hvilke funksjoner er spesifikke for et gitt område?
Miljøer kan opprettes i forskjellige områder, og er bundet til denne geografiske plasseringen. Når du oppretter en app i et miljø, blir appen distribuert til datasentre i denne geografiske plasseringen. Dette gjelder for alle elementene du oppretter i dette miljøet, inkludert databaser i Common Data Service, apper, tilkoblinger, gatewayer og egendefinerte koblinger.

Opprett og bruk miljøet i området Europa, hvis brukerne er i Europa, for optimal ytelse. Opprett og bruk miljøet i USA, hvis brukerne er i USA.

> [!NOTE]
> Lokale datagatewayer er ikke tilgjengelige i India-området, eller i egendefinerte miljøer. Du må opprette gatewayer i standardmiljøet.

