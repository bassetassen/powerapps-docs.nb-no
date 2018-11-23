---
title: Opprett en lerretsapp fra grunnen av basert på Excel-data | Microsoft Docs
description: Denne opplæringen beskriver hvordan du oppretter en lerretsapp med to skjermer, slik at brukerne kan opprette, redigere og slette poster i en Excel-fil.
author: AFTOwen
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 04/23/2018
ms.author: anneta
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 8c398bb7a916c98aa769e39477fe889a74fce32c
ms.sourcegitcommit: c1f58a16f8dcd309a1d5fc4658ca16d82c615994
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 11/23/2018
ms.locfileid: "51334000"
---
# <a name="create-an-canvas-app-from-scratch-based-on-excel-data"></a>Opprett en lerretsapp fra grunnen av basert på Excel-data

Opprett din egen lerretsapp fra grunnen av basert på Excel-data som er formatert som en tabell, og legg deretter til data fra andre kilder hvis du ønsker det. Du oppretter en app med to skjermer ved å følge denne opplæringen. På den ene skjermen kan brukerne bla gjennom et sett med poster. På den andre skjermen kan brukere opprette en post, oppdatere ett eller flere felt i en post eller slette en hel post. Denne fremgangsmåten er mye mer tidkrevende enn [automatisk generering av en app](get-started-create-from-data.md), men erfarne apputviklere kan bruke det til å lage de beste appene for et gitt behov.

## <a name="prerequisites"></a>Forutsetninger

Du må først opprette en Excel-fil ved hjelp av disse eksempeldataene for å følge trinnene i denne opplæringen nøyaktig.

1. Kopier disse dataene, og lim dem deretter inn i en Excel-fil.

    | StartDay | StartTime | Frivillig | Backup |
    | --- | --- | --- | --- |
    | Lørdag |10–12 |Åmodt |Kollerud |
    | Lørdag |12–14 |Edland |Stensen |
    | Lørdag |14–16 |Koch |Kolstad |
    | Søndag |10–12 |Hustoft |Alvestad |
    | Søndag |10–12 |Simonsen |Reiersen |
    | Søndag |10–12 |Bjerklund |Vestre |

2. Formater dataene som en tabell, kalt **Tidsplan**, slik at PowerApps kan analysere informasjonen.

    Hvis du vil ha mer informasjon, kan du se [Formater en tabell i Excel](how-to-excel-tips.md).

3. Lagre filen under navnet **eventisgnup.xls**, lukk den, og deretter laster du den opp til en [skylagringskonto](connections/cloud-storage-blob-connections.md), for eksempel OneDrive.

> [!IMPORTANT]
> Du kan bruke din egen Excel-fil og se gjennom denne opplæringen for bare generelle begreper. Dataene i Excel-filen må imidlertid være formatert som en tabell. Hvis du vil ha mer informasjon, kan du se [Formater en tabell i Excel](how-to-excel-tips.md).

## <a name="open-a-blank-app"></a>Å åpne en tom app
1. Logg deg på [PowerApps](http://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc).

    Du kan utforme en app fra grunnen av for telefoner eller andre enheter (for eksempel nettbrett). Dette emnet fokuserer på å utforme en app for telefoner.

1. Hold pekeren over flisen **Lag din egen app** under **Start fra tom**, velg telefonikonet, og velg deretter **Lag denne appen**.

    ![Flisen for tom app](./media/get-started-create-from-blank/start-from-blank.png)

    PowerApps Studio oppretter en tom app for telefoner.

1. Hvis dialogboksen **Velkommen til PowerApps Studio** åpnes, velger du **Hopp over**.

## <a name="connect-to-data"></a>Å koble til data
1. Midt på skjermen kan du velge **koble til data**.

1. Velg tilkoblingen for din skylagringskontoen i **Data**-ruten, hvis den vises. Ellers følger du disse trinnene for å legge til en tilkobling:

    1. Velg **Ny tilkobling**, velg flisen for skylagringskontoen din, og deretter velger du **Opprett**.
    2. Hvis du blir bedt om det, oppgir du legitimasjonen for denne kontoen.

1. Skriv eller lim inn de første bokstavene i **eventsignup** under **Velg en Excel-fil** for å filtrere listen, og velg deretter filen du lastet opp.

1. Merk av for **Tidsplan** under **Velg en tabell**, og deretter velger du **Koble til**.

## <a name="create-the-view-screen"></a>Å opprette visningsskjermen

1. Velg pil ned ved siden av **Ny skjerm** på **Hjem**-fanen for å åpne en liste over skjermtyper, og velg deretter **Listeskjerm**.

    ![Slik legger du til en listeskjerm](./media/get-started-create-from-blank/add-list-screen.png)

    En skjerm er lagt til med flere standardkontroller, for eksempel en søkeboks og en **[Galleri](controls/control-gallery.md)**-kontroll. Galleriet dekker hele skjermen under søkeboksen.

2. Velg galleriet ved å klikke eller trykke nær midten.

    En valgboks med håndtak omgir galleriet.

    ![Slik legger du til en listeskjerm](./media/get-started-create-from-blank/select-gallery.png)

3. I ruten til høyre velger du **CustomGallerySample** for å åpne **Data**-ruten.

    ![Å åpne dataruten](./media/get-started-create-from-blank/custom-gallery-sample.png)

4. Velg Pil ned under **Datakilde** for å åpne listen over datakilder for appen, og velg deretter **Tidsplan**.

    ![Å velge en datakilde](./media/get-started-create-from-blank/select-schedule.png)

5. Velg Pil ned under **Oppsett** for å åpne listen over oppsett, og velg deretter **tittel, undertittel og brødtekst**.

    ![Slik velger man oppsett](./media/get-started-create-from-blank/select-layout.png)

6. Endre kolonnen som vises fra **Backup** til **Frivillig** under **Tittel2**.

     ![Slik endrer man kolonnen i en etikett](./media/get-started-create-from-blank/change-title2.png)

7. Lukk **Data**-ruten ved å velge Lukk-ikonet øverst til høyre.

    Galleriet viser navnet på hver enkelt frivillig, samt dato og klokkeslett for den frivillige sin skifttid.

    ![Tidsplan-dataene i galleriet (usortert)](./media/get-started-create-from-blank/show-data-unsorted.png)

8. Velg galleriet, og bekreft at egenskapslisten viser **[Elementer](controls/properties-core.md)**.

    Som formellinjen viser, er verdien for denne egenskapen **Tidsplan**.

    ![Tidsplan-dataene i galleriet (usortert)](./media/get-started-create-from-blank/set-property.png)

9. Endre verdien for **Elementer**-egenskapen ved å kopiere denne formelen og lime den inn i formellinjen:

    **SortByColumns(Search(Schedule, TextSearchBox1.Text, "Volunteer"), "Volunteer", If(SortDescending1, SortOrder.Descending, SortOrder.Ascending))**

    Galleriet viser data i alfabetisk rekkefølge etter navn på frivillige.

    ![Tidsplan-dataene i galleriet (sortert)](./media/get-started-create-from-blank/show-data-sorted.png)

    Brukere kan sortere og filtrere galleriet etter navn på frivillige, basert på **SortByColumns**- og **Søk**-funksjonene i denne formelen.

   - Hvis en bruker skriver minst én bokstav i søkeboksen, viser galleriet bare de postene hvor **Frivillig**-feltet inneholder teksten brukeren skrev inn.
   - Hvis en bruker velger Sorter-knappen, vises postene i stigende eller synkende rekkefølge i galleriet (avhengig av hvor mange ganger brukeren velger knappen), basert på **Frivillig**-feltet.

     Hvis du vil ha mer informasjon om disse og andre funksjoner, kan du se [formelreferansen](formula-reference.md).

10. Skriv inn en **i** i søkeboksen, og velg sorteringsknappen ved å klikke eller trykke på den. Velg den deretter én gang til (eller flere ganger, alt ettersom).

     Galleriet viser disse resultatene.

     ![Å sortere og filtrere galleriet](./media/get-started-create-from-blank/sort-filter.png)

11. Fjern all tekst fra Søk-boksen.

12. Øverst på skjermen velger du **[Etikett](controls/control-text-box.md)**-kontrollen, og deretter erstatter du **[Tittel]** med **Vis poster**.

     ![Å endre tittellinjen](./media/get-started-create-from-blank/change-title-bar.png)

## <a name="create-the-change-screen"></a>Slik oppretter man skjermbildet for endring
1. På **Hjem**-fanen velger du Pil ned ved siden av **Ny skjerm**, og deretter velger du **Skjemaskjerm**.

     ![Å legge til skjemaskjerm](./media/get-started-create-from-blank/add-form-screen.png)

1. Velg **Koble til data** på skjermen du nettopp la til for å åpne **Data**-ruten, og deretter angir du datakilden til **Tidsplan**.

1. Merk av i alle avmerkingsboksene under **Felt** for å vise alle feltene i skjemaet.

     ![Å vise felt](./media/get-started-create-from-blank/show-fields.png)

1. Dra **Frivillig**-feltet opp slik at det vises øverst i listen over felt.

     ![Å endre rekkefølge på felt](./media/get-started-create-from-blank/reorder-fields.png)

1. Velg skjemaet, og angi **Element**-egenskapen til dette uttrykket ved å skrive eller lime den inn på formellinjen:<br>**BrowseGallery1.Selected**

1. Øverst på skjermen velger du **[Etikett](controls/control-text-box.md)**-kontrollen, og deretter erstatter du **[Tittel]** med **Endre poster**.

    ![Å endre tittellinjen](./media/get-started-create-from-blank/change-title-bar2.png)

## <a name="delete-and-rename-screens"></a>Å legge til og gi nytt navn til skjermer
1. I navigasjonsfeltet til venstre velger du ellipsen (...) for **Skjerm1**, og deretter velger du **Slett**.

    ![Å slette skjermer](./media/get-started-create-from-blank/delete-screen.png)

1. Velg ellipsen (...) for **Skjerm2**, velg **Gi nytt navn til**, og deretter skriver eller limer du inn **ViewScreen**.

1. Velg ellipsen (...) for **Skjerm3**, velg **Gi nytt navn til**, og deretter skriver eller limer du inn **ChangeScreen**.

## <a name="configure-icons-on-the-view-screen"></a>Å konfigurere ikoner på Vis-skjermen
1. Nær toppen av **ViewScreen** velger du det sirkelformede pilikonet.

    ![Å legge til post](./media/get-started-create-from-blank/refresh-icon.png)

1. Angi **OnSelect**-egenskapen for ikonet til denne formelen:<br>**Refresh(Schedule)**

    Når brukeren velger dette ikonet, oppdateres dataene fra **Tidsplan** fra Excel-filen.

    Hvis du vil ha mer informasjon om disse og andre funksjoner, kan du se [formelreferanse](formula-reference.md).

1. Øverst til høyre av **ViewScreen** velger du pluss-ikonet.

    ![Å legge til post](./media/get-started-create-from-blank/add-record.png)

1. Angi **OnSelect**-egenskapen for ikonet til denne formelen:<br>**NewForm(EditForm1);Navigate(ChangeScreen,ScreenTransition.None)**

    Når brukeren velger dette ikonet, vises **ChangeScreen** med tomme felt, slik at brukeren enklere kan opprette en post.

1. Velg pilen som peker mot høyre for å se den første posten i galleriet.

    ![Å velge pil](./media/get-started-create-from-blank/select-arrow.png)

1. Angi **OnSelect**-egenskapen for pilen til denne formelen:<br>**EditForm(EditForm1); Navigate(ChangeScreen, ScreenTransition.None)**

    Når brukeren velger dette ikonet, vises **ChangeScreen** med hvert felt som viser data for den valgte posten, slik at brukeren kan redigere eller slette posten enklere.

## <a name="configure-icons-on-the-change-screen"></a>Å konfigurere ikoner på Endre-skjermen
1. Velg ikonet «x» øverst til venstre på **ChangeScreen**.

    ![Avbryt-ikon](./media/get-started-create-from-blank/cancel-icon.png)

1. Angi **OnSelect**-egenskapen for ikonet til denne formelen:<br>**ResetForm(EditForm1);Navigate(ViewScreen, ScreenTransition.None)**

    Når brukeren velger dette ikonet, forkastes eventuelle endringer brukeren har gjort på denne skjermen, og visningsskjermen åpnes.

1. Velg hakeikonet øverst til høyre.

    ![Avmerking-ikon](./media/get-started-create-from-blank/checkmark-icon.png)

1. Angi **OnSelect**-egenskapen for hakemerket til denne formelen:<br>**SubmitForm(EditForm1); Navigate(ViewScreen, ScreenTransition.None)**

    Når brukeren velger dette ikonet, lagres eventuelle endringer brukeren har gjort for skjermen, og visningsskjermen åpnes.

1. Velg **Ikoner** på **Sett inn**-fanen, og deretter velger du **Papirkurv**-ikonet.

1. Angi det nye ikonets **farge**-egenskap til **Hvit**, og flytt det nye ikonet slik at det vises ved siden av hakeikonet.

    ![Papirkurv-ikon](./media/get-started-create-from-blank/trash-icon.png)

1. Angi **OnSelect**-egenskapen for papirkurvikonet til denne formelen:<br>**Remove(Schedule, BrowseGallery1.Selected); Navigate(ViewScreen, ScreenTransition.None)**

    Når brukeren velger dette ikonet, slettes den valgte posten fra datakilden, og Vis-skjermen åpnes.

## <a name="test-the-app"></a>Testing av appen
1. Velg **ViewScreen**, og åpne deretter Forhåndsvisning ved å trykke på F5 (eller ved å velge **Forhåndsvisning**-ikonet nær hjørnet øverst til høyre).

    ![Å åpne forhåndsvisningsmodus](./media/get-started-create-from-blank/open-preview.png)

1. Hent en post.

1. Oppdater posten som du har lagt til, og deretter lagrer du endringene.

1. Oppdater posten som du har lagt til, og deretter forkaster du endringene.

1. Slett posten du har lagt til.

1. Åpne forhåndsvisningsmodus ved å trykke på ESC (eller ved å velge Lukk-ikonet nær hjørnet øverst til høyre).

## <a name="next-steps"></a>Neste trinn

- Trykk på CTRL+S for å lagre appen i skyen, slik at du kan kjøre den fra andre enheter.
- [Del appen](share-app.md), slik at andre personer kan kjøre den.
- Finn ut mer om [funksjoner](working-with-formulas.md), for eksempel **Patch**, som du kan bruke til å administrere data uten å opprette et standardskjema.
- [Koble denne appen til en løsning](add-app-solution.md), slik at du for eksempel kan distribuere den til et annet miljø eller publisere den på AppSource.
