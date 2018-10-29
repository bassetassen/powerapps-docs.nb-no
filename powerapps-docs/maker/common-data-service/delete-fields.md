---
title: Slett felter i PowerApps | MicrosoftDocs
description: Lær hvordan du sletter felter
ms.custom: ''
ms.date: 06/20/2018
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
ms.assetid: 578ac950-da16-4ec6-a0a4-25f3aaa3b96e
caps.latest.revision: 33
ms.author: matp
manager: kvivek
tags: ''
ms.openlocfilehash: 82e560f063f2e46190420b6be5cef4cc55d9ab4f
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/08/2018
ms.locfileid: "39692667"
---
# <a name="delete-fields"></a>Slett felter

<a name="BKMK_DeletingFields"></a>   
 
 Hvis du har sikkerhetsrollen som systemansvarlig, kan du slette egendefinerte felter som ikke er en del av en administrert løsning. Når du sletter et felt, vil alle data som er lagret i feltet gå tapt. Den eneste måten å gjenopprette data fra et felt som har blitt slettet på, er å gjenopprette databasen fra et punkt før feltet ble slettet.  
  
 Før du kan slette en egendefinert enhet, må du fjerne alle avhengigheter som kan finnes de i andre løsningskomponentene. Åpne feltet og bruk knappen **Vis avhengigheter** på menylinjen for å vise eventuelle **Avhengighetskomponenter**. Hvis feltet for eksempel brukes i et skjema eller en visning, må du først fjerne referanser til feltet i disse løsningskomponentene.  
  
 Hvis du sletter et oppslagsfelt, slettes automatisk én-til-mange-enhetsrelasjon for den.  

 ## <a name="next-steps"></a>Neste trinn

 [Slett en egendefinert enhet](data-platform-delete-entity.md)
