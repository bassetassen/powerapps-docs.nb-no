---
title: 'Utviklere: Anbefalte fremgangsmåter og veiledning for skripting på klientsiden for modelldrevne apper | Microsoft Docs'
description: Anbefalte fremgangsmåter og veiledning for skripting på klientsiden for utviklere av modelldrevne apper i PowerApps.
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
ms.date: 12/12/2018
ms.author: jowells
search.audienceType:
- developer
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: e2b43178882cb66abba2305f65f78855915591ed
ms.sourcegitcommit: 44ca0a386fce0c4a18310b515a4880065942dd05
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/12/2019
ms.locfileid: "59537831"
---
# <a name="best-practices-and-guidance-of-client-side-scripting-for-model-driven-apps"></a>Anbefalte fremgangsmåter og veiledning for skripting på klientsiden for modelldrevne apper

Listen nedenfor inneholder alle de anbefalte fremgangsmåtene og veiledningene knyttet til skripting på klientsiden for modelldrevne apper.

|Anbefalt fremgangsmåte  |Beskrivelse  |
|---------|---------|
|[Unngå bruk av window.top](avoid-window-top.md)     |Beskriver hvordan du kan unngå skriptfeil og feilaktig programvirkemåte knyttet til bruken av window.top i JavaScript-tilpassinger.         |
|[Vurder å deaktivere navigasjonsfeltet når du åpner enhetsskjemaer eller -visninger programmatisk](consider-disabling-navbar-programmatically-opening-entity-forms-views.md)|Hvis du åpner enhetsskjemaer eller -visninger med en nettadresse, kan det føre til lavere ytelse for klienten på nettverk med høy ventetid når navigasjonsfeltet (Navigasjonsfelt) er aktivert.|
|[Anbefalte fremgangsmåter: Klientskripting i modelldrevne apper](../../clientapi/client-scripting-best-practices.md)     |Noen av de anbefalte fremgangsmåtene du bør vurdere mens du skriver JavaScript-kode for modelldrevne apper.         |
|[Samhandle med HTTP- og HTTPS-ressurser asynkront](interact-http-https-resources-asynchronously.md)     |Du bør samhandle med HTTP- og HTTPS-ressurser asynkront når du skriver JavaScript-klientutvidelser for modelldrevne apper.         |
|[Fjern deaktiverte tilpasninger](remove-deactivated-disabled-configurations.md)     |Deaktiverte tilpassinger bør fjernes fra en løsning for å forbedre løsningsbehandlingen, og for å redusere risikoen for bruk eller behandling av en utdatert komponent.         |

# <a name="see-also"></a>Se også
[Bruk forretningslogikk med klientskripting](../../client-scripting.md) <br />
 