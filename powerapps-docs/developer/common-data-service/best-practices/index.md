---
title: 'Utviklere: Anbefalte fremgangsmåter og veiledning for Common Data Service | Microsoft Docs'
description: Anbefalte fremgangsmåter og veiledning for utviklere av Common Data Service i PowerApps.
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
ms.date: 01/07/2019
ms.author: jowells
search.audienceType:
- developer
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: c89042e1f94e6f891bfdc255c38f72929c27cb1e
ms.sourcegitcommit: 5b2b70c3fc7bcba5647d505a79276bbaad31c610
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/22/2019
ms.locfileid: "58357349"
---
# <a name="best-practices-and-guidance-for-the-common-data-service"></a>Anbefalte fremgangsmåter og veiledning for Common Data Service

Common Data Service er et omfattende rammeverk som lar utviklere bygge svært tilpassede og skreddersydde opplevelser. Når utviklere tilpasser, utvider eller integrerer med Common Data Service, bør de være oppmerksomme på etablerte veiledninger og anbefalte fremgangsmåter. 

I denne inndelingen kan du lese om problemene som vi har identifisert, innvirkningen de har, og forstå veiledningen for å løse dem. Vi forklarer bakgrunnen for hvorfor ting gjøres på en bestemt måte, og for å unngå potensielle problemer i fremtiden. Dette kan øke brukervennligheten, støttemuligheten og ytelsen til miljøet. Veiledningsdokumentasjonen støtter den eksisterende informasjonen som finnes i utvikler- og administrasjonsveiledningene.

# <a name="targeted-customization-types"></a>Målrettede tilpassingstyper
Dokumentasjonen retter seg mot følgende tilpassingstyper:

- Egendefinerte arbeidsflytaktiviteter og programtillegg
- Arbeide med data for Common Data Service
- Integreringer som utvider Common Data Service

# <a name="sections"></a>Inndelinger
Hver veiledningsartikkel inneholder de fleste eller alle av følgende inndelinger:

- Tittel – beskrivelse av veiledningen
- Kategori – ett eller flere områder som påvirkes av ikke å følge veiledningen
- Innvirkningspotensiale – risikonivået (høyt, middels eller lavt) for å påvirke miljøet ved ikke å følge veiledningen
- Symptomer – mulige indikasjoner på at veiledningen ikke har blitt fulgt
- Veiledning – anbefalinger som også kan inneholde eksempler
- Problematiske mønstre – beskrivelse eller eksempler på ikke å følge veiledningen
- Tilleggsinformasjon – støttedetaljer for en mer omfattende visning
- Se også – referanser for å finne ut mer om noe som er nevnt i kategorien

# <a name="categories"></a>Kategorier
Hver veiledningsartikkel er klassifisert med én eller flere av følgende kategorier:

- Bruk – feilaktig bruk av en bestemt API, mønster eller konfigurasjon
- Utforming – utformingsfeil i en tilpassing
- Ytelse – tilpassing eller mønster som kan forårsake en negativ innvirkning på ytelsen i forbindelse med minnebehandling, prosessorutnyttelse, nettverkstrafikk eller brukeropplevelse
- Sikkerhet – potensielle sikkerhetsproblemer i en tilpassing som kan utnyttes i et kjøretidsmiljø
- Klargjøring av oppgradering – tilpassing eller mønster som kan øke risikoen for en mislykket versjonsoppgradering
- Overføring på nettet – tilpassing eller mønster som kan øke risikoen for en mislykket overføring på nettet
- Vedlikehold – tilpassing som unødvendig øker arbeidet en utvikler må gjøre for å foreta endringer, frekvensen av nødvendige endringer, eller muligheten for å introdusere regresjoner
- Støttemulighet – tilpassing eller mønster som faller utenfor grensene til publiserte kunngjøringer for støttemuligheten, inkludert bruk av fjernede API-er eller implementering av forbudte teknikker
