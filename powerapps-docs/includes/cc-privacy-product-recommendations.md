Ved å aktivere funksjonen Produktanbefalinger når du bygger en anbefalingsmodell i [!INCLUDE[pn_microsoftcrm](pn-microsoftcrm.md)], blir de historiske transaksjonsdataene i konfigurerte kurvdataenheter og i filtrene sendt til [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] og behandlet i [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] og lagret midlertidig i [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Storage, og til slutt sendt til API for Azure-anbefalinger for å bygge maskinlæringsmodellen. Etter at modellen er bygd med API for Azure-anbefalinger, slettes data fra[!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Storage. Vær oppmerksom på at bare ID-er (forretningsforbindelses-ID, produkt-ID, transaksjons-ID) sendes til [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] for å bygge anbefalingsmodellen.

En administrator kan aktivere funksjonen for produktanbefalinger under kategorien **Innstillinger** &gt; **Administrasjon** &gt; **Systeminnstillinger** &gt; **Forhåndsvisning** i [!INCLUDE[pn_microsoftcrm](pn-microsoftcrm.md)]-organisasjonen. Data sendes bare til API for Azure-anbefalinger når en anbefalingsmodell er bygget. Systemansvarlig har muligheten til å slette den eksisterende modellen for å slette data som deles med API for Azure-anbefalinger. I tillegg kan systemansvarlig slette tilkoblingen til API for Azure-anbefalinger for å stoppe bygging av anbefalingsmodeller i fremtiden.

[!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-komponenter og -tjenester som er involvert i funksjonen for produktanbefalinger, er beskrevet i avsnittene nedenfor.

[!INCLUDE[cc_privacy_note_azure_trust_center](cc-privacy-note-azure-trust-center.md)]

[Azure Logic Apps](https://azure.microsoft.com/services/app-service/logic/)

Dette tilbyr den ordnede data-pipeline som kan brukes til å synkronisere produktkatalog og transaksjonsdata med API for anbefalinger å bygge anbefalingsmodellversjonen. Denne pipeline fungerer som en tjeneste med flere leiere med flere API-apper for kommunikasjon mellom en Dynamics 365-organisasjon og API for anbefalinger. Logic Apps utløses fra [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)] med minimal kontekst, for eksempel en ID for modellversjon og URL-adressen til [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)]-organisasjonen. 

[Azure API Apps](https://azure.microsoft.com/services/app-service/api/)

Dette er nettprogrammene som utløser nettjobbene fra [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)]-organisasjonen og sender data til API for anbefalinger for å bygge anbefalingsmodellen. Det er tre API-apper og tilsvarende nettjobber – én for lesing av produktdata, én for lesing av transaksjonsdata og én for bygging av en anbefalingsmodell. API-apper bruker nettjobb til å utføre den faktiske databehandlingen i bakgrunnen og skrive utdataene til [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Blob Storage. Dataene lagres midlertidig i [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Blob Storage. Til slutt slettes dataene fra [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Storage når modellen er bygd.

[Azure Table](https://azure.microsoft.com/services/storage/tables/)

[!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Table brukes for kommunisering av modellversjon og organisasjonskontekst mellom API-appen og en nettjobb.

[Azure Blob-lagring](https://azure.microsoft.com/services/storage/) 

Dataene lagres midlertidig i [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Blob Storage etter nettjobber, og slettes med en gang Logic App-pipelinen er ferdig utført.

[API for Azure-anbefalinger](https://www.microsoft.com/cognitive-services/en-us/recommendations-api) API for Azure-anbefalinger sendes med produkt-ID-er, transaksjons-ID-er og forretningsforbindelses-ID-er med minimale data som skal brukes til å bygge anbefalingsmodellen. Data lagres med tjenesten for API for anbefalinger til det finnes en tilsvarende modellversjon.
