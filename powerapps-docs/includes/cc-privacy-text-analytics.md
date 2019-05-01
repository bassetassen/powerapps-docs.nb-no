---
ms.openlocfilehash: 80997689e9d4ebca8eb4809cc3e94dab549482b5
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/23/2019
ms.locfileid: "61577555"
---
Ved å aktivere tekstanalysefunksjonen, aktiverer du avhengige funksjoner i [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)], som utnytter API-en for tekstanalyse i [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Cognitive Services til å levere avansert innsikt. Disse avhengige funksjonene er:  
  
-   Kunnskapsforslag  
  
-   Saksemneanalyse  
  
-   Lignende saksforslag  
  
 En administrator kan aktivere tekstanalysefunksjonen under **Innstillinger** > **Administrasjon** > **Systeminnstillinger** > **Forhåndsvisning**-fanen i [!INCLUDE[pn_microsoftcrm](pn-microsoftcrm.md)]-organisasjonen.  
  
 Ved å aktivere tekstanalysefunksjonen når du konfigurerer kunnskapsforslag som er basert på tekstanalyse i [!INCLUDE[pn_microsoftcrm](pn-microsoftcrm.md)], sendes saken og tilknyttede enhetsdata til API-en for tekstanalyse i [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] for å trekke ut nøkkelord eller -uttrykk. Ingen data lagres med API-en for tekstanalyse i [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]. Det er bare konfigurerte felt i konfigurasjonen av kunnskapsartikkelen som sendes til API-en for tekstanalyse i [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] for å trekke ut vilkårene. Administrator eller tilpasser har mulighet til å deaktivere konfigurasjonen av kunnskapsartikkelen for å slutte å foreta API-kall til API-en for tekstanalyse i [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]. Tilpasseren kan også slutte å bruke forslag som er basert på tekstanalyse, ved å bytte tilbake til feltbaserte forslag i konfigurasjonen av saksenhetsskjema.  
  
 Ved å aktivere tekstanalysefunksjonen når du konfigurerer saksemneanalyse i [!INCLUDE[pn_microsoftcrm](pn-microsoftcrm.md)], sendes saken og tilknyttede enhetsdata til API-en for tekstanalyse i [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] for fastsettelse av emne. Ingen data lagres med API-en for tekstanalyse i [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]. Det er bare konfigurerte felt i emnemodellen som sendes til API-en for tekstanalyse i [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] for å trekke ut emner. Administrator eller tilpasser har mulighet til å deaktivere emnemodellen for å slutte å foreta API-kall for tekstanalyse i [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)].  
  
 Ved å aktivere tekstanalysefunksjonen når du konfigurerer forslag for lignende saker i [!INCLUDE[pn_microsoftcrm](pn-microsoftcrm.md)], og det avanserte alternativet for tekstanalyse er aktivert i likhetsregelen, sendes saken og tilknyttede enhetsdata til API-en for tekstanalyse i [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] for å trekke ut nøkkelord og -uttrykk. Det er bare tekstfelt som er konfigurert i likhetsregelen, som sendes til API-en for tekstanalyse i [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]. Ingen data lagres med API-en for tekstanalyse i [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]. Administrator eller tilpasser har mulighet til å deaktivere likhetsregelen for å slutte å foreta API-kall for tekstanalyse i [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)].  
  
 [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-komponenter og -tjenester som er involvert i funksjoner som er basert på tekstanalyse, beskrives i de følgende inndelingene.  
  
 [!INCLUDE[cc_privacy_note_azure_trust_center](cc-privacy-note-azure-trust-center.md)]  
  
 [Azure API-app](https://azure.microsoft.com/services/app-service/api/)  
  
 [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] API-appen utløser nettjobber som leser data fra [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)]-organisasjonen og sender data til API-en for tekstanalyse for å foreta emneanalyse. [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] API-appen bruker en nettjobb til å gjøre den faktiske databehandlingen i bakgrunnen, og skrive utdata til [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Blob Storage. Dataene lagres midlertidig i [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Blob Storage. Til slutt slettes data fra [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Storage, når fastsettelse av emne er gjort.  
  
 [Azure Scheduler](https://azure.microsoft.com/services/storage/)  
  
 [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Scheduler brukes til å utløse planlagte nettjobber for å utføre emneanalyse. Det er bare byggplanen for emnet som deles med planleggeren.  
  
 [Azure Table](https://azure.microsoft.com/services/storage/)  
  
 [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Table brukes til å kommunisere modellversjonen og organisasjonskonteksten mellom [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] API-appen og nettjobben.  
  
 [Azure Blob Storage](https://azure.microsoft.com/services/storage/)  
  
 Nettjobber lagrer data midlertidig i [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Blob Storage og sletter dem når datasamlebåndet for logikkappen er ferdig med å kjøre.  
  
 [API for tekstanalyse i Azure](https://www.microsoft.com/cognitive-services/en-us/text-analytics-api)  
  
 API-en for tekstanalyse i [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] er data som er sendt basert på felt som er konfigurert i aktive kunnskapssøkefelt eller konfigurasjonen av emnemodellen eller likhetsregelen. Saksenhetsfelt, for eksempel tittel og beskrivelse samt beskrivelsesfeltet i relaterte notater og aktiviteter, er for eksempel konfigurert i kunnskapssøkefeltkonfigurasjonen.  
  
 Relevanssøk for [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)]  
  
 Du kan bruke Relevanssøk til å finne lignende saksposter hvis dette er aktivert av en administrator. Tekstsamsvarsfelt og nøyaktige samsvarsfelt som brukes i likhetsregelen, brukes til å starte Relevanssøk-API-en. Hvis du vil ha informasjon om håndtering av data, kan du se på det tekniske innholdet for Relevanssøk for [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)].