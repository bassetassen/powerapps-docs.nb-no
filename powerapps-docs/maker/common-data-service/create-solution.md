---
title: Opprett en løsning | MicrosoftDocs
description: Lær hvordan du oppretter en løsning
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
author: Mattp123
ms.assetid: e21a4876-08b4-417a-a644-c577a27c5cf1
caps.latest.revision: 12
ms.author: matp
manager: kvivek
ms.openlocfilehash: 26ecc9b2f83375ba10e6b32dfc12d6cc37342cf4
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/08/2018
ms.locfileid: "39697266"
---
# <a name="create-a-solution"></a>Opprett en løsning

Da standardløsningen inneholder alle løsningskomponentene, kan det være enklere å bare finne de løsningskomponentene som du har tilpasset hvis du oppretter en separat løsning, og gjør alle tilpassingene dine der. Dette gjør det også enklere å eksportere en sikkerhetskopi av løsningen som en mindre fil. Hvis du velger å gjøre dette, må du alltid huske å legge til de løsningskomponentene du redigerer i denne løsningen. Når du oppretter nye løsningskomponenter, må du alltid opprette dem i konteksten av denne løsningen. På denne måten tas tilpassingsprefikset til løsningsutgiveren i bruk konsekvent. Etter at du har opprettet løsningskomponenter i løsningen din, eller lagt til eksisterende løsningskomponenter i den løsningen, kan du også redigere dem i standardløsningen.  
  
 Hvis du vil ha mer informasjon om løsningskonseptene, kan du se [Arbeid med løsninger](solutions-overview.md).  
  
1.  Gå til **[Innstillinger](../model-driven-apps/advanced-navigation.md#settings)** > **Løsninger**. 
  
2.  Velg **Ny** og fullfør de obligatoriske feltene for løsningen.  
  
    |Felt|Beskrivelse|  
    |-----------|-----------------|  
    |**Visningsnavn**|Navnet som vises i listen over løsninger. Du kan endre dette senere.|  
    |**Navn**|Det unike navnet til denne løsningen. Dette genereres ved bruk av verdien du angir i Visningsnavn-feltet. Du kan redigere dette før du lagrer løsningen, men etter at du lagrer løsningen, kan dette ikke endres.|  
    |**Utgiver**|Du kan velge standardutgiveren eller opprette en ny utgiver. Med mindre du planlegger å distribuere løsningen, bruker du bare standardutgiveren for organisasjonen.|  
    |**Versjon**|Oppgi et tall for versjonen av løsningen. Dette er bare viktig hvis du eksporterer løsningen. Versjonsnummeret blir inkludert i filnavnet når du eksporterer løsningen.|  
  
3.  Velg **Lagre**.  
  
 Etter at du lagrer løsningen, kan du legge til informasjon i felter som ikke er obligatorisk. Disse trinnene er valgfrie. Bruk **Beskrivelse**-feltet for å beskrive løsningen, og velg en HTML-nettressurs som en **konfigurasjonsside** for løsningen. Konfigurasjonssiden brukes som regel av ISV-er som distribuerer løsninger. Når dette er angitt, vises en ny **Konfigurasjonsnode** nedenfor **Informasjonsnode** for å vise nettressursen. Utviklere kan bruke denne siden til å inkludere instruksjoner eller kontroller. De kan angi konfigurasjonsdata eller lansere løsningen.  
  
<a name="BKMK_AddSolutionComponents"></a>   

## <a name="add-solution-components"></a>Legg til løsningskomponenter  
 Etter at du har opprettet løsningen, inneholder den ikke noen løsningskomponenter. Du kan opprette nye løsningskomponenter, eller du kan bruke knappen **Legg til eksisterende** i listemenyen for å legge til løsningskomponenter fra standardløsningen.  
  
 Når du gjør dette, kan det hende du ser dialogboksen **Mangler nødvendige komponenter**.  
   
 ![Dialogboksen Legg til nødvendige komponenter](media/crm-itpro-cust-addrequiredcomponents.PNG "Dialogboksen Legg til nødvendige komponenter")  
  
 Denne dialogboksen varsler deg om at løsningskomponentene har avhengigheter på andre løsningskomponenter. Hvis du velger **Nei, ikke inkluder nødvendige komponenter**, kan det hende løsningen mislykkes hvis du importerer den inn i en annen organisasjon, hvor alle de nødvendige komponentene mangler. Hvis løsningen ble importert, kan det hende at virkemåten i den andre løsningen ikke er identisk som den opprinnelige organisasjonen. Det er fordi komponentene er konfigurert på en annen måte enn de i kildeløsningen.  
  
 Det er som regel tryggere å inkludere de nødvendige komponentene hvis du ønsker å eksportere løsningen i en annen organisasjon. Hvis du ikke legger til disse komponentene når du legger til en individuell løsningskomponent, kan du komme tilbake senere, velge løsningskomponenten du la til, og velge **Legg til nødvendige komponenter** fra menyen.  
  
 Hvis du ikke har tenkt å eksportere løsningen, eller hvis du tenker å eksportere den som en uadministrert løsning og importere den tilbake til den samme organisasjonen, er det ikke nødvendig å inkludere nødvendige komponenter. Hvis du eksporterer løsningen, ser du en advarsel som indikerer at noen nødvendige komponenter mangler. Hvis du bare skal importere løsningen tilbake til den samme organisasjonen, kan du bare se bort fra denne advarselen. Fremgangsmåten for å redigere programnavigasjon eller båndet uten å bruke et tredjeparts redigeringsverktøy, blir at du eksporterer løsningen tilbake til den samme organisasjonen.  

> [!IMPORTANT]
>  Hvis du planlegger å inkludere avtaler i løsninger, anbefaler vi på det sterkeste at du ikke inkluderer bare avtaler og bare regelmessige avtaler i separate løsninger. Hvis du installerer og avinstallerer separate løsninger med ulike avtaletyper, får du en SQL Server-feil, og du må opprette avtalene på nytt. 
