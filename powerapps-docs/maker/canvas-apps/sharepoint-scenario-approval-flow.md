---
title: Oppretting av en flyt for å behandle prosjektgodkjenninger | Microsoft Docs
description: I denne oppgaven skal vi opprette en flyt som styrer prosessen med å godkjenne prosjekter.
author: stepsic-microsoft-com
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 01/09/18
ms.author: stepsic
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: d41807bedf85c151c8e115456b9fb3e23756629d
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/23/2019
ms.locfileid: "61538255"
---
# <a name="create-a-flow-to-manage-project-approvals"></a>Oppretting av en flyt for å behandle prosjektgodkjenninger
> [!NOTE]
> Denne artikkelen er en del av en opplæringsserie om hvordan du bruker PowerApps, Microsoft Flow og Power BI med SharePoint Online. Sørg for å lese [serieinnføringen](sharepoint-scenario-intro.md) for å få en fornemmelse av det store bildet, i tillegg til relaterte nedlastinger.

I denne oppgaven skal vi opprette en flyt som styrer prosessen med å godkjenne prosjekter. Microsoft Flow er integrert med SharePoint, slik at det er enkelt å opprette en flyt direkte fra en liste. Flyten vi skal opprette utløses når et element legges til listen for **prosjektforespørsler**. Flyten sender en e-postmelding til prosjektgodkjenneren, som godkjenner eller avslår forespørselen direkte via e-post. Flyten sender deretter en godkjenning eller avvisning via e-postmelding til prosjektanmoderen, og oppdaterer SharePoint-listen på riktig måte.

## <a name="step-1-configure-the-flow-template"></a>Trinn 1: Konfigurer flytmalen
1. I **Prosjekt**-listen klikker eller trykker du på **Flyt**, og deretter på **Opprett en flyt**.
   
    ![Oppretting av en flyt](./media/sharepoint-scenario-approval-flow/03-01-01-create-flow.png)
2. Klikk eller trykk på **Start godkjenning når et nytt element legges til** i den høyre ruten.
   
    ![Oppretting av en godkjenningsflyt](./media/sharepoint-scenario-approval-flow/03-01-02-approval-flow.png)
3. Hvis du ikke allerede er logget på, logger du deg på SharePoint og Outlook, og deretter klikker eller trykker du på **Fortsett**.
   
    ![Slik logger du deg på for å bruke maler](./media/sharepoint-scenario-approval-flow/03-01-03-continue.png)
   
    Du kan nå se malen som er klar til å fullføres for denne flyten. Boksene i flyten representerer trinnene. De henter inndata fra tidligere trinn, samt inndata som du angir. Hvert trinn kan deretter bruke utdata til de etterfølgende trinnene.
   
    ![Godkjenningsmal](./media/sharepoint-scenario-approval-flow/03-01-04-template.png)
4. Angi et navn som er gyldig i tenanten i **Tilordnet til**-boksen.
   
    ![E-postkontakt for godkjenning](./media/sharepoint-scenario-approval-flow/03-01-05-approval-email.png)
   
    Den neste boksen i flyten svarer på prosjektanmoderens beslutning, og ruter flyten til én av to *grener*: **Hvis Ja** eller **Hvis ingen**.
   
    ![Godkjenningsbetingelse](./media/sharepoint-scenario-approval-flow/03-01-06-condition.png)

## <a name="step-2-create-actions-for-approve--yes"></a>Trinn 2: Opprette handlinger for Godkjenn = Ja
Som standard sender denne grenen en e-postmelding til anmoderen og ber om godkjenning. Vi oppdaterer også **Prosjektforespørsler**-listen og legger til et element til **Prosjektdetaljer**-listen fordi prosjektet har blitt godkjent.

1. I **Hvis Ja**-grenen klikker eller trykker du på **Informer elementets oppretter om godkjenning**, deretter på **Rediger** for å se standardalternativene for e-postmeldingen som er sendt til anmoderen.
   
    ![Redigering av e-postinnstillinger](./media/sharepoint-scenario-approval-flow/03-01-07-yes-email.png)
2. Som standard sendes en e-postmelding til personen som opprettet listeelementet, med emnelinjen og meldingsteksten som du ser her. Du kan oppdatere dette hvis du ønsker det.
   
    ![Standardinnstillinger for e-post](./media/sharepoint-scenario-approval-flow/03-01-07a-yes-email-defaults.png)
3. Klikk eller trykk på **Legg til en handling**.
   
    ![Å legge til en handling](./media/sharepoint-scenario-approval-flow/03-00-01-add-action.png)
4. Under **Velg en handling** søker du etter «SharePoint», deretter klikker eller trykker du på **SharePoint – oppdater element**.
   
    ![Oppdatering av elementhandling](./media/sharepoint-scenario-approval-flow/03-00-02-update.png)
5. Angi nettadressen og listenavnet for SharePoint-området.
   
    ![Å oppdatere elementets parametere](./media/sharepoint-scenario-approval-flow/03-00-03-update-list.png)
6. Merk **ID**-boksen, og klikk eller trykk deretter på **ID** i dialogboksen *Dynamisk innhold*.
   
    ![Dynamisk innhold for liste-ID](./media/sharepoint-scenario-approval-flow/03-00-04-list-id.png)
   
    Dynamisk innhold er tilgjengelig i hele flyten, basert på forrige trinn. I dette tilfellet er informasjonen for SharePoint-listen tilgjengelig, og vi kan bruke den for handlingene vi oppretter.
7. Velg **Tittel**-boksen, søk etter «Tittel» i dialogboksen med dynamisk innhold, og klikk eller trykk på **Tittel**.
   
    ![Dynamisk innhold for listetittel](./media/sharepoint-scenario-approval-flow/03-00-05-list-title.png)
8. Angi «Ja» i **Godkjent**-boksen. Denne delen av flyten skal nå se ut som på bildet nedenfor.
   
    ![Listeoppdatering](./media/sharepoint-scenario-approval-flow/03-01-08-yes-update-complete.png)
9. Klikk eller trykk på **Legg til en handling** på nytt. Denne gangen legger vi til et element til **Prosjektdetaljer**-listen for prosjektet som ble godkjent.
   
    ![Å legge til en handling](./media/sharepoint-scenario-approval-flow/03-00-01-add-action.png)
10. Under **Velg en handling** søker du etter «SharePoint», og deretter velger du **SharePoint – opprett element**.
    
    ![Oppretting av elementhandling](./media/sharepoint-scenario-approval-flow/03-01-09-create.png)
11. Angi nettadressen og listenavnet for SharePoint-området.
    
    ![Oppdatering av elementets parametere](./media/sharepoint-scenario-approval-flow/03-01-10-yes-create-list.png)
12. Velg **Tittel**-boksen, søk etter «Tittel» i dialogboksen med dynamisk innhold, og klikk eller trykk på **Tittel**.
    
    ![Dynamisk innhold for listetittel](./media/sharepoint-scenario-approval-flow/03-00-05-list-title.png)
13. Merk **RequestId**-boksen, og klikk eller trykk deretter på **ID** i dialogboksen for dynamisk innhold.
    
    ![Dynamisk innhold for liste-ID](./media/sharepoint-scenario-approval-flow/03-00-04-list-id.png)
14. Angi «Ikke tilordnet» i **Tilordnet PM**-boksen. Denne delen av flyten skal nå se ut som på bildet nedenfor.
    
    ![Oppretting av element er fullført](./media/sharepoint-scenario-approval-flow/03-01-11-yes-create-complete.png)

## <a name="step-3-review-action-for-approve--no"></a>Trinn 3: Gå gjennom handling for Godkjenn = Nei
Som standard sender denne grenen en e-postmelding til anmoderen og ber om avvisning. Vi vil også oppdatere **Prosjektforespørsler**-listen. Prosjektet har ingen fremgang, så vi legger ikke til et element til **Prosjektdetaljer**-listen.

1. Klikk eller trykk på **Informer elementets oppretter om avvisningen** i **Hvis nei**-grenen, og deretter på **Rediger** for å se standardalternativene for e-posten som er sendt til anmoderen.
   
    ![Redigering av e-postinnstillinger](./media/sharepoint-scenario-approval-flow/03-01-12-no-email.png)
2. Som standard sendes en e-postmelding til personen som opprettet listeelementet, med emnelinjen og meldingsteksten som du ser her. Du kan oppdatere dette hvis du ønsker det.
   
    ![Standardinnstillinger for e-post](./media/sharepoint-scenario-approval-flow/03-01-13-no-email-defaults.png)
3. Klikk eller trykk på **Legg til en handling**.
   
    ![Å legge til en handling](./media/sharepoint-scenario-approval-flow/03-00-01-add-action.png)
4. Under **Velg en handling** søker du etter «SharePoint», deretter klikker eller trykker du på **SharePoint – oppdater element**.
   
    ![Oppdatering av elementhandling](./media/sharepoint-scenario-approval-flow/03-00-02-update.png)
5. Angi nettadressen og listenavnet for SharePoint-området.
   
    ![Å oppdatere elementets parametere](./media/sharepoint-scenario-approval-flow/03-00-03-update-list.png)
6. Merk **ID**-boksen, og klikk eller trykk deretter på **ID** i dialogboksen Dynamisk innhold.
   
    ![Dynamisk innhold for liste-ID](./media/sharepoint-scenario-approval-flow/03-00-04-list-id.png)
7. Velg **Tittel**-boksen, søk etter «Tittel» i dialogboksen med dynamisk innhold, og klikk eller trykk på **Tittel**.
   
    ![Dynamisk innhold for listetittel](./media/sharepoint-scenario-approval-flow/03-00-05-list-title.png)
8. Angi «Nei» i **Godkjent**-boksen. Denne delen av flyten skal nå se ut som på bildet nedenfor.
   
    ![Listeoppdatering](./media/sharepoint-scenario-approval-flow/03-01-08-no-update-complete.png)
9. Klikk eller trykk på **Opprett flyt** øverst til høyre på skjermen.
   
    Flyten er nå fullført, og det skal se ut som bildet nedenfor hvis du skjuler boksene.
   
    ![Fullføring av flyt](./media/sharepoint-scenario-approval-flow/03-01-16-flow-complete.png)

10. Klikk eller trykk på **Ferdig** øverst til høyre på skjermen.
   
    ![Ferdig-knapp](./media/sharepoint-scenario-approval-flow/03-01-15a-done-button.png)

## <a name="step-4-run-the-approval-flow"></a>Trinn 4: Kjør godkjenningsflyten
1. I **Prosjektforespørsler**-listen klikker du på **Hurtigredigering** og legger til et element, for eksempel følgende:
   
   * **Tittel** = «Ny skjerm til Gunvor»

   * **Beskrivelse** = «Gunvor trenger en 24" skjerm»

   * **ProjectType** = «Ny maskinvare»

   * **RequestDate** = «03.02.2017»

   * **Anmoder** = «Gunvor Svensli»

   * **EstimatedDays** = «1»

   * **Godkjent** = «Ventende»

     ![Element lagt til i listen](./media/sharepoint-scenario-approval-flow/03-02-01-list-add.png)
2. Klikk på **Ferdig** øverst på siden når du er ferdig.
   
    ![Ferdig-merke](./media/sharepoint-scenario-approval-flow/03-02-02-done.png)
3. Kontroller innboksen til godkjennerens e-postkonto. Du skal ha en e-postmelding som ser slik ut.
   
    ![E-post til Bjørn Rosendal](./media/sharepoint-scenario-approval-flow/03-02-03-allan-email.png)
4. Når du har klikket på **Godkjenn** eller **Avvis**, kjører flyten en annen prosess, og du får tilbakemelding som ser ut som følger, direkte i e-postmeldingen.
   
    ![Godkjenningshandling fullført](./media/sharepoint-scenario-approval-flow/03-02-04-action-complete.png)
5. Flyten sender en e-postmelding til Gunvor med Finn sitt svar, som i bildet nedenfor. Denne e-posten kommer *fra* Gunvor fordi hun eier flyten.
   
    ![E-post til Gunvor Svensli](./media/sharepoint-scenario-approval-flow/03-02-05-megan-email.png)

## <a name="next-steps"></a>Neste trinn
Det neste trinnet i denne opplæringsserien er å [generere en app til å håndtere prosjekter](sharepoint-scenario-build-app.md).

