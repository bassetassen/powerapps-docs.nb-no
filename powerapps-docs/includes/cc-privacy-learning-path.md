Ved å aktivere funksjonen for læringsforløp, aktiverer du at statisk HTML-kode, bilder og skript lagres på [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Content Delivery Network (CDN). I tillegg vil alt dynamisk innhold som vises, bli lagret i [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Redis-hurtigbuffer, som brukes til å forhåndsbufre fra [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] SQL Database.  
  
 En administrator kan aktivere og deaktivere bruk av funksjonen for læringsforløp i en [!INCLUDE[pn_crm_online_shortest](pn-crm-online-shortest.md)]-forekomst, ved å bruke innstillingen Aktiver veiledningshjelp i [!INCLUDE[pn_microsoftcrm](pn-microsoftcrm.md)]-organisasjonen.  
  
 [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-komponenter og -tjenester som er involvert i funksjonen for læringsforløp, er beskrevet i avsnittene nedenfor.  
  
> [!NOTE]
>  Hvis du vil ha mer informasjon om flere tjenestetilbud for Azure, kan du gå til [klareringssenteret for Microsoft Azure](https://azure.microsoft.com/support/trust-center/).  
  
 [Cloud Services](https://azure.microsoft.com/services/cloud-services/)  
  
 **Kjøretid for læringsforløp (webrolle)**  
  
 Dette er webprogrammet som leverer innholdet til brukere.  
  
 **Tjeneste for læringsforløp (arbeiderrolle)**  
  
 Arbeiderrollen er ansvarlig for å behandle dataene fra [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] SQL Database og hurtigbufre dem i [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Redis-hurtigbuffer.  
  
 [Azure SQL Database](https://azure.microsoft.com/services/sql-database/)  
  
 Læringsforløp bruker SQL Database til å lagre:  
  
-   Innhold  
  
-   Metadata for innhold  
  
-   Metadata for system  
  
 [Azure Blob-lagring](https://azure.microsoft.com/services/storage/)  
  
 HTML-koden, bilder, [!INCLUDE[pn_JavaScript](pn-javascript.md)] og CSS lagres alle i Blob-lagring for [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)].  
  
 [Azure-innholdsleveringsnettverk (CDN)](https://azure.microsoft.com/services/cdn/)  
  
 Læringsforløp bruker [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-innholdsleveringsnettverk til å levere statisk innhold til evalueringens kjøretid, for eksempel HTML-kode, bilder, [!INCLUDE[pn_JavaScript](pn-javascript.md)] og CSS.  
  
 [Azure Active Directory](https://azure.microsoft.com/services/active-directory/)  
  
 Læringsforløp bruker [!INCLUDE[pn_azure_active_directory](pn-azure-active-directory.md)]-tjenesten for å godkjenne webtjenester spesielt for utformeren. Utformeren vises ikke for kunder og partnere. Godkjenningen er derfor bare i [!INCLUDE[cc_Microsoft](cc-microsoft.md)]-domenet.  
  
 [Azure Redis-hurtigbuffer](https://azure.microsoft.com/services/cache/)  
  
 Læringsforløp bruker [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Redis-hurtigbufferen til å hurtigbufre dynamisk innhold som vi leverer til brukere.  
  
 [Azure-trafikkstyring](https://azure.microsoft.com/services/traffic-manager/)  
  
 Læringsforløp bruker Traffic Manager til å forbedre tilgjengeligheten for viktige programmer ved å overvåke dine [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-områder eller eksterne områder og tjenester, og automatisk omdirigere brukere til den nye plasseringen når det oppstår en feil.  
  
 [Azure Resource Manager](https://azure.microsoft.com/features/resource-manager/)  
  
 Læringsforløp bruker [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Resource Manager til å distribuere CDN, Redis-hurtigbuffer, SQL Database og skytjenester som ressursgrupper, slik at de er i en konsekvent tilstand og kan distribueres gjentatte ganger.