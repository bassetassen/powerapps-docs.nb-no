---
title: Opprette mange-til-mange-enhetsrelasjoner i Common Data Service ved hjelp av PowerApps-portalen | MicrosoftDocs
description: Lær hvordan du oppretter relasjoner av typen mange-til-mange
ms.custom: ''
ms.date: 06/11/2018
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

# <a name="create-many-to-many-entity-relationships-in-common-data-service-using-powerapps-portal"></a>Opprette mange-til-mange-enhetsrelasjoner i Common Data Service ved hjelp av PowerApps-portalen

[PowerApps-portalen](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) gir en enkel måte å opprette og redigere mange-til-mange-enhetsrelasjoner for Common Data Service.

Portalen gjør det mulig for konfigurasjon av de vanligste alternativene, men enkelte alternativer kan bare angis ved hjelp av løsningsutforskeren. Mer informasjon: 
- [Opprette N:N-enhetsrelasjoner (mange-til-mange)](create-edit-nn-relationships.md)
- [Opprette N:N-enhetsrelasjoner (mange-til-mange) i Common Data Service ved hjelp av løsningsutforskeren](create-edit-nn-relationships-solution-explorer.md)

## <a name="view-many-to-many-entity-relationships"></a>Vise mange-til-mange-enhetsrelasjoner

1. I [PowerApps-portalen](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) velger du utformingsmodusen **Modelldrevet** eller **Lerret**.
2. Velg **Data** > **Enheter**, og velg enheten som har relasjonene du vil vise.
3. Med **Relasjoner**-kategorien valgt kan du velge følgende visninger: 

 |Visning|Beskrivelse|
 |--|--|
 |**Alle**| Viser alle relasjonene for enheten|
 |**Egendefinert**|Viser bare egendefinerte relasjoner for enheten|
 |**Standard**|Viser bare standardrelasjonene for enheten|
<!-- TODO: What is the actual difference between All and Default? -->

![Relasjoner for forretningsforbindelsesenheten](media/view-account-relationships-portal.png)

Mange-til-mange-relasjoner vil ha **relasjonstypen** **mange-til-mange**.

> [!NOTE]
> Enheten du viser, trenger ikke ha noen **mange-til-mange**-relasjoner.

## <a name="create-relationships"></a>Opprette relasjoner

Når du [viser enhetsrelasjoner](#view-many-to-many-entity-relationships), velger du **Legg til relasjon** på kommandolinjen og velger **Mange-til-mange**.

![Velg relasjonstype](media/add-relationship-menu-portal.png)

I **Mange-til-mange**-panelet velger du ønsket enhet relatert til gjeldende enhet.

![Mange-til-mange-panelet med valgt forretningsforbindelsesenhet](media/many-to-many-panel-1.png)

Velg **Flere alternativer** for å vise feltene **Relasjonsnavn** og **Relasjonens enhetsnavn**.

![Mange-til-mange-panelet med Flere alternativer valgt](media/many-to-many-panel-2.png)

Verdiene for disse feltene genereres for deg basert på enhetene som er valgt.

> [!NOTE]
> Hvis du oppretter flere **Mange-til-mange**-relasjoner med de samme to enhetene, må du redigere de genererte **Relasjonsnavn**- og **Relasjonens enhetsnavn**-feltene slik at de blir unike.

Velg **OK** for å lukke **Mange-til-mange**-panelet. Relasjonen opprettes når du lagrer endringene i enheten. 

Når lagret, er det ikke noe som kan endres ved hjelp av [PowerApps-portalen](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc). Hvis du vil redigere egenskaper for relasjonen for modelldrevne apper, brukes [Løsningsutforsker](create-edit-nn-relationships-solution-explorer.md).

## <a name="delete-relationships"></a>Slette relasjoner

Når du [viser enhetsrelasjoner](#view-many-to-many-entity-relationships), velger du relasjonen du vil slette.

![Slette enhetsrelasjon](media/delete-entity-relationship-portal.png)

Du kan bruke **Slett relasjon**-kommandoen på kommandolinjen eller på radkontekstmenyen når du velger ellipsene (**...**).

Hvis du sletter mange-til-mange-relasjonen, slettes relasjonsenheten som ble opprettet. Alle data som kobler enheter ved hjelp av relasjonen, vil gå tapt.

### <a name="see-also"></a>Se også

[Opprette N:N-enhetsrelasjoner (mange-til-mange)](create-edit-nn-relationships.md)<br />
[Opprette N:N-enhetsrelasjoner (mange-til-mange) i Common Data Service ved hjelp av løsningsutforskeren](create-edit-nn-relationships-solution-explorer.md)
