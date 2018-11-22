Ved å installere og aktivere [!INCLUDE[pn_gamification](pn-gamification.md)]-løsningen, blir brukerens kontoopplysninger (for eksempel fornavn, etternavn og e-postadresse), lagret i [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] for å tillate godkjenning med [!INCLUDE[pn_gamification_shortest](pn-gamification-shortest.md)]-tjenesten, som driftes i [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]. Dette gjelder for alle brukere som aktiveres i [!INCLUDE[pn_gamification_shortest](pn-gamification-shortest.md)]-tjenesten av sin administrator. [!INCLUDE[pn_gamification_shortest](pn-gamification-shortest.md)]-løsningen sender KPI-data (Key Performance Indicators), som er konfigurert av en administrator, til [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-tjenesten, og dataene lagres i [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-strukturert lager og i tillegg i bloblagringen.  Hver brukers avatar, premier, og firmalogo lagres i [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)], men informasjonen returneres ikke til [!INCLUDE[pn_crm_shortest](pn-crm-shortest.md)].  
  
Vær oppmerksom på at administratorer og autoriserte brukere kan bruke [!INCLUDE[pn_crm_shortest](pn-crm-shortest.md)]-data, for eksempel telefonsamtaler, salgsmuligheter og registrert omsetning, til å konfigurere KPI-er som skal brukes i spill. [!INCLUDE[pn_gamification_shortest](pn-gamification-shortest.md)]-tjenesten videreformidler ingen anrop til [!INCLUDE[pn_crm_shortest](pn-crm-shortest.md)] og responderer bare på data, for eksempel spill der KPI-er blir brukt, som returneres til [!INCLUDE[pn_crm_shortest](pn-crm-shortest.md)].  
  
En administrator kan også angi at TV-strømmen for [!INCLUDE[pn_gamification_shortest](pn-gamification-shortest.md)] skal gjøres tilgjengelig for alle. Spilledere som setter opp TV-strømminger for [!INCLUDE[pn_gamification_shortest](pn-gamification-shortest.md)] og aktiverer offentlig strømming, tillater at TV-strømmen kan vises av alle på Internett med selve strømmekoblingen.  
  
En administrator deretter fjerne [!INCLUDE[pn_gamification_shortest](pn-gamification-shortest.md)]-funksjonen ved å avinstallere denne løsningen fra [!INCLUDE[pn_microsoftcrm](pn-microsoftcrm.md)]-organisasjonen.  
  
[!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-komponenter og -tjenester som er involvert i [!INCLUDE[pn_gamification_shortest](pn-gamification-shortest.md)], er beskrevet i avsnittene nedenfor.  
  
[!INCLUDE[cc_privacy_note_azure_trust_center](cc-privacy-note-azure-trust-center.md)]  
  
[Cloud Services](https://azure.microsoft.com/services/cloud-services/)  
  
 **Designer Service (webrolle)**  
  
Tilbyr flere webtjenester for kommunikasjon mellom en [!INCLUDE[pn_crm_shortest](pn-crm-shortest.md)]-organisasjon og multi-instanskomponentene for [!INCLUDE[pn_gamification_shortest](pn-gamification-shortest.md)] [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]. For eksempel hvis gamification-detaljer er lagret i [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] SQL Storage.  Spillberegninger bruker [!INCLUDE[pn_azure_service_bus](pn-azure-service-bus.md)]-kø, og de returneres som poeng og vises i tjenesten.  Kunde- og brukeropplastede bilder lagres i [!INCLUDE[pn_azure_blob_storage](pn-azure-blob-storage.md)]. Alle forespørsler er godkjent i forhold til [!INCLUDE[pn_azure_active_directory](pn-azure-active-directory.md)].  
  
[Azure Key Vault](https://azure.microsoft.com/services/key-vault/)  
  
Alle tjenester lagrer konfigurasjonsdata i [!INCLUDE[pn_azure_key_vault](pn-azure-key-vault.md)].  
  
[Azure SQL Database](https://azure.microsoft.com/services/sql-database/)  
  
[!INCLUDE[pn_gamification_shortest](pn-gamification-shortest.md)] bruker SQL [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] til å lagre:  
  
- KPI-data  
  
- Spillberegninger  
  
- Organisasjonsdata (leierdata)  
  
[Azure Blob-lagring](https://azure.microsoft.com/services/storage/)  
  
Avatarer, firmalogoer og andre kundeopplastede bilder lagres i [!INCLUDE[pn_azure_blob_storage](pn-azure-blob-storage.md)].  
  
[Azure Content Delivery Network (CDN)](https://azure.microsoft.com/services/cdn/)  
  
[!INCLUDE[pn_gamification_shortest](pn-gamification-shortest.md)] bruker [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Content Delivery Network til å levere statisk innhold til kjøretiden, for eksempel bilder (inkludert opplastede bilder som kundelogoer), [!INCLUDE[pn_JavaScript](pn-javascript.md)] og CSS.  
  
[Azure Active Directory](https://azure.microsoft.com/services/active-directory/)  
  
[!INCLUDE[pn_gamification_shortest](pn-gamification-shortest.md)] bruker [!INCLUDE[pn_azure_active_directory](pn-azure-active-directory.md)] til å godkjenne brukere og fastslå rettigheter til å bruke plattformen.