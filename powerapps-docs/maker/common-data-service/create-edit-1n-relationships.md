---
title: 'Oversikt over oppretting av enhetsrelasjoner av typen 1:N (en-til-mange) eller N:1 (mange-til-en) i PowerApps | MicrosoftDocs'
description: Lær hvordan du oppretter enhetsrelasjoner av typen én-til-mange eller mange-til-én
ms.custom: ''
ms.date: 05/27/2018
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
ms.assetid: 52c00707-b2bc-4950-abec-89baefd94f6e
caps.latest.revision: 33
ms.author: matp
manager: kvivek
tags: null
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="create-one-to-many-or-many-to-one-entity-relationships-overview"></a>Oversikt over oppretting av enhetsrelasjoner av typen én-til-mange eller mange-til-én

I Common Data Service for Apps definerer 1:N-relasjonen (én-til-mange) eller N:1-relasjonen (mange-til-én) hvordan to enheter er relatert til hverandre. 
  
Før du oppretter en egendefinert enhetsrelasjon, kan du vurdere om bruk av en eksisterende enhetsrelasjon oppfyller behovene dine. <br />Mer informasjon: [Opprette nye metadata eller bruke eksisterende metadata?](create-edit-metadata.md#create-new-metadata-or-use-existing-metadata)

Det finnes to utforminger som du kan bruke til å opprette og redigere 1:N- (én-til-mange) eller N:1-relasjoner (mange-til-én):

|Designer| Beskrivelse|
|--|--|
|[PowerApps-portalen](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)|Inneholder en enkel strømlinjeformet opplevelse, men noen spesialinnstillinger er ikke tilgjengelige.<br />Mer informasjon: [Opprette og redigere 1:N- (én-til-mange) eller N:1-enhetsrelasjoner (mange-til-én) i PowerApps-portalen](create-edit-1n-relationships-portal.md)|
|Løsningsutforsker|Ikke så enkel, men den er mer fleksibel når kravene er mindre vanlige. <br />Mer informasjon: [Opprette og redigere 1:N- (én-til-mange) eller N:1-enhetsrelasjoner (mange-til-én) med løsningsutforskeren](create-edit-1n-relationships-solution-explorer.md) |

> [!NOTE]
> Du kan også opprette nye enhetsrelasjoner i miljøet ved hjelp av følgende:
> - I modelldrevne apper velger du **Nytt felt** fra skjemaredigeringsprogrammet og oppretter et *Oppslag*-felt. <br />Mer informasjon: [Legge til et felt i et skjema](../model-driven-apps/add-field-form.md)
> - Opprett et nytt oppslagsfelt for den relaterte enheten. <br />Mer informasjon: [Opprette og redigere felt](create-edit-fields.md)
> - Importer en løsning som inneholder definisjonen av en enhetsrelasjon. <br />Mer informasjon: [Importere, oppdatere og eksportere løsninger](import-update-export-solutions.md)
> - Bruk Power Query til å opprette nye enheter og fylle dem med data. <br />Mer informasjon: [Legge til data i en enhet i Common Data Service for Apps ved hjelp av Power Query](data-platform-cds-newentity-pq.md).
> - En utvikler kan bruke [webtjenester](../../developer/common-data-service/use-web-services.md#metadata-services) til å skrive et program for å opprette og oppdatere enhetsrelasjoner. <br />Mer informasjon: [Tilpasse enhetsrelasjonsmetadata](https://docs.microsoft.com/dynamics365/customer-engagement/developer/customize-entity-relationship-metadata)

Informasjonen i dette emnet hjelper deg med å velge hvilken utforming du kan bruke. 

Du bør bruke PowerApps-portalen til å opprette og redigere 1:N- (én-til-mange) eller N:1-enhetsrelasjoner (mange-til-én) hvis du ikke trenger å ta hensyn til noen av de følgende kravene:

- Konfigurere felttilordninger
- Konfigurere navigasjonsrutealternativer for modelldrevet app
- Konfigurere relasjonsfunksjonalitet
- Angi om relasjonen skjules i avansert søk.
- Lage en hierarkisk relasjon


## <a name="community-tools"></a>Fellesskapsverktøy

**[Entity Relation Diagram Creator](https://www.xrmtoolbox.com/plugins/JourneyIntoCRM.XrmToolbox.ERDPlugin/)** er et verktøy som XrmToolbox-fellesskapet utviklet for CDS for Apps. Se [Utviklerverktøy for Common Data Service for Apps](https://docs.microsoft.com/dynamics365/customer-engagement/developer/developer-tools)-emnet for flere verktøy utviklet av fellesskapet.

> [!NOTE]
> Fellesskapsverktøy er ikke fra Microsoft og det er ikke kundestøtte for disse. Hvis du har spørsmål om verktøyet, kontakter du utgiveren. Mer informasjon: [XrmToolBox](https://www.xrmtoolbox.com).

### <a name="see-also"></a>Se også

[Opprette og redigere relasjoner mellom enheter](create-edit-entity-relationships.md)<br />
[Opprette og redigere 1:N- (én-til-mange) eller N:1-enhetsrelasjoner (mange-til-én) i PowerApps-portalen](create-edit-1n-relationships-portal.md)<br />
[Opprette og redigere 1:N- (én-til-mange) eller N:1-enhetsrelasjoner (mange-til-én) med løsningsutforskeren](create-edit-1n-relationships-solution-explorer.md)<br />
[Dokumentasjon for utviklere: Tilpasse enhetsrelasjonsmetadata](/dynamics365/customer-engagement/developer/customize-entity-relationship-metadata)<br />
[Dokumentasjon for utviklere: Rettigheter for enhetsrelasjon](/dynamics365/customer-engagement/developer/entity-relationship-eligibility)


