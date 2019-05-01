---
ms.openlocfilehash: 864bb7bde775f88cdf43ba5c453bd1ff02f81b85
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/23/2019
ms.locfileid: "61577523"
---
Når du aktiverer relasjonsanalyse, en innebygd intelligens funksjon, sendes og lagres              [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)]-kundedata, inkludert identifiserbar informasjon, i              [!INCLUDE[pn_customerinsight_full](pn-customer-insights-full.md)]. Det er en tjeneste som kjører i Azure, og formålet med dette er å beregne relasjons-KPI-er mellom             [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)]-brukere og -kunder. Dataene lagres også midlertidig i              [!INCLUDE[pn_azure_service_fabric](pn-azure-service-fabric.md)] og behandles for ekstra utdata, som relasjonstilstander og trender. Informasjonen returneres deretter til              [!INCLUDE[pn_customerinsight_short](pn-customer-insights-short.md)] og              [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)].  
  
 En systemansvarlig kan aktivere Relasjonsanalyse-funksjonen ved å installere den som en løsning i              [!INCLUDE[pn_microsoftcrm](pn-microsoftcrm.md)]-organisasjonen. En administrator kan i tillegg deretter deaktivere funksjonen ved å avinstallere denne løsningen fra [!INCLUDE[pn_microsoftcrm](pn-microsoftcrm.md)]-organisasjonen.  
  
 Ved at du aktiverer              [!INCLUDE[pn_Exchange](pn-exchange.md)]-data som en datakilde, sender du              [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)]-kundedata, inkludert identifiserbar informasjon, fra              [!INCLUDE[pn_customerinsight_full](pn-customer-insights-full.md)] til              [!INCLUDE[pn_Exchange_Online](pn-exchange-online.md)]. Formålet med dette er å  samle inn ekstra data, som brukes for KPI-beregninger og for å opprette andre analyser.  For at du skal kunne aktivere denne funksjonen, må              [!INCLUDE[pn_Office_365](pn-office-365.md)][!INCLUDE[pn_Exchange](pn-exchange.md)]-administratoren også godta en separat samtykkeerklæring i              [!INCLUDE[pn_Exchange](pn-exchange.md)]-programmet.  Når begge administratorene har gitt sitt samtykke gjennom aktuelle produkter, samler             [!INCLUDE[pn_Exchange](pn-exchange.md)] inn metadata om e-post og møter. Dette lagres i              [!INCLUDE[pn_customerinsight_full](pn-customer-insights-full.md)] og brukes for å forbedre KPI-beregningene og potensielt andre analyser som bestemmes av systemansvarlig for              [!INCLUDE[pn_customerinsight_full](pn-customer-insights-full.md)]. Hvis du deaktiverer              [!INCLUDE[pn_Exchange](pn-exchange.md)]-data som en datakilde i Relasjonsanalyse-konfigurasjonen, fjernes ikke              [!INCLUDE[pn_Exchange](pn-exchange.md)]-data fra              [!INCLUDE[pn_customerinsight_full](pn-customer-insights-full.md)].  Du kan BARE fjerne              [!INCLUDE[pn_Exchange](pn-exchange.md)]-data i              [!INCLUDE[pn_customerinsight_full](pn-customer-insights-full.md)] direkte fra              [!INCLUDE[pn_customerinsight_full](pn-customer-insights-full.md)].  
  
 [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-komponenter og -tjenester som er involvert i relasjonsanalyser, beskrives i de følgende inndelingene.  
  
 [!INCLUDE[cc_privacy_note_azure_trust_center](cc-privacy-note-azure-trust-center.md)]  
  
 **[!INCLUDE[pn_customerinsight_full](pn-customer-insights-full.md)]**  
  
 [!INCLUDE[pn_customerinsight_short](pn-customer-insights-short.md)], en tjeneste som kjører i              [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)], lagrer              [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)]-data, inkludert identifiserbar informasjon om kunder. Formålet med dette er å beregne utdataene for Relasjonsanalyse-funksjonen. Forhåndsvisningen av [!INCLUDE[pn_customerinsight_short](pn-customer-insights-short.md)] er underlagt disse [tilleggsvilkårene for bruk for evalueringsfunksjonalitet](http://go.microsoft.com/fwlink/p/?LinkId=511446).  
  
 [Lær mer om forhåndsvisningen av Customer Insights](https://azure.microsoft.com/en-us/services/customer-insights/).  
  
 [Azure Service Fabric](https://azure.microsoft.com/services/service-fabric/)  
  
 [!INCLUDE[pn_azure_service_fabric](pn-azure-service-fabric.md)]brukes for å lagre              [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)]-data midlertidig, inkludert identifiserbar informasjon om kunder. Formålet med dette er å beregne utdataene for Relasjonsanalyse-funksjonen.