---
ms.openlocfilehash: 509ad3f5b1b94378b2c6fd7661510b7aef0e3a23
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/23/2019
ms.locfileid: "61574931"
---
Ved å aktivere redigering av læringsforløp for en[!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)]-organisasjon så lagres læringsforløpsinnhold (publisert eller kladd) som ble opprettet av brukere (med de riktige rettighetene), i [!INCLUDE[pn_Azure_SQL_Database_long](pn-azure-sql-database-long.md)]. Hvis du aktiverer denne funksjonen så kan [!INCLUDE[pn_azure_cloud_services](pn-azure-cloud-services.md)] i tillegg hente følgende data tilknyttet en [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)]-organisasjon:  
  
-   Liste over organisasjoner i leieren  
  
-   [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)]-klienter og gjeldende nettleser-/OS-konfigurasjon for sluttbrukere  
  
-   Bruksdata for sluttbrukere – som tid brukt på læringsforløp eller registrerte klikk  
  
-   Samlede brukerdata – plassering, sikkerhetsrolle, brukerspråk  
  
-   Samlede brukerdata – plassering, sikkerhetsrolle, brukerspråk  
  
-   Ordrett tilbakemelding fra sluttbrukere  
  
 En systemansvarlig kan aktivere (og kan senere deaktivere) redigering av læringsforløp gjennom en innstilling på **Generelt**-fanen i dialogboksen **Systeminnstillinger**.  
  
 [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-komponenter og -tjenester som er involvert med funksjonen redigering av læringsforløp, beskrives i de følgende inndelingene.  
  
 [!INCLUDE[cc_privacy_note_azure_trust_center](cc-privacy-note-azure-trust-center.md)]  
  
 [Cloud Services](https://azure.microsoft.com/en-us/services/cloud-services/)  
  
 **Nettjeneste**  
  
 Nettjenesten står for kontrollene som gjengis på klienten av kjøretid for læringsforløp. Nettjenesten støtter også Designer API, som brukes av redigering av læringsforløp. Disse kontrollene lagres av tjenesten på [!INCLUDE[pn_Azure_SQL_Database_long](pn-azure-sql-database-long.md)].  
  
 **Kompilator (arbeidsrolle)**  
  
 Kompilatorrollen står for publiseringen av en kontroll til en publiseringsgruppe. Kompilatoren bruker køen til å lagre meldinger om publiseringsjobben. Resultatene lagres i [!INCLUDE[pn_Azure_SQL_Database_long](pn-azure-sql-database-long.md)].  
  
 [Azure SQL Database](https://azure.microsoft.com/en-us/services/sql-database/)  
  
 Læringsforløp bruker [!INCLUDE[pn_Azure_SQL_Database_long](pn-azure-sql-database-long.md)] til å lagre:  
  
-   kontroller som opprettes ved bruk av læringsforløp.  
  
-   konfigurasjonsrelatert redigering av læringsforløp.  
  
 [Azure Active Directory](https://azure.microsoft.com/en-us/services/active-directory/)  
  
 Læringsforløp bruker [!INCLUDE[pn_azure_active_directory](pn-azure-active-directory.md)] til å godkjenne nettjenesten.  
  
 [Azure Traffic Manager](https://azure.microsoft.com/en-us/services/traffic-manager/)  
  
 Læringsforløp bruker [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Traffic Manager til å fordele belastningen til nettjenesten for tilgjengelighet og ytelse.  
  
 [Azure Storage-kø](https://azure.microsoft.com/en-us/services/storage/)  
  
 [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Storage-køen brukes til å koordinere kommunikasjon mellom nettjenesten og kompilatorrollen.  
  
 [Azure Blob Storage](https://azure.microsoft.com/en-us/services/storage/)  
  
 Læringsforløp bruker [!INCLUDE[pn_azure_blob_storage](pn-azure-blob-storage.md)] til å lagre det statiske innholdet ([!INCLUDE[pn_JavaScript](pn-javascript.md)] på klientsiden, bilder, CSS-innhold).  
  
 [Azure Content Delivery Network (CDN)](https://azure.microsoft.com/en-us/services/cdn/)  
  
 CDN brukes til å hurtigbufre det statiske innholdet på klientsiden ([!INCLUDE[pn_JavaScript](pn-javascript.md)], bilder og CSS-filer) for å betjene dem fra et globalt CDN-nettverk.