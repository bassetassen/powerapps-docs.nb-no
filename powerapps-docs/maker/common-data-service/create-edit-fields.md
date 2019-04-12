---
title: Opprette og redigere felt for Common Data Service | MicrosoftDocs
ms.custom: ''
ms.date: 02/08/2019
ms.reviewer: ''
ms.service: powerapps
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
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="how-to-create-and-edit-fields"></a>Opprette og redigere felt

I Common Data Service brukes feltene til å definere individuelle dataelementer som kan brukes til å lagre data i en enhet. Feltene kalles *attributter* av utviklere. 
  
Før du oppretter et egendefinert felt, må du vurdere om bruk av et eksisterende felt oppfyller behovene dine. Mer informasjon: [Opprette nye metadata eller bruke eksisterende metadata?](create-edit-metadata.md#create-new-metadata-or-use-existing-metadata)

Det finnes to utforminger som du kan bruke til å opprette eller redigere felt:

|Designer| Beskrivelse|
|--|--|
|[PowerApps-portalen](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)|Inneholder en enkel strømlinjeformet opplevelse, men noen spesialinnstillinger er ikke tilgjengelige.<br />Mer informasjon: [Opprette og redigere felt for Common Data Service ved hjelp av PowerApps-portalen](create-edit-field-portal.md)|
|Løsningsutforsker|Ikke så enkel, men den er mer fleksibel når kravene er mindre vanlige.<br />Mer informasjon: [Opprette og redigere felt for Common Data Service ved hjelp av løsningsutforskeren i PowerApps](create-edit-field-solution-explorer.md) |

> [!NOTE]
> Du kan også opprette felt i miljøet ved hjelp av følgende:
> - I modelldrevne apper velger du **Nytt felt** fra skjemaredigeringsprogrammet.
> - Importer en løsning som inneholder definisjonen av feltene.
> - Bruk Power Query til å opprette nye enheter og fylle dem med data.<br />Mer informasjon: [Legge til data i en enhet i Common Data Service ved hjelp av Power Query](/powerapps/maker/common-data-service/data-platform-cds-newentity-pq).
> - En utvikler kan bruke [Metadata-tjenester](/powerapps/developer/common-data-service/use-web-services#metadata-services) til å skrive et program for å opprette og oppdatere felt.

Informasjonen i dette emnet hjelper deg med å velge hvilken utforming du kan bruke. 

Du kan bruke PowerApps-portalen til å opprette og redigere felt for Common Data Service med mindre du må oppfylle noen av disse kravene:

- Opprett et oppslagsfelt for kunde. 
   - Mer informasjon: [Ulike typer oppslag](types-of-fields.md#different-types-of-lookups)
- Opprett et felt i en annen løsning enn standard Common Data Service-løsningen. 
   - Mer informasjon: [Løsningsoversikt](solutions-overview.md)
- Angi overganger for statusårsaker. 
   - Mer informasjon: [Definere overganger for statusårsaker for tilfellet eller egendefinerte enheter](define-status-reason-transitions.md)
- Rediger flere felt samtidig.
- Aktiver sporing av endringer. 
   - Mer informasjon: [Oversikt over sporing av endringer](../../developer/common-data-service/auditing-overview.md)
- Aktiver feltnivåsikkerhet. 
   - Mer informasjon: [Feltsikkerhetsenheter](../../developer/common-data-service/field-security-entities.md)
- Velg om feltet vises i globalt filter i interaktiv opplevelse. 
   - Mer informasjon: [Konfigurere instrumentbord for interaktiv opplevelse for modelldrevet app](../model-driven-apps/configure-interactive-experience-dashboards.md)
- Velg om feltet kan sorteres i instrumentbord for interaktiv opplevelse. 
   - Mer informasjon: [Konfigurere instrumentbord for interaktiv opplevelse for modelldrevet app](../model-driven-apps/configure-interactive-experience-dashboards.md)
- Angi et feltkravnivå som anbefalt for selskapet. 
   - Mer informasjon: [Opprett forretningsregler og anbefalinger for å bruke logikk i et modelldrevet appskjema](../model-driven-apps/create-business-rules-recommendations-apply-logic-form.md)
- Angi forvaltede egenskaper for et felt. 
   - Mer informasjon: [Angi administrerte egenskaper for felt](set-managed-properties-for-field.md)

> [!NOTE]
> Du kan opprette et oppslagsfelt i PowerApps-portalen eller i løsningsutforskeren ved å opprette en én-til-mange-relasjon på enheten. Men bare løsningsutforskeren gir mulighet for å opprette denne relasjonen når du oppretter et felt.

## <a name="community-tools"></a>Fellesskapsverktøy

**[Attribute Manager](https://www.xrmtoolbox.com/plugins/DLaB.Xrm.AttributeManager/)** er et verktøy som XrmToolbox-fellesskapet utviklet for Common Data Service. Se emnet [Utviklerverktøy](https://docs.microsoft.com/dynamics365/customer-engagement/developer/developer-tools) for flere verktøy som er utviklet av fellesskapet.

> [!NOTE]
> Fellesskapsverktøy er ikke fra Microsoft og det er ikke kundestøtte for disse. Hvis du har spørsmål om verktøyet, kontakter du utgiveren. Mer informasjon: [XrmToolBox](https://www.xrmtoolbox.com).

### <a name="see-also"></a>Se også  
[Opprette og redigere felt for Common Data Service ved hjelp av PowerApps-portalen](create-edit-field-portal.md)<br />
[Opprette og redigere felt for Common Data Service ved hjelp av løsningsutforskeren i PowerApps](create-edit-field-solution-explorer.md)<br />
[Typer felt og feltdatatyper](types-of-fields.md)<br />
[Dokumentasjon for utviklere: Arbeide med attributtmetadata](/dynamics365/customer-engagement/developer/org-service/work-attribute-metadata)
 
