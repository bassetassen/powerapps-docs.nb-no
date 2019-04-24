---
title: Legg til og konfigurer en lerretsappkontroll | Microsoft Docs
description: Trinnvise instruksjoner for å legge til og konfigurere lerretsappkontroller direkte, fra verktøylinjen, i Egenskaper-fanen eller på formellinjen.
author: AFTOwen
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 01/25/2019
ms.author: anneta
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 798a355e1c8728b41f3e92f183d4a4e2831b7cc2
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/23/2019
ms.locfileid: "61530575"
---
# <a name="add-and-configure-a-canvas-app-control-in-powerapps"></a>Legg og konfigurer en lerretsappkontroll i PowerApps

Legg til forskjellige grensesnittelementer i lerretsappen, og konfigurer aspekter ved utseendet og virkemåten deres direkte, fra verktøylinjen, på **Egenskaper**-fanen eller på formellinjen. Disse grensesnittelementene kalles kontroller, og aspektene du konfigurerer, kalles egenskaper.

## <a name="prerequisites"></a>Forutsetninger

1. Hvis du ikke allerede har en PowerApps-lisens, [Registrer](../signup-for-powerapps.md), og deretter [Logg](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc).
1. Under **gjøre din egen app**, holder du pekeren over **lerretsapp fra tom**, og velg deretter **lag denne appen**.
1. Hvis du blir bedt om å følge omvisningen, velger du **neste** å bli kjent med nøkkelområder i PowerApps-grensesnittet (eller velg **Hopp over**).

    Du kan alltid se innføringen senere ved å velge spørsmålstegn-ikonet nær hjørnet øverst til høyre på skjermen, og deretter velge **kan du følge omvisningen**.

## <a name="add-and-select-a-control"></a>Legge til og velg en kontroll

På den **Sett inn** fanen, utføre noen av disse trinnene:

- Velg **etikett** eller **knappen** legge til en av disse typer kontroller.
- Velg en kategori av kontrollene, og velg deretter kontrolltypen du vil legge til.

Velg for eksempel **ny skjerm**, og velg deretter **tom** å legge til en tom skjerm i appen din. (Skjermer er en type kontroll som kan inneholde andre typer kontroller.)

![Legge til skjerm](./media/add-configure-controls/add-screen.png)

Den nye skjermen heter **skjerm2** og vises i den venstre navigasjonsruten. Denne ruten viser en hierarkisk listen over kontroller i appen din slik at du kan enkelt finne og velge hver kontroll.

![Skjerm2 i listen](./media/add-configure-controls/list-screen2.png)

For å demonstrere hvordan denne listen fungerer, kan du velge **etikett** på den **Sett inn** fanen. Den nye kontrollen vises under **skjerm2** i den hierarkiske listen.

![Skjerm2 i listen](./media/add-configure-controls/add-label.png)

En boks med seks håndtak omgir i skjermbildet etiketten som standard. Denne typen box omgir uansett hvilken kontroll er valgt. Hvis du velger skjermen ved å klikke på i den (men utenfor etiketten), forsvinner boksen fra etiketten. For å velge etiketten på nytt, kan du klikker eller trykker i den, eller du kan klikke eller trykk på **Label2** i den hierarkiske listen over kontroller.

> [!IMPORTANT]
> Du må alltid velger en kontroll før du kan konfigurere den.

## <a name="rename-a-control"></a>Gi nytt navn til en kontroll

I den hierarkiske listen over kontroller, Hold pekeren over kontrollen du vil gi nytt navn, velger du ellipseknappen som vises, og velg deretter **gi nytt navn til**. Du kan deretter skrive inn et navn for unike, lett å huske å gjøre bygger appen enklere.

![Å gi en kontroll et nytt navn](./media/add-configure-controls/rename-control.png)

## <a name="delete-a-control"></a>Slette en kontroll

I den hierarkiske listen over kontroller, Hold pekeren over kontrollen som du vil slette, velger du ellipseknappen som vises, og velg deretter **slette**. Hvis du vil slette en kontroll som ikke er en skjerm, kan du også velge kontrollen på lerretet, og trykk deretter på Slett-tasten.

![Slett kontroll](./media/add-configure-controls/delete-control.png)

## <a name="reorder-screens"></a>Endre rekkefølgen på skjermer

Hold pekeren over en skjerm som du ønsker å flytte opp eller ned, velg ellipseknappen som vises i den hierarkiske listen over kontroller, og velg deretter **Flytt opp** eller **Flytt ned**.

![Endre rekkefølgen på skjermen](./media/add-configure-controls/reorder-screen.png)

> [!NOTE]
> Når du åpner appen, vises vanligvis skjermen på toppen av den hierarkiske listen over kontroller først. Men du kan angi en annen skjerm ved å angi den **[OnStart](controls/control-screen.md)** egenskapen til en formel som inneholder den **[Navigate](functions/function-navigate.md)** funksjonen.

## <a name="move-and-resize-a-control"></a>Flytt og endre størrelsen på en kontroll

Hvis du vil flytte en kontroll, velg den, Hold pekeren over sentrum slik at den fire hoder pilen vises, og deretter dra kontrollen til en annen plassering.

![Flytt kontrollen](./media/add-configure-controls/move-control.png)

Hvis du vil endre størrelsen på en kontroll, velg den, Hold pekeren over et av håndtakene i valgboksen slik at den to hoder pilen vises, og dra.

![Flytt kontrollen](./media/add-configure-controls/resize-control.png)

> [!NOTE]
> Som dette emnet beskriver senere, kan du også flytte og endre størrelsen på en kontroll ved å endre en kombinasjon av dens  **[X](controls/properties-size-location.md)**,  **[Y](controls/properties-size-location.md)**,  **[Høyde](controls/properties-size-location.md)**, og **[bredde](controls/properties-size-location.md)** egenskaper i formellinjen.

## <a name="change-the-text-of-a-label-or-a-button"></a>Endre teksten i en etikett eller en knapp

Velg en etikett eller en knapp, Dobbeltklikk teksten som vises i kontrollen, og skriv deretter inn teksten du vil bruke.

![Endre tekst](./media/add-configure-controls/change-text.png)

> [!NOTE]
> Som dette emnet beskriver senere, kan du også endre denne teksten ved å endre den **[tekst](controls/properties-core.md)** -egenskapen i formellinjen.

## <a name="configure-a-control-from-the-toolbar"></a>Konfigurering av en kontroll fra verktøylinjen

Når du konfigurerer en kontroll fra verktøylinjen, kan du angi et større utvalg alternativer enn du kan ved å konfigurere en kontroll direkte.

Du kan for eksempel velge en etikett, velg den **Hjem** fanen, og deretter endre skrift for teksten i etiketten.

![Endre skrift](./media/add-configure-controls/change-font.png)

## <a name="configure-a-control-from-the-properties-tab"></a>Konfigurering av en kontroll fra Egenskaper-fanen

Ved hjelp av den **Egenskaper** fanen, kan du angi et større utvalg alternativer enn du kan ved å konfigurere en kontroll fra verktøylinjen.

Du kan for eksempel velger en kontroll og deretter vise eller skjule den ved å endre den **Visible** egenskapen.

![Angi synlighet](./media/add-configure-controls/set-visibility.png)

## <a name="configure-a-control-in-the-formula-bar"></a>Konfigurering av en kontroll i formellinjen

I stedet for å konfigurere en kontroll direkte, fra verktøylinjen, eller i den **Egenskaper** fanen, kan du konfigurere en kontroll ved å velge en egenskap i egenskapslisten og deretter angi en verdi i formellinjen. Når du følger denne fremgangsmåten, kan du søke etter en egenskap alfabetisk, og du kan angi flere typer verdier.

Du kan for eksempel velge en etikett, og deretter konfigurere den på følgende måter:

- Flytt den ved å velge **X** eller **Y** i Egenskaper-listen, og deretter angi et annet nummer i formellinjen.

    ![Angi X-egenskap](./media/add-configure-controls/x-property.png)

- Endre størrelsen på den ved å velge **høyde** eller **bredde** i Egenskaper-listen, og deretter angi et annet nummer i formellinjen.

    ![Angi høyde egenskapen](./media/add-configure-controls/height-property.png)

- Endre teksten ved å velge **tekst** i Egenskaper-listen, og deretter angi en hvilken som helst kombinasjon av en litteral streng, et uttrykk eller en formel i formellinjen.

    - En litteral streng er omsluttet av anførselstegn og vises nøyaktig slik du skriver den inn. **"Hello, world"** er en litteral streng.

        ![Angi tekst-egenskapen til en litteral streng](./media/add-configure-controls/literal-string.png)

    - Et uttrykk inneholder ikke en funksjon, og er ofte basert på en egenskap for en annen kontroll. **Screen1.Height** er et uttrykk som viser høyden på **Screen1**.

        ![Angi tekst-egenskapen til et uttrykk](./media/add-configure-controls/expression.png)

    - En formel inneholder én eller flere funksjoner. Den **nå** -funksjonen returnerer gjeldende dato og klokkeslett i den lokale tidssonen, og den **tekst** funksjonen formaterer verdier som datoer, klokkeslett og valuta.

        ![Angitt Text-egenskapen til en formel](./media/add-configure-controls/formula.png)

        Formler er vanligvis mye mer komplisert enn dette eksemplet slik at de kan oppdatere data, sortere, filtrere den og utføre andre operasjoner. Hvis du vil ha mer informasjon, kan du se den [formelreferanse](formula-reference.md).

## <a name="next-steps"></a>Neste trinn

- Du finner trinnvise fremgangsmåten for konfigurering av vanlige kontroller som [skjermer](add-screen-context-variables.md), [viser](add-list-box-drop-down-list-radio-button.md), [gallerier](add-gallery.md), [skjemaer](add-form.md), og [diagrammer](use-line-pie-bar-chart.md).
- Finn informasjon om hver type kontroll på den [kontroll referanse](reference-properties.md).
