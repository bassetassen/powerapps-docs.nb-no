---
title: 'Utviklere: Anbefalte fremgangsmåter og veiledning knyttet til programtilleggs- og arbeidsflytutvikling for Common Data Service for apper | Microsoft Docs'
description: Anbefalte fremgangsmåter og veiledning knyttet til programtilleggs- og arbeidsflytutvikling for utviklere i Common Data Service for apper i PowerApps.
services: ''
suite: powerapps
documentationcenter: na
author: jowells
manager: austinj
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 1/15/2019
ms.author: jowells
search.audienceType:
- developer
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: 87e7337a4bf62a10647edfd9b6c17bce0a0903bf
ms.sourcegitcommit: 72c97378e96fb54e5d92ec087a59dd0fb1444f99
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 01/16/2019
ms.locfileid: "54334021"
---
# <a name="best-practices-and-guidance-regarding-plug-in-and-workflow-development-for-the-common-data-service-for-apps"></a>Anbefalte fremgangsmåter og veiledning knyttet til programtilleggs- og arbeidsflytutvikling for Common Data Service for apper

Listen nedenfor inneholder alle de anbefalte fremgangsmåtene og veiledningene knyttet til programtilleggs- og arbeidsflytutvikling i Common Data Service for apper.

|Anbefalt fremgangsmåte  |Beskrivelse  |
|---------|---------|
|[Unngå bruk av satsvise forespørselstyper i programtilleggs- og arbeidsflytaktiviteter](avoid-batch-requests-plugin.md)     |Du må ikke bruke meldingsforespørselsklassene ExecuteMultipleRequest eller ExecuteTransactionRequest i forbindelse med et programtilleggs- eller en arbeidsflytaktivitet.         |
|[Utvikle IPlugin-implementeringer som tilstandsløs](develop-iplugin-implementations-stateless.md)     |Medlemmer av klasser som implementerer iPlugin, utsettes for potensielle trådsikkerhetsproblemer. Dette kan føre til datainkonsekvens eller ytelsesproblemer.         |
|[Ikke duplisere trinnregistrering for programtillegg](do-not-duplicate-plugin-step-registration.md)     |Trinnregistrering for programtillegg forårsaker at programtillegget kjøres flere ganger for samme melding/hendelse.         |
|[Inkluder filtreringsattributter med programtilleggsregistrering](include-filtering-attributes-plugin-registration.md)     |Hvis ingen filtreringsattributter er angitt for et trinn for programtilleggsregistrering, kjøres programtillegget hver gang en oppdateringsmelding skjer for den hendelsen.         |
|[Begrens registreringen av programtillegg for Retrieve- og RetrieveMultiple-meldinger](limit-registration-plugins-retrieve-retrievemultiple.md)     |Hvis du legger til synkron programtilleggslogikk til Retrieve- og RetrieveMultiple-meldingshendelser, kan det forårsake treghet.         |
|[Optimaliser tilpasset samlingsutvikling](optimize-assembly-development.md)     |Vurder å slå sammen separate programtillegg/tilpassede arbeidsflytaktiviteter i en enkelt tilpasset samling for å forbedre ytelsen og vedlikeholdet. Du kan også flytte programtillegg/tilpassede arbeidsflytaktiviteter til flere tilpassede samlinger hvis en samlingsstørrelse nærmer seg størrelsesbegrensningene for sandkassesamlingen.         |
|[Angi KeepAlive til usann når du samhandler med eksterne verter i et programtillegg](set-keepalive-false-interacting-external-hosts-plugin.md)     |Hvis KeepAlive-egenskapen er angitt til sann i HTTP-forespørselsoverskriften, eller ikke uttrykkelig er angitt som usann, kan det medføre at programtillegget kjører flere ganger enn nødvendig.         |
|[Bruk InvalidPluginExecutionException i programtillegg og arbeidsflytaktiviteter](use-invalidpluginexecutionexception-plugin-workflow-activities.md)     |Bruk InvalidPluginExecutionException når du angir feil i konteksten til programtillegget eller arbeidsflytaktiviteten.         |

# <a name="see-also"></a>Se også
[Bruk forretningslogikk med kode](../../apply-business-logic-with-code.md)<br />
[Bruk programtillegg til å utvide forretningsprosesser](../../plug-ins.md)<br />
[Arbeidsflytutvidelser](../../workflow/workflow-extensions.md)<br />