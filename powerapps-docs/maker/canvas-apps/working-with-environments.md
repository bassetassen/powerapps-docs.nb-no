---
title: Å arbeide med miljøer| Microsoft Docs
description: Bytt miljøer og forstå hvordan innhold på sidene endres.
documentationcenter: na
author: linhtranms
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: conceptual
ms.component: canvas
ms.date: 10/14/2016
ms.author: litran
ms.openlocfilehash: 4bf196041853e9f88c97aabcd3ff1c234b2608be
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/04/2018
ms.locfileid: "32329483"
---
# <a name="working-with-environments-and-microsoft-powerapps"></a>Å arbeide med miljøer og Microsoft PowerApps
Du kan arbeide i forskjellige miljøer og enkelt å bytte mellom dem med PowerApps. For en oversikt over miljøer, kan du se [Miljøoversikt](../../administrator/environments-overview.md), som forklarer i detalj hvorfor du bruker miljøer, og hvordan du kan opprette og administrere dem. Omfanget av denne artikkelen dekker følgende emner om miljø:

* Slik bytter du miljøet på powerapps.com
* Slik oppretter du en app i riktig miljø
* Slik viser du en app i riktig miljø

## <a name="switch-the-environment"></a>Slik bytter du miljøet
Når du registrerer deg og logger på powerapps.com for første gang, vil du sannsynligvis havne i et standardmiljø. Du kan bekrefte dette ved å se øverst til høyre på siden.

![Standardmiljø](./media/working-with-environments/env-dropdown.png)

*Standardmiljøet* er tilgjengelig for alle. Du kan begynne å opprette apper i dette miljøet og dele appene med andre brukere. Du kan også ha tilgang til andre miljøer, for eksempel de du [oppretter selv](../../administrator/environments-administration.md), eller de som er opprettet av andre, men som du har tilgang til. Du kan bytte miljøer ved å klikke rullegardinlisten for miljø øverst til høyre, og velge et annet miljø. I dette eksemplet byttes det fra *Standardmiljø* til *Miljø 1*.

![Slik bytter du miljøet](./media/working-with-environments/switch-env.png)

Når man bytter til et annet miljø (for eksempel Miljø 1), vil man se alle apper man har opprettet, eller har tilgang til i dette nye miljøet.

## <a name="create-apps-in-the-right-environment"></a>Slik oppretter du en app i riktig miljø
Du kan opprette apper i et miljø som du oppretter, eller som du har fått tilgang til. Å opprette et eget miljø krever imidlertid en [bestemt plan](../../administrator/pricing-billing-skus.md). Før du oppretter en app, må du alltid **kontrollere at du velger miljøet du vil at appen skal være i**. Ellers vil du måtte håndtere å flytte apper mellom miljøer.

Hvis du vil opprette en app i det rette miljøet, gjør du ett av følgende:

- [Logg deg på](http://web.powerapps.com) PowerApps Studio hvis det ikke er åpent allerede, og velg deretter miljøet du ønsker å opprette appen din i. Velg så **Apper** nær venstre kant, og velg til slutt **Opprett en app**.

- Hvis PowerApps Studio er åpen, velger du miljøet på nytt øverst til høyre.

5. Velg **Endre** på **Konto**-siden, ved siden av navnet på det gjeldende miljøet.

6. Velg miljøet der du ønsker å opprette appen.

    ![Slik bytter du miljø i Studio](./media/working-with-environments/studio-env-dropdown2.PNG)

7. Velg **Ny** for å begynne å opprette en app. Appen vil nå befinne seg i miljøet du valgte i trinn 6.

    ![Slik bytter du miljø i Studio](./media/working-with-environments/new-app.PNG)

## <a name="view-apps-in-the-right-environment"></a>Slik viser du en app i riktig miljø
Enten du arbeider i [powerapps.com](http://web.powerapps.com) eller PowerApps Studio, er listen over apper, tilkoblinger osv. som du ser alltid filtrert basert på miljøet som er valgt i rullegardinlisten. Hvis du ikke ser appene du leter etter, må du alltid bekrefte om riktig miljø er valgt.

Hvis du vil ha mer informasjon om miljøer, kan du se [denne oversikten](../../administrator/environments-overview.md).
