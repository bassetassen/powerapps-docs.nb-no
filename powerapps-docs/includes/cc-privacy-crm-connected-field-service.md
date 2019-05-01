---
ms.openlocfilehash: ce9db35844f46e9779055ec30dcba0f9459c3a16
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/23/2019
ms.locfileid: "61575526"
---
Ved å installere [!INCLUDE[pn_connected_field_service_msdyn365](pn-connected-field-service-msdyn365.md)], distribueres, når du angir [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-abonnementsinformasjonen din, de nødvendige [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-ressursene (oppført nedenfor), og [!INCLUDE[pn_dynamics_crm_online](pn-dynamics-crm-online.md)]-forekomsten sender data (for eksempel kommandoer og registreringer) til [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] for å aktivere IoT-aktiverte scenarioer som registrerer enheter, og sender og får deretter kommandoer til de registrerte enhetene. En administrator kan avinstallere tilkoblet felttjeneste for å fjerne funksjonen og deretter navigere til [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-portalen for å administrere eventuelle relaterte [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-tjenester som ikke lenger er nødvendige.  
  
 [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-komponenter og -tjenester som er involvert med tilkoblet felttjeneste-funksjonen, beskrives i de følgende inndelingene.  
  
 [!INCLUDE[cc_privacy_note_azure_trust_center](cc-privacy-note-azure-trust-center.md)]  
  
 [Service Bus-kø](https://azure.microsoft.com/documentation/articles/service-bus-dotnet-get-started-with-queues/)  
  
 Dette er en kø for både innkommende og utgående meldinger (kommandoer) som flyter mellom [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)] og [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]. Når et IoT-varsel sendes til [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)], eller en kommando sendes fra [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)] til IoT-huben, legges de i kø her.  
  
 [Logic Apps](https://azure.microsoft.com/services/logic-apps/)  
  
 Dette er en tjeneste for iverksetting, som bruker en [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)]-kobling og en køkobling. [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)]-koblinger brukes til å konstruere enheter som er spesifikke for [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)], og køkoblinger brukes for avspørring av køen.  
  
 [Stream Analytics](https://azure.microsoft.com/services/stream-analytics/)  
  
 Dette gir en fullstendig administrert motor for hendelsesbehandling i sanntid, som avdekker dyp innsikt fra data. Stream Analytics gjør det enkelt å konfigurere analyseberegninger i sanntid på datastrømming fra enheter, sensorer, nettsteder, sosiale medier, programmer, infrastruktursystemer med mer. Den fungerer som en trakt som sender selektive IoT-varsler til [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)].  
  
 [IoT Hub](https://azure.microsoft.com/services/iot-hub/)  
  
 Tilkoblede felttjenester bruker IoT Hub til å administrere tilstanden til de registrerte enhetene og ressursene. I tillegg sender IoT Hub kommandoer og varslinger til tilkoblede enheter og sporer levering av meldinger med mottaksbekreftelse. Enhetsmeldinger sendes på en robust måte for å ta høyde for enheter som bare periodevis er tilkoblet.  
  
 **Simulator**  
  
 Dette er en testnettapp som emulerer enheten som sender eller mottar kommandoer fra IoT-huben.  
  
 [Azure SQL Database](https://azure.microsoft.com/services/sql-database/)  
  
 Tilkoblet felttjeneste bruker SQL [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] til å lagre livstegnsmeldinger for enheten, for senere bruk av PowerBI til å vise statusen til enhetene i [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)].  
  
 [Azure Blob Storage](https://azure.microsoft.com/services/storage/)  
  
 Spørringer som brukes av Stream Analytics, lagres i [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Blob Storage.