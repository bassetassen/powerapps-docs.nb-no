---
title: Legge til teamenheten som et oppslagsalternativ i appen | MicrosoftDocs
description: Lær hvordan du legger til teamenheten som et oppslagsalternativ i appen
ms.custom: ''
ms.date: 07/24/2019
ms.reviewer: ''
ms.service: powerapps
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
author: Mattp123
ms.assetid: null
caps.latest.revision: 25
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="add-the-team-entity-as-a-lookup-option-in-your-app"></a>Legge til teamenheten som et oppslagsalternativ i appen

Med Enhetlig grensesnitt-apper må teamenheten legges til i appen for å være tilgjengelig i et oppslag. Kontaktoppføringer har for eksempel muligheten til å være tilordnet til en bruker eller et team.  

> [!div class="mx-imgBorder"] 
> ![](media/entity-lookup-teams.png "Enhetsoppslag med både brukere og team tilgjengelig")

Men hvis brukerenheten er inkludert i appen, men teamenheten ikke er det, vises bare brukeroppføringer i et oppslag. 

> [!div class="mx-imgBorder"] 
> ![](media/entity-lookup-user-only.png "Enhetsoppslag bare med brukere")

## <a name="add-the-team-entity-to-an-app"></a>Legge til teamenheten i en app

1. Åpne appen i Apputforming. 
2. Velg kategorien **Komponenter**, velg **Enheter**, og velg deretter **Team**.    

    > [!div class="mx-imgBorder"] 
    > ![](media/add-team-entity-app.png "Legg til teamenheten i appen")

3. Velg **Lagre**, og velg deretter **Publiser** for å gjøre endringen tilgjengelig for appbrukere.   

