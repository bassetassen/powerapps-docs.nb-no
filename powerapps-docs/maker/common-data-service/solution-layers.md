---
title: Vise løsningslag | MicrosoftDocs
description: Lær hvordan du kan bruke løsningslag
keywords: null
ms.date: 04/10/2019
ms.service: powerapps
ms.custom: null
ms.topic: article
applies_to:
  - Dynamics 365 for Customer Engagement (online)
  - Dynamics 365 for Customer Engagement Version 9.x
  - powerapps
ms.assetid: null
author: Mattp123
ms.author: matp
manager: kvivek
ms.reviewer: null
ms.suite: null
ms.tgt_pltfrm: null
caps.latest.revision: null
topic-status: Drafting
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="view-solution-layers"></a>Vise løsningslag
Løsningslag gjør det mulig å vise alle komponentendringer som skjer på grunn av endringer for løsningen over tid. I et løsningslag kan du drille ned for å vise de bestemte endrede og uendrede egenskapsdetaljene for en komponent. 

Løsningslag gir følgende fordeler: 
-   Lar deg se hvilken rekkefølge en løsning endret en komponent i. 
-   Lar deg vise alle egenskaper for en komponent i en bestemt løsning, inkludert endringer for komponenten. 
-   Kan brukes til å feilsøke problemer med avhengighet eller løsningslag ved å vise endringsdetaljer for en komponent som ble introdusert av en løsningsendring.

## <a name="view-the-solution-layers-for-a-component"></a>Vise løsningslagene for en komponent
Du kan få tilgang til løsningslag fra **Komponenter**-listen eller fra **Avhengighetsdetaljer**-dialogboksen i løsningsutforskeren. 

1. Hvis du vil vise løsningslag fra **Komponenter**-listen, [åpner du løsningsutforskeren](../model-driven-apps/advanced-navigation.md#solution-explorer) og velger en komponent i **Komponenter**-listen, for eksempel **Forretningsforbindelse**, og deretter velger du **Løsningslag**på verktøylinjen. 

   > [!div class="mx-imgBorder"] 
   > ![](media/solution-layers-toolbar.png "Løsningslag-knappen")

2. Løsningslag-siden vises med en oversikt over hvert lag for komponenten. Forretningsforbindelse-enheten vises for eksempel her med det siste laget øverst. Hvis du vil vise detaljene for et løsningslag, velger du det. 

   > [!div class="mx-imgBorder"] 
   > ![](media/solution-layers-list.png "Løsningslag-liste")

3. I **Løsningslag**-dialogboksen viser **Endrede egenskaper**-kategorien bare egenskapene som ble endret som en del av det bestemte løsningslaget. 

   > [!div class="mx-imgBorder"] 
   > ![](media/solution-layers-change-prop.png "Løsningslag, endrede egenskaper")

4. Velg **Alle egenskaper**-kategorien for å vise alle egenskaper, inkludert endrede og uendrede egenskaper, for løsningslaget. 

   > [!div class="mx-imgBorder"] 
   > ![](media/solution-layers-all-prop.png "Løsningslag, alle egenskaper")

## <a name="see-also"></a>Se også
[Løsningsoversikt](solutions-overview.md)