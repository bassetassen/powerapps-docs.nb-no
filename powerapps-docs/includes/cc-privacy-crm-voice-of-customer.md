---
ms.openlocfilehash: 3fb3961dc88033a44c60c4b6f09124c7c38a11bf
ms.sourcegitcommit: ad203331ee9737e82ef70206ac04eeb72a5f9c7f
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/18/2019
ms.locfileid: "67212779"
---
Når du publiserer en undersøkelse fra Dynamics 365, vil definisjonen for undersøkelsen sendes til Azure og lagres i Azure Storage ved å aktivere Voice of the Customer for Dynamics 365. Når en respondent sender en undersøkelse (ved å åpne koblingen for invitasjonen til en undersøkelse sendt til ham eller henne via e-post), lagres svarene på undersøkelsen midlertidig i Azure Service Bus, og deretter hentes og lagres de i Dynamics 365. Svarene blir slettet fra Azure etter at svarene er lagret i Dynamics 365.  
  
 Vær oppmerksom på at det er mulig å inkludere Dynamics 365-data, for eksempel kundenavn, produktnavn, saksnummer osv. i en undersøkelse (i undersøkelseselementer som spørsmål, svar osv.) ved gjengivelse av en undersøkelse for en respondent. Når en kobling for en invitasjon til en undersøkelse genereres, vil disse dataene for Dynamics 365 sendes ut av Dynamics 365, og lagres i Azure SQL Database i bytte mot en identifikator som brukes i koblingen for invitasjonen til undersøkelsen. Denne identifikatoren brukes til å vise Dynamics 365-dataene i undersøkelsen etter at undersøkelsen er åpnet ved hjelp av koblingen for invitasjonen til undersøkelsen. Identifikatorene i koblingen til undersøkelsen, som sendes via e-post til en respondent, er lagret i e-postsystemet til respondenten.  
  
 En administrator kan aktivere Voice of the Customer for Dynamics 365-funksjonen ved å installere den som en løsning i Dynamics 365-organisasjonen. En administrator kan i tillegg deretter deaktivere funksjonen ved å avinstallere denne løsningen fra Dynamics 365-organisasjonen.  
  
 Azure-komponenter og -tjenester som er involvert i Voice of the Customer for Dynamics 365-funksjonen, beskrives i følgende deler.  
  
 Debetnotaforslag Hvis du vil ha mer informasjon om flere Azure-tilbud, kan du se[https://azure.microsoft.com/support/trust-center/](https://azure.microsoft.com/support/trust-center/)Microsoft Azure klarerings Senter ().  
  
 **Cloud Services** ([https://azure.microsoft.com/services/cloud-services/](https://azure.microsoft.com/services/cloud-services/))  
  
 **Utformer-tjenesten (Nettrolle)**  
  
 Dette gir flere nettjenester for kommunikasjon mellom en Dynamics 365-organisasjon og komponenter med flere leiere for Voice of the Customer for Dynamics 365 Azure.  Undersøkelser blir for eksempel publisert og lagret til Azure Blob Storage.  Svar på undersøkelser er hentet fra en Azure Service Bus-kø, og returneres for å opprettholdes i Dynamics 365-organisasjonen.  Alle forespørsler er godkjent mot Azure Active Directory.  
  
 **Kjøretid for undersøkelsen (nettrolle)**  
  
 Dette er nettprogrammet som leverer undersøkelsene til respondentene.  Innsendt undersøkelse lagres midlertidig på en Azure Service Bus-kø før den blir behandlet ved henting av en asynkron tjeneste for Dynamics 365.  
  
 **Svarbehandler (arbeidesrolle)**  
  
 Denne arbeidsrollen er ansvarlig for å behandle rå fullførte undersøkelser til gyldige svar på undersøkelser som kan opprettes i Dynamics 365.  
  
 **Push-prosessor (arbeider rolle)**   Denne arbeider rollen er ansvarlig for å behandle de gyldige undersøkelses svarene og oppdateringen som Dynamics 365-enhets poster. 
 
 **Azure Key Vault** ([https://azure.microsoft.com/services/key-vault/](https://azure.microsoft.com/services/key-vault/))  
  
 Alle skytjenester lagrer konfigurasjonsdata i Azure Key Vault.  Organisasjonen, leierdata lagres i SQL Azure.  
  
 **Azure SQL Database** ([https://azure.microsoft.com/services/sql-database/](https://azure.microsoft.com/services/sql-database/))  
  
 Voice of the Customer for Dynamics 365 bruker SQL Azure til å lagre:  
  
-   Overført data  
  
-   Metadata for undersøkelse  
  
-   Organisasjonsdata (leier)  
  
 **Azure Blob Storage** ([https://azure.microsoft.com/services/storage/](https://azure.microsoft.com/services/storage/))  
  
 Definisjoner for undersøkelse og delvis fullførte (lagret) svar, lagres til Azure Blob lager.  
  
 **Azure Content Delivery Network (CDN)** ([https://azure.microsoft.com/services/cdn/](https://azure.microsoft.com/services/cdn/))  
  
 The Voice of the Customer for Dynamics 365-løsningen bruker Azure Content Delivery Network til å behandle statisk innhold til kjøretiden for undersøkelsen, som bilder (inkludert opplastede bilder, for eksempel kundelogoer), JavaScript og CSS.  
  
 **Azure Active Directory** ([https://azure.microsoft.com/services/active-directory/](https://azure.microsoft.com/services/active-directory/))  
  
 The Voice of the Customer for Dynamics 365-løsningen bruker Azure Active Directory-tjenesten til å godkjenne nettjenester.  
  
 **Azure Service Bus** ([https://azure.microsoft.com/services/service-bus/](https://azure.microsoft.com/services/service-bus/))  
  
 Meldinger som opprettes når en undersøkelse vises eller sendes blir midlertidig lagret i organisasjonens (leierens) Azure Service Bus-kø, frem til Azure-arbeidsrollen legger svarene fra undersøkelsen i en Dynamics 365-forekomst for en organisasjon, og opprettholder dem som enhetsoppføringer for Dynamics 365.
