---
title: Angi forvaltede egenskaper i Common Data Service for Apps-metadata | MicrosoftDocs
description: Lær hvordan du angir forvaltede egenskaper for metadata-elementer i en løsning
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
- powerapps
author: Mattp123
ms.assetid: edaa7d4a-a95f-4d66-a9d9-2ad6051332f7
caps.latest.revision: 41
ms.author: matp
manager: kvivek
ms.openlocfilehash: 46727f5a46e3fd518da52fac7d08a6e43992c00d
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/08/2018
ms.locfileid: "39692656"
---
# <a name="set-managed-properties-in-common-data-service-for-apps-metadata"></a>Angi forvaltede egenskaper i Common Data Service for Apps-metadata 

Forvaltede egenskaper gjelder bare når du inkluderer metadata med en administrert løsning og importerer den til et annet miljø. Disse innstillingene tillater at en løsningsmaker har noe kontroll over nivået av tilpassinger de vil tillate for personer som installerer den administrerte løsningen. 

> [!TIP]
> Det er vanligvis en god idé å tillate personer å utvide metadata i løsningen som fungerer med forretningsdata. Dette gjør at de kan skreddersy løsningen etter behov, på samme måte som de kan for standardenheter.
>
>For metadata som gir funksjonalitet for å støtte løsningen, men som ikke inneholder forretningsdata, er det lurt å begrense hvilke tilpasninger som er tillatt.

Angitte forvaltede egenskaper må gjøres ved hjelp av løsningsutforsker.

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]

## <a name="entity-managed-properties"></a>Forvaltede egenskaper for enhet

Velg enhet og [Forvaltede egenskaper](create-edit-entities-solution-explorer.md#view-entities) på menylinjen når du **viser enheter**.  Dette åpner dialogboksen **Angi forvaltede egenskaper**.

![Angi forvaltede egenskaper for enhet](media/set-managed-properties.png)
  
Enheter har flere forvaltede egenskaper enn alle andre typer løsningskomponenter. Hvis enheten kan tilpasses, kan du angi følgende alternativer:  

|Alternativ|Beskrivelse|
|--|--|
|**Kan tilpasses** |Kontrollerer alle andre alternativer. Ingen av de andre innstillingene gjelder hvis dette alternativet er `False`. Når det er `True`, kan du angi de andre tilpassingsalternativene. Når `False`, er det det samme som å angi alle andre alternativer til usann.|
|**Visningsnavn kan endres**|Om visningsnavnet for enheten kan endres.|
|**Kan endre flere egenskaper** |Gjelder for alt som ikke dekkes av andre alternativer.|
|**Nye skjemaer kan opprettes**|Om nye skjemaer kan opprettes for enheten.|
|**Nye diagrammer kan opprettes**|Om nye skjemaer kan opprettes for enheten.|
|**Nye visninger kan opprettes** |Om nye visninger kan opprettes for enheten.|
|**Kan endre hierarkisk relasjon**|Om innstillingene for hierarkiske relasjoner kan endres. Mer informasjon: [Definer og spør hierarkisk-relaterte data](define-query-hierarchical-data.md)|
|**Kan endringssporing aktiveres** |Om enhetsegenskapen **Endringssporing** kan endres.|
|**Kan aktivere-synkronisering til eksterne søkeindeks** |Angir om enheten kan konfigureres for å aktivere relevanssøk. Mer informasjon: [Konfigurer relevanssøk for å forbedre søkeresultater og ytelse](/dynamics365/customer-engagement/admin/configure-relevance-search-organization) |

## <a name="field-managed-properties"></a>Feltforvaltede egenskaper

Se [Opprett og rediger felter for Common Data Service for Apps ved bruk av løsningsutforsker for PowerApps](create-edit-field-solution-explorer.md), hvis du vil ha mer informasjon om hvordan du redigerer felt.

Velg et egendefinert felt fra en uadministrert løsning når du [viser felter](create-edit-field-solution-explorer.md#view-fields), og velg deretter **Flere handlinger** >  **Administrerte egenskaper** på menylinjen.

![Vis feltforvaltede egenskaper](media/view-field-managed-properties-solution-explorer.png)  
  
Dette åpner dialogboksen **Angi forvaltede egenskaper**.

![Vis feltforvaltede egenskaper](media/set-field-managed-property.png)

**Kan tilpasses**-alternativet kontrollerer alle andre alternativer. Ingen av de andre innstillingene gjelder hvis dette alternativet er **Usann**. Du kan angi de andre tilpassingsalternativene når det er **Sann**.  
  
Hvis feltet kan tilpasses, setter du følgende alternativer til **Sann** eller **Usann**.  
  
- **Visningsnavn kan endres**
- **Kan endre kravnivå** 
- **Kan endre tilleggsegenskaper** : Denne egenskapen kontrollerer eventuelle andre tilpassinger som ikke har en bestemt forvaltet egenskap.

Hvis alle de enkelte alternativene er satt til **Usann**, er dette det samme som å angi **Kan tilpasses** til **Usann**.  

Bruk valgene og klikk på **Angi** for å lukke dialogboksen.

> [!NOTE]
> En tilleggsegenskap for **Kan endre virkemåte for dato og klokkeslett** er tilgjengelig hvis dette feltet er et **Dato og klokkeslett**-felt. Mer informasjon: [Virkemåte og format for dato og klokkeslett-feltet](behavior-format-date-time-field.md)

## <a name="relationship-managed-properties"></a>Administrerte relasjonsegenskaper

Velg en relasjon fra en uadministrert løsning når du viser enhetsrelasjoner, og velg deretter **Flere handlinger** > **Forvaltede Egenskaper** på menylinjen.
  
Den eneste forvaltede egenskapen for relasjoner, er **Kan tilpasses**. Denne enkle innstillingen kontrollerer alle endringer som kan gjøres i enhetsrelasjonen. 


### <a name="see-also"></a>Se også

[Forvaltede egenskaper](solutions-overview.md#managed-properties)<br />
[Opprett og rediger enheter ved hjelp av løsningsutforsker](create-edit-entities-solution-explorer.md)<br />
[Opprett og rediger felter for Common Data Service for Apps ved bruk av løsningsutforsker for PowerApps](create-edit-field-solution-explorer.md)<br />
[Opprett og rediger én-til-mange eller mange-til-én-enhetsrelasjoner ved hjelp av løsningsutforsker](create-edit-1n-relationships-solution-explorer.md)<br />
[Opprett mange-til-mange-enhetsrelasjoner i Common Data Service for Apps ved hjelp av løsningsutforsker](create-edit-nn-relationships-solution-explorer.md)