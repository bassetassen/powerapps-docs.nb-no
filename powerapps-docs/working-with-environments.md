---
title: Å arbeide med miljøer| Microsoft Docs
description: Bytt miljøer og forstå hvordan innhold på sidene endres.
services: ''
suite: powerapps
documentationcenter: na
author: linhtranms
manager: anneta
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/14/2016
ms.author: litran
ms.openlocfilehash: ea9bd30ea9007800511e0f194c6f9f460773305e
ms.sourcegitcommit: 6afca7cb4234d3a60111c5950e7855106ff97e56
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 01/23/2018
ms.locfileid: "30986417"
---
# <a name="working-with-environments-and-microsoft-powerapps"></a>Å arbeide med miljøer og Microsoft PowerApps
Du kan arbeide i forskjellige miljøer og enkelt å bytte mellom dem med PowerApps. For en oversikt over miljøer, kan du se [Miljøoversikt](environments-overview.md), som forklarer i detalj hvorfor du bruker miljøer, og hvordan du kan opprette og administrere dem. Omfanget av denne artikkelen dekker følgende emner om miljø:

* Slik bytter du miljøet på powerapps.com
* Slik oppretter du en app i riktig miljø
* Slik viser du en app i riktig miljø

## <a name="switch-the-environment"></a>Bytt miljøet
Når du registrerer deg og logger på powerapps.com for første gang, vil du sannsynligvis havne i et standardmiljø. Du kan bekrefte dette ved å se øverst til høyre på siden.

![Standardmiljø](./media/working-with-environments/env-dropdown.png)

*Standardmiljøet* er tilgjengelig for alle. Du kan begynne å opprette apper i dette miljøet og dele appene med andre brukere. Du kan også ha tilgang til andre miljøer, for eksempel de du [oppretter selv](environments-administration.md), eller de som er opprettet av andre, men som du har tilgang til. Du kan bytte miljøer ved å klikke rullegardinlisten for miljø øverst til høyre, og velge et annet miljø. I dette eksemplet byttes det fra *Standardmiljø* til *Miljø 1*.

![Bytt miljø](./media/working-with-environments/switch-env.png)

Når man bytter til et annet miljø (for eksempel Miljø 1), vil man se alle apper man har opprettet, eller har tilgang til i dette nye miljøet.

## <a name="create-apps-in-the-right-environment"></a>Slik oppretter du en app i riktig miljø
Du kan opprette apper både i et nytt miljø og eksisterende miljøer som du har tilgang til. Å opprette et eget miljø krever imidlertid en bestemt plan. Hvis du vil ha mer informasjon, kan du se [dette emnet](pricing-billing-skus.md). Før du oppretter en app, må du alltid **kontrollere at du velger miljøet du vil at appen skal være i**. Ellers vil du måtte håndtere å flytte apper mellom miljøer.

1. Velg miljøet du ønsker å opprette appen i, hvis du er i [powerapps.com](http://web.powerapps.com). Hvis du er i *PowerApps Studio* eller *nettversjonen av PowerApps Studio*, hopper du til trinn 4.

2. Velg **+ Ny app**.

3. Velg **Åpne PowerApps Studio** eller **nettversjonen av PowerApps Studio**.

4. Velg miljøet på nytt øverst til høyre, når *PowerApps Studio* eller nettversjonen av *PowerApps Studio* åpnes. Vi vil forbedre denne opplevelsen i fremtiden, men i den gjeldende utgaven, må du velge dette hver gang du vil opprette en app i et nytt miljø.

    ![Bytt miljø i Studio](./media/working-with-environments/studio-switch-env.PNG)

5. Velg **Endre** på **Konto**-siden, ved siden av navnet på det gjeldende miljøet.

    ![Bytt miljø i Studio](./media/working-with-environments/studio-env-dropdown.PNG)

6. Velg miljøet der du ønsker å opprette appen.

    ![Bytt miljø i Studio](./media/working-with-environments/studio-env-dropdown2.PNG)

7. Velg **Ny** for å begynne å opprette en app. Appen vil nå befinne seg i miljøet du valgte i trinn 6.

    ![Bytt miljø i Studio](./media/working-with-environments/new-app.PNG)

## <a name="view-apps-in-the-right-environment"></a>Slik viser du en app i riktig miljø
Om du arbeider i [powerapps.com](http://web.powerapps.com), PowerApps Studio for Windows eller nettversjonen av PowerApps Studio, vil listen over apper, tilkoblinger, osv. som du ser, alltid filtreres basert på miljøet som er valgt i rullegardinlisten. Hvis du ikke ser appene du leter etter, må du alltid bekrefte om riktig miljø er valgt.

En gang til om bytting av miljøer i [powerapps.com](http://web.powerapps.com):

![Bytt miljø](./media/working-with-environments/switch-env.png)

Å bytte PowerApps Studio for Windows eller nettversjonen av PowerApps Studio:

![Bytt miljø i Studio](./media/working-with-environments/studio-switch-env.PNG)

Hvis du vil ha mer informasjon om miljøer, kan du se [denne oversikten](environments-overview.md).
