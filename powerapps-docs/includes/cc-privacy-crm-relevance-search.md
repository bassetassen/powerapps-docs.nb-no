---
ms.openlocfilehash: dff813dcdf6d025ba47e29699e2047f79cf85600
ms.sourcegitcommit: ad203331ee9737e82ef70206ac04eeb72a5f9c7f
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/18/2019
ms.locfileid: "67225479"
---
Ved å aktivere Relevanssøk, begynner data i deltakende enheter og attributter i [!INCLUDE[pn_dynamics_crm_online](pn-dynamics-crm-online.md)]-forekomsten å synkronisere til og lagres i en [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Search-indeks.  
  
 Relevanssøk er ikke aktivert som standard. Systemansvarlig må aktivere funksjonen i en [!INCLUDE[pn_dynamics_crm_online](pn-dynamics-crm-online.md)]-forekomst. Når Relevanssøk er aktivert, har systemansvarlige og -tilpassere full kontroll over dataene som skal synkroniseres til [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Search-indeksen.  
  
 Systemtilpassere kan også bruke dialogboksen **Konfigurere Relevanssøk** i **Tilpassingsverktøy** for å aktivere bestemte enheter for søk, og deretter konfigurere Hurtigsøk-visning på aktiverte enheter, for å velge de søkbare attributtene. Dataendringer synkroniseres kontinuerlig mellom [!INCLUDE[pn_dynamics_crm_online](pn-dynamics-crm-online.md)] og [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Search gjennom en sikker kobling.  Konfigurasjonsdata krypteres, og de nødvendige hemmelighetene lagres i [!INCLUDE[pn_azure_key_vault](pn-azure-key-vault.md)].  
  
 Azure-komponenter og -tjenester som er involvert med Relevanssøk-funksjonen, beskrives i de følgende inndelingene.  
  
 [!INCLUDE[cc_privacy_note_azure_trust_center](cc_privacy_note_azure_trust_center.md)]  
  
 [Azure Search-tjenester](https://azure.microsoft.com/services/search/)  
  
 En [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Search-indeks brukes til å levere resultater med høy kvalitet og rask svartid.  [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Search legger til kraftige og avanserte neste generasjons søkefunksjoner i [!INCLUDE[pn_dynamics_crm_online](pn-dynamics-crm-online.md)].  Dette er en dedikert søketjeneste utenfor [!INCLUDE[pn_dynamics_crm_online](pn-dynamics-crm-online.md)], som leveres av [!INCLUDE[pn_Windows_Azure](pn-windows-azure.md)]. Alle nye [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Search-indekser krypteres når de er inaktive.  Hvis du registrerte deg før 24. januar 2018, må du indeksere dataene dine på nytt ved å melde deg ut av Relevanssøk, vente en time, og registrere deg på nytt.  
  
 [Azure SQL Database](https://azure.microsoft.com/services/sql-database/)  
  
 Relevanssøk bruker [!INCLUDE[pn_Azure_SQL_Database_long](pn-azure-sql-database-long.md)] til å lagre:  
  
-   Konfigurasjonsdata som er knyttet til organisasjonen og tilhørende indeks  
  
-   Metadata som er knyttet til søketjenesten og indekser  
  
-   Pekere til systemmetadata og data ved synkronisering av endringer  
  
-   Godkjenningsdata for å aktivere forbedret sikkerhet på radnivå  
  
[Azure Event Hubs](https://azure.microsoft.com/services/event-hubs/)  
  
[!INCLUDE[pn_azure_event_hubs](pn-azure-event-hubs.md)]-komponenten brukes til meldingsutveksling mellom [!INCLUDE[pn_dynamics_crm_online](pn-dynamics-crm-online.md)] og [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)], og til å vedlikeholde arbeidselementer som administreres av synkroniseringsprosessen. Hver melding inneholder informasjon, for eksempel organisasjons-ID og enhetsnavn, som brukes til å synkronisere dataene.  
  
[Azure Service Fabric-klynge](https://azure.microsoft.com/services/service-fabric/)  
  
Behandling og indeksering av data håndteres i mikrotjenester som distribueres i virtuelle maskiner, som administreres gjennom Service Fabric-kjøretiden. Search-API-er og datasynkroniseringsprosessen driftes også av Service Fabric-klyngen.  
  
Service Fabric er resultatet av flere års erfaring hos Microsoft, med levering driftskritiske skytjenester, og har nå bevist sin produktivitet i mer enn fem år. Det er den grunnleggende teknologien vi kjører [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-kjerneinfrastrukturen på, og det driver tjenester som [!INCLUDE[pn_skype_for_business](pn-skype-for-business.md)], [!INCLUDE[pn_intune](pn-intune.md)], [!INCLUDE[pn_azure_event_hubs](pn-azure-event-hubs.md)] og [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Data Factory, [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] DocumentDB, [!INCLUDE[pn_Azure_SQL_Database_long](pn-azure-sql-database-long.md)] og [!INCLUDE[pn_cortana](pn-cortana.md)], som kan skaleres til å behandle mer enn 500 millioner evalueringer i sekundet.  
  
[Azure-skaleringssett for virtuelle maskiner](https://azure.microsoft.com/services/virtual-machine-scale-sets/)  
  
[!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-skaleringssett for virtuelle maskiner er elastiske og utformet for å støtte arbeidsbelastninger med hyperutskalering. [!INCLUDE[pn_azure_service_fabric](pn_azure_service_fabric.md)]-klyngen kjører på skaleringssett for virtuelle maskiner. Mikrotjenestene for behandling og indeksering av data driftes på skaleringssettene og administreres av Service Fabric-kjøretiden.  
  
[Azure Key Vault](https://azure.microsoft.com/services/key-vault/)  
  
[!INCLUDE[pn_azure_key_vault](pn-azure-key-vault.md)] brukes til sikker administrasjon av sertifikater, nøkler og andre hemmeligheter som brukes i søkeprosessen.  
  
[Azure Storage (Blob Storage)](https://azure.microsoft.com/services/storage/blobs/?b=16.38)  
  
Endringer i kundedata lagres i opptil 2 dager i [!INCLUDE[pn_azure_blob_storage](pn_azure_blob_storage.md)].  Disse blobene krypteres ved å utnytte den nyeste funksjonen i [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Storage SDK, som tilbyr symmetrisk og asymmetrisk krypteringsstøtte og integrasjon med [!INCLUDE[pn_azure_key_vault](pn-azure-key-vault.md)]. Med [!INCLUDE[pn_crm_8_2_0_online_subsequent](pn-crm-8-2-0-online-subsequent.md)] synkroniseres også dokumentene i notater og vedlegg i e-postmeldinger og avtaler, til Blob Storage.  
  
[Azure Active Directory-tjeneste](https://azure.microsoft.com/services/active-directory/)  
  
[!INCLUDE[pn_azure_active_directory](pn-azure-active-directory.md)] brukes til å godkjenne mellom [!INCLUDE[pn_dynamics_crm_online](pn-dynamics-crm-online.md)]- og [!INCLUDE[pn_Windows_Azure](pn-windows-azure.md)]-tjenester.  
  
[Azure Load Balancer](https://azure.microsoft.com/services/load-balancer/)  
  
[!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Load Balancer brukes til å distribuere innkommende trafikk blant sikre tjenesteforekomster i skytjenester eller virtuelle maskiner som er definert i et belastningsfordelingssett. Relevanssøk bruker den til å belastningsfordele endepunktene i en distribusjon.  
  
[Azure Virtual Networks](https://azure.microsoft.com/documentation/articles/virtual-networks-overview/)  
  
De virtuelle maskinene på Service Fabric-klyngen, som kjører i ett eller flere delnett, er tilkoblet av [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Virtual Network. Sikkerhetspolicyer, DNS-innstillinger, rutetabeller og IP-adresser er fullstendig kontrollert i dette virtuelle nettverket. Grupper for nettverkssikkerhet utnyttes til å bruke sikkerhetsregler på dette virtuelle nettverket. Disse reglene tillater eller nekter nettverkstrafikk til de virtuelle maskinene i det virtuelle nettverket.