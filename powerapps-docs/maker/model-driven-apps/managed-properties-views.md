---
title: Forvaltede egenskaper for visninger i modelldrevne apper med PowerApps | MicrosoftDocs
description: Finn ut hvordan du angir forvaltede egenskaper for en visning
ms.custom: ''
ms.date: 06/12/2018
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
ms.assetid: a9014576-8fb2-4f28-b8bb-5d2d49d76e12
caps.latest.revision: 25
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="model-driven-app-managed-properties-for-views"></a>Forvaltede egenskaper for visninger i modelldrevne apper

<a name="BKMK_ManagedProperties"></a>   
 
 Hvis du oppretter en egendefinert fellesvisning i PowerApps du vil ta med i en administrert løsning du skal distribuere, kan du begrense tilpassing av visningen for alle som installerer løsningen.  
  
 Sann er som standard angitt for den forvaltede egenskapen **Kan tilpasses** for de fleste visninger, slik at brukerne kan tilpasse visningene. Hvis du ikke har en svært god grunn til å endre dette, anbefaler vi at du tillater brukerne å tilpasse visninger i appen.  
  
## <a name="set-managed-properties-for-a-view"></a>Angi forvaltede egenskaper for en visning  
  
1.  Åpne [løsningsutforskeren](advanced-navigation.md#solution-explorer), utvid **Enheter**, velg enheten du vil bruke, og velg deretter **Visninger**.  
  
2.  Velg en egendefinert fellesvisning.  
  
3.  Velg **Flere handlinger** > **Forvaltede egenskaper** på menylinjen.  

    > [!div class="mx-imgBorder"] 
    > ![Meny for forvaltede egenskaper](media/managed-properties.png)
  
4.  Sett **Kan tilpasses** eller **Kan slettes** til **Sann** eller **Usann**.  

    > [!div class="mx-imgBorder"] 
    > ![Angi forvaltede egenskaper](media/set-managed-properties.png)
  
> [!NOTE]
> Innstillingen trer ikke i kraft før du eksporterer en løsning som inneholder visningen som en administrert løsning, og installerer den i et annet miljø.  

## <a name="next-steps"></a>Neste trinn
[Forstå visninger](create-edit-views.md)
