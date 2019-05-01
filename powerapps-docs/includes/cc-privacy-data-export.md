---
ms.openlocfilehash: e9b0446c2fb09cad33f5a3ae4bb69103f7d07d70
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/23/2019
ms.locfileid: "61579123"
---
Når du bruker dataeksporttjenesten ved aktivering av en dataeksportprofil i [!INCLUDE[pn_microsoftcrm](pn-microsoftcrm.md)], sendes dataene til enhetene som er lagt til i profilen, til [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]. Den innledende synkroniseringen omfatter alle dataene som er tilknyttet enhetene som er lagt til i eksportprofilen, men deretter omfatter synkroniseringen bare nye endringer, som kontinuerlig sendes til dataeksporttjenesten. Data som sendes til dataeksporttjenesten lagres midlertidig i [!INCLUDE[pn_azure_service_bus](pn_azure_service_bus.md)] og [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Storage, behandles i [!INCLUDE[pn_azure_service_fabric](pn_azure_service_fabric.md)] og synkroniseres til slutt (settes inn, oppdateres eller slettes) i måldatabasen som er angitt i [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-abonnementet. Når dataene er synkronisert, slettes de fra [!INCLUDE[pn_azure_service_bus](pn_azure_service_bus.md)] og [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Storage. Hvis det oppstår en feil under datasynkroniseringen, lagres et minimalt antall data som tilhører enhetstype, Post-ID og tidsstempel for synkronisering i [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Storage, for å tillate nedlasting av en liste med poster som ikke ble oppdatert.  
  
 En administrator kan deaktivere dataeksportprofilen når som helst for å stoppe datasynkronisering. I tillegg kan en administrator slette eksportprofilen for å fjerne eventuelle mislykkede postlogger, og kan avinstallere løsningen for dataeksporttjenesten for å slutte å bruke dataeksporttjenesten.  
  
 Datasynkronisering skjer kontinuerlig mellom [!INCLUDE[pn_crm_shortest](pn-crm-shortest.md)] og dataeksporttjenesten på en sikker måte. Data krypteres når de kontinuerlig utveksles mellom [!INCLUDE[pn_crm_shortest](pn-crm-shortest.md)] og dataeksporttjenesten.  
  
 Azure-komponenter og -tjenester som er involvert med dataeksporttjenesten, beskrives i de følgende inndelingene.  
  
 [!INCLUDE[cc_privacy_note_azure_trust_center](cc_privacy_note_azure_trust_center.md)]  
  
 [Azure Service Fabric](https://azure.microsoft.com/services/service-fabric/)  
  
 Denne angir API-en og behandler virtuelle [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-maskiner, slik at de kan behandle varsler om postsynkronisering fra [!INCLUDE[pn_crm_shortest](pn-crm-shortest.md)], og deretter behandle dem slik at de kan sette inn, oppdatere eller slette postdata i måldatabasen. Mikrotjenester som distribueres på virtuelle maskiner som administreres av [!INCLUDE[pn_azure_service_fabric](pn_azure_service_fabric.md)]-kjøretiden, håndterer alle databehandlingstjenester relatert til datasynkronisering.  
  
 [Azure Service Bus](https://azure.microsoft.com/services/service-bus/)  
  
 Denne angir meldingsbussen der [!INCLUDE[pn_crm_shortest](pn-crm-shortest.md)] setter inn varselmeldingene for synkronisering, som behandles av databehandlingsnoder i [!INCLUDE[pn_azure_service_fabric](pn_azure_service_fabric.md)]. Hver melding lagrer informasjon, som for eksempel organisasjons-ID og -post, som dataene skal synkroniseres til. Data i Azure Service Bus krypteres ikke når de er inaktive, men er bare tilgjengelige for dataeksporttjenesten.  
  
 [Azure Blob Storage](https://azure.microsoft.com/services/storage/)  
  
 Data lagres midlertidig i [!INCLUDE[pn_azure_blob_storage](pn_azure_blob_storage.md)], i tilfelle dataene for varsler for postsynkronisering er for store til å lagres i en melding, eller en midlertidig feil oppstår ved behandling av varselet for synkronisering. Disse blobene krypteres ved å utnytte den nyeste funksjonen i [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Storage SDK, som tilbyr symmetrisk og asymmetrisk krypteringsstøtte og integrasjon med [!INCLUDE[pn_azure_key_vault](pn-azure-key-vault.md)].  
  
 [Azure SQL](https://azure.microsoft.com/services/sql-database/)  
  
 [!INCLUDE[pn_Azure_SQL_Database_long](pn-azure-sql-database-long.md)] lagrer måledata for konfigurasjon av dataeksportprofil og datasynkronisering.