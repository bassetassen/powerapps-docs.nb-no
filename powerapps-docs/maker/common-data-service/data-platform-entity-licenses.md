---
title: Lisenskrav for enheter | Microsoft Docs
description: En forklaring av lisenskrav for enheter i Common Data Service (CDS) for apper.
author: clwesene
manager: kfile
ms.service: powerapps
ms.component: cds
ms.topic: conceptual
ms.date: 05/01/2018
ms.author: clwesene
ms.openlocfilehash: 716e1c2b7e670d8a54e1106cd557bb509323ba8d
ms.sourcegitcommit: b3b6118790d6b7b4285dbcb5736e55f6e450125c
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 05/15/2018
ms.locfileid: "34167108"
---
# <a name="license-requirements-for-entities"></a>Lisenskrav for enheter
Applagere kan bruke de fleste enheter som er tilgjengelige i Common Data Service (CDS) for apper (inkludert egendefinerte enheter og enheter som er en del av Common Data Model) for å opprette apper og flyt for brukere som bare en PowerApps Plan 1- eller Microsoft Flow Plan 1-lisens. I noen tilfeller kan enheter inneholde kompleks forretningslogikk eller er knyttet til Dynamics 365-produkter som krever at appbrukere har en bestemt lisens. Hvis du vil ha mer informasjon om tilgjengelige abonnementer, se [PowerApps-prissiden](https://powerapps.microsoft.com/pricing).

> [!NOTE]
> Apper og flyt som bruker disse enhetene krever at apper og flytbrukeren er lisensiert på riktig måte&mdash;ikke lageren eller utvikleren av appen eller flyten.

## <a name="entities-with-complex-business-logic"></a>Enheter med kompleks forretningslogikk
Enheter som inkluderer følgende kompleks serversidelogikk krever at brukere av en app eller flyt som bruker disse enhetene har en lisens for PowerApps Plan 2 eller Microsoft Flow Plan 2:

* Kodeplugin-moduler (Hvis du vil ha mer informasjon, se [plugin-modulutvikling](https://docs.microsoft.com/dynamics365/customer-engagement/developer/plugin-development))
* Sanntidsarbeidsflyter (Hvis du vil ha mer informasjon, se [arbeidsflytprosesser](https://docs.microsoft.com/dynamics365/customer-engagement/customize/workflow-processes))

    > [!NOTE]
    >  Bare arbeidsflyter som konverteres til en sanntidsarbeidsflyt vurderes i sanntid og er synkrone. Arbeidsflyter som kjører i bakgrunnen kan fortsatt brukes med den riktige PowerApps-planen, og krever ikke flere lisenser.

Hvis du vil vite om du har lagt til kompleks forretningslogikk til enheter, se gjennom listen over plugin-modulsamlinger og arbeidsflyter som er konfigurert i miljøet ditt.

## <a name="impacting-license-requirements-when-adding-complex-business-logic"></a>Påvirker lisenskrav når du legger til kompleks forretningslogikk
Applagere kan legge til kodeplugin-moduler og sanntidsarbeidsflyter til enheter i CDS for apper, men å gjøre det kan endre lisenskrav for brukere av apper som allerede er distribuert. Applagere bør være forsiktige når de legger til kompleks forretningslogikk til en enhet og bør først sjekke hvilke enheter som bruker enheten og om brukere av disse appene har passende lisenser.

## <a name="entities-restricted-to-dynamics-365-licenses"></a>Enheter som er begrenset til Dynamics 365-lisenser
Enkelte enheter som er knyttet til funksjonaliteten til Dynamics 365-produkter krever at appbrukere har tilhørende lisens for dette produktet gvis de ønsker å opprette, oppdatere eller slette poster i enhetene. For en fullstendig liste over begrensede enheter, kan du se [Begrensede enheter som krever Dynamics 365-lisenser](data-platform-restricted-entities.md).

## <a name="licensing-example"></a>Lisensieringseksempel
Barb og Isaac oppretter apper i PowerApps ved hjelp av CDS for apper for lagring av data.

Barb oppretter to lerretapper:

* App 1 &ndash; bruker kontaktenheten sammen med en tilpasset enhet som lagrer relatert informasjon
* App 2 &ndash; bruker kontaktenheten sammen med hendelsesenheten, som er en begrenset enhet

Isaac oppretter to modelldrevne apper:

* App 3 &ndash; bruker kontaktenheten sammen med en egendefinert enhet som lagrer relatert informasjon
* App 4 &ndash; bruker kontaktenheten sammen med hendelsesenheten, som er en begrenset enhet

Barn og Isaac trenger følgende lisenser:
* Barb trenger en PowerApps Plan 1-lisens for å opprette lerretapper med CDS for apper. Hvis hun trenger å opprette en database eller opprette en egendefinert enhet, trenger hun en PowerApps Plan 2-lisens.

* Isaac trenger en PowerApps Plan 2-lisens for å bygge modelldrevne apper.

Appbrukere trenger følgende lisenser:
* App 1-brukere trenger bare en PowerApps Plan 1- eller Plan 2-lisens, ettersom appen ikke inneholder alle enheter med kompleks forretningslogikk eller begrensede enheter.

* App 2-brukere trenger en Dynamics 365 for kundeservice, Enterprise-utgavelisens (eller en Dynamics 365 eller Dynamics 365-kundeengasjementplan), siden appen inneholder en begrenset enhet.

* App 3-brukere trenger en lisens for PowerApps Plan 2, fordi det er en modelldrevet app.

* App 4-brukere trenger en Dynamics 365 for kundeservice, Enterprise-utgavelisens (eller en Dynamics 365 eller Dynamics 365-kundeengasjementsplan), siden appen inkluderer en registrert enhet.

    Dynamics 365 for kundeserviceplanen inkluderer en PowerApps Plan 2-lisens, som lar brukere kjøre modelldrevne apper.

La oss nå se hva som skjer når Isaac legger til en sanntidsarbeidsflyt i den egendefinerte enheten som bruker både Barb og Isaac i appene sine.

Barn og Isaac trenger følgende lisenser:
* Barb trenger fortsatt en PowerApps Plan 1-lisens for å opprette lerretapper med CDS for apper.

* Isaac trenger fortsatt en PowerApps Plan 2-lisens for å bygge modelldrevne apper.

Appbrukere trenger følgende lisenser:
* App 1-brukere trenger nå en PowerApps Plan 2-lisens, fordi programmet inneholder en enhet med en arbeidsflyt for sanntid.

* App 2-brukere trenger fremdeles en Dynamics 365 for kundeservice, Enterprise-utgavelisens (eller en Dynamics 365 eller Dynamics 365-kundeengasjementsplan), siden appen inneholder en begrenset enhet. 

* App 3-brukere trenger fortsatt en PowerApps Plan 2-lisens, siden det er en modelldrevet app.

* App 4-brukere trenger fortsatt en Dynamics 365 for kundeservice, Enterprise-utgavelisens (eller en Dynamics 365 eller Dynamics 365-kundeengasjementsplan), siden appen inkluderer en registrert enhet.

    Dynamics 365 for kundeserviceplanen inkluderer en PowerApps Plan 2-lisens, som lar brukere kjøre modelldrevne apper.

Den eneste appen som påvirkes av denne endringen er App 1, som tidligere krevde en PowerApps Plan 1-lisens, men krever nå en PowerApps Plan 2-lisens, fordi den inneholder en enhet med kompleks forretningslogikk. 

## <a name="licensing"></a>Lisensiering
For mer informasjon om PowerApps- og Dynamics 365-lisenser, se [Lisensoversikt](../../administrator/pricing-billing-skus.md).
