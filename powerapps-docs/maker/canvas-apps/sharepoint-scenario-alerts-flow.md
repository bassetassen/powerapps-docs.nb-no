---
title: Å sette opp datavarsler for Power BI-instrumentbordet | Microsoft Docs
description: I denne oppgaven skal vi legge til et varsel i Power BI, slik at vi får beskjed hvis ventende prosjekter tar for lang tid å godkjenne, og en flyt som svarer når denne varslingen utløses.
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
ms.openlocfilehash: 89c22bec8972c0d58c559a09d4e9f0a8a8e3b7f5
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/23/2019
ms.locfileid: "61537581"
---
# <a name="set-up-data-alerts-for-the-power-bi-dashboard"></a>Å sette opp datavarsler for Power BI-instrumentbordet
> [!NOTE]
> Denne artikkelen er en del av en opplæringsserie om hvordan du bruker PowerApps, Microsoft Flow og Power BI med SharePoint Online. Sørg for å lese [innføringen for serien](sharepoint-scenario-intro.md) for å få forståelse av det store bildet, i tillegg til relaterte nedlastinger.

I denne oppgaven skal vi legge til et varsel i Power BI, slik at vi får beskjed hvis ventende prosjekter tar for lang tid å godkjenne, og en flyt som svarer når denne varslingen utløses. Hvis du vil ha mer informasjon om varsler, kan du se [Datavarsler i Power BI-tjenesten](https://docs.microsoft.com/power-bi/service-set-data-alerts).

## <a name="step-1-create-an-alert"></a>Trinn 1: Opprett et varsel
1. Åpne instrumentbordet du opprettet i den siste aktiviteten i Power BI-tjenesten.
2. Klikk på kortet med det enkle nummeret, eller trykk på ellipsen (**. . .**).
   
    ![Maksimalt antall dager for venting på godkjenning av kortet](./media/sharepoint-scenario-alerts-flow/07-01-01-tile-ellipsis.png)
3. Klikk eller trykk på ![klokkeikonet](./media/sharepoint-scenario-alerts-flow/icon-bell.png).
   
    ![Flis-meny](./media/sharepoint-scenario-alerts-flow/07-01-02-tile-bell.png)
4. Klikk eller trykk på **Legg til varslingsregel** i ruten til høyre.
   
    ![Å legge til varslingsregel](./media/sharepoint-scenario-alerts-flow/07-01-03-add-alert.png)
5. Se på alternativene som er tilgjengelig for varsler, for eksempel hvor ofte et varsel skal kjøres. Angi en verdi på 25 for **Terskel**, og klikk eller trykk deretter på **Lagre og lukk**.
   
    ![Å angi terskel for varselet og lagre](./media/sharepoint-scenario-alerts-flow/07-01-04-save-alert.png)

Varselet utløses ikke akkurat nå, selv om 56 er over terskelen på 25. Det utløses når dataene oppdateres, og dette ser vi når vi [kjører gjennom scenarioet fra start til slutt](sharepoint-scenario-summary.md).

Når varslene utløses, sender Power BI e-post til personen som opprettet varselet. I neste trinn skal vi se hvordan du sender flere e-poster med Microsoft Flow.

## <a name="step-2-create-a-flow-that-responds-to-the-alert"></a>Trinn 2: Opprette en flyt som svarer på varselet
1. Logg på flow.microsoft.com, klikk eller trykk på **Tjenester** og deretter på **Power BI**.
   
    ![Power BI i Microsoft Flow](./media/sharepoint-scenario-alerts-flow/07-01-05-power-bi.png)
2. Klikk eller trykk på **Send en e-post til en hvilken som helst mottakergruppe når et Power BI-datavarsel utløses**.
   
    ![Sende en e-post når et Power BI-datavarsel utløses](./media/sharepoint-scenario-alerts-flow/07-01-06-alert-flow.png)
3. Klikk eller trykk på **Bruk denne malen**.
4. Hvis du ikke allerede er logget på, logger du deg på Outlook og Power BI, og deretter klikker eller trykker du på **Fortsett**.
   
    ![Å logge på og fortsette](./media/sharepoint-scenario-alerts-flow/07-01-08-continue.png)
5. Velg **Varsel for maksimalt antall dager for venting på godkjenning** på rullegardinlisten **Varsel-ID**.
   
    ![Å angi og varsle som en utløser](./media/sharepoint-scenario-alerts-flow/07-01-09-choose-alert.png)
6. Skriv inn en gyldig e-postadresse i **Til**-boksen.
   
    ![Å angi hvem e-posten skal sendes til](./media/sharepoint-scenario-alerts-flow/07-01-10-choose-email.png)
7. Klikk eller trykk på **Rediger** for å se andre felt du kan oppdatere.
   
    ![Å redigere e-postvarsel](./media/sharepoint-scenario-alerts-flow/07-01-11-email-full.png)
8. Klikk eller trykk på **Opprett flyt** øverst til høyre på skjermen, og klikk deretter på **Ferdig**.
   
    ![Ferdig-knapp](./media/sharepoint-scenario-alerts-flow/07-01-12-done.png)

Vi vil se denne flytkjøringen når vi [kjører gjennom scenarioet fra start til slutt](sharepoint-scenario-summary.md). Nå går vi videre til den siste oppgaven i dette scenarioet – bygge inn en Power BI-rapport i SharePoint.

## <a name="next-steps"></a>Neste trinn
Det neste trinnet i denne opplæringsserien er å [bygge rapporten for Power BI-prosjektet inn i SharePoint Online](sharepoint-scenario-embed-report.md).

