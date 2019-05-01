---
ms.openlocfilehash: 3840a097743111f6ae89e65426a366207f8364d9
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/23/2019
ms.locfileid: "61574918"
---
Ved å aktivere læreprogram-funksjonen, static html, aktiverer du at bilder og skripter lagres på [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Content Delivery Network (CDN). I tillegg lagres alt dynamisk innhold som vises, i [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Redis Cache, som brukes til å forhåndsbufre fra [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] SQL-databasen.  
  
 En administrator kan aktivere og deaktivere bruken av Læreprogram-funksjonen i en [!INCLUDE[pn_crm_online_shortest](pn-crm-online-shortest.md)]-forekomst ved å bruke innstillingen Aktiver veiledningshjelp i [!INCLUDE[pn_microsoftcrm](pn-microsoftcrm.md)]-organisasjonen.  
  
 [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-komponenter og -tjenester som er involvert med Læreprogram-funksjonen, beskrives i de følgende inndelingene.  
  
> [!NOTE]
>  Hvis du vil ha mer informasjon om flere Azure-tjenestetilbud, kan du se [Microsoft Azure Klareringssenter](https://azure.microsoft.com/en-us/support/trust-center/).  
  
 [Cloud Services](https://azure.microsoft.com/en-us/services/cloud-services/)  
  
 **Læreprogram-kjøretid (nettrolle)**  
  
 Dette er nettprogrammet som leverer innholdet til brukerne.  
  
 **Læreprogram-tjeneste (arbeiderrolle)**  
  
 Arbeiderrollen er ansvarlig for behandling av data fra [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] SQL Database og bufre dem inn i [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Redis Cache.  
  
 [Azure SQL Database](https://azure.microsoft.com/en-us/services/sql-database/)  
  
 Læreprogrammet bruker SQL Database til å lagre:  
  
-   Innhold  
  
-   Metadata for innhold  
  
-   Systemmetadata  
  
 [Azure Blob Storage](https://azure.microsoft.com/en-us/services/storage/)  
  
 HTML, bilder, [!INCLUDE[pn_JavaScript](pn-javascript.md)] og CSS lagres i [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Blob Storage.  
  
 [Azure Content Delivery Network  (CDN)](https://azure.microsoft.com/en-us/services/cdn/)  
  
 Læreprogrammet bruker [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Content Delivery Network til å levere statisk innhold til kjøretiden for undersøkelsen, for eksempel HTML, bilder, [!INCLUDE[pn_JavaScript](pn-javascript.md)] og CSS.  
  
 [Azure Active Directory](https://azure.microsoft.com/en-us/services/active-directory/)  
  
 Læreprogrammet bruker [!INCLUDE[pn_azure_active_directory](pn-azure-active-directory.md)] Service til å godkjenne nettjenester spesifikt for designeren. Utformingsverktøyet vises for øyeblikket ikke for kunder og partnere. Derfor er godkjenningen bare innenfor [!INCLUDE[cc_Microsoft](cc-microsoft.md)]-domenet.  
  
 [Azure Redis Cache](https://azure.microsoft.com/en-us/services/cache/)  
  
 Læreprogrammet bruker [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Redis Cache til å bufre dynamisk innhold som vi leverer til brukerne.  
  
 [Azure Traffic Manager](https://azure.microsoft.com/en-us/services/traffic-manager/)  
  
 Læreprogrammet bruker Traffic Manager til å forbedre tilgjengeligheten til viktige programmer ved å overvåke [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] eller eksterne områder og tjenester, og automatisk dirigere brukere til nye plasseringer hvis det skulle oppstå feil.  
  
 [Azure Resource Manager](https://azure.microsoft.com/en-us/features/resource-manager/)  
  
 Læreprogrammet bruker [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Resource Manager til å distribuere CDN, Redis Cache, SQL Database og skytjenester som ressursgrupper, slik at de er i en konsekvent tilstand og kan distribueres gjentatte ganger.