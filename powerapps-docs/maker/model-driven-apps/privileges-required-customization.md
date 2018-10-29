---
title: Rettigheter som kreves for tilpassing av modelldrevne apper | MicrosoftDocs
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
ms.openlocfilehash: dd0c7e05d756145a701bb6bfb137dc07cb8c45fb
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/08/2018
ms.locfileid: "39692147"
---
# <a name="privileges-required-for-model-driven-app-customization"></a>Rettigheter som kreves for tilpassing av modelldrevne apper

App-brukere kan tilpasse systemet, og til og med dele noen av sine tilpassinger med andre, men bare brukere med de riktige rettighetene kan gjøre endringer for alle.  
  
> [!NOTE]
>  Denne delen forutsetter at du vet hvordan du arbeider med sikkerhetsroller. Hvis du vil ha mer informasjon om hvordan du arbeider med sikkerhetsroller, kan du se [Opprett brukere og tilordne sikkerhetsroller](https://docs.microsoft.com/dynamics365/customer-engagement/admin/create-users-assign-online-security-roles).  
  
<a name="BKMK_SysAdminAndSysCustomizer"></a>   
## <a name="system-administrator-and-system-customizer-security-roles"></a>Sikkerhetsroller for systemansvarlig og systemtilpasser  
 Alle som tilpasser har sikkerhetsrollen systemansvarlig eller systemtilpasser, som er forbundet med brukerkontoen. Disse sikkerhetsrollene gir deg tillatelsene du trenger for å tilpasse appen.  
  
|Systemadministrator|Å tilpasse et system|  
|--------------------------|-----------------------|  
|Har full tilgang til å tilpasse systemet|Har full tilgang til å tilpasse systemet|  
|Kan vise alle dataene i systemet|Kan bare vise poster for systemenheter som de oppretter|  
  
 Forskjellen mellom sikkerhetsrollene systemansvarlig og systemtilpasser, er at en systemansvarlig har leserettigheter til de fleste poster i systemet, og kan se alt. Tilordne rollen systemtilpasser til en person som trenger å utføre tilpassingsoppgaver, men som ikke behøver å se noen data i systemenhetene. Testing er imidlertid en viktig del av tilpassing av systemet. Hvis tilpassere ikke kan se noe data, må de opprette poster for å teste tilpassingene. Systemtilpassere har full tilgang til egendefinerte enheter som standard. Hvis du vil ha de samme begrensningene som finnes for systemenheter, må du justere sikkerhetsrollen som systemtilpasser slik at tilgangsnivået for egendefinerte enheter er **Bruker** i stedet for **Organisasjon**.  
  
<a name="BKMK_DelegatingCustomizationTasks"></a>   
## <a name="delegate-customization-tasks"></a>Deleger tilpassingsoppgaver  
 Du vil kanskje delegere noen oppgaver til klarerte personer, slik at de kan bruke endringer de trenger. Vær oppmerksom på at alle kan ha flere sikkerhetsroller som er knyttet til brukerkontoen, og at rettigheter og tilgangsrettigheter gitt av sikkerhetsroller er basert på det *minst restriktive* nivået av tillatelser.  
  
 Dette betyr at du kan gi sikkerhetsrollen systemtilpasser til en som allerede har en annen sikkerhetsrolle, kanskje en salgssjef. Dette lar dem tilpasse systemet, i tillegg til andre rettigheter som de allerede har. Du trenger ikke å redigere sikkerhetsrollen de allerede har, og du kan fjerne sikkerhetsrollen systemtilpasser fra brukerkontoen til personen når du ønsker.  
  
<a name="BKMK_UsingTwoUserAccounts"></a>   
## <a name="test-customizations-without-customization-privileges"></a>Teste tilpassinger uten mulighet til å tilpassingsrettigheter  
 Du bør alltid teste eventuelle tilpassinger du gjør med en brukerkonto som ikke har tilpassingsrettigheter. På denne måten kan du kontrollere at personer uten sikkerhetsrollene systemansvarlig eller systemtilpasser, kan bruke tilpassingene. Hvis du vil gjøre dette effektivt, må du ha tilgang til to brukerkontoer: én konto med sikkerhetsrollen systemansvarlig, og en annen som har sikkerhetsroller som representerer personene som skal bruke tilpassingene.  
  
> [!IMPORTANT]
>  Ikke forsøk å fjerne sikkerhetsrollen systemansvarlig hvis du bare har én brukerkonto. Systemet vil varsle deg hvis du prøver, men hvis du fortsetter kan du oppdage at du ikke kan få den tilbake. De fleste sikkerhetsroller tillater ikke redigering av sikkerhetsroller for en bruker.  
  
## <a name="next-steps"></a>Neste trinn  
 [Kom i gang med tilpassing](getting-started-customization.md)

