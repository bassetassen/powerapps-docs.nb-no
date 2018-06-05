---
title: Å opprette en app fra bunnen av | Microsoft Docs
description: Å opprette en app fra bunnen av ved å konfigurere hvert grensesnittelement og hver virkemåte til å administrere vanlige data som holder bedriften i gang.
services: ''
suite: powerapps
documentationcenter: na
author: AFTOwen
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/16/2016
ms.author: anneta
ms.openlocfilehash: efc965d607198ed6366f3390960ccdf44b2ea210
ms.sourcegitcommit: 078ba325480147e6e4da61e319ed53219f1c5cfc
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/06/2018
ms.locfileid: "30998362"
---
# <a name="create-an-app-from-scratch"></a>Å opprette en app fra bunnen av
Opprett din egen app fra bunnen av ved å velge blant en rekke datakilder, og du kan legge til flere kilder senere om du ønsker. Angi utseende og virkemåte for hvert grensesnittelement, slik at du kan optimalisere resultatet for bestemte mål og arbeidsflyter. Denne fremgangsmåten er mye mer tidkrevende enn [automatisk generering av en app](get-started-create-from-data.md), men erfarne apputviklere kan lage de beste appene for et gitt behov.

Du oppretter en app med to skjermer ved å følge denne opplæringen. På den ene skjermen kan brukerne bla gjennom et sett med poster:

![En skjerm der en bruker kan bla gjennom et sett med data](./media/get-started-create-from-blank/first-screen-final.png)

På den andre skjermen kan brukere opprette en post, oppdatere ett eller flere felt i en post eller slette en hel post:

![En skjerm der en bruker kan legge til eller oppdatere data](./media/get-started-create-from-blank/changescreen-final.png)

## <a name="prerequisites"></a>Forutsetninger
Du kan bruke din egen Excel-fil og se gjennom denne opplæringen for bare generelle begreper. Dataene i Excel-filen må imidlertid være formatert som en tabell. Hvis du vil ha mer informasjon, kan du se [Formater en tabell i Excel](how-to-excel-tips.md).

For å følge trinnene nedenfor nøyaktig, må du først opprette en Excel-fil ved hjelp av disse eksempeldataene.

1. Kopier disse dataene, og lim dem deretter inn i en Excel-fil.

   | Startdag | Starttid | Frivillig 1 | Frivillig 2 |
   | --- | --- | --- | --- |
   | Lørdag |10–12 |Åmodt |Kollerud |
   | Lørdag |12–14 |Edland |Stensen |
   | Lørdag |14–16 |Koch |Kolstad |
   | Søndag |10–12 |Hustoft |Alvestad |
   | Søndag |10–12 |Simonsen |Reiersen |
   | Søndag |10–12 |Bjerklund |Vestre |

2. Formater dataene som en tabell, kalt **Tidsplan**, slik at PowerApps kan analysere informasjonen.

    Hvis du vil ha mer informasjon, kan du se [Formater en tabell i Excel](how-to-excel-tips.md).

3. Lagre filen under navnet **eventisgnup.xls**, og last den deretter opp i en [skylagringskonto](connections/cloud-storage-blob-connections.md), for eksempel OneDrive.

4. Hvis du er ny PowerApps-bruker:

   * Finn ut hvordan du kan [legge til en kontroll og angi egenskapene](add-configure-controls.md), noe som bestemmer hvordan kontrollen vises og virker.
   * Finn ut hvordan du kan [legge til og gi nytt navn til en skjerm](add-screen-context-variables.md).

## <a name="create-a-blank-app-and-connect-to-data"></a>Oppretting av en tom app, og tilkobling til data
1. Klikk eller trykk på **Ny** på **Filmenyen** i PowerApps Studio (nær venstre kant av skjermen).

    ![Ny-alternativet på Fil-menyen](./media/get-started-create-from-blank/file-new.png)

2. Klikk eller trykk på **Telefonoppsett** på **Tom app**-flisen.

    ![Alternativ for å opprette en app fra data](./media/get-started-create-from-blank/create-from-blank.png)

3. Hvis du blir bedt om det, kan du følge omvisningen for å se de viktigste områdene i PowerApps (eller klikk eller trykk på **Hopp over**).

    ![Hurtigomvisning](./media/get-started-create-from-blank/quick-tour.png)

    Du kan følge omvisningen når som helst ved å klikke eller trykke på spørsmålstegn-ikonet nær hjørnet øverst til høyre på skjermen, og deretter klikke eller trykke på **Følg omvisningen**.

4. Klikk eller trykk på et ikon øverst til høyre i venstre navigasjonsfelt for å bytte til miniatyrbildevisningen.

    ![Å veksle mellom visningene](./media/get-started-create-from-blank/toggle-view.png)

5. Klikk eller trykk på **Legg til datakilde** i ruten til høyre.

    ![Å legge til en datakilde](./media/get-started-create-from-blank/add-data-source.png)

6. Følg ett av disse trinnene:

   * Hvis du allerede har en tilkobling til skylagringskontoen, klikker eller trykker du på denne.
   * Hvis du ikke har tilkobling til skylagringskontoen, kan du klikke eller trykke på **Legg til en tilkobling**, klikke eller trykke på kontotypen din eller på **Koble til**, og deretter (hvis du blir bedt om det) oppgir du legitimasjonen din.

7. Bla til **eventsignup.xlsx** under **Velg en Excel-fil**, og deretter klikker eller trykker du på den.

    ![Å angi hvilken Excel-fil du ønsker å bruke](./media/get-started-create-from-blank/select-excel-file.png)

8. Merk av for **Tidsplan** under **Velg en tabell**, og klikk eller trykk deretter på **Koble til**.

    ![Å angi hvilken Excel-tabell du ønsker å bruke](./media/get-started-create-from-blank/select-table.png)

    **Datakilder**-fanen i den høyre ruten viser hvilke data datakilder du har lagt til i appen.

    ![Å vise tilkoblede datakilder](./media/get-started-create-from-blank/data-connect.png)

    Denne opplæringen krever bare én datakilde, men du kan legge til flere datakilder senere.

## <a name="show-the-data"></a>Å vise dataene
1. Klikk eller trykk på **Ny skjerm** på **Hjem**-fanen, og klikk eller trykk deretter på **Listeskjerm**.

    ![Å legge til et oppsett med en overskrift, undertittel og et brødtekstelement](./media/get-started-create-from-blank/add-gallery.png)

    En skjerm er lagt til med flere standardkontroller, for eksempel en søkeboks og en **[Galleri](controls/control-gallery.md)**-kontroll. Galleriet dekker hele skjermen under søkeboksen.

2. Klikk eller trykk hvor som helst i galleriet, unntatt på pilen, for eksempel rett under søkeboksen.

    ![Å velge galleri](./media/get-started-create-from-blank/select-gallery.png)

3. Åpne **Oppsett**-listen i ruten til høyre, og klikk eller trykk deretter på alternativet som viser tittel, undertittel og brødtekst.

    ![Å velge galleri](./media/get-started-create-from-blank/select-layout.png)

4. Klikk eller trykk på **[Items](controls/properties-core.md)** i egenskaperlisten, kopier denne formelen og lim den inn i formellinjen:

    **SortByColumns(Search(Schedule, TextSearchBox1.Text, "Volunteer_x0020_1"), "Volunteer_x0020_1", If(SortDescending1, SortOrder.Descending, SortOrder.Ascending))**

    Hvis du ikke er sikker på hvor egenskapslisten er, kan du se [Legg til og konfigurer kontroller](add-configure-controls.md).

    > [!NOTE]
> For Excel- eller SharePoint-datakilder som inneholder kolonnenavn med mellomrom, viser PowerApps mellomrommene som **\_x0020\_**. I dette eksemplet vises kolonnen **"Volunteer 1"** i en formel som **"Volunteer_x0020_1"**.

    Dette galleriet viser dataene fra **Tidsplan**-tabellen.

    ![Tidsplan-dataene i galleriet som standard](./media/get-started-create-from-blank/show-data-default.png)

    En søkeboks kan filtrere galleriet basert på teksten brukeren skriver inn. Hvis en bruker skriver minst én bokstav i søkeboksen, viser galleriet bare postene i **Frivillig 1**-feltet som inneholder teksten brukeren skrev inn.

    Sorter-knappen kan sortere poster basert på data i **Frivillig 1**-kolonnen. Hvis en bruker klikker eller trykker på denne knappen, vil sorteringsrekkefølgen veksle mellom stigende og synkende.

    Denne formelen inneholder funksjonene **Sort**, **If**, **IsBlank**, **Filter** og **Text**. Hvis du vil ha mer informasjon om disse og andre funksjoner, kan du se [formelreferansen](formula-reference.md)

5. Skriv inn en **i** i søkeboksen, og klikk eller trykk på sorter-knappen én gang (eller et par ganger).

    Galleriet viser disse resultatene.

    ![Å sortere og filtrere galleriet](./media/get-started-create-from-blank/sort-filter.png)

    Mer informasjon om funksjonene **[Sort](functions/function-sort.md)**, **[Filter](functions/function-filter-lookup.md)** og [andre funksjoner](formula-reference.md)

6. Velg **[Etikett](controls/control-text-box.md)**-kontrollen øverst på skjermen ved å klikke eller trykke på kontrollen.

    ![Å velge tittellinje](./media/get-started-create-from-blank/select-title-bar.png)

7. Klikk eller trykk på **[Tekst](controls/properties-core.md)** i egenskapslisten, kopier denne teksten, og lim den deretter inn i formellinjen.<br>
   **Vis poster**

    ![Å endre tittellinjen](./media/get-started-create-from-blank/change-title-bar.png)

## <a name="create-the-changescreen-and-its-banner"></a>Opprett ChangeScreen og tilhørende banner
1. Slett **Screen1**, og gi **Screen2** det nye navnet **ViewScreen**.

    ![Å gi nytt navn til skjerm](./media/get-started-create-from-blank/rename-screen.png)

2. Legg til en skjerm, og gi den det nye navnet **ChangeScreen**.

    ![Å legge til skjerm, og gi den nytt navn](./media/get-started-create-from-blank/add-screen.png)

3. Klikk eller trykk på **Tekst** på **Sett inn**-fanen, og klikk eller trykk deretter på **[Etikett](controls/control-text-box.md)**.

4. Konfigurer **Etikett**-kontrollen du nettopp la til:

   * Angi **Tekst**-egenskapen til denne formelen:
     <br>**"Change record"**

   * Angi **Fyll**-egenskapen til denne formelen:
     <br>**RGBA(62, 96, 170, 1)**.

   * Angi **Farge**-egenskapen til denne formelen:
     <br>**RGBA(255, 255, 255, 1)**

   * Angi **Juster**-egenskapen til **Midtstilt**.
   * Angi **X**-egenskapen til **0**.

   * Angi **Bredde**-egenskapen til **640**.
     **Etikett**-kontrollen gjenspeiler endringene.

     ![ChangeScreen med banner](./media/get-started-create-from-blank/change-screen-blank.png)

## <a name="add-and-configure-a-form"></a>Å legge til og konfigurere et skjema
1. Klikk eller trykk på **Skjemaer** på **Sett inn**-fanen, og klikk eller trykk deretter på **Rediger**.

2. Flytt og endre størrelsen på skjemaet så det dekker mesteparten av skjermen.

    ![Å legge til et skjema](./media/get-started-create-from-blank/add-form.png)

    Skjemaet heter **Skjema1** som standard, med mindre du allerede har lagt til og fjernet et skjema. I så fall må du gi skjemaet det nye navnet **Skjema1**.

3. Angi **[DataSource](controls/control-form-detail.md)**-egenskapen for **Skjema1** til **Tidsplan**.

4. Angi **Element**-egenskapen for **Skjema1** til dette uttrykket:
   <br>**BrowseGallery1.Selected**

5. Merk av for hvert felt i avmerkingsboksen for å vise det i ruten til høyre.

    ![Å vise felt i skjema](./media/get-started-create-from-blank/schedule-checkbox.png)

6. Nær bunnen av skjemaet klikker eller trykker du på **Legg til et egendefinert kort**.

    ![Å legge til et egendefinert kort](./media/get-started-create-from-blank/add-custom-card.png)

7. Legg til en **[Etikett](controls/control-text-box.md)**-kontroll i det nye kortet.

8. Angi **[AutoHeight](controls/control-text-box.md)**-egenskapen for den nye kontrollen til **sann**, og angi **[Tekst](controls/properties-core.md)**-egenskapen til denne formelen:
   <br>**Form1.Error**

    Etiketten viser alle feil i skjemaet.

9. Klikk eller trykk på miniatyrbildet for **ChangeScreen** i venstre navigasjonsrute for å velge det.

10. Klikk eller trykk på **Ikoner**, klikk eller trykk på alternativet for å legge til en **Tilbake-pil**, og flytt deretter pilen til hjørnet nederst til venstre på skjermen, på **Sett inn**-fanen.

11. Angi pilens **[OnSelect](controls/properties-core.md)**-egenskap til denne formelen:

     **ResetForm(Form1);Navigate(ViewScreen,ScreenTransition.None)**

      Når brukeren klikker eller trykker på pilen, åpner **[Navigate](functions/function-navigate.md)**-funksjonen **ViewScreen**.

12. Legg til en **[Knapp](controls/control-button.md)** under skjemaet, og angi knappens **[Tekst](controls/properties-core.md)**-egenskap til **Lagre**.

     ![Å legge til en lagringsknapp](./media/get-started-create-from-blank/add-save-button.png)

13. Angi **[OnSelect](controls/properties-core.md)**-egenskapen for knappen til denne formelen:

    **SubmitForm(Form1); If(Form1.ErrorKind = ErrorKind.None, Navigate(ViewScreen, ScreenTransition.None))**

    Når brukeren klikker eller trykker på knappen, lagrer **[SubmitForm](functions/function-form.md)**-funksjonen alle endringer i datakilden, og **ViewScreen** vises på nytt.

14. Legg til en ny knapp nederst på skjermen, angi **[Tekst](controls/properties-core.md)**-egenskapen til **Fjern**, og angi **[OnSelect](controls/properties-core.md)**-egenskapen til denne formelen:

    **Remove(Schedule,BrowseGallery1.Selected);<br>If(IsEmpty(Errors(Schedule)),Navigate(ViewScreen,ScreenTransition.None))**

    Når brukeren klikker eller trykker på denne knappen, fjerner **[Remove](functions/function-remove-removeif.md)**-funksjonen posten, og **ViewScreen** vises på nytt.

15. Angi **[Synlig](controls/properties-core.md)**-egenskapen for **Fjern**-knappen til denne formelen:
    <br>**Form1.Mode=FormMode.Edit**

    Dette trinnet skjuler **Fjern**-knappen når brukeren oppretter en post.

    **ChangeScreen** samsvarer med dette eksemplet:

    ![Endelig ChangeScreen](./media/get-started-create-from-blank/changescreen-final.png)

## <a name="set-navigation-from-viewscreen"></a>Å angi navigasjon fra ViewScreen
1. Klikk eller trykk på miniatyrbildet for **ViewScreen** i venstre navigasjonsrute.

    ![Å åpne ViewScreen](./media/get-started-create-from-blank/select-viewscreen.png)

2. Klikk eller trykk på **Neste-pilen** for å finne den første posten i galleriet.

    ![Neste-pil](./media/get-started-create-from-blank/next-arrow.png)

3. Angi **[OnSelect](controls/properties-core.md)**-egenskapen for pilen til denne formelen:

    **Navigate(ChangeScreen,ScreenTransition.None)**

4. Klikk eller trykk på plussikonet i hjørnet øverst til høyre.

    ![Å legge til post](./media/get-started-create-from-blank/add-record.png)

5. Angi **[OnSelect](controls/properties-core.md)**-egenskapen for det valgte ikonet til denne formelen:

    **NewForm(Form1);Navigate(ChangeScreen,ScreenTransition.None)**`

     Når brukeren klikker eller trykker på dette ikonet, vises **ChangeScreen** med tomme felt, slik at brukeren enklere kan opprette en post.

## <a name="run-the-app"></a>Å kjøre appen
Når du tilpasser appen, kan du teste endringene ved å kjøre appen i forhåndsvisningsmodus, slik fremgangsmåten i denne inndelingen beskriver.

1. Klikk eller trykk på det øverste miniatyrbildet i navigasjonsfeltet til venstre for å velge**ViewScreen**.

    ![Å velge ViewScreen](./media/get-started-create-from-blank/select-viewscreen.png)

2. Åpne Forhåndsvisningsmodus ved å trykke på F5 (eller klikke eller trykke på **Forhåndsvisning-ikonet** nær hjørnet øverst til høyre).

    ![Å åpne Forhåndsvisningsmodus](./media/get-started-create-from-blank/open-preview.png)

3. Klikk eller trykk på Neste-pilen for å se en post som viser detaljer om denne posten.

4. Endre informasjonen i ett eller flere av feltene på **ChangeScreen**, og lagre deretter endringene ved å klikke eller trykke på **Lagre**, eller fjern posten ved å klikke eller trykke på **Fjern**.

5. Lukk Forhåndsvisningsmodus ved å trykke på ESC (eller ved å klikke eller trykke på lukkeikonet under tittellinjen).

    ![Lukk Forhåndsvisningsmodus](./media/get-started-create-from-blank/close-preview.png)

## <a name="next-steps"></a>Neste trinn
* Trykk på CTRL+S for å lagre appen i skyen, slik at du kan kjøre den fra andre enheter.
* [Del appen](share-app.md), slik at andre personer kan kjøre den.
* Finn ut mer om [gallerier](add-gallery.md), [skjemaer](add-form.md) og [formler](working-with-formulas.md).
