---
title: Angi forvaltede egenskaper for felter i PowerApps | MicrosoftDocs
description: Lær å angi forvaltede egenskaper for et felt
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
tags: ''
ms.openlocfilehash: be3b04bbc324520904c765506e32d6027927e214
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/08/2018
ms.locfileid: "39697209"
---
# <a name="set-managed-properties-for-fields"></a>Angi forvaltede egenskaper for felter

<a name="BKMK_SettingManagedProperties"></a>   

 Forvaltede egenskaper gjelder bare når du inkluderer felter i en administrert løsning og importerer den til et annet miljø. Disse innstillingene tillater at en løsningsmaker har noe kontroll over nivået av tilpassinger personer som installerer den administrerte løsningen, kan ha når de tilpasser dette feltet. Hvis du vil angi forvaltede egenskaper for felt, velger du **Forvaltede egenskaper** på menylinjen.  
  
 **Kan tilpasses**-alternativet kontrollerer alle andre alternativer. Ingen av de andre innstillingene gjelder hvis dette alternativet er `False`. Når det er `True`, kan du angi de andre tilpassingsalternativene.  
  
 Hvis feltet kan tilpasses, setter du følgende alternativer til `True` eller `False`.  
  
- **Visningsnavn kan endres**  
  
- **Kan endre kravnivå**  
  
- **Kan endre flere egenskaper**  
  
 Disse alternativene er selvforklarende. Hvis du angir alle de enkelte alternativene til `False`, kan du like så godt angi **Kan tilpasses** til `False`.  

 ## <a name="next-steps"></a>Neste trinn

 [Opprette og redigere felter](create-edit-fields.md)