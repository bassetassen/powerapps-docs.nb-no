---
title: Opprett og rediger enheter ved hjelp av løsningsutforsker | MicrosoftDocs
description: Finn ut hvordan du oppretter en enhet ved hjelp av løsningsutforsker
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
ms.author: matp
manager: kvivek
ms.openlocfilehash: 48025088da85bf0685ba1a46efa4f3a989a20a58
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/08/2018
ms.locfileid: "39690291"
---
# <a name="create-and-edit-entities-using-solution-explorer"></a>Opprett og rediger enheter ved hjelp av løsningsutforsker

Du kan enkelt opprette en enhet ved bruk av PowerApps-portalen for de fleste vanlige situasjoner, men ikke alle funksjonene er implementert der. Når du har behov for å møte kravene som beskrives i [Opprett og rediger enheter i Common Data Service for Apper](create-edit-entities.md), kan du oppnå dette ved å opprette og redigere enheter ved hjelp av løsningsutforskeren.

## <a name="open-solution-explorer"></a>Åpne løsningsutforsker

En del av navnet til enheten du oppretter, er tilpassingsprefikset. Dette angis basert på løsningsutgiveren for løsningen du jobber i. Hvis du er opptatt av tilpassingsprefikset, må du kontrollere at du jobber i en ikke-administrert løsning, der tilpassingsprefikset er det du vil ha for denne enheten. Mer informasjon: [Endre prefiks for løsningsutgiver](change-solution-publisher-prefix.md) 

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]

## <a name="view-entities"></a>Vis enheter

Velg **Enheter**-noden i løsningsutforskeren i **Komponenter**-noden.

![Vis enheter i løsningsutforsker](media/view-entities-solution-explorer.png)

## <a name="create-an-entity"></a>Opprett en enhet

Velg **Ny** mens du [viser enheter](#view-entities) for å åpne et nytt enhetsskjema.

![nytt enhetsskjema i løsningsutforsker](media/new-entity-form-solution-explorer.png)

Det nye enhetsskjemaet har to faner. **Generelt**-fanen er for enhetsalternativer. **Primærfelt**-fanen er for alternativer om den spesielle enkeltlinjen i tekstfeltet hver enhet har, som definerer teksten som vises når det finnes en kobling som åpner enheten i et oppslagsfelt.

Hvis du vil ha informasjon om hver inndeling, kan du se følgende:
- [Konfigurere primærfeltet](#configure-the-primary-field)
- [Konfigurere obligatoriske felt](#configure-required-fields)

> [!NOTE]
> Du kan også gjøre enheten om til en egendefinert aktivitet. Dette valget endrer noen av standardverdiene for alternativer. Mer informasjon: [Opprett en egendefinert aktivitet](#create-custom-activity-entity)

Når du har angitt alle nødvendige alternativene for enheten, klikker du på ![Lagre kommando](media/save-entity-icon-solution-explorer.png) for å opprette den egendefinerte enheten.

### <a name="configure-the-primary-field"></a>Konfigurer primærfeltet

Du kan vanligvis godta standardverdiene for primærfeltet i **Primærfelt**-fanen, men du har følgende alternativer:

|Felt   |Beskrivelse  |
|---------|---------|
|**Visningsnavn**|Angi den lokaliserbare etiketten som skal vises for dette feltet i skjemaer og lister. Standardverdien er **Navn**.|
|**Navn**|Angi navnet som brukes i systemet for dette feltet. Standardverdien er `<customization prefix>_name`|
|**Maksimumslengde**|Angi den maksimale lengden for feltverdiene. Standarden er 100.|

> [!NOTE]
> Disse alternativene gjelder ikke hvis enheten er en aktivitetsenhet. Mer informasjon:  [Opprett en egendefinert aktivitetsenhet](#create-custom-activity-entity)

### <a name="configure-required-fields"></a>Konfigurer obligatoriske felt

Noen av alternativene i **Generelt**-fanen kreves før du kan lagre enheten.

|Felt   |Beskrivelse  |
|---------|---------|
|**Visningsnavn**|Dette er enkeltnavnet for enheten, som vises i appen.<br />Dette kan endres senere.|
|**Flertallsnavn**|Dette er flertallsnavnet for enheten, som vises i appen.<br />Dette kan endres senere.|
|**Navn**|Dette feltet er forhåndsutfylt basert på visningsnavnet du angir. Dette omfatter tilpassingsprefikset for løsningsutgiveren.|
|**Eierskap**|Du kan velge bruker-, team- eller organisasjonseid. Mer informasjon: [Enhetseierskap](types-of-entities.md#entity-ownership)|

## <a name="edit-an-entity"></a>Rediger en enhet

Velg enheten du vil redigere, eller fortsett å redigere en ny enhet du nettopp har lagret, mens du [viser enheter](#view-entities).

> [!NOTE]
> Standardenheter eller egendefinerte enheter som er en del av en administrert løsning, kan ha begrensninger for hvilke endringer du kan bruke. Hvis alternativet er ikke tilgjengelig eller er deaktivert, kan du ikke gjøre endringen.

#### <a name="set-once-options"></a>Alternativer som kan angis en gang

Følgende alternativer kan angis en gang og kan ikke endres når du har angitt dem. Pass på å angi disse alternativene bare når du trenger dem.

<!-- 
Same data is presented in edit-entities.md
Both should point to this include
 -->
[!INCLUDE [cc_entity-set-once-options-table](../../includes/cc_entity-set-once-options-table.md)]

#### <a name="options-that-you-can-change"></a>Alternativer du kan endre

Følgende egenskaper kan endres når som helst.

<!-- 
Same data is presented in edit-entities.md
Both should point to this include
 -->
[!INCLUDE [cc_entity-changeable-options-table](../../includes/cc_entity-changeable-options-table.md)]

Du kan også gjøre følgende endringer:
- [Opprett og rediger felter for Common Data Service for apper](create-edit-fields.md)
- [Opprett og rediger relasjoner mellom enheter](create-edit-entity-relationships.md)
- [Opprette og utforme skjemaer](../model-driven-apps/create-design-forms.md)
- [Opprett en forretningsprosessflyt for å standardisere prosesser](/flow/create-business-process-flow)

## <a name="delete-an-entity"></a>Slett en enhet

Hvis du har sikkerhetsrollen som systemansvarlig, kan du slette egendefinerte enheter som ikke er en del av en administrert løsning.  
  
> [!IMPORTANT]
>  Når du sletter en egendefinert løsning, slettes databasetabellene som lagrer data for denne enheten, og alle dataene de inneholder, går tapt. Alle tilknyttede poster som har en overordnet relasjon til den egendefinerte enheten, blir også slettet. Hvis du vil ha mer informasjon om overordnede relasjoner, kan du se [Opprett og rediger relasjoner mellom enheter](create-edit-entity-relationships.md).  
  
> [!NOTE]
> Den eneste måten å gjenopprette data fra en enhet som har blitt slettet på, er å gjenopprette databasen fra et punkt før enheten ble slettet. Mer informasjon: [Sikkerhetskopi- og gjenopprettingsforekomster](/dynamics365/customer-engagement/admin/backup-restore-instances)

Klikk på ![Slett kommando](media/delete.gif)-kommandoen på verktøylinjen mens du [viser enheter](#view-entities).

Bruk Slett-kommandoen på menylinjen mens du viser en enhet.

![Slett kommando](media/delete-custom-entity-solution-explorer.png)

> [!WARNING]
> Sletting av en enhet som inneholder data, fjerner alle dataene. Disse dataene kan bare hentes ved sikkerhetskopiering av databasen.

> [!NOTE]
> Hvis det finnes enhetsavhengigheter, får du feilmeldingen **Kan ikke slette komponent** med en **Detaljer**-kobling du kan bruke for å finne informasjon om hvorfor enheten ikke kan slettes. I de fleste tilfeller skjer dette fordi en avhengighet må fjernes. 
>
> Det kan være mer enn én avhengighet som blokkerer sletting av en enhet. Denne feilmeldingen viser kanskje bare den første. Hvis du vil ha en annen måte å finne avhengigheter på, kan du se [Identifiser enhetsavhengigheter](#identify-entity-dependencies)



### <a name="identify-entity-dependencies"></a>Identifiser enhetsavhengigheter

Du kan identifisere avhengigheter som hindrer at en enhet slettes før du prøver å slette den. 

1. Klikk på **Vis avhengigheter** på kommandolinjen i løsningsutforsker når enheten er valgt.

![Vis kommando for avhengigheter](media/entity-show-dependencies.png)

2. Rull nedover listen til høyre i dialogvinduet som åpnes for å vise **Avhengighetstype**-kolonnen.

![Utgitt avhengighetstype](media/published-entity-dependency.png)

**Utgitte** avhengigheter blokkerer for sletting av en enhet. **Interne** avhengigheter løses av systemet.  

3. Hvis du fjerner disse utgitte avhengighetene, skal du kunne slette enheten.

 > [!NOTE]
 > En svært vanlig avhengighet er at et annet enhetsskjema har et oppslagsfelt for enheten du sletter. Fjerning av oppslagsfeltet fra feltet løser avhengigheten.

## <a name="create-custom-activity-entity"></a>Opprett en egendefinert aktivitetsenhet

Hvis du vil opprette enheten som en aktivitetsenhet, bruker du de samme trinnene som er beskrevet i dette emnet, bortsett fra at du må velge **Definer som en aktivitetsenhet**.

![Definer som aktivitetsenhet](media/create-activity-entity-solution-explorer.png)

En aktivitetsenhet er en spesiell type enhet som sporer handlinger en oppføring kan gjøre i en kalender. Mer informasjon: [Aktivitetsenheter](types-of-entities.md#activity-entities).

Når du angir dette alternativet, vil ikke alle egenskaper være kompatible. En aktivitetsenhet må overholde standardvirkemåten alle aktivitetsenheter bruker.

Primært felt-**navn** og **Visningsnavn** angis til **Emne**, og du kan ikke endre dette.

Følgende alternativer er angitt som standard og kan ikke endres:

 - **Tilbakemelding**
 - **Notater (inkludert vedlegg)**
 - **Tilkoblinger**
 - **Køer**
 - **Frakoblede funksjoner for Dynamics 365 for Outlook**

Følgende alternativer kan ikke angis:

- **Områder som viser denne enheten**
- **Aktiviteter**
- **Sending av e-post**
- **Utskriftsfletting**
- **Overvåking av enkeltposter**
- **Overvåking av flere poster**

## <a name="create-a-virtual-entity"></a>Opprett en virtuell enhet

Noen alternativer bruke bare ved oppretting av en virtuell enhet.

|Alternativ   |Beskrivelse  |
|---------|---------|
|**Virtuell enhet**|Om enheten er en virtuell enhet.|
|**Datakilde**|Datakilden for enheten.|

Mer informasjon: [Opprett og rediger virtuelle enheter som inneholder data fra en ekstern datakilde](create-edit-virtual-entities.md)

### <a name="see-also"></a>Se også
[Opprett og rediger enheter i Common Data Service for apper](create-edit-entities.md)<br />
[Opplæring: Opprette en egendefinert enhet som har PowerApps-komponenter](/powerapps/maker/common-data-service/create-custom-entity)<br />
[Opprette en løsning](create-solution.md)