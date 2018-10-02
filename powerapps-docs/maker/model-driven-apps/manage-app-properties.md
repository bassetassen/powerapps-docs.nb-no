---
title: Administrere egenskaper for modelldrevne apper i apputformingen til PowerApps | MicrosoftDocs
description: Finn ut hvordan du administrerer egenskapene for appen
keywords: ''
ms.date: 06/27/2018
ms.service: crm-online
ms.custom: null
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
author: Mattp123
ms.assetid: e773e60f-0211-4c4b-a1af-663be4997629
ms.author: matp
manager: kvivek
ms.reviewer: null
ms.suite: null
ms.tgt_pltfrm: null
caps.latest.revision: 14
topic-status: Drafting
---

# <a name="manage-model-driven-app-properties-in-the-app-designer"></a>Administrere egenskaper for modelldrevne apper i apputformingen

Appegenskaper definerer viktige detaljer om appen, som tittelen eller URL-adressen. Du definerer appegenskaper når du oppretter en app. Hvis du vil endre disse egenskapene senere, kan du gjøre dette i apputformingen.  
  
1.  Til høyre i apputformingen velger du kategorien **Egenskaper**.  

    > [!div class="mx-imgBorder"] 
    > ![Egenskaper-ruten i apputforming](media/app-designer-properties-tab.png "Egenskaper-ruten i apputforming")  
  
2.  Endre informasjonen etter behov>  

    |Egenskap|Beskrivelse|  
    |--------------|-----------------|
    |**Navn**|Angi et unikt og beskrivende navn for appen.|  
    |**Beskrivelse**|Skriv inn en kort beskrivelse av appen.|  
    |**Ikon**|Som standard er **Bruk standardapp** avmerket. Fjern merket hvis du vil velge en annen webressurs som ikon for appen, og velg deretter et ikon fra rullegardinlisten. Dette ikonet vises i forhåndsvisningsflisen for appen.|
    |**Unikt navn**| Du kan ikke endre det unike navnet. Ved hjelp av det unike navnet kan du spørre tabeller for å hente data fra database.| 
    |**Klient**|Definerer klienttypen som appen skal brukes for.<br/>-  **Web:** Dette er den klassiske Dynamics 365 customer engagement-nettleserklienten.<br/>-  **Enhetlig grensesnitt:** Dette er en ny nettleserklient som har et lignende grensesnitt på PC og mobile enheter.|
    |**Suffiks for URL-adresse for appen**| Nettadressen du valgte under oppretting av appen, vises her som standard. Du kan endre URL-adressen for appen i dialogboksen **Administrer app**. Legg merke til at du ikke kan eksportere eller importere suffikset for appens URL-adresse via en løsning for øyeblikket.|
    |**Velg en velkomstside for appen**|Dette alternativet lar deg velge fra webressursene som er tilgjengelige i miljøet. Velkomstsidene du lager, kan inneholde nyttig informasjon til brukere, for eksempel koblinger til videoer oppgraderingsinstruksjoner eller informasjon om å komme i gang. Du finner mer informasjon om hvordan du oppretter en webressurs, for eksempel en HTML-fil som du kan bruke som velkomstside, i [Opprette og redigere webressurser for å utvide webprogrammet](create-edit-web-resources.md).|
    |**Aktiver Mobile Offline**|Dett alternativet lar appen være tilgjengelig i frakoblet modus på mobiler for profilene som velges med rullegardinlisten **Mobile Offline-profiler**.|
  
3.  Lagre appen.  
  
## <a name="next-steps"></a>Neste trinn  
 [Opprette eller redigere en app](create-edit-app.md)
