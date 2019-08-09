Funksjonen for å hjelpe med å forbedre [!INCLUDE[pn_unified_service_desk](pn-unified-service-desk.md)] sender bruksinformasjon for [!INCLUDE[pn_unified_service_desk](pn-unified-service-desk.md)], for eksempel operativsystemdetaljer, nettleserdetaljer, programspesifikk informasjon for [!INCLUDE[pn_unified_service_desk](../includes/pn-unified-service-desk.md)] og [!INCLUDE[pn_unified_service_desk](pn-unified-service-desk.md)]-versjonen fra datamaskinen du installerer klienten på. [!INCLUDE[pn_unified_service_desk](pn-unified-service-desk.md)] sender informasjonen til [!INCLUDE[cc_Microsoft](cc-microsoft.md)] via en sikker tilkobling til Organisasjonsinnsikt, og den lagres i [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Table Storage.
  
> [!NOTE]
>  Organisasjonsinnsikt gir systemansvarlig for en [!INCLUDE[pn_crm_shortest](pn-crm-shortest.md)]-organisasjon en kort oversikt over hvordan organisasjonen brukes. Systemansvarlig kan vise de mest aktive brukerne, antall SDK-forespørsler som initieres, og antallet som vises av SDK-brukere.
  
 En liste over [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-komponenter og -tjenester som er involvert i funksjonen for å hjelpe å forbedre Unified Service Desk, vises nedenfor.  
  
> [!NOTE]
>  Hvis du vil ha mer informasjon om flere tjenestetilbud for [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)], kan du gå til [klareringssenteret for Microsoft Azure](https://azure.microsoft.com/support/trust-center/).  
  
 [Cloud Services](https://azure.microsoft.com/services/cloud-services/) OrgInsights Data REST API (webrolle)  
  
 Denne webrollen godtar forespørsler fra diagrammene som viser data i Organisasjonsinnsikt. API-et leser samlede data fra [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-tabeller og returnere dem.  
  
 [Azure Blob-lagring](https://azure.microsoft.com/services/storage/blobs/)  
  
 En [!INCLUDE[pn_crm_shortest](pn-crm-shortest.md)]-organisasjons telemetrirådata samles inn av overvåkingsagenten (som kjører på alle datamaskiner i skaleringsgruppen), og de lastes opp i Bond-format (binært format) til [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Blob-lagring.  
  
 [Azure Table Storage](https://azure.microsoft.com/services/storage/tables/)  
  
 Telemetrirådata i [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Blob-lagring samles og lagres i Azure Table Storage, som lese av Cloud Service.  
  
 [Azure Active Directory](https://azure.microsoft.com/services/active-directory/)  
  
 Organisasjonsinnsikt bruker [!INCLUDE[pn_azure_active_directory](pn-azure-active-directory.md)]-tjenesten til å godkjenne webtjenester.  
  
 [Azure Service Bus](https://azure.microsoft.com/services/service-bus/)  
  
 Overvåkingsagenten oppretter og setter meldinger i kø når den laster opp data til [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Blob-lagring. Disse meldingene velges av CMA-pipen for å samle dataene som er lastet opp.