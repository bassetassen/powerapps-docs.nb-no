---
title: Egendefinert visualobjekt i PowerApps for Power BI | Microsoft Docs
description: Prosedyre og begrensninger for innebygging av en lerretsapp som bruker samme datakilde og kan filtreres som andre rapportelementer i Power BI
author: chmoncay
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 08/30/2019
ms.author: chmoncay
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 562811ebce59660d6033585868afd42da46442d5
ms.sourcegitcommit: 25a85b462515cb64f3f2b114864a682abf803f4a
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 09/03/2019
ms.locfileid: "70213936"
---
# <a name="powerapps-custom-visual-for-power-bi"></a>Egendefinert visualobjekt i PowerApps for Power BI

Power BI muliggjør datainnsikt og bedre beslutninger, mens PowerApps gjør det mulig for enhver å bygge og bruke apper som er koblet til forretningsdata. Ved å bruke det egendefinerte visualobjektet i PowerApps kan du overføre kontekstavhengige data til en lerretsapp, som oppdateres i sanntid etter hvert som du gjør endringer i en rapport. Nå kan brukerne av appen din få forretningsinnsikt og foreta handlinger direkte fra sine Power BI-rapporter og -instrumentbord.

## <a name="using-the-powerapps-custom-visual"></a>Bruk av et egendefinert visualobjekt fra PowerApps

La oss se på fremgangsmåten for å bruke det egendefinerte visualobjektet fra PowerApps i Power BI-rapporten.

1. Hent visualobjektet fra [AppSource](https://appsource.microsoft.com/product/power-bi-visuals/WA104381378?tab=Overview), eller importer det direkte i Power BI-tjenesten.

    ![Egendefinert visualobjekt i Marketplace](./media/powerapps-custom-visual/powerapps-store.png) 

2. Legg til PowerApps-visualobjektet i rapporten, og angi datafeltene som er knyttet til det.

    ![Velg rapportdata](./media/powerapps-custom-visual/add-visual-set-data.png)

    Du kan velge en eksisterende app eller opprette en, men rapporten må publiseres til Power BI-tjenesten og åpnes i Microsoft Edge eller Google Chrome.

3.  Hvis du velger å opprette en app, kan du velge hvilket miljø du vil opprette den i.

    ![Ny eller eksisterende app](./media/powerapps-custom-visual/create-new-or-choose-app.png)

    Hvis du velger å bruke en eksisterende app, vil visualobjektet be deg om å åpne appen i PowerApps. Deretter angir visualobjektet de nødvendige komponentene i appen, så Power BI kan sende data til PowerApps.

    Hvis du oppretter en ny app, oppretter PowerApps en enkel app med de nødvendige komponentene allerede konfigurert.

    ![Ny app](./media/powerapps-custom-visual/new-app.png)

4. Nå kan du bruke datafeltene du anga i trinn 2, i PowerApps Studio. `PowerBIIntegration`-objektet fungerer som alle andre skrivebeskyttede datakilder eller -samlinger i PowerApps. Du kan bruke objektet til å fylle ut en kontroll eller føye sammen og filtrere med andre datakilder.

    ![Egendefinert formel](./media/powerapps-custom-visual/custom-formula.png)

    Denne formelen kobler Power BI-data med kundedatakilden: `LookUp(Customer,Customer_x0020_Name=First(PowerBIIntegration.Data).Customer_Name)`

   Power BI-rapporten og forekomsten av PowerApps Studio som ble startet, deler en direkte datatilkobling. Når begge er åpne, kan du filtrere eller endre dataene i rapporten og se de oppdaterte dataene øyeblikkelig gjenspeilet i appen i PowerApps Studio.

5. Når du er ferdig med å bygge eller gjøre endringer i appen, kan du lagre og publisere appen i PowerApps for å se den i Power BI-rapporten.

6. Når du er fornøyd med endringene, kan du dele PowerApps-appen med brukerne av rapporten din, og deretter lagre rapporten.

7. Dermed har du opprettet en rapport som brukerne kan foreta handlinger i, etter som de får innsikt fra dataene.

    ![Arbeid i rapporten](./media/powerapps-custom-visual/working-report.gif)

    Hvis du må gjøre endringer i en app, åpner du rapporten i redigeringsmodus, klikker eller trykker på **Flere alternativer** ( **. . .** ) på PowerApps-visualobjektet og velger **Rediger**.

    ![Rediger appen](./media/powerapps-custom-visual/edit-app.png)

## <a name="limitations-of-the-powerapps-custom-visual"></a>Begrensninger ved visualobjektet fra PowerApps

Følgende begrensninger gjelder for de egen definerte PowerApps-effektene:

- Hvis du endrer datafeltene som er tilknyttet visualobjektet, må du redigere appen fra Power BI-tjenesten ved å velge ellipsen (…) og deretter **Redigere**. Ellers blir ikke endringene overført til PowerApps, og appen vil fungere på uventede måter.
- Den egen definerte PowerApps-effekten kan ikke utløse en oppdatering av Power BI rapporter og Power BI data kilder i Power BI Desktop. Hvis du skriver tilbake data fra appen til den samme data kilden som rapporten, gjenspeiles ikke endringene umiddelbart i Power BI Desktop. Endringene gjenspeiles i den neste planlagte oppdateringen.
- Det egendefinerte PowerApps-visualobjektet kan ikke filtrere dataene eller sende data tilbake til rapporten.
- Du må dele PowerApps-appen adskilt fra rapporten. Finn ut mer om [deling av apper i PowerApps](share-app.md).
- Rapportserver for Power BI og mobilappen for Power BI støtter ikke den egen definerte visuelle effekten i PowerApps.
- Hvis du bruker funksjonen PowerBIIntegration. refresh (), må du bruke en kilde som støtter [directquery](https://docs.microsoft.com/en-us/power-bi/desktop-directquery-data-sources) , og data tilkoblingen må opprettes med DirectQuery-metode.

> [!NOTE]
> Vi anbefaler at du først publiserer rapporten til Power Bi-tjeneste og deretter oppretter eller endrer apper.

## <a name="browser-support"></a>Nett leser støtte

Tabellen nedenfor viser støtte for nett lesere for visning, oppretting og endring av handlinger i den egen definerte visuelle effekten i PowerApps. Støttede nett lesere og handlinger identifiseres med en hake ( &check; ).

|Nettleser|Vis|Opprette|Tilpass
|-|-|-|-
|Microsoft Edge|&check;|&check;|&check;
|Internet Explorer 11|&check;
|Google Chrome|&check;|&check;|&check;
|Safari|&check;
|Mozilla Firefox
|Alle andre lesere

## <a name="next-steps"></a>Neste trinn

* Følg en enkel [trinnvis opplæring](embed-powerapps-powerbi.md).
* Ta en titt på [videoen](https://aka.ms/powerappscustomvisualvideo)vår.
