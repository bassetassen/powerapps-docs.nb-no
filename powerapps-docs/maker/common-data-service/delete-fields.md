---
title: Slette felt i PowerApps | MicrosoftDocs
description: Lær hvordan du kan slette felt
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
tags: null
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="delete-fields"></a>Slette felt

<a name="BKMK_DeletingFields"></a>   
 
 Som en bruker med sikkerhetsrollen Systemadministrator, kan du slette eventuelle egendefinerte felt som ikke er en del av en administrert løsning. Når du sletter et felt, går eventuelle data som er lagret i feltet tapt. Den eneste metoden for å gjenopprette data fra et felt som ble slettet, er å gjenopprette databasen fra et punkt før feltet ble slettet.  
  
 Før du kan slette en egendefinert enhet, må du fjerne alle avhengigheter som finnes i andre løsningskomponenter. Åpne feltet, og bruke **Vis avhengigheter** på menylinjen til å vise eventuelle **Avhengige komponenter**. Hvis feltet for eksempel brukes i et skjema eller en visning, må du først fjerne referanser til felt i disse løsningskomponentene.  
  
 Hvis du sletter et oppslagsfelt, vil 1:N-enhetsrelasjonen for den automatisk bli slettet.  

 ## <a name="next-steps"></a>Neste trinn

 [Slette en egendefinert enhet](data-platform-delete-entity.md)
