---
title: Opprett eller rediger en modelldreven app ved hjelp av apputforming i PowerApps | MicrosoftDocs
description: Finn ut hvordan du oppretter eller redigerer apper ved hjelp av apputforming
keywords: ''
ms.date: 05/23/2018
ms.service: crm-online
ms.custom: null
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
author: Mattp123
ms.assetid: 2a44229e-44f0-4c4e-ba21-a476210d0a12
ms.author: matp
manager: kvivek
ms.reviewer: null
ms.suite: null
ms.tgt_pltfrm: null
caps.latest.revision: 19
topic-status: Drafting
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="tutorial-create-a-model-driven-app-by-using-the-app-designer"></a>Opplæring: Opprett eller rediger en modelldreven app ved hjelp av apputforming

I denne opplæringen lærer du det grunnleggende om hvordan du oppretter og redigerer en modelldrevet app ved hjelp av flisbasert apputforming.

## <a name="prerequisites"></a>Forhåndskrav
Før du begynner å opprette en app, kontrollerer du følgende forhåndskrav:
- Et PowerApps-miljø Mer informasjon: [Opprette et miljø](https://docs.microsoft.com/powerapps/administrator/create-environment)
- Sikkerhetsrollen Systemadministrator eller Systemtilpasser. Mer informasjon: [Om forhåndsdefinerte sikkerhetsroller](https://docs.microsoft.com/powerapps/maker/model-driven-apps/share-model-driven-app#about-predefined-security-roles).
 
<a name="createApp"></a>   
## <a name="create-an-app"></a>Opprette en app  

1.  På [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)-området velger du **Modelldrevet** (nederst til venstre i navigasjonsruten).  

    ![Modelldrevet utformingsmodus](media/model-driven-switch.png)

    > [!IMPORTANT]
    > "Hvis utformingsmodusen **Modelldrevet** ikke er tilgjengelig, må du kanskje [opprette et miljø](https://docs.microsoft.com/powerapps/administrator/create-environment). 

2. Velg **Apper**, og velg deretter **Opprett en app**.

3. På siden **Opprett en ny app** skriver du inn følgende detaljer: 

    - **Navn**: Angi et navn for appen.  
  
    - **Unikt navn**: Det unike navnet fylles ut automatisk basert på appnavnet du angir. Det innledes med et utgiverprefiks. Du kan endre den delen av det unike navnet som kan redigeres. Det unike navnet kan bare inneholde engelske tegn og tall.  
  
        > [!NOTE]
        >  Utgiverprefikset er teksten som legges til en enhet eller et felt som opprettes for en løsning som har denne utgiveren.   
  
    - **Beskrivelse**: Skriv inn en kort beskrivelse av hva appen er eller gjør.  
  
    - **Ikon**: Som standard er det merket av for miniatyrbildefeltet **Bruk standardapp**. Fjern merket hvis du vil velge en annen webressurs som ikon for appen, og velg deretter et ikon fra rullegardinlisten. Dette ikonet vises i forhåndsvisningsflisen for appen.  
  
    - Velg klienttypen som appen skal brukes for.  
  
        - **Enhetlig grensesnitt**: Dette er den nyere og responsive nettleserklienten som har et lignende grensesnitt på PC og mobilenheter.  

        - **Web**: Dette er den klassiske Dynamics 365 customer engagement-nettleserklienten.  
    
    - **Suffiks for URL-adresse for appen**: URL-adressen for appen fylles ut automatisk basert på appnavnet du angir. Du vil se en forhåndsvisning av hvordan hele URL-adressen ser ut. URL-adressen for appen må være unik.  
  
         Eksempel: https://\<org>.crm#.dynamics.com/Apps/\<App-URL>

         For lokale: http://\<server>/\<organisasjonsnavn>/Apps/\<URL-adresse for app> 
  
      > [!NOTE]
      >  Hvis du fjerner merket for **Suffiks for URL-adresse for appen** og deretter lagrer appen, genereres URL-adressen for appen automatisk med app-ID-en.  
  
    - **Bruk eksisterende løsning til å opprette appen**: Velg dette alternativet for å opprette appen fra en liste over installerte løsninger. Når du velger dette alternativet, endres **Fullført** til **Neste** i overskriften. Hvis du velger **Neste**, åpnes siden **Opprett app fra eksisterende løsning**. I rullegardinlisten **Velg løsning** velger du løsningen som du vil opprette appen fra. Hvis områdekart er tilgjengelig for den valgte løsningen, vises rullegardinlisten **Velg områdekart**. Velg områdekartet og deretter **Fullført**.

      > [!NOTE]
      > Ved å velge **Standardløsning** når du legger til et områdekart, blir komponentene som er tilknyttet områdekartet automatisk lagt til i appen.  

      ![Siden Bruk eksisterende løsning til å opprette appen](media/use-existing-solution-to-create-the-app.png "Siden Bruk eksisterende løsning til å opprette appen") 

    - **Velg en velkomstside**: Dette alternativet lar deg velge fra webressursene som er tilgjengelige i organisasjonen. Velkomstsidene du lager, kan inneholde informasjon som er nyttig for brukere, for eksempel koblinger til videoer oppgraderingsinstruksjoner eller informasjon om å komme i gang. Velkomstsiden vises når en app åpnes. Brukere kan velge **Ikke vis denne velkomstskjermen neste gang** på velkomstsiden for å deaktivere siden, slik at den ikke vises neste gang appen starter. Mer informasjon om hvordan du oppretter en webressurs, for eksempel en HTML-fil som du kan bruke som velkomstside: [Opprette og redigere webressurser for å utvide webprogrammet](create-edit-web-resources.md)  
      
    Hvis du vil redigere appegenskaper senere, kan du gå til **Egenskaper**-kategorien i apputformingen. Mer informasjon: [Administrere appegenskaper](manage-app-properties.md)  
  
     > [!NOTE]
     >  Du kan ikke endre det unike navnet og suffikset for URL-adressen for appen i kategorien **Egenskaper**.  
  
4. Velg **Fullført** eller&mdash;, hvis du valgte **Bruk eksisterende løsning for å opprette appen**&mdash;, klikk **Neste** for å velge blant de tilgjengelige løsningene som ble importert i organisasjonen.  
  
    En ny app blir opprettet, og viser statusen Utkast. Du vil se lerretet for apputforming for den nye appen. Derfra kan du legge til komponenter, for eksempel enheter, visninger og instrumentbord, for å gjøre appen nyttig. Mer informasjon: [Legge til eller redigere appkomponenter](add-edit-app-components.md)  
   
<a name="editApp"></a>   
## <a name="edit-an-app"></a>Redigere en app  
  
1.  På [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)-området velger du **Modelldrevet** (nederst til venstre i navigasjonsruten).  

> [!IMPORTANT]
> "Hvis utformingsmodusen **Modelldrevet** ikke er tilgjengelig, må du kanskje [opprette et miljø](https://docs.microsoft.com/powerapps/administrator/create-environment). 

2. I navigasjonsruten til venstre velger du **Apper**, velger en app, og velger deretter **Rediger** på verktøylinjen.   

3. I apputformingen legger du til eller redigerer komponenter i appen etter behov. Mer informasjon: [Legge til eller redigere appkomponenter](add-edit-app-components.md)  
 
  
### <a name="next-steps"></a>Neste trinn  
 [Legge til eller redigere appkomponenter](add-edit-app-components.md)   


