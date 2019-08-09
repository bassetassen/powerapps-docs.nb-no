---
title: Oversikt over enhetsrelasjoner for Common Data Service | MicrosoftDocs
ms.custom: ''
ms.date: 04/25/2019
ms.reviewer: ''
ms.service: powerapps
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - PowerApps
ms.assetid: c765b6d9-4d87-4c2d-aae2-5b1c3b664a71
caps.latest.revision: 28
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="entity-relationships-overview"></a>Oversikt over enhetsrelasjoner
Enhetsrelasjoner definerer hvordan oppføringer kan relateres til hverandre i databasen. På det enkleste nivået vil det å legge til et oppslagsfelt i en enhet opprette en ny 1:N-relasjon (en-til-mange) mellom de to enhetene, og la deg sette oppslagsfeltet i et skjema. Med oppslagsfeltet kan brukere knytte flere *underordnet* oppføringer i enheten til én enkelt *overordnet* enhetsoppføring.  
  
I tillegg til å definere hvordan oppføringer kan relateres til andre oppføringer, gir 1:N-enhetsrelasjoner data for å løse følgende spørsmål:  
  
- Når jeg sletter en oppføring, skal oppføringene som er knyttet til den aktuelle oppføringen også slettes?  
- Når jeg tilordner en oppføring, må jeg også tilordne alle oppføringer som er knyttet til den aktuelle oppføringen til den nye eieren?  
- Hvordan kan jeg effektivisere dataregistreringsprosessen når jeg oppretter en ny relatert oppføring i konteksten til en eksisterende oppføring?  
- Hvordan skal brukere som viser en oppføring kunne vise de tilknyttede oppføringene?  
  
 Enheter kan også delta i en N:N-relasjon (mange-til-mange) der et hvilket som helst antall oppføringer for to enheter kan være knyttet til hverandre.  

<a name="BKMK_Connections"></a>

## <a name="decide-whether-to-use-entity-relationships-or-connections"></a>Bestemme om du vil bruke enhetsrelasjoner eller tilkoblinger 
Enhetsrelasjoner er metadata som gjør endringer i databasen. Disse relasjonene lar spørringer hente relaterte data svært effektivt. Bruk enhetsrelasjoner til å definere formelle relasjoner som definerer enheten, eller som de fleste oppføringer kan bruke. En salgsmulighet uten en potensiell kunde er for eksempel ikke så nyttig. Salgsmulighet-enheten har også en N:N-relasjon til Konkurrent-enheten. Dette gjør det mulig å legge til flere konkurrenter i salgsmuligheten. Du vil kanskje registrere disse dataene og lage en rapport som viser konkurrentene.  
  
Det finnes andre mindre formelle relasjonstyper mellom oppføringer som kalles *tilkoblinger*. Det kan for eksempel være nyttig å vite om to kontakter er gift, eller kanskje de er venner på fritiden, eller kanskje en kontakt tidligere arbeidet for en annen forretningsforbindelse. De fleste virksomheter genererer ikke rapporter som bruker denne typen informasjon, eller krever ikke at det er angitt, så er det sannsynligvis ikke verdt å opprette enhetsrelasjoner. Mer informasjon: [Konfigurere tilkoblingsroller](configure-connection-roles.md)

  
<a name="BKMK_TypesOfRelationships"></a>
 
## <a name="types-of-entity-relationships"></a>Typer entitetsrelasjoner
Når du ser på løsningsutforskeren, tror du kanskje det finnes tre typer enhetsrelasjoner. Det er faktisk bare to, som vist i tabellen nedenfor.  
  
|Relasjonstype|Beskrivelse|  
|-----------------------|-----------------|  
|**1:N (én-til-mange)**|En enhetsrelasjon der én enhetsoppføring for **Hovedenhet** kan knyttes til mange andre oppføringer for **Relatert enhet** på grunn av et oppslagsfelt i den relaterte enheten.<br /><br /> Når du viser en oppføring for hovedenhet, vises en liste over relaterte enhetsoppføringer som er knyttet til den.|  
|**N:N (mange-til-mange)**|En enhetsrelasjon som er avhengig av en spesiell **Relasjonsenhet**, også kalt skjæringspunktenhet, slik at mange oppføringer av én enhet kan relateres til mange oppføringer for en annen enhet.<br /><br /> Når du viser oppføringer for hver enhet i en N:N-relasjon, vises en liste over oppføringer i den andre enheten som er knyttet til den.|  
  
**N:1 (mange-til-en)**-relasjonstypen finnes i brukergrensesnittet fordi utformingen viser en visning som er gruppert etter enheter. 1:N-relasjoner finnes faktisk *mellom* enheter, og refererer til hver enhet som en **Hovedenhet** eller **Relatert enhet**. Den relaterte enheten, noen ganger kalt den *underordnede* enheten, har et oppslagsfelt som gjør det mulig å lagre en referanse til en oppføring fra hovedenheten, noen ganger kalt *overordnede* enhet. En N:1-relasjon er bare en 1:N-relasjon som vises fra den relaterte enheten.  
 
## <a name="entity-relationship-behavior"></a>Enhetsrelasjonsfunksjonalitet
Virkemåte for relaterte enheter er viktig fordi den sikrer dataintegritet og kan automatisere forretningsprosesser for selskapet.

### <a name="preserve-data-integrity"></a>Opprettholde dataintegritet
Noen enheter finnes for å støtte andre enheter. De har ingen mening på egen hånd. De har vanligvis et nødvendig oppslagsfelt for å koble til den primære enheten de støtter. Hva skal skje når hovedoppføringen slettes?

Du kan bruke relasjonsfunksjonaliteten for å definere dette i samsvar med reglene i bedriften din. To alternativer er:

- Hindre sletting av den primære enheten, slik at de relaterte enhetsoppføringene kan avstemmes, kanskje ved at man knytter dem til en annen hovedenhet.
- Tillate at de relaterte enhetene slettes automatisk med slettingen av hovedenhetsoppføringen.

Hvis den relaterte enheten ikke støtter en hovedenhet, kan du tillate at den primære enheten slettes, og verdien for oppslaget fjernes.

### <a name="automate-business-processes"></a>Automatisere forretningsprosesser
Anta at du har en ny selger, og du vil tilordne vedkommende en rekke eksisterende forretningsforbindelser som er tilordnet en annen selger. Hver forretningsforbindelsesoppføring kan ha en rekke tilknyttede oppgaveaktiviteter. Du kan enkelt finne de aktive forretningsforbindelsene du vil tilordne på nytt, og tilordne dem til den nye selgeren. Men hva skal skje med oppgaveaktivitetene som er knyttet til forretningsforbindelsene? Vil du åpne hver oppgave og avgjøre om den også skal tilordnes den nye selgeren? Sannsynligvis ikke. I stedet kan du la relasjonen automatisk bruke noen standardregler for deg. Disse reglene gjelder bare for oppgaveoppføringer som er knyttet til forretningsforbindelser som du tilordner på nytt. Alternativene er:  
  
- Tilordne alle aktive oppgaver på nytt.  
- Tilordne alle oppgaver på nytt. 
- Tilordne ingen av oppgavene på nytt.  
- Tilordne alle oppgaver på nytt som er tilordnet til den tidligere eieren av forretningsforbindelsen.  
  
Relasjonen kan styre hvordan handlingene som utføres på en oppføring for hovedenhetsoppføringen, overlapper ned til eventuelle relatert oppføringer.  

### <a name="behaviors"></a>Virkemåter
Det finnes flere typer virkemåter som kan brukes når bestemte handlinger forekommer.

|Virkemåte|Beskrivelse|
|--|--|
|**Overlapp aktive**|Utfør handlingen på alle aktive relatert enhetsoppføringer.|
|**Overlapp alle**|Utfør handlingen på alle relatert enhetsoppføringer.|
|**Overlapp ingen**|Ikke gjør noe.|
|**Fjern kobling**|Fjern oppslagsverdien for alle relaterte oppføringer.|
|**Begrens**|Hindre at hovedenhetsoppføringen slettes når det finnes relaterte enhetsoppføringer.|
|**Overlapp brukereide**|Utfør handlingen på alle relatert enhetsoppføringer som eies av samme bruker som hovedenhetsoppføringen.|

### <a name="actions"></a>Handlinger
Dette er handlinger som kan utløse enkelte virkemåter:

|Felt|Beskrivelse|Alternativer|
|--|--|--|
|**Tilordne**|Hva skal skje når hovedenhetsoppføringen tilordnes til noen andre?|Overlapp alle<br />Overlapp aktive<br />Overlapp brukereide<br />Overlapp ingen|
|**Overordne på nytt**|Hva skal skje når oppslagsverdien for en relatert enhet i en overordnet relasjon endres?<br />Mer informasjon: [Overordnede enhetsrelasjoner](#parental-entity-relationships)|Overlapp alle<br />Overlapp aktive<br />Overlapp brukereide<br />Overlapp ingen|
|**Dele**|Hva skal skje når hovedenhetsoppføringen deles?|Overlapp alle<br />Overlapp aktive<br />Overlapp brukereide<br />Overlapp ingen|
|**Slett**|Hva skal skje når hovedenhetsoppføringen slettes?|Overlapp alle<br />Fjern kobling<br />Begrens|
|**Oppheve deling**|Hva skal skje når delingen av en hovedenhetsoppføring oppheves?|Overlapp alle<br />Overlapp aktive<br />Overlapp brukereide<br />Overlapp ingen|
|**Slå sammen**|Hva skal skje når en hovedenhetsoppføring slås sammen?|Overlapp alle<br />Overlapp ingen|
|**Visning av beregnet verdi**|Hva er ønsket virkemåte for visningen av beregnet verdi knyttet til denne relasjonen? |Overlapp alle<br />Overlapp aktive<br />Overlapp brukereide<br />Overlapp ingen|


### <a name="parental-entity-relationships"></a>Overordnede enhetsrelasjoner
Hvert par med enheter som er kvalifiserte for en 1:N-relasjon, kan ha flere 1:N-relasjoner mellom dem. Vanligvis kan bare én av disse relasjonene anses som en overordnet enhetsrelasjon.

En overordnet enhetsrelasjon er en 1:N-enhetsrelasjon der ett av overlappingsalternativene i **Overordnet**-kolonnen i den følgende tabellen er sann.

|Handling|Overordnet|Ikke overordnet|  
|------------|--------------|------------------|  
|**Tilordne**|Overlapp alle<br />Overlapp brukereide<br />Overlapp aktive|Overlapp ingen|  
|**Slett**|Overlapp alle|Fjern kobling<br />Begrens|  
|**Overordne på nytt**|Overlapp alle<br />Overlapp brukereide<br />Overlapp aktive|Overlapp ingen|  
|**Dele**|Overlapp alle<br />Overlapp brukereide<br />Overlapp aktive|Overlapp ingen|  
|**Oppheve deling**|Overlapp alle<br />Overlapp brukereide<br />Overlapp aktive|Overlapp ingen|  

Hvis du for eksempel oppretter en ny egendefinert enhet og legger til en 1:N-enhetsrelasjon med forretningsforbindelsesenheten der den egendefinerte enheten er den relaterte enheten, kan du konfigurere handlingene for denne enhetsrelasjonen slik at den bruker alternativene i **Overordnet**-kolonnen. Hvis du senere legger til en ny 1:N-enhetsrelasjon med den egendefinerte enheten som den refererende enheten, kan du bare konfigurere handlingene for bruk av alternativene i **Ikke overordnet**-kolonnen.

Dette betyr vanligvis at for hvert enhetspar er det bare én overordnet relasjon. Det finnes enkelte tilfeller der oppslaget på den relaterte enheten kan tillate en relasjon til mer enn én type enhet.

For eksempel hvis en enhet har et kundeoppslag som kan referere til en kontakt- eller forretningsforbindelsesenhet. Det finnes to separate overordnede 1:N-enhetsrelasjoner.

En aktivitetsenhet har et lignende sett med overordnede enhetsrelasjoner for enheter som kan tilknyttes ved hjelp av oppslagsfeltet Angående.

<a name="BKMK_RelationshipBehaviorLimitations"></a>   

### <a name="limitations-on-behaviors-you-can-set"></a>Begrensninger for virkemåter som du kan angi
På grunn av overordnede relasjoner finnes det enkelte begrensninger som du bør ha i tankene når du definerer enhetsrelasjoner.  
  
- En egendefinert enhet kan ikke være hovedenhet i en relasjon med en relatert systemenhet som overlapper. Dette betyr at du ikke kan ha en relasjon med handling satt til **Overlapp alle**, **Overlapp aktive** eller **Overlapp brukereide** mellom en egendefinert hovedenhet og en relatert systemenhet.  
- Nye relasjoner kan ikke ha handling satt til **Overlapp alle**, **Overlapp aktiv** eller **Overlapp brukereide** hvis den relaterte enheten i relasjonen allerede finnes som en relatert enhet i en annen relasjon, som har en handling satt til **Overlapp alle**, **Overlapp aktiv** eller **Overlapp brukereide**. Dette hindrer relasjoner som har relasjoner med flere overordnede.  

### <a name="see-also"></a>Se også
[Oversikt over enheter og metadata](create-edit-metadata.md)<br />
[Opprette og redigere 1:N-relasjoner (én-til-mange) eller N:1-relasjoner (mange-til-én)](create-edit-1n-relationships.md)<br />
[Opprette mange-til-mange-enhetsrelasjoner (N:N)](create-edit-nn-relationships.md)

