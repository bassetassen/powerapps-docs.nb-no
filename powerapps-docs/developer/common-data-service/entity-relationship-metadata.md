---
title: Metadata for enhetsrelasjoner | Microsoft Docs
description: Lær om bruken av metadata for enhetsrelasjoner i Common Data Service for apper.
services: ''
suite: powerapps
documentationcenter: na
author: JimDaly
manager: faisalmo
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/12/2018
ms.author: jdaly
search.audienceType:
- developer
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: ea59e1eea1c0a85c2de1f2d654c10ed687ffe858
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/24/2018
ms.locfileid: "42863521"
---
# <a name="entity-relationship-metadata"></a>Metadata for enhetsrelasjoner

Når du ser på løsningsutforsker eller de tre løsningssamlingene i `EntityMetadata`, tror du kanskje at det finnes tre typer enhetsrelasjoner. Det finnes faktisk bare to, som vist i den følgende tabellen.

|Relasjonstype|Beskrivelse|
|--|--|
|Én-til-mange<br />[OneToManyRelationshipMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.onetomanyrelationshipmetadata)|En enhetsrelasjon der én enhetspost for **Hovedenhet** kan være knyttet til mange andre **Relatert enhet**-poster, på grunn av et oppslagsfelt i den relaterte enheten.<br />Når du viser en hovedenhetspost, kan du se en liste over de relaterte enhetspostene som er tilknyttet.|
|Mange-til-mange<br />[ManyToManyRelationshipMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.manytomanyrelationshipmetadata)|En enhetsrelasjon som avhenger av en spesiell *relasjonsenhet*, som noen ganger kalles en *skjæringspunktenhet*, så mange poster i én enhet kan være relatert til mange poster i en annen enhet.<br />Når du viser poster i begge enhetene i en mange-til-mange-relasjon, kan du se en liste over alle postene i den andre enheten som er knyttet til den.|

samlingen `EntityMetadata` `ManyToOneRelationships` inneholder typene [OneToManyRelationshipMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.onetomanyrelationshipmetadata). Én-til-mange-relasjoner finnes mellom enheter, og de henviser til hver enhet som enten *Hovedkontakt* eller *Relatert enhet*. Den relaterte enheten, noen ganger kalt den *underordnede enheten*, har en oppslagsattributt der du kan lagre en referanse i en post fra hovedenheten, noen ganger kalt den *overordnede enheten*. En mange-ti-én-relasjon er bare en én-til-mange-relasjon sett fra den relaterte enheten.

> [!NOTE]
> Selv om relaterte enheter noen ganger kalles *underordnede enheter*, må du ikke forveksle disse med [underordnede enheter](entity-metadata.md#child-entities). De gjelder nemlig for hvordan sikkerhet tas i bruk i relaterte enheter.

Mer informasjon:
- [Tilpassingsveiledning for Dynamics 365 Customer Engagement: Opprett og rediger relasjoner mellom enheter](/dynamics365/customer-engagement/customize/create-edit-entity-relationships)
- [Dynamics 365 Customer Engagement – Veiledning for utviklere: Egendefiner metadata for enhetsrelasjon](/dynamics365/customer-engagement/developer/customize-entity-relationship-metadata)

## <a name="cascade-configuration"></a>Overlappet konfigurasjon

Når en én-til-mange-relasjon finnes, finnes det overlappende virkemåter som kan konfigureres for å beholde dataintegriteten og automatisere forretningsprosesser.

Mer informasjon:

- [Tilpassingsveiledning for Dynamics 365 Customer Engagement: Opprett 1:N-relasjoner (én-til-mange) eller N:1-relasjoner (mange-til-én) > Virkemåte for relasjon](/dynamics365/customer-engagement/customize/create-and-edit-1n-relationships#relationship-behavior)
- [Dynamics 365 Customer Engagement – Veiledning for utviklere: Virkemåte for enhetsrelasjon](/dynamics365/customer-engagement/developer/entity-relationship-behavior)


## <a name="create-a-hierarchy-of-entities"></a>Opprett et enhetshierarki

Du kan angi et hierarki ved å angi `IsHierarchical`-egenskapen til `true`, i en selvrefererende én-til-mange-relasjon.

Det muliggjør en opplevelse der du kan vise og samhandle med hierarkiet, ved bruk av modelldrevne apper. 

Utviklere kan ta i bruk nye typer spørringer basert på hierarkiet ved bruk av `Under`- og `Not Under`-operatorene.

Mer informasjon: [Dynamics 365 Customer Engagement – Veiledning for utviklere: Spør og visualiser hierarkisk beslektede data](/dynamics365/customer-engagement/customize/query-visualize-hierarchical-data)

### <a name="see-also"></a>Se også

[Enheter for Common Data Service for apper](entities.md)
