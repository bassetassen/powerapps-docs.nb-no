---
title: Tilpass kommandoer med modelldrevne apper | Microsoft Docs
description: Lær hvordan du tilpasser kommandoer med modelldrevne apper
services: ''
suite: powerapps
documentationcenter: na
author: JimDaly
manager: faisalmo
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/17/2018
ms.author: jdaly
search.audienceType:
- developer
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: 4721ba49fe227d31f539eabd863b50842e7515b6
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/24/2018
ms.locfileid: "42836258"
---
# <a name="customize-commands-with-model-driven-apps"></a>Tilpass kommandoer med modelldrevne apper 

Kommandoene som vises i kommandolinjen til et skjema eller en liste, kan tilpasses. Kommandoer er basert på XML-skjemaene som brukes i Office-bånd, så begrepet *bånd* brukes fremdeles. Nå du oppretter en kommando, kan du definere tre elementer:

- *Visningsregler* evalueres når skjemaet eller listen lastes, for å fastslå om en kommando eller gruppe med kommandoer er synlig.
- *Aktiver regler* kontrollerer om en kommando er aktivert basert på en rekke betingelser, som gjeldende valgte elementet i brukergrensesnittet.
- En *handling* for hver kommando for å fortelle den hva som skal skje, når de er valgt. En kommando kan åpne en nettadresse eller kjøre en funksjon som er definert i en JavaScript-nettressurs.

Egendefinerte kommandoer plasseres basert på eventuelle eksisterende kommandoer. Du må opprette en *egendefinert handling* som definerer hvilke endringer som skal tas i bruk, for det gjeldende settet med kommandoer. 

Det er ingen utformingsverktøy for kommandoer. Men heldigvis har fellesskapet egne verktøy. [Båndarbeidsområdet](http://www.develop1.net/public/rwb/ribbonworkbench.aspx) har en grafisk grensesnitt og er det vanligste brukte verktøyet for å tilpasse kommandoer.

Hvis du vil ha mer informasjon, kan du se [Dynamics 365 Customer Engagement – Veiledning for utviklere: Tilpass kommandoer og båndet](/dynamics365/customer-engagement/developer/customize-dev/customize-commands-ribbon)


