Ved å aktivere de innebygde Power BI-flisene og -instrumentbordene når en bruker innebygger en Power BI-flis eller -instrumentbord, brukes denne brukerens [!INCLUDE[pn_azure_active_directory](pn-azure-active-directory.md)]-godkjenningstoken for [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)] til å godkjenne med Power BI-tjenesten med en implisitt tilgang, noe som gir en sømløs opplevelse med "enkel pålogging" for sluttbrukeren.  
  
 En administrator kan deaktivere innebygging av Power BI-fliser og -instrumentbord når som helst for å stoppe bruken av [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)]-godkjenningstoken for godkjenning med Power BI-tjeneste. Alle eksisterende fliser eller instrumentbord vil stoppe gjengivelse for sluttbrukeren.  
  
 [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-komponenten eller -tjenesten som er involvert i innebygging av Power BI-fliser, er beskrevet i delen nedenfor.  
  
 [!INCLUDE[cc_privacy_note_azure_trust_center](cc-privacy-note-azure-trust-center.md)]  
  
 [Azure Active Directory](https://azure.microsoft.com/services/active-directory/)  
  
 Denne tjenesten inneholder godkjenningstoken som er utvekslet med Power BI-tjeneste for API- og grensesnittgodkjenning.