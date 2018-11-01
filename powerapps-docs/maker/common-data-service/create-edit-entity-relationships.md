---
title: Oversikt over enhetsrelasjoner for Common Data Service for Apps | MicrosoftDocs
ms.custom: ''
ms.date: 05/26/2018
ms.reviewer: ''
ms.service: crm-online
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
manager: brycho
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
 
## <a name="see-also"></a>Se også

[Oversikt over enheter og metadata](create-edit-metadata.md)<br />
[Opprette og redigere 1:N-relasjoner (én-til-mange) eller N:1-relasjoner (mange-til-én)](create-edit-1n-relationships.md)<br />
[Opprette mange-til-mange-enhetsrelasjoner (N:N)](create-edit-nn-relationships.md)

