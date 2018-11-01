---
title: Angi forvaltede egenskaper for felt i PowerApps | MicrosoftDocs
description: Finn ut hvordan du angir forvaltede egenskaper for et felt
ms.custom: ''
ms.date: 06/19/2018
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
ms.assetid: 4ddcfcf3-5604-4b93-a5ee-589d4fb97fa4
caps.latest.revision: 33
ms.author: matp
manager: kvivek
tags: null
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="set-managed-properties-for-fields"></a>Angi forvaltede egenskaper for felt

<a name="BKMK_SettingManagedProperties"></a>   

 Forvaltede egenskaper er bare aktuelt når du inkluderer felt i en administrert løsning og importerer løsningen til et annet miljø. Disse innstillingene lar løsningsutviklere få litt kontroll over tilpassingsnivået som brukere som installerer administrerte løsninger, kan ha når de tilpasser feltet. Hvis du vil angi forvaltede egenskaper for et felt, velger du **Forvaltede egenskaper** på menylinjen.  
  
 Alternativet **Kan tilpasses** kontrollerer alle de andre alternativene. Hvis dette alternativet er `False`, er ingen av de andre innstillingene aktuelle. Når det er `True`, kan du angi de andre tilpassingsalternativene.  
  
 Hvis feltet kan tilpasses, setter du følgende alternativer til `True` eller `False`.  
  
- **Visningsnavnet kan endres**  
  
- **Kan endre kravnivå**  
  
- **Kan endre tilleggsegenskaper**  
  
 Disse alternativene er selvforklarende. Hvis du angir alle de individuelle alternativene til `False`, kan du like godt også angi **Kan tilpasses** til `False`.  

 ## <a name="next-steps"></a>Neste trinn

 [Opprette og rediger felt](create-edit-fields.md)
