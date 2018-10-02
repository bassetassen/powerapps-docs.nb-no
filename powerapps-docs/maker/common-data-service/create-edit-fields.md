---
title: Opprette og redigere felt for Common Data Service for Apps | MicrosoftDocs
ms.custom: ''
ms.date: 05/18/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - PowerApps
ms.assetid: d88677fa-2caf-47b0-aec6-10a25a7ec9c3
caps.latest.revision: 55
ms.author: matp
manager: brycho
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="how-to-create-and-edit-fields"></a>Opprette og redigere felt

I Common Data Service for Apps brukes feltene til å definere individuelle dataelementer som kan brukes til å lagre data i en enhet. Feltene kalles *attributter* av utviklere. 
  
Før du oppretter et egendefinert felt, må du vurdere om bruk av et eksisterende felt oppfyller behovene dine. Mer informasjon: [Opprette nye metadata eller bruke eksisterende metadata?](create-edit-metadata.md#create-new-metadata-or-use-existing-metadata)

Det finnes to utforminger som du kan bruke til å opprette eller redigere felt:

|Designer| Beskrivelse|
|--|--|
|[PowerApps-portalen](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)|Inneholder en enkel strømlinjeformet opplevelse, men noen spesialinnstillinger er ikke tilgjengelige.<br />Mer informasjon: [Opprette og redigere felt for Common Data Service for Apps ved hjelp av PowerApps-portalen](create-edit-field-portal.md)|
|Løsningsutforsker|Ikke så enkel, men den er mer fleksibel når kravene er mindre vanlige.<br />Mer informasjon: [Opprette og redigere felt for Common Data Service for Apps ved hjelp av løsningsutforskeren i PowerApps](create-edit-field-solution-explorer.md) |

> [!NOTE]
> Du kan også opprette felt i miljøet ved hjelp av følgende:
> - I modelldrevne apper velger du **Nytt felt** fra skjemaredigeringsprogrammet.
> - Importer en løsning som inneholder definisjonen av feltene.
> - Bruk Power Query til å opprette nye enheter og fylle dem med data.<br />Mer informasjon: [Legge til data i en enhet i Common Data Service ved hjelp av Power Query](/powerapps/maker/common-data-service/data-platform-cds-newentity-pq).
> - En utvikler kan bruke [Metadata-tjenester](/powerapps/developer/common-data-service/use-web-services#metadata-services) til å skrive et program for å opprette og oppdatere felt.

Informasjonen i dette emnet hjelper deg med å velge hvilken utforming du kan bruke. 

Du kan bruke PowerApps-portalen til å opprette og redigere felt for Common Data Service for Apps med mindre du må oppfylle noen av disse kravene:

- Opprett et oppslagsfelt for kunde
- Opprett et felt i en annen løsning enn standard CDS-løsningen
- Angi overganger for statusårsaker
- Rediger flere felt samtidig
- Aktiver sporing av endringer
- Aktiver feltnivåsikkerhet
- Velg om feltet vises i globalt filter i interaktiv opplevelse
- Velg om feltet kan sorteres i instrumentbord for interaktiv opplevelse
- Angi et feltkravnivå som anbefalt for selskapet
- Angi forvaltede egenskaper for et felt

> [!NOTE]
> Du kan opprette et oppslagsfelt i PowerApps-portalen eller i løsningsutforskeren ved å opprette en én-til-mange-relasjon på enheten. Men bare løsningsutforskeren gir mulighet for å opprette denne relasjonen når du oppretter et felt.

## <a name="community-tools"></a>Fellesskapsverktøy

**[Attribute Manager](https://www.xrmtoolbox.com/plugins/DLaB.Xrm.AttributeManager/)** er et verktøy som XrmToolbox-fellesskapet utviklet for CDS for Apps. Se emnet [Utviklerverktøy](https://docs.microsoft.com/dynamics365/customer-engagement/developer/developer-tools) for flere verktøy som er utviklet av fellesskapet.

> [!NOTE]
> Fellesskapsverktøy er ikke fra Microsoft og det er ikke kundestøtte for disse. Hvis du har spørsmål om verktøyet, kontakter du utgiveren. Mer informasjon: [XrmToolBox](https://www.xrmtoolbox.com).

### <a name="see-also"></a>Se også  
[Opprette og redigere felt for Common Data Service for Apps ved hjelp av PowerApps-portalen](create-edit-field-portal.md)<br />
[Opprette og redigere felt for Common Data Service for Apps ved hjelp av løsningsutforskeren i PowerApps](create-edit-field-solution-explorer.md)<br />
[Typer felt og feltdatatyper](types-of-fields.md)<br />
[Dokumentasjon for utviklere: Arbeide med attributtmetadata](/dynamics365/customer-engagement/developer/org-service/work-attribute-metadata)
 
