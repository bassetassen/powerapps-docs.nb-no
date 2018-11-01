---
title: Enheter og metadata i Common Data Service for Apps | MicrosoftDocs
description: Finn ut mer om enheter og metadata i Common Data Service for Apps
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
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="entities-and-metadata-in-common-data-service-for-apps"></a>Enheter og metadata i Common Data Service for Apps

Common Data Service for Apps er utformet slik at du kan raskt og enkelt opprette en datamodell for programmet. Du trenger vanligvis ikke bry deg med noen av detaljene om metadata som introduseres i dette emnet. Men hvis du ønsker å få en dypere forståelse av hvordan apper som bruker CDS for Apps, fungerer, eller du evaluerer hva som er mulig, kan en forståelse av metadataene som brukes av CDS for Apps, gi deg innsikt.

*Metadata* betyr data om data. CDS for Apps er en fleksibel plattform fordi det er relativt enkelt å redigere definisjonene av dataene som brukes i miljøet. I CDS for Apps er metadataene en samling enheter. Enheter beskriver hvilke typer data som er lagret i databasen.  Hver enhet svarer til en databasetabell, og hvert felt (også kalt attributt) i en enhet representerer en kolonne i denne tabellen. Metadata for enhet er det som styrer typene oppføringer du kan opprette og typen handlinger som kan utføres på dem. Når du bruker tilpassingsverktøyene for å opprette eller redigere enheter, felt og enhetsrelasjoner, redigerer du disse metadataene. 
  
Ulike klienter som brukerne bruker til å arbeide med dataene i miljøet, avhenger av enhetsmetadataene og tilpasses etter hvert som du tilpasser metadataene. Men disse klientene er også avhengige av andre data for å styre hvilke visuelle elementer som skal vises, eventuell tilpasset logikk som skal brukes, og hvordan sikkerhet skal brukes. Disse systemdataene er også lagret i enheter, men selve enhetene er ikke tilgjengelige for tilpassing.

Du kan lære om standard enheter, attributter og enhetsrelasjoner som er inkludert som standard i CDS for Apps, ved å gå gjennom [enhetsreferansen](/powerapps/developer/common-data-service/reference/about-entity-reference).

> [!TIP]
> Utformingene som er tilgjengelige for redigering av metadata, kan ikke vise alle detaljene i metadataene. Du kan installere en modelldrevet app som kalles **metadataleseren** som gjør det mulig å vise alle enhetene og metadataegenskapene som blir funnet i systemet. Mer informasjon: [Bla gjennom metadataene for miljøet](https://docs.microsoft.com/dynamics365/customer-engagement/developer/browse-your-metadata).
  
<a name="BKMK_CreateNewOrUseExistingMetadata"></a>

## <a name="create-new-metadata-or-use-existing-metadata"></a>Vil du opprette nye metadata eller bruke eksisterende metadata?

CDS for Apps kommer med en rekke standardenheter som støtter kjernefunksjoner i forretningsprogram. Data om kunder eller potensielle kunder er for eksempel ment å lagres ved hjelp av forretningsforbindelses- eller kontaktenhetene.  
  
Hver av disse enhetene inneholder også en rekke felt som representerer vanlige data som systemet kanskje må lagre for den aktuelle enheten.  
  
I de fleste organisasjoner er det best å bruke standardenhetene og -attributtene til formålene de er ment for. 
  
Hvis du vil installere en løsning, kan du regne med at løsningsutvikleren har brukt standardenhetene og -attributtene. Hvis du oppretter en ny egendefinert enhet som erstatter en systemenhet eller et systemattributt, betyr det at tilgjengelige løsninger kanskje ikke fungerer for organisasjonen.  
  
Derfor anbefaler vi at du ser etter og bruker de tilgjengelige standardenhetene, -feltene og enhetsrelasjonene når de er aktuelle å bruke for organisasjonen. Hvis de ikke er aktuelle og ikke kan redigeres slik at de passer organisasjonens behov, bør du vurdere om det er nødvendig å opprette en ny enhet, felt eller enhetsrelasjon. 

<!--  Can we say this yet? 
    
> [!NOTE]
> The [Common Data Model](/powerapps/common-data-model/overview) will provide a capability to add additional standard entities. 

-->

Husk at du kan endre visningsnavnet for en enhet, slik at det samsvarer med terminologien organisasjonen din bruker. Det er for eksempel svært vanlig å endre visningsnavnet for forretningsforbindelsesenheten til *Firma* eller navnet til kontaktenheten til *Person*. Du kan gjøre dette for enheter eller attributter uten å endre virkemåten til enheten. Hvis du vil ha mer informasjon om å gi nytt navn til enheter, kan du se [Endre navnet på en enhet](edit-entities.md#change-the-name-of-an-entity).
  
Du kan ikke slette standardenheter, -felt eller enhetsrelasjoner. De regnes som en del av systemløsningen, og alle organisasjoner forventes å ha dem. Hvis du vil skjule en standardenhet, endrer du sikkerhetsrollerettighetene for organisasjonen for å fjerne leserettigheten for denne enheten. Dermed fjernes enheten fra de fleste deler av programmet. Hvis det er et systemfelt du ikke trenger, kan du fjerne det fra skjemaet og alle visninger som bruker det. Endre **Søkbar**-verdien i felt- og enhetsrelasjonsdefinisjonene slik at de ikke vises i avansert søk. 
  
<a name="BKMK_LimitationsOnMetadata"></a>   

## <a name="limitations-on-creating-metadata-items"></a>Begrensninger ved opprettelse av metadataelementer  

Det er en grense for hvor mange enheter du kan opprette. Du kan finne informasjon om maksimumsantallet på siden **[Innstillinger](../model-driven-apps/advanced-navigation.md#settings)** > **Administrasjon** > **Ressurser i bruk**. Hvis du trenger flere egendefinerte enheter, kan du kontakte teknisk støtte. Denne øvre grensen kan justeres.  
  
Det er en øvre grense for antall felt du kan opprette i hver enhet. Denne grensen er basert på tekniske begrensninger når det gjelder mengden data som kan lagres i en rad i en databasetabell. Det er vanskelig å gi et bestemt tall siden de ulike felttypene kan bruke ulike mengder plass. Den øvre grensen avhenger av den totale plassen som brukes av alle feltene for enheten.  
  
De fleste oppretter ikke nok egendefinerte felt til at grensen nås, men hvis du har tenkt å legge til hundrevis av egendefinerte felt i en enhet, bør du vurdere om dette er den beste utformingen. Beskriver alle feltene du har tenkt å legge til, egenskaper til en oppføring for denne enheten? Forventer du at personer som bruker organisasjonen, faktisk kan administrere et skjema som inneholder så mange felt? Antallet felt du legger til i et skjema, øker mengden data som må overføres hver gang en oppføring redigeres, og påvirker ytelsen til systemet. Ta disse faktorene med i betraktningen når du legger til egendefinerte felt i en enhet.  
  
Alternativsettfelt gir et sett med alternativer som vises i en rullegardinkontroll i et skjema eller i en plukklistekontroll når avansert søk brukes. Miljøet kan støtte tusenvis av alternativer i et alternativsett, men du bør ikke betrakte dette som den øvre grensen. Undersøkelser av brukervennlighet har vist at personer har problemer med å bruke et system der rullegardinkontrollen tilbyr svært mange alternativer. Bruk alternativsettfelt til å definere kategorier for data. Ikke bruk alternativsettfelt til å velge kategorier som faktisk representerer separate dataelementer. I stedet for å ha et alternativsettfelt som brukes til å lagre hver av hundrevis av mulige produsenter av en type utstyr, bør du vurdere å opprette en enhet som brukes til å lagre referanser til hver produsent, og bruke et oppslagsfelt i stedet for et alternativsett.  
  
## <a name="next-steps"></a>Neste trinn 

[Opprette eller redigere enheter (oppføringstyper)](create-edit-entities.md)<br />
[Opprette og redigere relasjoner mellom enheter](create-edit-entity-relationships.md)

