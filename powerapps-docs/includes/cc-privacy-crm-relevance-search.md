Ved å aktivere relevanssøk blir data i enheter og attributter som deltar, begynne å synkroniseres i forekomsten av [!INCLUDE[pn_dynamics_crm_online](pn-dynamics-crm-online.md)], og lagres i en [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Search-indeks.  
  
 Relevanssøk er ikke deaktivert som standard. Systemansvarlig må aktivere funksjonaliteten i en forekomst av [!INCLUDE[pn_dynamics_crm_online](pn-dynamics-crm-online.md)]. Når relevanssøk er aktivert, har systemansvarlige og tilpassere full kontroll over dataene som skal synkroniseres med [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Search-indeksen.  
  
 Systemtilpassere kan bruke dialogboksen **Konfigurer relevanssøk** i **tilpassingsverktøyene** for å gjøre det mulig for bestemte enheter å søke, og deretter konfigurere hurtigsøkvisninger på aktiverte enheter til å velge de søkbare attributtene. Dataendringer synkroniseres fortløpende mellom [!INCLUDE[pn_dynamics_crm_online](pn-dynamics-crm-online.md)] og [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Search via en sikker tilkobling.  Konfigurasjonsdata krypteres, og påkrevde hemmeligheter lagres i [!INCLUDE[pn_azure_key_vault](pn-azure-key-vault.md)].  
  
 Azure-komponenter og -tjenester som er involvert i Relevanssøk-funksjonalitet, er beskrevet i avsnittene nedenfor.  
  
 [!INCLUDE[cc_privacy_note_azure_trust_center](cc_privacy_note_azure_trust_center.md)]  
  
 [Azure Search-tjenester](https://azure.microsoft.com/services/search/)  
  
 En [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Search-indeks brukes for å gi søkeresultater av høy kvalitet med hurtig svartid.  [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Search legger til kraftige og avanserte neste generasjons søkefunksjoner i [!INCLUDE[pn_dynamics_crm_online](pn-dynamics-crm-online.md)].  Dette er en dedikert ekstern søketjeneste for [!INCLUDE[pn_dynamics_crm_online](pn-dynamics-crm-online.md)] som leveres av [!INCLUDE[pn_Windows_Azure](pn-windows-azure.md)]. Alle nye [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-søkeindekser krypteres mens de er inaktive.  Hvis du valgte dette alternativet før 24. januar 2018, må du indeksere dataene på nytt ved å velge bort relevanssøk, vente en time og deretter velge det på nytt.  
  
 [Azure SQL Database](https://azure.microsoft.com/services/sql-database/)  
  
 Relevanssøk bruker [!INCLUDE[pn_Azure_SQL_Database_long](pn-azure-sql-database-long.md)] til å lagre:  
  
-   Konfigurasjonsdata relatert til organisasjonen og den tilhørende indeksen  
  
-   Metadata relatert til søketjenesten og indekser  
  
-   Pekere til metadata for system og data når synkroniseringen endres  
  
-   Godkjenningsdata for å aktivere forbedret sikkerhet på radnivå  
  
[Azure Event Hubs](https://azure.microsoft.com/services/event-hubs/)  
  
[!INCLUDE[pn_azure_event_hubs](pn-azure-event-hubs.md)]-komponenten brukes til meldingsutveksling mellom [!INCLUDE[pn_dynamics_crm_online](pn-dynamics-crm-online.md)] og [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)], og til vedlikehold av arbeidselementer som styres av synkroniseringsprosessen. Hver enkelt melding lagrer informasjon, for eksempel organisasjons-ID og enhetsnavn, som brukes til å synkronisere dataene.  
  
[Azure Service Fabric Cluster](https://azure.microsoft.com/services/service-fabric/)  
  
Behandlingen og indekseringen av data håndteres i mikrotjenester som distribueres på virtuelle maskiner som administreres via Service Fabric ved kjøring. API-ene for søk og datasynkroniseringsprosessen driftes også i Service Fabric-klyngen.  
  
Service Fabric er et resultat av år med erfaring hos Microsoft med å levere forretningskritiske skytjenester, og er nå prøvd i produksjon i mer enn fem år. Det er teknologigrunnlaget som vi kjører [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-kjerneinfrastrukturen på og leverer tjenester fra, inkludert [!INCLUDE[pn_skype_for_business](pn-skype-for-business.md)], [!INCLUDE[pn_intune](pn-intune.md)], [!INCLUDE[pn_azure_event_hubs](pn-azure-event-hubs.md)], [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Data Factory, [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] DocumentDB, [!INCLUDE[pn_Azure_SQL_Database_long](pn-azure-sql-database-long.md)] og [!INCLUDE[pn_cortana](pn-cortana.md)], som kan skalere for å behandle mer enn 500 million evalueringer per sekund.  
  
[Azure Virtual Machine Scale Sets](https://azure.microsoft.com/services/virtual-machine-scale-sets/)  
  
[!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Virtual Machine Scale Sets er elastiske og utviklet til å støtte hyperutskaleringsarbeidsbelastninger. [!INCLUDE[pn_azure_service_fabric](pn_azure_service_fabric.md)]-klyngen kjøres på skaleringssett for virtuell maskin. Mikrotjenestene for behandling og indeksering av data driftes også på skaleringssett og styres av Service Fabric ved kjøring.  
  
[Azure Key Vault](https://azure.microsoft.com/services/key-vault/)  
  
[!INCLUDE[pn_azure_key_vault](pn-azure-key-vault.md)] brukes for sikker administrasjon av sertifikater, nøkler og andre hemmeligheter som brukes i søkeprosessen.  
  
[Azure Storage (Blob-lagring)](https://azure.microsoft.com/services/storage/blobs/?b=16.38)  
  
Endringer for kundedata lagres i opptil to dager i [!INCLUDE[pn_azure_blob_storage](pn_azure_blob_storage.md)].  Disse blobene krypteres ved å bruke den nyeste funksjonen i [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Storage SDK, som gir symmetrisk og asymmetrisk krypteringsstøtte og integrering med [!INCLUDE[pn_azure_key_vault](pn-azure-key-vault.md)]. Med [!INCLUDE[pn_crm_8_2_0_online_subsequent](pn-crm-8-2-0-online-subsequent.md)] synkroniseres også dokumentene i notater og vedlegg i e-postmeldinger og avtaler med bloblagringen.  
  
[Azure Active Directory-tjeneste](https://azure.microsoft.com/services/active-directory/)  
  
[!INCLUDE[pn_azure_active_directory](pn-azure-active-directory.md)] brukes til godkjenning mellom [!INCLUDE[pn_dynamics_crm_online](pn-dynamics-crm-online.md)] og [!INCLUDE[pn_Windows_Azure](pn-windows-azure.md)]-tjenester.  
  
[Azure Load Balancer](https://azure.microsoft.com/services/load-balancer/)  
  
The [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Load Balancer brukes til å distribuere innkommende trafikk mellom sunne tjenesteforekomster i skytjenester eller virtuelle maskiner som er definert i et belastningsfordelingssett. Relevanssøk bruker det til å lastfordele endepunktene i en distribusjon.  
  
[Azure Virtual Networks](https://azure.microsoft.com/documentation/articles/virtual-networks-overview/)  
  
De virtuelle maskinene i Service Fabric-klyngen som kjører i ett eller flere delnett, kobles til ved hjelp av [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Virtual Network. Sikkerhetspolicyene, DNS-innstillinger, rutetabeller og IP-adresser er under fullstendig kontroll i dette virtuelle nettverket. Sikkerhetsgrupper for nettverk utnyttes for å bruke sikkerhetsregler i dette virtuelle nettverket. Disse reglene tillater og nekter nettverkstrafikk til de virtuelle maskinene i det virtuelle nettverket.