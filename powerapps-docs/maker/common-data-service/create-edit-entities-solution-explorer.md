---
title: Opprette og redigere enheter ved hjelp av løsningsutforskeren | MicrosoftDocs
description: Finn ut hvordan du oppretter en enhet ved hjelp av løsningsutforskeren
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
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="create-and-edit-entities-using-solution-explorer"></a>Opprette og redigere enheter ved hjelp av løsningsutforskeren

Du kan enkelt opprette en enhet ved hjelp av PowerApps-portalen i de vanligste situasjoner, men ikke alle funksjonene er implementert der. Når du må oppfylle kravene beskrevet i [Opprette og redigere enheter i Common Data Service for Apps](create-edit-entities.md), kan du gjøre dette ved å opprette eller redigere enheter ved hjelp av løsningsutforskeren.

## <a name="open-solution-explorer"></a>Åpne løsningsutforskeren

En del av navnet på enheter du oppretter, er tilpassingsprefikset. Dette angis basert på løsningsutgiveren for løsningen du arbeider i. Hvis du er interessert i tilpassingsprefikset, må du kontrollere at du arbeider i en ikke-administrert løsning der tilpassingsprefikset er det du vil bruke for denne enheten. Mer informasjon: [Endre løsningsutgiverprefikset](change-solution-publisher-prefix.md) 

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]

## <a name="view-entities"></a>Vise enheter

I løsningsutforskeren i **Komponenter**-noden velger du **Enheter**noden.

![Vise enheter i løsningsutforskeren](media/view-entities-solution-explorer.png)

## <a name="create-an-entity"></a>Opprette en enhet

Når du [viser enheter](#view-entities), velger du **Ny** for å åpne det nye enhetsskjemaet.

![nytt enhetsskjema i løsningsutforskeren](media/new-entity-form-solution-explorer.png)

Det nye enhetsskjemaet har to kategorier. **Generelt**-kategorien gjelder for enhetsalternativene. **Hovedfelt**-kategorien gjelder for alternativer for det spesielle feltet for enkeltlinje med tekst som hver enhet har, og som definerer teksten som vises når det finnes en kobling for å åpne enheten i et oppslagsfelt.

Hvis du vil ha mer informasjon om hver del, se følgende:
- [Konfigurere hovedfeltet](#configure-the-primary-field)
- [Konfigurere obligatoriske felt](#configure-required-fields)

> [!NOTE]
> Du kan også gjøre enheten til en egendefinert aktivitet. Dette alternativet endrer noen av standardvalgverdiene. Mer informasjon: [Opprette en egendefinert aktivitetsenhet](#create-custom-activity-entity)

Når du har angitt alternativene som er nødvendige for enheten, klikker du på ![Lagre, kommando](media/save-entity-icon-solution-explorer.png) for å opprette den egendefinerte enheten.

### <a name="configure-the-primary-field"></a>Konfigurere hovedfeltet

I **Hovedfelt**-kategorien kan du vanligvis godta standardverdiene for hovedfeltet, men du har følgende alternativer:

|Felt   |Beskrivelse  |
|---------|---------|
|**Visningsnavn**|Skriv inn den lokaliserbare etiketten som vil vises for dette feltet i skjemaer og lister. Standardverdien er **Navn**.|
|**Navn**|Angi navnet som brukes i systemet for dette feltet. Standardverdien er `<customization prefix>_name`|
|**Maksimumslengde**|Angi maksimumslengden for feltverdiene. Standardinnstillingen er 100.|

> [!NOTE]
> Disse alternativene brukes ikke hvis enheten er en aktivitetsenhet. Mer informasjon: [Opprette en egendefinert aktivitetsenhet](#create-custom-activity-entity)

### <a name="configure-required-fields"></a>Konfigurere obligatoriske felt

I **Generelt**-kategorien er noen av alternativene nødvendige før du kan lagre enheten.

|Felt   |Beskrivelse  |
|---------|---------|
|**Visningsnavn**|Dette er entallsnavnet for enheten som skal vises i appen.<br />Dette kan endres senere.|
|**Flertallsnavn**|Dette er flertallsnavnet for enheten som skal vises i appen.<br />Dette kan endres senere.|
|**Navn**|Dette feltet er forhåndsutfylt basert på visningsnavnet du angir. Det inkluderer tilpassingsprefikset for løsningsutgiveren.|
|**Eierskap**|Du kan velge enten bruker- eller teameid eller organisasjonseid. Mer informasjon: [Enhetseierskap](types-of-entities.md#entity-ownership)|

## <a name="edit-an-entity"></a>Redigere en enhet

Når du [viser enheter](#view-entities), velger du enheten du vil redigere, eller fortsetter å redigere en ny enhet du nettopp har lagret.

> [!NOTE]
> Standardenheter eller egendefinerte enheter som er en del av en administrert løsning, kan begrense endringer du kan bruke. Hvis alternativet ikke er tilgjengelig eller er deaktivert, kan du ikke gjøre endringen.

#### <a name="set-once-options"></a>Alternativer som kan angis én gang

Følgende alternativer kan angis én gang, og kan ikke endres etter at du har angitt dem. Pass på at du bare angir disse alternativene når du trenger dem.

<!-- 
Same data is presented in edit-entities.md
Both should point to this include
 -->
[!INCLUDE [cc_entity-set-once-options-table](../../includes/cc_entity-set-once-options-table.md)]

#### <a name="options-that-you-can-change"></a>Alternativer som du kan endre

Følgende egenskaper kan endres når som helst.

<!-- 
Same data is presented in edit-entities.md
Both should point to this include
 -->
[!INCLUDE [cc_entity-changeable-options-table](../../includes/cc_entity-changeable-options-table.md)]

Du kan også gjøre følgende endringer:
- [Opprette og redigere felt for Common Data Service for Apps](create-edit-fields.md)
- [Opprette og redigere relasjoner mellom enheter](create-edit-entity-relationships.md)
- [Opprette og utforme skjemaer](../model-driven-apps/create-design-forms.md)
- [Opprette en forretningsprosessflyt for å standardisere prosesser](/flow/create-business-process-flow)

## <a name="delete-an-entity"></a>Slette en enhet

Som en bruker med sikkerhetsrollen Systemadministrator, kan du slette egendefinerte enheter som ikke er en del av en administrert løsning.  
  
> [!IMPORTANT]
>  Når du sletter en egendefinert enhet, slettes databasetabellene som lagrer data for enheten, og alle data de inneholder, går tapt. Alle tilknyttede oppføringer som har en overordnet relasjon til den egendefinerte enheten, slettes også. Hvis du vil ha mer informasjon om overordnede relasjoner, kan du se [Opprette og redigere relasjoner mellom enheter](create-edit-entity-relationships.md).  
  
> [!NOTE]
> Den eneste metoden for å gjenopprette data fra en enhet som ble slettet, er å gjenopprette databasen fra et punkt før enheten ble slettet. Mer informasjon: [Sikkerhetskopiere og gjenopprette forekomster](/dynamics365/customer-engagement/admin/backup-restore-instances)

Når du [viser enheter](#view-entities), klikker du på ![Slett-kommandoen](media/delete.gif)-kommandoen på verktøylinjen.

Når du viser en enhet, bruker du Slett-kommandoen på menylinjen.

![Slett-kommandoen](media/delete-custom-entity-solution-explorer.png)

> [!WARNING]
> Sletting av en enhet som inneholder data, fjerner alle dataene. Disse dataene kan bare hentes ved hjelp av sikkerhetskopi av databasen.

> [!NOTE]
> Hvis det finnes enhetsavhengigheter, får du feilmeldingen **Kan ikke slette komponent** med en **Detaljer**-kobling du kan bruke til å finne informasjon om hvorfor enheten ikke kan slettes. I de fleste tilfeller er dette på grunn av en avhengighet som må fjernes. 
>
> Det kan være mer enn én avhengighet som blokkerer slettingen av en enhet. Denne feilmeldingen viser kanskje bare den første. For en annen måte å finne avhengigheter på, kan du se [Identifisere enhetsavhengigheter](#identify-entity-dependencies)



### <a name="identify-entity-dependencies"></a>Identifisere enhetsavhengigheter

Du kan identifisere avhengigheter som hindrer en enhet fra å slettes før du prøver å slette den. 

1. I løsningsutforskeren med enheten valgt, klikker du på **Vis avhengigheter** på kommandolinjen.

![Kommandoen Vis avhengigheter](media/entity-show-dependencies.png)

2. I dialogboksen som åpnes, ruller du listen til høyre for å vise **Avhengighetstype**-kolonnen.

![Publisert avhengighetstype](media/published-entity-dependency.png)

**Publiserte** avhengigheter blokkerer sletting av en enhet. **Interne** avhengigheter må løses av systemet.  

3. Fjerne disse publiserte avhengighetene, og du skal kunne slette enheten.

 > [!NOTE]
 > En vanlig avhengighet er at et annet enhetsskjema har et oppslagsfelt for enheten du sletter. Hvis du fjerner oppslagsfeltet fra skjemaet, løses avhengigheten.

## <a name="create-custom-activity-entity"></a>Opprette egendefinert aktivitetsenhet

Hvis du vil opprette enheten som en aktivitetsenhet, bruker du de samme trinnene som beskrives i dette emnet unntatt å velge **Definer som aktivitetsenhet**.

![Definere som aktivitetsenhet](media/create-activity-entity-solution-explorer.png)

En aktivitetsenhet er en spesiell type enhet som sporer handlinger som en oppføring kan opprettes for i en kalender. Mer informasjon: [Aktivitetsenheter](types-of-entities.md#activity-entities).

Hvis du velger dette alternativet, er ikke noen enhetsegenskaper kompatible. En aktivitetsenhet må være i samsvar med standard funksjonalitet som alle aktivitetsenheter bruker.

Hovedfeltet **Navn** og **Visningsnavn** settes til **Emne**, og du kan ikke endre dette.

Følgende alternativer er angitt som standard og kan ikke endres:

 - **Tilbakemelding**
 - **Notater (inkludert vedlegg)**
 - **Tilkoblinger**
 - **Køer**
 - **Frakoblet funksjon for Dynamics 365 for Outlook**

Følgende alternativer kan ikke angis:

- **Områder som viser denne enheten**
- **Aktiviteter**
- **Sending av e-post**
- **Utskriftsfletting**
- **Sporing av én oppføring**
- **Sporing av flere oppføringer**

## <a name="create-a-virtual-entity"></a>Opprette en virtuell enhet

Noen av alternativene brukes bare når du oppretter en virtuell enhet.

|Alternativ   |Beskrivelse  |
|---------|---------|
|**Virtuell enhet**|Om enheten er en virtuell enhet.|
|**Datakilde**|Datakilden for enheten.|

Mer informasjon: [Opprette og redigere virtuelle enheter som inneholder data fra en ekstern datakilde](create-edit-virtual-entities.md)

### <a name="see-also"></a>Se også
[Opprette og redigere enheter i Common Data Service for Apps](create-edit-entities.md)<br />
[Opplæring: Opprette en egendefinert enhet som har komponenter i PowerApps](/powerapps/maker/common-data-service/create-custom-entity)<br />
[Opprette en løsning](create-solution.md)
