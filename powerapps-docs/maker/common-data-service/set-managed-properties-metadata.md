---
title: Angi forvaltede egenskaper i Common Data Service for Apps-metadata | MicrosoftDocs
description: Lær hvordan du angir forvaltede egenskaper for metadataelementer i en løsning
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
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="set-managed-properties-in-common-data-service-for-apps-metadata"></a>Angi forvaltede egenskaper i Common Data Service for Apps-metadata 

Forvaltede egenskaper er bare aktuelt når du inkluderer metadata med en administrert løsning og importerer den til et annet miljø. Disse innstillingene lar løsningsutviklere få litt kontroll over tilpassingsnivået de vil at brukere som installerer forvaltede løsninger, skal ha. 

> [!TIP]
> Det er vanligvis en god idé å tillate personer å utvide metadata i løsningen som fungerer med forretningsdata. Dette gjør at de kan tilpasse løsningen deres etter behov på samme måte som de kan for standardenheter.
>
>For metadata som inneholder funksjoner som støtter løsningen, men ikke inneholder forretningsdata, er det lurt å begrense hvilke tilpassinger som er tillatt.

Hvis du angir forvaltede egenskaper, må du gjøre det ved hjelp av løsningsutforskeren.

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]

## <a name="entity-managed-properties"></a>Forvaltede egenskaper for enhet

Når du [viser enheter](create-edit-entities-solution-explorer.md#view-entities), velg enheten, og velg **Forvaltede egenskaper** på menylinjen.  Dette åpner dialogboksen **Angi forvaltede egenskaper**.

![Angi forvaltede egenskaper for enhet](media/set-managed-properties.png)
  
Enheter har flere forvaltede egenskaper enn alle andre typer løsningskomponenter. Hvis enheten kan tilpasses, kan du angi følgende alternativer:  

|Alternativ|Beskrivelse|
|--|--|
|**Kan tilpasses** |Kontroller alle de andre alternativene. Hvis dette alternativet er `False`, er ingen av de andre innstillingene aktuelle. Når det er `True`, kan du angi de andre tilpassingsalternativene. Når `False`, er det tilsvarende til å sette alle andre alternativer til usann.|
|**Visningsnavnet kan endres**|Om visningsnavnet for enheten kan endres.|
|**Kan endre tilleggsegenskaper** |Gjelder for alt som er ikke dekket av andre alternativer.|
|**Nye skjemaer kan opprettes**|Om nye skjemaer kan opprettes for enheten.|
|**Nye diagrammer kan opprettes**|Om nye diagrammer kan opprettes for enheten.|
|**Nye visninger kan opprettes** |Om nye visninger kan opprettes for enheten.|
|**Kan endre hierarkisk relasjon**|Om innstillinger for hierarkiske relasjoner kan endres. Mer informasjon: [Definere og spørre etter hierarkisk relaterte data](define-query-hierarchical-data.md)|
|**Kan endringssporing aktiveres** |Om egenskapen **Endringssporing** kan endres.|
|**Kan aktivere synkronisering til ekstern søkeindeks** |Om enheten kan konfigureres til å aktivere relevanssøk. Mer informasjon: [Konfigurere relevanssøk for å forbedre søkeresultatene og ytelsen](/dynamics365/customer-engagement/admin/configure-relevance-search-organization) |

## <a name="field-managed-properties"></a>Feltadministrerte egenskaper

Se [Opprette og redigere felt for Common Data Service for Apps ved hjelp av løsningsutforskeren i PowerApps](create-edit-field-solution-explorer.md) for informasjon om hvordan du redigerer felt.

Når du [viser felt](create-edit-field-solution-explorer.md#view-fields), velger du et egendefinert felt fra en uadministrert løsning, og velg deretter **Flere handlinger** >  **Forvaltede egenskaper** på menylinjen.

![Vise feltadministrerte egenskaper](media/view-field-managed-properties-solution-explorer.png)  
  
Dette åpner dialogboksen **Angi forvaltede egenskaper**.

![Angi feltadministrerte egenskaper](media/set-field-managed-property.png)

Alternativet **Kan tilpasses** kontrollerer alle de andre alternativene. Hvis dette alternativet er **Usann**, er ingen av de andre innstillingene aktuelle. Når det er **Sann**, kan du angi de andre tilpassingsalternativene.  
  
Hvis feltet kan tilpasses, setter du følgende alternativer til **Sann** eller **Usann**.  
  
- **Visningsnavnet kan endres**
- **Kan endre kravnivå** 
- **Kan endre tilleggsegenskaper** : Denne egenskapen kontrollerer alle tilpassinger som ikke har en bestemt forvaltet egenskap.

Å sette alle alternativene til **Usann** tilsvarer å sette **Kan tilpasses** til **Usann**.  

Aktiver valgene, og klikk **Angi** for å lukke dialogboksen.

> [!NOTE]
> Hvis dette feltet er et **Dato og klokkeslett**-felt, er en ekstra **Kan endre virkemåte for dato og klokkeslett**-egenskap tilgjengelig. Mer informasjon: [Virkemåte og format for dato og klokkeslett-feltet](behavior-format-date-time-field.md)

## <a name="relationship-managed-properties"></a>Egenskaper for administrert relasjon

Når du viser enhetsrelasjoner, velger du en relasjon fra en uadministrert løsning, og velg deretter **Flere handlinger** > **Forvaltede egenskaper** på menylinjen.
  
Med relasjoner er den eneste forvaltede egenskapen **Kan tilpasses**. Denne ene innstillingen styrer alle endringer som kan utføres for enhetsrelasjonen. 


### <a name="see-also"></a>Se også

[Forvaltede egenskaper](solutions-overview.md#managed-properties)<br />
[Opprette og redigere enheter ved hjelp av løsningsutforskeren](create-edit-entities-solution-explorer.md)<br />
[Opprette og redigere felt for Common Data Service for Apps ved hjelp av løsningsutforskeren i PowerApps](create-edit-field-solution-explorer.md)<br />
[Opprette og redigere 1:N- (én-til-mange) eller N:1-enhetsrelasjoner (mange-til-én) med løsningsutforskeren](create-edit-1n-relationships-solution-explorer.md)<br />
[Opprette N:N-enhetsrelasjoner (mange-til-mange) i Common Data Service for Apps ved hjelp av løsningsutforskeren](create-edit-nn-relationships-solution-explorer.md)
