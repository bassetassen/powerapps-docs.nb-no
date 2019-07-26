---
ms.openlocfilehash: 787ff9592604f9a9bce1929e4d429a39da5ec48a
ms.sourcegitcommit: 982cab99d84663656a8f73d48c6fae03e7517321
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/28/2019
ms.locfileid: "67456838"
---
Når du aktiverer Dynamics 365 mens du er frakoblet, lastes Dynamics 365 (online)-data til SQL Azure-databasen ved hjelp av Azure-skyen, basert på enhetene du aktiverer for tilgjengelighet i frakoblet modus. Når en bruker kobler til Azure Cloud-tjenesten fra en mobilapp med funksjon for frakoblet modus, lastes data ned fra SQL Azure-databasen til en lokal database på mobilenheten. Dataoverføring mellom SQL Azure-databasen på Azure-skyen og Dynamics 365-mobilappen med frakoblet funksjonen, skjer gjennom en sikker SSL-tilkobling. Til slutt lagres data i SQL Azure-databasen på mobilenheten.  
  
 En administrator bestemmer om brukerne i en organisasjon har tillatelse til å koble fra med Mobil Offline-programmet for Microsoft Dynamics 365 ved å bruke sikkerhetsroller og profiltilpassing for Dynamics 365 Mobile. Dynamics 365-administratorer kan konfigurere hvilke enheter som lastes ned via Frakoblet synkronisering, ved å bruke innstillingen synkroniseringsfiltre i dialogboksen for innstillinger for Mobile Offline.  
  
 Vær oppmerksom på at lagrede data på enheten til brukeren kontrolleres av brukeren, ikke av Microsoft. Administratoren har full kontroll over data som kan trekkes ut på brukerens sikkerhetsrolle eller enhetsnivåer. Når dataene er trukket ut, blir sikkerhetsgrensen fra Dynamics 365 Online igjen.  
  
 En liste over Azure-komponenter og -tjenester som er involvert med Mobile Offline-funksjonen, vises nedenfor.  
  
 **Merk:** Hvis du vil ha mer informasjon om flere Azure-tjenestetilbud, kan du se [Microsoft Azure Klareringssenter](https://azure.microsoft.com/support/trust-center/).  
  
 **Cloud Services (nettrolle)**  
  
 Mobile Offline benytter to skytjenester. Den ene er for klargjøring, og den andre er for datasynkronisering.  
  
 Klargjøringstjenesten har en enkelt nettrolle som leser meldinger fra Service Bus (SB)-køen for ulike hendelser som kommer fra Dynamics 365, for eksempel klargjøring eller fjerning av klargjøring. Den behandler disse meldingene ved å opprette eller slette organisasjonsdatabaser og sende regelmessige arbeidselementer (meldinger) på SB-køen for datasynkronisering. I løpet av denne prosessen leser eller skriver den konfigurasjonsdata, enten fra CSCFG-filen eller fra Dynamics 365 SW-API-en.  
  
 Datasynkroniseringstjenesten har to nettroller. Den ene holder skjema og data for den foreløpige databasen synkronisert med metadataene og dataene for Dynamics 365-organisasjonen, mens den andre nettrollen er for kjøring av synkroniseringsserveren og behandling av klientens synkroniseringsforespørsler. Den første nettrollen behandler meldinger fra SB-køen for datasynkronisering for ulike organisasjoner, og kontakter deretter Dynamics 365 for å få metadata- og dataendringene før lagring i den foreløpige databasen. Den konfigurerer også synkroniseringsserveren med organisasjoner som kommer inn og ut av systemet og klientmodellene deres. Den andre nettrollen kjører synkroniseringsserveren (ikke-administrert kode) for å drifte administrator- og synkroniseringsendepunkter. Administratorendepunktet brukes av den andre nettrollen til å sende konfigurasjonsdata. Synkroniseringsendepunktet brukes av eksterne klienter (Mobile-programmet for Dynamics 365) til å foreta datasynkronisering. På samme måte som med klargjøringstjenesten, leser eller skriver begge disse rollene konfigurasjonsdata enten fra CSCFG-filen eller fra Dynamics 365 SW-API-en.  
  
 **Kø**  
  
 Mobile Offline bruker Azure Queues for utveksling av meldinger mellom Dynamics 365 og Azure. Den brukes til å opprettholde arbeidselementer som behandles av skytjenester. Hver melding lagrer informasjon, for eksempel organisasjons-ID, enhetsnavn for der dataene skal synkroniseres og tilkoblingsstrengen for OData-endepunktet for organisasjonen.  
  
 **SQL Database**  
  
 Mobile Offline bruker Azure SQL Storage til å lagre:  
  
-   Data som er kopiert fra Dynamics 365-organisasjoner og for å betjene klientsynkroniseringsforespørsler.  
  
-   Konfigurasjonsdata, for eksempel tilkoblingsstrenger fra organisasjonsdatabasen.  
  
 **Lagring**  
  
 Mobile Offline bruker Azure Blob Storage til å lagre logger og spor som er generert av skytjenesten.  
  
 **Active Directory-tjeneste**  
  
 Mobile Offline bruker Azure Active Directory-tjenesten til å godkjenne med andre tjenester, for eksempel Dynamics 365 eller SW-API eller Azure Management-API-er.  
  
 **Azure DNS**  
  
 Mobile Offline bruker Azure DNS til å omadressere klientforespørsler, basert på organisasjonsnavn, til de korrekte endepunktene for skytjenestene.  
  
 **Azure Virtual Network**  
  
 Et virtuelt Azure-nettverk (VNet) er en representasjon av ditt eget nettverk i skyen. Dynamics 365-produktteamet kan kontrollere Azure-nettverksinnstillingene og definere DHCP-adresseblokker, DNS-innstillinger, sikkerhetspolicyer og ruting.  
  
 **Azure Load Balancer**  
  
 Azure Load Balancer leverer høy tilgjengelighet og nettverksytelse til programmene dine. Det er en Layer 4 Load Balancer (TP UDP), som distribuerer innkommende trafikk blant sikre tjenesteforekomster i skytjenester eller virtuelle maskiner som er definert i et belastningsfordelingssett. Vi bruker den til å fordele belastningen til endepunktene i en distribusjon.