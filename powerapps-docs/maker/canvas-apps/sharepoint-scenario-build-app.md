---
title: Å opprette en app for å administrere prosjekter | Microsoft Docs
description: I denne oppgaven skal vi opprette en app fra grunnen av. Denne appen lar en bruker tilordne en leder til prosjekter og oppdatere prosjektdetaljer.
author: mgblythe
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 06/12/2017
ms.author: mblythe
ms.openlocfilehash: b4daabf019236a4245db324121a6745290c8b3ab
ms.sourcegitcommit: dfa0e1a7981814e15e6ca4720e2a5f930e859db1
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 07/13/2018
ms.locfileid: "39021623"
---
# <a name="create-an-app-to-manage-projects"></a>Å opprette en app for å styre prosjektene
> [!NOTE]
> Denne artikkelen er en del av en opplæringsserie om hvordan du bruker PowerApps, Microsoft Flow og Power BI med SharePoint Online. Sørg for å lese [serieinnføringen](sharepoint-scenario-intro.md) for å få et inntrykk av det store bildet, i tillegg til relaterte nedlastinger.

I denne oppgaven skal vi opprette en app fra grunnen av. Denne appen lar en bruker tilordne en leder til prosjekter og oppdatere prosjektdetaljer. Du vil se noen av de samme kontrollene og formlene du så i den første appen, men denne gangen skal du utforme appen i større grad selv. Prosessen er mer komplisert, men du vil lære mer – noe vi mener er et rettferdig bytte.

> [!TIP]
> [Nedlastingspakken](https://aka.ms/o4ia0f) for dette scenariet inkluderer en fullført versjon av denne appen: project-detaljer-app.msapp.

## <a name="quick-review-of-powerapps-studio"></a>Rask gjennomgang av PowerApps Studio
PowerApps Studio har tre ruter og ett bånd, noe som gjør at opplevelsen av app-oppretting ligner på det å opprette en lysbildevisning i PowerPoint:

1. Venstre navigasjonsfelt, som viser en hierarkisk visning av alle skjermer og kontroller for appen, samt miniatyrbilder av skjermene
2. Midterste rute, som inneholder app-skjermen du arbeider i
3. Høyre rute, der du angir alternativer som for eksempel oppsett og datakilder
4. Egenskaper-rullegardinlisten, der du kan velge hvilke formler som gjelder for hvilke egenskaper
5. Formellinjen, der du legger til formler (som i Excel) som definerer appens virkemåte
6. Båndet, der du legger til kontroller og tilpasser utformingselementene

![PowerApps Studio](./media/sharepoint-scenario-build-app/04-00-00-powerapps-studio.png)

## <a name="step-1-create-screens"></a>Trinn 1: Å opprette skjermer
Med denne gjennomgangen ute av veien kan vi nå begynne å utforme en app.

### <a name="create-and-save-the-app"></a>Å opprette og lagre appen
1. Klikk eller trykk på **Ny**i PowerApps Studio, deretter klikker eller trykker du på **Telefonoppsett** under **Tom app**.
   
    ![Tom app – telefonoppsett](./media/sharepoint-scenario-build-app/04-01-01-blank-phone-app.png)
2. Klikk eller trykk på **Fil**, som åpnes i en **appinnstillinger**-fane. Skriv inn navnet «Prosjektstyringsapp».
   
    ![Appnavn](./media/sharepoint-scenario-build-app/04-01-02-app-name.png)
3. Klikk eller trykk på **Lagre som**, kontroller at appen skal lagre i skyen, og klikk deretter på **Lagre** nederst til høyre.
   
    ![Å lagre til skyen](./media/sharepoint-scenario-build-app/04-01-03-save-to-cloud.png)

4. Klikk eller trykk på ![Tilbake til app-ikonet](./media/sharepoint-scenario-build-app/icon-back-to-app.png) for å gå tilbake til appen.

### <a name="add-four-screens-to-the-app"></a>Å legge til fire skjermer til appen
I dette trinnet skal vi opprette fire tomme skjermer for appen. Vi bruker ulike skjermoppsett, avhengig av formålet med skjermbildet. Vi legger til disse skjermene i senere trinn.

| **Skjerm** | **Formål** |
| --- | --- |
| **SelectTask** |Åpningsskjerm – gå til andre skjermer |
| **AssignManager** |Tilordne en leder til et godkjent prosjekt |
| **ViewProjects** |Vis en liste over prosjekter med sammendragsinformasjon |
| **UpdateDetails** |Vis og oppdater detaljene for et prosjekt |

1. Klikk eller trykk på **NewScreen** på **Hjem-fanen**, og deretter på **Skjerm som kan rulles**.
   
    ![Skjerm som kan rulles](./media/sharepoint-scenario-build-app/04-01-03a-scrollable-screen.png)
2. Gi nytt navn til skjermen: **SelectTask**.
   
    ![Å gi nytt navn til skjermen](./media/sharepoint-scenario-build-app/04-01-04-rename-screen.png)
3. Opprett og endre navn på flere skjermer:
   
   1. Klikk eller trykk på **NewScreen**, deretter på **Skjerm som kan rulles**. Gi nytt navn til skjermen: **AssignManager**.
   2. Klikk eller trykk på **NewScreen**, deretter på **Listeskjerm**. Gi nytt navn til skjermbildet: **ViewProjects**.
   3. Klikk eller trykk på **NewScreen**, deretter på **Skjema-skjermbilde**. Gi nytt navn til skjermen: **UpdateDetails**.
4. Velg ellipsen (**...** ) ved siden av **Screen1**, klikk eller trykk deretter på **Slett**.
   
    ![Å slette skjermer](./media/sharepoint-scenario-build-app/04-01-04a-delete-screen.png)

Appen skal nå se ut som på følgende bilde.

![Alle app-skjermer](./media/sharepoint-scenario-build-app/04-01-05-all-screens.png)

## <a name="step-2-connect-to-a-sharepoint-list"></a>Trinn 2: Å koble til en SharePoint-liste
I dette trinnet kobler vi til **Produktdetaljer**-listen for SharePoint. Vi bruker bare én liste i denne appen, men du kan enkelt koble til begge hvis du vil utvide appen.

1. Klikk eller trykk på **SelectTask** i venstre navigasjonsfelt.
2. Klikk eller trykk på **Legg til datakilde** i ruten til høyre.
   
    ![Å koble til data](./media/sharepoint-scenario-build-app/04-02-01-connect.png)
3. Klikk eller trykk på **Ny tilkobling**.
   
    ![Ny tilkobling](./media/sharepoint-scenario-build-app/04-02-02-new-connection.png)
4. Klikk eller trykk på **SharePoint**.
   
    ![SharePoint-tilkobling](./media/sharepoint-scenario-build-app/04-02-03-sharepoint-connection.png)
5. Velg **Koble til direkte (skytjenester)**, klikk eller trykk deretter på **Opprett**.
   
    ![Å koble til direkte (skytjenester)](./media/sharepoint-scenario-build-app/04-02-03a-sharepoint-cloud.png)
6. Angi en nettadresse for SharePoint, klikk eller trykk deretter på **Gå til**.
   
    ![Nettadresse for SharePoint, for tilkobling](./media/sharepoint-scenario-build-app/04-02-04-sharepoint-url.png)
7. Velg **Prosjektdetaljer**-listen, og klikk eller trykk deretter på **Koble til**.
   
    ![Å velge liste for prosjektdetaljer](./media/sharepoint-scenario-build-app/04-02-05-sharepoint-lists.png)
   
    **Datakilder**-fanen i den høyre ruten viser nå tilkoblingen du har opprettet.
   
    ![Datakilder-fane](./media/sharepoint-scenario-build-app/04-02-06-data-sources.png)

## <a name="step-3-build-the-selecttask-screen"></a>Trinn 3: Å opprette skjermen SelectTask
I dette trinnet viser vi en fremgangsmåte for å navigere til de andre skjermene i appen og for å arbeide med noen av kontrollene, formlene og formateringsalternativene som tilbys i PowerApps.

### <a name="update-the-title-and-insert-introductory-text"></a>Å oppdatere tittelen og sette inn innledende tekst
1. Velg **SelectTask**-skjermen i venstre navigasjonsfelt.
2. I den midterste ruten velger du standard **[Tittel]**, deretter oppdaterer du **Tekst**-egenskapen til «Contoso-prosjektstyring».
   
    ![Tekst-egenskapen i formellinjen](./media/sharepoint-scenario-build-app/04-03-02-text-property.png)
3. Klikk eller trykk på **Etikett** på **Sett inn**-fanen, og deretter drar du etiketten ned under det øverste banneret.
   
    ![Å legge til en etikett](./media/sharepoint-scenario-build-app/04-03-03-text-default.png)
4. Angi følgende egenskaper for etiketten i formellinjen:
   
   * **Farge**-egenskapen = **DarkGray**

   * **Størrelse**-egenskapen = **18**

   * **Tekst**-egenskapen = «**Klikk eller trykk på en oppgave for å fortsette...»**
     
     ![Å oppdatere tekst for en etikett](./media/sharepoint-scenario-build-app/04-03-04-text-updated.png)

### <a name="add-two-navigation-buttons"></a>Å legge til to navigasjonsknapper
1. Klikk eller trykk på **Knapp** på **Sett inn**-fanen, og deretter drar du knappen ned under etiketten.
   
    ![Legg til-knappen](./media/sharepoint-scenario-build-app/04-03-05-button-default.png)
2. Angi følgende egenskaper for knappen i formellinjen:
   
   * **OnSelect** egenskapen = **Navigate(AssignManager, Fade)**. Når du kjører appen og klikker på denne knappen, kan du gå til den andre skjermen i appen, med en uttonet overgang mellom skjermene.

   * **Tekst**-egenskapen = **«Tilordne leder»**

3. Endre størrelsen på knappen for å få plass til teksten.
   
    ![Å oppdatere knappeteksten](./media/sharepoint-scenario-build-app/04-03-06-button-updated.png)
4. Sett inn en annen knapp med følgende egenskaper:
   
   * **OnSelect**-egenskapen = **Navigate(ViewProjects, Fade)**.

   * **Tekst**-egenskapen = **«Oppdateringsdetaljer»**
     
     ![Å oppdatere knappeteksten](./media/sharepoint-scenario-build-app/04-03-08-buttons-final.png)
     
     > [!NOTE]
     > Knappen kalles **Oppdater detaljer**, men vi går først til **ViewProjects**-skjermen for å velge et prosjekt som skal oppdateres.

### <a name="run-the-app"></a>Å kjøre appen
Appen gjør ikke mye ennå, men du kan kjøre den hvis du vil:

1. Klikk eller trykk på **SelectTask**-skjermen (appen starter alltid fra valgte skjerm i forhåndsvisningsmodus i PowerApps Studio).

2. Klikk eller trykk på ![Kjør app-ikonet](./media/sharepoint-scenario-build-app/icon-run-arrow.png) øverst til høyre for å kjøre appen.

3. Klikk eller trykk på én av knappene for å navigere til en annen skjerm.

4. Klikk eller trykk på ![Lukk forhåndsvisning-ikonet for appen](./media/sharepoint-scenario-build-app/icon-close-preview.png) øverst til høyre for å lukke appen.

## <a name="step-4-build-the-assignmanager-screen"></a>Trinn 4: Å bygge skjermen AssignManager
I dette trinnet bruker vi et galleri for å vise alle prosjekter som har blitt godkjent, men som ennå ikke har en overordnet leder. Vi skal legge til andre kontroller, slik at du kan tilordne en leder.

> [!NOTE]
>  Vi skal opprette en side senere i appen, som lar deg redigere alle felt for et prosjekt (inkludert overordnet-feltet), men vi tenkte det ville være kult å opprette en skjerm som dette i tillegg.

1. Lagre endringene du har gjort så langt.

2. Klikk eller trykk på **AssignManager** i venstre navigasjonsfelt.

### <a name="update-the-title-and-insert-introductory-text"></a>Å oppdatere tittelen og sette inn innledende tekst

1. Endre **[Tittel]** til **Tilordne leder**.

2. Legg til en etikett med følgende egenskaper:
   
   * **Farge**-egenskapen = **DarkGray**

   * **Størrelse**-egenskapen = **18**

   * **Tekst**-egenskapen = «**Velg et prosjekt og tilordne deretter en leder»**
     
     ![Oppsett for tilordning av leder](./media/sharepoint-scenario-build-app/04-04-01-layout.png)

### <a name="add-a-back-arrow-to-return-to-the-selecttask-screen"></a>Legg til en Tilbake-pil for å gå tilbake til SelectTask-skjermen

1. Klikk eller trykk den blå linjen øverst på skjermen.

2. Klikk eller trykk på **Ikoner** på **Sett inn**-fanen, og deretter klikker eller trykker du på **Venstre**.
   
    ![Å sette inn Pil venstre](./media/sharepoint-scenario-build-app/04-04-02-icon-left.png)

3. Flytt pilen til venstre side for den blå linjen, og angi følgende egenskaper:
   
   * **Farge**-egenskapen = **Hvit**

   * **Høyde**-egenskapen = **40**

   * **OnSelect**-egenskapen = **Navigate(SelectTask, Fade)**

   * **Bredde**-egenskapen = **40**
     
     ![Å legge til Tilbake-knappen](./media/sharepoint-scenario-build-app/04-04-03-left-arrow.png)

### <a name="add-and-modify-a-gallery"></a>Å legge til og endre et galleri

1. På **Sett inn**-fanen, klikker eller trykker du på **Galleri**, deretter på **Loddrett**.
   
    ![Å legge til et loddrett galleri](./media/sharepoint-scenario-build-app/04-04-04-gallery.png)

2. Velg **tittel, undertittel og brødtekst** fra **Oppsett**-menyen i den høyre ruten. 
   
    ![Endring av gallerioppsettet](./media/sharepoint-scenario-build-app/04-04-04a-gallery-layout.png)
   
    Galleriet har nå det rette oppsettet, men det har fortsatt standard-eksempelteksten. Vi fikser dette etterpå.
   
    ![Galleri med standardtekst](./media/sharepoint-scenario-build-app/04-04-05-gallery-default.png)

3. Angi følgende egenskaper for galleriet:
   
   * **BorderThickness**-egenskapen = **1**

   * **BorderStyle**-egenskapen = **Prikket**

   * **Elementer**-egenskapen = **Filter('Project Details', PMAssigned="Unassigned")**. Bare prosjekter uten overordnede som er tilordnet, er inkludert i galleriet.
     
     ![Galleri med tekst fra listen](./media/sharepoint-scenario-build-app/04-04-06-gallery-updated.png)

4. Oppdater feltene i høyre rute for å samsvare med den følgende listen:
   
   * **ApprovedDate**

   * **Status**

   * **Tittel**
     
     ![Gallerifelt](./media/sharepoint-scenario-build-app/04-04-07-gallery-fields.png)

5. Endre størrelsen på etikettene i galleriet etter behov, og fjern pilen fra det første gallerielementet (vi ikke trenger å navigere noe sted fra dette galleriet).
   
    ![Å fjerne pil-ikonet](./media/sharepoint-scenario-build-app/04-04-07a-remove-arrow.png)
   
    Skjermen skal nå se ut som på følgende bilde.
   
    ![Formatert galleri](./media/sharepoint-scenario-build-app/04-04-07b-gallery-size-text.png)

### <a name="change-the-color-of-an-item-if-its-selected"></a>Endre fargen på et element hvis det er valgt

1. Velg galleriet, og angi deretter **TemplateFill**-egenskapen til **If (ThisItem.IsSelected=true, Orange, White)**.

2. Velg et element i galleriet. Skjermen skal nå se ut som på følgende bilde.
   
    ![Galleri med valgt element](./media/sharepoint-scenario-build-app/04-04-08-gallery-selected.png)

### <a name="add-a-label-text-input-and-ok-button-to-submit-manager-assignments"></a>Legg til en etikett, innskriving av tekst og OK-knappen for å sende leder-oppgaver

1. Klikk eller trykk utenfor galleriet du har arbeidet i.

2. Klikk eller trykk på **Etikett** på **Sett inn**-fanen. Dra etiketten under galleriet til venstre. Angi følgende egenskaper for etiketten:
   
   * **Størrelse**-egenskapen = **20**

   * **Tekst**-egenskapen = **«Leder:»**
   
   ![Å legge til Leder-etikett](./media/sharepoint-scenario-build-app/04-04-09-controls-text.png)

3. Klikk eller trykk på **Tekst** på **Sett inn**-fanen, og klikk eller trykk deretter på **Tekstinndata**. Dra tekstinndataene til under galleriet, i midten. Angi følgende egenskaper for rullegardinlisten:
   
   * **Standard**-egenskapen = **""**

   * **Høyde**-egenskapen = **60**

   * **Størrelse**-egenskapen = **20**

   * **Bredde**-egenskapen = **250**
   
   ![Å legge til tekstinndata](./media/sharepoint-scenario-build-app/04-04-10-controls-text-box.png)

4. Klikk eller trykk på **Knapp** på **Sett inn**-fanen. Dra knappen til under galleriet, til høyre. Angi følgende egenskaper for knappen:
   
   * **Høyde**-egenskapen = **60**

   * **OnSelect**-egenskapen = **Patch('Project Details', LookUp('Project Details', ID = Gallery1.Selected.ID), {PMAssigned: TextInput1.Text})**. Hvis du vil ha mer informasjon, kan du se [Grundig innføring i formler](#formula-deep-dive).

   * Formelen oppdaterer **Prosjektdetaljer**-listen og angir en verdi for feltet PMAssigned.

   * **Størrelse**-egenskapen = **20**

   * **Tekst**-egenskapen = **«OK»**

   * **Bredde**-egenskapen = **80**
   
   ![Å legge til OK-knapp](./media/sharepoint-scenario-build-app/04-04-11-controls-button.png)

Det fullførte skjermbildet skal nå se ut som på følgende bilde.

![Ferdig med Tilordne leder-skjermen](./media/sharepoint-scenario-build-app/04-04-12-complete.png)

## <a name="step-5-build-the-viewprojects-screen"></a>Trinn 5: Å bygge ViewProjects-skjermen
I dette trinnet skal vi endre egenskaper for galleriet på **ViewProjects**-skjermen. Dette galleriet viser elementer fra **Prosjektdetaljer**-listen. Du velger et element på denne skjermen, og deretter redigerer du detaljene på **UpdateDetails**-skjermen.

1. Klikk eller trykk på **ViewProjects** i venstre navigasjonsfelt.

2. Endre **[Tittel]** til **«Vis prosjekter»**.

3. Klikk eller trykk på **BrowserGallery1** i venstre navigasjonsfelt under **ViewProjects**.

4. Velg **tittel, undertittel og brødtekst** fra **Oppsett**-menyen i den høyre ruten. 
   
    ![Å endre gallerioppsettet](./media/sharepoint-scenario-build-app/04-04-04a-gallery-layout.png)
   
    Galleriet har nå det rette oppsettet, med standard eksempeltekst.
   
    ![Galleri med standardtekst](./media/sharepoint-scenario-build-app/04-04-04b-gallery-default.png)

5. Velg oppdateringsknappen ![Oppdater ikon](./media/sharepoint-scenario-build-app/icon-refresh.png), og angi **OnSelect**-egenskapen til **Oppdater («Prosjektdetaljer»)**.

6. Velg knappen for nytt element, ![Legg til nytt ikon](./media/sharepoint-scenario-build-app/icon-add-item.png), og angi **OnSelect**-egenskapen til **NewForm(EditForm1); Navigate(UpdateDetails, ScreenTransition.None)**.

### <a name="add-a-back-arrow-to-return-to-the-selecttask-screen"></a>Legg til en Tilbake-pil for å gå tilbake til SelectTask-skjermen

1. Klikk eller trykk på **AssignManager** i venstre navigasjonsfelt.

2. Velg tilbakepilen du har lagt til der, og kopier den.

3. Lim inn pilen på **ViewProjects**-skjermen, og plasser den til venstre for Oppdater-knappen. 
   
    ![Tilbake-knapp](./media/sharepoint-scenario-build-app/04-05-04-left-arrow-v.png)
   
    Alle egenskapene kommer sammen med den, inkludert **OnSelect**-egenskapen for **Navigate(SelectTask, Fade)**.

### <a name="change-the-data-source-for-the-browsegallery1-gallery"></a>Å endre datakilden for BrowseGallery1-galleriet

1. Velg **BrowseGallery1**-galleriet, og angi **Elementer**-egenskapen for galleriet til **SortByColumns(Filter('Project Details', StartsWith(Title, TextSearchBox1.Text)), "Title", If(SortDescending1, Descending, Ascending))**.
   
    Dette angir datakilden for galleriet til **Prosjektdetaljer**-listen, og bruker **Tittel**-feltet til søking og sortering.

2. Velg ![Detaljer-pilikonet](./media/sharepoint-scenario-build-app/icon-details-arrow.png) i det første gallerielementet, og angi **OnSelect**-egenskapen til **Navigate(UpdateDetails, None)**.
   
    ![ Vis prosjekter-galleri – første element valgt](./media/sharepoint-scenario-build-app/04-05-05b-gallery-arrow-v.png)

3. Oppdater feltene i høyre rute for å samsvare med den følgende listen:
   
   * **Status**

   * **PMAssigned**

   * **Tittel**
     
     ![Gallerifelt](./media/sharepoint-scenario-build-app/04-05-06-gallery-fields.png)
     
     Det fullførte skjermbildet skal nå se ut som på følgende bilde.
     
     ![Vis ferdig Prosjekt-skjerm](./media/sharepoint-scenario-build-app/04-05-07-viewprojects-final.png)

## <a name="step-6-build-the-updatedetails-screen"></a>Trinn 6: Å opprette skjermen UpdateDetails
I dette trinnet skal vi koble redigeringsskjemaet på **UpdateDetails**-skjermen til datakilden, og vi vil gjøre noen endringer for egenskaper og felt. På denne skjermen kan du redigere detaljer for et prosjekt som du har valgt på **Vis prosjekter**-skjermen.

1. Klikk eller trykk på **UpdateDetails** i det venstre navigasjonsfeltet.

2. Endre **[Tittel]** til **«Oppdater detaljer»**.

3. Klikk eller trykk på **EditForm1** i det venstre navigasjonsfeltet under **UpdateDetails**.

4. Angi følgende egenskaper for skjemaet:
   
   * **DataSource**-egenskapen = **«Prosjektdetaljer»**

   * **Element**-egenskapen = **BrowseGallery1.Selected**

5. I den høyre ruten, hvorpå skjemaet fremdeles er valgt, merker du av for følgende felt i vist rekkefølge:
   
   * **Tittel**

   * **PMAssigned**

   * **Status**

   * **ProjectedStartDate**

   * **ProjectedEndDate**

   * **ProjectedDays**

   * **ActualDays**
     
     ![Å redigere skjemafelt](./media/sharepoint-scenario-build-app/04-06-03-edit-fields.png)
6. Velg Avbryt-knappen ![Avbryt-ikon](./media/sharepoint-scenario-build-app/icon-cancel.png), og angi **OnSelect**-egenskapen til **ResetForm(EditForm1); Back()**.

7. Velg Lagre-knappen ![Lagre-ikon](./media/sharepoint-scenario-build-app/icon-check-mark.png), og se på **OnSelect**-formelen – **SubmitForm(EditForm1)**. Fordi vi bruker redigeringskontrollen for skjemaet, kan vi bruke **Submit()** i stedet for å bruke **Patch()**, som vi gjorde tidligere.

Den fullførte skjermen skal nå se ut som bildet nedenfor (hvis feltene er tomme, sørger du for at du velger et element på **Vis prosjekter**-skjermen).

![Oppdater detaljer-skjermbildet fullført](./media/sharepoint-scenario-build-app/04-06-06-edit-final.png)

## <a name="step-7-run-the-app"></a>Trinn 7: Å kjøre appen
Nå som appen er fullført, kan vi kjøre den for å se hvordan den fungerer. Vi skal legge til en kobling på SharePoint-området til appen. Du vil kunne kjøre appen i nettleseren, men du må kanskje dele den med andre for at de skal kunne kjøre den. Du finner mer informasjon i [Å dele en app](https://powerapps.microsoft.com/guided-learning/learning-manage-share-apps).

### <a name="add-a-link-to-the-app"></a>Å legge til en kobling til appen
1. Klikk eller trykk på **PowerApps** i startprogrammet for Office 365.
   
    ![PowerApps i startprogrammet for Office 365](./media/sharepoint-scenario-build-app/04-07-02a-waffle.png)

2. Klikk eller trykk på ellipsen (**. . .**) for **App for prosjektstyring** i PowerApps, og trykk deretter på **Åpne**.
   
    ![Velg app for prosjektstyring](./media/sharepoint-scenario-build-app/04-07-02b-select-app.png)

3. Kopier adressen (Nettadresse) for appen i nettleseren.
   
    ![Å kopiere appens nettadresse](./media/sharepoint-scenario-build-app/04-07-02ba-copy-url.png)

4. Klikk eller trykk på **REDIGER KOBLINGER** i SharePoint.
   
    ![Å redigere koblinger for SharePoint-område](./media/sharepoint-scenario-build-app/04-07-02c-edit-links.png)

5. Klikk eller trykk på **(+) kobling**.
   
    ![Å legge til kobling for appen til SharePoint-område](./media/sharepoint-scenario-build-app/04-07-02d-add-link.png)

6. Skriv inn «App for prosjektstyring», og lim inn adressen for appen.
   
    ![Å redigere koblingsegenskaper](./media/sharepoint-scenario-build-app/04-07-02e-link-dialog.png)

7. Klikk eller trykk på **OK**, deretter på **Lagre**.
   
    ![Å lagre koblingsendringer](./media/sharepoint-scenario-build-app/04-07-02f-save.png)

### <a name="assign-a-manager-to-a-project"></a>Å tilordne en leder til et prosjekt
Nå som vi har appen på SharePoint-området, skal vi finne en rolle for godkjenneren av prosjektet. Vi kan se etter prosjekter som ikke har en tilordnet leder, og tilordner deretter en leder til ett av prosjektene. Deretter skal vi tildele rollen til prosjektstyreren, og legge til litt informasjon om et prosjekt som er tildelt oss.

1. Først skal vi se på **Prosjektdetaljer**-listen i SharePoint. To prosjekter har verdien **Ikke tilordnet** i **PMAssigned**-kolonnen. Vi ser disse i appen.
   
    ![Ikke-tilordnede prosjekter i SharePoint-liste](./media/sharepoint-scenario-build-app/04-07-01-unassigned.png)

2. Klikk eller trykk på koblingen som du opprettet i appen.

3. Klikk eller trykk på **Tilordne leder** på den første skjermen.
   
    ![Introduksjonsskjerm for app](./media/sharepoint-scenario-build-app/04-07-03-intro-screen.png)

4. På **Tilordne leder**-skjermen ser du de to ikke-tilordnede prosjektene fra listen. Velg **Ny BI-programvare**-prosjektet.
   
    ![Galleri med valgt element](./media/sharepoint-scenario-build-app/04-07-04-selected.png)

5. I **Leder**-tekstinndataene skriver du inn «Ingjerd Espeseth», og deretter klikker du på **OK**.
   
    Endringen brukes i listen, og galleriet oppdateres slik at bare det gjenværende ikke-tilordnede prosjektet vises.
   
    ![Å tilordne en leder til et prosjekt](./media/sharepoint-scenario-build-app/04-07-05-updated.png)

6. Gå tilbake til SharePoint-listen, og oppdater siden. Du ser at prosjektoppføringen nå er oppdatert med navnet på prosjektstyrer.
   
    ![Prosjektlederen er tilordnet i SharePoint-listen](./media/sharepoint-scenario-build-app/04-07-07-assigned.png)

### <a name="update-details-for-the-project"></a>Å oppdatere detaljer for prosjektet

1. Klikk eller trykk på ![Tilbake-ikon](./media/sharepoint-scenario-build-app/icon-back.png) for å gå tilbake til det første skjermbildet, klikk eller trykk deretter på **Oppdater detaljer**.
   
   ![Introduksjonsskjerm for app](./media/sharepoint-scenario-build-app/04-07-08-intro-screen.png)

2. På **Vis prosjekter**-skjermen skriver du inn «Ny» i søkeboksen.
   
   ![Å søke i appgalleriet](./media/sharepoint-scenario-build-app/04-07-09-search-new.png)

3. Klikk på ![Detaljer-pilikonet](./media/sharepoint-scenario-build-app/icon-details-arrow.png) for **Ny BI-programvare**-elementet.
   
   ![Gallerielement er valgt](./media/sharepoint-scenario-build-app/04-07-10-select-project.png)

4. Angi følgende verdier på **Oppdater detaljer**-skjermen:
   
   * **ProjectedStartDate**-feltet = «6/3/2017»

   * **ProjectedEndDate**-feltet = «24/3/2017»

   * **ProjectedDays**-feltet = «15»
   
   ![Å oppdatere detaljer for element](./media/sharepoint-scenario-build-app/04-07-11-update.png)

5. Klikk eller trykk på ![hakemerkeikonet](./media/sharepoint-scenario-build-app/icon-check-mark.png) for å bruke endringen i SharePoint-listen.

6. Lukk appen, og gå tilbake til listen. Du ser at prosjektoppføringen nå er oppdatert med endringene for dato og ukedag.
   
    ![Oppdatert SharePoint-liste](./media/sharepoint-scenario-build-app/04-07-11-updated-list.png)

## <a name="formula-deep-dive"></a>Grundig innføring i formler
Dette er den andre valgfrie inndelingen i PowerApps-formler. I den første grundige innføringen så vi på én av formlene som PowerApps genererer for Bla gjennom-galleriet i en app med tre skjermer. I denne grundige innføringen skal vi se på en formel vi bruker for **AssignManager**-skjermen for den andre appen. Her er formelen:

**Patch ( 'Project Details', LookUp ( 'Project Details', ID = Gallery1.Selected.ID ), {PMAssigned: TextInput1.Text} )**

Hva gjør denne formelen? Når du velger et element i galleriet og klikker på **OK**-knappen, oppdaterer formelen **Prosjektdetaljer**-listen og angir **PMAssigned**-kolonnen til verdien som du angir i teksten. Formelen bruker funksjoner:

* [**Patch-**-funksjonen](functions/function-patch.md) endrer én eller flere poster for en datakilde.

* [**LookUp**-funksjonen](functions/function-filter-lookup.md) finner den første posten i en tabell som oppfyller en formel.

Når du plasserer funksjonene sammen i formelen, skjer følgende:

1. Når du klikker på **OK**-knappen, brukes **Patch**-funksjonen til å oppdatere **Prosjektdetaljer**-listen.

2. I **Patch**-funksjonen identifiserer **LookUp**-funksjonen hvilken rad i **Prosjektdetaljer**-listen som skal oppdateres. Den gjør dette ved å sammenligne ID-en for det merkede gallerielementet med ID-en i listen. En ID for 12 betyr eksempelvis at oppføringen for **Ny BI-programvare** bør oppdateres.

3. Nå som **Patch**-funksjonen har riktig ID, oppdaterer den **PMAssigned**-feltet med verdien i **TextInput1.Text**.

## <a name="next-steps"></a>Neste trinn
Det neste trinnet i denne opplæringsserien handler om å [opprette en Power BI-rapport til å analysere prosjekter](sharepoint-scenario-build-report.md).

