---
title: Dele en innebygd lerretapp | MicrosoftDocs
ms.custom: ''
ms.date: 06/25/2019
ms.reviewer: ''
ms.service: powerapps
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
Dette emnet forklarer hvordan du deler en innebygd lerretapp som du allerede har opprettet.

Når du har opprettet og lagt til en innebygd lerretapp i et modelldrevet skjema, må du kontrollere at alle brukere som har tilgang til det modelldrevne skjemaet, også har tilgang til lerretappen og dataene den bruker. Se følgende retningslinjer:
-   Dele den innebygde lerretappen med alle i organisasjonen, en sikkerhetsgruppe eller bestemte brukere. Mer informasjon: [Dele en app](../canvas-apps/share-app.md#share-an-app).
-   Kontroller at brukerne har riktige rettigheter for Common Data Service-enheter som den innebygde lerretappen bruker. Mer informasjon: [Behandle enhetstillatelser](../canvas-apps/share-app.md#manage-entity-permissions)
-   Kontroller at brukerne har riktige rettigheter for data i skytjenester som den innebygde lerretappen bruker, for eksempel SharePoint eller OneDrive. Fremgangsmåten for å dele er spesifikk for hver skytjeneste og utenfor omfanget av PowerApps.

> [!NOTE]
> For øyeblikket kan du ikke bruke **Lerretapp**-rettigheten i en sikkerhetsrolle for å gi appbrukere tilgang til enten en innebygd eller frittstående lerretapp.

Innebygde lerretapper er også løsningsavhengige. Som standard opprettes innebygde lerretapper i den samme løsningen som det vertsmodelldrevne skjemaet. Hvis du vil flytte den innebygde lerretappen fra ett miljø til et annet, eksporterer og importerer du innebygde lerretapper som en del av en løsning som alle andre komponenter.

## <a name="see-also"></a>Se også
[Bygge inn en lerretapp i et modelldrevet skjema](embed-canvas-app-in-form.md) <br />
[Legge til en innebygd lerretapp i et modelldrevet skjema](embedded-canvas-app-add-classic-designer.md) <br />
[Redigere en innebygd lerretapp i et modelldrevet skjema](embedded-canvas-app-edit-classic-designer.md) <br />
[Tilpasse skjermstørrelsen og -retningen for en lerretapp som er innebygd i et modelldrevet skjema](embedded-canvas-app-customize-screen.md) <br />
[Utføre forhåndsdefinerte handlinger på vertsskjemaet fra en innebygd lerretapp](embedded-canvas-app-actions.md) <br />
[Egenskaper og handlinger for ModelDrivenFormIntegration-kontroll](embedded-canvas-app-properties-actions.md) <br />
[Retningslinjer for arbeid med innebygde lerretapper](embedded-canvas-app-guidelines.md) <br />
[Overføre innebygde lerretapper på modelldrevne skjemaer opprettet ved hjelp av offentlig forhåndsversjon av nyeste](embedded-canvas-app-migrate-from-preview.md) <br />
