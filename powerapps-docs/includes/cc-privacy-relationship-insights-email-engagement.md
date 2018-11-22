Ved å aktivere E-postengasjement, som er en funksjon i Innebygd intelligens, når en e-post merket med innstillingen **Følg**, sendes fra [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)], blir informasjon om samhandlinger med e-posten av mottakere samlet inn og lagret i [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] for å beregne KPI-er for  mottakeraktivitet og samhandlinger for "fulgte" e-poster.  
  
 En systemadministrator aktiverer E-postengasjement ved å klargjøre funksjonen fra fanen **E-postengasjement** i Innebygd intelligens. Administratorer kan deretter deaktivere E-postengasjement i organisasjonen fra noden **Konfigurasjon av intelligens** under **Innstillinger**.  
  
 Når funksjonen er deaktivert, kan ikke e-poster som sendes fra [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)], følges verken fra brukergrensesnittet eller programmatisk. I tillegg blir ikke data for mottakersamhandling lenger samlet inn for sendte e-poster merket med innstillingen **Følg**. Data som tidligere ble samlet inn, blir værende i [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] og blir tilgjengelige igjen hvis funksjonen aktiveres på nytt i organisasjonen. Data beholdes i 90 dager etter at kunder sier opp abonnementet hos Microsoft. [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)]-brukere kan også deaktivere funksjonen Innebygd intelligens - E-postengasjement per kontakt eller per kundeemne ved å endre innstillingen **Følg e-post** under **Kontaktinnstillinger**.  
  
 [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-komponenter og -servicer som er involvert i funksjonen E-postengasjement, er beskrevet nedenfor.  
  
 [!INCLUDE[cc_privacy_note_azure_trust_center](cc-privacy-note-azure-trust-center.md)]  
  
 **[!INCLUDE[pn_azure_storage_account](pn-azure-storage-account.md)]**  
  
 Funksjonen E-postengasjement bruker [!INCLUDE[pn_azure_storage_account](pn-azure-storage-account.md)] til å lagre e-postsamhandlingsblober midlertidig.