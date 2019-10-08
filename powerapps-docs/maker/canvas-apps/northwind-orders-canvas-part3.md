---
title: Opprett et detalj galleri i et arbeidsom råde program | Microsoft Docs
description: Opprett et detalj galleri i en lerret-app for å administrere data for Gas tro nor delikat Esser
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 04/25/2019
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 7a975669d1e22289b7152b830808631992389a1f
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/07/2019
ms.locfileid: "71991620"
ms.PowerAppsDecimalTransform: true
---
# <a name="create-a-detail-gallery-in-a-canvas-app"></a>Opprett et detalj galleri i en lerret-app

Følg trinn vise instruksjoner for å opprette et detalj galleri i en lerret-app for å administrere fiktive data i databasen Gas tro nor delikat Esser. Dette emnet er en del av en serie som forklarer hvordan du bygger et forretnings program på relasjonelle data i Common Data Service. Du får best resultat ved å utforske disse emnene i denne rekkefølgen:

1. [Opprett et ordre Galleri](northwind-orders-canvas-part1.md).
1. [Opprett et sammendrags skjema](northwind-orders-canvas-part2.md).
1. Opprett et detalj galleri (**dette emnet**).

> [!div class="mx-imgBorder"]
> @no__t – 0Definition av skjerm områder @ no__t-1

## <a name="prerequisites"></a>Forutsetninger

Før du starter dette emnet, må du installere databasen som beskrevet tidligere i dette emnet. Du må enten opprette ordre galleriet og sammendrags skjemaet eller åpne **Gastronor-ordrer (lerret)-Start del 3-** appen, som allerede inneholder dette galleriet og det skjemaet.

## <a name="create-another-title-bar"></a>Opprett en annen tittel linje

1. Øverst på skjermen velger du [**etikett**](controls/control-text-box.md) -kontrollen som fungerer som tittel linje, kopier den ved å trykke CTRL + C, og deretter lime den inn ved å trykke CTRL-V:

    > [!div class="mx-imgBorder"]
    > ![Copy og lim inn tittel linje @ no__t-1

1. Endre størrelse på og Flytt kopien slik at den vises like under sammendrags skjemaet.

1. Fjern teksten fra kopien på én av følgende måter:

    - Dobbelt klikk på teksten for å merke den, og trykk deretter på Slett.
    - Angi etikettens **tekst** -egenskap til en tom streng ( **""** ).

    > [!div class="mx-imgBorder"]
    > @no__t – 0Remove teksten fra tittel linjen Kopier @ no__t-1

## <a name="add-a-gallery"></a>Å legge til et galleri

1. Sett inn en [**Galleri**](controls/control-gallery.md) -kontroll med et **tomt loddrett** oppsett:

    > [!div class="mx-imgBorder"]
    > @no__t – 0Add et tomt, loddrett Galleri @ no__t-1

    Det nye galleriet, som viser ordre detaljer, vises i hjørnet øverst til venstre:

    > [!div class="mx-imgBorder"]
    > ![Default plassering for Order-detalj Galleri @ no__t-1

1. Lukk **data** -ruten, og endre deretter størrelsen på og Flytt detalj galleriet til hjørnet nederst til høyre, under den nye tittel linjen:

    > [!div class="mx-imgBorder"]
    > ![Final plassering for Order-detalj Galleri @ no__t-1

1. Angi **elementer** -egenskapen for detalj galleriet til denne formelen:

    ```powerapps-comma
    Gallery1.Selected.'Order Details'
    ```

    > [!div class="mx-imgBorder"]
    > @no__t – 0Set elementer-egenskapen for detalj galleriet @ no__t-1

    Hvis det oppstår en feil, må du bekrefte at rekkefølge-galleriet heter **Gallery1** (i **tre visnings** ruten nær den venstre kanten). Hvis dette galleriet har et annet navn, kan du gi det **Gallery1**.

    Du har akkurat koblet de to galleriene. Når brukeren velger en ordre i ordre galleriet, identifiserer dette utvalget en post i **Orders** -enheten. Hvis denne rekkefølgen inneholder ett eller flere linje elementer, knyttes posten i **Orders** -enheten til én eller flere poster i **ordre detaljer** -enheten, og data fra disse postene vises i detalj galleriet. Denne virke måten gjenspeiler én-til-mange-relasjonen som ble opprettet for deg mellom **ordre** -og **ordre detaljer** enheter. Formelen du har angitt, hjelper som relasjon ved hjelp av punktnotasjon:

    > [!div class="mx-imgBorder"]
    > @no__t – 0One-til-mange-relasjon mellom Orders-enheten og ordre detaljer enheten @ no__t-1

## <a name="show-product-names"></a>Vis produkt navn

1. Velg **Legg til et element fra sett inn-fanen** i detalj galleriet, og velg Galleri malen:

    > [!div class="mx-imgBorder"]
    > @no__t – 0Select malen for detalj galleriet @ no__t-1

    Sørg for at du har valgt Galleri malen i stedet for selve galleriet. Bindings boksen må være litt innenfor grense linjen for galleriet og antakelig kortere enn høyden på galleriet. Når du setter inn kontroller i denne malen, gjentas de for hvert element i galleriet.

1. Sett inn en etikett i detalj galleriet på **Sett inn** -fanen.

    Etiketten skal vises i galleriet. Hvis den ikke gjør det, kan du prøve på nytt, men du må velge Galleri malen før du setter inn etiketten.

    > [!div class="mx-imgBorder"]
    > @no__t – 0Add en etikett til detalj galleriet @ no__t-1

1. Angi **tekst** -egenskapen for den nye etiketten til denne formelen:

    ```powerapps-comma
    ThisItem.Product.'Product Name'
    ```

    Hvis det ikke vises noen tekst, velger du pilen for **ordre 0901** nær bunnen av rekkefølge galleriet.

1. Endre størrelsen på etiketten slik at hele teksten vises:

    > [!div class="mx-imgBorder"]
    > @no__t – 0Show produkt navn i ordre detaljer @ no__t-1

    Dette uttrykket leder fra en post i **Order detaljer** -enheten. Posten beholdes i **ThisItem** over til **ordrens produkt** enheter gjennom en mange-til-én-relasjon:

    > [!div class="mx-imgBorder"]
    > @no__t-til-en-relasjon mellom Order detalj-og ordre produkt-enheten @ no__t-1

    Feltet for **produkt navn** (og andre felt som du er i ferd med å bruke), trekkes ut:

    > [!div class="mx-imgBorder"]
    > @no__t – 0Fields i ordre produkt enheter @ no__t-1

## <a name="show-product-images"></a>Vis produkt bilder

1. Sett inn en [**bilde**](controls/control-image.md) -kontroll i detalj galleriet på **Sett inn** -fanen:

    > [!div class="mx-imgBorder"]
    > ![Insert bilde kontroll @ no__t-1

1. Endre størrelse på og Flytt bildet, og etiketten skal være side ved side.

    > [!TIP]
    > Hvis du vil ha fin justert kontroll over størrelsen og plasseringen til en kontroll, kan du begynne å endre størrelsen eller flytte den uten å trykke på Alt-tasten, og deretter fortsette å endre størrelsen på kontrollen mens du holder nede Alt-tasten:

    > [!div class="mx-imgBorder"]
    > ![Move bilde kontroll @ no__t-1

1. Angi bildets **bilde** egenskap til denne formelen:

    ```powerapps-comma
    ThisItem.Product.Picture
    ```

    Uttrykket refererer til et produkt som er knyttet til ordre detaljene, og trekker ut **bilde** feltet som skal vises.

    > [!div class="mx-imgBorder"]
    > produkt bilde for @no__t 0Show @ no__t-1

1. Reduser høyden på galleriets mal slik at mer enn én **ordre detalj** post vises om gangen:

    > [!div class="mx-imgBorder"]
    > @no__t – 0Shorten galleriets mal @ no__t-1

## <a name="show-product-quantity-and-cost"></a>Vis produkt antall og-kostnad

1. Sett inn en annen etikett i detalj galleriet på **Sett inn** -fanen, og endre deretter størrelsen på og Flytt den nye etiketten til høyre for produkt informasjonen.

1. Angi **tekst** -egenskapen for den nye etiketten til dette uttrykket:

    ```powerapps-comma
    ThisItem.Quantity
    ```

    Denne formelen henter informasjon direkte fra enheten **for ordre detaljer** (ingen relasjoner kreves).

    > [!div class="mx-imgBorder"]
    > produkt antall for ![Show @ no__t-1 

1. Endre justeringen for denne kontrollen til **høyre**på **hjem** -fanen:

    > [!div class="mx-imgBorder"]
    > 0Change-justering @ no__t-1 @no__t

1. Sett inn en annen etikett i detalj galleriet på **Sett inn** -fanen, og endre deretter størrelsen på og Flytt etiketten til høyre for antall-etiketten.

1. Angi **tekst** -egenskapen for den nye etiketten til denne formelen:

    ```powerapps-comma
    Text( ThisItem.'Unit Price'; "[$-en-US]$ #,###.00" )
    ```

    Hvis du ikke inkluderer språk koden ( **[$-en-us]** ), blir den lagt til basert på ditt språk og område. Hvis du bruker en annen språk kode, bør du fjerne **$** like etter avsluttende hake parentes ( **]** ), og deretter legge til ditt eget valuta symbol i denne posisjonen.

    > [!div class="mx-imgBorder"]
    > ![Show enhets pris @ no__t-1

1. Endre justeringen for denne kontrollen til **høyre**på **hjem** -fanen:

    > [!div class="mx-imgBorder"]
    > 0Change-justering @ no__t-1 @no__t

1. Sett inn en annen etikett-kontroll i detalj galleriet på **Sett inn** -fanen, og endre deretter størrelsen på og Flytt den nye etiketten til høyre for enhets prisen.

1. Angi **tekst** -egenskapen for den nye etiketten til denne formelen:

    ```powerapps-comma
    Text( ThisItem.Quantity * ThisItem.'Unit Price'; "[$-en-US]$ #,###.00" )
    ```

    Hvis du ikke inkluderer språk koden ( **[$-en-us]** ), vil den bli lagt til basert på ditt språk og område. Hvis koden er forskjellig, bør du bruke ditt eget valuta symbol i stedet for **$** like etter avsluttende hake parentes ( **]** ).

    > [!div class="mx-imgBorder"]
    > @no__t – 0Show utvidet pris @ no__t-1

1. Endre justeringen for denne kontrollen til **høyre**på **hjem** -fanen:

    > [!div class="mx-imgBorder"]
    > 0Change-justering @ no__t-1 @no__t

    Du er ferdig med å legge til kontroller i detalj galleriet for øyeblikket.

1. I ruten med **tre visninger** velger du **Screen1** for å sikre at detalj galleriet ikke lenger er valgt.

## <a name="add-text-to-the-new-title-bar"></a>Legg til tekst på den nye tittel linjen

1. Sett inn en annen etikett på skjermen i **Sett inn** -fanen:

    > [!div class="mx-imgBorder"]
    > etikett for ![Insert @ no__t-1

1. Endre størrelse på og Flytt den nye etiketten over bildene til produktene i den andre tittel linjen, og endre deretter fargen på teksten til hvit på **hjem** -fanen.

1. Dobbelt klikk etikettens tekst, og skriv deretter inn **produkt**:

    > [!div class="mx-imgBorder"]
    > @no__t – 0Change etikett tekst til produkt @ no__t-1

1. Kopier og lim inn produkt etiketten, og endre deretter størrelsen på og Flytt kopien over antall-kolonnen.

1. Dobbelt klikk på teksten til den nye etiketten, og skriv deretter inn **antall**:

    > [!div class="mx-imgBorder"]
    > @no__t 0Change etikett tekst til antall @ no__t-1

1. Kopier og lim inn antall-etiketten, og endre deretter størrelsen på og Flytt kopien over kolonnen for enhets pris.

1. Dobbelt klikk på teksten til den nye etiketten, og skriv deretter inn **enhets pris**:

    > [!div class="mx-imgBorder"]
    > @no__t 0Change etikett tekst til enhets pris @ no__t-1

1. Kopier og lim inn enhets pris etiketten, og endre deretter størrelsen på og Flytt kopien over kolonnen med utvidet pris.

1. Dobbelt klikk på teksten til den nye etiketten, og skriv deretter inn **utvidet**:

    > [!div class="mx-imgBorder"]
    > @no__t 0Change etikett tekst til utvidet @ no__t-1

## <a name="display-order-totals"></a>Vis ordre total Summer

1. Reduser høyden på detalj galleriet for å gjøre plass for ordre summene nederst på skjermen:

    > [!div class="mx-imgBorder"]
    > ![Shorten Order – detalj Galleri @ no__t-1

1. Kopier og lim inn tittel linjen midt på skjermen, og flytt deretter kopien til bunnen av skjermen:

    > [!div class="mx-imgBorder"]
    > tittel linje for ![Copy, og Flytt kopi til nedre kant @ no__t-1

1. Kopier og lim inn produkt etiketten fra den midtre tittel linjen, og flytt deretter kopien til den nederste tittel linjen, rett til venstre for **antall** -kolonnen.

1. Dobbelt klikk på teksten til den nye etiketten, og skriv deretter inn teksten:<br>**Bestillings totalt:**

    > [!div class="mx-imgBorder"]
    > ![Add etikett for ordre Totals @ no__t-1

1. Kopier og lim inn etiketten Order-total etikett, og endre deretter størrelsen og Flytt kopien til høyre for etiketten for ordre-total.

1. Angi **tekst** -egenskapen for den nye etiketten til denne formelen:

    ```powerapps-comma
    Sum( Gallery1.Selected.'Order Details'; Quantity )
    ```

    Denne formelen viser en delegerings advarsel, men du kan ignorere den, fordi ingen enkelt rekkefølge vil inneholde mer enn 500 produkter.

1. På **hjem** -fanen angir du den nye etikettens tekst justering til **høyre**:

    > [!div class="mx-imgBorder"]
    > 0Change-justering @ no__t-1 @no__t

1. Kopier og lim inn denne etikett-kontrollen, og endre deretter størrelsen på og Flytt kopien under den **utvidede** kolonnen.

1. Angi kopiens **tekst** -egenskap til denne formelen:

    ```powerapps-comma
    Text( Sum( Gallery1.Selected.'Order Details'; Quantity * 'Unit Price' ); "[$-en-US]$ #,###.00" )
    ```

    Denne formelen viser en delegerings advarsel, men du kan ignorere den, fordi ingen enkelt rekkefølge vil inneholde mer enn 500 produkter.

    > [!div class="mx-imgBorder"]
    > @no__t – 0Show totale kostnaden for Order @ no__t-1

## <a name="add-space-for-new-details"></a>Legg til plass for nye detaljer

Du kan vise data i et hvilket som helst Galleri, men du kan ikke oppdatere dem eller legge til poster. Under detalj galleriet legger du til et område der brukeren kan konfigurere en post i **Order detaljer** -enheten og sette inn denne posten i en rekkefølge.

1. Reduser høyden på detalj galleriet nok til å gjøre plass for et redigerings område med ett element under dette galleriet.

    Her skal du legge til kontroller slik at brukeren kan legge til en ordre detaljer:

    > [!div class="mx-imgBorder"]
    > @no__t – 0Shorten detalj galleriet @ no__t-1

1. Sett inn en etikett på **Sett inn** -fanen, og endre deretter størrelsen og Flytt den under detalj galleriet.

    > [!div class="mx-imgBorder"]
    > @no__t – 0Insert en etikett @ no__t-1

1. Dobbelt klikk på teksten til den nye etiketten, og trykk deretter på Slett.

1. Angi **Fyll** fargen for den nye etiketten i **hjem** -fanen til **LightBlue**:

    > [!div class="mx-imgBorder"]
    > ![Change etikett er fyll til lys blå @ no__t-1

## <a name="add-the-order-details-data-source"></a>Legg til data kilden for ordre detaljer

1. Velg **data kilder**på **Vis** -fanen, og velg deretter **Legg til data kilde** i **data** -ruten:

    > [!div class="mx-imgBorder"]
    > ![Add data kilde @ no__t-1

1. Velg **Common data service**:

    > [!div class="mx-imgBorder"]
    > ![Select Common Data Service @ no__t-1

1. Skriv inn **rekkefølgen** i søke boksen øverst i **data** -ruten, Merk av for **ordre detaljer** , og velg deretter **Koble** til nederst i ruten:

    > [!div class="mx-imgBorder"]
    > 0Specify ordre detaljer enhet @ no__t-1 @no__t

    Du har nettopp lagt til en annen data kilde i appen:

    > [!div class="mx-imgBorder"]
    > ![List for data kilder @ no__t-1

    Du må legge til denne data kilden fordi appen kan lese gjennom en én-til-mange-relasjon, men appen kan ikke skrive tilbake endringer ennå. Appen må gjøre endringer direkte med den relaterte enheten.

1. Lukk **data** -ruten.

## <a name="select-a-product"></a>Velg et produkt

1. Velg **kontroller** > **kombinasjons boks**på **Sett inn** -fanen:

    > [!div class="mx-imgBorder"]
    > kombinasjons boks for ![Insert @ no__t-1

    [**Kombinasjons boks**](controls/control-combo-box.md) kontrollen vises i hjørnet øverst til venstre.

1. Angi **element** -egenskapen for kombinasjons boksen til denne formelen:

    ```powerapps-comma
    Choices( 'Order Details'.Product )
    ```

    > [!div class="mx-imgBorder"]
    > @no__t – 0Set til kombinasjons boksens elementer @ no__t-1

    [**Choices**](functions/function-choices.md) -funksjonen returnerer en tabell med alle de mulige verdiene for **produkt** -feltet i **Order detaljer** -enheten. Dette feltet er et oppslag i en mange-til-én-relasjon, og derfor returnerer **valg** alle postene i **ordrens produkt** enhet.

    > [!NOTE]
    > Du kan også bruke **valg** med alternativ sett til å returnere en tabell med alle alternativene. Trinnene omtaler ikke denne tilnærmingen, men du brukte den allerede da du la til kombinasjons boksen som viser **ordre status** i sammendrags skjemaet.

1. Åpne den **primære tekst** listen i **data** -ruten, og velg deretter **nwind_productname**. 

1. Åpne **SearchField** -listen, og velg deretter **nwind_productname**.

    Du angir det logiske navnet fordi **data** ruten ikke støtter visnings navn i dette tilfellet ennå:

    > [!div class="mx-imgBorder"]
    > @no__t – 0Set primær teksten for kombinasjons boksen @ no__t-1

1. Lukk **data** -ruten.

1. I **Egenskaper** -fanen nær høyre kant ruller du ned, Deaktiver **Tillat flere valg**og sørg for at **Søk** er aktivert:

    > [!div class="mx-imgBorder"]
    > @no__t – 0Disable flere valg og Aktiver søk @ no__t-1

1. Endre størrelse på og Flytt kombinasjons boksen til det lyse blå området, like under kolonnen produkt navn i detalj galleriet:

    > [!div class="mx-imgBorder"]
    > kombinasjons boks for ![Move @ no__t-1

    I denne kombinasjons boksen vil brukeren angi en post i **produkt** enheten for **ordre detaljer** -posten som appen oppretter.

1. Velg pil ned for kombinasjons boks mens du holder nede Alt.

    > [!TIP]
    > Hvis du holder nede Alt-tasten, kan du samhandle med kontrollene i PowerApps Studio uten å åpne forhånds visnings modus.

1. Velg et produkt i listen over produkter som vises:

    > [!div class="mx-imgBorder"]
    > @no__t – 0Select et produkt i kombinasjons boksen @ no__t-1

## <a name="add-a-product-image"></a>Legg til en produkt avbildning

1. Velg **Media** > **bilde**på **Sett inn** -fanen:

    > [!div class="mx-imgBorder"]
    > ![Insert bilde kontroll @ no__t-1

    [**Bilde**](controls/control-image.md) kontrollen vises i hjørnet øverst til venstre:

    > [!div class="mx-imgBorder"]
    > ![Default plassering av bilde kontroll @ no__t-1

1. Endre størrelse på og Flytt bildet til det lyse blå området under de andre produkt bildene, og ved siden av kombinasjons boksen.

1. Angi **bilde** -egenskapen for bildet til:

    ```powerapps-comma
    ComboBox1.Selected.Picture
    ```

    > [!div class="mx-imgBorder"]
    > ![Set image-egenskapen for bildet @ no__t-1

    Du bruker det samme knepet som du brukte til å vise det ansatte i Sammendrag-skjemaet. Den **valgte** egenskapen for kombinasjons boksen returnerer hele posten for hvilket produkt brukeren velger, inkludert **bilde** -feltet.

## <a name="add-a-quantity-box"></a>Legg til en mengde boks

1. På **Sett inn** -fanen velger du **tekst**@no__t – 2**tekst inn data**:

    > [!div class="mx-imgBorder"]
    > tekst inn data boks for ![Add @ no__t-1

    [**Tekst inn data**](controls/control-text-input.md) -kontrollen vises i hjørnet øverst til venstre:

    > [!div class="mx-imgBorder"]
    > ![Default plassering av tekst inn data boks @ no__t-1

1. Endre størrelse på og Flytt tekst boksen til høyre i kombinasjons boksen, under antall-kolonnen i detalj galleriet:

    > [!div class="mx-imgBorder"]
    > @no__t – 0Resize og Flytt tekst inn data boks @ no__t-1

    Ved å bruke denne tekst boksen, vil brukeren angi **antall** -feltet i **ordre detaljer** -posten.

1. Angi **Default** -egenskapen for denne **kontrollen til:**

    > [!div class="mx-imgBorder"]
    > @no__t – 0Set egenskapen * * default * * for tekst inn data boksen @ no__t-1

1. På **hjem** -fanen kan du angi tekst justering for denne kontrollen til **høyre**:

    > [!div class="mx-imgBorder"]
    > 0Change-justering @ no__t-1 @no__t

## <a name="show-the-unit-and-extended-prices"></a>Vis enheten og de utvidede prisene

1. Sett inn en **etikett** -kontroll på **Sett inn** -fanen.

    Etiketten vises i hjørnet øverst til venstre på skjermen:

    > [!div class="mx-imgBorder"]
    > @no__t – 0Insert en etikett @ no__t-1

1. Endre størrelse på og Flytt etiketten til høyre for tekst inn data-kontrollen, og angi etikettens **tekst** -egenskap til denne formelen:

    ```powerapps-comma
    Text( ComboBox1.Selected.'List Price'; "[$-en-US]$ #,###.00" )
    ```

    > [!div class="mx-imgBorder"]
    > @no__t – 0Set etikettens tekst-egenskap @ no__t-1

    Denne kontrollen viser **liste prisen** fra enheten **for ordre produkter** . Denne verdien bestemmer **enhets pris** -feltet i **ordre detaljer** -posten.

    > [!NOTE]
    > I dette scenarioet er verdien skrivebeskyttet, men andre scenarioer kan være et kall til app-brukeren for å endre den. I så fall kan du bruke en **tekst inn data** -kontroll og angi **standard** -egenskapen til å **vise pris**.

1. På **hjem** -fanen kan du angi tekst justering for listen – pris etiketten til **høyre**:

    > [!div class="mx-imgBorder"]
    > 0Change-justering @ no__t-1 @no__t

1. Kopier og lim inn liste pris etiketten, og endre deretter størrelsen på og Flytt kopien til høyre for etikett-pris-etiketten.

1. Angi **tekst** -egenskapen for den nye etiketten til denne formelen:

    ```powerapps-comma
    Text( Value(TextInput1.Text) * ComboBox1.Selected.'List Price'; "[$-en-US]$ #,###.00" )
    ```

    > [!div class="mx-imgBorder"]
    > @no__t – 0Set den nye etikettens tekst egenskap @ no__t-1

    Denne kontrollen viser den utvidede prisen basert på antallet som app-brukeren har angitt, og liste prisen for produktet som app-brukeren valgte. Det er rent informativt for appens bruker.

1. Dobbelt klikk på tekst inn data-kontrollen for antall, og skriv deretter inn et tall.

    Den **utvidede** pris etiketten beregnes på nytt for å vise den nye verdien:

    > [!div class="mx-imgBorder"]
    > @no__t – 0Specify et antall, og Vis den utvidede prisen @ no__t-1

## <a name="add-an-add-icon"></a>Legg til et Legg til-ikon

1. På **Sett inn** -fanen velger du **ikoner** > **Legg til**:

    > [!div class="mx-imgBorder"]
    > @no__t 0Insert Legg til ikon @ no__t-1

    Ikonet vises øverst til venstre på skjermen.

    > [!div class="mx-imgBorder"]
    > ![Default plassering av Legg til-ikon @ no__t-1

1. Endre størrelse på og Flytt dette ikonet til høyre kant av det lyse blå området, og angi deretter **OnSelect** -egenskapen for ikonet til denne formelen:

    ```powerapps-comma
    Patch( 'Order Details';
        Defaults('Order Details');
        {
            Order: Gallery1.Selected;
            Product: ComboBox1.Selected;
            Quantity: Value(TextInput1.Text);
            'Unit Price': ComboBox1.Selected.'List Price'
        }
    );;
    Refresh( Orders );;
    Reset( ComboBox1 );;
    Reset( TextInput1 )
    ```

    > [!div class="mx-imgBorder"]
    > ![Set ikonets OnSelect-egenskap @ no__t-1

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
    > @no__t – 0Animation for å legge til en ordre detaljer @ no__t-1

1. valg fritt Legg til et annet element i ordren.

1. Trykk på ESC for å lukke forhånds visnings modus.

## <a name="remove-an-order-detail"></a>Fjern en ordre detaljer

1. Velg malen for detalj galleriet midt på skjermen.

    > [!div class="mx-imgBorder"]
    > mal for ![Select for Galleri @ no__t-1

1. På **Sett inn** -fanen velger du **ikoner** > **papir kurv**:

    > [!div class="mx-imgBorder"]
    > ![Insert for kurve @ no__t-1

    Papir kurv ikonet vises øverst til venstre i galleriets mal.

    > [!div class="mx-imgBorder"]
    > ![Default plassering av ikon @ no__t-1

1. Endre størrelse på og Flytt papir kurv ikonet til høyre side av detalj galleriets mal, og angi **OnSelect** -egenskapen for ikonet til denne formelen:

    ```powerapps-comma
    Remove( 'Order Details'; ThisItem );; Refresh( Orders )
    ```

    > [!div class="mx-imgBorder"]
    > ![Set ikonets OnSelect-egenskap @ no__t-1

    Ved denne skriving kan du ikke fjerne en post direkte fra en relasjon, så [**Remove**](functions/function-remove-removeif.md) -funksjonen fjerner en post direkte fra den relaterte enheten. **ThisItem** angir posten som skal fjernes, tatt fra samme post i detalj galleriet der papir kurv ikonet vises.

    Operasjonen bruker hurtigbufrede data på nytt, så **oppdaterings** funksjonen informerer **ordrer** -enheten om at appen har endret én av de relaterte enhetene.

1. Trykk på F5 for å åpne forhånds visnings modus, og velg deretter papir kurv ikonet ved siden av hver **ordre detaljer** -post som du vil fjerne fra bestillingen.

1. Prøv å legge til og fjerne ulike ordre detaljer fra bestillingene dine:

    > [!div class="mx-imgBorder"]
    > @no__t – 0Animation for å legge til og fjerne ordre detaljer @ no__t-1

## <a name="in-conclusion"></a>I konklusjon

Du har lagt til et annet galleri i oppsummering for å vise bestillings detaljer og-kontroller som legger til og fjerner ordre detaljer i appen. Du har brukt disse elementene:

- En annen galleri-kontroll som er koblet til ordre galleriet gjennom en én-til-mange-relasjon: **Gallery2. items** =  @ no__t-2
- En mange-til-én-relasjon fra enheten **for ordre detaljer** til **ordrens produkt** enheter: `ThisItem.Product.'Product Name'` og `ThisItem.Product.Picture`
- **Valg** funksjonen for å hente en liste over produkter: `Choices( 'Order Details'.Product' )`
- Den **valgte** egenskapen for en kombinasjons boks som fullført mange-til-én-relatert post: `ComboBox1.Selected.Picture` og `ComboBox1.Selected.'List Price'`
- **Patch** -funksjonen for å opprette en post **for ordre detaljer** : `Patch( 'Order Details'; Defaults( 'Order Details' ); ... )`
- **Remove** -funksjonen for å slette en post **for ordre detaljer** : `Remove( 'Order Details'; ThisItem )`

Denne serien av emner er en rask gjennomgang av bruk av Common Data Service relasjoner og alternativ sett i en lerret-app for å kunne bruke utdannelse. Før du frigir apper til produksjon, bør du vurdere felt Valide ring, feil håndtering og mange andre faktorer.
