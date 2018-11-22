Ved å installere [!INCLUDE[pn_connected_field_service_msdyn365](pn-connected-field-service-msdyn365.md)], når du oppgir informasjon om [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-abonnementet, blir de obligatoriske [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-ressursene (oppført nedenfor) tatt i bruk, og din forekomst av [!INCLUDE[pn_dynamics_crm_online](pn-dynamics-crm-online.md)] sender data (for eksempel kommandoer og registreringer) til [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] for å aktivere IoT-aktiverte scenarier som registrerer enheter og deretter sender kommandoer til og mottar kommandoer fra de registrerte enhetene. En administrator kan avinstallere Connected Field Service for å fjerne funksjonaliteten og deretter gå til [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-portalen for å administrere relaterte [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-servicer som det ikke lenger er behov for.  
  
 [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-komponenter og -tjenester som er involvert i Connected Field Service-funksjonalitet, beskrives i avsnittene nedenfor.  
  
 [!INCLUDE[cc_privacy_note_azure_trust_center](cc-privacy-note-azure-trust-center.md)]  
  
 [Service Bus-kø](https://azure.microsoft.com/documentation/articles/service-bus-dotnet-get-started-with-queues/)  
  
 Her finner du en kø for både inngående og utgående meldinger (kommandoer) mellom [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)] og [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]. Når et IoT-varsel sendes til [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)], eller en kommando sendes fra [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)] til IoT Hub-en, blir den lagt i kø her.  
  
 [Logiske apper](https://azure.microsoft.com/services/logic-apps/)  
  
 Her finner du en orkestreringsservice som bruker en [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)]-kobling og en køkobling. [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)]-koblinger brukes til å konstruere enheter som er spesifikke for [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)], og køkontakter brukes til å avspørre køen.  
  
 [Stream Analytics](https://azure.microsoft.com/services/stream-analytics/)  
  
 Her finner du en fullstendig administrert hendelsesbehandlingsmotor i sanntid som du kan bruke til å få mer detaljert innsikt fra data. Stream Analytics gjør det enkelt å konfigurere analytiske beregninger i sanntid for data som strømmes fra enheter, sensorer, nettsteder, sosiale medier, apper, infrastruktursystemer og mer. Den fungerer som en trakt for å sende utvalgte IoT-varsler til [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)].  
  
 [IoT-hub](https://azure.microsoft.com/services/iot-hub/)  
  
 Connected Field Services bruker IoT Hub-en til å administrere tilstanden til registrerte enheter og aktiva. I tillegg sender IoT Hub-en kommandoer og varslinger til tilkoblede enheter, og sporer meldingslevering med bekreftelseskvitteringer. Enhetsmeldinger sendes på en varig måte for å legge til rette for periodisk tilkoblede enheter.  
  
 **Simulator**  
  
 Dette er en testnettapp for å emulere enheten som sender kommandoer til eller mottar kommandoer fra IoT Hub-en.  
  
 [Azure SQL Database](https://azure.microsoft.com/services/sql-database/)  
  
 Connected Field Service bruker SQL [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] til å lagre enhetsmeldinger for senere bruk av PowerBI til å vise statusen for enheter i [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)].  
  
 [Azure Blob-lagring](https://azure.microsoft.com/services/storage/)  
  
 Spørringer som Stream Analytics bruker, lagres i [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Blob-lagring.