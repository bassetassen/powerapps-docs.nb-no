---
title: Redigere en enhet i PowerApps | MicrosoftDocs
description: Lær de ulike måtene du kan redigere en enhet på
ms.custom: ''
ms.date: 05/15/2018
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
ms.assetid: 8b00780c-74f0-4e3a-b570-b9289d0d5383
caps.latest.revision: 41
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="edit-an-entity"></a>Redigere en enhet

Du kan redigere enhver egendefinert enhet du oppretter. Standardenheter eller administrerte egendefinerte enheter kan ha begrensninger for hvilke endringer du kan gjøre.  
  
> [!NOTE]
> **Standardenheter** er vanlige enheter som er inkludert i miljøet, som ikke er **systemenheter** eller **egendefinerte enheter**. *Administrerte egendefinerte enheter* er enheter som er lagt til i systemet ved å importere en administrert løsning. Hvor mye du kan redigere disse enhetene, bestemmes av de forvaltede egenskapene som er angitt for hver enhet. Alle egenskaper som ikke kan redigeres, vil bli deaktivert. 

Det er to metoder for å redigere en enhet ved hjelp av en designer:

|Designer|Beskrivelse|
|--|--|
|[PowerApps-portalen](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)|Inneholder en enkel strømlinjeformet opplevelse, men noen spesialinnstillinger er ikke tilgjengelige.|
|Løsningsutforsker|Ikke så enkel, men den er mer fleksibel når kravene er mindre vanlige.|

I både PowerApps-portalen og løsningsutforskeren kan du utføre følgende:

- **Rediger enhetsfeltene**. Mer informasjon:  [Opprette og redigere felt for Common Data Service](create-edit-fields.md)
  
- **Rediger enhetsrelasjonene**. Mer informasjon: [Opprette og redigere relasjoner mellom enheter](create-edit-entity-relationships.md)

- **Nøkler**. [Definere alternative nøkler for å referere til oppføringer](define-alternate-keys-reference-records.md)
  
Du kan også gjøre endringer i oppføringer som støtter enheten:  

- **Forretningsregler**. Mer informasjon: [Opprett forretningsregler og anbefalinger hvis du vil bruke logikk i et skjema](../model-driven-apps/create-business-rules-recommendations-apply-logic-form.md)

- **Visninger**. Mer informasjon: [Opprette eller redigere en visning](../model-driven-apps/create-edit-views.md)
  
- **Skjemaer**. Mer informasjon: [Opprette og utforme skjemaer](../model-driven-apps/create-design-forms.md)

- **Instrumentbord**. Mer informasjon: [Opprette eller redigere instrumentbord](../model-driven-apps/create-edit-dashboards.md)

- **Diagrammer**. [Opprette eller redigere et systemdiagram](../model-driven-apps/create-edit-system-chart.md)

## <a name="edit-using-powerapps-portal-designer"></a>Redigere ved hjelp av designeren i PowerApps-portalen

I designeren PowerApps-portalen er det bare tre enhetsegenskaper du kan redigere:
 - Visningsnavn
 - Flertallsvisningsnavn
 - Beskrivelse

I designeren velger du enheten du vil redigere, og klikk deretter for å åpne enhetsdesigneren. Hvis du vil endre enhetsegenskapene, klikker du på **Innstillinger**-kommandoen for å vise skjemaet **Rediger enhet**, som vist nedenfor:

![Redigere enhetsegenskaper](media/edit-entity-properties-powerapps-portal-designer.png)

> [!NOTE]
>  Navnene på mange standardenheter kan også brukes i annen tekst i programmet. Hvis du vil finne og endre tekst der dette navnet ble brukt, kan du se [Redigere standardenhetsmeldinger](edit-system-entity-messages.md).

For andre endringer i enhetsalternativer må du redigere enheten ved hjelp av løsningsutforskeren.

## <a name="edit-using-solution-explorer"></a>Redigere med løsningsutforskeren

Når du redigerer en enhet med løsningsutforskeren, må du finne den uadministrerte løsningen der du vil legge til enheten.

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]
  
<a name="BKMK_ChangeEntityName"></a> 
  
## <a name="change-the-name-of-an-entity"></a>Endre navnet på en enhet  

Du kan bruke egenskapene **Visningsnavn** og **Flertallsnavn** til å endre navnet på enheten i programmet. 

> [!NOTE]
>  Navnene på mange standardenheter kan også brukes i annen tekst i programmet. Hvis du vil finne og endre tekst der dette navnet ble brukt, kan du se [Redigere standardenhetsmeldinger](edit-system-entity-messages.md).
  
<a name="BKMK_ChangeEntityIcon"></a>   

###  <a name="change-the-icons-used-for-custom-entities"></a>Endre ikonene som brukes for egendefinerte enheter  

Som standard har alle egendefinerte enheter i webprogrammet de samme ikonene. Du kan opprette bildewebressurser for ikonene du vil ha for de egendefinerte enhetene. Mer informasjon: [Endre ikoner for egendefinerte enheter](../model-driven-apps/change-custom-entity-icons.md).  
  
<a name="BKMK_EnableOptions"></a>  
 
###  <a name="entity-options-that-can-only-be-enabled"></a>Enhetsalternativer som bare kan aktiveres  

Tabellen nedenfor viser alternativene som kan aktiveres for en entitet, men når disse elementene er aktivert, kan de ikke kan deaktiveres:  

[!INCLUDE [cc_entity-set-once-options-table](../../includes/cc_entity-set-once-options-table.md)] 
  
<a name="BKMK_EnableDisableOptions"></a>  
 
###  <a name="enable-or-disable-entity-options"></a>Aktivere eller deaktivere enhetsalternativer  

Tabellen nedenfor viser enhetsalternativene som du kan aktivere eller deaktivere når som helst.  

[!INCLUDE [cc_entity-changeable-options-table](../../includes/cc_entity-changeable-options-table.md)] 

### <a name="see-also"></a>Se også

[Opprette en enhet](create-edit-entities.md)<br />
[Opprette og redigere enheter ved hjelp av løsningsutforskeren](create-edit-entities-solution-explorer.md)
