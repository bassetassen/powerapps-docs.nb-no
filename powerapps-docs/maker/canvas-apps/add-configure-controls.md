---
title: Legg til og konfigurer en lerretsappkontroll | Microsoft Docs
description: Trinnvise instruksjoner for å legge til og konfigurere lerretsappkontroller direkte, fra verktøylinjen, i Egenskaper-fanen eller på formellinjen.
author: tapanm-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 01/25/2019
ms.author: tapanm
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 9d16e4c7b8d15611b06644520c0ee39417fd3ee0
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/07/2019
ms.locfileid: "71994696"
---
# <a name="add-and-configure-a-canvas-app-control-in-powerapps"></a>Legg og konfigurer en lerretsappkontroll i PowerApps

Legg til forskjellige grensesnittelementer i lerretsappen, og konfigurer aspekter ved utseendet og virkemåten deres direkte, fra verktøylinjen, på **Egenskaper**-fanen eller på formellinjen. Disse grensesnittelementene kalles kontroller, og aspektene du konfigurerer, kalles egenskaper.

## <a name="prerequisites"></a>Forutsetninger

1. Hvis du ikke allerede har en PowerApps-lisens, kan du [registrere](../signup-for-powerapps.md)deg og [logge deg på](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc).
1. Under **Lag din egen app**, holder du pekeren over en **lerrets app fra Tom**, og deretter velger du **gjør denne appen**.
1. Hvis du blir bedt om å ta med innføringen, velger du **neste** for å bli kjent med nøkkel områder i powerapps-grensesnittet (eller velg **Hopp over**).

    Du kan alltid ta omvisningen senere ved å velge spørsmåls tegnet nær hjørnet øverst til høyre på skjermen, og deretter velge **ta den innføringen**.

## <a name="add-and-select-a-control"></a>Legg til og velg en kontroll

På **Sett inn** -fanen utfører du ett av disse trinnene:

- Velg **etikett** eller **knapp** for å legge til én av disse kontroll typene.
- Velg en kategori med kontroller, og velg deretter kontroll typen du vil legge til.

Velg for eksempel **ny skjerm**, og velg deretter **tom** for å legge til en tom skjerm i appen. (Skjermer er en type kontroll som kan inneholde andre typer kontroller.)

![Legg til skjerm](./media/add-configure-controls/add-screen.png)

Den nye skjermen heter **Screen2** og vises i navigasjons ruten til venstre. Denne ruten viser en hierarkisk liste over kontroller i appen, slik at du enkelt kan finne og velge hver kontroll.

![Screen2 i listen](./media/add-configure-controls/list-screen2.png)

Hvis du vil vise hvordan denne listen fungerer, velger du **etikett** på **Sett inn** -fanen. Den nye kontrollen vises under **Screen2** i den hierarkiske listen.

![Screen2 i listen](./media/add-configure-controls/add-label.png)

På skjermen omgir en boks med seks håndtak etiketten som standard. Denne typen boks omslutter av kontrollen som er valgt. Hvis du velger skjermen ved å klikke eller trykke på den (men utenfor etiketten), forsvinner boksen fra etiketten. Hvis du vil velge etiketten på nytt, kan du klikke eller trykke på den, eller du kan klikke eller trykke på navnet i den hierarkiske listen over kontroller.

> [!IMPORTANT]
> Du må alltid velge en kontroll før du kan konfigurere den.

## <a name="rename-a-control"></a>Gi nytt navn til en kontroll

Beveg pekeren over kontrollen du vil gi nytt navn, i den hierarkiske listen over kontroller, Velg ellipse-knappen som vises, og velg deretter **gi nytt navn**. Deretter kan du skrive inn et unikt navn for å gjøre det enklere å utvikle appen.

![Å gi en kontroll et nytt navn](./media/add-configure-controls/rename-control.png)

## <a name="delete-a-control"></a>Slette en kontroll

Beveg pekeren over kontrollen du vil slette, i den hierarkiske listen over kontroller, Velg ellipse-knappen som vises, og velg deretter **Slett**. Hvis du vil slette en kontroll som ikke er en skjerm, kan du også velge kontrollen på lerretet, og deretter trykke på Slett-tasten.

![Slett kontroll](./media/add-configure-controls/delete-control.png)

## <a name="reorder-screens"></a>Endre rekkefølgen på skjermer

Beveg pekeren over et skjerm bilde som du vil flytte opp eller ned i den hierarkiske listen over kontroller, Velg den uttrykks knappen som vises, og velg deretter **Flytt opp** eller **Flytt ned**.

![Ordne skjerm bilde](./media/add-configure-controls/reorder-screen.png)

> [!NOTE]
> Når appen åpnes, vises skjerm bildet øverst i den hierarkiske listen over kontroller vanligvis først. Du kan imidlertid angi en annen skjerm ved å angi **[OnStart](controls/control-screen.md)** -egenskapen til en formel som inkluderer **[Naviger](functions/function-navigate.md)** -funksjonen.

## <a name="move-and-resize-a-control"></a>Flytt og endre størrelse på en kontroll

Hvis du vil flytte en kontroll, merker du den, holder pekeren over sentrum, slik at den firehodede pilen vises, og deretter drar du kontrollen til en annen plassering.

![Flytt kontroll](./media/add-configure-controls/move-control.png)

Hvis du vil endre størrelsen på en kontroll, merker du den, holder pekeren over et håndtak i valg boksen slik at den tohodede pilen vises, og deretter drar du håndtaket.

![Flytt kontroll](./media/add-configure-controls/resize-control.png)

> [!NOTE]
> Som dette emnet beskriver senere, kan du også flytte og endre størrelsen på en kontroll ved å endre en kombinasjon av egenskapene **[X](controls/properties-size-location.md)** , **[Y](controls/properties-size-location.md)** , **[høyde](controls/properties-size-location.md)** og **[bredde](controls/properties-size-location.md)** på formel linjen.

## <a name="change-the-text-of-a-label-or-a-button"></a>Endre teksten i en etikett eller en knapp

Velg en etikett eller knapp, dobbelt klikk på teksten som vises i kontrollen, og skriv deretter inn teksten du vil bruke.

![Endre tekst](./media/add-configure-controls/change-text.png)

> [!NOTE]
> Som dette emnet beskriver senere, kan du også endre denne teksten ved å endre **[tekst](controls/properties-core.md)** -egenskapen på formel linjen.

## <a name="configure-a-control-from-the-toolbar"></a>Konfigurering av en kontroll fra verktøylinjen

Når du konfigurerer en kontroll fra verktøylinjen, kan du angi et større utvalg alternativer enn du kan ved å konfigurere en kontroll direkte.

Du kan for eksempel velge en etikett, velge **hjem** -fanen, og deretter endre skrift typen i teksten i etiketten.

![Endre skrift](./media/add-configure-controls/change-font.png)

## <a name="configure-a-control-from-the-properties-tab"></a>Konfigurering av en kontroll fra Egenskaper-fanen

Ved å bruke **Egenskaper** -fanen kan du angi flere forskjellige alternativer enn du kan ved å konfigurere en kontroll fra verktøy linjen.

Du kan for eksempel velge en kontroll og deretter vise eller skjule den ved å endre **synlig** -egenskapen.

![Angi synlighet](./media/add-configure-controls/set-visibility.png)

## <a name="configure-a-control-in-the-formula-bar"></a>Konfigurering av en kontroll i formellinjen

I stedet for å konfigurere en kontroll direkte, fra verktøy linjen eller i **Egenskaper** -fanen, kan du konfigurere en kontroll ved å velge en egenskap i egenskaps listen, og deretter angi en verdi på formel linjen. Når du følger denne fremgangsmåten, kan du søke etter en egenskap alfabetisk, og du kan angi flere typer verdier.

Du kan for eksempel velge en etikett og deretter konfigurere den på følgende måter:

- Flytt den ved å velge **X** eller **Y** i egenskaps listen, og angi deretter et annet tall i formel linjen.

    ![Angi X-egenskap](./media/add-configure-controls/x-property.png)

- Endre størrelsen ved å velge **høyde** eller **bredde** i egenskaps listen, og angi deretter et annet tall på formel linjen.

    ![Angi egenskapen Height](./media/add-configure-controls/height-property.png)

- Endre teksten ved å merke **tekst** i egenskaps listen, og angi deretter en kombinasjon av en ordrett streng, et uttrykk eller en formel på formel linjen.

    - En ordrett streng er omgitt av anførsels tegn og vises nøyaktig slik du skriver den inn. **"Hello, World"** er en ordrett streng.

        ![Angi tekst-egenskap til en ordrett streng](./media/add-configure-controls/literal-string.png)

    - Et uttrykk inneholder ikke en funksjon og er ofte basert på en egenskap for en annen kontroll. **Screen1. Height** er et uttrykk som viser høyden på **Screen1**.

        ![Angi tekst-egenskap til et uttrykk](./media/add-configure-controls/expression.png)

    - En formel inneholder én eller flere funksjoner. **Now** -funksjonen returnerer gjeldende dato og klokkeslett i den lokale tids sonen, og **tekst** -funksjonen formaterer verdier som datoer, klokkeslett og valuta.

        ![Angi tekst-egenskap til en formel](./media/add-configure-controls/formula.png)

        Formler er vanligvis mye mer komplekse enn dette eksemplet, slik at de kan oppdatere data, sortere dem, filtrere dem og utføre andre operasjoner. Hvis du vil ha mer informasjon, kan du se [formel referansen](formula-reference.md).

## <a name="next-steps"></a>Neste trinn

- Finn trinn vise prosedyrer for konfigurering av vanlige kontroller, for eksempel [skjermer](add-screen-context-variables.md), [lister](add-list-box-drop-down-list-radio-button.md), [gallerier](add-gallery.md), [skjemaer](add-form.md)og [diagrammer](use-line-pie-bar-chart.md).
- Finn referanse informasjon om hver kontroll type i [kontroll referansen](reference-properties.md).
