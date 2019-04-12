---
title: Oversikt over oppretting av mange-til-mange-enhetsrelasjoner i Common Data Service | MicrosoftDocs
description: Lær hvordan du oppretter enhetsrelasjoner av typen mange-til-mange
ms.custom: ''
ms.date: 05/29/2018
ms.reviewer: ''
ms.service: powerapps
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
author: Mattp123
ms.assetid: 248cecfd-c9e8-430b-b4b0-860669866084
caps.latest.revision: 33
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="create-many-to-many-entity-relationships-overview"></a>Oversikt over oppretting av mange-til-mange-enhetsrelasjoner

1:N-enhetsrelasjoner (én-til-mange) oppretter et hierarki mellom oppføringer. Det finnes ikke et eksplisitt hierarki med mange-til-mange-relasjoner (N:N). Det finnes ingen oppslagsfelt eller virkemåter å konfigurere. Oppføringer som er opprettet ved hjelp av mange-til-mange-relasjoner, er likestilte og relasjonen er resiprok.  
  
Med mange-til-mange-relasjoner lagrer en relasjon (eller skjæringspunkt) dataene som knytter enhetene sammen. Denne enheten har en én-til-mange-enhetsrelasjon med begge de tilknyttede enhetene og lagrer bare verdiene som er nødvendig for å definere relasjonen. Du kan ikke legge til egendefinerte felt i en relasjonsenhet, og den er aldri synlig i brukergrensesnittet. 
  
Oppretting av mange-til-mange-relasjoner krever at du velger de to enhetene som du vil ha med i relasjonen. Du kan velge hvordan de respektive listene skal være tilgjengelige i navigasjonen for hver enhet, for modelldrevne apper. Dette er de samme alternativene som brukes for hovedenheten i 1:N-enhetsrelasjoner. Mer informasjon: [Navigasjonsruteelement for primærenhet](create-edit-1n-relationships-solution-explorer.md#navigation-pane-item-for-primary-entity)
  
Ikke alle enheter kan brukes med mange-til-mange-relasjoner. Hvis enheten ikke er tilgjengelig for valg i utformingen, kan du ikke opprette en ny mange-til-mange-relasjon med enheten. Mer informasjon: [Dokumentasjon for utviklere: Rettigheter for enhetsrelasjon](https://docs.microsoft.com/dynamics365/customer-engagement/developer/entity-relationship-eligibility)

Det finnes to utforminger som du kan bruke til å opprette og redigere 1:N- (én-til-mange) eller N:1-relasjoner (mange-til-én):

|Designer| Beskrivelse|
|--|--|
|[PowerApps-portalen](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)|Inneholder en enkel strømlinjeformet opplevelse, men noen spesialinnstillinger er ikke tilgjengelige.<br />Mer informasjon: [Opprette mange-til-mange-enhetsrelasjoner i Common Data Service ved hjelp av PowerApps-portalen](create-edit-nn-relationships-portal.md)|
|Løsningsutforsker|Ikke så enkel, men den er mer fleksibel når kravene er mindre vanlige.<br />Mer informasjon: [Opprette N:N-enhetsrelasjoner (mange-til-mange) i Common Data Service ved hjelp av løsningsutforskeren](create-edit-nn-relationships-solution-explorer.md) |

> [!NOTE]
> Du kan også opprette ny mange-til-mange-enhetsrelasjon (N:N) i miljøet ved hjelp av følgende:
> - Importer en løsning som inneholder definisjonen av relasjonen. Mer informasjon: [Importere, oppdatere og eksportere løsninger](import-update-export-solutions.md)
> - En utvikler kan bruke [Metadata-tjenester](../../developer/common-data-service/metadata-services.md) til å skrive et program for å opprette og oppdatere enhetsrelasjoner. Mer informasjon: [Dokumentasjon for utviklere: Tilpasse enhetsrelasjonsmetadata](https://docs.microsoft.com/dynamics365/customer-engagement/developer/customize-entity-relationship-metadata)

Informasjonen i dette emnet hjelper deg med å velge hvilken utforming du kan bruke. 

Du bør bruke PowerApps-portalen til å opprette og redigere mange-til-mange-enhetsrelasjoner (N:N) hvis du ikke trenger å ta hensyn til noen av de følgende kravene:

- Konfigurere navigasjonsrutealternativer for modelldrevne apper.
- Skjul relasjonen fra Avansert søk i modelldrevne apper.

## <a name="see-also"></a>Se også

[Opprette og redigere relasjoner mellom enheter](create-edit-entity-relationships.md)<br />
[Opprette mange-til-mange-enhetsrelasjoner i Common Data Service ved hjelp av PowerApps-portalen](create-edit-nn-relationships-portal.md)<br />
[Opprette N:N-enhetsrelasjoner (mange-til-mange) i Common Data Service ved hjelp av løsningsutforskeren](create-edit-nn-relationships-solution-explorer.md)<br />
[Dokumentasjon for utviklere: Tilpasse enhetsrelasjonsmetadata](https://docs.microsoft.com/dynamics365/customer-engagement/developer/customize-entity-relationship-metadata)<br />
[Dokumentasjon for utviklere: Rettigheter for enhetsrelasjon](https://docs.microsoft.com/dynamics365/customer-engagement/developer/entity-relationship-eligibility)
