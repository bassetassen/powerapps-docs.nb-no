---
title: Opprette et sammendrag av skjema i en lerretsapp | Microsoft Docs
description: Opprette et sammendrag av skjema i en lerretsapp til å behandle data for Northwind Traders
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 04/25/2019
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 5c40cb030241d142a2ee2a68d32f7fb839a350ff
ms.sourcegitcommit: 55bc11ac6a964f22301c9fdadb06ee34e1399f83
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/07/2019
ms.locfileid: "66805921"
ms.PowerAppsDecimalTransform: true
---
# <a name="create-a-summary-form-in-a-canvas-app"></a>Opprette et sammendrag av skjema i en lerretsapp

Følg trinnvise instruksjoner for å lage et sammendrag av skjema i en lerretsapp for administrasjon av fiktive data i databasen Northwind Traders. Dette emnet er en del av en serie som forklarer hvordan du bygger en business-app på relasjonelle data i Common Data Service. Utforsk disse emnene i denne sekvensen for best resultat:

1. [Opprett en ordre galleri](northwind-orders-canvas-part1.md).
2. Opprette et sammendrag av skjema (**dette emnet**).
3. [Opprett et galleri i detalj](northwind-orders-canvas-part3.md).

> [!div class="mx-imgBorder"]
> ![Definisjonen av skjermen områder](media/northwind-orders-canvas-part1/orders-parts.png)

## <a name="prerequisites"></a>Forutsetninger

1. [Installere Northwind Traders database og apper](northwind-install.md).
1. Se gjennom den [oversikt over lerretsapp](northwind-orders-canvas-overview.md) for Northwind Traders.
1. [Opprett galleriet rekkefølge](northwind-orders-canvas-part1.md) deg selv, eller åpne den **Northwind ordrer (lerret) - begynne del 2** appen, som inneholder allerede galleriet.

## <a name="add-a-title-bar"></a>Å legge til en tittellinje

Langs toppen av appen, kan du opprette en tittellinje, som skal inneholde handlingsknapper ved slutten av dette emnet.

1. I den **trevisning** ruten velger **Screen1** å sikre at du ikke ved et uhell legger til en kontroll til galleriet rekkefølge:

    > [!div class="mx-imgBorder"]
    > ![Velg Screen1 i treet Vis-ruten](media/northwind-orders-canvas-part2/titlebar-01.png)

1. På den **Sett inn** fanen og velge **etikett** til å sette inn en [ **etikett** ](controls/control-text-box.md) kontroll:

    > [!div class="mx-imgBorder"]
    > ![Sett inn en etikett](media/northwind-orders-canvas-part2/titlebar-02.png)

    Den nye etiketten skal vises bare én gang, over galleriet. Hvis det vises i hvert element i galleriet, slette den første forekomsten av etiketten, kontroller at skjermen er valgt (som beskriver det forrige trinnet), og deretter sette inn etiketten på nytt.

1. Flytt og endre størrelsen på den nye etiketten slik at den dekker toppen av skjermen:

    > [!div class="mx-imgBorder"]
    > ![Flytte og endre størrelse på etiketten](media/northwind-orders-canvas-part2/titlebar-03.png)

1. Dobbeltklikk teksten i etiketten, og skriv deretter inn **Northwind ordrer**.

    Som et alternativ, kan du endre den **tekst** -egenskapen i formellinjen for å oppnå det samme resultatet:

    > [!div class="mx-imgBorder"]
    > ![Endre teksten i tittellinjen](media/northwind-orders-canvas-part2/titlebar-04.png)

1. På den **Hjem** fanen, formatere etiketten:
    - Øk skriftstørrelsen til 24 punkt.
    - Gjøre teksten fet.
    - Gjøre teksten hvit.
    - Midtstill teksten.
    - Legge til en mørkeblå fyll i bakgrunnen.

    > [!div class="mx-imgBorder"]
    > ![Formateringsalternativene på Hjem-fanen](media/northwind-orders-canvas-part2/titlebar-05.png)

## <a name="add-an-edit-form-control"></a>Legg til en redigeringskontrollen for skjemaet

I denne delen, skal du legge til kontroller for å vise et sammendrag av hvilken som helst rekkefølge som brukeren velger i galleriet.

1. På den **Sett inn** fanen, sette inn en [ **redigeringsskjema** ](controls/control-form-detail.md) kontroll:

    > [!div class="mx-imgBorder"]
    > ![Legg til en redigeringskontrollen for skjemaet](media/northwind-orders-canvas-part2/form-01.png)

    Som standard vises skjemaet i hjørnet øverst til venstre, der andre kontroller kan være vanskelig å finne:

    > [!div class="mx-imgBorder"]
    > ![Rediger skjema-kontrollen i standardplasseringen](media/northwind-orders-canvas-part2/form-02.png)

1. Flytt og endre størrelsen på skjemaet for å dekke hjørnet øverst til høyre på skjermen under tittellinjen:

    > [!div class="mx-imgBorder"]
    > ![Flytt og endre redigeringskontrollen for skjemaet](media/northwind-orders-canvas-part2/form-03.png)

1. I formellinjen, kan du angi den **DataSource** egenskapen for skjemaet til denne verdien:

    ```powerapps-comma
    Orders
    ```

    > [!div class="mx-imgBorder"]
    > ![Angi DataSource-egenskapen for redigeringskontrollen for skjemaet](media/northwind-orders-canvas-part2/form-04.png)

    Du kan angi den samme egenskapen i den **Egenskaper** fanen nær høyre kant, men denne tilnærmingen legger til felt som du ikke trenger i skjemaet. Hvis du bruker formellinjen, forblir skjemaet tom.

## <a name="add-and-arrange-fields"></a>Legg til og ordne felt

1. I den **Egenskaper** fanen nær høyre kant, velg **Rediger felt** å åpne den **felt** ruten:

    > [!div class="mx-imgBorder"]
    > ![Åpne felt-ruten](media/northwind-orders-canvas-part2/form-05.png)

1. I den **felt** ruten velger **Legg til felt**, og velg deretter merket for den **kunden** og **ansatte** felt.

    > [!div class="mx-imgBorder"]
    > ![Legge til feltene kunder og ansatte i redigeringskontrollen for skjemaet](media/northwind-orders-canvas-part2/form-06.png)

1. Bla nedover til disse feltene vises, og Merk av i avmerkingsboksene:

    - **Notater**
    - **Ordredato**
    - **Ordrenummer**
    - **Ordrestatus**
    - **Betalt dato**

    > [!div class="mx-imgBorder"]
    > ![Legg til fem flere felt i redigeringskontrollen for skjemaet](media/northwind-orders-canvas-part2/form-07.png)

1. Nederst i den **felt** ruten velger **Legg til**, og lukk deretter den **felt** ruten.

    Skjemaet viser sju felt:

    > [!div class="mx-imgBorder"]
    > ![Rediger skjema-kontrollen viser sju felt](media/northwind-orders-canvas-part2/form-08.png)

    > [!NOTE]
    > Hvis alle felt som viser en rød Feilikonet, kan ha det oppstod et problem når dataene ble trukket fra kilden. For å løse feilen, kan du oppdatere dataene:
    >
    > 1. Velg **Datakilder** på **Vis**-fanen.
    > 1. I den **Data** ruten velger **datakilder**.
    > 1. Siden **ordrer**, velg ellipsen (...), velg **Oppdater**, og lukk deretter den **Data** ruten.
    >
    > Hvis kombinasjonsboksen for navnet på kunden eller ansatt viser fremdeles feil, må du kontrollere den **primærtekst** og **SearchField** av hver, ved å merke den og deretter åpne den **Data** ruten. Begge feltene for kundeboksen bør settes til **nwind_company**. Etter den ansatte, må begge feltene være satt til **nwind_lastname**.

1. Skjemaet er valgt, endrer du antallet kolonner i skjemaet fra 3 til 12 i den **Egenskaper** fanen nær høyre kant.

    Dette trinnet legger til fleksibilitet som du ordner feltene:

    > [!div class="mx-imgBorder"]
    > ![Endre deretter antall kolonner i redigeringskontrollen for skjemaet](media/northwind-orders-canvas-part2/form-08b.png)

    Mange UI-utforminger, er avhengige av 12-spalter fordi de har plass til radene i 1, 2, 3, 4, 6 og 12 Kontroller jevnt. I dette emnet oppretter du rader som inneholder 1, 2 eller 4 kontroller.

1. Flytt og endre størrelsen på feltene ved å dra håndtakene deres, slik du ville gjøre en annen kontroll, slik at hver rad inneholder disse datakort i angitt rekkefølge:

    - Første rad: **Ordrenummer**, **ordrestatus**, **Bestillingsdato**, og **betalt dato**
    - Andre rad: **Kunden** og **ansatt**
    - Tredje rad: **Notater**

    > [!NOTE]
    > Du kan det være enklere å utvide den **notater**, **kunden**, og **ansatte** data kort før du ordne dem.

    > [!div class="mx-imgBorder"]
    > ![Flytt og endre felt](media/northwind-orders-canvas-part2/form-rearrange.gif)

    Mer informasjon om hvordan du vil ordne felt i et skjema: [Forstå dataskjemaer for lerretsapper](working-with-form-layout.md).

## <a name="hide-time-controls"></a>Skjul kontroller for tid

I dette eksemplet trenger du ikke tid-deler av datofeltene fordi det nivået av tettheten kan ta oppmerksomheten bort brukeren. Hvis du sletter dem, kan du føre til problemer i formler som er avhengige av disse kontrollene til å oppdatere datoverdier eller fastslå plasseringen av en annen kontroll i datakortet. I stedet du vil skjule kontrollene tid ved å angi deres **Visible** egenskapen.

1. I den **trevisning** rute, velger du **Ordredato** datakort.

    Kortet kan ha et annet navn, men den inneholder **Ordredato**.

1. Velg time, minutt og kolon-skilletegn kontrollene i mens du holder nede SKIFT, den **Ordredato** datakort.

    > [!div class="mx-imgBorder"]
    > ![Velg klokkeslett kontrollene i Ordredato kort](media/northwind-orders-canvas-part2/form-09.png)

1. Angi kontrollene **Visible** egenskapen til **USANN**.

    Alle valgte kontroller forsvinner fra skjemaet:

    > [!div class="mx-imgBorder"]
    > ![Angi synlig-egenskapen til USANN.](media/northwind-orders-canvas-part2/form-10.png)

1. Endre størrelsen på den [ **datovelger** ](controls/control-date-picker.md) kontrollen til å vise dato for fullført:

    > [!div class="mx-imgBorder"]
    > ![Endre størrelse på datovelgeren](media/northwind-orders-canvas-part2/form-11.png)

    Deretter kan du vil gjenta de forrige trinnene for den **betalt dato** felt.

1. I den **trevisning** rute, velger tiden kontroller i den **betalt dato** datakort:

    > [!div class="mx-imgBorder"]
    > ![Velg tid kontrollen i kortet betalt dato](media/northwind-orders-canvas-part2/form-12.png)

1. Angi de valgte kontrollene **Visible** egenskapen til **USANN**:

    > [!div class="mx-imgBorder"]
    > ![Angi synlig-egenskapen til USANN.](media/northwind-orders-canvas-part2/form-13.png)

1. Endre størrelse på datovelgeren i den **dato betalt** kortet:

    > [!div class="mx-imgBorder"]
    > ![Endre størrelse på datovelgeren](media/northwind-orders-canvas-part2/form-14.png)

## <a name="connect-the-order-gallery"></a>Koble til galleriet rekkefølge

1. I den **trevisning** , skjule skjemaet for å lettere å søke etter navnet på galleriet rekkefølge, og deretter, hvis nødvendig, gi den nytt navn til **Gallery1**.

1. Angi sammendrag skjemaets **element** egenskapen til dette uttrykket:

    ```powerapps-comma
    Gallery1.Selected
    ```

    > [!div class="mx-imgBorder"]
    > ![Angi element-egenskapen for skjemaet](media/northwind-orders-canvas-part2/form-15.png)

    Skjemaet viser et sammendrag av fornuftig rekkefølge appbrukeren velger i listen.

    > [!div class="mx-imgBorder"]
    > ![Velg en ordre i listen for å vise oversikten i skjemaet](media/northwind-orders-canvas-part2/form-select.gif)

## <a name="replace-a-data-card"></a>Erstatt et datakort

**Ordrenummer** er en identifikator som Common Data Service-tilordner automatisk når du oppretter en post. Dette feltet har en [ **tekstinndata** ](controls/control-text-input.md) kontrollen som standard, men du vil erstatte den med en etikett slik at brukeren ikke kan redigere dette feltet.

1. Velg skjemaet, velg **Rediger felt** i den **Egenskaper** fanen nær høyre kant, og velg deretter den **ordrenummer** felt:

    > [!div class="mx-imgBorder"]
    > ![Velg feltet rekkefølge](media/northwind-orders-canvas-part2/alt-01.png)

1. Åpne den **kontroll av typen** listen:

    > [!div class="mx-imgBorder"]
    > ![Åpne den ** kontrollen typen ** liste](media/northwind-orders-canvas-part2/alt-02.png)

1. Velg den **Vis tekst** datakort:

    > [!div class="mx-imgBorder"]
    > ![Velg den ** Vis tekst ** datakort](media/northwind-orders-canvas-part2/alt-02b.png)

1. Lukk den **felt** ruten.

    Brukeren kan ikke lenger endre nummeret for:

    > [!div class="mx-imgBorder"]
    > ![Ordrenummer er skrivebeskyttet](media/northwind-orders-canvas-part2/alt-03.png)

1. På den **Hjem** fanen, endre skriftstørrelse for hvor rekkefølgen til 20 punkt, slik at feltet er enklere å finne:

    > [!div class="mx-imgBorder"]
    > ![Endre den bestillingsnummer skriftstørrelse](media/northwind-orders-canvas-part2/alt-04.png)

## <a name="use-a-many-to-one-relationship"></a>Bruk en mange-til-én-relasjon

Den **ordrer** enheten har en mange-til-én-relasjon med den **ansatte** enhet: hver ansatt kan opprette mange ordrer, men hver ordre kan tilordnes til bare én ansatt. Når brukeren velger en ansatt i den [ **kombinasjonsboks** ](controls/control-combo-box.md) kontroll, sin **valgt** egenskapen gir den ansattes hele post fra den **ansatte**  enhet. Som et resultat kan du konfigurere en [ **bilde** ](controls/control-image.md) kontrollen til å vise bildet av ansatt brukeren velger i kombinasjonsboksen.

1. Velg den **ansatte** datakort:

    > [!div class="mx-imgBorder"]
    > ![Velg datakortet](media/northwind-orders-canvas-part2/employee-01.png)

1. I den **avansert** fanen nær høyre kant, låse opp datakortet slik at du kan redigere formler som var tidligere skrivebeskyttet:

    > [!div class="mx-imgBorder"]
    > ![Låse opp datakortet](media/northwind-orders-canvas-part2/employee-02.png)

1. I datakortet, Reduser bredden på kombinasjonsboksen å gi plass til ansatte bildet:

    > [!div class="mx-imgBorder"]
    > ![Endre størrelsen på kombinasjonsboksen kontrollen](media/northwind-orders-canvas-part2/employee-03b.png)

1. På den **Sett inn** fanen og velge **Media** > **bilde**:

    > [!div class="mx-imgBorder"]
    > ![Sett inn et bilde](media/northwind-orders-canvas-part2/employee-04.png)

    Et bilde vises i datakortet, som utvider til plass til den:

    > [!div class="mx-imgBorder"]
    > ![Ansatte datakort med bilde-kontrollen](media/northwind-orders-canvas-part2/employee-05.png)

1. Endre størrelse på bildet, og Flytt den til høyre for kombinasjonsboksen:

    > [!div class="mx-imgBorder"]
    > ![Flytte og endre størrelse på bilde-kontrollen](media/northwind-orders-canvas-part2/employee-06.png)

1. Angi den **bilde** egenskapen til bildet til denne formelen, erstatter nummeret på slutten av DataCardValue om nødvendig:

    ```powerapps-comma
    DataCardValue7.Selected.Picture
    ```

    > [!div class="mx-imgBorder"]
    > ![Angi bilde-egenskapen for bildet](media/northwind-orders-canvas-part2/employee-07.png)

    Bildet av den valgte ansatt vises.

1. Mens du holder nede Alt-tasten, velg en annen ansatt i kombinasjonsboksen å bekrefte at endres bildet også.

    > [!div class="mx-imgBorder"]
    > ![Velg en ansatt som skal vise bildet av den ansatte](media/northwind-orders-canvas-part2/employee-select.gif)

## <a name="add-a-save-icon"></a>Legg til en lagre-ikonet

1. I den **trevisning** ruten velger **Screen1**, og velg deretter **Sett inn** > **ikoner**  >  **Kontroller**:

    > [!div class="mx-imgBorder"]
    > ![Sett inn hakemerkeikonet](media/northwind-orders-canvas-part2/save-01.png)

    Den [ **Kontroller** ](controls/control-shapes-icons.md) ikonet vises i hjørnet øverst til venstre som standard, der andre kontroller kan gjøre ikonet vanskelig å finne:

    > [!div class="mx-imgBorder"]
    > ![Standardplasseringen-ikonet](media/northwind-orders-canvas-part2/save-02.png)

1. På den **Hjem** endrer du den **farge** -egenskapen for ikonet til hvit, endre størrelse på ikonet, og Flytt den nær høyre kant av tittellinjen:

    > [!div class="mx-imgBorder"]
    > ![Konfigurer farge, størrelse og plassering for lagring ikon](media/northwind-orders-canvas-part2/save-03.png)

1. I den **trevisning** ruten bekrefte at skjemanavn er **Form1**, og angi deretter ikonets **OnSelect** egenskapen til denne formelen:

    ```powerapps-comma
    SubmitForm( Form1 )
    ```

    > [!div class="mx-imgBorder"]
    > ![Angi lagre ikonets OnSelect-egenskap](media/northwind-orders-canvas-part2/save-04.png)

    Når brukeren velger ikonet, den [ **SubmitForm** ](functions/function-form.md) funksjonen samler alle endrede verdiene i skjemaet, og sender dem til datakilden. Prikkene mars langs toppen av skjermen når dataene er sendt, og galleriet rekkefølge gjenspeiler endringene når prosessen er fullført.

1. Angi ikonets **DisplayMode** egenskapen til denne formelen:

    ```powerapps-comma
    If( Form1.Unsaved; DisplayMode.Edit; DisplayMode.Disabled )
    ```

    > [!div class="mx-imgBorder"]
    > ![Angi ikonets DisplayMode egenskapen](media/northwind-orders-canvas-part2/save-05.png)

    Hvis alle endringer i skjemaet har blitt lagret, ikonet er deaktivert og vises i den **DisabledColor**, som du vil angi neste.

1. Angi ikonets **DisabledColor** egenskapen til denne verdien:

    ```powerapps-comma
    Gray
    ```

    > [!div class="mx-imgBorder"]
    > ![Angi ikonets DisabledColor egenskapen](media/northwind-orders-canvas-part2/save-06.png)

    Brukeren kan lagre endringer i en ordre ved å velge ikonet kontroller, som deretter er deaktivert og nedtonet før brukeren gjør en annen endring:

    > [!div class="mx-imgBorder"]
    > ![Lagre endringer](media/northwind-orders-canvas-part2/save-submit.gif)

## <a name="add-a-cancel-icon"></a>Legg til en Avbryt-ikon

1. På den **Sett inn** fanen og velge **ikoner** > **Avbryt**:

    > [!div class="mx-imgBorder"]
    > ![Legg til Avbryt-ikon](media/northwind-orders-canvas-part2/save-07.png)

    Ikonet vises i hjørnet øverst til venstre som standard, der andre kontroller kan gjøre ikonet vanskelig å finne:

    > [!div class="mx-imgBorder"]
    > ![Avbryt-ikon i standardplasseringen](media/northwind-orders-canvas-part2/save-08.png)

1. På den **Hjem** endrer ikonets **farge** egenskapen til hvit, endre størrelse på ikonet, og Flytt den til venstre for ikonet for avmerkingsboksen:

    > [!div class="mx-imgBorder"]
    > ![Endre farge, størrelse og plassering for Avbryt-ikon](media/northwind-orders-canvas-part2/save-09.png)

1. Angi på Avbryt-ikonet **OnSelect** egenskapen til denne formelen:

    ```powerapps-comma
    ResetForm( Form1 )
    ```

    > [!div class="mx-imgBorder"]
    > ![Angi OnSelect-egenskapen på Avbryt-ikonet](media/northwind-orders-canvas-part2/save-10.png)

    Den [ **ResetForm** ](functions/function-form.md) funksjonen sletter alle endringer i skjemaet, som returnerer den til den opprinnelige tilstanden.

1. Angi på Avbryt-ikonet **DisplayMode** egenskapen til denne formelen:

    ```powerapps-comma
    If( Form1.Unsaved Or Form1.Mode = FormMode.New; DisplayMode.Edit; DisplayMode.Disabled )
    ```

    > [!div class="mx-imgBorder"]
    > ![Angi på Avbryt-ikonet DisplayMode egenskapen](media/northwind-orders-canvas-part2/save-11.png)

    Denne formelen avviker litt fra den til kontroller-ikonet. På Avbryt-ikonet er deaktivert hvis alle endringene er lagret eller skjemaet er i **ny** modus, som du vil aktivere neste. I så fall **ResetForm** forkaster den nye posten.

1. Angi på Avbryt-ikonet **DisabledColor** egenskapen til denne verdien:

    ```powerapps-comma
    Gray
    ```

    > [!div class="mx-imgBorder"]
    > ![Angi på Avbryt-ikonet DisabledColor egenskapen](media/northwind-orders-canvas-part2/save-12.png)

    Brukeren kan avbryte endringer i en ordre, og kontroller og Avbryt ikonene er deaktivert og nedtonet hvis alle endringene er lagret:

    > [!div class="mx-imgBorder"]
    > ![Lagre og avbryting av endringer](media/northwind-orders-canvas-part2/save-cancel.gif)

## <a name="add-an-add-icon"></a>Legge til et ikon for Legg til

1. På den **Sett inn** fanen og velge **ikoner** > **Legg til**.

    > [!div class="mx-imgBorder"]
    > ![Sett inn en Add-ikon](media/northwind-orders-canvas-part2/save-13.png)

    Den **Legg til** ikonet vises i hjørnet øverst til venstre som standard, der andre kontroller kan være vanskelig å finne:

    > [!div class="mx-imgBorder"]
    > ![Standardplasseringen for Legg til-ikon](media/northwind-orders-canvas-part2/save-14.png)

1. På den **Hjem** fanen, angir du **farge** -egenskapen for ikonet Legg til hvit, endre størrelse på ikonet, og Flytt den til venstre for på Avbryt-ikonet:

    > [!div class="mx-imgBorder"]
    > ![Endre farge, størrelse og plassering av ikonet Legg til](media/northwind-orders-canvas-part2/save-15.png)

1. Angi ikonet Legg til **OnSelect** egenskapen til denne formelen:

    ```powerapps-comma
    NewForm( Form1 )
    ```

    > [!div class="mx-imgBorder"]
    > ![Angi OnSelect-egenskapen for ikonet Legg til](media/northwind-orders-canvas-part2/save-15b.png)

    Den [ **NewForm** ](functions/function-form.md) funksjonen viser en tom post i skjemaet.  

1. Angi ikonet Legg til **DisplayMode** egenskapen til denne formelen:

    ```powerapps-comma
    If( Form1.Unsaved Or Form1.Mode = FormMode.New; DisplayMode.Disabled; DisplayMode.Edit )
    ```

    > [!div class="mx-imgBorder"]
    > ![Angi egenskapen for ikonet Legg til DisplayMode](media/northwind-orders-canvas-part2/save-16.png)

    Formelen deaktiverer Legg til ikonet under disse betingelsene:

    - Brukeren gjør endringer, men ikke lagre eller avbryte dem, som er den motsatte virkemåten fra ikonene kontroll og Avbryt.
    - Brukeren velger ikonet Legg til, men endrer ikke.

1. Angi ikonet Legg til **DisabledColor** egenskapen til denne verdien:

    ```powerapps-comma
    Gray
    ```

    > [!div class="mx-imgBorder"]
    > ![Angi egenskapen for ikonet Legg til DisabledColor](media/northwind-orders-canvas-part2/save-17.png)

    Brukeren kan opprette en ordre hvis de ikke gjøre endringer eller lagre eller annullere alle endringer de har gjort. (Hvis brukeren velger dette ikonet, de kan ikke velge den på nytt før de gjør en eller flere endringer og deretter lagre eller avbryte endringene):

    > [!div class="mx-imgBorder"]
    > ![Opprette en ordre](media/northwind-orders-canvas-part2/save-new.gif)

> [!NOTE]
> Hvis du oppretter og lagrer en ordre, må du kanskje bla nedover i galleriet rekkefølge for å vise den nye bestillingen. Den vil ikke ha en Totalpris fordi du ikke har lagt til en hvilken som helst Ordredetaljer ennå.

## <a name="add-a-trash-icon"></a>Legg til et Papirkurv-ikon

1. På den **Sett inn** fanen og velge **ikoner** > **Papirkurv**.

    > [!div class="mx-imgBorder"]
    > ![Sett inn en Papirkurv-ikon](media/northwind-orders-canvas-part2/save-18.png)

    Den **Papirkurv** ikonet vises i hjørnet øverst til venstre som standard, der andre kontroller kan være vanskelig å finne:

    > [!div class="mx-imgBorder"]
    > ![Standardplasseringen for papirkurvikonet](media/northwind-orders-canvas-part2/save-19.png)

1. På den **Hjem** endrer du på Papirkurv-ikonet **farge** egenskapen til hvit, endre størrelse på ikonet, og Flytt den til venstre for ikonet Legg til:

    > [!div class="mx-imgBorder"]
    > ![Endre farge, størrelse og plassering av Papirkurv-ikonet](media/northwind-orders-canvas-part2/save-20.png)

1. Angi på Papirkurv-ikonet **OnSelect** egenskapen til denne formelen:

    ```powerapps-comma
    Remove( Orders; Gallery1.Selected )
    ```

    > [!div class="mx-imgBorder"]
    > ![Angi OnSelect-egenskapen på Papirkurv-ikonet](media/northwind-orders-canvas-part2/save-21.png)

    Den [ **fjerne** ](functions/function-remove-removeif.md) funksjonen fjerner en post fra en datakilde. I denne formelen fjerner funksjonen posten som er valgt i galleriet rekkefølge. Papirkurvikonet vises nær sammendrag skjemaet (ikke i rekkefølge-galleriet) fordi skjemaet viser mer informasjon om posten, slik at brukeren kan enklere å identifisere posten som formelen, slettes.

1. Angi på Papirkurv-ikonet **DisplayMode** egenskapen til denne formelen:

    ```powerapps-comma
    If( Form1.Mode = FormMode.New; DisplayMode.Disabled; DisplayMode.Edit )
    ```

    > [!div class="mx-imgBorder"]
    > ![Angi på Papirkurv-ikonet DisplayMode egenskapen](media/northwind-orders-canvas-part2/save-22.png)

    Denne formelen deaktiverer papirkurvikonet Hvis brukeren oppretter en post. Før brukeren lagrer posten, den **fjerne** -funksjonen har ingen posten som skal slettes.

1. Angi på Papirkurv-ikonet **DisabledColor** egenskapen til denne verdien:

    ```powerapps-comma
    Gray
    ```

    > [!div class="mx-imgBorder"]
    > ![Angi på Papirkurv-ikonet DisabledColor egenskapen](media/northwind-orders-canvas-part2/save-23.png)

    Brukeren kan slette en ordre.

    > [!div class="mx-imgBorder"]
    > ![Sletting av ordrer](media/northwind-orders-canvas-part2/save-delete.gif)

## <a name="summary"></a>Sammendrag

Hvis du vil kort oppsummering, du har lagt til et skjema der brukeren kan vise og redigere et sammendrag av hver ordre, og du brukte disse elementene:

- Et skjema som viser data fra den **ordrer** enhet: **Form1.DataSource =** `Orders`
- En tilkobling mellom skjemaet og galleriet rekkefølge: **Form1.Item =** `Gallery1.Selected`
- En annen kontroll for den **ordrenummer** felt: **Vis tekst**
- En mange-til-én-relasjon til å vise den ansattes bilde i den **ansatte** datakort: `DataCardValue1.Selected.Picture`
- Et ikon for å lagre endringer i en ordre: `SubmitForm( Form1 )`
- Et ikon for å avbryte endringer i en ordre: `ResetForm( Form1 )`
- Et ikon for å opprette en ordre: `NewForm( Form1 )`
- Et ikon for å slette en ordre: `Remove( Orders; Gallery1.Selected )`

## <a name="next-step"></a>Neste trinn

I neste emne, skal du legge til en annen galleriet for å vise produktene i hver ordre, og du vil endre disse detaljene ved hjelp av den [ **Patch** ](functions/function-patch.md) funksjonen.

> [!div class="nextstepaction"]
> [Opprett detalj-galleri](northwind-orders-canvas-part3.md)
