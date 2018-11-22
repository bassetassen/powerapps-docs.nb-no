Ved å aktivere Kundens mening for Dynamics 365, sendes definisjonen for undersøkelsen til Azure og lagres i Azure Storage når du publiserer en undersøkelse i Dynamics 365. Når en respondent sender en undersøkelse (ved åpning av koblingen til invitasjonsundersøkelsen som er sendt til ham eller henne via e-post), lagres undersøkelsessvarene midlertidig i Azure Service Bus og hentes og lagres deretter i Dynamics 365. Når svarene er lagret i Dynamics 365, slettes de fra Azure.  
  
 Legg merke til at det er mulig å ta med Dynamics 365-data, for eksempel kundenavn, produktnavn, saksnummer osv. i en evaluering (i evalueringselementer som spørsmål og svar) ved gjengivelse av en evaluering for en respondent. Når en undersøkelsesinvitasjonskobling er generert, sendes disse Dynamics 365-dataene ut av Dynamics 365 og lagres i Azure SQL-databasen i bytte mot en identifikator som brukes i undersøkelsesinvitasjonskoblingen. Denne identifikatoren brukes til å vise Dynamics 365-data i undersøkelsen etter at undersøkelsen er åpnet ved hjelp av undersøkelsesinvitasjonskoblingen. Identifikatorene i undersøkelseskoblingen som sendes via e-post til respondenten, lagres i respondentens e-postsystem.  
  
 En administrator kan aktivere Kundens mening for funksjonen Dynamics 365 ved å installere den som en løsning i Dynamics 365-organisasjonen. I tillegg kan en administrator deretter deaktivere funksjonen ved å avinstallere denne løsningen fra Dynamics 365-organisasjonen.  
  
 Azure-komponenter og -tjenester som er involvert i Kundens mening for funksjonen Dynamics 365, er beskrevet i avsnittene nedenfor.  
  
 Obs! Hvis du vil ha mer informasjon om flere Azure-tjenestetilbud, kan du gå til klareringssenteret ([https://azure.microsoft.com/support/trust-center/](https://azure.microsoft.com/support/trust-center/)) for Microsoft Azure.  
  
 **Cloud Services** ([https://azure.microsoft.com/services/cloud-services/](https://azure.microsoft.com/services/cloud-services/))  
  
 **Designer Service (webrolle)**  
  
 Tilbyr flere webtjenester for kommunikasjon mellom en Dynamics 365-organisasjon og Dynamics 365 Azures multi-instanskomponenter for Kundens mening.  Undersøkelser publiseres og lagres for eksempel i Azure Blob-lagring.  Undersøkelsessvar hentes fra en Azure Service Bus-kø og returneres for å beholdes i Dynamics 365-organisasjonen.  Alle forespørsler godkjennes mot Azure Active Directory.  
  
 **Kjøretid for undersøkelse (webrolle)**  
  
 Dette er webprogrammet som leverer undersøkelsene til svarpersonene.  Sendte undersøkelsessvar lagres midlertidig i en Azure Service Bus-kø før de behandles og hentes av en asynkron Dynamics 365-tjeneste.  
  
 **Svarbehandling (arbeiderrolle)**  
  
 Denne arbeiderollen er ansvarlig for å behandle råundersøkelser til gyldige undersøkelsessvar som kan opprettes i Dynamics 365.  
  
 ***Overføringsbehandling (arbeiderrolle)**   Denne arbeiderollen er ansvarlig for å behandle de gyldige undersøkelsessvarene og oppdatere dem som oppføringer for Dynamics 365-enheten. 
 
 **Azure Key Vault** ([https://azure.microsoft.com/services/key-vault/](https://azure.microsoft.com/services/key-vault/))  
  
 Alle skytjenester lagrer konfigurasjonsdata i Azure Key Vault.  Organisasjons- og leierdata lagres i SQL Azure.  
  
 **Azure SQL Database** ([https://azure.microsoft.com/services/sql-database/](https://azure.microsoft.com/services/sql-database/))  
  
 Kundens mening for Dynamics 365 bruker SQL Azure til å lagre:  
  
-   Overførte data  
  
-   Undersøkelsesmetadata  
  
-   Organisasjonsdata (leierdata)  
  
 **Azure Blob-lagring** ([https://azure.microsoft.com/services/storage/](https://azure.microsoft.com/services/storage/))  
  
 Undersøkelsesdefinisjoner og delvis fullførte (lagrede) svar lagres i Azure Blob-lagring.  
  
 **Azure Content Delivery Network (CDN)** ([https://azure.microsoft.com/services/cdn/](https://azure.microsoft.com/services/cdn/))  
  
 Kundens mening for Dynamics 365-løsningen bruker Azure Content Delivery Network til å levere statisk innhold til undersøkelsens kjøretid som bilder (inkluderer opplastede bilder som kundelogoer), JavaScript og CSS.  
  
 **Azure Active Directory** ([https://azure.microsoft.com/services/active-directory/](https://azure.microsoft.com/services/active-directory/))  
  
 Kundens mening for Dynamics 365-løsningen bruker Azure Active Directory Service til å godkjenne webtjenester.  
  
 **Azure Service Bus** ([https://azure.microsoft.com/services/service-bus/](https://azure.microsoft.com/services/service-bus/))  
  
 Meldinger som opprettes når en evaluering vises eller sendes, lagres midlertidig i organisasjonens (leierens) Azure Service Bus-kø til Azure-arbeiderrollen overfører evalueringssvarene til en organisasjons Dynamics 365-forekomst og bevarer dem som oppføringer i Dynamics 365-enheten.
