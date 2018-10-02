---
title: Oversikt over oppretting og redigering av globale alternativsett (valglister) for Common Data Service for Apps | MicrosoftDocs
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
ms.assetid: f06b8941-8dca-4601-b965-341cfb6fc3b2
caps.latest.revision: 11
ms.author: matp
manager: brycho
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="create-and-edit-global-option-sets-overview"></a>Oversikt over oppretting og redigering av globale alternativsett 

Et alternativsett (valgliste) er en type felt som kan inkluderes i en enhet. Det definerer et sett med alternativer. Når et alternativsett vises i skjemaet, bruker det en rullegardinlistekontroll. Når det vises i **Avansert søk**, bruker det en *plukklistekontroll*. Alternativsett kalles noen ganger plukklister av utviklere.  
  
Du kan definere et alternativsett for å bruket et sett med alternativer som er definert i seg selv (lokalt), eller det kan bruke et sett med alternativer som er definert andre steder (globalt), som kan brukes av andre alternativsettfelt. 

Globale alternativsett er nyttige når du har et standardsett med kategorier som du kan bruke på mer enn ett felt. Det er vanskelig å vedlikeholde to separate alternativsett med de samme verdiene, og hvis de ikke er synkronisert, kan det oppstå feil, spesielt hvis du tilordner enhetsfelt i en en-til-mange-enhetsrelasjon. Mer informasjon: [Tilordne enhetsfelt](map-entity-fields.md)

> [!NOTE]
> Hvis du angir hvert alternativsett som et globalt alternativsett, vil listen over globale alternativsett vokse og kan bli vanskelig å administrere. Hvis du vet at settet med alternativer bare skal brukes på ett sted, bruker du et lokalt alternativsett.

Det finnes to utforminger som du kan bruke til å opprette eller redigere globale alternativsett:

|Designer| Beskrivelse|
|--|--|
|[PowerApps-portalen](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)|Inneholder en enkel strømlinjeformet opplevelse, men noen spesialinnstillinger er ikke tilgjengelige.<br />Mer informasjon: [Opprette et alternativsett](custom-picklists.md) |
|Løsningsutforsker|Ikke så enkel, men den er mer fleksibel når kravene er mindre vanlige. <br />Mer informasjon: [Opprette og redigere globale alternativsett for Common Data Service for Apps ved hjelp av løsningsutforskeren](create-edit-global-option-sets-solution-explorer.md) |

> [!NOTE]
> Du kan også opprette globale alternativsett i miljøet ved hjelp av følgende:
> - Importer en løsning som inneholder definisjonen av de globale alternativsettene.
> - En utvikler kan skrive et program for å opprette dem. <br />Mer informasjon: [Dokumentasjon for utviklere: Tilpasse globale alternativsett](/dynamics365/customer-engagement/developer/org-service/customize-global-option-sets).

Informasjonen i dette emnet hjelper deg med å velge hvilken utforming du kan bruke. 

Du bør bruke [PowerApps-portalen](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) til å arbeide med globale alternativsett med mindre du må oppfylle noen av følgende krav:

- Tilordne farger til alternativer
- Endre rekkefølgen på alternativer
- Opprett et globalt alternativsett i en annen løsning enn standard CDS-løsningen
- Angi forvaltede egenskaper
- Angi egenskaper som brukes for virtuelle enheter
- Vis avhengigheter

## <a name="see-also"></a>Se også

[Opprette et alternativsett](custom-picklists.md)<br />
[Opprette og redigere globale alternativsett for Common Data Service for Apps ved hjelp av løsningsutforskeren](create-edit-global-option-sets-solution-explorer.md)<br />
[Dokumentasjon for utviklere: Tilpasse globale alternativsett](/dynamics365/customer-engagement/developer/org-service/customize-global-option-sets)
  

 
