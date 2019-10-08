---
title: Opprett et bestillings galleri i en lerret-app | Microsoft Docs
description: Opprett et ordre galleri i en lerret-app for å administrere data for Gas tro nor delikat Esser
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
ms.openlocfilehash: ac6586067105d5f6cd1ce2aab5568450804fe4c6
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/07/2019
ms.locfileid: "71990953"
ms.PowerAppsDecimalTransform: true
---
# <a name="create-an-order-gallery-in-a-canvas-app"></a>Opprett et ordre galleri i en lerret-app

Følg trinn vise instruksjoner for å opprette et ordre galleri i en lerret-app for å administrere fiktive data i databasen Gas tro nor delikat Esser. Dette emnet er en del av en serie som forklarer hvordan du bygger et forretnings program på relasjonelle data i Common Data Service. Du får best resultat ved å utforske disse emnene i denne rekkefølgen:

1. Opprett et ordre galleri (**dette emnet**).
1. [Opprett et sammendrags skjema](northwind-orders-canvas-part2.md).
1. [Opprett et detalj Galleri](northwind-orders-canvas-part3.md).

> [!div class="mx-imgBorder"]
> @no__t – 0Definition av skjerm områder @ no__t-1

## <a name="prerequisites"></a>Forutsetninger

- [Installer databasen Gas tro nor delikat Esser](northwind-install.md).
- Les gjennom [oversikten over lerretet](northwind-orders-canvas-overview.md) for Gas tro nor delikat Esser.

## <a name="create-a-blank-app"></a>Å opprette en tom app

1. [Logg deg på powerapps](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc), og opprett deretter en tom tavle-app.

    > [!div class="mx-imgBorder"]
    > ![Canvas app fra en tom flis @ no__t-1

1. Gi appen et navn som du liker, og velg deretter **Opprett**.

    > [!div class="mx-imgBorder"]
    > ![Canvas app fra Tom dialog boks @ no__t-1

    PowerApps Studio åpnes, slik at du kan legge til data kilder og kontroller i appen:

    > [!div class="mx-imgBorder"]
    > ![PowerApps Studio @ no__t-1

1. Aktiver en [eksperimentell funksjon](working-with-experimental.md) for å vise resultatet av en formel direkte fra formel linjen.

    1. Velg **App-innstillinger**på **fil** -menyen, og velg deretter **Avanserte innstillinger**.
    1. Rull til bunnen av listen over funksjoner, og Aktiver deretter **resultat visningen Aktiver formel linjen**:

        > [!div class="mx-imgBorder"]
        > @no__t – 0List av eksperimentelle funksjoner @ no__t-1

1. Velg tilbake-pilen i hjørnet øverst til venstre for å gå tilbake til det tomme lerretet.

## <a name="add-the-data"></a>Legg til dataene

1. Velg **data kilder**på **Vis** -fanen, og velg deretter **Legg til data kilde** i **data** -ruten:

    > [!div class="mx-imgBorder"]
    > ![Select visning, data kilder, Legg til data kilde @ no__t-1

1. Velg **Common data service**.

    Hvis **Common data service** ikke vises i listen over tilkoblinger, velger du **ny tilkobling**, og deretter legger du den til.

    > [!div class="mx-imgBorder"]
    > @no__t – 0List av tilkoblinger @ no__t-1

1. Under **Velg en enhet**, Skriv inn **bestillinger**, Merk av for **ordrer** -boksen, og velg deretter **Koble til**:

    > [!div class="mx-imgBorder"]
    > @no__t – 0List av enheter @ no__t-1

    Du har lagt til **ordre** data kilden i appen:

    > [!div class="mx-imgBorder"]
    > @no__t 0Data-rute @ no__t-1

    **Ordrer** -enheten inneholder mange felt av ulike typer:

    > [!div class="mx-imgBorder"]
    > ![List for felt i Orders-enheten @ no__t-1

    Hvert felt har et **visnings navn** og et **navn**, som noen ganger kalles det logiske navnet. Begge navnene refererer til samme element. Generelt sett bruker du visnings navnet når du bygger en app, men noen tilfeller krever det mer Cryptic **navn**, som angitt i en prosedyre.

1. Lukk **data** -ruten i PowerApps Studio ved å velge Lukk-ikonet (x) i hjørnet øverst til høyre.

## <a name="create-the-order-gallery"></a>Opprette ordre galleriet

1. Velg **galleri** > **tomme loddrett** i **Sett inn** -fanen for å legge til en [**Galleri**](controls/control-gallery.md) -kontroll, som vil vise ordrene.

    > [!div class="mx-imgBorder"]
    > ![Insert, Galleri, tom loddrett @ no__t-1

1. Angi **element** -egenskapen for galleriet til denne formelen i formel linjen:

    ```powerapps-comma
    Sort( Orders; 'Order Number'; Descending )
    ```

    [**Sorterings**](functions/function-sort.md) funksjonen bestiller listen slik at den nyeste ordren (som har det høyeste ordre nummeret) vises først.

    > [!div class="mx-imgBorder"]
    > 0Set Items-egenskapen for galleriet @ no__t-1 @no__t

1. Åpne **Oppsett** -listen i **Egenskaper** -fanen nær høyre kant:

    > [!div class="mx-imgBorder"]
    > @no__t – 0List av alternativer for oppsett @ no__t-1

1. Velg **Tittel og under tittel**i listen over alternativer:

    > [!div class="mx-imgBorder"]
    > @no__t – 0Select et oppsett @ no__t-1

    To [**etikett**](controls/control-text-box.md) kontroller legges til i malen for galleriet. Som standard viser disse kontrollene to kolonner i **Orders** -enheten, som du vil endre neste. Malen til galleriet er rep lik ert loddrett for hver post i enheten.

1. Hvis du har lukket **data** -ruten, velger du **Rediger** (ved siden av **felt**) i **Egenskaper** -fanen nær høyre kant.

1. I **data** -ruten velger du **Title1** (eller velger den øvre etiketten i malen for galleriet).

1. Angi etikettens **tekst** -egenskap i formel linjen til dette uttrykket:

    ```powerapps-comma
    "Order " & ThisItem.'Order Number'
    ```

    > [!div class="mx-imgBorder"]
    > tittel etikett for ![Set, tekst egenskap @ no__t-1

    Ordre nummeret vises øverst i hvert Galleri element. I Galleri malen gir **ThisItem** tilgang til alle feltene i **Order** -enheten.

1. I **data** -ruten velger du **Subtitle1** (eller velger den nedre etiketten i Galleri malen):

    > [!div class="mx-imgBorder"]
    > etikett for ![Select under tittel @ no__t-1

1. Angi etikettens **tekst** -egenskap i formel linjen til dette uttrykket:

    ```powerapps-comma
    ThisItem.Customer.Company
    ```

    > [!div class="mx-imgBorder"]
    > ![Set under tittel etikett tekst egenskap @ no__t-1

    Når du har angitt denne formelen, kan det vise en rød bølge feil i et øyeblikk. Feilen bør tømmes hvis du velger hva som helst utenfor formel linjen, og deretter returnerer markøren til formel linjen. Hvis feilen vedvarer, eller hvis du ikke ser en verdi, velger du **Vis** -fanen, velger **data kilder**, og deretter oppdaterer du **Orders** -enheten ved å velge ellipsen (...) til høyre for data kilde navnet.

    Når du angir **ThisItem. Customer**, vil du bruke en mange-til-én-relasjon mellom **ordrene** og **kunde enhetene og** hente kunde posten som er knyttet til hver ordre. Fra kunde oppføringen trekker du ut data i **firma** -kolonnen for visning.

    Du kan vise alle relasjonene fra **ordrer** -enheten til andre enheter, inkludert **kunde** enheten:

    > [!div class="mx-imgBorder"]
    > @no__t – 0List av relasjoner @ no__t-1

1. Lukk **data** -ruten ved å velge Lukk-ikonet (x) i øvre høyre hjørne.

## <a name="show-each-orders-status"></a>Vis status for hver ordre

I denne prosedyren vil du legge til plass i galleriet for en etikett og konfigurere den til å vise hver ordre status i en annen farge basert på dataene.

1. Reduser bredden på den første etiketten i galleriets mal, **Title1**:

    > [!div class="mx-imgBorder"]
    > ![Title1 i galleriets mal @ no__t-1

1. Gjenta det forrige trinnet med den andre etiketten, **Subtitle1**:

    > [!div class="mx-imgBorder"]
    > ![Subtitle1 i galleriets mal @ no__t-1

1. Hvis du har valgt Galleri malen (eller en kontroll i malen), velger du **etikett** på **Sett inn** -fanen:

    > [!div class="mx-imgBorder"]
    > @no__t – 0Add en etikett @ no__t-1

1. Flytt den nye etiketten til høyre for **Title1** -etiketten:

    > [!div class="mx-imgBorder"]
    > @no__t – 0Move og endre størrelsen på en etikett @ no__t-1

1. Angi **tekst** -egenskapen for den nye etiketten til dette uttrykket:

    ```powerapps-comma
    ThisItem.'Order Status'
    ```

    > [!div class="mx-imgBorder"]
    > @no__t – 0Set tekst-egenskapen @ no__t-1

    I **Orders** -enheten inneholder **ordre status** -feltet en verdi fra alternativ settet **ordre status** . Et alternativ sett ligner på en opplisting i andre programmerings verktøy. Hvert sett med alternativer er definert i databasen, slik at brukere bare kan angi de alternativene som er i settet. Alternativ settet **ordre status** er også globalt, ikke lokal, slik at du kan bruke det i andre enheter:

    > [!div class="mx-imgBorder"]
    > ![Orders status alternativ sett @ no__t-1

    Hvert alternativ i et sett har et navn som vises hvis du viser det i en etikett. Disse navnene kan lokaliseres, og appen gjenkjenner det samme alternativet, enten en engelsk bruker velger **Apple**, en fransk bruker velger **Pomme**, eller en spansk bruker velger **Manzana**. På grunn av dette kan du ikke opprette en formel som er avhengig av en hardkodet streng for et alternativ, da dette emnet demonstrerer senere.

    I formler må du omgi **bestillings status** med enkle anførsels tegn fordi den inneholder et mellomrom. Dette navnet fungerer imidlertid på samme måte som andre navn i PowerApps, for eksempel **kunde** eller **firma**.

1. På **hjem** -fanen øker du skrift størrelsen på status etiketten til 20 punkter, og høyre justerer teksten:

    > [!div class="mx-imgBorder"]
    > @no__t – 0Change skrift størrelse og-justering @ no__t-1

1. Angi **farge** -egenskapen for status etiketten til denne formelen i formel linjen:

    ```powerapps-comma
    Switch( ThisItem.'Order Status';
        'Orders Status'.Closed; Green;
        'Orders Status'.New; Black;
        'Orders Status'.Invoiced; Blue;
        'Orders Status'.Shipped; Purple
    )
    ```

    > [!div class="mx-imgBorder"]
    > @no__t – 0Set farge-egenskapen for status etiketten @ no__t-1

    PowerApps hindrer deg i å opprette en formel som er avhengig av en hardkodet streng for hvert alternativ i et sett fordi slike formler kan gi upassende resultater hvis alternativ navnene er lokalisert. I stedet bestemmer **Switch** -funksjonen fargen basert på en streng som vises i etiketten basert på brukerens innstillinger.

    Med denne formelen på plass vises forskjellige status verdier i forskjellige farger, som den forrige grafikken viser.

## <a name="display-each-orders-total"></a>Vis totalen for hver ordre

1. Velg det første elementet i galleriet, som er malen for galleriet:

    > [!div class="mx-imgBorder"]
    > @no__t – 0Select Galleri malen @ no__t-1

1. Velg **etikett** på **Sett inn** -fanen for å legge til en ny etikett:

    > [!div class="mx-imgBorder"]
    > @no__t – 0Add en etikett @ no__t-1

1. Flytt den nye etiketten slik at den vises under status etiketten:

    > [!div class="mx-imgBorder"]
    > @no__t – 0Resize og Flytt den nye etiketten @ no__t-1

1. Angi **tekst** -egenskapen for ny etikett i formel linjen:

    ```powerapps-comma
    Text( Sum( ThisItem.'Order Details'; Quantity * 'Unit Price' ); "[$-en-US]$ #,###.00" )
    ```

    > [!div class="mx-imgBorder"]
    > @no__t – 0Formula for beregning av en ordres totale kostnader @ no__t-1

    I denne formelen legger [**Sum**](functions/function-aggregates.md) -funksjonen inn postene i **ordre detaljer** -enheten som er knyttet til hver post i **Order** -enheten gjennom en én-til-mange-relasjon. Disse linje elementene utgjør hver ordre, og du bruker den samme én-til-mange-relasjonen til å vise og redigere linje elementene nederst til høyre på skjermen.

    Denne formelen viser en blå understreking og en [delegerings advarsel](delegation-overview.md) fordi Common data service ikke støtter delegering av komplekse aggregat funksjoner (for eksempel summen av en multiplikasjon). Du kan ignorere denne informasjonen, fordi ingen rekkefølge i dette eksemplet vil inneholde mer enn 500 linje elementer. Hvis det er nødvendig for en annen app, kan du øke grensen i **App-innstillinger**.

    [**Tekst**](functions/function-text.md) -funksjonen i denne formelen legger til et valuta symbol og formaterer resultatet med tusener og desimal skille tegn. Som skrevet, inneholder formelen språk koden for USA Engelsk ( **[$-en-us]** ) og et dollar symbol ( **$** ). Hvis du fjerner språk koden, erstattes den med en basert på språk innstillingene dine, og etiketten vil vise de riktige formatene for den koden. Hvis du lar dollar-symbolet være, viser etiketten riktig valuta symbol basert på brukerens innstillinger. Du kan imidlertid tvinge et annet symbol til å vises ved å erstatte dollar symbolet med det du foretrekker.

1. Endre skrift størrelsen på den nyeste etiketten til 20 punkt på **hjem** -fanen, og høyre justert teksten:

    > [!div class="mx-imgBorder"]
    > @no__t – 0Change skrift størrelsen og justeringen av etiketten @ no__t-1

1. Flytt galleriet til venstre kant av skjermen, og Reduser bredden på galleriet for å lukke litt plass.

1. Øk høyden på galleriet slik at det er nesten like høyt som skjermen, men la det stå litt plass øverst i en tittel linje, som du legger til ved begynnelsen av neste emne:

    > [!div class="mx-imgBorder"]
    > @no__t – 0Move og endre størrelsen på galleriet @ no__t-1

## <a name="summary"></a>Oversikt

For å oppsummering, begynte du å bygge en nett BAS ert nett BAS ert lerrets App ved å legge til ordre galleriet, som inkluderer disse elementene:

- Et uttrykk for å vise ordre nummeret: `"Orders " & ThisItem.OrderNumber`
- Et felt i en mange-til-én-relasjon: `ThisItem.Customer.Company`
- En etikett som viser navnet på et alternativ i et sett: `ThisItem.'Order Status'`
- En etikett som endrer format basert på hvilket alternativ i et sett etiketten viser: `Switch( ThisItem.'Order Status'; 'Orders Status'.Closed; Green; ...`
- En kompleks aggregat funksjon over en én-til-mange-relasjon: `Sum( ThisItem.'Order Details'; Quantity * 'Unit Price' )`

## <a name="next-topic"></a>Neste emne

I neste emne kan du legge til en [**redigerings skjema**](controls/control-form-detail.md) -kontroll for å vise og redigere et sammendrag av hvilken rekkefølge brukeren velger i galleriet du nettopp opprettet.

> [!div class="nextstepaction"]
> [Opprett sammendrags skjemaet](northwind-orders-canvas-part2.md)