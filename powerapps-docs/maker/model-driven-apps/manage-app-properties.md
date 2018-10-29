---
title: Behandle egenskaper for modelldrevet app i apputforming i PowerApps | MicrosoftDocs
description: Lær hvordan du kan behandle egenskapene for appen din
keywords: ''
ms.date: 06/27/2018
ms.service: crm-online
ms.custom: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
author: Mattp123
ms.assetid: e773e60f-0211-4c4b-a1af-663be4997629
ms.author: matp
manager: kvivek
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
caps.latest.revision: 14
topic-status: Drafting
ms.openlocfilehash: 62129690a0f5969b6f0f749e110eca001f2c0c8b
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/08/2018
ms.locfileid: "39693299"
---
# <a name="manage-model-driven-app-properties-in-the-app-designer"></a>Behandle egenskaper for modelldrevet app i apputforming

Appegenskapene definerer viktige opplysninger om appen, som for eksempel tittelen eller nettadressen. Du definere appegenskaper når du oppretter en app. Hvis du vil endre disse innstillingene senere, kan du gjøre det i apputforming.  
  
1.  Velg **Egenskaper**-fanen til høyre i apputforming.  
  
    ![Egenskaper-ruten i apputforming](media/app-designer-properties-tab.png "Egenskaper-ruten i apputforming")  
  
2.  Endre informasjonen etter behov:  

    |Egenskap|Beskrivelse|  
    |--------------|-----------------|
    |**Navn**|Angi et unikt og meningsfullt navn for appen.|  
    |**Beskrivelse**|Skriv inn en kort beskrivelse av hva appen er.|  
    |**Ikon**|Som standard er det merket av for **Bruk standardapp**. Hvis du vil velge en annen nettressurs som et ikon for appen, fjerner du avmerkingen, og velger deretter et ikon fra rullegardinlisten. Dette ikonet vises på appens forhåndsvisningsflis.|
    |**Unikt navn**| Du kan ikke endre det unike navnet. Ved hjelp av det unike navnet, kan du spørre tabellene for å hente data fra databasen.| 
    |**Klient**|Definerer typen klient som appen skal brukes for.<br/>-  **Nett:** dette er den klassiske nettleserklienten for Dynamics 365 Customer Engagement.<br/>-  **Enhetlig grensesnitt:** dette er den nye nettleserklienten som har et lignende grensesnitt på PC og mobile enheter.|
    |**Appnettadressens suffiks**| Nettadressen du valgte under oppretting av appen, vises her som standard. Du kan endre appnettadressen i dialogboksen **Administrer app**. Vær oppmerksom på at du foreløpig ikke kan eksportere eller importere appnettadressens suffiks via en løsning.|
    |**Velg en velkomstside for appen**|Dette alternativet lar deg velge fra nettressursene som er tilgjengelige i ditt miljø. Velkommen-sidene du oppretter, kan inneholde nyttig informasjon for brukere, for eksempel koblinger til videoer, instruksjoner for oppgradering eller informasjon om å komme i gang. Hvis du vil ha mer informasjon om hvordan du oppretter en nettressurs, for eksempel en HTML-fil som du kan bruke som en velkomstside, kan du se [Opprett og rediger nettressurser for å utvide nettprogrammet](create-edit-web-resources.md).|
    |**Aktiver frakoblet mobilmodus**|Dette alternativet gjør det mulig at appen kan være tilgjengelig frakoblet på mobiltelefoner for profiler som er valgt i rullegardinlisten **Frakoblede mobilprofiler**.|
  
3.  Lagre appen.  
  
## <a name="next-steps"></a>Neste trinn  
 [Opprett eller rediger en app](create-edit-app.md)
