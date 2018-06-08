---
title: Publisere Power BI-prosjektrapporten og opprette et instrumentbord i Microsoft Docs
description: I denne oppgaven publiserer vi datasettene og rapportene våre til Power BI-tjenesten, og deretter skal vi opprette et instrumentbord som er basert på rapporten.
documentationcenter: na
author: mgblythe
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: conceptual
ms.component: canvas
ms.date: 01/30/2018
ms.author: mblythe
ms.openlocfilehash: cc738334cc20f2911e17404faf679c0ed6bc2832
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/04/2018
ms.locfileid: "31830874"
---
# <a name="publish-the-power-bi-project-report-and-create-a-dashboard"></a>Publisere Power BI-prosjektrapporten og opprette et instrumentbord
> [!NOTE]
> Denne artikkelen er en del av en opplæringsserie om hvordan du bruker PowerApps, Microsoft Flow og Power BI med SharePoint Online. Sørg for å lese [innføringen for serien](sharepoint-scenario-intro.md) for å få forståelse av det store bildet, i tillegg til relaterte nedlastinger.

I denne oppgaven publiserer vi datasettene og rapportene våre til Power BI-tjenesten, og deretter skal vi opprette et instrumentbord som er basert på rapporten. I mange tilfeller har en rapport et stort antall visualiseringer, og bare et delsett av disse brukes på et instrumentbord. I vårt tilfelle skal vi legge alle fire visualiseringer til på instrumentbordet.

## <a name="step-1-publish-the-dataset-and-report"></a>Trinn 1: Publisere datasettet og rapporten
1. Klikk eller trykk på **Publiser** under **Hjem**-fanen i Power BI Desktop.
   
    ![Å publisere datasett og rapport](./media/sharepoint-scenario-publish-report/06-01-01-publish.png)
2. Hvis du ikke allerede er logget på Power BI-tjenesten, angir du en konto og klikker eller trykker deretter på **Logg på**.
   
    ![Å logge på kontoen](./media/sharepoint-scenario-publish-report/06-01-02-account.png)
3. Skriv inn et passord, og klikk eller trykk deretter på **Logg på**.
   
    ![Å skrive inn passordet for kontoen](./media/sharepoint-scenario-publish-report/06-01-03-password.png)
4. Velg et mål for rapporten, og klikk eller trykk på **Velg**. Vi anbefaler å publisere til et gruppearbeidsområde for å forenkle tilgangen til rapporten i SharePoint. I dette tilfellet publiserer vi til gruppearbeidsområdet **Project Management**. Hvis du vil ha mer informasjon, kan du se [Samarbeide i arbeidsområdet for Power BI-appen](https://docs.microsoft.com/power-bi/service-collaborate-power-bi-workspace).
   
    ![Målarbeidsområde](./media/sharepoint-scenario-publish-report/06-01-04-workspace.png)
5. Klikk eller trykk på **Open 'project-analysis.pbx' in Power BI** når publiseringen er fullført.
   
    ![Publisering vellykket](./media/sharepoint-scenario-publish-report/06-01-05-open-report.png)
6. Power BI-tjenesten laster inn rapporten i en nettleser. Hvis den venstre navigasjonsruten ikke er utvidet, klikker eller trykker du på menyen øverst til venstre **(a)** for å utvide den.
   
    ![Rapport i Power BI-tjeneste](./media/sharepoint-scenario-publish-report/06-01-06-service-report.png)
   
    Du kan se at når vi publiserte, lastet Power BI Desktop opp et datasett **(d)** og en rapport **(c)**. Du oppretter instrumentbord i tjenesten, ikke i Power BI Desktop, og dette arbeidsområdet har ingen instrumentbord ennå **(b)**. Vi skal snart opprette et.

## <a name="step-2-configure-credentials-for-refresh"></a>Trinn 2: Konfigurer legitimasjon for oppdatering
1. Klikk eller trykk på ![tannhjulikonet](./media/sharepoint-scenario-publish-report/icon-gear.png) øverst til høyre i tjenesten, og klikk deretter eller trykk på **Innstillinger**.
2. Klikk eller trykk på **Datasett** og deretter på **project-analysis**.
   
    ![Datasettet project-analysis](./media/sharepoint-scenario-publish-report/06-01-07-dataset.png)
3. Utvid **Legitimasjon for datakilde**, og klikk eller trykk deretter på **Rediger legitimasjon**.
   
    ![Å redigere legitimasjon for datakilde](./media/sharepoint-scenario-publish-report/06-01-08-credentials.png)
4. Velg **OAuth2** for godkjenningsmetode, og klikk eller trykk på **Logg på**.
   
    ![Å logge på SharePoint](./media/sharepoint-scenario-publish-report/06-01-09-sign-in.png)
5. Velg eller logg på en konto som har tillatelser for SharePoint-lister.
   
    ![Logget på Office 365](./media/sharepoint-scenario-publish-report/06-01-10-account.png)
   
    Når prosessen er fullført, får du følgende melding i tjenesten.
   
    ![Datakilden er oppdatert](./media/sharepoint-scenario-publish-report/06-01-11-updated.png)

## <a name="step-3-create-a-dashboard"></a>Trinn 3: Opprette et instrumentbord

1. Klikk eller trykk på **project analysis** under **RAPPORTER** for å komme tilbake til rapporten din.

1. Klikk eller trykk på diagrammet øverst til venstre, og klikk eller trykk deretter på ![Fest-ikonet](./media/sharepoint-scenario-publish-report/icon-pin.png).
   
    ![Å feste diagram](./media/sharepoint-scenario-publish-report/06-01-12-pin-projected.png)
2. Skriv inn et navn for instrumentbordet du vil feste til, og klikk eller trykk deretter på **Fest**.
   
    ![Å feste diagram til nytt instrumentbord](./media/sharepoint-scenario-publish-report/06-01-13-pin-new.png)
3. Klikk eller trykk på diagrammet øverst til høyre, og klikk eller trykk deretter på ![Fest-ikonet](./media/sharepoint-scenario-publish-report/icon-pin.png).
   
    ![Å feste diagram](./media/sharepoint-scenario-publish-report/06-01-14-pin-variance.png)
4. Velg det eksisterende instrumentbordet, og klikk eller trykk deretter på **Fest**.
   
    ![Å feste diagram til eksisterende instrumentbord](./media/sharepoint-scenario-publish-report/06-01-15-pin-existing.png)

5. Gjenta fremgangsmåten for festing av de to andre visuelle effektene.

6. Klikk eller trykk på navnet til instrumentbordet i den venstre navigasjonsruten.
   
    ![Nytt instrumentbord i områdenavigasjon](./media/sharepoint-scenario-publish-report/06-01-16-dashboard-menu.png)

7. Se gjennom instrumentbordet. Hvis du klikker på en flis, går du tilbake til rapporten.
   
    ![Fullførte instrumentbord](./media/sharepoint-scenario-publish-report/06-01-17-dashboard-completed.png)

Dette oppsummerer det meste av arbeidet i Power BI. Hvis dette er første gang du har opprettet rapporter og instrumentbord, er gratulasjoner på sin plass! Hvis du allerede er proff, håper vi du kom deg raskt gjennom det. Nå skal vi legge til varslinger for å sikre at vi vet når instrumentbordet krever oppmerksomhet fra vår side.

## <a name="next-steps"></a>Neste trinn
Det neste trinnet i denne opplæringsserien er å [sette opp datavarsler for Power BI-prosjektrapporten](sharepoint-scenario-alerts-flow.md).

