---
title: Lisenskrav for enheter | Microsoft Docs
description: En forklaring på lisenskrav for enheter i Common Data Service (CDS) for Apps.
author: clwesene
manager: kfile
ms.service: powerapps
ms.component: cds
ms.topic: conceptual
ms.date: 05/01/2018
ms.author: clwesene
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="license-requirements-for-entities"></a>Lisenskrav for enheter
Apputviklere kan bruke de fleste enheter som er tilgjengelige i Common Data Service (CDS) for Apps (inkludert egendefinerte enheter og enheter som er en del av Common Data Model), for å opprette apper og flyter for brukere som har en PowerApps Plan 1- eller Microsoft Flow Plan 1-lisens. I noen tilfeller inneholder enheter kompleks forretningslogikk eller er knyttet til Dynamics 365-programmer som krever at appbrukerne har en bestemt lisens. 


|Enhet    |Beskrivelse    |Krav    |
|---------|---------|---------|
|Enheter med kompleks forretningslogikk   | Dette er enheter som bruker kompleks forretningslogikk for serverside. For eksempel en enhet som bruker en arbeidsflyt i sanntid eller kodeplugin-modul.       |  [PowerApps Plan 2](https://powerapps.microsoft.com/pricing/) eller [Flow Plan 2](https://flow.microsoft.com/pricing/)        |
|Begrensede enheter  |  Dette er enheter som ikke er standard med Common Data Service for Apps, men er inkludert i et Dynamics 365 customer engagement-program eller tredjepartsløsning. For eksempel kunnskapsartikkel-, mål- og rettighetsenhetene.     |  [En Dynamics 365-plan](https://dynamics.microsoft.com/pricing/)      | 


> [!NOTE]
> Apper og flyter som bruker disse enhetene, krever at app- og flytbrukeren er riktig lisensiert - ikke produsenten eller utvikleren av appen eller flyten.

## <a name="entities-with-complex-business-logic"></a>Enheter med kompleks forretningslogikk
Enheter som inneholder følgende komplekse serversidelogikk, krever at brukere av en app eller flyt som bruker disse enhetene, har en PowerApps Plan 2- eller Microsoft Flow Plan 2-lisens:

* Plugin-moduler med kode (for mer informasjon se [Utvikling av plugin-moduler](https://docs.microsoft.com/dynamics365/customer-engagement/developer/plugin-development))
* Sanntidsarbeidsflyter (for mer informasjon se [Arbeidsflytprosesser](https://docs.microsoft.com/dynamics365/customer-engagement/customize/workflow-processes)).

    > [!NOTE]
    >  Bare arbeidsflyter som er konvertert til en sanntidsarbeidsflyt, vurderes som i sanntid og synkroniserte. Arbeidsflyter som kjører i bakgrunnen, kan fremdeles brukes med riktig PowerApps-plan og krever ikke flere lisenser.

Hvis du vil vite om du har lagt til kompleks forretningslogikk i enhetene, kan du se listen over plugin-modulsamlinger og arbeidsflyter som er konfigurert i miljøet. Hvis du vil se listen over enheter som kan inneholde serversidelogikk etter installasjon av et Dynamics 365-program, kan du se [Komplekse enheter som krever PowerApps Plan 2-lisenser](data-platform-complex-entities.md)  

### <a name="impacting-license-requirements-when-adding-complex-business-logic"></a>Påvirker lisenskrav når kompleks forretningslogikk legges til
Apputviklere kan legge til plugin-moduler med kode og sanntidsarbeidsflyter i enheter i CDS for Apps, men dette kan endre lisenskravene for brukere av apper som allerede er distribuert. Apputviklere bør være forsiktige når de legger til kompleks forretningslogikk i en enhet, og bør først sjekke hvilke apper som bruker enheten, og om brukerne av disse appene har riktige lisenser.

## <a name="restricted-entities"></a>Begrensede enheter
Enkelte enheter som er knyttet til funksjonaliteten i Dynamics 365-programmer, krever at appbrukere har tilsvarende lisens for dette programmet hvis de ønsker å opprette, oppdatere eller slette oppføringer i enhetene. En fullstendig liste over begrensede enheter finnes i [Begrensede enheter krever Dynamics 365-lisenser](data-platform-restricted-entities.md).

## <a name="licensing-examples"></a>Lisensieringseksempler
Barb og Isaac oppretter apper i PowerApps ved hjelp av CDS for Apps for å lagre dataene.

Barb oppretter to lerretsapper:

* App 1 &ndash; bruker Avtale-enheten sammen med en egendefinert enhet som lagrer relatert informasjon
* App 2 &ndash; bruker Avtale-enheten sammen med Hendelse-enheten, som er en begrenset enhet

Isaac oppretter to modelldrevne apper:

* App 3 &ndash; bruker Avtale-enheten sammen med en egendefinert enhet som lagrer relatert informasjon
* App 4 &ndash; bruker Avtale-enheten sammen med Hendelse-enheten, som er en begrenset enhet

Barb og Isaac trenger følgende lisenser:
* Barb trenger en PowerApps Plan 1-lisens for å opprette lerretsapper ved hjelp av CDS for Apps. Hvis hun må opprette en database eller opprette en egendefinert enhet, må hun ha en PowerApps Plan 2-lisens.

* Isaac trenger en PowerApps Plan 2-lisens for å bygge modelldrevne apper.

Appbrukere må ha følgende lisenser:
* App 1-brukere trenger bare en PowerApps Plan 1- eller Plan 2-lisens siden appen ikke inneholder enheter med kompleks forretningslogikk eller begrensede enheter.

* App 2-brukere må ha en Dynamics 365 for Customer Service, Enterprise edition-lisens (eller en Dynamics 365 eller Dynamics 365 Customer Engagement-Plan), siden appen inkluderer en begrenset enhet.

* App 3-brukere må ha en PowerApps Plan 2-lisens fordi det er en modelldrevet app.

* App 4-brukere må ha en Dynamics 365 for Customer Service, Enterprise edition-lisens (eller en Dynamics 365 eller Dynamics 365 Customer Engagement-Plan), siden appen inkluderer en begrenset enhet.

    Dynamics 365 for Customer Service-planen inkluderer en PowerApps Plan 2-lisens, som lar brukere kjøre modelldrevne apper.

Nå skal vi se hva som skjer når Isaac legger til en sanntidsarbeidsflyt i den egendefinerte enheten som både Barb og Isaac bruker i appene sine.

Barb og Isaac trenger følgende lisenser:
* Barb trenger fortsatt en PowerApps Plan 1-lisens for å opprette lerretsapper ved hjelp av CDS for Apps.

* Isaac trenger fortsatt en PowerApps Plan 2-lisens for å bygge modelldrevne apper.

Appbrukere må ha følgende lisenser:
* App 1-brukere trenger nå en PowerApps Plan 2-lisens, siden appen inneholder en enhet med en sanntidsarbeidsflyt.

* App 2-brukere må fortsatt ha en Dynamics 365 for Customer Service, Enterprise edition-lisens (eller en Dynamics 365 eller Dynamics 365 Customer Engagement-Plan), siden appen inkluderer en begrenset enhet. 

* App 3-brukere må fortsatt ha en PowerApps Plan 2-lisens fordi det er en modelldrevet app.

* App 4-brukere må fortsatt ha en Dynamics 365 for Customer Service, Enterprise edition-lisens (eller en Dynamics 365- eller Dynamics 365 Customer Engagement-plan), siden appen inkluderer en begrenset enhet.

    Dynamics 365 for Customer Service-planen inkluderer en PowerApps Plan 2-lisens, som lar brukere kjøre modelldrevne apper.

Den eneste appen som påvirkes av denne endringen, er App 1, som tidligere krevde en PowerApps Plan 1-lisens, men nå krever en PowerApps Plan 2-lisens, siden den inneholder en enhet med kompleks forretningslogikk. 

## <a name="more-about-licensing"></a>Mer om lisensiering
Hvis du vil ha mer informasjon om PowerApps- og Dynamics 365-lisenser, kan du se [Lisensieringsoversikt](../../administrator/pricing-billing-skus.md).
