---
title: Opprette og redigere enheter med PowerApps-portalen | MicrosoftDocs
description: Finn ut hvordan du oppretter og redigerer enheter med PowerApps-portalen
ms.custom: ''
ms.date: 05/30/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
author: Mattp123
ms.assetid: fa04f99d-a5f9-48cb-8bfb-f0f50718ccee
caps.latest.revision: 41
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="create-and-edit-entities-using-powerapps-portal"></a>Opprette og redigere enheter ved hjelp av PowerApps-portalen

[PowerApps-portalen](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) gir en enkel måte å opprette og redigere enheter på for Common Data Service for Apps.

Portalen gjør det mulig for konfigurasjon av de vanligste alternativene, men enkelte alternativer kan bare angis ved hjelp av løsningsutforskeren. Mer informasjon: 
- [Opprette og redigere enheter i Common Data Service for Apps](create-edit-entities.md)
- [Opprette og redigere enheter ved hjelp av løsningsutforskeren](create-edit-entities-solution-explorer.md)

## <a name="view-entities"></a>Vise enheter

1. I [PowerApps-portalen](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) velger du utformingsmodusen **Modelldrevet** eller **Lerret**.
2. Velg **Data** > **Enheter**

![Vise enheter](media/view-entities-portal.png)

Du kan filtrere enhetene som vises, ved hjelp av følgende visninger i en liste: 

![Enhetsvisninger](media/entity-views-portal.png)

 |Visning|Beskrivelse|
 |--|--|
 |**Alle**| Viser alle enhetene|
 |**Egendefinert**|Viser bare egendefinerte enheter|
 |**Standard**|Viser bare standardenhetene |

Du kan også velge **Gruppe** for å gruppere enheter med **Merker**.

## <a name="create-an-entity"></a>Opprette en enhet

Når du [viser enheter](#view-entities), velger du **Ny enhet** på menylinjen. Dette åpner Ny enhet-panelet.

![Ny enhet-panelet](media/new-entity-panel.png)

Angi data for følgende felt

|Felt|Beskrivelse|
|--|--|
|**Visningsnavn**|Dette er entallsnavnet for enheten som skal vises i appen. Dette kan endres senere.|
|**Flertallsvisningsnavn**|Dette er flertallsnavnet for enheten som skal vises i appen. Dette kan endres senere.|
|**Navn**|Dette feltet er forhåndsutfylt basert på **visningsnavnet** du angir. Det inkluderer tilpassingsprefikset for CDS-løsningsutgiveren. Du kan ikke endre dette når enheten er lagret.|
|**Beskrivelse**|Angi en relevant beskrivelse av formålet med enheten.|

Velg **Neste** for å fortsette. Dette lukker **Ny enhet**-panelet og viser listen over felt.

**Hovednavn**-feltet er det eneste synlige feltet for øyeblikket. Velg **Hovednavn**-feltet for å redigere det hvis du vil endre **Visningsnavn** eller **Navn** i feltet. Standardverdiene vises nedenfor:

![Hovednavn-panelet](media/primary-name-panel.png)

Velg **Lagre enhet** for å opprette enheten eller fortsett å redigere enheten.

![Lagre enhet](media/save-entity-portal.png)

## <a name="edit-an-entity"></a>Redigere en enhet

Når du [viser enheter](#view-entities), velger du enheten du vil redigere.

Angi innstillinger fra menyen hvis du vil redigere **Visningsnavn**, **Flertallsvisningsnavn** eller **Beskrivelse** for enheten.

![Enhetsinnstillinger](media/entity-settings-portal.png)

For andre elementer velger du fra kategoriene.

### <a name="fields"></a>Felt

Se [Opprette og redigere felt](create-edit-fields.md)

### <a name="relationships"></a>Relasjoner

Se [Opprette og redigere relasjoner mellom enheter](create-edit-entity-relationships.md)

### <a name="business-rules"></a>Forretningsregler

Se [Opprett forretningsregler og anbefalinger hvis du vil bruke logikk i et skjema](../model-driven-apps/create-business-rules-recommendations-apply-logic-form.md)

### <a name="views"></a>Visninger

Se [Opprett eller rediger en visning](../model-driven-apps/create-edit-views.md)

### <a name="forms"></a>Skjemaer

Se [Opprette og utforme skjemaer](../model-driven-apps/create-design-forms.md)

### <a name="dashboards"></a>Instrumentbord

Se [Opprette eller redigere instrumentbord](../model-driven-apps/create-edit-dashboards.md)

### <a name="charts"></a>Diagrammer

Se [Opprett et systemdiagram](../model-driven-apps/create-edit-system-chart.md)

### <a name="keys"></a>Nøkler

Se [Definere alternative nøkler for å referere til oppføringer](define-alternate-keys-reference-records.md)

### <a name="data"></a>Data

Vis dataene i enheten.
Bruk **Velg visning**-menyen for å velge blant tilgjengelige visninger for enheten, eller for å vise alle feltene.

![Velge visning](media/entity-data-select-view.png)

Bruk kommandoene **Neste side** og **Forrige side** nederst i skjemaet for å se flere data.

## <a name="delete-an-entity"></a>Slette en enhet

Som en bruker med sikkerhetsrollen Systemadministrator, kan du slette egendefinerte enheter som ikke er en del av en administrert løsning.  
  
> [!IMPORTANT]
>  Når du sletter en egendefinert enhet, slettes databasetabellene som lagrer data for enheten, og alle data de inneholder, går tapt. Alle tilknyttede oppføringer som har en overordnet relasjon til den egendefinerte enheten, slettes også. Hvis du vil ha mer informasjon om overordnede relasjoner, kan du se [Opprette og redigere relasjoner mellom enheter](create-edit-entity-relationships.md).  
  
> [!NOTE]
> Den eneste metoden for å gjenopprette data fra en enhet som ble slettet, er å gjenopprette databasen fra et punkt før enheten ble slettet. Mer informasjon: [Sikkerhetskopiere og gjenopprette forekomster](/dynamics365/customer-engagement/admin/backup-restore-instances)

Når du [viser enheter](#view-entities), velger du enheten og velger **Slett enhet** på menyen eller hurtigmenyen.

![Slette en enhet ved hjelp av PowerApps-portalen](media/delete-entity-powerapps-portal.png)

Hvis enheten har avhengigheter som forhindrer at den slettes, vises en feilmelding. Hvis du vil identifisere eventuelle avhengigheter, må du bruke løsningsutforskeren. Mer informasjon [Identifisere enhetsavhengigheter](create-edit-entities-solution-explorer.md#identify-entity-dependencies)

### <a name="see-also"></a>Se også

[Opprette og redigere enheter i Common Data Service for Apps](create-edit-entities.md)<br />
[Opprette og redigere enheter ved hjelp av løsningsutforskeren](create-edit-entities-solution-explorer.md)


