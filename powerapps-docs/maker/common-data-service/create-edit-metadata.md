---
title: Enheter og metadata i Common Data Service for apper | MicrosoftDocs
description: Lær om enheter og metadata i Common Data Service for apper
ms.custom: ''
ms.date: 05/30/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
author: Mattp123
ms.assetid: 88b18946-474c-4c94-8e4c-27532f930757
caps.latest.revision: 28
ms.author: matp
manager: kvivek
ms.openlocfilehash: ef2f92865205fa7c97ada356edc70ac69a637e0f
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/08/2018
ms.locfileid: "39697841"
---
# <a name="entities-and-metadata-in-common-data-service-for-apps"></a>Enheter og metadata i Common Data Service for apper

Common Data Service for apper er laget slik at du raskt og enkelt kan opprette en datamodell for programmet. Normalt trenger du ikke å tenke på noen av detaljene rundt metadata som introduseres i dette emnet. Men hvis du ønsker å utvikle en dypere forståelse om hvordan apper som bruker CDS for apper fungerer, eller du evaluerer hva som er mulig, kan det være nyttig å forstå metadataene som brukes av CDS for apper.

*Metadata* betyr data om data. CDS for apper inneholder en fleksibel plattform. Det er nemlig relativt enkelt å redigere definisjonene av dataene som miljøet skal bruke. ICDS for apper er metadataene en samling av enheter. Enheter beskriver datatypene som lagres i databasen.  Hver enhet samsvarer med en databasetabell, og hvert felt (også kjent som attributt) i en enhet representerer en kolonne i den tabellen. Enhetsmetadata er det som kontrollerer de postene du kan opprette, og hvilke handlinger som kan utføres for dem. Når du bruker tilpassingsverktøyene til å opprette eller redigere enheter, felter og enhetsrelasjoner, redigerer du disse metadataene. 
  
Ulike klienter som brukes til å samhandle med dataene i miljøet, avhenger av enhetsmetadataene, og de tilpasser seg mens du endrer metadataene. Men disse klientene er også avhengig av annen data for å kontrollere hvilke visuelle elementer som skal vises, eventuell egendefinert logikk som skal tas i bruk, og hvordan ta i bruk sikkerhet. Disse systemdataene lagres også i enheter, men selve enhetene er ikke tilgjengelig for tilpassing.

Du kan lære om standardenheter, attributter, og enhetsrelasjoner som inkluderes som standard i CDS for apper, ved å gå gjennom [enhetsreferansen](/powerapps/developer/common-data-service/reference/about-entity-reference).

> [!TIP]
> Utformingsprogrammene som er tilgjengelig for å redigere metadata, kan ikke vise alle detaljene fra metadataene. Du kan installere en modelldrevet app med navnet **Metadata Browser**. Ved bruk av appen kan du vise alle egenskapene for enheter og metadata i systemet. Mer informasjon: [Bla gjennom metadataene for miljøet](https://docs.microsoft.com/dynamics365/customer-engagement/developer/browse-your-metadata).
  
<a name="BKMK_CreateNewOrUseExistingMetadata"></a>

## <a name="create-new-metadata-or-use-existing-metadata"></a>Opprette nye metadata eller bruke eksisterende?

CDS for apper leveres med en antall standardenheter som støtter kjernefunksjonene til forretningsprogrammer. Data om kundene eller potensielle kunder skal for eksempel lagrer ved bruk av kontoen eller kontaktenhetene.  
  
Hver av disse enhetene inneholder også et antall felter som representerer vanlige data, som systemet muligens må lagre for den respektive enheten.  
  
For de fleste organisasjonene er det til din fordel å bruke standardenheter og -attributter til de tiltenkte formålene. 
  
Hvis du installerer en løsning, kan du forvente at løsningsutvikleren har dratt nytte av standardenhetene og -attributtene. Hvis du oppretter en ny standardenhet som erstatter en systemenhet eller -attributt, kan det hende at de tilgjengelige løsningene ikke fungerer for organisasjonen din.  
  
På grunn av dette anbefaler vi at du ser etter og bruker de tilgjengelige standardenhetene, feltene og enhetsrelasjonene når dette oppfyller behovene for organisasjonen din. Hvis de ikke oppfyller behovene og ikke kan redigeres for å oppnå dem, bør du evaluere om det er nødvendig å opprette en ny enhet, et nytt felt eller enhetsrelasjon. 

<!--  Can we say this yet? 
    
> [!NOTE]
> The [Common Data Model](/powerapps/common-data-model/overview) will provide a capability to add additional standard entities. 

-->

Husk at du kan endre visningsnavnet for en enhet slik at det stemmer overens med terminologien organisasjonen bruker. Det er for eksempel vanlig at man endrer visningsnavnet på kontoenheten til *Firma* eller navnet på kontaktenheten til *Enkeltperson*. Dette kan gjøres for enheter eller attributter uten å endre virkemåten til enheten. Hvis du vil ha mer informasjon om å endre navnet på enheter, kan du se [Endre navnet på en enhet](edit-entities.md#change-the-name-of-an-entity).
  
Du kan ikke slette standardenheter, felter eller enhetsrelasjoner. De regnes som en del av systemløsningen, og hver organisasjon forventes å ha dem. Hvis du ønsker å skjule en standardenhet, endrer du sikkerhetsrollerettighetene for organisasjonen for å fjerne leserettighetene for enheten. Dette fjerner enheten fra de fleste delene av programmet. Hvis det finnes et systemfelt du ikke trenger, fjerner du det fra skjemaet og eventuelle visninger som bruker det. Endre **Søkbar**-verdien i feltet og definisjonene av enhetsrelasjonen, slik at de ikke vises i Avansert søk. 
  
<a name="BKMK_LimitationsOnMetadata"></a>   

## <a name="limitations-on-creating-metadata-items"></a>Begrensninger for oppretting av metadataelementer  

Det er en grense for hvor mange enheter du kan opprette. Du finner informasjon om det maksimale antallet på siden **[Innstillinger](../model-driven-apps/advanced-navigation.md#settings)** > **Administrasjon** > **Ressurser i bruk**. Hvis du trenger flere egendefinerte enheter, kontakter du kundestøtte. Denne øvre grensen kan justeres.  
  
Det er en øvre grense med tanke på antallet felter du kan opprette i hver enheter. Denne grensen er basert på de tekniske begrensningene på mengden av data som kan lagres i en rad i en databasetabell. Det er vanskelig å oppgi et bestemt tall, fordi hver felttype kan bruke forskjellige plassmengder. Den øvre grensen avhenger av den totale plassen som brukes av alle feltene for enheten.  
  
De fleste oppretter ikke nok egendefinerte felter til å nå grensen, men hvis du planlegger å legge til flere hundre egendefinerte felter i en enhet, bør du vurdere om dette er det beste valget. Beskriver alle feltene du planlegger å legge til, egenskapene for en post for den enheten? Forventer du virkelig at folk som bruker organisasjonen, klarer å administrere et skjema som inkluderer så mange felter? Antallet felter du legger til i et skjema, øker datamengden som må transformeres hver gang en post redigeres. Dette vil påvirke ytelsen til systemet. Ta hensyn til disse faktorene når du legger til egendefinerte felter i en enhet.  
  
Alternativsettfelter har et sett med alternativer som vises i en rullegardinlistekontroll i et skjema, eller i en nedtrekksmeny når du bruker Avansert søk. Miljøet kan støtte tusenvis av alternativer i et alternativsett, men du bør ikke anse dette som den øvre grensen. Brukervennlighetsstudier har vist at folk har problemer med å bruke et system der en rullegardinlistekontroll gir et stort antall alternativer. Bruk alternativsettfelt for å definere kategorier for dataene. Ikke bruk alternativsett-felter til å velge kategorier som faktisk representerer separate dataelementer. Du kan for eksempel heller opprette en enhet som lagrer referanser til hver produsent og bruke et oppslagsfelt i stedet for et alternativsett, i stedet for å opprettholde et alternativsettfelt som lagrer hundrevis av mulige produsenter av en type utstyr.  
  
## <a name="next-steps"></a>Neste trinn 

[Opprett eller rediger enheter (posttyper)](create-edit-entities.md)<br />
[Opprett og rediger relasjoner mellom enheter](create-edit-entity-relationships.md)

