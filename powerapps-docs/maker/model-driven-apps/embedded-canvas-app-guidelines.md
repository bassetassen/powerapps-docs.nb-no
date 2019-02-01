---
title: Retningslinjer for arbeid med innebygde lerretapper | MicrosoftDocs
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

# <a name="guidelines-on-working-with-embedded-canvas-apps"></a>Retningslinjer for arbeid med innebygde lerretapper
[!INCLUDE [cc-beta-prerelease-disclaimer](../../includes/cc-beta-prerelease-disclaimer.md)]

Dette emnet gir veiledning om hvordan du arbeider med innebygde lerretapper, samt nyttige tips for å feilsøke problemer som kan oppstå.

-   Innebygde lerretapper støttes bare med Enhetlig grensesnitt-modelldrevne apper.
-   Du kan bare aktivere én innebygd lerretapp per skjema. 
     - Du kan legge til flere innebygde lerretapper i skjemaet, men du kan bare aktivere én om gangen.
     - Hvis du prøver å aktivere mer enn én innebygd lerretapp i et modelldrevet skjema, får du meldingen "Du kan bare aktivere én lerretapp i et skjema".
     - For å aktivere eller deaktivere en innebygd lerretapp, se [Aktivere en innebygd lerretapp](#enable-an-embedded-canvas-app) og [Deaktivere en innebygd lerretapp](#disable-an-embedded-canvas-app).
-   Innebygde lerretapper kan bare opprettes, redigeres og spilles av via det vertsmodelldrevne skjemaet.
     - Du kan ikke opprette en innebygde lerretapp direkte utenfor konteksten av et modelldrevet skjema.
     - Åpning av en innebygde lerretapp for redigering eller avspilling utenfor konteksten av et modelldrevet skjema, støttes ikke.

     > [!NOTE]
     > Selv om det kan være mulig å åpne en innebygd lerretapp utenfor en modelldrevet app, støttes dette ikke.

-   Vær oppmerksom på følgende når du bruker en delrutenettkontroll til å legge til en innebygd lerretapp i et modelldrevet skjema.
     - Dataene (felt og verdier) som sendes til den innebygde lerretappen under kjøring, avhenger av visningen som er angitt som **Standardvisning** i delen **Datakilde** i egenskapene til delrutenettkontollen. Bruk bare feltene i den innebygde lerrettappen som er inkludert i visningen, eller legg dem til i visningen om nødvendig. Felt som ikke er inkludert i visningen, viser tomme verdier under kjøring. 
     - Filtervilkårene for en visning blir ikke brukt ved redigering. Derfor er ikke dataene som vises når du redigerer innebygde lerretapper, filtrert. Det er bare en liste over de få øverste oppføringene som du har tilgang til. Ved kjøring brukes filtervilkårene for visningen som forventet, og bare relevante data vises.
-   Når du bruker en feltkontroll til å legge til en innebygd lerretapp i et modelldrevet skjema, bruk alltid et obligatorisk felt som garantert har en verdi. Hvis feltet ikke har en verdi, oppdateres ikke den innebygde lerretappen i henhold til endringer i data i det vertsmodelldrevne skjemaet.
-   Publisering av et modelldrevet skjema publiserer ikke også den innebygde lerretappen.
     - Innebygde lerretapper må publiseres uavhengig av det vertmodelldrevne skjemaet. Mer informasjon: [Publisere en app](../canvas-apps/save-publish-app.md#publish-an-app).
-   Hvis åpning av PowerApps Studio for å opprette eller redigere en innebygd lerretapp via **Tilpass**-knappen i egenskapene for lerretappkontrollen, blokkeres på grunn av popup-blokkering i nettleseren, må du aktivere webområdet web.powerapps.com eller midlertidig deaktivere popup-blokkeringen og deretter velge **Tilpass** på nytt.
-   Innebygde lerretapper vises ikke når du oppretter en ny oppføring, fordi de må sendes en oppføringskontekst.
-   ModelDrivenFormIntegration.Data-objektet er skrivebeskyttet. 
     - Du må bruke Common Data Service-koblingen for å skrive data tilbake. Mer informasjon: [Common Data Service](/connectors/commondataservice/)
-   ModelDrivenFormIntegration.Data-objektet er en liste over oppføringer. 
     - Selv den gjeldende oppføringen overføres til den innebygde lerretappen via ModelDrivenFormIntegration.Data som en liste som inneholder én enkelt oppføring.
     - For å referere til oppføringen direkte kan du bruke [First-funksjonen](../canvas-apps/functions/function-first-last.md). Eksempel: First(ModelDrivenFormIntegration.Data).Name
-   Manuell endring av app-ID-en i egenskapene til lerretappkontrollen må unngås så langt som mulig.
     - App-ID-en til lerretappen genereres automatisk og fylles ut for deg. 
     - Hvis du av en eller annen grunn må redigere den manuelt, må du kontrollere at alle app-ID-er du bruker, tilsvarer en *innebygd* lerretapp og ikke bare en frittstående lerretapp.
     - Den innebygde lerretappen må også opprettes med samme datakontekst som det modelldrevne skjemaet sender.
     - Når du har oppdatert app-IDen, velg **Tilpass** for å koble til den nye appen.
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
- Den egendefinerte kontrollen for lerretappen støttes bare for bruk med **Web**-klienttypen. For øyeblikket støttes ikke **Telefon**- og **Nettbrett**-klienttypene. Mer informasjon: [Bruke egendefinerte kontroller for datavisualiseringer i modelldrevne apper](use-custom-controls-data-visualizations.md)
- Når du oppretter en ny oppføring, vises ikke en innebygd lerretapp i et skjema selv etter at oppføringen er lagret. 
-    ModelDrivenFormIntegration.Data-objektet fungerer for øyeblikket ikke med kontrollene for visningsskjema og redigeringsskjema.
- Du kan ikke bruke **Lerretapp**-rettigheten i en sikkerhetsrolle for å gi appbrukere tilgang til enten en innebygd eller frittstående lerretapp. For mer informasjon om å dele en innebygd lerretapp, kan du se: [Dele en innebygd lerretapp](share-embedded-canvas-app.md).
- Hvis du skriver tilbake de samme dataene som vises i det vertsmodelldrevne skjemaet, fortsetter skjemaet å vise gamle data helt til det blir oppdatert. 

## <a name="see-also"></a>Se også
[Bygge inne en lerretapp i et modelldrevet skjema](embed-canvas-app-in-form.md) <br />
[Sende gjeldende oppføring som datakontekst til en innebygd lerretapp](pass-current-embedded-canvas-app.md) <br />
[Sende en liste over relaterte oppføringer som datakontekst til en innebygd lerretapp](pass-related-embedded-canvas-app.md) <br />
[Dele en innebygd lerretapp](share-embedded-canvas-app.md)
