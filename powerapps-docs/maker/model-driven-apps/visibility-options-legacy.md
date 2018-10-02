---
title: Vise eller skjule skjemaelementer for modelldrevne apper med PowerApps | MicrosoftDocs
description: 'Finn ut hvordan du kan vise eller skjule skjemaelementer, for eksempel kategorier, inndelinger eller felt'
ms.custom: ''
ms.date: 06/11/2018
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
ms.assetid: 7b9e8dc2-229c-455f-ae18-49e8d879ff71
caps.latest.revision: 63
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="show-or-hide-model-driven-app-form-elements"></a>Vise eller skjule skjemaelementer for modelldrevne apper

 Flere typer skjemaelementer har muligheten til å vises eller skjules som standard. Kategorier, inndelinger, felt, iFrames og webressurser har denne muligheten. Ved hjelp av skjemaskript eller forretningsregler kan synligheten av disse elementene kontrolleres for å opprette dynamiske skjemaer for å gi et brukergrensesnitt som tilpasser seg til betingelser i skjemaet.  
  
> [!NOTE]
>  Skjuling av skjemaelementer er ikke en anbefalt metode for å håndheve sikkerheten. Det finnes flere metoder for brukere for å vise alle elementene og dataene i skjemaet når elementer er skjult. 
  
 I stedet for å utforme skjemaer som er avhengige av skript for å styre synligheten av alternativer, bør du vurdere om en forretningsprosessflyt, en dialogboks eller å bytte til et annet skjema kan være bedre egnet til å dekke dine behov. Hvis du bruker skript, må du kontrollere at alle elementer som kan være skjult er skjult som standard. Vis det bare med skript når logikken tilsier det. På denne måten vil det ikke vises i presentasjoner som ikke støtter skript.  

## <a name="next-steps"></a>Neste trinn

[Oversikt over grensesnittet i skjemaredigeringsprogrammet](form-editor-user-interface-legacy.md)
