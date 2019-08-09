Når du aktiverer Dynamics 365 Mobile Offline, lastes Dynamics 365 (online)-data bare ned til SQL Azure-databasen via Azure-skyen basert på enhetene du aktiverer for tilgjengelighet i frakoblet modus. Når en bruker kobler til Azure-skytjenesten fra en mobilapp ved hjelp av SQL Mobile-programmet med frakoblet funksjon, lastes det ned data i en lokal database på den mobile enheten. Overføring av data mellom SQL Azure-databasen i Azure-skyen og Dynamics 365-mobilappen med frakoblet funksjon, foregår via en sikker SSL-tilkobling. Til slutt lagres kundedataene i SQL Azure-databasen og på mobilenheten.  
  
 En administrator kan avgjøre om brukerne i organisasjonen har tillatelse til å koble fra med Microsoft Dynamics 365 Mobile Offline-appen ved hjelp av sikkerhetsroller og Dynamics CRM 365 Mobile-profiltilpassing. Dynamics 365-administratorer kan konfigurere hvilke enheter som lastes ned via synkronisering i frakoblet modus ved hjelp av innstillingen Synkroniseringsfiltre i dialogboksen Innstilling – Mobile Offline.  
  
 Legg merke til at data som er lagret i brukerens enhet, styres av kunden, ikke Microsoft. Administratoren har full kontroll over dataene som kan trekkes ut med sikkerhetsrollen eller enhetsnivåene for brukeren. Når dataene er trukket ut, etterlates imidlertid sikkerhetsgrensen fra Dynamics 365 Online.  
  
 En liste over Azure-komponenter og -tjenester som er involvert i funksjonen for Mobile Offline, vises nedenfor.  
  
 **Obs!** Hvis du vil ha mer informasjon om flere tjenestetilbud for Azure, kan du gå til [klareringssenteret for Microsoft Azure](https://azure.microsoft.com/support/trust-center/).  
  
 **Cloud Services (webrolle)**  
  
 Mobile Offline benytter to skytjenester, én for klargjøring og den andre for synkronisering av data.  
  
 Klargjøringstjenesten har en enkelt webrolle som leser meldinger fra tjenestebusskøen (SB) for ulike hendelser som kommer fra Dynamics 365, som klargjøring eller oppheving av klargjøring. Deretter behandles disse meldingene ved å opprette eller slette organisasjonsdatabaser og sende regelmessige arbeidselementer (meldinger) på SB-køen for datasynkronisering. Under denne prosessen leser og skriver konfigurasjonsdata fra filen CSCFG eller fra Dynamics 365 SW-API.  
  
 Datasynkroniseringstjenesten har to webroller. En holder skjemaet og dataene for oppsamlingsdatabasen synkronisert med en Dynamics 365-organisasjons metadata og data, mens den andre webrollen er for å kjøring av synkroniseringsserveren og behandling av klientens synkroniseringsforespørsler. Første webrolle behandler meldingene fra SB-køen for datasynkronisering for ulike organisasjoner og kontakter deretter Dynamics 365 for å få metadata og dataendringer før de lagres i oppsamlingsdatabasen. Det gjør også jobben med å konfigurere serveren for synkronisering med organisasjoner som kommer inn og ut av systemet og deres klientmodeller. Den andre webrollen kjører synkroniseringsserveren (uadministrert kode) til vertsadministrasjons- og synkroniseringsendepunkt. Administrasjonsendepunkt brukes av den andre webrollen til å sende konfigurasjonsdata. Endepunktet for synkronisering brukes av eksterne klienter (Dynamics 365 Mobile-appen) til å utføre datasynkronisering. I likhet med klargjøringstjenesten leser/skriver disse rollene konfigurasjonsdata fra CSCFG-filen eller fra API-et for Dynamics 365-programvaren.  
  
 **Kø**  
  
 Mobile Offline bruker Azure-køer for meldingsutveksling mellom Dynamics 365 og Azure. Den brukes til å vedlikeholde arbeidselementer som behandles av skytjenestene. Hver enkelt melding inneholder informasjon som organisasjons-ID-en, enhetsnavn for å synkronisere data og tilkoblingsstrengen for organisasjonens OData-endepunkt.  
  
 **SQL-database**  
  
 Mobile Offline bruker Azure SQL Storage for å lagre følgende:  
  
-   Data som replikeres fra Dynamics 365-organisasjoner og brukes til å behandle synkroniseringsforespørsler fra klienter.  
  
-   Konfigurasjonsdata som f.eks. tilkoblingsstrenger for organisasjonsdatabasen.  
  
 **Lagringsplass**  
  
 Mobile Offline bruker Azure Blob-lagring til å lagre logger og spor som er generert av skytjeneste.  
  
 **Active Directory-tjeneste**  
  
 Mobile Offline bruker Azure Active Directory-tjenesten til å godkjenne med andre tjenester, for eksempel Dynamics 365 eller SW API eller API-er for Azure-administrasjon.  
  
 **Azure DNS**  
  
 Mobile Offline bruker Azure DNS til å omadressere klientforespørsler basert på organisasjonsnavn, til riktige skytjenesteendepunkter.  
  
 **Azure virtual Network**  
  
 Et Azure Virtual Network (VNet)-nettverk er en representasjon av ditt eget nettverk i skyen. Dynamics 365-produktteamet kan kontrollere Azure-nettverksinnstillingene og definere adresseområder for DHCP, DNS-innstillinger, sikkerhetspolicyer og ruting.  
  
 **Azure Load Balancer**  
  
 Azure Load Balancer gir høy tilgjengelighet og nettverksytelse i programmene. Det er en Lag-4-belastningsfordeler (TCP, UDP) som distribuerer innkommende trafikk mellom sunne tjenesteforekomster i skytjenester eller virtuelle maskiner som er definert i et belastningsfordelingssett. Vi bruker det til å lastfordele endepunktene i en distribusjon.