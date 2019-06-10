---
title: Opprett et galleri i detalj i en lerretsapp | Microsoft Docs
description: Opprett et galleri i detalj i en lerretsapp til å behandle data for Northwind Traders
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
ms.openlocfilehash: 9549b8f389cf696cf3fc8e4659da6b418383ac6e
ms.sourcegitcommit: e85072f7a80da308c4caabe20adbf2509588ca57
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/07/2019
ms.locfileid: "66760963"
---
# <a name="create-a-detail-gallery-in-a-canvas-app"></a>Opprett et galleri i detalj i en lerretsapp

Følg trinnvise instruksjoner for å opprette et galleri i detalj i en lerretsapp for administrasjon av fiktive data i databasen Northwind Traders. Dette emnet er en del av en serie som forklarer hvordan du bygger en business-app på relasjonelle data i Common Data Service. Utforsk disse emnene i denne sekvensen for best resultat:

1. [Opprett en ordre galleri](northwind-orders-canvas-part1.md).
1. [Opprette et sammendrag av skjema](northwind-orders-canvas-part2.md).
1. Opprett et detalj-galleri (**dette emnet**).

> [!div class="mx-imgBorder"]
> ![Definisjonen av skjermen områder](media/northwind-orders-canvas-part1/orders-parts.png)

## <a name="prerequisites"></a>Forutsetninger

Før du starter dette emnet, må du installere databasen som beskrevet tidligere i dette emnet. Du må deretter oppretter du galleriet rekkefølge og sammendrag skjemaet eller åpner den **Northwind ordrer (lerret) - begynne del 3** app, som inneholder allerede galleriet og dette skjemaet.

## <a name="create-another-title-bar"></a>Opprette en annen tittellinjen

1. Øverst på skjermen, velg den [ **etikett** ](controls/control-text-box.md) kontroll som fungerer som en tittellinje, Kopier den ved å trykke på Ctrl + C, og lim den deretter inn ved å trykke på Ctrl-V:

    > [!div class="mx-imgBorder"]
    > ![Kopier og Lim inn tittellinjen](media/northwind-orders-canvas-part3/details-01.png)

1. Endre størrelsen på og flytte kopien slik at den vises bare under sammendrag skjemaet.

1. Fjern teksten fra kopien i én av følgende måter:

    - Dobbeltklikk teksten for å merke den, og trykk deretter på Slett.
    - Angi etikettens **tekst** egenskapen til en tom streng ( **""** ).

    > [!div class="mx-imgBorder"]
    > ![Fjerne teksten fra tittellinjen-kopi](media/northwind-orders-canvas-part3/details-02.png)

## <a name="add-a-gallery"></a>Å legge til et galleri

1. Sett inn en [ **galleriet** ](controls/control-gallery.md) kontroll med en **tomt, loddrett** oppsett:

    > [!div class="mx-imgBorder"]
    > ![Legg til et tomt loddrett galleri](media/northwind-orders-canvas-part3/details-03.png)

    Ny galleriet, som viser Ordredetaljer, vises i hjørnet øverst til venstre:

    > [!div class="mx-imgBorder"]
    > ![Standardplasseringen for Ordredetaljer galleriet](media/northwind-orders-canvas-part3/details-04.png)

1. Lukk den **Data** ruten, og deretter endre størrelsen på og Flytt galleriet detaljer til hjørnet nederst til høyre under tittellinjen for nye:

    > [!div class="mx-imgBorder"]
    > ![Endelige plasseringen av Ordredetaljer galleri](media/northwind-orders-canvas-part3/details-05.png)

1. Angi den **elementer** -egenskapen for galleriet detaljer til denne formelen:

    ```powerapps-dot
    Gallery1.Selected.'Order Details'
    ```

    > [!div class="mx-imgBorder"]
    > ![Angi Items-egenskapen for galleriet detaljer](media/northwind-orders-canvas-part3/details-06.png)

    Hvis det vises en feil, kan du bekrefte at rekkefølgen galleriet heter **Gallery1** (i den **trevisning** ruten nær venstre kant). Hvis galleriet har et annet navn, gi nytt navn til den **Gallery1**.

    Du har nettopp koblet to galleriene. Når brukeren velger en ordre i galleriet rekkefølge, det merkede området identifiserer en post i den **ordrer** enhet. Hvis at ordren inneholder én eller flere linje elementer, posten i den **ordrer** enheten er koblet til én eller flere poster i den **Ordredetaljer** enhet, og data fra disse postene vises i galleriet for detaljer. Denne virkemåten gjenspeiler én-til-mange-relasjon som ble opprettet for deg mellom den **ordrer** og **Ordredetaljer** enheter. Formelen som du har angitt leder «» denne relasjonen ved hjelp av prikk notasjon:

    > [!div class="mx-imgBorder"]
    > ![Én-til-mange-relasjon mellom enheten ordrer og Ordredetaljer enheten](media/northwind-orders-canvas-part3/schema-orders-rel.png)

## <a name="show-product-names"></a>Vis produktnavnene

1. I galleriet detaljer, velg **legge til et element fra kategorien Sett inn** til å velge gallerimalen:

    > [!div class="mx-imgBorder"]
    > ![Velg en mal for galleriet detaljer](media/northwind-orders-canvas-part3/details-07.png)

    Kontroller at du har valgt i malgalleriet i stedet for selve galleriet. Rammen må være litt innenfor galleriets grensen og sannsynligvis kortere enn galleriets høyde. Når du setter inn kontroller i denne malen, gjentas for hvert element i galleriet.

1. På den **Sett inn** fanen, sette inn en etikett i galleriet for detaljer.

    Etiketten skal vises i galleriet; Hvis ikke, prøv på nytt, men Pass på å velge malen i galleriet før du setter inn etiketten.

    > [!div class="mx-imgBorder"]
    > ![Legge til en etikett i detalj-galleriet](media/northwind-orders-canvas-part3/details-08.png)

1. Angi ny etikettens **tekst** egenskapen til denne formelen:

    ```powerapps-dot
    ThisItem.Product.'Product Name'
    ```

    Hvis ingen teksten vises, velger du pilen for **rekkefølge 0901** nær bunnen av galleriet rekkefølge.

1. Endre størrelse på etiketten slik at hele teksten vises:

    > [!div class="mx-imgBorder"]
    > ![Vis Produktnavn i Ordredetaljer](media/northwind-orders-canvas-part3/details-09.png)

    Dette uttrykket går fra en post i den **Ordredetaljer** enhet. Posten er beholdes i **ThisItem** over til den **bestille produkter** enheten via en mange-til-én-relasjon:

    > [!div class="mx-imgBorder"]
    > ![Mange-til-én-relasjon mellom Ordredetaljer enheten og selve produktenheten for rekkefølge](media/northwind-orders-canvas-part3/schema-orderdetails-rel.png)

    Den **Produktnavn** feltet (og andre felt som du er i ferd med å bruke) som er trukket ut:

    > [!div class="mx-imgBorder"]
    > ![Feltene i enheten bestille produkter](media/northwind-orders-canvas-part3/schema-products-fields.png)

## <a name="show-product-images"></a>Vis produktbildene

1. På den **Sett inn** fanen, sette inn en [ **bilde** ](controls/control-image.md) kontroll i galleriet detaljer:

    > [!div class="mx-imgBorder"]
    > ![Sett inn bilde-kontrollen](media/northwind-orders-canvas-part3/details-10.png)

1. Endre størrelse på og flytte bildet og etiketten som skal være side ved side.

    > [!TIP]
    > For finjustert kontroll over størrelsen og plasseringen av en kontroll, begynner å endre størrelse på eller flytte den uten å trykke på Alt-tasten, og fortsett deretter å endre størrelse på eller flytte kontrollen mens du holder nede Alt-tasten:

    > [!div class="mx-imgBorder"]
    > ![Flytt bilde-kontrollen](media/northwind-orders-canvas-part3/details-11.png)

1. Angi bildets **bilde** egenskapen til denne formelen:

    ```powerapps-dot
    ThisItem.Product.Picture
    ```

    På nytt, de uttrykket refererer til en produktet som er forbundet med dette bestille detaljer og å trekke ut de **bilde** felt som skal vises.

    > [!div class="mx-imgBorder"]
    > ![Vis produktbilde](media/northwind-orders-canvas-part3/details-12.png)

1. Redusere høyden på malen i galleriet slik at mer enn én **Ordredetaljer** post vises på et tidspunkt:

    > [!div class="mx-imgBorder"]
    > ![Forkort malen i galleriet](media/northwind-orders-canvas-part3/details-13.png)

## <a name="show-product-quantity-and-cost"></a>Vis produktantall og kostnad

1. På den **Sett inn** fanen, sette inn en annen etikett i galleriet for detaljer, og deretter endre størrelse på og flytte den nye etiketten til høyre for produktinformasjon.

1. Angi ny etikettens **tekst** egenskapen til dette uttrykket:

    ```powerapps-dot
    ThisItem.Quantity
    ```

    Denne formelen henter informasjon direkte fra den **Ordredetaljer** enhet (ingen relasjoner kreves).

    > [!div class="mx-imgBorder"]
    > ![Vis produktantallet](media/northwind-orders-canvas-part3/details-13b.png) 

1. På den **Hjem** endrer justeringen for denne kontrollen til **høyre**:

    > [!div class="mx-imgBorder"]
    > ![Endre justering](media/northwind-orders-canvas-part3/details-14.png)

1. På den **Sett inn** fanen, sette inn en annen etikett i galleriet for detaljer, og endre størrelse på og flytte etiketten til høyre for etiketten antall.

1. Angi ny etikettens **tekst** egenskapen til denne formelen:

    ```powerapps-dot
    Text( ThisItem.'Unit Price', "[$-en-US]$ #,###.00" )
    ```

    Hvis du ikke inkluderer språkkoden ( **[$-en-US]** ), legges den for deg basert på ditt språk og område. Hvis du bruker en annen språkkode, vil du vil fjerne den **$** like etter Lukk hakeparentes ( **]** ), og deretter legge til dine egne valutasymbol i plasseringen.

    > [!div class="mx-imgBorder"]
    > ![Vis salgspris](media/northwind-orders-canvas-part3/details-15.png)

1. På den **Hjem** endrer justeringen for denne kontrollen til **høyre**:

    > [!div class="mx-imgBorder"]
    > ![Endre justering](media/northwind-orders-canvas-part3/details-16.png)

1. På den **Sett inn** fanen, sette inn en annen etikettkontroll i galleriet for detaljer, og deretter endre størrelse på og flytte den nye etiketten til høyre for enhetsprisen.

1. Angi ny etikettens **tekst** egenskapen til denne formelen:

    ```powerapps-dot
    Text( ThisItem.Quantity * ThisItem.'Unit Price', "[$-en-US]$ #,###.00" )
    ```

    På nytt, hvis du ikke inkluderer språkkoden ( **[$-en-US]** ), legges den for deg basert på ditt språk og område. Hvis merket er forskjellig, vil du vil bruke din egen valutasymbol i stedet for den **$** like etter Lukk hakeparentes ( **]** ).

    > [!div class="mx-imgBorder"]
    > ![Vis utvidet pris](media/northwind-orders-canvas-part3/details-17.png)

1. På den **Hjem** endrer justeringen for denne kontrollen til **høyre**:

    > [!div class="mx-imgBorder"]
    > ![Endre justering](media/northwind-orders-canvas-part3/details-18.png)

    Du er ferdig å legge til kontroller i detalj-galleriet for øyeblikket.

1. I den **trevisning** ruten velger **Screen1** å sikre at det ikke lenger er valgt i detalj-galleriet.

## <a name="add-text-to-the-new-title-bar"></a>Legge til tekst i nye tittellinjen

1. På den **Sett inn** fanen, sette inn en annen etikett videre til skjermen:

    > [!div class="mx-imgBorder"]
    > ![Sett inn etikett](media/northwind-orders-canvas-part3/details-19.png)

1. Endre størrelse på og flytte den nye etiketten over bilder av produktene i andre tittellinjen, og endre deretter tekstens farge hvit på den **Hjem** fanen.

1. Dobbeltklikk etikettens tekst, og skriv deretter inn **produktet**:

    > [!div class="mx-imgBorder"]
    > ![Endre etiketteksten til produktet](media/northwind-orders-canvas-part3/details-20.png)

1. Kopier og Lim inn produktetikett, og endre størrelse på og flytte kopien over antall-kolonnen.

1. Dobbeltklikk den nye etiketten tekst, og skriv deretter inn **antall**:

    > [!div class="mx-imgBorder"]
    > ![Endre etiketteksten til antall](media/northwind-orders-canvas-part3/details-21.png)

1. Kopier og Lim inn antall etiketten, og endre størrelse på og flytte kopien over enhetsprisen kolonnen.

1. Dobbeltklikk den nye etiketten tekst, og skriv deretter inn **enhetsprisen**:

    > [!div class="mx-imgBorder"]
    > ![Endre etiketteksten til salgspris](media/northwind-orders-canvas-part3/details-22.png)

1. Kopier og Lim inn enhetsprisen etiketten, og endre størrelse på og flytte kopien over utvidet pris-kolonnen.

1. Dobbeltklikk teksten i den nye etiketten, og skriv deretter inn **utvidet**:

    > [!div class="mx-imgBorder"]
    > ![Endre etiketteksten til utvidet](media/northwind-orders-canvas-part3/details-23.png)

## <a name="display-order-totals"></a>Vis totalsum

1. Redusere høyden på galleriet detaljer for å gi plass til av ordrer nederst på skjermen:

    > [!div class="mx-imgBorder"]
    > ![Forkort Ordredetaljer galleriet](media/northwind-orders-canvas-part3/sum-01.png)

1. Kopier og Lim inn tittellinjen midt på skjermen, og flytt deretter kopien til bunnen av skjermen:

    > [!div class="mx-imgBorder"]
    > ![Kopier tittellinjen, og Flytt kopi til den nederste kanten](media/northwind-orders-canvas-part3/sum-02.png)

1. Kopier og Lim inn produktet etiketten fra den midterste tittellinjen, og deretter flytte kopien til den nederste linjen for tittel, bare til venstre for den **antall** kolonnen.

1. Dobbeltklikk den nye etiketten tekst, og skriv deretter inn denne teksten:<br>**Totalsum:**

    > [!div class="mx-imgBorder"]
    > ![Legg til etikett for totalsum](media/northwind-orders-canvas-part3/sum-03.png)

1. Kopier og Lim inn-totalsum etiketten, og endre størrelse på og flytte kopien til høyre for etiketten totalsum.

1. Angi ny etikettens **tekst** egenskapen til denne formelen:

    ```powerapps-dot
    Sum( Gallery1.Selected.'Order Details', Quantity )
    ```

    Denne formelen viser en delegeringsadvarsel, men du kan ignorere den fordi ingen enkelt ordre vil inneholde mer enn 500 produkter.

1. På den **Hjem** fanen, angir du den nye etiketten tekstjustering **høyre**:

    > [!div class="mx-imgBorder"]
    > ![Endre justering](media/northwind-orders-canvas-part3/sum-04.png)

1. Kopier og Lim inn denne etikettkontrollen, og deretter endre størrelse på og flytte kopien under den **utvidet** kolonnen.

1. Angi kopien **tekst** egenskapen til denne formelen:

    ```powerapps-dot
    Text( Sum( Gallery1.Selected.'Order Details', Quantity * 'Unit Price' ), "[$-en-US]$ #,###.00" )
    ```

    Denne formelen viser en delegeringsadvarsel, men du kan ignorere den fordi ingen enkelt ordre vil inneholde mer enn 500 produkter.

    > [!div class="mx-imgBorder"]
    > ![Vis totale kostnaden for ordre](media/northwind-orders-canvas-part3/sum-05.png)

## <a name="add-space-for-new-details"></a>Legg til plass til nye detaljer

I en hvilken som helst galleri, du kan vise data, men du kan ikke oppdatere den eller legge til poster. Under galleriet for detaljer, skal du legge til et område der brukeren kan konfigurere en post i den **Ordredetaljer** enhets- og Sett inn som registrerer til en ordre.

1. Redusere høyden på detaljer galleriet nok til å gi plass til ett element redigering plass under galleriet.

    I dette området, skal du legge til kontroller slik at brukeren kan legge til en Ordredetaljer:

    > [!div class="mx-imgBorder"]
    > ![Korte ned i detaljer-galleriet](media/northwind-orders-canvas-part3/add-details-01.png)

1. På den **Sett inn** fanen, sette inn en etikett, og deretter endre størrelse på og Flytt den under galleriet for detaljer.

    > [!div class="mx-imgBorder"]
    > ![Sett inn en etikett](media/northwind-orders-canvas-part3/add-details-02.png)

1. Dobbeltklikk teksten i den nye etiketten, og trykk deretter på Slett.

1. På den **Hjem** fanen, angir du den nye etiketten **Fyll** farge til **LightBlue**:

    > [!div class="mx-imgBorder"]
    > ![Endre etikettens fyll til lys blå](media/northwind-orders-canvas-part3/add-details-03.png)

## <a name="add-the-order-details-data-source"></a>Legg til detaljer om datakilden

1. På den **Vis** fanen og velge **datakilder**, og velg deretter **Legg til datakilde** i den **Data** ruten:

    > [!div class="mx-imgBorder"]
    > ![Legg til datakilde](media/northwind-orders-canvas-part3/add-details-04.png)

1. Velg **Common Data Service-** :

    > [!div class="mx-imgBorder"]
    > ![Velg Common Data Service](media/northwind-orders-canvas-part3/add-details-05.png)

1. På toppen av den **Data** ruten, skriver du inn **rekkefølge** i søkeboksen, velger du den **Ordredetaljer** Merk av i boksen, og velg deretter **koble til** på den bunnen av ruten:

    > [!div class="mx-imgBorder"]
    > ![Angi rekkefølgen detaljer-enhet](media/northwind-orders-canvas-part3/add-details-06.png)

    Du har nettopp la til en annen datakilde i appen:

    > [!div class="mx-imgBorder"]
    > ![Listen over datakilder](media/northwind-orders-canvas-part3/add-details-07.png)

    Du må legge til denne datakilden fordi, ikke selv om appen kan lese gjennom en én-til-mange-relasjon, appen kan ennå skrive tilbake endringer. Appen må gjøre endringer direkte med den relaterte enheten.

1. Lukk den **Data** ruten.

## <a name="select-a-product"></a>Velg et produkt

1. På den **Sett inn** fanen og velge **Kontroller** > **kombinasjonsboks**:

    > [!div class="mx-imgBorder"]
    > ![Sett inn kombinasjonsboks](media/northwind-orders-canvas-part3/add-details-08.png)

    Den [ **kombinasjonsboks** ](controls/control-combo-box.md) kontrollen vises i hjørnet øverst til venstre.

1. Angi kombinasjonsboksen **elementer** egenskapen til denne formelen:

    ```powerapps-dot
    Choices( 'Order Details'.Product )
    ```

    > [!div class="mx-imgBorder"]
    > ![Angi kombinasjonsboksen for egenskapen element-egenskap](media/northwind-orders-canvas-part3/add-details-09.png)

    Den [ **valg** ](functions/function-choices.md) -funksjonen returnerer en tabell med alle de mulige verdiene for den **produktet** feltet i den **Ordredetaljer** enhet. Dette feltet er et oppslag i en mange-til-én-relasjon, så **valg** returnerer alle postene i den **bestille produkter** enhet.

    > [!NOTE]
    > Du kan også bruke **valg** med alternativsett til å returnere en tabell med alle alternativene. Trinnene ikke er nevnt denne fremgangsmåten, men du brukt den allerede når du har lagt til i en kombinasjonsboks vises som viser **ordrestatus** i skjemaet sammendrag.

1. I den **Data** ruten, åpne det **primærtekst** listen, og velg deretter **nwind_productname**. 

1. Åpne den **SearchField** listen, og velg deretter **nwind_productname**.

    Du kan angi det logiske navnet fordi den **Data** ruten støtter ikke visningsnavnene i dette tilfellet ennå:

    > [!div class="mx-imgBorder"]
    > ![Angi den primære teksten for kombinasjonsboksen](media/northwind-orders-canvas-part3/add-details-10.png)

1. Lukk den **Data** ruten.

1. I den **Egenskaper** fanen nær høyre kant, bla nedover, slå av **Tillat flere valg**, og Sørg for at **Tillat søker** er slått på:

    > [!div class="mx-imgBorder"]
    > ![Deaktiver flere valg og aktivere søk](media/northwind-orders-canvas-part3/add-details-12.png)

1. Endre størrelsen på og flytte kombinasjonsboksen til lyseblå, like under Produktnavn kolonnen i galleriet detaljer:

    > [!div class="mx-imgBorder"]
    > ![Flytt kombinasjonsboks](media/northwind-orders-canvas-part3/add-details-13.png)

    I denne kombinasjonsboksen, vil brukeren angir en post i den **produktet** enhet for den **Ordredetaljer** post som oppretter appen.

1. Mens du holder nede Alt-tasten, velger du pil ned for kombinasjonsboksen.

    > [!TIP]
    > Du kan samhandle med kontroller i PowerApps Studio uten å åpne forhåndsvisningsmodus ved å holde nede Alt-tasten.

1. Velg et produkt i listen over produkter som vises:

    > [!div class="mx-imgBorder"]
    > ![Velg et produkt i kombinasjonsboksen](media/northwind-orders-canvas-part3/add-details-14.png)

## <a name="add-a-product-image"></a>Legg til en produktbilde

1. På den **Sett inn** fanen og velge **Media** > **bilde**:

    > [!div class="mx-imgBorder"]
    > ![Sett inn bilde-kontrollen](media/northwind-orders-canvas-part3/add-details-15.png)

    Den [ **bilde** ](controls/control-image.md) kontrollen vises i hjørnet øverst til venstre:

    > [!div class="mx-imgBorder"]
    > ![Standardplasseringen for bilde-kontrollen](media/northwind-orders-canvas-part3/add-details-16.png)

1. Endre størrelsen på og flytte bildet til lyseblå under andre produktbildene og ved siden av kombinasjonsboksen.

1. Angi den **bilde** egenskapen til bildet til:

    ```powerapps-dot
    ComboBox1.Selected.Picture
    ```

    > [!div class="mx-imgBorder"]
    > ![Angi bilde-egenskapen for bildet](media/northwind-orders-canvas-part3/add-details-17.png)

    Du bruker det samme trikset som du brukte til å vise bildet ansatte i skjemaet sammendrag. Den **valgt** -egenskapen for kombinasjonsboksen returnerer hele posten av uansett hvilket produkt som brukeren velger, inkludert den **bilde** felt.

## <a name="add-a-quantity-box"></a>Legge til en antall boks

1. På den **Sett inn** fanen og velge **tekst** > **tekstinndata**:

    > [!div class="mx-imgBorder"]
    > ![Legg til tekstinndata-boksen](media/northwind-orders-canvas-part3/add-details-18.png)

    Den [ **tekstinndata** ](controls/control-text-input.md) kontrollen vises i hjørnet øverst til venstre:

    > [!div class="mx-imgBorder"]
    > ![Standardplasseringen for tekstinndata-boksen](media/northwind-orders-canvas-part3/add-details-19.png)

1. Endre størrelsen på og flytte tekstinndata-boksen til høyre i kombinasjonsboksen, under antall-kolonnen i galleriet detaljer:

    > [!div class="mx-imgBorder"]
    > ![Endre størrelsen på og flytte tekstinndata-boksen](media/northwind-orders-canvas-part3/add-details-20.png)

    Ved å bruke denne tekstinndata-boksen, vil brukeren angi den **antall** feltet i den **Ordredetaljer** post.

1. Angi den **standard** for denne kontrollen til **""** :

    > [!div class="mx-imgBorder"]
    > ![Angi den ** standard **-egenskapen for tekstinndata-boksen](media/northwind-orders-canvas-part3/add-details-21.png)

1. På den **Hjem** fanen, angir tekstjusteringen for denne kontrollen til **høyre**:

    > [!div class="mx-imgBorder"]
    > ![Endre justering](media/northwind-orders-canvas-part3/add-details-22.png)

## <a name="show-the-unit-and-extended-prices"></a>Vis enhet og utvidet priser

1. På den **Sett inn** fanen, sette inn en **etikett** kontroll.

    Etiketten vises i hjørnet øverst til venstre på skjermen:

    > [!div class="mx-imgBorder"]
    > ![Sett inn en etikett](media/northwind-orders-canvas-part3/add-details-23.png)

1. Endre størrelse på og flytte etiketten til høyre for kontrollen for innskriving av tekst, og angi etikettens **tekst** egenskapen til denne formelen:

    ```powerapps-dot
    Text( ComboBox1.Selected.'List Price', "[$-en-US]$ #,###.00" )
    ```

    > [!div class="mx-imgBorder"]
    > ![Angi etikettens tekstegenskapen](media/northwind-orders-canvas-part3/add-details-24.png)

    Denne kontrollen viser den **listepris** fra den **bestille produkter** enhet. Bestemmer denne verdien den **enhetsprisen** feltet i den **Ordredetaljer** post.

    > [!NOTE]
    > Verdien er skrivebeskyttet for dette scenarioet, men andre scenarioer kan kalle for appen bruker til å endre den. I så fall må bruke en **tekstinndata** kontroll, og angi dens **standard** egenskapen til **listepris**.

1. På den **Hjem** fanen, angir tekstjusteringen for listepris etiketten til **høyre**:

    > [!div class="mx-imgBorder"]
    > ![Endre justering](media/northwind-orders-canvas-part3/add-details-25.png)

1. Kopier og Lim inn listepris etiketten, og endre størrelse på og flytte kopien til høyre for listepris etiketten.

1. Angi ny etikettens **tekst** egenskapen til denne formelen:

    ```powerapps-dot
    Text( Value(TextInput1.Text) * ComboBox1.Selected.'List Price', "[$-en-US]$ #,###.00" )
    ```

    > [!div class="mx-imgBorder"]
    > ![Angi ny etikettens tekstegenskapen](media/northwind-orders-canvas-part3/add-details-27.png)

    Denne kontrollen viser den utvidede prisen basert på antallet som appen brukeren angav og listeprisen for produktet som appen brukeren har valgt. Det er bare ment som informasjon for app-bruker.

1. Dobbeltklikk tekstinndata kontrollen for antall, og skriv deretter inn et tall.

    Den **utvidet** pris etikett beregner på nytt for å vise den nye verdien:

    > [!div class="mx-imgBorder"]
    > ![Angi et antall, og Vis den utvidede prisen](media/northwind-orders-canvas-part3/add-details-28.png)

## <a name="add-an-add-icon"></a>Legge til et ikon for Legg til

1. På den **Sett inn** fanen og velge **ikoner** > **Legg til**:

    > [!div class="mx-imgBorder"]
    > ![Sett inn Legg til-ikon](media/northwind-orders-canvas-part3/add-details-29.png)

    Ikonet vises i hjørnet øverst til venstre på skjermen.

    > [!div class="mx-imgBorder"]
    > ![Standardplasseringen for Legg til-ikon](media/northwind-orders-canvas-part3/add-details-30.png)

1. Endre størrelse på og flytte dette ikonet til høyre kant av lyseblå området, og angi deretter ikonets **OnSelect** egenskapen til denne formelen:

    ```powerapps-dot
    Patch( 'Order Details',
        Defaults('Order Details'),
        {
            Order: Gallery1.Selected,
            Product: ComboBox1.Selected,
            Quantity: Value(TextInput1.Text),
            'Unit Price': ComboBox1.Selected.'List Price'
        }
    );
    Refresh( Orders );
    Reset( ComboBox1 );
    Reset( TextInput1 )
    ```

    > [!div class="mx-imgBorder"]
    > ![Angi ikonets OnSelect-egenskapen](media/northwind-orders-canvas-part3/add-details-31.png)

    Vanligvis den [ **Patch** ](functions/function-patch.md) funksjonen oppdaterer og oppretter poster, og de bestemte argumentene i denne formelen ut nøyaktig endringene som funksjonen vil gjøre.

    - Det første argumentet angir datakilden (i dette tilfellet den **Ordredetaljer** enhet) der funksjonen vil oppdatere eller opprette en post.
    - Det andre argumentet angir at funksjonen oppretter en post med standardverdiene for den **Ordredetaljer** enhet med mindre annet er angitt i det tredje argumentet.
    - Det tredje argumentet angir at fire kolonner i den nye posten, inneholder verdier fra brukeren.

      - Den **rekkefølge** kolonnen vil inneholde antall rekkefølgen at brukeren har valgt i galleriet rekkefølge.
      - Den **produktet** kolonnen vil inneholde navnet på produktet som brukeren valgte i kombinasjonsboksen viser produkter.
      - Den **antall** kolonnen vil inneholde verdien som brukeren som er angitt i tekstinndata-boksen.
      - Den **enhetsprisen** kolonnen vil inneholde listeprisen for produktet som brukeren har valgt for denne Ordredetaljer.

    > [!NOTE]
    > Du kan bygge formler som bruker data fra en hvilken som helst kolonne (i den **bestille produkter** enhet) for produktet appbrukeren velger i kombinasjonsboksen som viser produkter. Når brukeren velger en post i den **bestille produkter** enhet, ikke bare, produktnavnet vises i denne kombinasjonsboksen, men også produktets enhetsprisen vises i en etikett. Hver oppslagsverdi i en lerretsapp refererer til en hel post, ikke bare en primærnøkkel.

    Den **Oppdater** funksjonen sikrer at den **ordrer** enhet gjenspeiler posten som du nettopp har lagt til den **Ordredetaljer** enhet. Den **tilbakestille** funksjonen fjernes produkt, antall og enhetsprisen dataene slik at brukeren enklere kan opprette en annen rekkefølge detaljer for samme rekkefølge.

1. Trykk på F5, og velg deretter den **Legg til** ikonet.

    Rekkefølgen gjenspeiler informasjonen du har angitt:

    > [!div class="mx-imgBorder"]
    > ![Animasjon av å legge til en Ordredetaljer](media/northwind-orders-canvas-part3/add-details.gif)

1. (valgfritt) Legg til et annet element i rekkefølgen.

1. Trykk Esc for å lukke forhåndsvisningsmodus.

## <a name="remove-an-order-detail"></a>Fjern en Ordredetaljer

1. Velg en mal for detaljert galleriet i midten av skjermen:

    > [!div class="mx-imgBorder"]
    > ![Velg gallerimal](media/northwind-orders-canvas-part3/remove-details-01.png)

1. På den **Sett inn** fanen og velge **ikoner** > **Papirkurv**:

    > [!div class="mx-imgBorder"]
    > ![Sett inn Papirkurv-ikon](media/northwind-orders-canvas-part3/remove-details-02.png)

    Papirkurv-ikonet vises i hjørnet øverst til venstre i malen galleriet.

    > [!div class="mx-imgBorder"]
    > ![Standardplasseringen for ikon](media/northwind-orders-canvas-part3/remove-details-03.png)

1. Endre størrelse på og flytte på Papirkurv-ikonet til høyre side av malen i detalj galleriet, og angi ikonets **OnSelect** egenskapen til denne formelen:

    ```powerapps-dot
    Remove( 'Order Details', ThisItem ); Refresh( Orders )
    ```

    > [!div class="mx-imgBorder"]
    > ![Angi ikonets OnSelect-egenskapen](media/northwind-orders-canvas-part3/remove-details-04.png)

    Du kan ikke fjerne en post i skrivende stund direkte fra en relasjon, slik at den [ **fjerne** ](functions/function-remove-removeif.md) funksjonen fjerner en post direkte fra den relaterte enheten. **ThisItem** angir posten som du vil fjerne, hentet fra den samme posten i galleriet detalj der papirkurvikonet vises.

    På nytt, operasjonen bruker bufrede data, slik at den **Oppdater** funksjonen informerer de **ordrer** enhet at appen er endret en av sine relaterte enheter.

1. Trykk F5 for å åpne forhåndsvisningsmodus, og velg deretter på Papirkurv-ikonet ved siden av hvert **Ordredetaljer** posten du vil fjerne fra rekkefølgen.

1. Prøv å legge til og fjerne ulike Ordredetaljer fra ordrene dine:

    > [!div class="mx-imgBorder"]
    > ![Animasjon av å legge til og fjerne Ordredetaljer](media/northwind-orders-canvas-part3/remove-details.gif)

## <a name="in-conclusion"></a>I konklusjon

Hvis du vil kort oppsummering, du har lagt til en annen galleriet til å vise detaljer om og kontroller legge til og fjerne en Ordredetaljer i appen. Du brukte disse elementene:

- En annen gallerikontroll, som er koblet til galleriet rekkefølge gjennom en én-til-mange-relasjon: **Gallery2.items** = `Gallery1.Selected.'Order Details'`
- En mange-til-én-relasjon fra den **Ordredetaljer** enheten til den **bestille produkter** enhet: `ThisItem.Product.'Product Name'` og `ThisItem.Product.Picture`
- Den **valg** funksjonen til å få en liste over produkter: `Choices( 'Order Details'.Product' )`
- Den **valgt** egenskapen av en kombinasjonsboks som den fullstendige mange-til-én relatert post: `ComboBox1.Selected.Picture` og `ComboBox1.Selected.'List Price'`
- Den **Patch** funksjonen til å opprette en **Ordredetaljer** post: `Patch( 'Order Details', Defaults( 'Order Details' ), ... )`
- Den **fjerne** funksjonen til å slette en **Ordredetaljer** post: `Remove( 'Order Details', ThisItem )`

Denne serien av emner er en rask gjennomgang av ved hjelp av Common Data Service-relasjoner, og alternativet angir i en lerretsapp for opplærings-formål. Før du slipper en hvilken som helst app til produksjon, bør du vurdere validering, feilhåndtering og mange andre faktorer.
