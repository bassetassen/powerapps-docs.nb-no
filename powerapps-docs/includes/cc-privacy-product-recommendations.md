---
ms.openlocfilehash: 1cdcb40245aae9a23ecb6d3392e412f8a60b95ba
ms.sourcegitcommit: ad203331ee9737e82ef70206ac04eeb72a5f9c7f
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/18/2019
ms.locfileid: "67212322"
---
Ved å aktivere funksjonen Produktanbefalinger når du bygger en anbefalingsmodell fra [!INCLUDE[pn_microsoftcrm](pn-microsoftcrm.md)], sendes de historiske transaksjonsdataene basert på konfigurerte handlekurvdataenheter og deres filter til [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)], de behandles i [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] og lagres midlertidig i [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-lagring, og til slutt sendes de til API-en for anbefalinger for Azure for å bygge maskinlæringsmodellen. Etter at modellen er bygget med API-en for anbefalinger for Azure, slettes data fra [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-lagring. Vær oppmerksom på at bare ID-er (konto-ID, produkt-ID, transaksjons-ID) sendes til [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] for å bygge anbefalingsmodellen.

En administrator kan aktivere funksjonen Produktanbefalinger under **Innstillinger** &gt; **Administrasjon** &gt; **Systeminnstillinger** &gt; **Forhåndsvisning**-fanen i [!INCLUDE[pn_microsoftcrm](pn-microsoftcrm.md)]-organisasjonen. Data sendes til API-en for anbefalinger for Azure bare når en anbefalingsmodell er bygget. Systemansvarlig kan slette den eksisterende modellen for å slette data som er delt med API-en for anbefalinger for Azure. Systemansvarlig kan i tillegg slette tilkoblingen til API-en for anbefalinger for Azure, slik at eventuelle anbefalingsmodeller ikke blir bygget i fremtiden.

[!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-komponenter og -tjenester som er involvert produktanbefalinger, beskrives i de følgende inndelingene.

[!INCLUDE[cc_privacy_note_azure_trust_center](cc-privacy-note-azure-trust-center.md)]

[Azure Logic Apps](https://azure.microsoft.com/services/app-service/logic/)

Dette gjør det mulig for datasamlebåndet å synkronisere produktkatalogen og transaksjonsdata med API-en for anbefalinger, for å bygge versjonen av anbefalingsmodellen. Datasamlebåndet kjøres som en multi-utleid tjeneste med flere API-apper for kommunikasjon mellom Dynamics 365-organisasjonen og API-en for anbefalinger. Logiske apper utløses fra [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)] med minimal kontekst, som modellversjon-ID og nettadressen til [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)]-organisasjonen. 

[Azure API-apper](https://azure.microsoft.com/services/app-service/api/)

Dette er nettprogrammene som utløser nettjobbene som leser data fra [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)]-organisasjonen, og som sender dataene til API-en for anbefalinger for å bygge anbefalingsmodellen. Det finnes tre API-apper og tilsvarende nettjobber - én for å lese produktdata, én for å lese transaksjonsdata og én for å bygge en anbefalingsmodell. API-apper bruker en nettjobb til å gjøre den faktiske databehandlingen i bakgrunnen, og skrive utdata til [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Blob Storage. Dataene lagres midlertidig i [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Blob Storage. Til slutt slettes data fra [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Storage så snart modellen er bygget.

[Azure Table](https://azure.microsoft.com/services/storage/tables/)

[!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Table brukes til å kommunisere modellversjonen og organisasjonskonteksten mellom API-appen og en nettjobb.

[Azure Blob Storage](https://azure.microsoft.com/services/storage/) 

Nettjobber lagrer data midlertidig i [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Blob Storage, og sletter dem når datasamlebåndet for logikkappen er ferdig med å kjøre.

[API-en for anbefalinger for Azure](https://www.microsoft.com/cognitive-services/en-us/recommendations-api) API-en for anbefalinger for Azure sendes med minimal datakontekst, som produkt-ID-er, transaksjons-ID-er og konto-ID-er, for å bygge anbefalingsmodellen. Data lagres med tjenesten API for anbefalinger, helt til en tilsvarende modellversjon finnes.
