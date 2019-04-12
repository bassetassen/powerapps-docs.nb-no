---
title: Tilordne modelldrevet appskjemarekkefølge i PowerApps | MicrosoftDocs
description: Lær hvordan du tilordner standardskjemaet i appen
ms.custom: ''
ms.date: 03/07/2019
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
ms.assetid: 914c5694-9c80-4424-be89-9f63256b4811
caps.latest.revision: 33
ms.author: matp
manager: kvivek
tags: null
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="assign-model-driven-app-form-order"></a>Tilordne modelldrevet appskjemarekkefølge

 Når du har flere hovedskjemaer, hurtigopprettingsskjemaer, hurtigvisningsskjemaer eller kortskjemaer for en enhet, kan du tilordne en skjemarekkefølge. Skjemarekkefølgen bestemmer hvilket av de tilgjengelige skjemaene som skal vises som standard. De tilgjengelige hovedskjemaene kan styres ytterligere ved å tilordne sikkerhetsroller til skjemaet. Se [Styre tilgang til skjemaer](control-access-forms.md) for mer informasjon.  
  
 Du kan ikke tilordne sikkerhetsroller til hurtigopprettingsskjemaer, hurtigvisningsskjemaer eller kortskjemaer, så det eneste skjemaet som brukes av alle, er det som er øverst i skjemarekkefølgen.  
  
## <a name="to-assign-a-form-order"></a>Slik tilordner du en skjemarekkefølge  
  
1.  Åpne [løsningsutforskeren](advanced-navigation.md#solution-explorer), utvid enheten du vil ha, og velg deretter **Skjemaer**.  
  
2.  Velg **Skjemarekkefølge** på verktøylinjen for skjemalisten.  

     > [!div class="mx-imgBorder"] 
     > ![Verktøylinjekommando for skjemarekkefølge](media/form-order.png)
  
3.  Velg **Hovedskjemasett**, **Angi hurtigoppretting av skjema**, **Sett med hurtigvisningsskjemaer** eller **Kortskjemasett** avhengig av skjematypen du vil arbeide med. Mer informasjon: [Skjematyper](types-forms.md). 
  
4.  Dialogboksen **Skjemarekkefølge** er en enkel liste der du kan flytte et merket skjema opp eller ned i skjemarekkefølgen.  
  
5.  Når du har angitt ønsket rekkefølge, klikker du **OK** for å lukke dialogboksen.  

## <a name="next-steps"></a>Neste trinn

[Endre navigasjon i et skjema](use-the-form-editor-legacy.md)
