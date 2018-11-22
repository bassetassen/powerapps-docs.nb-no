Ved å aktivere redigering av læringsforløp for en [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)]-organisasjon, blir innhold i læringsforløp (publisert eller utkast) som er opprettet av brukere (med de riktige sikkerhetsrettighetene), lagret i [!INCLUDE[pn_Azure_SQL_Database_long](pn-azure-sql-database-long.md)]. I tillegg kan [!INCLUDE[pn_azure_cloud_services](pn-azure-cloud-services.md)] lagre følgende data som er knyttet til en [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)]-organisasjon, når funksjonen aktiveres:  
  
-   Liste over organisasjoner i leieren  
  
-   Sluttbrukeres [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)]-klient og aktuelle konfigurasjon av nettleser / OS  
  
-   Bruksdata for sluttbrukere, for eksempel tid brukt på læringsforløp eller registrerte klikk  
  
-   Samlede sluttbrukerdata – sted, sikkerhetsrolle, brukerspråk  
  
-   Samlede sluttbrukerdata – sted, sikkerhetsrolle, brukerspråk  
  
-   Beskrivende tilbakemelding fra sluttbrukere  
  
 En administrator kan aktivere (og kan deretter deaktivere) redigering av læringsforløp via en innstilling i fanen **Generelt** i dialogboksen **Systeminnstillinger**.  
  
 [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-komponenter og -tjenester som er involvert i funksjonen for redigering av læringsforløp, er beskrevet i avsnittene nedenfor.  
  
 [!INCLUDE[cc_privacy_note_azure_trust_center](cc-privacy-note-azure-trust-center.md)]  
  
 [Cloud Services](https://azure.microsoft.com/en-us/services/cloud-services/)  
  
 **Webtjeneste**  
  
 Webtjeneste betjener kontrollene som gjengis i klienten av kjøretiden for læringsforløp. Webtjeneste støtter også Designer API, som brukes av redigeringen av læringsforløp. Kontrollene lagres av tjenesten på [!INCLUDE[pn_Azure_SQL_Database_long](pn-azure-sql-database-long.md)].  
  
 **Kompilator (arbeiderrolle)**  
  
 Kompilatorrollen administrerer publiseringen av en kontroll i en publiseringsgruppe. Kompilatoren bruker køen til å lagre meldinger om publiseringsjobben. Resultatene lagres i [!INCLUDE[pn_Azure_SQL_Database_long](pn-azure-sql-database-long.md)].  
  
 [Azure SQL Database](https://azure.microsoft.com/en-us/services/sql-database/)  
  
 Læringsforløpet bruker [!INCLUDE[pn_Azure_SQL_Database_long](pn-azure-sql-database-long.md)] til å lagre:  
  
-   Kontroller som opprettes ved hjelp av læringsforløpet.  
  
-   Konfigurasjonsrelatert redigering av læringsforløp.  
  
 [Azure Active Directory](https://azure.microsoft.com/en-us/services/active-directory/)  
  
 Læringsforløpet bruker [!INCLUDE[pn_azure_active_directory](pn-azure-active-directory.md)] til å godkjenne Webtjeneste.  
  
 [Azure Traffic Manager](https://azure.microsoft.com/en-us/services/traffic-manager/)  
  
 Læringsforløpet bruker [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Traffic Manager til å lastfordele webtjenesten for tilgjengelighet og ytelse.  
  
 [Azure Storage-kø](https://azure.microsoft.com/en-us/services/storage/)  
  
 [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Storage-kø brukes til å koordinere kommunikasjon mellom rollene Webtjeneste og Kompilator.  
  
 [Azure Blob-lagring](https://azure.microsoft.com/en-us/services/storage/)  
  
 Læringsforløpet bruker [!INCLUDE[pn_azure_blob_storage](pn-azure-blob-storage.md)] til å lagre det statiske innholdet ([!INCLUDE[pn_JavaScript](pn-javascript.md)] på klientsiden, bilder, CSS-innhold).  
  
 [Azure Content Delivery Network (CDN)](https://azure.microsoft.com/en-us/services/cdn/)  
  
 CDN brukes til å bufre det statiske innholdet på klientsiden ([!INCLUDE[pn_JavaScript](pn-javascript.md)], bilder og CSS-filer) for å betjene dem fra et globalt CDN-nettverk.