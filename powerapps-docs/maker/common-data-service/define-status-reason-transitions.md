---
title: Definere overføringer av statusårsak med PowerApps | MicrosoftDocs
description: Lær hvordan du angir overføringer for statusårsaker
ms.custom: ''
ms.date: 05/25/2018
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
ms.assetid: dbc4f436-0b23-42f9-8079-b0de482aaebe
caps.latest.revision: 11
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="define-status-reason-transitions-for-the-case-or-custom-entities"></a>Definere overganger for statusårsaker for saken eller egendefinerte enheter

Du kan du angi overføringer for statusårsak for enheten Hendelse (**Sak**) eller en egendefinert enhet.

> [!NOTE]
> Selv om hendelsesenheten (saken) ikke er inkludert i et standard Common Data Service for Apps-miljø, brukes den av [Dynamics 365 for Customer Service](https://dynamics.microsoft.com/customer-service/) og er definert i [Common Data Model](https://github.com/Microsoft/CDM/blob/master/schemaDocuments/core/applicationCommon/foundationCommon/crmCommon/service/Incident.cdm.json)
  
Overføringer for statusårsak er et valgfritt tilleggsnivå for filtrering for å angi hva verdien for statusårsaken kan endres til for hver statusårsak. Hvis du angir en begrenset liste med gyldige alternativer, kan dette gjøre det enklere for brukere å velge riktig neste statusårsak for en oppføring når du har et stort antall kombinasjoner av gyldige verdier for statusårsak.  
  
<a name="BKMK_StatusAndStatusReasons"></a>

## <a name="what-is-the-connection-between-status-and-status-reason-fields"></a>Hva er sammenhengen mellom feltene Status og Statusårsak?  

Enheter som kan ha ulike statusverdier, har to felt som fanger opp disse dataene:  
  
|Visningsnavn|Beskrivelse|  
|------------------|-----------------|  
|**Status**|Representerer statusen for oppføringen. Vanligvis **Aktiv** eller **Inaktiv**. Du kan ikke legge til nye statusalternativer.|  
|**Statusårsak**|Representerer en årsak som er knyttet til en bestemt status. Hver status må ha minst én mulig statusårsak. Du kan legge til flere alternativer for statusårsak.|  
  
Metadataene for feltet angir hvilke statusverdier som er gyldige for en bestemt tilstand. Standardstatus og alternativer for statusårsak for Hendelse-enheten (**Sak**) er for eksempel:  
  
|Status|Statusårsak|  
|------------|-------------------|  
|**Aktiv**|<li>**Pågår**</li><li>**På vent**</li><li>**Venter på detaljer**</li><li>**Undersøker**</li>| 
|**Løst**|<li>**Problem løst**</li><li>**Angitt informasjon**</li>|
|**Annullert**|<li>**Annullert**</li><li>**Sammenslått**</li>|
  
  
<a name="BKMK_EditStatusReasonTransitions"></a>   

## <a name="edit-status-reason-transitions"></a>Rediger overføringer av statusårsak
 
Du kan endre feltalternativene for statusårsaken for Sak-enheten og egendefinerte enheter for å definere hvilke andre alternativer for statusårsak brukere kan velge. Den eneste begrensningen er at hvert alternativ for statusårsak for en aktiv status må ha minst én bane til en inaktiv status. Hvis ikke, kan du skape en situasjon der det ikke vil være mulig å løse eller avbryte saken.  

> [!NOTE]
> Redigere overganger for statusårsak krever bruk av løsningsutforskeren. Se [Opprette og redigere felt for Common Data Service for Apps ved hjelp av løsningsutforskeren i PowerApps](create-edit-field-solution-explorer.md) for informasjon om hvordan du redigerer felt.
  
 Når du redigerer et statusårsaksfelt, vises knappen **Rediger overføringer av statusårsak** på menyen. 

![Kommandoen Rediger overføringer av statusårsak](media/status-reason-transitions-command.png)

Når du klikker denne knappen, gir dialogboksen **Overføringer av statusårsak** mulighet til å velge **Aktiver overføringer av statusårsak**. Når dette alternativet er valgt, må du angi hvilke *andre* verdier for statusårsak som er tillatt for hver statusårsak. Hvis du vil fjerne filtrering som brukes, fjerner du merkingen for **Aktiver overføringer av statusårsak**. Overføringene du har angitt vil bli beholdt, men ikke brukt.  
  
Skjermbildet nedenfor viser et eksempel som oppfyller følgende krav: 
 
- En sak kan slås sammen når som helst. Du kan ikke slå sammen saker hvis en overføring av statusårsak ikke tillater det.  
- En aktiv sak kan avsluttes når som helst.  
- En løst eller avsluttet sak kan ikke reaktiveres.  
- Alle saker som må gå gjennom følgende trinn: **Pågår** > **På vent** > **Venter på detaljer** > **Undersøker** før de kan løses. En sak kan ikke settes til en tidligere status med denne konfigurasjonen.  
  > [!NOTE]
  >  Dette er ikke et godt eksempel for faktisk arbeid, men det demonstrerer hvordan statustrinn kan håndheves gjennom overføringer av statusårsak.  
  
 ![Eksempel på statusårsaksoverganger for saken](media/status-reason-transitions-example.PNG)  
  
### <a name="see-also"></a>Se også  

[Opprette og redigere felt for Common Data Service for Apps ved hjelp av løsningsutforskeren i PowerApps](create-edit-field-solution-explorer.md)<br />
[Enhetsmetadata > Enhetstilstander](/powerapps/developer/common-data-service/entity-metadata#entity-states)<br />
[Definere egendefinerte tilstandsmodelloverganger](/dynamics365/customer-engagement/developer/define-custom-state-model-transitions)

