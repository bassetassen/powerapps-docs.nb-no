---
title: Legg til og konfigurer en lerretsappkontroll | Microsoft Docs
description: Trinnvise instruksjoner for å legge til og konfigurere lerretsappkontroller direkte, fra verktøylinjen, i Egenskaper-fanen eller på formellinjen.
author: AFTOwen
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 07/10/2017
ms.author: anneta
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 03f768124b2b7260995fe89120091e85e4cdaa0d
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/24/2018
ms.locfileid: "42826499"
---
# <a name="add-and-configure-a-canvas-app-control-in-powerapps"></a>Legg og konfigurer en lerretsappkontroll i PowerApps

Legg til forskjellige grensesnittelementer i lerretsappen, og konfigurer aspekter ved utseendet og virkemåten deres direkte, fra verktøylinjen, på **Egenskaper**-fanen eller på formellinjen. Disse grensesnittelementene kalles kontroller, og aspektene du konfigurerer, kalles egenskaper.

## <a name="prerequisites"></a>Forutsetninger

1. [Registrer deg](../signup-for-powerapps.md) for PowerApps, og deretter [logger du deg på](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) ved å angi samme legitimasjon som du brukte til å registrere deg.

2. Klikk eller trykk på **Ny** i **Fil**-menyen (nær venstre kant) i PowerApps Studio.

    ![Ny-alternativet i Fil-menyen](./media/add-configure-controls/file-new.png)

3. Klikk eller trykk på **Telefonoppsett** på **Tom app**-flisen.

    ![Å opprette en app fra grunnen av](./media/add-configure-controls/blank-app.png)

4. Hvis du blir bedt om å følge omvisningen, kan du klikke eller trykke på **Neste** for å bli kjent med nøkkelområder i PowerApps-grensesnittet (eller klikke eller trykke på **Hopp over**).

    ![Åpningsskjermen i omvisningen](./media/add-configure-controls/quick-tour.png)

    Du kan følge omvisningen når som helst ved å klikke eller trykke på spørsmålstegn-ikonet nær hjørnet øverst til høyre og deretter klikke eller trykke på **Følg omvisningen**.

## <a name="add-a-control"></a>Å legge til en kontroll
Du kan legge til en hvilken som helst kontroll i forskjellige kategorier, ved å klikke eller trykke på **Sett inn**-fanen til verktøylinjen, klikke eller trykke på en kategori og deretter klikke eller trykke på kontrollen du vil bruke. I denne delen kan du se gjennom kontrollene i hver kategori for å bli kjent med de ulike kontrolltypene du kan legge til og finne ut hvor du kan finne dem.

Klikk eller trykk på hvilken som helst av disse kategoriene på **Sett inn**-fanen, og deretter klikker eller trykker du på kontrollen du vil legge til:

**Tekst**: Etikett, Tekstinndata HTML-tekst, Penneinndata<br>
**Kontroller**: Knapp, Rullegardin, Datovelger, Listeboks, Avmerkingsboks, Alternativknapp, Veksle, Glidebryter, Vurdering, Tidtaker<br>
**Galleri**: Loddrett, Vannrett, Fleksibel høyde, Tom loddrett, Tom vannrett, Tom fleksibel høyde<br>
**Datatabell**<br>
**Skjemaer**: rediger, vis, enhetsskjema<br>
**Media**: Bilde, Kamera, Strekkode, Video, Lyd, Mikrofon, Legg til bilde<br>
**Diagrammer**: Stolpediagram, Linjediagram, Sektordiagram<br>
**Ikoner**

> [!TIP]
> Hvis du trenger mer plass til kontroller, kan du [legge til en annen skjerm](add-screen-context-variables.md).

## <a name="configure-a-control-directly"></a>Å konfigurere en kontroll direkte
I denne prosedyren legger du til og konfigurerer en **Etikett**-kontroll, men du kan bruke mange av de samme prinsippene på andre kontroller.

1. Klikk eller trykk på **Sett inn**-fanen, og deretter klikker eller trykker du på **Etikett**.

    ![Sett inn-fanen](./media/add-configure-controls/insert-text-box.png)

    Når du legger til en kontroll, velges den som standard. Du kan også velge en eksisterende kontroll ved å klikke eller trykke på den. Når en kontroll er valgt, omgis den av en valgboks og andre deler av grensesnittet endres, slik at du kan konfigurere den valgte kontrollen. En valgt **Etikett**-kontroll ligner for eksempel på denne grafikken.

    ![En valgt etikett](./media/add-configure-controls/selected-text-box.png)

    > [!IMPORTANT]
   > Hvis en kontroll er valgt når du velger en ny kontroll eller et tomt område på skjermen, er ikke det første elementet lenger valgt.
2. Gjør **Etikett**-kontrollen smalere ved å dra i et håndtak på høyre kant av valgboksen til venstre. (Det midterste håndtaket vises bare hvis du zoomer inn.)

    ![En etikett med endret størrelse](./media/add-configure-controls/shorter-text-box.png)

     Du kan også endre størrelsen på en kontroll ved å endre egenskapene **[Høyde](controls/properties-size-location.md)**, **[Bredde](controls/properties-size-location.md)** eller begge, slik dette emnet beskriver senere.

3. Flytt **Etikett**-kontrollen ved å dra selve valgboksen (eller ved å endre **[X](controls/properties-size-location.md)**, **[Y](controls/properties-size-location.md)** eller begge egenskapene, slik dette emnet beskriver senere).

4. Trippelklikk på teksten som vises i **Etikett**-kontrollen, og skriv deretter inn **Hei, verden**.

    ![En etikett med egendefinert tekst](./media/add-configure-controls/change-text-directly.png)

     Du kan også endre denne teksten ved å angi **[Tekst](controls/properties-core.md)**-egenskapen for denne kontrollen, slik dette emnet beskriver senere.

## <a name="configure-a-control-from-the-toolbar"></a>Konfigurering av en kontroll fra verktøylinjen
Når du konfigurerer en kontroll fra verktøylinjen, kan du angi et større utvalg alternativer enn du kan ved å konfigurere en kontroll direkte.

1. Når du har valgt **Etikett**-kontrollen, klikker eller trykker du på **Hjem**-fanen på verktøylinjen.

    ![Hjem-fanen](./media/add-configure-controls/home-tab.png)

2. Klikk eller trykk på **Fyll**, og deretter klikker eller trykker du på en farge, for eksempel akvamarin.

    ![Fyll-alternativet](./media/add-configure-controls/fill-option.png)

    **Etikett**-kontrollen reflekterer valget.

    ![En etikett med akvamarin-fyll](./media/add-configure-controls/change-fill.png)

3. Endre skriftserien og størrelsen på teksten (for eksempel til 18 pkt. Georgia).

    ![Skrift-kontroller](./media/add-configure-controls/font-size.png)

    **Etikett**-kontrollen reflekterer valget.

    ![18-punkts Georgia](./media/add-configure-controls/change-font.png)

4. Klikk eller trykk på **Etikett**-fanen, klikk eller trykk på **VerticalAlign**, og klikk eller trykk deretter på **Øverst**.

    ![Tekstboks-fanen](./media/add-configure-controls/text-box-tab.png)

    **Etikett**-kontrollen reflekterer valget.

    ![En etikett med teksten justert i forhold til toppen av boksen](./media/add-configure-controls/change-align.png)

## <a name="configure-a-control-from-the-properties-tab"></a>Konfigurering av en kontroll fra Egenskaper-fanen
Når du bruker **Egenskaper**-fanen, kan du konfigurere en kontroll uten å skrive en formel. I denne prosedyren legger du til og konfigurerer en ny **Etikett**-kontroll, men du kan bruke mange av de samme prinsippene på andre kontroller.

1. Legg til en ny **Etikett**-kontroll, som beskrevet tidligere i dette emnet.

2. Når du har valgt den nye kontrollen, klikker eller trykker du på **Egenskaper**-fanen i den høyre ruten.

    ![Egenskaper-panelet](./media/add-configure-controls/properties-panel.png)

3. Skriv inn **Egenskaper-fane** i **Tekst**-boksen.

    ![Etikettekst for Egenskaper-panelet](./media/add-configure-controls/properties-panel-text.png)

    **Etikett**-kontrollen viser den angitte teksten.

    ![Lerrettekst for Egenskaper-panelet](./media/add-configure-controls/properties-panel-canvas-text.png)

4. Klikk eller trykk på **Fyll**-ikonet i **Egenskaper**-ruten, og klikk eller trykk deretter på en farge.

    ![Fargetekst for Egenskaper-panelet](./media/add-configure-controls/properties-panel-color.png)

    **Etikett**-kontrollen reflekterer valget.

    ![Lerretfarge for Egenskaper-panelet](./media/add-configure-controls/properties-panel-canvas-color.png)

5. Klikk eller trykk på **Farge**-egenskapen i Egenskaper-panelet.

    ![Egenskap for Egenskaper-panelet](./media/add-configure-controls/properties-panel-property.png)

    Verdien for **Farge**-egenskapen utheves i formellinjen.

    ![Egenskapsuttrykk for Egenskaper-panelet](./media/add-configure-controls/properties-panel-property-expression.png)

6. Slett den andre **Etikett**-kontrollen ved å klikke eller trykke på den og deretter trykke på Slett.

## <a name="configure-a-control-in-the-formula-bar"></a>Konfigurering av en kontroll i formellinjen
Når du bruker formellinjen, kan du angi egenskaper du ikke kan angi direkte i **Egenskaper**-fanen eller fra verktøylinjen. Du kan for eksempel angi et verktøytips som vises når en bruker peker på kontrollen uten å klikke eller trykke på den. Du kan også angi kompliserte formler som gjør appen mer kraftfull.

Hver endring du har gjort tidligere i dette emnet, har oppdatert verdien for en [egenskap](reference-properties.md) for kontrollen du har konfigurert.

* Når du endret størrelsen på kontrollen, endret du også **[Bredde](controls/properties-size-location.md)**-egenskapen.
* Når du flyttet kontrollen, endret du egenskapene **[X](controls/properties-size-location.md)** og **[Y](controls/properties-size-location.md)**.
* Når du endret teksten kontrollen viser, endret du **[Tekst](controls/properties-core.md)**-egenskapen.

I stedet for å konfigurere en kontroll direkte, i **Egenskaper**-fanen eller fra verktøylinjen, kan du også oppdatere verdien for en egenskap ved å velge den i egenskapslisten og deretter angi en verdi i formellinjen. Når du følger denne fremgangsmåten, kan du søke etter en egenskap alfabetisk, og du kan angi flere typer verdier.

1. Når den gjenværende **Etikett**-kontrollen er valgt, klikker eller trykker du på **[Tekst](controls/properties-core.md)** i egenskapslisten, og skriver deretter inn **«Mitt firmanavn»** (i anførselstegn) i formellinjen.

    ![En litteral streng i en etikett](./media/add-configure-controls/text-literal.png)

    Når du omgir en tekststreng med anførselstegn, angir du at den skal behandles nøyaktig slik du skrev den inn. Et annet alternativ er å angi verdien for en egenskap til en formel.

2. Når **Etikett**-kontrollen er valgt, klikker eller trykker du på **[Tekst](controls/properties-core.md)** i egenskapslisten, og skriver deretter inn **I dag()** (uten anførselstegn) i formellinjen.

    Kontrollen viser gjeldende dato.

    ![I dag-funksjonen](./media/add-configure-controls/today-function.png)

    > [!TIP]
   > Du kan [formatere datoer og klokkeslett](show-text-dates-times.md) på forskjellige måter, i tillegg til å utføre beregninger på dem.

## <a name="configure-two-controls-to-interact-with-each-other"></a>Konfigurering av to kontroller så de kan samhandle med hverandre
I denne prosedyren må du legge til en avmerkingsboks og deretter konfigurere etiketten du allerede har, så den vises bare når avmerkingsboksen er merket.

1. Klikk eller trykk på **Sett inn**-fanen.

    ![Sett inn-fanen](./media/add-configure-controls/insert-tab.png)

2. Klikk eller trykk på **Kontroller**, og trykk deretter på **Avmerkingsboks**.

    ![Å sette inn avmerkingsboks](./media/add-configure-controls/insert-check-box.png)

3. Flytt **Avmerkingsboks**-kontrollen, slik at den vises under **Etikett**-kontrollen, og angi **[Tekst](controls/properties-core.md)**-egenskapen for **Avmerkingsboks**-kontrollen, slik at **Vis tekst** vises.

    ![Å konfigurere avmerkingsboksen](./media/add-configure-controls/configure-check-box.png)

4. Mens **Avmerkingsboks**-kontrollen fremdeles er valgt, klikker eller trykker du på navnet rett over **Egenskaper**-fanen, og skriver deretter inn **MyCheckbox**

    ![Å gi nytt navn til avmerkingsboksen](./media/add-configure-controls/properties-panel-rename.png)

5. Klikk eller trykk på **Etikett**-kontrollen for å velge den.

6. Klikk eller trykk på **Synlig**-egenskapen på **Egenskaper**-fanen.

    ![Synlig-egenskapen](./media/add-configure-controls/properties-panel-visible-property.png)

7. Slett **sann** i formellinjen, og skriv eller lim deretter inn denne formelen:

    **If(MyCheckbox.Value = true, true, false)**

    Denne **[If-funksjonen](functions/function-if.md)** sier at etiketten skal vises bare når avmerkingsboksen er merket. Siden merket er fjernet i avmerkingsboksen, forsvinner **Etikett**-kontrollen (unntatt for valgboksen).

    ![Synlig-formelen](./media/add-configure-controls/visible-formula.png)

8. Klikk eller trykk på **Avmerkingsboks**-kontrollen for å legge til valgboksen, og deretter klikker eller trykker du på den igjen for å legge til et merke.

    **Etikett** vises på nytt:

    ![Etiketten vises når avmerkingsboksen er merket](./media/add-configure-controls/show-text.png)

9. Fjern merket i **Avmerkingsboks**-kontrollen for å skjule **Etikett**-kontrollen.

    ![Etiketten forsvinner når merket i avmerkingsboksen er fjernet](./media/add-configure-controls/hide-text.png)

Dette eksemplet er grunnleggende, men du kan konfigurere virkemåten og visningen for appen ved å utvikle én eller flere [formler](formula-reference.md), fra enkle til avanserte.

## <a name="rename-a-screen-or-a-control"></a>Å gi nytt navn til en skjerm eller kontroll
Hvis du gir nytt navn til en skjerm eller kontroll, kan du utvikle formler som er enklere å lese og vedlikeholde.

1. Klikk eller trykk på skjermen eller kontrollen du vil gi et nytt navn til.

2. Klikk eller trykk på navnet til kontrollen (rett over **Egenskaper**-fanen) i høyre rute, og skriv deretter inn navnet du vil bruke.

    ![Å gi nytt navn til avmerkingsboksen](./media/add-configure-controls/properties-panel-rename.png)

## <a name="find-and-select-a-screen-or-a-control"></a>Å finne og velge en skjerm eller kontroll
Du kan finne og velge en skjerm eller kontroll, selv om den er skjult eller overlapper med en annen kontroll, ved å søke etter den i den venstre ruten. Denne ruten viser enten et miniatyrbilde av hver skjerm i appen, eller en hierarkisk visning av hver skjerm og kontrollene den inneholder.

* Klikk eller trykk på et ikon i øvre høyre hjørne av ruten for å **bytte mellom miniatyrbilder og hierarkisk visning**.

    ![Å veksle mellom visninger](./media/add-configure-controls/toggle-view.png)

* Skriv inn ett eller flere tegn for å utheve kontrollnavnene som inneholder teksten du skrev inn for **å finne en kontroll**.

    Hvis du klikker eller trykker på et søkeresultat, kan du velge kontrollen i appen.

    ![Å søke i trevisning](./media/add-configure-controls/search.png)

* Hvis du vil **flytte en skjerm opp eller ned, duplisere den, slette den eller gi den et nytt navn**, høyreklikker du på skjermen (eller klikker eller trykker på ellipsen ved siden av den), og deretter klikker eller trykker du på alternativet du vil ha.

    ![Kontekstmeny for trevisning](./media/add-configure-controls/context.png)

* Hvis du vil **kopiere eller lime inn en kontroll, slette den eller gi den et nytt navn**, høyreklikker du på kontrollen (eller klikker eller trykker på ellipsen ved siden av den), og deretter klikker eller trykker du på alternativet du vil ha.
