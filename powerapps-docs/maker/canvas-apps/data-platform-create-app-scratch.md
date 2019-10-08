---
title: Opprett en lerretsapp fra grunnen av ved hjelp av Common Data Service | Microsoft Docs
description: Opprett en lerretsapp i PowerApps for å legge til, oppdatere og slette poster i Common Data Service.
author: tapanm-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 05/21/2019
ms.author: tapanm
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: c058e5f5710c090c39c2971974d57aacd40923a8
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/07/2019
ms.locfileid: "71986011"
ms.PowerAppsDecimalTransform: true
---
# <a name="create-a-canvas-app-from-scratch-using-common-data-service"></a>Opprett en lerretsapp fra grunnen av ved hjelp av Common Data Service

Bygg en lerretsapp for å behandle data som er lagret i Common Data Service, ved hjelp av standardenheter (som er innebygd), egendefinerte enheter (som organisasjonen oppretter) eller begge deler.

Når du bygger en app fra Common Data Service, trenger du ikke å opprette en tilkobling fra PowerApps, slik du gjør med datakilder som SharePoint, Dynamics 365 eller Salesforce. Du trenger bare å angi hvilke enheter du vil vise eller administrere i appen.

## <a name="prerequisites"></a>Forutsetninger

- Før du oppretter appen fra grunnen av, må du gjøre deg selv kjent med det grunnleggende om PowerApps ved å [generere en app](data-platform-create-app.md), og deretter egendefinere appens [galleri](customize-layout-sharepoint.md), [skjemaer](customize-forms-sharepoint.md) og [kort](customize-card.md).
- [Bytt til et miljø](working-with-environments.md) der databasen ble opprettet med eksempeldata. Hvis du har en gyldig lisense, kan du [opprette et miljø](../../administrator/create-environment.md) for å oppfylle dette behovet.
- Hvis du vil opprette en app, må du være tilordnet sikkerhetsrollen [Miljøoppretter](https://docs.microsoft.com/power-platform/admin/database-security#predefined-security-roles).

## <a name="open-a-blank-app"></a>Å åpne en tom app

1. Logg deg på [PowerApps](http://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc).

1. Under **Lag din egen app** velger du **Lerretsapp fra tom**.

    ![Flisen for tom app](./media/data-platform-create-app-scratch/blank-app.png)

1. Angi et navn for appen, velg **Telefon**, og velg deretter **Opprett**.

    Du kan bygge en app fra grunnen av for nettbrett, men dette emnet viser bygging av en app for telefoner.

## <a name="specify-an-entity"></a>Å angi en enhet

1. Midt på skjermen kan du velge **koble til data**.

1. Velg **Common Data Service** i **Data**-ruten, merk av for **Kontoer**, og velg deretter **Koble til**.

1. Lukk **Data**-ruten ved å velge Lukk-ikonet øverst til høyre.

## <a name="add-a-list-screen"></a>Slik legger du til en listeskjerm

1. Velg nedoverpilen ved siden av **Ny skjerm** på **Hjem**-fanen, og velg deretter **Liste**.

    ![Slik legger du til en listeskjerm](./media/data-platform-create-app-scratch/list-screen.png)

1. Velg **BrowseGallery1** i venstre navigasjonsrute, og angi deretter verdien for **Elementer**-egenskapen til denne formelen:

    `SortByColumns(Search(Accounts; TextSearchBox1.Text; "name"); "name"; If(SortDescending1; SortOrder.Descending; SortOrder.Ascending))`

    Denne formelen angir at:

   - Galleriet skal vise data fra **Kontoer**-enheten.
   - Dataene skal sorteres i stigende rekkefølge, inntil en bruker velger sorteringsknappen for å veksle sorteringsrekkefølgen.
   - Hvis en bruker skriver eller limer inn ett eller flere tegn i søkefeltet (**TextSearchBox1**), viser listen bare de kontoene der **Navn**-feltet inneholder tegnene som brukeren oppga.

     Du kan bruke [disse og mange andre funksjoner](formula-reference.md) for å angi hvordan appen vises og virker.

     ![Slik angir du galleriets Element-egenskap](./media/data-platform-create-app-scratch/gallery-items.png)

1. Angi at galleriets oppsett skal vises bare navnet på hver konto, og konfigurer tittellinjen til å vise ordet **Bla gjennom**, som [Tilpassing av galleri](customize-layout-sharepoint.md) beskriver.

    ![Bla gjennom-skjerm](./media/data-platform-create-app-scratch/final-browse.png)

1. Hold pekeren over**Skjerm1** i venstre navigasjonsfelt, velg ellipseikonet (...), og velg deretter **Slett**.

1. Hold pekeren over**Skjerm2** i venstre navigasjonsfelt, velg ellipseikonet (...), og velg deretter **Gi nytt navn**.

1. Skriv eller lim inn **BrowseScreen**, og gi deretter galleriet på den skjermen et nytt navn til **BrowseGallery**.

    ![Å gi Bla gjennom-skjermen et nytt navn, galleri](./media/data-platform-create-app-scratch/rename-browse.png)

## <a name="add-a-form-screen"></a>Skjermen Legg til et skjema

1. Gjenta første trinn i den forrige prosedyren, men legg til en **Skjema**-skjerm i stedet for en **Liste**-skjerm.

1. Angi skjemaets **DataSource**-egenskap til **Kontoer** og **Elementer**-egenskapen til **BrowseGallery.Selected**, som vist i **Avansert**-fanen i ruten til høyre.

    ![Å angi skjemaets Datakilde- og Element-egenskap](./media/data-platform-create-app-scratch/form-datasource.png)

1. På **Egenskaper** -fanen i ruten til høyre velger du **Rediger felt** for å åpne **felt** -ruten.

1. Velg **Legg til felt**, og merk deretter av for disse feltene:

    - **Kontonavn**
    - **Adresse 1: Gateadresse 1**
    - **Adresse 1: Poststed**
    - **Adresse 1: Postnummer**
    - **Antall ansatte**
    - **Årlig omsetning**

    > [!NOTE]
    > Utenfor dette scenarioet kan du opprette et egen definert felt ved å velge **nytt felt**, gi den nødvendige informasjonen, og deretter velge **ferdig**. Mer informasjon: [Opprett et felt](../common-data-service/create-edit-field-portal.md#create-a-field).<br><br>![](media/data-platform-create-app-scratch/choose-or-add-fields.png "Velg og Legg til et felt")

1. Velg **Legg til**.

1. Angi tittellinjens **Tekst**-egenskap til å vise **Opprett/rediger**.

    Skjermbildet gjenspeiler endringen.

    ![Å angi skjemaets Datakilde- og Element-egenskap](./media/data-platform-create-app-scratch/field-list.png)

1. Endre navnet på denne skjermen til **FormScreen**.

## <a name="configure-icons"></a>Konfigurering av porter

1. På **BrowseScreen** angir du **OnSelect**-egenskapen for sirkelikonet nær toppen av skjermen til denne formelen:

    `Refresh(Accounts)`

    ![Oppdater-ikon](./media/data-platform-create-app-scratch/refresh-icon.png)

1. Angi **OnSelect**-egenskapen for plussikonet til denne formelen:

    `NewForm(EditForm1);; Navigate(FormScreen; ScreenTransition.None)`

    ![Legg til-ikon](./media/data-platform-create-app-scratch/plus-icon.png)

1. Angi **OnSelect**-egenskapen for den første pilen som peker til høyre, til denne formelen:

    `EditForm(EditForm1);; Navigate(FormScreen; ScreenTransition.None)`

    ![Neste-ikon](./media/data-platform-create-app-scratch/next-icon.png)

1. På **FormScreen** angir du **OnSelect**-egenskapen for det valgte ikonet til denne formelen:

    `ResetForm(EditForm1);;Navigate(BrowseScreen; ScreenTransition.None)`

    ![Avbryt-ikon](./media/data-platform-create-app-scratch/cancel-icon.png)

1. Angi **OnSelect**-egenskapen for avmerkingsikonet til denne formelen:

    `SubmitForm(EditForm1);; Navigate(BrowseScreen; ScreenTransition.None)`

    ![Avmerking-ikon](./media/data-platform-create-app-scratch/checkmark-icon.png)

1. Velg **Ikoner** på **Sett inn**-fanen, og deretter velger du **Papirkurv**-ikonet.

1. Angi **Papirkurv**-ikonets **Farge**-egenskap til **Hvit** og **OnSelect**-egenskap til denne formelen:

    `Remove(Accounts; BrowseGallery.Selected);; Navigate(BrowseScreen; ScreenTransition.None)`

    ![Papirkurv-ikon](./media/data-platform-create-app-scratch/trash-icon.png)

## <a name="test-the-app"></a>Testing av appen

1. Velg **BrowseScreen** i venstre navigasjonsrute, og åpne deretter Forhåndsvisning ved å trykke på F5 (eller ved å velge avspillingsikonet nær øvre høyre hjørne).

    ![Å åpne Forhåndsvisning](./media/data-platform-create-app-scratch/open-preview.png)

1. Veksle listen mellom stigende og synkende sorteringsrekkefølger, og filtrer listen etter bestemte tegn i hvert kontonavn.

1. Legg til en konto, rediger kontoen du la til, begynn å oppdater kontoen men avbryt endringene, og slett deretter kontoen.

## <a name="next-steps"></a>Neste trinn

- [Koble denne appen til en løsning](add-app-solution.md), slik at du for eksempel kan distribuere den til et annet miljø eller publisere den på AppSource.
- [Åpne én eller flere eksempelapper](open-and-run-a-sample-app.md), og utforsk forskjellige typer apper du kan opprette.
