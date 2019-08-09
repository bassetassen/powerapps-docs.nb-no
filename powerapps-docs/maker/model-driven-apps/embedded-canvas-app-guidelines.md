---
title: Retningslinjer for arbeid med innebygde lerretapper | MicrosoftDocs
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

# <a name="guidelines-on-working-with-embedded-canvas-apps"></a>Retningslinjer for arbeid med innebygde lerretapper
Dette emnet gir veiledning om hvordan du arbeider med innebygde lerretapper, samt nyttige tips for å feilsøke problemer som kan oppstå.

-   Innebygde lerretapper støttes bare med Enhetlig grensesnitt-modelldrevne apper.
-   Du kan bare aktivere én innebygd lerretapp per skjema. 
     - Du kan legge til flere innebygde lerretapper i skjemaet, men du kan bare aktivere én om gangen.
     - Hvis du prøver å aktivere mer enn én innebygd lerretapp i et modelldrevet skjema, får du meldingen "Du kan bare aktivere én lerretapp i et skjema".
     - For å aktivere eller deaktivere en innebygd lerretapp, se [Aktivere en innebygd lerretapp](#enable-an-embedded-canvas-app) og [Deaktivere en innebygd lerretapp](#disable-an-embedded-canvas-app).
-   Når du legger til en innebygd lerretapp i et modelldrevet skjema, bruk alltid et obligatorisk felt som garantert har en verdi. Hvis feltet ikke har en verdi, oppdateres ikke den innebygde lerretappen i henhold til endringer i data i det vertsmodelldrevne skjemaet.
-   Publisering av et modelldrevet skjema publiserer ikke også den innebygde lerretappen.
     - Innebygde lerretapper må publiseres uavhengig av det vertmodelldrevne skjemaet. Mer informasjon: [Publisere en app](../canvas-apps/save-publish-app.md#publish-an-app).
-   Hvis åpning av PowerApps Studio for å opprette eller redigere en innebygd lerretapp via **Tilpass**-knappen i egenskapene for lerretappkontrollen blokkeres på grunn av popup-blokkering i nettleseren, må du aktivere webområdet web.powerapps.com eller midlertidig deaktivere popup-blokkeringen og deretter velge **Tilpass** på nytt.
-   Innebygde lerretapper vises ikke når du oppretter en ny oppføring, fordi de må sendes en oppføringskontekst.
-   ModelDrivenFormIntegration.Item-objektet er skrivebeskyttet. 
     - Du må bruke Common Data Service-koblingen for å skrive data tilbake. Mer informasjon: [Common Data Service](/connectors/commondataservice/)
-   Innebygde lerretapper kan bare opprettes via det vertsmodelldrevne skjemaet. 
    - Det er ikke støtte for å legge til eksisterende lerretapper som innebygd i modelldrevne skjemaer.
    - Støtte for å bygge inn en eksisterende lerretapp i et modelldrevet skjema ved hjelp av app-ID, gis i en fremtidig oppdatering.
- Når du viser et modelldrevet skjema med en innebygd lerretapp, hvis det vises en feilmelding om "Beklager, vi fant ikke denne appen", må du forsikre deg om at den innebygde lerretappen er i den samme løsningen som det modelldrevne skjemaet.
- Når du viser et modelldrevet skjema med en innebygd lerretapp, hvis det vises en feilmelding om "Det ser ut til at du ikke har tilgang til denne appen. Be eieren om å dele den med deg", sørg for at forfatteren har delt den innebygde lerretappen med deg. Mer informasjon: [Dele en innebygd lerretapp](share-embedded-canvas-app.md).

## <a name="enable-an-embedded-canvas-app"></a>Aktivere en innebygd lerretapp
1. Velg feltet eller delrutenettkontrollen som er tilpasset til å vises som en innebygd lerretapp.
2. I dialogboksen **Feltegenskaper** (eller **Angi egenskaper** for delrutenettet) velger du **Kontroller**-kategorien.
3. I listen over kontroller velger du **Lerretapp**, og deretter velger du **Web**-alternativet.
4. Velg **OK**.

## <a name="disable-an-embedded-canvas-app"></a>Deaktivere en innebygd lerretapp
1. Velg feltet eller delrutenettkontrollen som er tilpasset til å vises som en innebygd lerretapp.
2. I dialogboksen **Feltegenskaper** (eller **Angi egenskaper** for delrutenettet) velger du **Kontroller**-kategorien.
3. I listen over kontroller velger du standardkontrollen, og deretter velger du **Web**-alternativet.
4. Velg **OK**.

## <a name="known-issues-and-limitations-with-embedded-canvas-apps"></a>Kjente problemer og begrensninger med innebygde lerretapper
- Den egendefinerte kontrollen for lerretappen støttes bare for bruk med **Web**-klienttypen. For øyeblikket støttes ikke **Telefon**- og **Nettbrett**-klienttypene.
- Du kan ikke bruke **Lerretapp**-rettigheten i en sikkerhetsrolle for å gi appbrukere tilgang til enten en innebygd eller frittstående lerretapp. For mer informasjon om å dele en innebygd lerretapp, kan du se: [Dele en innebygd lerretapp](share-embedded-canvas-app.md).
- Hvis du skriver tilbake de samme dataene som vises i det vertsmodelldrevne skjemaet, fortsetter skjemaet å vise gamle data helt til det blir oppdatert. En enkel måte å gjøre det på er å bruke [RefreshForm](embedded-canvas-app-actions.md#refreshformshowprompt)-metoden.

## <a name="see-also"></a>Se også
[Bygge inn en lerretapp i et modelldrevet skjema](embed-canvas-app-in-form.md) <br />
[Legge til en innebygd lerretapp i et modelldrevet skjema](embedded-canvas-app-add-classic-designer.md) <br />
[Redigere en innebygd lerretapp i et modelldrevet skjema](embedded-canvas-app-edit-classic-designer.md) <br />
[Tilpasse skjermstørrelsen og -retningen for en lerretapp som er innebygd i et modelldrevet skjema](embedded-canvas-app-customize-screen.md) <br />
[Utføre forhåndsdefinerte handlinger på vertsskjemaet fra en innebygd lerretapp](embedded-canvas-app-actions.md) <br />
[Egenskaper og handlinger for ModelDrivenFormIntegration-kontroll](embedded-canvas-app-properties-actions.md) <br />
[Dele en innebygd lerretapp](share-embedded-canvas-app.md) <br />
[Overføre innebygde lerretapper på modelldrevne skjemaer opprettet ved hjelp av offentlig forhåndsversjon av nyeste](embedded-canvas-app-migrate-from-preview.md) <br />
