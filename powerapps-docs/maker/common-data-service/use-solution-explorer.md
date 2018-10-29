---
title: Bruk løsningsutforsker i PowerApps | MicrosoftDocs
description: Lær hvordan du bruker løsningsutforsker til å opprette eller tilpasse apper
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
- powerapps
author: Mattp123
ms.assetid: 72bacfbb-96a3-4daa-88ff-11bdaaac9a3d
caps.latest.revision: 57
ms.author: matp
manager: kvivek
ms.openlocfilehash: 6abbe701a6207e68ac367fbe80495a7d04a6e682
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/08/2018
ms.locfileid: "39691651"
---
# <a name="use-the-solution-explorer"></a>Bruk løsningsutforskeren

 I løsningsutforskeren kan du navigere gjennom et hierarki av noder ved hjelp av navigasjonsruten på venstre side av verktøyet, som vist i følgende skjermbilde:  
  
 ![Standardløsning med skjulte enheter](media/crm-itpro-cust-defaultsolutionentitiescollapsed.PNG "Standardløsning med skjulte enheter")  
  
> [!NOTE]
>  Bruk musen og tastaturet når du arbeider med tilpassingsverktøy i løsningsutforskeren. Denne delen av programmet er ikke optimalisert for berøring.  
  
 Når du velger hver node, kan du se en liste over løsningskomponentene. Handlingene som er tilgjengelige i kommandolinjen blir endret avhengig av konteksten til noden du har valgt, og om løsningen er standardløsningen eller en administrert løsning. Med uadministrerte løsninger som ikke er standardløsningen, kan du bruke kommandoen **Legg til eksisterende** for å hente inn løsningskomponentene som ikke allerede finnes i løsningen.  
  
Med administrerte løsninger er det ingen tilgjengelige kommandoer, og du ser meldingen:  

> [!NOTE]
> Du kan ikke redigere komponentene i en administrert løsning direkte. Hvis de forvaltede egenskapene for løsningskomponentene er satt til å tillate tilpassing, kan du redigere dem ved hjelp av et utformingsverktøy for PowerApps eller fra en annen uadministrert løsning.    
  
 Du må finne løsningskomponenten i standardløsningen, og prøve å redigere det der eller legge det til en annen uadministrert løsning som du har opprettet. Løsningskomponenten kan kanskje ikke tilpasses. Mer informasjon: [Forvaltede egenskaper](solutions-overview.md#managed-properties)
  
 Mange av tilpassingene du vil gjøre, vil omfatte enheter. Du kan utvide **Enheter**-noden for å vise en liste over alle enheter i systemet som kan tilpasses på en eller annen måte. Du kan videre utvide hver enhet for å se løsningskomponentene som er en del av enheten, som vist med kontoenheten i følgende skjermbilde:  
  
 ![Standardløsning som viser utvidet kontoenheten](media/crm-itpro-cust-defaultsolution.PNG "Standardløsning som viser utvidet kontoenheten")  
  
 Hvis du vil ha mer informasjon om hvordan du tilpasser de individuelle løsningskomponentene funnet i løsningsutforskeren, kan du se følgende emner:  
  
-   Hvis du vil ha mer informasjon om tilpassinger av enhet, enhetsrelasjoner, felt og melding, kan du se [Metadata](create-edit-metadata.md).  
  
-   Hvis du vil ha mer informasjon om enhetsskjemaer, kan du se [Skjemaer](../model-driven-apps/create-design-forms.md).  
  
-   Hvis du vil ha mer informasjon om prosesser, kan du se [Prosesser](../model-driven-apps/guide-staff-through-common-tasks-processes.md).  
  
-   Hvis du vil ha mer informasjon om forretningsregler, kan du se [Forretningsregler](../model-driven-apps/create-business-rules-recommendations-apply-logic-form.md).  
