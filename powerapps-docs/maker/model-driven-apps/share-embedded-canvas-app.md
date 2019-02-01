---
title: Dele en innebygd lerretapp | MicrosoftDocs
ms.custom: ''
ms.date: 01/07/2019
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: get-started-article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - PowerApps
author: Aneesmsft
ms.author: matp
manager: kvivek
tags:
  - PowerApps maker portal impact
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="share-an-embedded-canvas-app"></a>Dele en innebygd lerretapp
[!INCLUDE [cc-beta-prerelease-disclaimer](../../includes/cc-beta-prerelease-disclaimer.md)]

Dette emnet forklarer hvordan du deler en innebygd lerretapp som du allerede har opprettet.

Når du har opprettet og lagt til en innebygd lerretapp i et modelldrevet skjema, må du kontrollere at alle brukere som har tilgang til det modelldrevne skjemaet, også har tilgang til lerretappen og dataene den bruker. Se følgende retningslinjer:
-   Dele den innebygde lerretappen med alle i organisasjonen, en sikkerhetsgruppe eller bestemte brukere. Mer informasjon: [Dele en app](../canvas-apps/share-app.md#share-an-app).
-   Kontroller at brukerne har riktige rettigheter for Common Data Service-enheter som den innebygde lerretappen bruker. Mer informasjon: [Behandle enhetstillatelser](../canvas-apps/share-app.md#manage-entity-permissions)
-   Kontroller at brukerne har riktige rettigheter for data i skytjenester som den innebygde lerretappen bruker, for eksempel SharePoint eller OneDrive. Fremgangsmåten for å dele er spesifikk for hver skytjeneste og utenfor omfanget av PowerApps.

> [!NOTE]
> For øyeblikket kan du ikke bruke **Lerretapp**-rettigheten i en sikkerhetsrolle for å gi appbrukere tilgang til enten en innebygd eller frittstående lerretapp.

Innebygde lerretapper er også løsningsavhengige. Som standard opprettes innebygde lerretapper i den samme løsningen som det vertsmodelldrevne skjemaet. Hvis du vil flytte den innebygde lerretappen fra ett miljø til et annet, eksporterer og importerer du innebygde lerretapper som en del av en løsning som alle andre komponenter.

## <a name="see-also"></a>Se også
[Bygge inne en lerretapp i et modelldrevet skjema](embed-canvas-app-in-form.md) <br />
[Sende gjeldende oppføring som datakontekst til en innebygd lerretapp](pass-current-embedded-canvas-app.md) <br />
[Sende en liste over relaterte oppføringer som datakontekst til en innebygd lerretapp](pass-related-embedded-canvas-app.md) <br />
[Retningslinjer for arbeid med innebygde lerretapper](embedded-canvas-app-guidelines.md)
