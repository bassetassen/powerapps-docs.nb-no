---
title: Egendefinert visualobjekt i PowerApps for Power BI | Microsoft Docs
description: Prosedyre og begrensninger ved å bygge inn en app som bruker samme datakilde og kan filtreres som andre rapportelementer i Power BI
documentationcenter: na
author: mgblythe
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: conceptual
ms.component: canvas
ms.date: 03/15/2018
ms.author: mblythe
ms.openlocfilehash: da3d21e3f4488f552568a95d856af175f9a042eb
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/04/2018
ms.locfileid: "31827101"
---
# <a name="powerapps-custom-visual-for-power-bi"></a>Egendefinert visualobjekt i PowerApps for Power BI

Power BI muliggjør datainnsikt og bedre beslutninger, mens PowerApps gjør det mulig for enhver å bygge og bruke apper som er koblet til forretningsdata. Ved å bruke det egendefinerte visualobjektet i PowerApps kan du overføre kontekstavhengige data til en PowerApps-app, som oppdaterer i sanntid etter som du gjør endringer i en rapport. Nå kan brukerne av appen din få forretningsinnsikt og foreta handlinger direkte fra sine Power BI-rapporter og -instrumentbord.

## <a name="using-the-powerapps-custom-visual"></a>Bruk av et egendefinert visualobjekt fra PowerApps

La oss se på fremgangsmåten for å bruke det egendefinerte visualobjektet fra PowerApps i Power BI-rapporten.

1. Hent visualobjektet fra [AppSource](https://appsource.microsoft.com/product/power-bi-visuals/WA104381378?tab=Overview), eller importer det direkte i Power BI-tjenesten.

    ![Egendefinert visualobjekt i Marketplace](./media/powerapps-custom-visual/powerapps-store.png) 

1. Legg til PowerApps-visualobjektet i rapporten, og angi datafeltene som er knyttet til det.

    ![Velg rapportdata](./media/powerapps-custom-visual/add-visual-set-data.png)

1. Du kan velge en eksisterende app eller opprette en. Hvis du velger å opprette en app, kan du velge hvilket miljø du vil opprette den i.

    ![Ny eller eksisterende app](./media/powerapps-custom-visual/create-new-or-choose-app.png)

    Hvis du velger å bruke en eksisterende app, vil visualobjektet be deg om å åpne appen i PowerApps. Deretter angir visualobjektet de nødvendige komponentene i appen, så Power BI kan sende data til PowerApps.

    Hvis du oppretter en ny app, oppretter PowerApps en enkel app med de nødvendige komponentene allerede konfigurert.

    ![Ny app](./media/powerapps-custom-visual/new-app.png)

1. Nå kan du bruke datafeltene du anga i trinn 2, i PowerApps Studio. `PowerBIIntegration`-objektet fungerer som alle andre skrivebeskyttede datakilder eller -samlinger i PowerApps. Du kan bruke objektet til å fylle ut en kontroll eller føye sammen og filtrere med andre datakilder.

    ![Egendefinert formel](./media/powerapps-custom-visual/custom-formula.png)

    Denne formelen kobler Power BI-data med kundedatakilden: `LookUp(Customer,Customer_x0020_Name=First(PowerBIIntegration.Data).Customer_Name)`

 Power BI-rapporten og forekomsten av PowerApps Studio som ble startet, deler en direkte datatilkobling. Når begge er åpne, kan du filtrere eller endre dataene i rapporten og se de oppdaterte dataene øyeblikkelig gjenspeilet i appen i PowerApps Studio.

1. Når du er ferdig med å bygge eller gjøre endringer i appen, kan du lagre og publisere appen i PowerApps for å se den i Power BI-rapporten.

1. Når du er fornøyd med endringene, kan du dele PowerApps-appen med brukerne av rapporten din, og deretter lagre rapporten.

1. Dermed har du opprettet en rapport som brukerne kan foreta handlinger i, etter som de får innsikt fra dataene.

    ![Arbeid i rapporten](./media/powerapps-custom-visual/working-report.gif)

    Hvis du må gjøre endringer i en app, åpner du rapporten i redigeringsmodus, klikker eller trykker på **Flere alternativer** (**. . .**) på PowerApps-visualobjektet og velger **Rediger**.

    ![Rediger appen](./media/powerapps-custom-visual/edit-app.png)

## <a name="limitations-of-the-powerapps-custom-visual"></a>Begrensninger ved visualobjektet fra PowerApps

PowerApps-visualobjektet er tilgjengelig i forhåndsvisning og har disse begrensningene:

- Du kan ikke opprette eller endre apper når du bruker PowerApps-visualobjektet i Power BI Desktop, Internet Explorer eller Mozilla Firefox. Vi anbefaler at du først publiserer rapporten til Power BI-tjenesten. Deretter kan du bruke Microsoft Edge eller Google Chrome til å opprette nye apper og endre apper.
- Hvis du endrer datafeltene som er tilknyttet visualobjektet, må du redigere appen fra Power BI-tjenesten ved å velge ellipsen (…) og deretter **Redigere**. Ellers blir ikke endringene overført til PowerApps, og appen vil fungere på uventede måter.
- Det egendefinerte PowerApps-visualobjektet kan ikke utløse en oppdatering av Power BI-rapporten eller Power BI-datakilden. Hvis du skriver tilbake data fra appen til samme datakilde som rapporten, gjenspeiles ikke endringene umiddelbart. Endringene gjenspeiles i den neste planlagte oppdateringen.
- Det egendefinerte PowerApps-visualobjektet kan ikke filtrere dataene eller sende data tilbake til rapporten.
- Du må dele PowerApps-appen adskilt fra rapporten. Finn ut mer om [deling av apper i PowerApps](share-app.md).
- Mobilappen for Power BI støtter ikke egendefinerte PowerApps-visualobjekter.

## <a name="next-steps"></a>Neste trinn

* Følg en enkel [trinnvis opplæring](embed-powerapps-powerbi.md).
* Sjekk ut vår [video](https://aka.ms/powerappscustomvisualvideo).