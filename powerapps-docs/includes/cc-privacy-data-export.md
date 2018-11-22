Ved å bruke dataeksporttjenesten når du aktiverer en dataeksportprofil i [!INCLUDE[pn_microsoftcrm](pn-microsoftcrm.md)], sendes dataene for enhetene som legges til i profilen til [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]. Den første synkroniseringen inkluderer alle dataene som er knyttet til enhetene som legges til i eksportprofilen, men etterpå inkluderer synkroniseringen bare nye endringer, som sendes til dataeksporttjenesten kontinuerlig. Data som sendes til dataeksporttjenesten, lagres midlertidig i [!INCLUDE[pn_azure_service_bus](pn_azure_service_bus.md)] og [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Storage, behandles i [!INCLUDE[pn_azure_service_fabric](pn_azure_service_fabric.md)], og synkroniseres til slutt (settes inn, oppdateres eller slettes) i måldatabasen som er angitt i [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-abonnementet. Når dataene er synkronisert, slettes de fra [!INCLUDE[pn_azure_service_bus](pn_azure_service_bus.md)] og [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Storage. Hvis det oppstår en feil under datasynkroniseringen, lagres det minimale data knyttet til enhetstype, post-ID og tidsstempel for synkronisering i [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Storage for å tillate nedlasting av en liste med poster som ikke ble oppdatert.  
  
 En administrator kan deaktivere dataeksportprofilen når som helst for å stoppe datasynkronisering. I tillegg kan en administrator slette eksportprofilen for å fjerne alle mislykkede postlogger, og kan avinstallere løsningen for dataeksporttjeneste for å slutte å bruke den.  
  
 Datasynkroniseringen skjer fortløpende mellom [!INCLUDE[pn_crm_shortest](pn-crm-shortest.md)] og dataeksporttjenesten på en sikker måte. Dataene krypteres siden de utveksles fortløpende mellom [!INCLUDE[pn_crm_shortest](pn-crm-shortest.md)] og dataeksporttjenesten.  
  
 Azure-komponenter og -tjenester som er involvert i dataeksporttjenesten, er beskrevet i avsnittene nedenfor.  
  
 [!INCLUDE[cc_privacy_note_azure_trust_center](cc_privacy_note_azure_trust_center.md)]  
  
 [Azure Service Fabric](https://azure.microsoft.com/services/service-fabric/)  
  
 Dette inneholder API-en og [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] VM-er for beregning som skal brukes til å behandle varsler for synkronisering av poster som mottas fra [!INCLUDE[pn_crm_shortest](pn-crm-shortest.md)], og deretter behandle dem for å sette inn, oppdatere eller slette postdata i måldatabasen. Mikrotjenester som distribueres på virtuelle maskiner styrt av kjøretiden for [!INCLUDE[pn_azure_service_fabric](pn_azure_service_fabric.md)], håndterer alle beregningstjenester som er relatert til datasynkronisering.  
  
 [Azure Service Bus](https://azure.microsoft.com/services/service-bus/)  
  
 Dette inneholder meldingsbussen hvor [!INCLUDE[pn_crm_shortest](pn-crm-shortest.md)] setter inn synkroniseringsvarslene som skal behandles av beregningsnoder i [!INCLUDE[pn_azure_service_fabric](pn_azure_service_fabric.md)]. Hver enkelt melding lagrer informasjon, for eksempel organisasjons-ID og post som det skal synkroniseres data for. Data i Azure Service Bus krypteres ikke, men er bare tilgjengelige via dataeksporttjenesten.  
  
 [Azure Blob-lagring](https://azure.microsoft.com/services/storage/)  
  
 Dataene lagres midlertidig i [!INCLUDE[pn_azure_blob_storage](pn_azure_blob_storage.md)], i tilfelle dataene i synkroniseringsvarselet for post er for store til å lagres i en melding, eller at det blir oppdaget en midlertidig feil ved behandling av synkroniseringsvarselet. Disse blobene krypteres ved å bruke den nyeste funksjonen i [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Storage SDK, som gir symmetrisk og asymmetrisk krypteringsstøtte og integrering med [!INCLUDE[pn_azure_key_vault](pn-azure-key-vault.md)].  
  
 [Azure SQL](https://azure.microsoft.com/services/sql-database/)  
  
 [!INCLUDE[pn_Azure_SQL_Database_long](pn-azure-sql-database-long.md)] lagrer konfigurasjonen av dataeksportprofil og metrikkverdier for datasynkronisering.