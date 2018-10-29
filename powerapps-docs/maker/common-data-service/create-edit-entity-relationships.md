---
title: Opprett og rediger enhetsrelasjoner for Common Data Service for apper | MicrosoftDocs
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
ms.openlocfilehash: 896b026bc72022e66e548db95f78d785e14fdf23
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/08/2018
ms.locfileid: "39690776"
---
# <a name="create-and-edit-relationships-between-entities"></a>Opprett og rediger relasjoner mellom enheter 

Enhetsrelasjoner definerer hvordan poster kan knyttes til hverandre i databasen. Hvis du legger til et oppslagsfelt til en enhet, opprettes en ny 1:N-relasjon (én-til-mange) mellom de to enhetene og du kan legge dette oppslagsfeltet i et skjema. Ved bruk av det oppslagsfeltet kan brukerne tilknytte *underordnede* poster i den enheten til en enkelt *overordnet* enhetspost.  
  
I tillegg til å gi en enkel definisjon av hvordan poster er relatert til hverandre, gir også 1:N-enhetsrelasjoner data som kan brukes til å ta hånd om følgende spørsmål:  
  
- Når jeg sletter en post, skal da eventuelle poster som er knyttet til den posten, også slettes?  
- Når jeg tilordner en post, må jeg også da tilordne alle postene som er knyttet til den posten, til den nye eieren?  
- Hvordan kan jeg strømlinjeforme dataregistreringsprosessen når jeg oppretter en ny relatert post, i konteksten til en eksisterende post?  
- Hvordan skal de som viser en post, være i stand til å vise de tilknyttede postene?  
  
 Enheter kan også delta i en N:N-relasjon (mange-til-mange) hvor en antall poster for to enheter kan være tilknyttet hverandre.  

<a name="BKMK_Connections"></a>

## <a name="decide-whether-to-use-entity-relationships-or-connections"></a>Bestem om du vil bruke enten enhetsrelasjoner eller tilkoblinger 
 
Enhetsrelasjoner er metadata som gjør endringer til databasen. Disse relasjonene muliggjør at spørringer kan hente relaterte data på en svært effektiv måte. Du kan bruke enhetsrelasjoner til å definere formelle relasjoner som definerer enheten, eller som de fleste postene kan bruke. En salgsmulighet uten en potensiell kunde ville for eksempel ikke vært spesielt nyttig. Salgsmulighet-enheten har også en N:N-relasjon med Konkurrent-enheten. Dette gjør det mulig å legge til flere konkurrenter i salgsmuligheten. Du kan registrere disse dataene og opprette en rapport som viser konkurrentene.  
  
Det finnes andre mindre formelle typer relasjoner mellom poster, og de kalles *tilkoblinger*. Det kan for eksempel være nyttig å vite om to kontakter er gift, eller kanskje er de venner utenfor jobben, eller kanskje en kontakt pleide å jobbe for en annen kontakt. De fleste virksomhetene genererer ikke rapporter ved bruk av denne typen informasjon, eller krever at det skal oppgis, så det er sannsynligvis ikke verdt å opprette enhetsrelasjoner. Mer informasjon: [Konfigurer tilkoblingsroller](configure-connection-roles.md)

  
<a name="BKMK_TypesOfRelationships"></a>
 
## <a name="types-of-entity-relationships"></a>Typer enhetsrelasjoner

Når du ser på løsningsutforsker, tror du kanskje at det finnes tre typer enhetsrelasjoner. Det finnes faktisk bare to, som vist i den følgende tabellen.  
  
|Relasjonstype|Beskrivelse|  
|-----------------------|-----------------|  
|**1:N (én til mange)**|En enhetsrelasjon der én enhetspost for **Hovedenhet** kan være knyttet til mange andre **Relatert enhet**-poster, på grunn av et oppslagsfelt i den relaterte enheten.<br /><br /> Når du viser en hovedenhetspost, kan du se en liste over de relaterte enhetspostene som er tilknyttet.|  
|**N:N (mange til mange)**|En enhetsrelasjon som avhenger av en spesiell **Relasjonsenhet**, som noen ganger kalles en skjæringspunktenhet, så mange poster i én enhet kan være relatert til mange poster i en annen enhet.<br /><br /> Når du viser poster i begge enhetene i en N:N-relasjon, kan du se en liste over alle postene i den andre enheten som er knyttet til den.|  
  
**N:1 (mange-til-én)**-relasjontypen finnes i brukergrensesnittet fordi utformingsverktøyet har en visning som er gruppert etter enheter. 1:N-relasjoner finnes faktisk *mellom* enheter, og de henviser til hver enhet som enten **Hovedkontakt** eller **Relatert enhet**. Den relaterte enheten, noen ganger kalt den *underordnede* enheten, har et oppslagsfelt der du kan lagre en referanse i en post fra hovedenheten, noen ganger kalt den *overordnede* enheten. En N:1-relasjon er bare en 1:N-relasjon sett fra den relaterte enheten.  
 
## <a name="see-also"></a>Se også

[Oversikt over enheter og metadata](create-edit-metadata.md)<br />
[Opprett og rediger 1:N (én-til-mange)- eller N:1 (mange-til-én)-relasjoner](create-edit-1n-relationships.md)<br />
[Opprett mange-til-mange (N:N)-enhetsrelasjoner](create-edit-nn-relationships.md)

