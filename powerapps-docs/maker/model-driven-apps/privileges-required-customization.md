---
title: Rettigheter som kreves for å tilpasse modelldrevne apper | MicrosoftDocs
ms.custom: ''
ms.date: 06/18/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - PowerApps
ms.assetid: 43cf7f3a-7e26-4990-8b5a-c817ac6d51bb
caps.latest.revision: 13
ms.author: matp
manager: kvivek
author: Mattp123
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="privileges-required-for-model-driven-app-customization"></a>Rettigheter som kreves for å tilpasse modelldrevne apper

Applikasjonsbrukere kan tilpasse systemet og til og med dele noen av sine tilpassinger med andre, men bare brukere med riktige rettigheter kan bruke endringer for alle.  
  
> [!NOTE]
>  Denne delen forutsetter at du vet hvordan du arbeider med sikkerhetsroller. Hvis du vil ha mer informasjon om hvordan du arbeider med sikkerhetsroller, kan du se [Opprette brukere og tilordne sikkerhetsroller](https://docs.microsoft.com/dynamics365/customer-engagement/admin/create-users-assign-online-security-roles).  
  
<a name="BKMK_SysAdminAndSysCustomizer"></a>   
## <a name="system-administrator-and-system-customizer-security-roles"></a>Sikkerhetsrollene Systemansvarlig og Systemtilpasser  
 Alle som tilpasser, har sikkerhetsrollen Systemansvarlig eller Systemtilpasser knyttet til deres konto. Disse sikkerhetsrollene gir deg tillatelsene du trenger til å tilpasse applikasjonen.  
  
|Systemansvarlig|Systemtilpasser|  
|--------------------------|-----------------------|  
|Har alle tillatelser til å tilpasse systemet|Har alle tillatelser til å tilpasse systemet|  
|Kan vise alle data i systemet|Kan bare vise oppføringer for systemenheter de oppretter|  
  
 Forskjellen mellom sikkerhetsrollene Systemansvarlig og Systemtilpasser er at en systemansvarlig har leserettigheter for de fleste oppføringer i systemet og kan se alt. Tilordne rollen Systemtilpasser til noen som må utføre tilpassingsoppgaver, men som ikke skal se data i systemenhetene. Testing er imidlertid en viktig del av å tilpasse systemet. Hvis Systemtilpassere ikke kan se data, må de opprette oppføringer for å teste tilpassingene sine. Systemtilpassere har som standard full tilgang til egendefinerte enheter. Hvis du vil ha de samme begrensningene som finnes for systemenheter, må du justere sikkerhetsrollen Systemtilpasser slik at tilgangsnivået er **Bruker** i stedet for **Organisasjon** for egendefinerte enheter.  
  
<a name="BKMK_DelegatingCustomizationTasks"></a>   
## <a name="delegate-customization-tasks"></a>Delegere tilpassingsoppgaver  
 Du vil kanskje delegere noen oppgaver til klarerte personer, slik at de kan bruke endringer de trenger. Husk at alle kan ha flere sikkerhetsroller knyttet til brukerkontoen sin, og at rettigheter og tilgangsrettigheter som gis av sikkerhetsroller, er basert på det *minst restriktive* tillatelsesnivået.  
  
 Dette betyr at du kan gi sikkerhetsrollen Systemtilpasser til noen som allerede har en annen sikkerhetsrolle, kanskje en salgssjef. Dette gjør det mulig for dem å tilpasse systemet i tillegg til andre rettigheter som de allerede har. Du trenger ikke å redigere sikkerhetsrollen de allerede har, og du kan når som helst fjerne sikkerhetsrollen Systemtilpasser fra personens brukerkonto.  
  
<a name="BKMK_UsingTwoUserAccounts"></a>   
## <a name="test-customizations-without-customization-privileges"></a>Teste tilpassinger uten tilpassingsrettigheter  
 Du bør alltid teste alle tilpassinger du gjør, med en brukerkonto som ikke har tilpassingsrettigheter. Dermed kan du kontrollere at personer uten sikkerhetsrollene Systemansvarlig eller Systemtilpasser, kan bruke tilpassingene. For å kunne gjøre dette effektivt må du ha tilgang til to brukerkontoer: én konto med sikkerhetsrollen Systemansvarlig og én annen som har sikkerhetsrollene som representerer personene som skal bruke tilpassingene.  
  
> [!IMPORTANT]
>  Ikke prøv å fjerne sikkerhetsrollen Systemansvarlig hvis du bare har én brukerkonto. Systemet advarer deg hvis du gjør et forsøk, men hvis du går videre, kan det hende at du ikke kan få den tilbake. De fleste sikkerhetsrollene tillater ikke redigering av en sikkerhetsrollene til en bruker.  
  
## <a name="next-steps"></a>Neste trinn  
[Forstå modelldrevede appkomponenter](model-driven-app-components.md)

