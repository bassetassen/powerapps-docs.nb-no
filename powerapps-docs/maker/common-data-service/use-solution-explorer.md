---
title: Bruke løsningsutforskeren i PowerApps | MicrosoftDocs
description: Finn ut hvordan du bruker løsningsutforskeren til å opprette eller tilpasse apper
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
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="use-the-solution-explorer"></a>Bruke løsningsutforskeren

 I løsningsutforskeren kan du navigere gjennom et hierarki av noder ved hjelp av navigasjonsruten på venstre side, som vist i følgende skjermbilde:  
  
 ![Standardløsning med enheter skjult](media/crm-itpro-cust-defaultsolutionentitiescollapsed.PNG "Standardløsning med enheter skjult")  
  
> [!NOTE]
>  Bruk musen og tastaturet når du arbeider med tilpassingsverktøy i løsningsutforskeren. Denne delen av programmet er ikke optimalisert for berøring.  
  
 Når du velger hver node, kan du se en liste over løsningskomponentene. Handlingene som er tilgjengelige i kommandolinjen, endres avhengig av konteksten til noden du har valgt, og hvorvidt løsningen er standardløsningen eller en administrert løsning. Med uadministrerte løsninger som ikke er standardløsningen, kan du bruke kommandoen **Legg til eksisterende** for å hente løsningskomponenter som ikke allerede finnes i løsningen.  
  
Med administrerte løsninger blir ingen kommandoer tilgjengelige, og du vil se meldingen:  

> [!NOTE]
> Du kan ikke redigere komponentene i en administrert løsning direkte. Hvis det er definert at de forvaltede egenskapene for løsningskomponenter tillater tilpassing, kan du redigere dem med et PowerApps-designverktøy eller fra en annen uadministrert løsning.    
  
 Du må finne løsningskomponenten i standardløsningen og prøve å redigere den der eller legge den til i en annen uadministrert løsning som du har opprettet. Løsningskomponenten kan kanskje ikke tilpasses. Mer informasjon: [Forvaltede egenskaper](solutions-overview.md#managed-properties)
  
 Mange av tilpassingene du vil gjøre, omfatter enheter. Du kan utvide **Enheter**-noden for å vise en liste over alle enheter i systemet som kan tilpasses på et eller annet vis. Videre kan du utvide hver enhet for å vise løsningskomponentene som er en del av enheten, som vist med enheten for forretningsforbindelsen i følgende skjermbilde:  
  
 ![Standardløsning som viser utvidet enhet for forretningsforbindelse](media/crm-itpro-cust-defaultsolution.PNG "Standardløsning som viser utvidet enhet for forretningsforbindelse")  
  
 For mer informasjon om tilpassing av individuelle løsningskomponenter som finnes i løsningsutforskeren, kan du se følgende emner:  
  
-   For tilpassinger av enheter, enhetsrelasjoner, felt og meldinger, se [Metadata](create-edit-metadata.md).  
  
-   For enhetsskjemaer se [Skjemaer](../model-driven-apps/create-design-forms.md).  
  
-   For prosesser kan du se [Prosesser](../model-driven-apps/guide-staff-through-common-tasks-processes.md).  
  
-   For forretningsregler kan du se [Forretningsregler](../model-driven-apps/create-business-rules-recommendations-apply-logic-form.md).  
