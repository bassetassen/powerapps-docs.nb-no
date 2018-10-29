---
title: Forvaltede egenskaper for modelldrevne apper for visninger med PowerApps | MicrosoftDocs
description: Lær å angi forvaltede egenskaper for en visning
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
ms.openlocfilehash: 9f33212ae81de0418dfc3695d5ae3c8e5acf36da
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/08/2018
ms.locfileid: "39693376"
---
# <a name="model-driven-app-managed-properties-for-views"></a>Forvaltede egenskaper for modelldrevne apper for visninger

<a name="BKMK_ManagedProperties"></a>   
 
 Hvis du oppretter en egendefinert offentlig visning i PowerApps som du vil inkludere i en administrert løsning som skal distribueres, kan du begrense muligheten til å tilpasse visningen, for alle som installerer løsningen din.  
  
 De fleste visninger har som standard den forvaltede egenskapen **Kan tilpasses** satt til sann, slik at den kan tilpasses. Hvis du ikke har en svært god grunn til å endre dette, anbefales det at du gir folk lov til å tilpasse visninger i appen.  
  
## <a name="set-managed-properties-for-a-view"></a>Angi forvaltede egenskaper for en visning  
  
1.  Åpne [Løsningsutforsker](advanced-navigation.md#solution-explorer), utvid **Enheter**, velg enheten du vil bruke, og velg deretter **Visninger**.  
  
2.  Velg en egendefinert offentlig visning.  
  
3.  Velg **Flere handlinger** > **Forvaltede egenskaper** på menylinjen.  

    ![Meny for forvaltede egenskaper](media/managed-properties.png)
  
4.  Angi alternativene **Kan tilpasses** eller **Kan slettes** til **Sann** eller **Usann**.  

    ![Angi forvaltede egenskaper](media/set-managed-properties.png)
  
> [!NOTE]
> Innstillingen trer ikke i kraft før du eksporterer en løsning som inneholder visningen som en administrert løsning og installer den i et annet miljø.  

## <a name="next-steps"></a>Neste trinn
[Forstå visninger](create-edit-views.md)
