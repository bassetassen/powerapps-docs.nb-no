Ved å installere og bruke [!INCLUDE[pn_fieldservice_mobile_app_long](pn-fieldservice-mobile-app-long.md)]-mobilappen på en mobilenhet, godtar brukere overføring av brukerorganisasjonens tilordnede ID og tilordnede sluttbruker-ID, og enhets-ID til Microsoft og Resco.net, Inc. i forbindelse med formidling av tjenestene samt kontroll av programvaren at er forskriftsmessig lisensiert.  
&nbsp;<br />
Hvis du bruker [!INCLUDE[pn_fieldservice_mobile_app_long](pn-fieldservice-mobile-app-long.md)]-mobilappen til å koble [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)] til [!include[](../includes/tn-glympse.md)]-tjenester, samtykker brukere til overføring av kundedata til [!include[](../includes/tn-glympse.md)] ved å installere eller bruke programvaren, basert på tjenester for å aktivere sanntidsplassering. Denne funksjonen krever at en autorisert bruker eller administrator integrerer og konfigurerer organisasjonen eksisterende [!include[](../includes/tn-glympse.md)]-forretningsforbindelse for å arbeide med [!include[](../includes/pn-dynamics-crm.md)]. Bruk av [!include[](../includes/tn-glympse.md)]-tjenester er underlagt vilkårene og personvernerklæringen gjelder for [!include[](../includes/tn-glympse.md)]-forretningsforbindelsen din.  
&nbsp;<br />
Hvis brukere bruker appen til å koble til [!include[](../includes/pn-microsoft-dynamics.md)] CRM (online) eller [!include[](../includes/pn-crm-online.md)], ved å installere appen, samtykker brukere til overføringen av sin organisasjons tilordnede ID og tilordnede sluttbruker-ID, og enhets-ID-en til Microsoft i forbindelse med å aktivere tilkoblinger på tvers av flere enheter, eller forbedre [!include[](../includes/pn-microsoft-dynamics.md)] CRM (online), [!include[](../includes/pn-crm-online.md)] eller appen.  
&nbsp;<br />
**Stedsdata.** Hvis brukere ber om og aktiverer stedsbaserte tjenester eller funksjoner i appen, kan det hende appen samler inn og bruker nøyaktige data om stedet. Presise stedsdata kan være GPS-data, og i tillegg data som identifiserer mobilmaster og Wi-Fi-aktiveringspunkt i nærheten. Appen kan sende stedsdata til [!include[](../includes/pn-microsoft-dynamics.md)] CRM eller [!include[](../includes/pn-dynamics-crm.md)]. Appen kan sende stedsdata til [!include[](../includes/pn-bing-maps.md)] og andre tredjepartstilordnede tjenester, for eksempel Google Maps og [!include[](../includes/tn-apple.md)] Maps, som fungerer ved å behandle brukerens stedsdata i appen. Brukere kan deaktivere plasseringsbaserte tjenester eller funksjoner eller deaktivere appens tilgang til brukerens plassering ved å deaktivere plasseringstjenesten eller deaktivere appens tilgang til plasseringstjenesten. Brukernes benyttelse av [!include[](../includes/pn-bing-maps.md)] styres av [!include[](../includes/pn-bing-maps.md)] sluttbrukervilkårene, som er tilgjengelige på [https://go.microsoft.com/?linkid=9710837](https://go.microsoft.com/?linkid=9710837), og [!include[](../includes/pn-bing-maps.md)] personvernerklæringen, som er tilgjengelig på [https://go.microsoft.com/fwlink/?LinkID=248686](https://go.microsoft.com/fwlink/?LinkID=248686). Brukernes benyttelse av tilordningstjenester fra tredjeparter, og informasjonen brukerne angir til dem, er underlagt deres tjenestespesifikke sluttbrukervilkår og personvernerklæringer. Brukere bør se nøye gjennom disse andre sluttbrukervilkårene og personvernerklæringene.  
&nbsp;<br />
Appen kan inneholde koblinger til andre Microsoft-tjenester og tredjepartstjenester som har retningslinjer for personvern og sikkerhet som kan være forskjellige fra [!include[](../includes/pn-microsoft-dynamics.md)] CRM eller [!include[](../includes/pn-dynamics-crm.md)].  HVIS BRUKERE SENDER DATA TIL ANDRE MICROSOFT-TJENESTER ELLER TREDJEPARTSTJENESTER, ER SLIKE DATA UNDERLAGT DE RESPEKTIVE PERSONVERNERKLÆRINGENE. For å unngå misforståelser: data som er delt utenfor [!include[](../includes/pn-microsoft-dynamics.md)] CRM eller [!include[](../includes/pn-dynamics-crm.md)] som ikke er dekket av brukernes [!include[](../includes/pn-microsoft-dynamics.md)] CRM eller [!include[](../includes/pn-dynamics-crm.md)]-avtaler eller det aktuelle klareringssenteret for [!include[](../includes/pn-microsoft-dynamics.md)]. Microsoft oppfordrer brukere til å lese gjennom disse andre personvernerklæringene.  
&nbsp;<br />
Når du aktiverer [!INCLUDE[pn_fieldservice_mobile_app_long](pn-fieldservice-mobile-app-long.md)]-mobilappen på en mobilenhet med posisjonstjenester aktivert, sendes stedsdata i sanntid til [!INCLUDE[pn_bing_maps](pn-bing-maps.md)] og lagres i [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)]. Brukerne bes gi tillatelse til flyten av stedsdata i sanntid under installasjonen eller ved bruk av appen Field Service Mobile. Hvis brukeren vil deaktivere flyten av stedsdata i sanntid fra enheten, må han/hun deaktivere posisjonstjenesten på enheten eller avinstallere programmet.  
&nbsp;<br />
Stedsdataene i sanntid som sendes av appen Field Service Mobile, brukes til å støtte følgende scenarioer:  

 -  Til å vise posisjonen til brukerens kunder. Data om brukerens gjeldende posisjon sendes til kartleggingsleverandøren som kontekst for kartet som gjengis av leverandøren og vises i appen Field Service Mobile.  

 -  Til å opprette og oppdatere en brukers tidsplan. Data om brukerens gjeldende posisjon videresendes til Field Service-funksjonen i [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)] for å opprette og oppdatere en brukers tidsplan. For eksempel for å tilordne en oppgave til den nærmeste teknikeren.  
  
Hvis appen Field Service Mobile aktiveres på en mobilenhet, sendes informasjon om bruken av mobilappen, f.eks. programfeil, til Microsoft gjennom en sikker kobling til Organisasjonsinnsikt, og lagres i [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Table Storage.  
  
**Obs!** Organisasjonsinnsikt gir systemansvarlig for en [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)]-organisasjon en kort oversikt over hvordan organisasjonen brukes. Systemadministratoren kan vise de mest aktive brukerne, antall SDK-forespørsler som initieres, og antallet som vises av SDK-brukere.  
  
En liste over [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-komponenter og -tjenester som er involvert i funksjonen for å hjelpe å forbedre [!INCLUDE[pn_unified_service_desk](pn-unified-service-desk.md)], vises nedenfor.  
  
[!INCLUDE[cc_privacy_note_azure_trust_center](cc-privacy-note-azure-trust-center.md)]  
  
[Cloud Services](https://azure.microsoft.com/services/cloud-services/)  
  
**OrgInsights Data REST API (webrolle)**  
  
Denne webrollen godtar forespørsler fra diagrammene som viser data i Organisasjonsinnsikt. API-et leser samlede data fra [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-tabeller og returnere dem.  
  
[Azure Blob-lagring](https://azure.microsoft.com/services/storage/blobs/)  
  
En overvåkingsagent (som kjører på alle datamaskiner i skaleringsgruppen) samler inn [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)]-organisasjons telemetrirådata, og de lastes opp i Bond-format (binært format) til [!INCLUDE[pn_azure_blob_storage](pn-azure-blob-storage.md)].  
  
[Azure Table Storage](https://azure.microsoft.com/services/storage/tables/)  
  
Telemetrirådata i [!INCLUDE[pn_azure_blob_storage](pn-azure-blob-storage.md)] samles og lagres i [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Table Storage, som leses av skytjenesten.  
  
[Azure Active Directory](https://azure.microsoft.com/services/active-directory/)  
  
Organisasjonsinnsikt bruker [!INCLUDE[pn_azure_active_directory](pn-azure-active-directory.md)]-tjenesten til å godkjenne webtjenester.  
  
[Azure Service Bus](https://azure.microsoft.com/services/service-bus/)  
  
Overvåkingsagenten oppretter og setter meldinger i kø når den laster opp data til [!INCLUDE[pn_azure_blob_storage](pn-azure-blob-storage.md)]. CMA-pipen plukker opp disse meldingene for å samle dataene som er lastet opp.