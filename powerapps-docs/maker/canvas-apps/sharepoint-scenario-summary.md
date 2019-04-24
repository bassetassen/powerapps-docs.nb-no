---
title: Trinnvis gjennomgang av integreringsscenario for SharePoint Online | Microsoft Docs
description: Ta en trinnvis gjennomgang av scenarioet vi har utviklet i denne opplæringsserien.
author: NickWaggoner
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 06/12/2017
ms.author: niwaggon
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 64a26fbd0e36937427bc679869d5bc942f254130
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/23/2019
ms.locfileid: "61531737"
---
# <a name="walk-end-to-end-through-the-completed-sharepoint-online-integration-scenario"></a>Ta en trinnvis gjennomgang av det komplette integreringsscenarioet for SharePoint Online
> [!NOTE]
> Denne artikkelen er en del av en opplæringsserie om hvordan du bruker PowerApps, Microsoft Flow og Power BI med SharePoint Online. Sørg for å lese [innføringen for serien](sharepoint-scenario-intro.md) for å få forståelse av det store bildet, i tillegg til relaterte nedlastinger.

Vi har dekket et stort område i denne opplæringsserien, fra utvikling av lerretsapper og flyter til å opprette rapporter og bygge dem inn i SharePoint. Vi håper du har lært mye og har nok innsyn i hvordan du integrerer disse teknologiene, slik at du kan integrere lerretsapper, flyter og rapporter i SharePoint som er basert på dine egne behov. Før vi fullfører vil vi gå gjennom scenariet fra start til slutt, og se hvordan alle komponentene samvirker.

## <a name="step-1-add-a-project-to-the-project-requests-list"></a>Trinn 1: Legge til et prosjekt i prosjektforespørsler-listen
1. Klikk eller trykk på **Alle elementer** i **Prosjektforespørsler-listen**, og deretter klikker eller trykker du på **Prosjektforespørsler-appen**.
   
    ![Visning av Prosjektforespørsler-appen](./media/sharepoint-scenario-summary/09-00-01-view-app.png)
2. Klikk på **Åpne**, og appen åpnes i en ny fane i nettleseren.
   
    ![Å åpne Prosjektforespørsler-appen](./media/sharepoint-scenario-summary/09-00-02-open-app.png)
3. Klikk eller trykk på ![Legg til element-ikonet i appen](./media/sharepoint-scenario-summary/icon-add-item.png) for å opprette et nytt element.
4. Fyll ut skjemaet med følgende verdier:
   
   * **Tittel** = «Mobile enheter for utformingsteam»

   * **Godkjent** = «Ventende»

   * **Beskrivelse** = «Utformingsteamet vil nå bruke enheter levert av Contoso»

   * **EstimatedDays** = «30»

   * **ProjectType** = «Ny maskinvare»

   * **RequestDate** = «01.03.2017»

   * **Anmoder** = «Gitte Olsen»
     
     ![Redigeringsskjema for prosjektforespørsler](./media/sharepoint-scenario-summary/09-01-01-app-new.png)
5. Klikk eller trykk på ![hakemerkeikonet](./media/sharepoint-scenario-summary/icon-check-mark.png), lukk deretter nettleserfanen.
6. Gå tilbake til **Prosjektforespørsler-listen**, klikk eller trykk på **Prosjektforespørsler-appen** og deretter på **Alle elementer**.
   
    ![Å vise alle elementer](./media/sharepoint-scenario-summary/09-01-01a-view-all.png)
7. Kontroller den nye oppføringen i listen.
   
    ![SharePoint-liste med ny oppføring](./media/sharepoint-scenario-summary/09-01-02-list-new.png)

## <a name="step-2-approve-the-project"></a>Trinn 2: Godkjenne prosjektet
1. Når du legger til elementet i trinn 1, kjører flyten og sender ut en e-post for godkjenning. Kontroller innboksen til godkjennerens e-postkonto.
   
    ![Godkjenningsforespørsel per e-post](./media/sharepoint-scenario-summary/09-02-01-allan-email.png)
2. Klikk på **Godkjenn**. Flyten kjører en annen prosess, og du får tilbakemelding direkte i e-postmeldingen som ser ut som følger.
   
    ![Handling fullført](./media/sharepoint-scenario-summary/09-02-01a-action-complete.png)
3. Kontroller innboksen til anmoderens e-postkonto, og du vil se en e-post for godkjenning.
   
    ![E-post for godkjenning til anmoder](./media/sharepoint-scenario-summary/09-02-02-megan-email.png)
4. Kontroller den oppdaterte oppføringen i listen.
   
    ![SharePoint-liste med oppdatert oppføring](./media/sharepoint-scenario-summary/09-02-03-yes.png)

## <a name="step-3-assign-a-manager-to-the-project"></a>Trinn 3: Tilordne en leder til prosjektet
1. Først skal vi se på **Prosjektdetaljer**-listen i SharePoint. Det nye prosjektet har verdien **Ikke tilordnet** i **PMAssigned**-kolonnen.
   
    ![Ikke-tilordnet SharePoint-listeelement](./media/sharepoint-scenario-summary/09-03-01-unassigned.png)
2. Klikk eller trykk på **App for prosjektstyring** på SharePoint-området.
3. Klikk eller trykk på **Tilordne leder** på den første skjermen.
   
    ![Å tilordne en leder til et prosjekt](./media/sharepoint-scenario-summary/09-03-02-intro-screen.png)
4. På **Tilordne leder**-skjermen ser du de to ikke-tilordnede prosjektene fra listen. Velg **Mobilenheter for utformingsteamet**-prosjektet.
   
    ![Ikke-tilordnet prosjekt som er valgt i appen](./media/sharepoint-scenario-summary/09-03-03-selected.png)
5. I **Leder**-tekstinndataene skriver du inn «Ingjerd Espeseth», og deretter klikker du på **OK**.
   
    Endringen brukes i listen, og galleriet oppdateres slik at bare det gjenværende ikke-tilordnede prosjektet vises.
   
    ![Leder er tildelt til prosjekt](./media/sharepoint-scenario-summary/09-03-04-updated.png)
6. Lukk appen, og gå tilbake til SharePoint-listen. Du ser at prosjektoppføringen nå er oppdatert med navnet på prosjektstyrer.
   
    ![Tilordnet SharePoint-listeelement](./media/sharepoint-scenario-summary/09-03-05-assigned.png)

## <a name="step-4-add-time-estimates-for-the-project"></a>Trinn 4: Legge til tidsestimater for prosjektet
1. Klikk eller trykk på ![Tilbake-ikonet](./media/sharepoint-scenario-summary/icon-back.png) for å gå tilbake til den første skjermen, og klikk eller trykk deretter på **Oppdater detaljer**.
   
    ![Å oppdatere prosjektdetaljer](./media/sharepoint-scenario-summary/09-04-00-intro-screen.png)
2. På **Vis prosjekter**-skjermen skriver du inn «Mobil» i søkeboksen.
   
    ![Å søke i appen](./media/sharepoint-scenario-summary/09-04-01-search-mobile.png)
3. Klikk på ![detaljer-pilikonet](./media/sharepoint-scenario-summary/icon-details-arrow.png) for **Mobilenheter for utformingsteam**-elementet.
   
    ![Å velge prosjektet som skal oppdateres](./media/sharepoint-scenario-summary/09-04-02-select-project.png)
4. Angi følgende verdier på **Oppdater detaljer**-skjermbildet:
   
   * **Status**-feltet = «Ikke påbegynt»

   * **ProjectedStartDate**-feltet = «3/6/2017»

   * **ProjectedEndDate**-feltet = «24/3/2017»

   * **ProjectedDays**-feltet = «15»
     
     ![Å oppdatere prosjektdetaljer](./media/sharepoint-scenario-summary/09-04-03-update.png)
5. Klikk eller trykk på ![hakemerkeikonet](./media/sharepoint-scenario-summary/icon-check-mark.png) for å bruke endringen i SharePoint-listen.
6. Lukk appen, og gå tilbake til listen. Du ser at prosjektoppføringen nå er oppdatert med endringene for dato og ukedag.
   
   ![Detaljer er oppdatert i SharePoint-listen](./media/sharepoint-scenario-summary/09-04-04-updated-list.png)

## <a name="step-5-review-report-data-for-existing-projects"></a>Trinn 5: Gå gjennom rapportdata for eksisterende prosjekter
1. Klikk eller trykk på **Områdeinnhold** og deretter på **Områdesider**i SharePoint Online.
2. Åpne **Prosjektanalyse**-siden vi opprettet tidligere.
   
    ![Innebygd prosjektanalyserapport](./media/sharepoint-scenario-summary/09-05-01-report-complete.png)
3. Se gjennom variansvisualiseringen.
   
    ![Diagram som viser variansen](./media/sharepoint-scenario-summary/09-05-02-chart-variance.png)
   
    Som vi var inne på når vi opprettet denne visualiseringen, er det mye mer varians for prosjekter som ble kjørt av Finn Andresen kontra Ingjerd Espeseth.
4. Drill inn i visualiseringen, og du vil se at mye av variansen kommer fra to prosjekter som tok mye lengre tid enn anslått.
   
    ![Diagram som viser detaljer for variansen](./media/sharepoint-scenario-summary/09-05-03-chart-variance-drill.png)
5. Se gjennom tabellen som viser hvor lang tid det tar fra godkjenning av prosjekter til planlagt oppstartdato.
   
    ![Tabell som viser forskjeller for startdatoer](./media/sharepoint-scenario-summary/09-05-04-chart-diff-completed.png)
   
    Som vi nevnte da vi opprettet denne visualiseringen, tar prosjektene som er tilordnet til Bjarne Kollerud lenger tid før det starter, hvorav to prosjekter tar mye lenger tid enn resten.

## <a name="step-6-respond-to-pending-project-delays"></a>Trinn 6: Svar på ventende forsinkede leveringer
1. Klikk eller trykk på datasettet **Prosjektanalyse** i Power BI-tjenesten, og deretter klikker eller trykker du på **OPPDATER NÅ**. Oppdateringen utløser varselet vi konfigurerer for ventende prosjekter.
   
    ![Oppdater datasettet nå](./media/sharepoint-scenario-summary/09-06-01-refresh.png)
2. Når oppdateringen er fullført, viser **varslingssenteret** øverst til høyre et nytt varsel-ikon.
   
    ![Varslingssenter for Power BI](./media/sharepoint-scenario-summary/09-06-02-alert.png)
   
    Dette kan ta litt tid, så kom tilbake hvis du ikke ser endringen umiddelbart.
3. Åpne varslingssenteret for å se detaljene for varselet som ble utløst.
   
    ![Varsling for datavarsel](./media/sharepoint-scenario-summary/09-06-03-notification.png)
4. Sjekk innboksen for personen som opprettet varselet (Linda Skistad i vårt tilfelle).
   
    ![E-postvarsel fra Power BI](./media/sharepoint-scenario-summary/09-06-04-email-powerbi.png)
5. Sjekk innboksen for personen du har lagt til i flyten for datavarsler (Jan Høvik i vårt tilfelle).
   
    ![E-postvarsel fra Microsoft Flow](./media/sharepoint-scenario-summary/09-06-05-email-flow.png)
6. Nå som du har informasjon om ventende prosjekter, kan du gå tilbake og godkjenne de som har ventet på din oppmerksomhet.

Dette fører oss til konklusjonen for vår trinnvise gjennomgang, og for hele denne opplæringsserien. Vi oppfordrer deg til å fortsette reisen din ved å sjekke ut følgende nettsteder:

* [PowerApps](http://www.powerapps.com/)
* [Microsoft Flow](http://flow.microsoft.com)
* [Power BI](http://www.powerbi.com)
* [Power Users-fellesskapet](https://powerusers.microsoft.com/)
* [SharePoint](http://sharepoint.microsoft.com)
* [Microsoft Tech-fellesskapet](https://techcommunity.microsoft.com/)

Gi oss beskjed i kommentarfeltet hvis du har tilbakemeldinger på denne serien, forslag til tillegg eller ideer til tilleggsinnhold som kan hjelpe deg med å arbeide med teknologier som vi har omtalt.

