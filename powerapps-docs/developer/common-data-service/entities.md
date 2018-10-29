---
title: Enheter for Common Data Service for apper | Microsoft Docs
description: Lær om de tilgjengelige enhetene i Common Data Service for apper.
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
ms.date: 03/19/2018
ms.author: jdaly
search.audienceType:
- developer
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: f40c05c3bdab521cb1230be15cefc5dbb58eac18
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/24/2018
ms.locfileid: "42844230"
---
# <a name="common-data-service-for-apps-entities"></a>Enheter for Common Data Service for apper

Lagring av data er den viktigste funksjonen til Common Data Service for apper. Common Data Service inneholder et grunnleggende sett med enheter som gir struktur for data, som brukes av forretningsprogrammer. 

Du kan vise det grunnleggende settet med enheter i [Enhetsreferanse for Common Data Service for apper](reference/about-entity-reference.md).

## <a name="modify-entities"></a>Endre enheter

Du kan endre enhetsmetadataene ved bruk av flere ulike metoder.

### <a name="use-designers"></a>Bruk utformingsverktøy

Det er flere måter du kan redigere enhetsmetadata på, ved bruk av utformingsverktøy.


|Utforming  |Beskrivelse  |
|---------|---------|
|powerapps.com|Den enkleste og vanligste tilnærmingen hvis du vil endre skjemaet, er å bruke [powerapps.com](https://web.powerapps.com/)-området for å redigere Common Data Service tilknyttet med et miljø. Endringer som tas i bruk her, utføres i konteksten til en uadministrert standardløsning for Common Data Service. <!-- TODO: Add link to topic that describes this -->|
|Standard løsningsutforsker for Common Data Services|Det er et annet utformingsverktøy tilgjengelig fra [powerapps.com](https://web.powerapps.com/)-området når du redigerer Common Data Service. **Advanced**-knappen nede til venstre åpner løsningsutforsker for standardløsningen Common Data Service. |
|Løsningsutforsker for løsningen |Hvis du distribuerer en løsning, må du opprette eventuelle nye enheter, attributter eller relasjoner i konteksten til den uadministrerte løsningen du skal bruke til å utvikle løsningen. <br /> Mer informasjon: [Opprett en løsningsutgiver og løsning](introduction-solutions.md#create-a-solution-publisher-and-solution)|
|Fra redigeringsprogrammet for skjema|Når du redigerer et modelldrevet appskjema for en enhet, kan du klikke på**Nytt felt**-knappen i **feltutforsker**. Hvis du oppretter et oppslagsfelt, oppretter du en ny enhetsrelasjon for å støtte det.|

### <a name="import-a-solution"></a>Importer en løsning

En løsning kan inneholde enhetsmetadata og andre tilpassede komponenter. Disse enhetene inkluderes hvis du importerer en administrert eller uadministrert løsning i leieren for Common Data Service for apper, eller eksisterende enheter utvides med de nye enhetsmetadataene de inneholder.

### <a name="from-a-data-source-using-power-query"></a>Fra en datakilde som bruker Power Query

Du kan opprette nye enheter og fylle dem med data ved bruk av Power Query. Mer informasjon: [Legg til data i en enhet i Common Data Service ved hjelp av Power Query](../../maker/common-data-service/data-platform-cds-newentity-pq.md).

### <a name="use-metadata-services"></a>Bruk metadatatjenester

Nettjenestene som vises i Common Data Service inkluderer muligheten til å opprette, lese, skrive og slette enhetsmetadata. Disse tjenestene brukes oftest til å lese metadataene. Det er fordi dataene kan informere koden ved kjøring om hvordan miljøet har blitt tilpasset.

Mer informasjon: [Metadatatjenester](use-web-services.md#metadata-services)

## <a name="entity-metadata"></a>Enhetsmetadata

Datamodellen er definert som metadata som lagres i Common Data Service. Dataene om skjemaet er kjent som *enhetsmetadata*. 

- [EntityMetadata-klassen](/dotnet/api/microsoft.xrm.sdk.metadata.entitymetadata) definerer dette med organisasjonstjenesten. 
- [EntityMetadata EntityType](/dynamics365/customer-engagement/web-api/entitymetadata) definerer dette for Web API-en. 

Enhetsmetadataene inneholder følgende informasjon:


|Data  |Beskrivelse  |
|---------|---------|
|Enhetsegenskaper|Hver enhet har omtrent 100 egenskaper som beskriver hvordan den identifiseres, og hva som kan gjøres med den.  Mer informasjon: [Enhetsmetadata](entity-metadata.md)|
|Attributter|`Attributes`-egenskapen for enheten er en samling av attributter. Hver attributt har omtrent 50 egenskaper som beskriver hvordan den identifiseres, datatypen den inneholder, hvordan den er formatert, og hva som kan gjøres med den. Mer informasjon: [Attributtmetadata](entity-attribute-metadata.md).|
|Relasjoner|Tre av enhetsegenskapene er samlinger av relasjoner mellom enheter. Disse samlingene inneholder ulike typer relasjoner: mange-til-mange, mange-til-én og én-til-mange. Mer informasjon: [Metadata for enhetsrelasjoner](entity-relationship-metadata.md)|
|Rettigheter|Én av enhetsegenskapene er en samling av mellom null og åtte rettigheter som identifiserer typen dataoperasjoner som kan utføres på den enheten, ved bruk av en unik identifikator som er knyttet til hver enkelt. Disse operasjonene inneholder: *Tilføye*, *AppendTo*, *Tilordne*, *Opprette*, *Slette*, *Lese*, *Dele* og *Skrive*.|
|Nøkler|Hver enhet har som standard en enkel GUID-attributt (global unik identifikator), og `Keys`-egenskapen er en tom samling. Du kan legge til alternative nøkler i en enhet. Mer informasjon: [Enhetsnøkler](entity-metadata.md#entity-keys)|

> [!TIP]
> Hvis du utvikler en forståelse av enhetsmetadataene i systemet, er det enklere å forstå hvordan plattformen Common Data Service fungerer. Mange av egenskapene kontrollerer også hva enhetene i modelldrevne apper kan kjøre. Utformingsprogrammene som er tilgjengelig for å redigere metadata, kan ikke vise alle detaljene fra metadataene. Du kan installere en modelldrevet app med navnet Metadata Browser. Ved bruk av appen kan du vise alle de skjulte enhetene og metadataegenskapene i systemet. Hvis du vil ha mer informasjon, kan du se [Dynamics 365 Customer Engagement – Veiledning for utviklere: Bla gjennom metadataene for organisasjonen](/dynamics365/customer-engagement/developer/browse-your-metadata)

### <a name="see-also"></a>Se også

[Oversikt for utviklere – Common Data Service for apper](overview.md)


