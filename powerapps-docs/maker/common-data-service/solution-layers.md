---
title: Vise løsningslag | MicrosoftDocs
description: Lær hvordan du kan bruke løsningslag
keywords: null
ms.date: 04/18/2019
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

<!--note from editor: Best practice is that H1 title and title in metadata are different.    -->

# <a name="view-solution-layers"></a>Vise løsningslag
Løsningslag lar deg vise alle komponentendringer som skjer på grunn av endringer i løsningen over tid. I et løsningslag kan du drille ned for å vise de bestemte endrede og uendrede egenskapsdetaljene til en komponent. 

Løsningslag: 
-   Lar deg se hvilken rekkefølge en løsning endret en komponent i. 
-   Lar deg vise alle egenskaper for en komponent i en bestemt løsning, inkludert endringer i komponenten. 
-   Kan brukes til å feilsøke problemer med avhengighet eller løsningslag ved å vise endringsdetaljer for en komponent som ble introdusert etter en løsningsendring.

## <a name="view-the-solution-layers-for-a-component"></a>Vise løsningslagene for en komponent
Du kan få tilgang til løsningslag fra **Komponenter**-listen eller fra **Avhengighetsdetaljer**-dialogboksen i løsningsutforskeren. 

<!--note from editor: In step 2 below, does the page display a name at top? If so, use the same capitalization in text. -->

1. Hvis du vil vise løsningslag fra **Komponent**-listen, må du åpne [løsningsutforskeren](../model-driven-apps/advanced-navigation.md#solution-explorer). I listen over **Komponenter** velger du en komponent, for eksempel **Forretningsforbindelse**, og deretter **Løsningslag** på verktøylinjen. 

   > [!div class="mx-imgBorder"] 
   > ![Knappen for løsningslag](media/solution-layers-toolbar.png "Knappen for løsningslag")

2. Siden Løsningslag vises. Løsningslagssiden viser hvert lag av komponenten, slik som **Forretningsforbindelse**-enheten som vises her, med det nyeste laget øverst. Hvis du vil vise detaljene for et løsningslag, velger du det. 

   > [!div class="mx-imgBorder"] 
   > ![Løsningslagliste](media/solution-layers-list.png "Løsningslagliste")

3. I **Løsningslag**-dialogboksen viser **Endrede egenskaper**-kategorien bare egenskapene som ble endret som en del av det bestemte løsningslaget. 

   > [!div class="mx-imgBorder"] 
   > ![Endrede egenskaper for løsningslag](media/solution-layers-change-prop.png "Endrede egenskaper for løsningslag")

4. Velg **Alle egenskaper**-kategorien for å vise alle egenskaper, inkludert endrede og uendrede egenskaper, for løsningslaget. 

   > [!div class="mx-imgBorder"] 
   > ![Alle egenskaper for løsningslag](media/solution-layers-all-prop.png "Alle egenskaper for løsningslag")

### <a name="see-also"></a>Se også
[Løsningsoversikt](solutions-overview.md)
