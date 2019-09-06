---
title: 'Opprette N:N-enhetsrelasjoner (mange-til-mange) i Common Data Service ved hjelp av løsningsutforskeren | MicrosoftDocs'
description: Lær hvordan du oppretter relasjoner av typen mange-til-mange
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
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="create-nn-many-to-many-entity-relationships-in-common-data-service-using-solution-explorer"></a>Opprette N:N-enhetsrelasjoner (mange-til-mange) i Common Data Service ved hjelp av løsningsutforskeren

Løsningsutforskeren har en måte for å opprette og redigere N:N (mange-til-mange) for Common Data Service.

[PowerApps-portalen](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) gjør det mulig for konfigurasjon av de vanligste alternativene, men enkelte alternativer kan bare angis ved hjelp av løsningsutforskeren. Mer informasjon:
- [Opprette mange-til-mange-enhetsrelasjoner (N:N)](create-edit-nn-relationships.md)
- [Opprett mange-til-en-enhetsrelasjoner i Common Data Service ved hjelp av PowerApps-portalen](create-edit-nn-relationships-portal.md)

  
## <a name="open-solution-explorer"></a>Åpne løsningsutforskeren

En del av navnet på egendefinerte relasjoner du oppretter, er tilpassingsprefikset. Dette angis basert på løsningsutgiveren for løsningen du arbeider i. Hvis du er interessert i tilpassingsprefikset, må du kontrollere at du arbeider i en ikke-administrert løsning der tilpassingsprefikset er det du vil bruke for denne enheten. Mer informasjon: [Endre løsningsutgiverprefikset](change-solution-publisher-prefix.md) 

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]

## <a name="view-entity-relationships"></a>Vise enhetsrelasjoner

I løsningsutforskeren utvider du **Enheter** og velger en enhet. Velg **N:N-relasjoner** i denne enheten.

![Vise N:N-enhetsrelasjoner](media/view-nn-entity-relationships-solution-explorer.png)

## <a name="create-relationships"></a>Opprette relasjoner

Når du [viser enhetsrelasjoner](#view-entity-relationships), velger du **Ny mange-til-mange-relasjon** på kommandolinjen.

> [!NOTE]
> Hvis kommandoen ikke er tilgjengelig, er ikke enheten kvalifisert for å opprette en egendefinert relasjon.

![Skjema for ny mange-til-mange-relasjon](media/new-nn-entity-relationship-form-solution-explorer.png)

I gruppen **Annen enhet** i **Enhetsnavn**-feltet velger du enheten som du vil opprette relasjonen med. Dette fyller ut feltene **Navn** og **Relasjonens enhetsnavn** i **Relasjonsdefinisjon**-gruppen.

Du kan klikke på ![Lagre enhetsrelasjon-knappen](media/save-entity-icon-solution-explorer.png) for å lagre enheten og fortsette å redigere. Mer informasjon: [Redigere relasjoner](#edit-relationships)

> [!NOTE]
> Hvis verdien **Navn** eller **Relasjonens enhetsnavn** allerede finnes i systemet, får du en feil når du lagrer. Rediger verdiene slik at de er unike, og prøv på nytt.

## <a name="edit-relationships"></a>Redigere relasjoner

Når du [viser enhetsrelasjoner](#view-entity-relationships), velger du enheten du vil redigere. 

> [!NOTE]
> Utgiveren av en administrert løsning kan hindre tilpassinger av relasjoner som er en del av deres løsning.

Følgende egenskaper for enhetsrelasjon kan redigeres når relasjonen opprettes.

> [!IMPORTANT]
> Når du har redigert disse egenskapene, må du publisere tilpassingene før de trer i kraft i modelldrevne apper.

### <a name="edit-display-options"></a>Redigere visningsalternativer

For både **Gjeldende enhet** og **Annen enhet** kan du redigere feltene for visningsalternativer som kontrollerer hvordan de relaterte enhetene vises for modelldrevne apper.

|Felt|Beskrivelse|
|--|--|
|**Visningsalternativ**|Hvordan listen med relaterte enheter skal vises. Mer informasjon: [Visningsalternativer](#display-options)|
|**Tilpasset etikett**|Angi den lokaliserbare teksten som skal brukes i stedet for flertallsnavnet når du velger **Bruk egendefinert etikett** som **Visningsalternativ**.|
|**Visningsområde**|Velg en av de tilgjengelige grupperingene for å vise listen. De tilgjengelige alternativene er: **Detaljer** (for *Felles*-gruppen), **Markedsføring**, **Salg** og **Service**. |
|**Visningsrekkefølge**|Styrer hvor navigasjonselementet skal plasseres innenfor det valgte visningsområdet. Området med tillatte tall starter med 10 000. Navigasjonsruteelementer med en lavere verdi vises over andre relasjoner med høyere verdier.|

<!-- TODO: Not sure whether Display Area or Display Order are still used anymore. Might only be used in the Outlook client?-->

#### <a name="display-options"></a>Visningsalternativer

Dette er de tilgjengelige visningsalternativene:

|Alternativ|Beskrivelse|
|--|--|
|**Ikke vis**|Ikke vis de relaterte enhetene for denne relasjonen.|
|**Bruk tilpasset etikett**|Når dette alternativet er valgt, aktiveres **Egendefinert etikett**-feltet slik at du kan angi den lokaliserbare teksten som skal brukes i stedet for flertallsnavnet.|
|**Bruk flertallsnavn**|Bruk flertallsvisningsnavnet som definert for den relaterte enheten.|

### <a name="searchable"></a>Søkbar

Du kan skjule relasjonen fra **Avansert søk** i modelldrevne apper ved å sette **Søkbar**-feltet til **Nei**.

## <a name="delete-relationships"></a>Slette relasjoner

Når du [viser enhetsrelasjoner](#view-entity-relationships), velger du enhetsrelasjonen du vil slette, og klikker på ![Slett-kommandoen](media/delete.gif)-kommandoen.

Hvis du sletter relasjonen, slettes relasjonsenheten som ble opprettet. Alle data som kobler enheter ved hjelp av relasjonen, vil gå tapt.

### <a name="see-also"></a>Se også

[Opprette mange-til-mange-enhetsrelasjoner (N:N)](create-edit-nn-relationships.md)<br />
[Opprett mange-til-en-enhetsrelasjoner i Common Data Service ved hjelp av PowerApps-portalen](create-edit-nn-relationships-portal.md)<br />
[Opprette og redigere 1:N-enhetsrelasjoner (én-til-mange) eller N:1-enhetsrelasjoner (mange-til-én)](create-edit-1n-relationships.md)
