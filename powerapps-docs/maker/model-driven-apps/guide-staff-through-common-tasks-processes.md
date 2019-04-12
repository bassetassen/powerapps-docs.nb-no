---
title: Bruke egendefinert forretningslogikk med forretningsregler og flyter i modelldrevne apper | MicrosoftDocs
description: Få informasjon om de ulike typene forretningslogikk du kan bruke appen
ms.custom: ''
ms.date: 08/02/2018
ms.reviewer: ''
ms.service: powerapps
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: get-started-article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
ms.assetid: 0b4e6602-5701-4859-81cc-6f6fe50901b2
caps.latest.revision: 44
author: Mattp123
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="apply-custom-business-logic-with-business-rules-and-flows-in-model-driven-apps"></a>Bruke egendefinert forretningslogikk med forretningsregler og flyter i modelldrevne apper

En av hovedårsakene til at personer bruker modelldrevne apper, er at de kan definere og håndheve konsekvente forretningsprosesser. Konsekvente prosessene er med på å sikre at de som bruker en modelldrevet app, kan fokusere på arbeidet sitt og slippe å huske hvordan et sett med manuelle trinn utføres. 

## <a name="business-rules"></a>Forretningsregler

Forretningsregler har et enkelt grensesnitt for å implementere og vedlikeholde regler som endres og brukes ofte. *Omfanget* til en forretningsregel definerer hvor forretningsregelen skal kjøres:

|||  
|-|-|  
|**Hvis du velger dette elementet...**|**Omfanget angis til...**|  
|**Enhet**|Alle skjemaer og server|  
|**Alle skjemaer**|Alle skjemaer|  
|Bestemt skjema (for eksempel **Konto**-skjema)|Bare dette skjemaet| 

Hvis du vil ha mer informasjon om å definere forretningsregler for et skjema i en modelldrevet app, kan du se [Opprette forretningsregler for å bruke logikk i et modelldrevet appskjema](create-business-rules-recommendations-apply-logic-form.md).

> [!NOTE]
> Hvis du vil definere en forretningsregel for en enhet slik at den gjelder på servernivået for både *lerretsapper* og *modelldrevne apper*, kan du se [Opprette en forretningsregel for en enhet](/powerapps/maker/common-data-service/data-platform-create-business-rule).

## <a name="flows"></a>Flyter  
  
Microsoft Flow inneholder flere typer prosesser, og hver enkelt kan være utformet for ulike formål:  

-   Automatiske flyter. Opprett en flyt som automatisk utfører én eller flere oppgaver når den utløses av en hendelse. Mer informasjon: [Opprette en flyt](/flow/get-started-logic-flow).
    
-   Knappeflyter. Utfør repeterende oppgaver ved å trykke på en knapp på mobilenheten. Hvis du vil ha mer informasjon: [innføring i knappeflyter](/flow/introduction-to-button-flows)
  
-   Planlagte flyter. Opprett en flut som utfører én eller flere aktiviteter i en tidsplan, for eksempel én gang per dag, på en bestemt dato eller etter et bestemt klokkeslett. Mer informasjon: [Kjøre flyter etter en tidsplan](/flow/run-scheduled-tasks)
  
-   Forretningsprosessflyter.  Du kan sikre at brukere skriver inn data konsekvent og følger de samme trinnene hver gang de arbeider i en app, ved å opprette en forretningsprosessflyt. Mer informasjon: [Oversikt over forretningsprosessflyter](/flow/business-process-flows-overview)

-   Arbeidsflyter og handlinger. Dynamics 365 Customer Engagement-tilpassere er kanskje kjent med klassiske Common Data Service-prosesser, som er arbeidsflyter og handlinger. Mer informasjon: [Bruke arbeidsflytprosesser](/flow/workflow-processes) og [Handlingsoversikt](/flow/actions)
  
## <a name="next-step"></a>Neste trinn

[Opprette forretningsregler for å bruke logikk i et modelldrevet appskjema](create-business-rules-recommendations-apply-logic-form.md)

### <a name="see-also"></a>Se også

[Bruke forretningslogikk med Common Data Service](../common-data-service/cds-processes.md)
