---
title: Opprett et detalj galleri i et arbeidsom råde program | Microsoft Docs
description: Opprett et detalj galleri i en lerret-app for å administrere data for Gas tro nor delikat Esser
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
ms.openlocfilehash: 36fc8c552dea9331ff5ffbaa2dca3bdac5508306
ms.sourcegitcommit: 39b32abb19ad9fae98ca986ded6974bcbbb3cea7
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 07/24/2019
ms.locfileid: "68475430"
---
# <a name="create-a-detail-gallery-in-a-canvas-app"></a>Opprett et detalj galleri i en lerret-app

Følg trinn vise instruksjoner for å opprette et detalj galleri i en lerret-app for å administrere fiktive data i databasen Gas tro nor delikat Esser. Dette emnet er en del av en serie som forklarer hvordan du bygger et forretnings program på relasjonelle data i Common Data Service. Du får best resultat ved å utforske disse emnene i denne rekkefølgen:

1. [Opprett et ordre Galleri](northwind-orders-canvas-part1.md).
1. [Opprett et sammendrags skjema](northwind-orders-canvas-part2.md).
1. Opprett et detalj galleri (**dette emnet**).

> [!div class="mx-imgBorder"]
> ![Definisjon av skjerm områder](media/northwind-orders-canvas-part1/orders-parts.png)

## <a name="prerequisites"></a>Forutsetninger

Før du starter dette emnet, må du installere databasen som beskrevet tidligere i dette emnet. Du må enten opprette ordre galleriet og sammendrags skjemaet eller åpne **Gastronor-ordrer (lerret)-Start del 3-** appen, som allerede inneholder dette galleriet og det skjemaet.

## <a name="create-another-title-bar"></a>Opprett en annen tittel linje

1. Øverst på skjermen velger du [**etikett**](controls/control-text-box.md) -kontrollen som fungerer som tittel linje, kopier den ved å trykke CTRL + C, og deretter lime den inn ved å trykke CTRL-V:

    > [!div class="mx-imgBorder"]
    > ![Kopier og lim inn tittel linje](media/northwind-orders-canvas-part3/details-01.png)

1. Endre størrelse på og Flytt kopien slik at den vises like under sammendrags skjemaet.

1. Fjern teksten fra kopien på én av følgende måter:

    - Dobbelt klikk på teksten for å merke den, og trykk deretter på Slett.
    - Angi etikettens **tekst** -egenskap til en tom streng ( **""** ).

    > [!div class="mx-imgBorder"]
    > ![Fjern teksten fra tittel linjen kopier](media/northwind-orders-canvas-part3/details-02.png)

## <a name="add-a-gallery"></a>Å legge til et galleri

1. Sett inn en [**Galleri**](controls/control-gallery.md) -kontroll med et **tomt loddrett** oppsett:

    > [!div class="mx-imgBorder"]
    > ![Legg til et tomt loddrett galleri](media/northwind-orders-canvas-part3/details-03.png)

    Det nye galleriet, som viser ordre detaljer, vises i hjørnet øverst til venstre:

    > [!div class="mx-imgBorder"]
    > ![Standard plassering for Galleri for bestillings detaljer](media/northwind-orders-canvas-part3/details-04.png)

1. Lukk **data** -ruten, og endre deretter størrelsen på og Flytt detalj galleriet til hjørnet nederst til høyre, under den nye tittel linjen:

    > [!div class="mx-imgBorder"]
    > ![Endelig plassering av ordre detaljer galleri](media/northwind-orders-canvas-part3/details-05.png)

1. Angi **elementer** -egenskapen for detalj galleriet til denne formelen:

    ```powerapps-dot
    Gallery1.Selected.'Order Details'
    ```

    > [!div class="mx-imgBorder"]
    > ![Angi elementer-egenskapen for detalj galleriet](media/northwind-orders-canvas-part3/details-06.png)

    Hvis det oppstår en feil, må du bekrefte at rekkefølge-galleriet heter **Gallery1** (i **tre visnings** ruten nær den venstre kanten). Hvis dette galleriet har et annet navn, kan du gi det **Gallery1**.

    Du har akkurat koblet de to galleriene. Når brukeren velger en ordre i ordre galleriet, identifiserer dette utvalget en post i Orders- enheten. Hvis denne rekkefølgen inneholder ett eller flere linje elementer, knyttes posten i **Orders** -enheten til én eller flere poster i **ordre detaljer** -enheten, og data fra disse postene vises i detalj galleriet. Denne virke måten gjenspeiler én-til-mange-relasjonen som ble opprettet for deg mellom **ordre** -og **ordre detaljer** enheter. Formelen du har angitt, hjelper som relasjon ved hjelp av punktnotasjon:

    > [!div class="mx-imgBorder"]
    > ![Én-til-mange-relasjon mellom Orders-enheten og ordre detaljer enheten](media/northwind-orders-canvas-part3/schema-orders-rel.png)

## <a name="show-product-names"></a>Vis produkt navn

1. Velg **Legg til et element fra sett inn-fanen** i detalj galleriet, og velg Galleri malen:

    > [!div class="mx-imgBorder"]
    > ![Velg malen for detalj galleriet](media/northwind-orders-canvas-part3/details-07.png)

    Sørg for at du har valgt Galleri malen i stedet for selve galleriet. Bindings boksen må være litt innenfor grense linjen for galleriet og antakelig kortere enn høyden på galleriet. Når du setter inn kontroller i denne malen, gjentas de for hvert element i galleriet.

1. Sett inn en etikett i detalj galleriet på **Sett inn** -fanen.

    Etiketten skal vises i galleriet. Hvis den ikke gjør det, kan du prøve på nytt, men du må velge Galleri malen før du setter inn etiketten.

    > [!div class="mx-imgBorder"]
    > ![Å legge til en etikett i detalj galleriet](media/northwind-orders-canvas-part3/details-08.png)

1. Angi **tekst** -egenskapen for den nye etiketten til denne formelen:

    ```powerapps-dot
    ThisItem.Product.'Product Name'
    ```

    Hvis det ikke vises noen tekst, velger du pilen for **ordre 0901** nær bunnen av rekkefølge galleriet.

1. Endre størrelsen på etiketten slik at hele teksten vises:

    > [!div class="mx-imgBorder"]
    > ![Vis produkt navn i ordre detaljer](media/northwind-orders-canvas-part3/details-09.png)

    Dette uttrykket leder fra en post i **Order detaljer** -enheten. Posten beholdes i **ThisItem** over til **ordrens produkt** enheter gjennom en mange-til-én-relasjon:

    > [!div class="mx-imgBorder"]
    > ![Mange-til-én-relasjon mellom ordre detaljer enheten og ordre produkt enheten](media/northwind-orders-canvas-part3/schema-orderdetails-rel.png)

    Feltet for **produkt navn** (og andre felt som du er i ferd med å bruke), trekkes ut:

    > [!div class="mx-imgBorder"]
    > ![Felt i ordrens produkt enhet](media/northwind-orders-canvas-part3/schema-products-fields.png)

## <a name="show-product-images"></a>Vis produkt bilder

1. Sett inn en [**bilde**](controls/control-image.md) -kontroll i detalj galleriet på **Sett inn** -fanen:

    > [!div class="mx-imgBorder"]
    > ![Sett inn bilde-kontroll](media/northwind-orders-canvas-part3/details-10.png)

1. Endre størrelse på og Flytt bildet, og etiketten skal være side ved side.

    > [!TIP]
    > Hvis du vil ha fin justert kontroll over størrelsen og plasseringen til en kontroll, kan du begynne å endre størrelsen eller flytte den uten å trykke på Alt-tasten, og deretter fortsette å endre størrelsen på kontrollen mens du holder nede Alt-tasten:

    > [!div class="mx-imgBorder"]
    > ![Flytt bilde-kontroll](media/northwind-orders-canvas-part3/details-11.png)

1. Angi bildets **bilde** egenskap til denne formelen:

    ```powerapps-dot
    ThisItem.Product.Picture
    ```

    Uttrykket refererer til et produkt som er knyttet til ordre detaljene, og trekker ut **bilde** feltet som skal vises.

    > [!div class="mx-imgBorder"]
    > ![Vis produkt bilde](media/northwind-orders-canvas-part3/details-12.png)

1. Reduser høyden på galleriets mal slik at mer enn én **ordre detalj** post vises om gangen:

    > [!div class="mx-imgBorder"]
    > ![Forkort malen for galleriet](media/northwind-orders-canvas-part3/details-13.png)

## <a name="show-product-quantity-and-cost"></a>Vis produkt antall og-kostnad

1. Sett inn en annen etikett i detalj galleriet på **Sett inn** -fanen, og endre deretter størrelsen på og Flytt den nye etiketten til høyre for produkt informasjonen.

1. Angi **tekst** -egenskapen for den nye etiketten til dette uttrykket:

    ```powerapps-dot
    ThisItem.Quantity
    ```

    Denne formelen henter informasjon direkte fra enheten **for ordre detaljer** (ingen relasjoner kreves).

    > [!div class="mx-imgBorder"]
    > ![Vis produkt antall](media/northwind-orders-canvas-part3/details-13b.png) 

1. Endre justeringen for denne kontrollen til **høyre**på **hjem** -fanen:

    > [!div class="mx-imgBorder"]
    > ![Endre justering](media/northwind-orders-canvas-part3/details-14.png)

1. Sett inn en annen etikett i detalj galleriet på **Sett inn** -fanen, og endre deretter størrelsen på og Flytt etiketten til høyre for antall-etiketten.

1. Angi **tekst** -egenskapen for den nye etiketten til denne formelen:

    ```powerapps-dot
    Text( ThisItem.'Unit Price', "[$-en-US]$ #,###.00" )
    ```

    Hvis du ikke inkluderer språk koden ( **[$-en-us]** ), blir den lagt til basert på ditt språk og område. Hvis du bruker en annen språk kode, bør du fjerne det **$** like etter den avsluttende hake parentesen ( **]** ), og deretter legge til ditt eget valuta symbol i denne posisjonen.

    > [!div class="mx-imgBorder"]
    > ![Vis enhets pris](media/northwind-orders-canvas-part3/details-15.png)

1. Endre justeringen for denne kontrollen til **høyre**på **hjem** -fanen:

    > [!div class="mx-imgBorder"]
    > ![Endre justering](media/northwind-orders-canvas-part3/details-16.png)

1. Sett inn en annen etikett-kontroll i detalj galleriet på **Sett inn** -fanen, og endre deretter størrelsen på og Flytt den nye etiketten til høyre for enhets prisen.

1. Angi **tekst** -egenskapen for den nye etiketten til denne formelen:

    ```powerapps-dot
    Text( ThisItem.Quantity * ThisItem.'Unit Price', "[$-en-US]$ #,###.00" )
    ```

    Hvis du ikke inkluderer språk koden ( **[$-en-us]** ), vil den bli lagt til basert på ditt språk og område. Hvis koden er forskjellig, bør du bruke ditt eget valuta symbol i stedet for det **$** like etter det avsluttende hake parenteset ( **]** ).

    > [!div class="mx-imgBorder"]
    > ![Vis utvidet pris](media/northwind-orders-canvas-part3/details-17.png)

1. Endre justeringen for denne kontrollen til **høyre**på **hjem** -fanen:

    > [!div class="mx-imgBorder"]
    > ![Endre justering](media/northwind-orders-canvas-part3/details-18.png)

    Du er ferdig med å legge til kontroller i detalj galleriet for øyeblikket.

1. I ruten med **tre visninger** velger du **Screen1** for å sikre at detalj galleriet ikke lenger er valgt.

## <a name="add-text-to-the-new-title-bar"></a>Legg til tekst på den nye tittel linjen

1. Sett inn en annen etikett på skjermen i **Sett inn** -fanen:

    > [!div class="mx-imgBorder"]
    > ![Sett inn etikett](media/northwind-orders-canvas-part3/details-19.png)

1. Endre størrelse på og Flytt den nye etiketten over bildene til produktene i den andre tittel linjen, og endre deretter fargen på teksten til hvit på **hjem** -fanen.

1. Dobbelt klikk etikettens tekst, og skriv deretter inn **produkt**:

    > [!div class="mx-imgBorder"]
    > ![Endre etiketteksten til produkt](media/northwind-orders-canvas-part3/details-20.png)

1. Kopier og lim inn produkt etiketten, og endre deretter størrelsen på og Flytt kopien over antall-kolonnen.

1. Dobbelt klikk på teksten til den nye etiketten, og skriv deretter inn **antall**:

    > [!div class="mx-imgBorder"]
    > ![Endre etikettekst til antall](media/northwind-orders-canvas-part3/details-21.png)

1. Kopier og lim inn antall-etiketten, og endre deretter størrelsen på og Flytt kopien over kolonnen for enhets pris.

1. Dobbelt klikk på teksten til den nye etiketten, og skriv deretter inn **enhets pris**:

    > [!div class="mx-imgBorder"]
    > ![Endre etikett tekst til enhets pris](media/northwind-orders-canvas-part3/details-22.png)

1. Kopier og lim inn enhets pris etiketten, og endre deretter størrelsen på og Flytt kopien over kolonnen med utvidet pris.

1. Dobbelt klikk på teksten til den nye etiketten, og skriv deretter inn **utvidet**:

    > [!div class="mx-imgBorder"]
    > ![Endre etiketteksten til utvidet](media/northwind-orders-canvas-part3/details-23.png)

## <a name="display-order-totals"></a>Vis ordre total Summer

1. Reduser høyden på detalj galleriet for å gjøre plass for ordre summene nederst på skjermen:

    > [!div class="mx-imgBorder"]
    > ![Kort rekkefølge – detalj galleri](media/northwind-orders-canvas-part3/sum-01.png)

1. Kopier og lim inn tittel linjen midt på skjermen, og flytt deretter kopien til bunnen av skjermen:

    > [!div class="mx-imgBorder"]
    > ![Kopier tittel linje, og Flytt kopi til nedre kant](media/northwind-orders-canvas-part3/sum-02.png)

1. Kopier og lim inn produkt etiketten fra den midtre tittel linjen, og flytt deretter kopien til den nederste tittel linjen, rett til venstre for **antall** -kolonnen.

1. Dobbelt klikk på teksten til den nye etiketten, og skriv deretter inn teksten:<br>**Bestillings totalt:**

    > [!div class="mx-imgBorder"]
    > ![Legg til etikett for bestillings Summer](media/northwind-orders-canvas-part3/sum-03.png)

1. Kopier og lim inn etiketten Order-total etikett, og endre deretter størrelsen og Flytt kopien til høyre for etiketten for ordre-total.

1. Angi **tekst** -egenskapen for den nye etiketten til denne formelen:

    ```powerapps-dot
    Sum( Gallery1.Selected.'Order Details', Quantity )
    ```

    Denne formelen viser en delegerings advarsel, men du kan ignorere den, fordi ingen enkelt rekkefølge vil inneholde mer enn 500 produkter.

1. På **hjem** -fanen angir du den nye etikettens tekst justering til **høyre**:

    > [!div class="mx-imgBorder"]
    > ![Endre justering](media/northwind-orders-canvas-part3/sum-04.png)

1. Kopier og lim inn denne etikett-kontrollen, og endre deretter størrelsen på og Flytt kopien under den **utvidede** kolonnen.

1. Angi kopiens **tekst** -egenskap til denne formelen:

    ```powerapps-dot
    Text( Sum( Gallery1.Selected.'Order Details', Quantity * 'Unit Price' ), "[$-en-US]$ #,###.00" )
    ```

    Denne formelen viser en delegerings advarsel, men du kan ignorere den, fordi ingen enkelt rekkefølge vil inneholde mer enn 500 produkter.

    > [!div class="mx-imgBorder"]
    > ![Vis total kostnad for ordre](media/northwind-orders-canvas-part3/sum-05.png)

## <a name="add-space-for-new-details"></a>Legg til plass for nye detaljer

Du kan vise data i et hvilket som helst Galleri, men du kan ikke oppdatere dem eller legge til poster. Under detalj galleriet legger du til et område der brukeren kan konfigurere en post i **Order detaljer** -enheten og sette inn denne posten i en rekkefølge.

1. Reduser høyden på detalj galleriet nok til å gjøre plass for et redigerings område med ett element under dette galleriet.

    Her skal du legge til kontroller slik at brukeren kan legge til en ordre detaljer:

    > [!div class="mx-imgBorder"]
    > ![Gjør detalj galleriet kortere](media/northwind-orders-canvas-part3/add-details-01.png)

1. Sett inn en etikett på **Sett inn** -fanen, og endre deretter størrelsen og Flytt den under detalj galleriet.

    > [!div class="mx-imgBorder"]
    > ![Sett inn en etikett](media/northwind-orders-canvas-part3/add-details-02.png)

1. Dobbelt klikk på teksten til den nye etiketten, og trykk deretter på Slett.

1. Angi **Fyll** fargen for den nye etiketten i **hjem** -fanen til **LightBlue**:

    > [!div class="mx-imgBorder"]
    > ![Endre etikettens fyll til lys blå](media/northwind-orders-canvas-part3/add-details-03.png)

## <a name="add-the-order-details-data-source"></a>Legg til data kilden for ordre detaljer

1. Velg **data kilder**på **Vis** -fanen, og velg deretter **Legg til data kilde** i **data** -ruten:

    > [!div class="mx-imgBorder"]
    > ![Legg til data kilde](media/northwind-orders-canvas-part3/add-details-04.png)

1. Velg **Common data service**:

    > [!div class="mx-imgBorder"]
    > ![Velg Common Data Service](media/northwind-orders-canvas-part3/add-details-05.png)

1. Skriv inn **rekkefølgen** i søke boksen øverst i **data** -ruten, Merk av for **ordre detaljer** , og velg deretter **Koble** til nederst i ruten:

    > [!div class="mx-imgBorder"]
    > ![Angi enhet for ordre detaljer](media/northwind-orders-canvas-part3/add-details-06.png)

    Du har nettopp lagt til en annen data kilde i appen:

    > [!div class="mx-imgBorder"]
    > ![Liste over data kilder](media/northwind-orders-canvas-part3/add-details-07.png)

    Du må legge til denne data kilden fordi appen kan lese gjennom en én-til-mange-relasjon, men appen kan ikke skrive tilbake endringer ennå. Appen må gjøre endringer direkte med den relaterte enheten.

1. Lukk **data** -ruten.

## <a name="select-a-product"></a>Velg et produkt

1. Velg **Kontroller** > **kombinasjons boks**på **Sett inn** -fanen:

    > [!div class="mx-imgBorder"]
    > ![Sett inn kombinasjons boks](media/northwind-orders-canvas-part3/add-details-08.png)

    [**Kombinasjons boks**](controls/control-combo-box.md) kontrollen vises i hjørnet øverst til venstre.

1. Angi **element** -egenskapen for kombinasjons boksen til denne formelen:

    ```powerapps-dot
    Choices( 'Order Details'.Product )
    ```

    > [!div class="mx-imgBorder"]
    > ![Angi elementer-egenskapen for kombinasjons boksen](media/northwind-orders-canvas-part3/add-details-09.png)

    [**Choices**](functions/function-choices.md) -funksjonen returnerer en tabell med alle de mulige verdiene for **produkt** -feltet i **Order detaljer** -enheten. Dette feltet er et oppslag i en mange-til-én-relasjon, og derfor returnerer **valg** alle postene i **ordrens produkt** enhet.

    > [!NOTE]
    > Du kan også bruke **valg** med alternativ sett til å returnere en tabell med alle alternativene. Trinnene omtaler ikke denne tilnærmingen, men du brukte den allerede da du la til kombinasjons boksen som viser **ordre status** i sammendrags skjemaet.

1. Åpne den **primære tekst** listen i **data** -ruten, og velg deretter **nwind_productname**. 

1. Åpne **SearchField** -listen, og velg deretter **nwind_productname**.

    Du angir det logiske navnet fordi **data** ruten ikke støtter visnings navn i dette tilfellet ennå:

    > [!div class="mx-imgBorder"]
    > ![Angi primær teksten for kombinasjons boksen](media/northwind-orders-canvas-part3/add-details-10.png)

1. Lukk **data** -ruten.

1. I **Egenskaper** -fanen nær høyre kant ruller du ned, Deaktiver **Tillat flere valg**og sørg for at **Søk** er aktivert:

    > [!div class="mx-imgBorder"]
    > ![Deaktiver flere valg og Aktiver søk](media/northwind-orders-canvas-part3/add-details-12.png)

1. Endre størrelse på og Flytt kombinasjons boksen til det lyse blå området, like under kolonnen produkt navn i detalj galleriet:

    > [!div class="mx-imgBorder"]
    > ![Flytt kombinasjons boks](media/northwind-orders-canvas-part3/add-details-13.png)

    I denne kombinasjons boksen vil brukeren angi en post i **produkt** enheten for **ordre detaljer** -posten som appen oppretter.

1. Velg pil ned for kombinasjons boks mens du holder nede Alt.

    > [!TIP]
    > Hvis du holder nede Alt-tasten, kan du samhandle med kontrollene i PowerApps Studio uten å åpne forhånds visnings modus.

1. Velg et produkt i listen over produkter som vises:

    > [!div class="mx-imgBorder"]
    > ![Velg et produkt i kombinasjons boksen](media/northwind-orders-canvas-part3/add-details-14.png)

## <a name="add-a-product-image"></a>Legg til en produkt avbildning

1. Velg **medie** > **bilde**på **Sett inn** -fanen:

    > [!div class="mx-imgBorder"]
    > ![Sett inn bilde-kontroll](media/northwind-orders-canvas-part3/add-details-15.png)

    [**Bilde**](controls/control-image.md) kontrollen vises i hjørnet øverst til venstre:

    > [!div class="mx-imgBorder"]
    > ![Standard plassering for bilde-kontroll](media/northwind-orders-canvas-part3/add-details-16.png)

1. Endre størrelse på og Flytt bildet til det lyse blå området under de andre produkt bildene, og ved siden av kombinasjons boksen.

1. Angi **bilde** -egenskapen for bildet til:

    ```powerapps-dot
    ComboBox1.Selected.Picture
    ```

    > [!div class="mx-imgBorder"]
    > ![Angi bilde-egenskapen for bildet](media/northwind-orders-canvas-part3/add-details-17.png)

    Du bruker det samme knepet som du brukte til å vise det ansatte i Sammendrag-skjemaet. Den **valgte** egenskapen for kombinasjons boksen returnerer hele posten for hvilket produkt brukeren velger, inkludert **bilde** -feltet.

## <a name="add-a-quantity-box"></a>Legg til en mengde boks

1. På **Sett inn** -fanen velger du **tekst** > **tekst inn data**:

    > [!div class="mx-imgBorder"]
    > ![Legg til boks for tekst inn data](media/northwind-orders-canvas-part3/add-details-18.png)

    [**Tekst inn data**](controls/control-text-input.md) -kontrollen vises i hjørnet øverst til venstre:

    > [!div class="mx-imgBorder"]
    > ![Standard plassering for tekst inn data boks](media/northwind-orders-canvas-part3/add-details-19.png)

1. Endre størrelse på og Flytt tekst boksen til høyre i kombinasjons boksen, under antall-kolonnen i detalj galleriet:

    > [!div class="mx-imgBorder"]
    > ![Endre størrelse på og flytte tekst inn data boks](media/northwind-orders-canvas-part3/add-details-20.png)

    Ved å bruke denne tekst boksen, vil brukeren angi **antall** -feltet i **ordre detaljer** -posten.

1. Angi **Default** -egenskapen for denne **kontrollen til:**

    > [!div class="mx-imgBorder"]
    > ![Angi egenskapen * * default * * i tekst inn data-boksen](media/northwind-orders-canvas-part3/add-details-21.png)

1. På **hjem** -fanen kan du angi tekst justering for denne kontrollen til **høyre**:

    > [!div class="mx-imgBorder"]
    > ![Endre justering](media/northwind-orders-canvas-part3/add-details-22.png)

## <a name="show-the-unit-and-extended-prices"></a>Vis enheten og de utvidede prisene

1. Sett inn en **etikett** -kontroll på **Sett inn** -fanen.

    Etiketten vises i hjørnet øverst til venstre på skjermen:

    > [!div class="mx-imgBorder"]
    > ![Sett inn en etikett](media/northwind-orders-canvas-part3/add-details-23.png)

1. Endre størrelse på og Flytt etiketten til høyre for tekst inn data-kontrollen, og angi etikettens **tekst** -egenskap til denne formelen:

    ```powerapps-dot
    Text( ComboBox1.Selected.'List Price', "[$-en-US]$ #,###.00" )
    ```

    > [!div class="mx-imgBorder"]
    > ![Angi etikettens tekst egenskap](media/northwind-orders-canvas-part3/add-details-24.png)

    Denne kontrollen viser **liste prisen** fra enheten **for ordre produkter** . Denne verdien bestemmer enhets **pris** -feltet i **ordre detaljer** -posten.

    > [!NOTE]
    > I dette scenarioet er verdien skrivebeskyttet, men andre scenarioer kan være et kall til app-brukeren for å endre den. I så fall kan du bruke en **tekst inn data** -kontroll og angi **standard** -egenskapen til å **vise pris**.

1. På **hjem** -fanen kan du angi tekst justering for listen – pris etiketten til **høyre**:

    > [!div class="mx-imgBorder"]
    > ![Endre justering](media/northwind-orders-canvas-part3/add-details-25.png)

1. Kopier og lim inn liste pris etiketten, og endre deretter størrelsen på og Flytt kopien til høyre for etikett-pris-etiketten.

1. Angi **tekst** -egenskapen for den nye etiketten til denne formelen:

    ```powerapps-dot
    Text( Value(TextInput1.Text) * ComboBox1.Selected.'List Price', "[$-en-US]$ #,###.00" )
    ```

    > [!div class="mx-imgBorder"]
    > ![Angi tekst egenskapen for den nye etiketten](media/northwind-orders-canvas-part3/add-details-27.png)

    Denne kontrollen viser den utvidede prisen basert på antallet som app-brukeren har angitt, og liste prisen for produktet som app-brukeren valgte. Det er rent informativt for appens bruker.

1. Dobbelt klikk på tekst inn data-kontrollen for antall, og skriv deretter inn et tall.

    Den **utvidede** pris etiketten beregnes på nytt for å vise den nye verdien:

    > [!div class="mx-imgBorder"]
    > ![Angi et antall, og Vis den utvidede prisen](media/northwind-orders-canvas-part3/add-details-28.png)

## <a name="add-an-add-icon"></a>Legg til et Legg til-ikon

1. Velg**Legg til** **ikoner** > på **Sett inn** -fanen:

    > [!div class="mx-imgBorder"]
    > ![Sett inn Legg til-ikon](media/northwind-orders-canvas-part3/add-details-29.png)

    Ikonet vises øverst til venstre på skjermen.

    > [!div class="mx-imgBorder"]
    > ![Standard plassering for Legg til-ikon](media/northwind-orders-canvas-part3/add-details-30.png)

1. Endre størrelse på og Flytt dette ikonet til høyre kant av det lyse blå området, og angi deretter **OnSelect** -egenskapen for ikonet til denne formelen:

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
    > ![Angi OnSelect-egenskapen for ikonet](media/northwind-orders-canvas-part3/add-details-31.png)

    Som regel oppdaterer [**oppdaterings**](functions/function-patch.md) funksjonen og oppretter poster, og de spesifikke argumentene i denne formelen bestemmer de nøyaktige endringene som funksjonen vil gjøre.

    - Det første argumentet angir data kilden (i dette tilfellet **rekkefølgen for ordre detaljer** ) der funksjonen vil oppdatere eller opprette en post.
    - Det andre argumentet angir at funksjonen oppretter en post med standard verdiene for **ordre detaljer** enheten, med mindre annet er angitt i det tredje argumentet.
    - Det tredje argumentet angir at fire kolonner i den nye posten vil inneholde verdier fra brukeren.

      - **Order** -kolonnen vil inneholde nummeret på ordren som brukeren valgte i ordre galleri.
      - **Produkt** -kolonnen inneholder navnet på produktet som brukeren valgte i kombinasjons boksen som viser produkter.
      - **Antall** -kolonnen inneholder verdien som brukeren har angitt i tekst inn data-boksen.
      - **Enhetspris** -kolonnen vil inneholde liste prisen for produktet som brukeren valgte for denne ordre detaljene.

    > [!NOTE]
    > Du kan bygge formler som bruker data fra en hvilken som helst kolonne (i **ordrens produkt** enhet) for hvilket produkt appen bruker velger i kombinasjons boksen som viser produkter. Når brukeren velger en post i **ordre produkt** enheten, vises ikke produkt navnet i kombinasjons boksen, men produktets enhets pris vises i en etikett. Hver oppslags verdi i en lerret-app refererer til en hel post, ikke bare en primær nøkkel.

    **Oppdaterings** funksjonen sikrer at **ordrer** -enheten gjenspeiler posten som du nettopp har lagt til i **ordre detaljer** enheten. **Reset** -funksjonen fjerner produkt-, mengde-og enhets pris data, slik at brukeren enkelt kan opprette flere ordre detaljer for den samme ordren.

1. Trykk på F5, og velg deretter **Legg til** -ikonet.

    Rekkefølgen gjenspeiler informasjonen du har angitt:

    > [!div class="mx-imgBorder"]
    > ![Animasjon av å legge til en ordre detaljer](media/northwind-orders-canvas-part3/add-details.gif)

1. valg fritt Legg til et annet element i ordren.

1. Trykk på ESC for å lukke forhånds visnings modus.

## <a name="remove-an-order-detail"></a>Fjern en ordre detaljer

1. Velg malen for detalj galleriet midt på skjermen.

    > [!div class="mx-imgBorder"]
    > ![Velg Galleri mal](media/northwind-orders-canvas-part3/remove-details-01.png)

1. På **Sett inn** -fanen velger du **ikoner** > **papir kurv**:

    > [!div class="mx-imgBorder"]
    > ![Sett inn papir kurv ikon](media/northwind-orders-canvas-part3/remove-details-02.png)

    Papir kurv ikonet vises øverst til venstre i galleriets mal.

    > [!div class="mx-imgBorder"]
    > ![Standard plassering for ikon](media/northwind-orders-canvas-part3/remove-details-03.png)

1. Endre størrelse på og Flytt papir kurv ikonet til høyre side av detalj galleriets mal, og angi **OnSelect** -egenskapen for ikonet til denne formelen:

    ```powerapps-dot
    Remove( 'Order Details', ThisItem ); Refresh( Orders )
    ```

    > [!div class="mx-imgBorder"]
    > ![Angi OnSelect-egenskapen for ikonet](media/northwind-orders-canvas-part3/remove-details-04.png)

    Ved denne skriving kan du ikke fjerne en post direkte fra en relasjon, så [**Remove**](functions/function-remove-removeif.md) -funksjonen fjerner en post direkte fra den relaterte enheten. **ThisItem** angir posten som skal fjernes, tatt fra samme post i detalj galleriet der papir kurv ikonet vises.

    Operasjonen bruker hurtigbufrede data på nytt, så **oppdaterings** funksjonen informerer **ordrer** -enheten om at appen har endret én av de relaterte enhetene.

1. Trykk på F5 for å åpne forhånds visnings modus, og velg deretter papir kurv ikonet ved siden av hver **ordre detaljer** -post som du vil fjerne fra bestillingen.

1. Prøv å legge til og fjerne ulike ordre detaljer fra bestillingene dine:

    > [!div class="mx-imgBorder"]
    > ![Animasjon av å legge til og fjerne ordre detaljer](media/northwind-orders-canvas-part3/remove-details.gif)

## <a name="in-conclusion"></a>I konklusjon

Du har lagt til et annet galleri i oppsummering for å vise bestillings detaljer og-kontroller som legger til og fjerner ordre detaljer i appen. Du har brukt disse elementene:

- En annen galleri-kontroll som er koblet til ordre galleriet gjennom en én-til-mange-relasjon: **Gallery2. elementer** = `Gallery1.Selected.'Order Details'`
- En mange-til-én-relasjon fra enheten **for ordre detaljer** til **ordrens produkt** enheter `ThisItem.Product.'Product Name'` : og`ThisItem.Product.Picture`
- **Valg** funksjonen for å få en liste over produkter:`Choices( 'Order Details'.Product' )`
- Den **valgte** egenskapen for en kombinasjons boks som fullført mange-til-én-relatert post `ComboBox1.Selected.Picture` : og`ComboBox1.Selected.'List Price'`
- **Patch** -funksjonen for å opprette en post **for ordre detaljer** :`Patch( 'Order Details', Defaults( 'Order Details' ), ... )`
- **Remove** -funksjonen for å slette en post **for ordre detaljer** :`Remove( 'Order Details', ThisItem )`

Denne serien av emner er en rask gjennomgang av bruk av Common Data Service relasjoner og alternativ sett i en lerret-app for å kunne bruke utdannelse. Før du frigir apper til produksjon, bør du vurdere felt Valide ring, feil håndtering og mange andre faktorer.
