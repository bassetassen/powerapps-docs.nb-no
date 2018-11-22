Ved å aktivere tekstanalysefunksjonen aktiverer du avhengige funksjoner i [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)] som bruker API for [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Cognitive Services-tekstanalyse for å tilby avansert innsikt. Disse avhengige funksjonene er:  
  
-   Kunnskapsforslag  
  
-   Saksemneanalyse  
  
-   Forslag for lignende saker  
  
 En administrator kan aktivere funksjonen for tekstanalyse under kategorien **Innstillinger** > **Administrasjon** > **Systeminnstillinger** > **Forhåndsvisning** i [!INCLUDE[pn_microsoftcrm](pn-microsoftcrm.md)]-organisasjonen.  
  
 Ved å aktivere tekstanalysefunksjonen når du konfigurerer tekstanalysebaserte kunnskapsforslag i [!INCLUDE[pn_microsoftcrm](pn-microsoftcrm.md)], sendes saken og de relaterte enhetenes data til API-en for [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-tekstanalyse for å trekke ut nøkkelord/uttrykk. Ingen data lages med API-en for [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-tekstanalyse. Bare konfigurerte felt i kunnskapsartikkelkonfigurasjonen sendes til API-en for [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-tekstanalyse for å trekke ut termene. Den systemansvarlige eller tilpasseren har muligheten til å deaktivere kunnskapsartikkelkonfigurasjonen for å stoppe API-kall til API-en for [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-tekstanalyse. Tilpasseren kan også stoppe bruk av tekstanalysebaserte forslag ved å bytte tilbake til feltbaserte forslag i konfigurasjonen av saksenhetsskjema.  
  
 Ved å aktivere tekstanalysefunksjonen når du konfigurerer saksemneanalyse i [!INCLUDE[pn_microsoftcrm](pn-microsoftcrm.md)], sendes saken og de relaterte enhetenes data til API-en for [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-tekstanalyse for fastsettelse av emne. Ingen data lages med API-en for [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-tekstanalyse. Bare konfigurerte felt i konfigurasjonen av emnemodell sendes til API-en for [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-tekstanalyse for å trekke ut emnene. Den systemansvarlige eller tilpasseren har muligheten til å deaktivere emnemodellen for å foreta API-kall til [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-tekstanalyse.  
  
 Ved å aktivere tekstanalysefunksjonen når du konfigurerer forslag for lignende saker i [!INCLUDE[pn_microsoftcrm](pn-microsoftcrm.md)], hvis alternativet for avansert tekstanalyse er aktivert i likhetsregelen, sendes saken og de relaterte enhetenes data til API-en for [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-tekstanalyse for å trekke ut nøkkelord og uttrykk. Bare tekstfelt konfigurert i likhetsregelen sendes til API-en for [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-tekstanalyse. Ingen data lages med API-en for [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-tekstanalyse. Den systemansvarlige eller tilpasseren har muligheten til å deaktivere likhetsregelen for å stoppe API-kall til [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-tekstanalyse.  
  
 [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-komponenter og -tjenester som er involvert i tekstanalysebaserte funksjoner, er beskrevet i avsnittene nedenfor.  
  
 [!INCLUDE[cc_privacy_note_azure_trust_center](cc-privacy-note-azure-trust-center.md)]  
  
 [Azure API-app](https://azure.microsoft.com/services/app-service/api/)  
  
 [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] API-appen utløser nettjobbene som leser dataene fra [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)]-organisasjonen, og sender data til API-en for tekstanalyse for å foreta emneanalyse. [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] API-appen bruker nettjobb til å utføre den faktiske databehandlingen i bakgrunnen og skrive utdataene til[!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Blob Storage. Dataene lagres midlertidig i [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Blob Storage. Til slutt slettes dataene fra [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Storage når fastsettelse av emne er foretatt.  
  
 [Azure Scheduler](https://azure.microsoft.com/services/storage/)  
  
 [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Scheduler brukes til å utløse en nettjobb på planlagt basis for å utføre eneanalyse. Bare byggeplanen for emnemodell deles med planleggeren.  
  
 [Azure Table](https://azure.microsoft.com/services/storage/)  
  
 [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Table brukes for kommunisering av modellversjon og organisasjonskontekst mellom [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] API-appen og nettjobben.  
  
 [Azure Blob-lagring](https://azure.microsoft.com/services/storage/)  
  
 Nettjobber lagrer data midlertidig i [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Blob Storage, og sletter dem med en gang Logic App-pipelinen er ferdig utført.  
  
 [API for Azure-tekstanalyse](https://www.microsoft.com/cognitive-services/en-us/text-analytics-api)  
  
 API-en for [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-tekstanalyse sendes data basert på felt som er konfigurert i aktive felt for kunnskapssøk eller emnemodellkonfigurasjonen eller likhetsregalkonfigurasjonen. Saksenhetsfeil, for eksempel tittel og beskrivelse, og beskrivelsesfeltet i relaterte notater og aktiviteter, blir konfigurert i konfigurasjonen av feltet for kunnskapsbasesøk.  
  
 [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)] Relevanssøk  
  
 Du kan bruke relevanssøk hvis det er aktivert av en administrator, til å finne like poster for saker. Felt for tekstsamsvar og felt for nøyaktig treff som brukes i likhetsregelen, brukes til å starte API-en for relevanssøk. Se i det tekniske innholdet for [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)]-relevanssøk for detaljer om datahåndtering.