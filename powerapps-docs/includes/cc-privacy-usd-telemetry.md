---
ms.openlocfilehash: 7b58f302f694246564d7073a954ecd53b1b25361
ms.sourcegitcommit: 982cab99d84663656a8f73d48c6fae03e7517321
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/28/2019
ms.locfileid: "67456907"
---
[!INCLUDE[pn_unified_service_desk](pn-unified-service-desk.md)]-funksjonen Bidra til å forbedre sender informasjon om bruk av [!INCLUDE[pn_unified_service_desk](pn-unified-service-desk.md)], for eksempel informasjon om operativsystem, nettleser og programspesifikk informasjon om [!INCLUDE[pn_unified_service_desk](../includes/pn-unified-service-desk.md)] og [!INCLUDE[pn_unified_service_desk](pn-unified-service-desk.md)]-versjonen fra datamaskinen der du installerer klienten. [!INCLUDE[pn_unified_service_desk](pn-unified-service-desk.md)] sender informasjonen til [!INCLUDE[cc_Microsoft](cc-microsoft.md)] gjennom en sikker kobling, til Organisasjonsinnsikt, og den lagres i [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Table Storage.
  
> [!NOTE]
>  Organisasjonsinnsikt gir systemansvarlig for en [!INCLUDE[pn_crm_shortest](pn-crm-shortest.md)]-organisasjon en rask oversikt over hvordan organisasjonen brukes. Systemansvarlig kan vise de fleste aktive brukere, antall SDK-forespørsler som er startet, og antall som vises for SDK-brukere.
  
 En liste over [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-komponenter og -tjenester som er involvert i Unified Service Desk-funksjonen Bidra til å forbedre, vises nedenfor.  
  
> [!NOTE]
>  Hvis du vil mer informasjon om flere [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-tjenestetilbud, kan du se [Microsoft Azure Klareringssenter](https://azure.microsoft.com/support/trust-center/).  
  
 [Cloud Services](https://azure.microsoft.com/services/cloud-services/) REST-API for OrgInsights Data (nettrolle)  
  
 Denne nettrollen godtar forespørsler fra diagrammer som viser data i Organisasjonsinnsikt. API-en leser aggregerte data fra [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-tabeller og returnerer dem.  
  
 [Azure Blob Storage](https://azure.microsoft.com/services/storage/blobs/)  
  
 En [!INCLUDE[pn_crm_shortest](pn-crm-shortest.md)]-organisasjons telemetrirådata samles av overvåkingsagenten (som kjører på hver datamaskin med skaleringsgruppe) og lastes opp i Bond-format (binært format) til [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Blob Storage.  
  
 [Azure Table Storage](https://azure.microsoft.com/services/storage/tables/)  
  
 Telemetrirådata i [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Blob Storage aggregeres og lagres i Azure Table Storage, som leses av Cloud Service.  
  
 [Azure Active Directory](https://azure.microsoft.com/services/active-directory/)  
  
 Organisasjonsinnsikt bruker [!INCLUDE[pn_azure_active_directory](pn-azure-active-directory.md)]-tjenesten til å godkjenne nettjenester.  
  
 [Azure Service Bus](https://azure.microsoft.com/services/service-bus/)  
  
 Overvåkingsagenten oppretter og legger meldinger i kø når data lastes opp til [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Blob Storage. Disse meldingene velges av CMA-kanalen for å aggregere de opplastede dataene.