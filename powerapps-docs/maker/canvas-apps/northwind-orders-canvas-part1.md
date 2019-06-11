---
title: Opprett en ordre-galleriet i en lerretsapp | Microsoft Docs
description: Opprett en ordre-galleriet i en lerretsapp til å behandle data for Northwind Traders
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
ms.openlocfilehash: 94d6c104cb888bb13f3724231d7891d622f5377b
ms.sourcegitcommit: e85072f7a80da308c4caabe20adbf2509588ca57
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/07/2019
ms.locfileid: "66761009"
ms.PowerAppsDecimalTransform: true
---
# <a name="create-an-order-gallery-in-a-canvas-app"></a>Opprett en ordre-galleriet i en lerretsapp

Følg trinnvise instruksjoner for å opprette en ordre-galleriet i en lerretsapp for administrasjon av fiktive data i databasen Northwind Traders. Dette emnet er en del av en serie som forklarer hvordan du bygger en business-app på relasjonelle data i Common Data Service. Utforsk disse emnene i denne sekvensen for best resultat:

1. Opprett en ordre-galleri (**dette emnet**).
1. [Opprette et sammendrag av skjema](northwind-orders-canvas-part2.md).
1. [Opprett et galleri i detalj](northwind-orders-canvas-part3.md).

> [!div class="mx-imgBorder"]
> ![Definisjonen av skjermen områder](media/northwind-orders-canvas-part1/orders-parts.png)

## <a name="prerequisites"></a>Forutsetninger

- [Installere Northwind Traders database og apper](northwind-install.md).
- Les gjennom den [oversikt over lerretsapp](northwind-orders-canvas-overview.md) for Northwind Traders.

## <a name="create-a-blank-app"></a>Å opprette en tom app

1. [Logg deg på PowerApps](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc), og deretter opprette en tom app for nettbrett.

    > [!div class="mx-imgBorder"]
    > ![Lerretsapp fra tom flis](media/northwind-orders-canvas-part1/start-01.png)

1. Gi appen uansett hvilke et navn du, og velg deretter **Opprett**.

    > [!div class="mx-imgBorder"]
    > ![Lerretsapp fra tom dialogboksen](media/northwind-orders-canvas-part1/start-02.png)

    PowerApps Studio åpner slik at du kan legge til datakilder og kontroller i appen din:

    > [!div class="mx-imgBorder"]
    > ![PowerApps Studio](media/northwind-orders-canvas-part1/start-03.png)

1. Aktiver en [eksperimentell funksjon](working-with-experimental.md) for å vise resultatet av en formel direkte fra formellinjen.

    1. På den **filen** menyen velger **appinnstillinger**, og velg deretter **avanserte innstillinger**.
    1. Bla til bunnen av listen over funksjoner, og deretter aktivere **aktiverer formellinjen resultatvisningen**:

        > [!div class="mx-imgBorder"]
        > ![Liste over eksperimentelle funksjoner](media/northwind-orders-canvas-part1/start-04.png)

1. Velg tilbake-pilen for å gå tilbake til tomt lerret i hjørnet øverst til venstre.

## <a name="add-the-data"></a>Legge til data

1. På den **Vis** fanen og velge **datakilder**, og velg deretter **Legg til datakilde** i den **Data** ruten:

    > [!div class="mx-imgBorder"]
    > ![Velg visning, datakilder, Legg til datakilde](media/northwind-orders-canvas-part1/datasource-01.png)

1. Velg **Common Data Service-** .

    Hvis **Common Data Service-** vises ikke i listen over tilkoblinger, velg **ny tilkobling**, og legg deretter til den.

    > [!div class="mx-imgBorder"]
    > ![Listen over tilkoblinger](media/northwind-orders-canvas-part1/datasource-02.png)

1. Under **Velg en enhet**, typen **ordrer**, og velg den **ordrer** avmerkingsboks, og velg deretter **koble til**:

    > [!div class="mx-imgBorder"]
    > ![Listen over enheter](media/northwind-orders-canvas-part1/datasource-03.png)

    Du har lagt til den **ordrer** datakilde i appen din:

    > [!div class="mx-imgBorder"]
    > ![Data-ruten](media/northwind-orders-canvas-part1/datasource-04.png)

    Den **ordrer** enhet inneholder mange ulike typer felter:

    > [!div class="mx-imgBorder"]
    > ![Liste over felt i ordrer-enhet](media/northwind-orders-canvas-part1/datasource-05.png)

    Hvert felt har en **visningsnavn** og en **navnet**, som kalles noen ganger det logiske navnet. Både navn referere til samme ting. Generelt du bruker visningsnavnet når du bygger en app, men noen tilfeller kreve mer kryptisk **navnet**, som er nevnt i en prosedyre.

1. I PowerApps Studio, kan du lukke den **Data** ruten ved å velge Lukk-ikonet (x) i det øvre høyre hjørnet.

## <a name="create-the-order-gallery"></a>Opprett ordre-galleri

1. På den **Sett inn** fanen og velge **galleriet** > **tomt, loddrett** til å legge til en [ **galleriet** ](controls/control-gallery.md)kontrollen, som viser ordrene.

    > [!div class="mx-imgBorder"]
    > ![INSERT-, galleriet, tom loddrett](media/northwind-orders-canvas-part1/orders-01.png)

1. Angi galleriets i formellinjen, **elementer** egenskapen til denne formelen:

    ```powerapps-comma
    Sort( Orders; 'Order Number'; Descending )
    ```

    Den [ **Sorter** ](functions/function-sort.md) funksjonen bestillinger listen slik at den nyeste rekkefølgen (som har det høyeste bestillingsnummeret) vises først.

    > [!div class="mx-imgBorder"]
    > ![Angi elementer-egenskapen for galleriet](media/northwind-orders-canvas-part1/orders-02.png)

1. I den **Egenskaper** fanen nær høyre kant, åpne det **oppsett** listen:

    > [!div class="mx-imgBorder"]
    > ![Listen over alternativer for oppsett](media/northwind-orders-canvas-part1/orders-03.png)

1. I listen over alternativer, velger du **tittel og undertittel**:

    > [!div class="mx-imgBorder"]
    > ![Velg et oppsett](media/northwind-orders-canvas-part1/orders-04.png)

    To [ **etikett** ](controls/control-text-box.md) kontrollene er lagt til i malen i galleriet. Disse kontrollene viser som standard, to kolonner med den **ordrer** enhet, som du vil endre neste. Malen i galleriet replikeres loddrett for hver post i enheten.

1. Hvis du har lukket den **Data** ruten velger **Rediger** (siden **felt**) i den **Egenskaper** fanen nær høyre kant.

1. I den **Data** ruten velger **Title1** (eller velg den øvre etiketten i malen i galleriet).

1. I formellinjen, kan du angi etikettens **tekst** egenskapen til dette uttrykket:

    ```powerapps-comma
    "Order " & ThisItem.'Order Number'
    ```

    > [!div class="mx-imgBorder"]
    > ![Angi tittel etikettens tekstegenskapen](media/northwind-orders-canvas-part1/orders-06.png)

    Nummeret for vises øverst på hvert gallerielement. I gallerimalen **ThisItem** gir tilgang til alle feltene i den **rekkefølge** enhet.

1. I den **Data** ruten velger **Subtitle1** (eller velg den nederste etiketten i malen i galleriet):

    > [!div class="mx-imgBorder"]
    > ![Velg undertittelen etikett](media/northwind-orders-canvas-part1/orders-07.png)

1. I formellinjen, kan du angi etikettens **tekst** egenskapen til dette uttrykket:

    ```powerapps-comma
    ThisItem.Customer.Company
    ```

    > [!div class="mx-imgBorder"]
    > ![Angi undertittel etikettens tekstegenskapen](media/northwind-orders-canvas-part1/orders-08.png)

    Når du skriver inn denne formelen, kan en rød bølgete feil vise et øyeblikk. Feilen bør fjerne Hvis du velger noe utenfor formellinjen, og gå deretter tilbake markøren til formellinjen. Hvis feilen vedvarer, eller du ikke ser en verdi, velger du den **Vis** fanen og velge **datakilder**, og oppdater deretter den **ordrer** enheten ved å velge ellipsen (...) til den til høyre på datakilde-navnet.

    Når du angir **ThisItem.Customer**, du er å dra nytte av en mange-til-én-relasjon mellom den **ordrer** og **kunder** enheter og henting av kundeposten som er tilknyttet hver ordre. Fra kundeposten, er du trekker ut data i den **firmaet** kolonne for visning.

    Du kan vise alle relasjoner fra den **ordrer** enhet til andre enheter, inkludert den **kunden** enhet:

    > [!div class="mx-imgBorder"]
    > ![Liste over relasjoner](media/northwind-orders-canvas-part1/orders-09.png)

1. Lukk den **Data** ruten ved å velge Lukk-ikonet (x) i det øvre høyre hjørnet.

## <a name="show-each-orders-status"></a>Vis status for hver ordre

I denne prosedyren må du legge til plass i galleriet for en etikett og konfigurerer den for å vise hver ordrestatus i en annen farge basert på dataene.

1. Reduser bredden på den første etiketten, i malen i galleriet, **Title1**:

    > [!div class="mx-imgBorder"]
    > ![Title1 i malen i galleriet](media/northwind-orders-canvas-part1/status-01.png)

1. Gjenta det forrige trinnet med den andre etiketten, **Subtitle1**:

    > [!div class="mx-imgBorder"]
    > ![Subtitle1 i malen i galleriet](media/northwind-orders-canvas-part1/status-02.png)

1. Med galleriet malen (eller en kontroll i malen) valgt, velger du **etikett** på den **Sett inn** fanen:

    > [!div class="mx-imgBorder"]
    > ![Legg til en etikett](media/northwind-orders-canvas-part1/status-03.png)

1. Flytt den nye etiketten til høyre for den **Title1** etikett:

    > [!div class="mx-imgBorder"]
    > ![Flytte og endre størrelse på en etikett](media/northwind-orders-canvas-part1/status-04.png)

1. Angi den **tekst** -egenskapen for den nye etiketten til dette uttrykket:

    ```powerapps-comma
    ThisItem.'Order Status'
    ```

    > [!div class="mx-imgBorder"]
    > ![Angi Text-egenskapen](media/northwind-orders-canvas-part1/status-05.png)

    I den **ordrer** enhet, den **ordrestatus** feltet inneholder en verdi fra den **ordrestatus** alternativsett. Et alternativsett ligner på en opplisting i andre programmeringsverktøy. Hvert sett med alternativer er definert i databasen, slik at brukere kan angi bare disse alternativene som er i settet. Den **ordrestatus** alternativsett er også globale, ikke lokalt, slik at du kan bruke den i andre enheter:

    > [!div class="mx-imgBorder"]
    > ![Bestillinger Status alternativsett](media/northwind-orders-canvas-part1/status-06.png)

    Hvert alternativ i et sett har et navn som vises hvis du vise den i en etikett. Disse navnene kan lokaliseres, og appen gjenkjenner det samme alternativet om en engelske brukeren velger **Apple**, en fransk bruker velger **Pomme**, eller en spansk brukeren velger **Manzana**. Du kan ikke opprette en formel som er avhenger av en streng som hardkodede for et alternativ, derfor som dette emnet beskriver senere.

    I formler, må du omslutte **ordrestatus** med enkle anførselstegn fordi den inneholder et mellomrom. Men dette navnet fungerer på samme måte som alle andre navn i PowerApps, som **kunden** eller **firmaet**, samsvarer.

1. På den **Hjem** fanen, Øk skriftstørrelsen for status etiketten til 20 punkt og Høyrejuster teksten:

    > [!div class="mx-imgBorder"]
    > ![Endre skriftstørrelse og justering](media/northwind-orders-canvas-part1/status-07.png)

1. I formellinjen, kan du angi den **farge** egenskapen for etiketten statusen til denne formelen:

    ```powerapps-comma
    Switch( ThisItem.'Order Status';
        'Orders Status'.Closed; Green;
        'Orders Status'.New; Black;
        'Orders Status'.Invoiced; Blue;
        'Orders Status'.Shipped; Purple
    )
    ```

    > [!div class="mx-imgBorder"]
    > ![Angi farge-egenskapen for etiketten status](media/northwind-orders-canvas-part1/status-08.png)

    PowerApps forhindrer deg fra å opprette en formel som baserer seg på en streng som hardkodede for hvert alternativ i et sett fordi slike formler kan gi upassende resultater hvis alternativnavnene er lokalisert. I stedet den **Switch** funksjonen bestemmer fargen basert på uansett hvilke strengen vises i etiketten basert på brukerens innstillinger.

    Med denne formelen på sted vises forskjellige statusverdier i forskjellige farger, som vist i forrige grafisk.

## <a name="display-each-orders-total"></a>Vise hver ordre totalt

1. Velg det første elementet i galleriet, som er malen i galleriet:

    > [!div class="mx-imgBorder"]
    > ![Velge gallerimalen](media/northwind-orders-canvas-part1/aggregate-01.png)

1. På den **Sett inn** fanen og velge **etikett** å legge til en annen etikett:

    > [!div class="mx-imgBorder"]
    > ![Legg til en etikett](media/northwind-orders-canvas-part1/aggregate-02.png)

1. Flytt den nye etiketten slik at den vises under etiketten status:

    > [!div class="mx-imgBorder"]
    > ![Endre størrelsen på og flytte den nye etiketten](media/northwind-orders-canvas-part1/aggregate-03.png)

1. Angi den nye etiketten i formellinjen, **tekst** egenskapen til denne formelen:

    ```powerapps-comma
    Text( Sum( ThisItem.'Order Details'; Quantity * 'Unit Price' ); "[$-en-US]$ #,###.00" )
    ```

    > [!div class="mx-imgBorder"]
    > ![Formelen for å beregne en ordre totalkostnad](media/northwind-orders-canvas-part1/aggregate-04.png)

    I denne formelen den [ **Sum** ](functions/function-aggregates.md) funksjonen legger sammen postene i den **Ordredetaljer** enhet som er knyttet til hver post i den **rekkefølge**enheten via en én-til-mange-relasjon. Disse linjeelementer utgjør hver ordre, og du vil bruke den samme én-til-mange-relasjonen til å vise og redigere linjeelementene i området nederst til høyre på skjermen.

    Denne formelen viser en blå understreking og en [delegeringsadvarsel](delegation-overview.md) fordi Common Data Service ikke støtter delegering av komplekse mengdefunksjoner (for eksempel summen av en multiplikasjon). Fordi ingen rekkefølge i dette eksemplet vil inneholde mer enn 500 linjeelementer, kan du ignorere denne informasjonen. Hvis nødvendig for en annen app, kan du øke denne grensen i **appinnstillinger**.

    Den [ **tekst** ](functions/function-text.md) funksjon i denne formelen legger til et valutasymbol, og formater resultatet med tusenvis og desimalskilletegn. Slik den er skrevet, inkluderer formelen språkkoden for USA Engelsk ( **[$-en-US]** ) og et symbol dollar ( **$** ). Hvis du fjerner språkkoden, den vil bli erstattet med en basert på språkinnstillingene, og etiketten viser de riktige formatene koden. Hvis du lar dollarsymbolet, viser etiketten rett valutasymbol basert på brukerens innstillinger. Du kan imidlertid tvinge et annet symbol vises ved å erstatte dollarsymbolet med det som du foretrekker.

1. På den **Hjem** fanen, endre størrelsen på den nyeste etiketten til 20 punkt og Høyrejuster teksten:

    > [!div class="mx-imgBorder"]
    > ![Endre skriftstørrelse og justering for en etikett](media/northwind-orders-canvas-part1/aggregate-05.png)

1. Flytt galleriet til venstre kant av skjermen, og Reduser galleriets bredden å lukke Frigjør plass.

1. Øk galleriets høyden slik at den er nesten like høye som skjermen, men la det være litt plass øverst en tittellinje, som du legger ved starten av neste emne:

    > [!div class="mx-imgBorder"]
    > ![Flytt og endre størrelsen på galleriet](media/northwind-orders-canvas-part1/aggregate-06.png)

## <a name="summary"></a>Sammendrag

Hvis du vil kort oppsummering, begynte du å bygge en lerretsapp på én skjerm ved å legge til galleriet rekkefølge, som inkluderer disse elementene:

- Et uttrykk til å vise bestillingsnummeret: `"Orders " & ThisItem.OrderNumber`
- Et felt i en mange-til-én-relasjon: `ThisItem.Customer.Company`
- En etikett som viser navnet på et alternativ i et sett: `ThisItem.'Order Status'`
- En etikett som endrer format basert på hvilket alternativ i et sett etiketten viser: `Switch( ThisItem.'Order Status'; 'Orders Status'.Closed; Green; ...`
- En kompleks mengdefunksjon over en én-til-mange-relasjon: `Sum( ThisItem.'Order Details'; Quantity * 'Unit Price' )`

## <a name="next-topic"></a>Neste emne

I neste emne, skal du legge til en [ **redigeringsskjema** ](controls/control-form-detail.md) kontrollen til visnings- og et sammendrag av rekkefølgen brukeren velger i galleriet som du nettopp opprettet.

> [!div class="nextstepaction"]
> [Opprett sammendrag skjemaet](northwind-orders-canvas-part2.md)