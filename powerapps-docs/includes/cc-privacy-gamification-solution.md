---
ms.openlocfilehash: 747ea34b784b852261debe91f587d64ee3277804
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/23/2019
ms.locfileid: "61574947"
---
Ved å installere og aktivere [!INCLUDE[pn_gamification](pn-gamification.md)]-løsningen, lagres identifikatorene for den aktiverte brukerens konto (som for eksempel fornavn, etternavn og e-postadresse) i [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] for å tillate godkjenning med [!INCLUDE[pn_gamification_shortest](pn-gamification-shortest.md)]-tjenesten, som er drevet av [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]. Dette gjelder for alle brukere som er aktivert i [!INCLUDE[pn_gamification_shortest](pn-gamification-shortest.md)]-tjenesten av systemansvarlig. [!INCLUDE[pn_gamification_shortest](pn-gamification-shortest.md)]-løsningen sender data fra sentrale ytelsesindikatorer (KPI-er) som er konfigurert av en administrator, til [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-tjenesten, og dataene lagres i strukturert lagring og BLOB-lagring i [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)].  Hver brukers Avatar, egendefinerte utmerkelser og firmalogo er lagret i [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)], men informasjonen returneres ikke til [!INCLUDE[pn_crm_shortest](pn-crm-shortest.md)].  
  
Vær oppmerksom på at administratorer og autoriserte brukere kan dra nytte av [!INCLUDE[pn_crm_shortest](pn-crm-shortest.md)]-data, som for eksempel telefonsamtaler, salgsmuligheter og bestilt omsetning til å konfigurere KPI-er for bruk i spill. [!INCLUDE[pn_gamification_shortest](pn-gamification-shortest.md)]-tjenesten oppretter ikke anrop til [!INCLUDE[pn_crm_shortest](pn-crm-shortest.md)] og responderer bare på data, som for eksempel spill der KPI-er brukes, som flyter tilbake til [!INCLUDE[pn_crm_shortest](pn-crm-shortest.md)].  
  
En administrator kan også aktivere TV-dataflyten for [!INCLUDE[pn_gamification_shortest](pn-gamification-shortest.md)] slik at den blir gjort offentlig. Spilledere som konfigurerer TV-dataflyter for [!INCLUDE[pn_gamification_shortest](pn-gamification-shortest.md)] og aktiverer offentlig strømming, tillater at TV-dataflyten kan vises av alle på nett som har koblingen til strømmingen.  
  
En administrator kan deretter deaktivere [!INCLUDE[pn_gamification_shortest](pn-gamification-shortest.md)]-funksjonen ved å avinstallere denne løsningen fra [!INCLUDE[pn_microsoftcrm](pn-microsoftcrm.md)]-organisasjonen.  
  
[!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-komponenter og -tjenester som er involvert i [!INCLUDE[pn_gamification_shortest](pn-gamification-shortest.md)], beskrives i de følgende inndelingene.  
  
[!INCLUDE[cc_privacy_note_azure_trust_center](cc-privacy-note-azure-trust-center.md)]  
  
[Cloud Services](https://azure.microsoft.com/services/cloud-services/)  
  
 **Utformer-tjenesten (Nettrolle)**  
  
Her får brukerne tilgang til flere nettjenester for kommunikasjon mellom en [!INCLUDE[pn_crm_shortest](pn-crm-shortest.md)]-organisasjon og [!INCLUDE[pn_gamification_shortest](pn-gamification-shortest.md)] [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-komponenter for flere leiere. For eksempel spillifiseringsdetaljer lagret i SQL-lagring for [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)].  Spillberegninger bruker [!INCLUDE[pn_azure_service_bus](pn-azure-service-bus.md)]-kø og returneres for å evalueres og vises i tjenesten.  Kunde- og brukeropplastede bilder lagres i [!INCLUDE[pn_azure_blob_storage](pn-azure-blob-storage.md)]. Alle forespørsler er godkjent mot [!INCLUDE[pn_azure_active_directory](pn-azure-active-directory.md)].  
  
[Azure Key Vault](https://azure.microsoft.com/services/key-vault/)  
  
Alle tjenester lagrer konfigurasjonsdata i [!INCLUDE[pn_azure_key_vault](pn-azure-key-vault.md)].  
  
[Azure SQL Database](https://azure.microsoft.com/services/sql-database/)  
  
[!INCLUDE[pn_gamification_shortest](pn-gamification-shortest.md)] bruker SQL [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] til å lagre:  
  
- KPI-data  
  
- Spillberegninger  
  
- Organisasjonsdata (leier)  
  
[Azure Blob Storage](https://azure.microsoft.com/services/storage/)  
  
Avatarer, firmalogoer og andre kundeopplastede bilder lagres i [!INCLUDE[pn_azure_blob_storage](pn-azure-blob-storage.md)].  
  
[Azure Content Delivery Network (CDN)](https://azure.microsoft.com/services/cdn/)  
  
[!INCLUDE[pn_gamification_shortest](pn-gamification-shortest.md)] bruker [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Content Delivery Network til å behandle statisk innhold for kjøringen, som for eksempel bilder (inkludert opplastede bilder, som for eksempel kundelogoer), [!INCLUDE[pn_JavaScript](pn-javascript.md)] og CSS.  
  
[Azure Active Directory](https://azure.microsoft.com/services/active-directory/)  
  
[!INCLUDE[pn_gamification_shortest](pn-gamification-shortest.md)] bruker [!INCLUDE[pn_azure_active_directory](pn-azure-active-directory.md)] til å godkjenne brukere, og avgjøre om de er kvalifisert til å bruke plattformen.