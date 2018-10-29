---
title: Vis eller skjul skjemaelementer for en modelldrevet app med PowerApps | MicrosoftDocs
description: Lær hvordan du kan vise eller skjuler fra elementer, for eksempel faner, inndelinger eller felter
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
ms.openlocfilehash: 86fafe70ae3bc04eff5e85a4baf3682c32427149
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/08/2018
ms.locfileid: "39697361"
---
# <a name="show-or-hide-model-driven-app-form-elements"></a>Vis eller skjul skjemaelementer for en modelldrevet app

 Flere typer skjemaelementer har muligheten for å bli vist eller skjult som standard. Faner, inndelinger, felter, iFrames og nettressurser tilbyr dette alternativet. Synligheten av disse elementene kan bli kontrollert til å opprette et dynamisk skjema for å gi et brukergrensesnitt som tilpasser seg betingelser i skjemaet, ved hjelp av skjemaskript eller forretningsregler.  
  
> [!NOTE]
>  Skjuling av skjemaelementer er ikke en anbefalt måte å fremtvinge sikkerhet på. Det finnes flere måter personer kan vise alle elementer og data i skjemaet på når elementer er skjult. 
  
 I stedet for å utforme skjemaer som er avhengige av skripter for å kontrollere synligheten av alternativer, bør du vurdere om forretningsprosessflyten, en dialogboks eller å bytte til et annet skjema, kan passe bedre for dine behov. Hvis du bruker skripter, må du kontrollere at et hvilket som helst element som kan være skjult, er skjult som standard. Bare vis den med skript når logikken tilsier det. Den vil ikke vises i presentasjoner som ikke støtter skript på denne måten.  

## <a name="next-steps"></a>Neste trinn

[Oversikt over brukergrensesnittet for skjemaredigeringsprogrammet ](form-editor-user-interface-legacy.md)