---
title: Opprett en lerretsapp fra grunnen av ved hjelp av Common Data Service for apper | Microsoft Docs
description: Opprett en lerretsapp i PowerApps for å legge til, oppdatere og slette poster i Common Data Service for apper.
author: AFTOwen
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 03/18/2018
ms.author: anneta
ms.openlocfilehash: df2ed422cdfbaf8689dae7c8f3e6b54eba093b74
ms.sourcegitcommit: e3f5a2bef64085d02aec82e62ff94ae8a4d01d24
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/02/2018
ms.locfileid: "39471355"
---
# <a name="create-a-canvas-app-from-scratch-using-common-data-service-for-apps"></a>Opprett en lerretsapp fra grunnen av ved hjelp av Common Data Service for apper

Bygg en lerretsapp for å behandle data som er lagret i Common Data Service for apper, ved hjelp av standardenheter (som er innebygd), egendefinerte enheter (som organisasjonen oppretter) eller begge deler.

Når du bygger en app fra Common Data Service, trenger du ikke å opprette en tilkobling fra PowerApps, slik du gjør med datakilder som SharePoint, Dynamics 365 eller Salesforce. Du trenger bare å angi hvilke enheter du vil vise, administrere eller bruke for begge aktivitetene i appen.

## <a name="prerequisites"></a>Forutsetninger

- Før du oppretter appen fra grunnen av, må du gjøre deg selv kjent med det grunnleggende om PowerApps ved å [generere en app](data-platform-create-app.md), og deretter egendefinere appens [galleri](customize-layout-sharepoint.md), [skjemaer](customize-forms-sharepoint.md) og [kort](customize-card.md).
- [Bytt til et miljø](working-with-environments.md) der databasen ble opprettet med eksempeldata. Hvis du har en gyldig lisense, kan du [opprette et miljø](../../administrator/create-environment.md) for å oppfylle dette behovet.

## <a name="open-a-blank-app"></a>Slik åpner man en tom app

1. Logg deg på [PowerApps](http://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc).

    ![Hjemmesiden for PowerApps](./media/data-platform-create-app-scratch/sign-in.png)

1. Hold pekeren over flisen **Start med en tom app** under **Opprett slike apper**, klikk eller trykk på telefonikonet, og klikk eller trykk deretter på **Lag denne appen**.

    ![Flisen for tom app](./media/data-platform-create-app-scratch/blank-app.png)

    Du kan utforme en app fra grunnen av for telefoner og andre enheter (som nettbrett), og dette emnet fokuserer på hvordan du utformer apper for telefoner.

## <a name="specify-an-entity"></a>Å angi en enhet

1. Klikk eller trykk på **koble til data** midt på skjermen, og deretter, i **Data**-ruten, klikker eller trykker du på **Common Data Service**-tilkoblingen.

1. Skriv eller lim inn de første bokstavene til **Kontoer** i søkeboksen for å filtrere listen over enheter, merk av for **Kontoer**, og klikk eller trykk deretter på **Koble til**.

    ![Slik angir Kontoer-enheten](./media/data-platform-create-app-scratch/cds-connect.png)

1. Lukk **Data**-ruten ved å klikke eller trykke på Lukk-ikonet øverst til høyre.

## <a name="add-a-list-screen"></a>Slik legger du til en listeskjerm

1. Klikk eller trykk på Pil ned for **Ny skjerm** på **Hjem**-fanen, og klikk eller trykk deretter på **Listeskjerm**.

    ![Slik legger du til en listeskjerm](./media/data-platform-create-app-scratch/list-screen.png)

1. Klikk eller trykk på **TemplateGalleryList1**i venstre navigasjonsrute for å velge den, og angi deretter verdien for **Elementer**-egenskapen til denne formelen:

    `SortByColumns(Search(Accounts, TextSearchBox1.Text, "name"), "name", If(SortDescending1, SortOrder.Descending, SortOrder.Ascending))`

    Denne formelen angir at:

   - Galleriet skal vise data fra **Kontoer**-enheten.
   - Dataene skal sorteres i stigende rekkefølge før en bruker klikker eller trykker på sorteringsknappen for å veksle sorteringsrekkefølgen.
   - Hvis en bruker skriver eller limer inn ett eller flere tegn i søkefeltet, viser listen bare de kontoene som inneholder tegnene som bruker oppgav.

     Du kan bruke [disse og mange andre funksjoner](formula-reference.md) for å angi hvordan appen vises og virker.

     ![Slik angir du galleriets Element-egenskap](./media/data-platform-create-app-scratch/gallery-items.png)

1. Angi at galleriets oppsett skal vises bare navnet på hver konto, og konfigurer tittellinjen til å vise ordet **Bla gjennom**, som [Tilpassing av galleri](customize-layout-sharepoint.md) beskriver.

    ![Bla gjennom-skjermen](./media/data-platform-create-app-scratch/final-browse.png)

1. Hold pekeren over **Screen1** i det venstre navigasjonsfeltet, klikk eller trykk på ellipsen (...), og klikk eller trykk deretter på **Slett**.

1. Hold pekeren over **Screen2** i det venstre navigasjonsfeltet, klikk eller trykk på ellipsen (...), og klikk eller trykk deretter på **Gi nytt navn**.

1. Skriv eller lim inn **BrowseScreen**, og gi deretter galleriet på den skjermen et nytt navn til **BrowseGallery**.

    ![Å gi Bla gjennom-skjermen et nytt navn, galleri](./media/data-platform-create-app-scratch/rename-browse.png)

## <a name="add-a-form-screen"></a>Skjermen Legg til et skjema

1. Gjenta det første trinnet til den forrige prosedyren, men legger også til en **Skjemaskjerm** i stedet for en **Listeskjerm**.

1. Angi skjemaets **DataSource**-egenskap til **Kontoer** og **Elementer**-egenskap til **BrowseGallery.Selected**, som vist i **Avansert-fanen** i ruten til høyre.

    ![Å angi skjemaets Datakilde- og Element-egenskap](./media/data-platform-create-app-scratch/form-datasource.png)

1. Klikk eller trykk på **Kontoer** på **Egenskaper**-fanen i den høyre ruten for å åpne **Data**-ruten, og merk deretter av for disse feltene:

    - Kontonavn
    - Adresse 1: Gate 1
    - Adresse 1: Poststed
    - Adresse 1: Postnummer
    - Antall ansatte
    - Årlig omsetning

1. Angi tittellinjens **Tekst**-egenskap til å vise **Opprett/rediger**.

    Skjermbildet gjenspeiler endringen.

    ![Å angi skjemaets Datakilde- og Element-egenskap](./media/data-platform-create-app-scratch/field-list.png)

1. Endre navnet på denne skjermen til **FormScreen**.

## <a name="configure-icons"></a>Konfigurering av porter

1. Klikk eller trykk på sirkelikonet nær toppen av skjermen på **BrowseScreen**, og angi **OnSelect**-egenskapen til denne formelen:

    `Refresh(Accounts)`

    ![Oppdater-ikon](./media/data-platform-create-app-scratch/refresh-icon.png)

1. Klikk eller trykk på plussikonet, og angi **OnSelect**-egenskapen til denne formelen:

    `NewForm(EditForm1); Navigate(FormScreen, ScreenTransition.None)`

    ![Legg til-ikon](./media/data-platform-create-app-scratch/plus-icon.png)

1. Klikk eller trykk på den første pilen som peker mot høyre, og angi **OnSelect**-egenskapen til denne formelen:

    `EditForm(EditForm1); Navigate(FormScreen, ScreenTransition.None)`

    ![Neste-ikon](./media/data-platform-create-app-scratch/next-icon.png)

1. Klikk eller trykk på Avbryt-ikonet på **FormScreen**, og angi **OnSelect**-egenskapen til denne formelen:

    `ResetForm(EditForm1);Navigate(BrowseScreen, ScreenTransition.None)`

    ![Avbryt-ikon](./media/data-platform-create-app-scratch/cancel-icon.png)

1. Klikk eller trykk på Avmerking-ikonet, og angi **OnSelect**-egenskapen til denne formelen:

    `SubmitForm(EditForm1); Navigate(BrowseScreen, ScreenTransition.None)`

    ![Avmerking-ikon](./media/data-platform-create-app-scratch/checkmark-icon.png)

1. Klikk eller trykk på **Ikoner** på **Sett inn**-fanen, og klikk eller trykk deretter på **Papirkurv**-ikonet.

1. Angi **Papirkurv**-ikonets **Farge**-egenskap til **Hvit** og **OnSelect**-egenskap til denne formelen:

    `Remove(Accounts, BrowseGallery.Selected); Navigate(BrowseScreen, ScreenTransition.None)`

    ![Papirkurv-ikon](./media/data-platform-create-app-scratch/trash-icon.png)

## <a name="test-the-app"></a>Test appen

1. Velg **BrowseScreen** i den venstre navigeringsruten, og åpne deretter forhåndsvisningsmodus ved å trykke på F5 (eller ved å klikke på avspillingsikonet nær hjørnet øverst til høyre).

    ![Å åpne Forhåndsvisning](./media/data-platform-create-app-scratch/open-preview.png)

1. Veksle listen mellom stigende og synkende sorteringsrekkefølger, og filtrer listen etter bestemte tegn i hvert kontonavn.

1. Legg til en konto, rediger kontoen du la til, begynn å oppdater kontoen men avbryt endringene, og slett deretter kontoen.

## <a name="next-steps"></a>Neste trinn

[Åpne én eller flere eksempelapper](open-and-run-a-sample-app.md), og utforsk forskjellige typer apper du kan opprette.