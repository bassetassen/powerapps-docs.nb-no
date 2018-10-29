---
title: Administrer en PowerApps Enterprise-distribusjon | MicrosoftDocs
description: Les hvitboken om hvordan du administrerer en PowerApps Enterprise-distribusjon.
ms.custom: ''
ms.date: 08/09/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: get-started-article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
ms.assetid: 83200632-a36b-4401-ba41-952e5b43f939
caps.latest.revision: 31
author: jimholtz
ms.author: jimholtz
manager: kvivek
search.audienceType:
- admin
search.app:
- D365CE
- PowerApps
- Powerplatform
ms.openlocfilehash: ce8daad960834c2965e2a5432ccaf2a3f515e503
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/24/2018
ms.locfileid: "42857498"
---
# <a name="administering-a-powerapps-enterprise-deployment"></a>Administrer en PowerApps Enterprise-distribusjon

PowerApps er en programutviklingsplattform med høy produktivitet fra Microsoft.  Plattformen brukes av Microsoft for å bygge deres egen førstepartsprogrammer for Dynamics 365 for Sales, Service, Field Service, Marketing and Talent.  Dette betyr at disse programmene er opprinnelig bygget på plattformen.   Bedriftskunder kan også bygge sin egne bedriftsprogrammer ved bruk av samme teknologi.  Individuelle brukere og team i organisasjonen kan også bygge produktivitetsprogrammer uten kode, eller med svært lite kode. 

Les den følgende nedlastbare hvitboken: [Administrer en PowerApps Enterprise-distribusjon](https://aka.ms/powerappsadminwhitepaper)

Denne hvitboken er rettet mot systemansvarlig for Enterprise-programmer med ansvar for planlegging, sikring, distribusjon og støtte programmer, som er bygget på PowerApps- plattformen.  Hensikten med hvitboken er å hjelpe deg forstå hva som befinner seg i miljøet ditt for øyeblikket, hvordan du proaktivt planlegger for utvikling og distribuering av programmer, og til slutt hvordan du håndterer de daglige administrative oppgavene for å behandle distribusjoner.
I denne hvitboken tar vi for oss viktige konsepter, plattformarkitektur, og nødvendige beslutninger.  Det er mulig at vi hjelper deg med å utvikle anbefalte fremgangsmåter for organisasjonen, for å sikre vellykkede distribusjoner og høy produktivitet for brukerne som bruker plattformen.

PowerApps-plattformen er en del av den større Microsoft Power-plattformen som også inkluderer PowerBI og Microsoft Flow, og den drar nytte av den vanlige infrastrukturen til Common Data Service for apper og datakoblinger. Disse funksjonene er bygget på og drar nytte av Microsoft Azure-skytjenestene.  Programmer som er bygget på PowerApps-plattformen, kan også inkludere Azure-skytjenester for å skalere fra individuell produktivitet til driftskritiske forretningsprogrammer.

![Microsoft Power-plattform](media/ms-power-platform.png "Microsoft Power-plattform")
