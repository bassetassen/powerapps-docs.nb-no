---
title: Slik fungerer tabeller i lerretsapper | Microsoft Docs
description: Referanseinformasjon om hvordan du arbeider med lerretsapptabeller, -kolonner og -poster i PowerApps
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 05/23/2019
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: b35f8efdc090cc899476a65d73fd8cb3a4200faf
ms.sourcegitcommit: 9163abbe9a24298f216f15139f977adfd2c3f2ae
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/16/2019
ms.locfileid: "69550385"
ms.PowerAppsDecimalTransform: true
---
# <a name="understand-canvas-app-tables-and-records-in-powerapps"></a>Slik fungerer lerretsapptabeller og -poster i PowerApps

Du kan opprette en lerretsapp i PowerApps, som har tilgang til informasjon i Microsoft Excel, SharePoint, SQL Server og flere andre kilder der det lagres data i poster og tabeller. Hvis du vil arbeide mest mulig effektivt med denne typen data, kan du se gjennom begrepene som ligger til grunn for disse strukturene.

* En post inneholder én eller flere kategorier med informasjon om en person, et sted eller en ting. En post kan for eksempel inneholde navnet, e-postadressen og telefonnummeret til en enkeltkunde. Andre verktøy refererer til en post som en rad eller et element.
* En tabell inneholder én eller flere poster som inneholder de samme kategoriene av informasjon. En tabell kan for eksempel inneholde navnene, e-postadressene og telefonnumrene til 50 kunder.

I appen din skal du bruke [formler](working-with-formulas.md) for å opprette, oppdatere, og endre poster og tabeller. Du skal sannsynligvis lese og skrive data til en ekstern [datakilde](working-with-data-sources.md), som er en utvidet tabell. I tillegg kan du opprette én eller flere interne tabeller, som kalles [samlinger](working-with-data-sources.md#collections).

Du kan bygge et utvalg av formler som tar navnet på en tabell som et argument, på samme måte som en formel i Excel tar én eller flere cellereferanser som argumenter. Noen formler i PowerApps returnerer en tabell som gjenspeiler argumentene du angir. Du kan for eksempel opprette en formel:

* for å oppdatere en post i en tabell ved å angi denne tabellen som ett av flere argumenter for  **[Patch](functions/function-patch.md)** -funksjonen
* for å legge til, fjerne og gi nytt navn til kolonner i en tabell ved å angi denne tabellen som et argument for **[ AddColumns-](functions/function-table-shaping.md)** , **[DropColumns-](functions/function-table-shaping.md)** eller **[RenameColumns](functions/function-table-shaping.md)** -funksjonen. Ingen av disse funksjonene endrer den opprinnelige tabellen. Funksjonen returnerer i stedet en annen tabell som er basert på de andre argumentene du angir.

## <a name="elements-of-a-table"></a>Elementene i en tabell
![](media/working-with-tables/elements-of-a-table.png)

### <a name="records"></a>Poster
Hver post inneholder minst én kategori med informasjon for en person, et sted eller en ting. Eksemplet ovenfor viser en post for hvert produkt (**sjokolade**, **brød**, og **vann**), og en kolonne for hver kategori med informasjon (**pris**, **antall på lager**, og **antall i ordre**).

I en formel kan du referere til en post som står alene, utenfor konteksten til en tabell ved hjelp av klammeparenteser. For eksempel denne posten **{Name: «Strawberries»; pris: 7;99}** er ikke knyttet til en tabell. Vær oppmerksom på at feltnavn, for eksempel **Name** og **Price** i eksempelet over, ikke står i doble anførselstegn.

### <a name="fields"></a>Felt
Et felt er et enkeltstående stykke informasjon i en post. Du kan visualisere denne type av felt som en verdi i en kolonne for en bestemt post.

På samme måte som med en kontroll, refererer du til et felt eller en post ved å bruke **.** [operatoren](functions/operators.md) for posten.  **First(Products).Name** returnerer for eksempel **Navn**-feltet for den første posten i **Produkt**-tabellen.

Et felt kan inneholde en annen post eller tabell, som eksemplet for **[GroupBy](functions/function-groupby.md)** -funksjonen viser. Du kan neste så mange nivåer av poster og tabeller som du ønsker.

### <a name="columns"></a>Kolonner
En kolonne refererer til det samme feltet for én eller flere poster i en tabell. I eksemplet ovenfor har hvert produkt et prisfelt, og denne prisen er i samme kolonne for alle produkter.  Tabellen ovenfor har fire kolonner som vises vannrett øverst på tvers:

* **Navn**
* **Pris**
* **Antall på lager**
* **Antall i ordre**

Navnet på kolonnen gjenspeiler feltene i denne kolonnen.

Alle verdier i en kolonne er av samme datatype. I eksemplet ovenfor inneholder kolonnen «Antall på lager» alltid et tall og kan ikke inneholde en streng, for eksempel «12 enheter», for én post.  Verdien for et felt kan også være *tom*.  

Det kan hende at andre verktøy kaller kolonner «felt».

> [!NOTE]
> PowerApps erstatter mellomrommene med **"\_x0020\_"** for SharePoint- og Excel-datakilder som inneholder kolonnenavn med mellomrom. **Kolonnenavn** i SharePoint eller Excel, vil for eksempel vises som **Column_x0020_Name** i PowerApps når det vises i dataoppsettet, eller brukes i en formel.

### <a name="table"></a>Table
En tabell består av én eller flere poster, som hver har flere felt med konsekvente navn på tvers av postene.

Alle tabeller som er lagret i en datakilde eller en samling, har et navn, som du bruker til å referere til tabellen og sende den til funksjoner som tar tabeller som argumenter.  Tabeller kan også være et resultatet av en funksjon eller formel.

Som i eksemplet nedenfor, kan du uttrykke en tabell i en formel ved hjelp av **[Table](functions/function-table.md)** -funksjonen sammen med et sett med poster, som du uttrykker i klammeparenteser:

`Table( { Value: "Strawberry" }; { Value: "Vanilla" } )`

Du kan også definere en enkeltkolonne-tabell med hakeparenteser.  En tilsvarende måte å skrive det ovenfor:

`[ "Strawberry"; "Vanilla" ]`

## <a name="table-formulas"></a>Tabellformler
I Excel og PowerApps, kan du bruke formler til å endre tall og strenger av tekst på lignende måte:

* Skriv for eksempel inn en verdi som **42** i celle **A1**, i Excel, og skriv deretter for eksempel inn en formel som **A1 + 2** i en annen celle, for å vise verdien av **44**.
* I PowerApps kan du angi **[Standard](controls/properties-core.md)** -egenskapen for **Slider1** til **42**, og angi  **[Tekst](controls/properties-core.md)** -egenskapen for en etikett til **Slider1.Value + 2** til å vise verdien av **44**.

I begge tilfeller endres automatisk den beregnede verdien, hvis du endrer verdiene av argumentene (for eksempel tall i celle **A1**, eller verdien av **Slider1**).

På samme måte kan du bruke formler til å få tilgang til og endre data i tabeller og poster. Du kan bruke navnene på tabeller som argumenter i noen formler, som for eksempel **Min(Catalog; Price)** , til å vise den laveste verdien i **Pris**-kolonnen i **Katalog**-tabellen. Andre formler gir hele tabeller som returverdier, for eksempel **RenameColumns(Catalog; "Price"; "Cost")** , som returnerer alle postene fra **Katalog**-tabellen, men endrer navnet på **Pris**-kolonnen til **Kostnader**.

Akkurat som med tall, beregnes formler som involverer tabeller og poster automatisk samtidig med at den underliggende tabellen eller posten endres. Hvis kostnaden for et produkt i **Katalog**-tabellen senkes under det forrige minimumsnivået, vil returverdien for **[Min](functions/function-aggregates.md)** -formelen endres automatisk, slik at de stemmer overens.

La oss gå gjennom noen enkle eksempler.

1. Opprett en tom app for en telefon, og legg til en loddrett **[Galleri](controls/control-gallery.md)** -kontroll som inneholder andre kontroller.

    Som standard viser skjermen plassholdertekst fra en tabell kalt **CustomGallerySample**. **[Elementer](controls/properties-core.md)** -egenskapen til skjermens **[Gallery](controls/control-gallery.md)** -kontroll angis automatisk for den tabellen.

    ![](media/working-with-tables/gallery-items.png)

    > [!NOTE]
    > Noen av kontrollene har blitt omorganisert og forstørret for illustrasjonsformål.

2. I stedet for å angi **[Elementer](controls/properties-core.md)** -egenskapen til navnet på en tabell, kan du angi en formel som inneholder navnet på tabellen som et argument, som i dette eksemplet:

    `Sort(CustomGallerySample; SampleHeading; Descending)`

    Denne formelen inneholder **[Sort](functions/function-sort.md)** -funksjonen, som tar navnet på en tabell som første argument. og navnet på en kolonne i denne tabellen som det andre argumentet. Funksjonen støtter også et valgfritt tredje argument, som stipulerer at du vil sortere dataene i synkende rekkefølge.

    ![](media/working-with-tables/gallery-items-sort.png)

3. Angi **[Elementer](controls/properties-core.md)** -egenskapen til en formel som tar formelen fra det forrige trinnet som et argument og returnerer en tabell, som i dette eksemplet:

    `FirstN(Sort(CustomGallerySample; SampleHeading; Descending); 2)`

    I denne formelen bruker du **[FirstN](functions/function-first-last.md)** -funksjonen til å vise et bestemt antall poster i en tabell. Bruk **[Sort](functions/function-sort.md)** -funksjonen som det første argumentet til **[FirstN](functions/function-first-last.md)** , og et tall (i dette tilfellet **2**) som det andre argumentet, som angir hvor mange poster for som skal vises.

    Hele formelen returnerer en tabell som inneholder de to første postene i **CustomGallerySample**-tabellen, sortert etter **SampleHeading**-kolonnen i synkende rekkefølge.

    ![](media/working-with-tables/gallery-items-sort-firstn.png)

## <a name="table-functions-and-control-properties"></a>Tabellfunksjoner og kontrollegenskaper

Vurder den **nedre** funksjonen. Hvis den variable **velkomsten** inneholder tekst strengen **"Hello, World"** , returnerer formelen **lavere (Velkommen)** **"Hello, World"** .  Denne funksjonen kan ikke på noen måte endre verdien i denne variabelen. **Lavere** er en ren funksjon som bare behandler inn data og produserer utdata. Det er alt; den har ingen side effekter. Alle funksjoner i Excel og de fleste funksjonene i PowerApps er rene funksjoner, som gjør at arbeids boken eller appen kan beregnes på nytt automatisk.

PowerApps tilbyr et sett med funksjoner som opererer i tabeller på samme måte. Disse funksjonene tar tabeller som inn data og filtrerer, sorterer, transformerer, reduserer og oppsummerer alle tabeller med data. Men mange andre funksjoner som vanligvis tar en enkelt verdi, kan også ta en tabell med én kolonne som inn data.

* **[Sort](functions/function-sort.md)** , **[Filter](functions/function-filter-lookup.md)** – sorterer og filtrerer poster.
* **[FirstN](functions/function-first-last.md)** , **[LastN](functions/function-first-last.md)** – returnerer den første eller de siste N-postene i tabellen.
* **[ABS](functions/function-numericals.md)** , **[Rot](functions/function-numericals.md)** , **[Avrund](functions/function-round.md)** , **[Avrund.opp](functions/function-round.md)** , **[Avrund.ned](functions/function-round.md)** – aritmetiske operasjoner i hver post i en enkeltkolonne-tabell, noe som resulterer i en enkeltkolonne-tabell med resultater.
* **[Left](functions/function-left-mid-right.md)** , **[Mid](functions/function-left-mid-right.md)** , **[Right](functions/function-left-mid-right.md)** , **[Replace](functions/function-replace-substitute.md)** , **[Substitute](functions/function-replace-substitute.md)** , **[Trim](functions/function-trim.md)** , **[Lower](functions/function-lower-upper-proper.md)** , **[Upper](functions/function-lower-upper-proper.md)** , **[Proper](functions/function-lower-upper-proper.md)** – strengendringer i hver post i en enkeltkolonne-tabell, noe som resulterer i en enkeltkolonne-tabell med strenger.
* **[Lengde](functions/function-len.md)** – returnerer en enkeltkolonne-tabell for en kolonne med strenger, som inneholder lengden på hver streng.
* **[Kjede.sammen](functions/function-concatenate.md)**  – kjeder sammen flere kolonner med strenger, noe som resulterer i en enkeltkolonne-tabell med strenger.
* **[AddColumns](functions/function-table-shaping.md)** , **[DropColumns](functions/function-table-shaping.md)** , **[RenameColumns](functions/function-table-shaping.md)** , **[ShowColumns](functions/function-table-shaping.md)** – kolonneredigering av tabellen, noe som resulterer i en ny tabell med andre kolonner.
* **[Distinct](functions/function-distinct.md)** – fjerner duplikater for poster.
* **[Shuffle](functions/function-shuffle.md)** – flytter poster i tilfeldig rekkefølge.
* **[HashTags](functions/function-hashtags.md)** – søker etter emneknagger i en streng.
* **[Errors](functions/function-errors.md)** – gir informasjon om feil når du arbeider med en datakilde.

Mange av disse funksjonene tar en tabell med én kolonne som inn data. Hvis en hel tabell bare har én kolonne, kan du angi den ved navn. Hvis en tabell har flere kolonner, kan du angi én av disse Kol onnene ved hjelp av *Table. Column* -syntaks. **Products.name** returnerer for eksempel tabellen med én kolonne med navne verdier fra **produkter** -tabellen.

Du kan forme en tabell fullstendig, men du vil bruke funksjonen **[AddColumns](functions/function-table-shaping.md)** , **[RenameColumns](functions/function-table-shaping.md)** , **[ShowColumns](functions/function-table-shaping.md)** eller **[DropColumns](functions/function-table-shaping.md)** . Disse funksjonene endrer bare utdata, ikke kilden.

Egenskaper for kontroller kan også være tabeller:

* **Elementer** – gjelder gallerier, liste bokser og kombinasjons bokser. Denne egenskapen definerer tabellen som galleriet eller listen viser.
* **SelectedItems** – gjelder lister og kombinasjons bokser. Denne egenskapen definerer tabellen med elementer som brukeren har valgt hvis **SelectMultiple** er aktivert.

## <a name="behavioral-formulas"></a>Virke måte formler

Andre funksjoner er spesielt utformet for å endre data og ha bivirkninger. Fordi disse funksjonene ikke er ekte, må du bygge dem grundig, og de kan ikke delta i automatisk omberegning av verdier i appen. Du kan bare bruke disse funksjonene i [formler som fungerer](working-with-formulas-in-depth.md).

* **[Innsamling](functions/function-clear-collect-clearcollect.md)** , **[tømming](functions/function-clear-collect-clearcollect.md)** , **[ClearCollect](functions/function-clear-collect-clearcollect.md)** – oppretter samlinger, fjerner dem og legger til data i dem.
* **[Oppdatering](functions/function-patch.md)** – endrer ett eller flere felt i en post.
* **[Update](functions/function-update-updateif.md)** , **[UpdateIf](functions/function-update-updateif.md)** – oppdaterer poster som oppfyller ett eller flere vilkår som du angir.
* **[Fjern](functions/function-remove-removeif.md)** , **[RemoveIf](functions/function-remove-removeif.md)** – sletter poster som oppfyller ett eller flere vilkår du angir.

## <a name="record-formulas"></a>Postformler

Du kan også bygge en formel som beregner data for en individuell post, tar en individuell post som et argument, og gir en individuell post som en returverdi. La oss gå tilbake til galleri-eksemplet ovenfor, og bruke **Gallery1.Selected** til å vise informasjon fra en post brukeren velger i galleriet.

1. Legg til en [**knapp**](controls/control-button.md), og angi **[OnSelect](controls/properties-core.md)** -egenskapen til denne formelen:<br>
    **Collect( SelectedRecord; Gallery1.Selected )**

2. Velg knappen mens du holder nede ALT.

3. Velg **Samlinger** i **Fil**-menyen.

    ![](media/working-with-tables/selected-collection.png)

Denne formelen returnerer en post som ikke bare inneholder data fra gjeldende post som er valgt i galleriet, men også hver kontroll i galleriet. Posten inneholder for eksempel både en **SampleText**-kolonne, som samsvarer med **SampleText**-kolonnen i den opprinnelige tabellen, og en **Subtitle1**-kolonne, som representerer etiketten som viser data fra denne kolonnen. Velg tabellikonet i **Subtitle1**-kolonnen for å drille ned i dataene.

> [!NOTE]
> **Subtitle1**-kolonnen kan ha navnet **Subtitle2** eller lignende, hvis du har lagt til andre elementer enn de som kreves for dette emnet.

Nå som du har valgt posten, kan du trekke ut enkeltfelten fra den med **.** -operatoren.

1. Legg til en **[Etikett](controls/control-text-box.md)** -kontroll, og flytt den deretter under galleriet på bunnen.

1. Angi etikettens **[Tekst](controls/properties-core.md)** -egenskap til dette uttrykket:<br>
    **"Selected: " & Gallery1.Selected.SampleHeading**

    ![](media/working-with-tables/gallery-selected.png)

Du har tatt **Merket**-egenskapen, som er en post, og pakket ut **SampleHeading**-egenskapen fra den.

Du kan også bruke en post som en beholder til generelt bruk for relaterte navngitte verdier.

* Bruk en post til å samle [ kontekstvariablene](working-with-variables.md#use-a-context-variable) som du vil oppdatere, hvis du bygger en formel rundt **[UpdateContext](functions/function-updatecontext.md)** - og **[Naviger](functions/function-navigate.md)** -funksjonene.
* Bruk **[Oppdateringer](controls/control-form-detail.md)** -egenskapen i en **[Redigeringsskjema](controls/control-form-detail.md)** -kontroll for å samle inn endringene som er gjort av brukeren i et skjema.
* Bruk **[Patch](functions/function-patch.md)** -funksjonen til å oppdatere en datakilde, men også for å slå sammen poster.

Posten ble aldri en del av en tabell i disse tilfellene.

## <a name="record-functions-and-control-properties"></a>Postfunksjoner og kontrollegenskaper
Funksjoner som returnerer poster:

* **[FirstN](functions/function-first-last.md)** , **[LastN](functions/function-first-last.md)** – returnerer den første eller siste posten, eller postene, i tabellen.
* **[Lookup](functions/function-filter-lookup.md)** – returnerer den første posten fra en tabell som samsvarer med ett eller flere vilkår.
* **[Patch](functions/function-patch.md)**  – oppdaterer en datakilde eller fletter poster.
* **[Defaults](functions/function-defaults.md)** – returnerer standardverdiene for en datakilde.

Egenskaper som returnerer poster:

* **Selected** – gjelder gallerier og listebokser. Returnerer gjeldende merket rad.
* **Updates** – gjelder gallerier.  Trekker sammen alle endringene som en bruker gjør i et skjema for dataregistrering.
* **[Update](functions/function-update-updateif.md)** – gjelder inndata-kontroller, for eksempel tekstinndata-kontroller og glidebrytere. Angir individuelle egenskaper for galleriet til å trekke sammen.

## <a name="record-scope"></a>Postomfang

Noen funksjoner fungerer ved å enkeltvis evaluere en formel på tvers av alle poster i en tabell. Formelens resultat brukes på forskjellige måter:

* **AddColumns** – formelen angir verdien for feltet som er lagt til.
* **Average**, **Max**, **Min**, **Sum**, **StdevP**, **VarP** – formelen angir verdien skal aggregeres.
* **Filter**, **Lookup** – formelen bestemmer om posten skal inkluderes i utdataene.
* **Kjed.sammen** – formelen bestemmer strengene som skal settes sammen.
* **Distinct** – formelen returnerer en verdi som brukes til å identifisere like poster.
* **ForAll** -formelen kan returnere enhver verdi, potensielt med side effekter.
* **Sort** – formelen angir verdien som postene sorteres etter.
* **Med** -formelen kan du returnere alle verdier, potensielt ved hjelp av bivirkninger.

I disse formlene kan du referere til feltene i posten som behandles. Hver av disse funksjonene oppretter et «postomfang» der formelen beregnes, og der feltene i posten er tilgjengelige som identifikatorer på øverste nivå. Du kan også referere til kontrollegenskaper og andre verdier i hele appen.

Ta for eksempel en tabell med **Produkter**:

![](media/working-with-tables/requested.png)

Hvis du vil opprette denne eksempel tabellen i appen, setter du inn en knapp, angir **OnSelect** -egenskapen til denne formelen, og deretter velger du knappen (Klikk den mens du holder nede Alt-tasten i PowerApps Studio):

```powerapps-comma
Set( Products;
    Table(
        { Product: "Widget";    'Quantity Requested': 6;  'Quantity Available': 3 };
        { Product: "Gadget";    'Quantity Requested': 10; 'Quantity Available': 20 };
        { Product: "Gizmo";     'Quantity Requested': 4;  'Quantity Available': 11 };
        { Product: "Apparatus"; 'Quantity Requested': 7;  'Quantity Available': 6 }
    )
)
```

For å finne ut om noen av disse produktene måtte ha vært mer forespurt enn det som er tilgjengelig:

`Filter( Products; 'Quantity Requested' > 'Quantity Available' )`

Det første argumentet i **Filter** er tabellen med poster som det opereres med, og det andre argumentet er en formel.  **Filter** oppretter et postomfang for evaluering av denne formelen, der feltene for hver post er tilgjengelig, i dette tilfellet **Produkt**, **Ønsket antall**, og **Disponibelt antall**.  Resultatet av sammenligningen bestemmer om hver post skal inkluderes i resultatet av funksjonen:

![](media/working-with-tables/needed.png)

For å legge til i dette eksemplet, kan vi beregne hvor mye av hvert produkt som skal bestilles:

```powerapps-comma
AddColumns( 
    Filter( Products; 'Quantity Requested' > 'Quantity Available' ); 
    "Quantity To Order"; 'Quantity Requested' - 'Quantity Available'
)
```

Her er legger vi til en beregnet kolonne til resultatet. **AddColumns** har sitt eget postomfang, som brukes til å beregne forskjellen mellom hva som er forespurt og hva som er tilgjengelig.

![](media/working-with-tables/toorder.png)

Til slutt kan vi redusere resultat tabellen til bare Kol onnene som vi ønsker:

```powerapps-comma
ShowColumns(
    AddColumns(
        Filter( Products; 'Quantity Requested' > 'Quantity Available' );
        "Quantity To Order"; 'Quantity Requested' - 'Quantity Available'
    );
    "Product";
    "Quantity To Order"
)
```

![](media/working-with-tables/toorderonly.png)

Vær oppmerksom på at i det ovenstående brukte vi doble anførselstegn (") noen steder og enkle anførselstegn (') andre steder.  Enkle anførselstegn er nødvendig når du refererer til verdien for et objekt, for eksempel et felt eller en tabell, der navnet på objektet inneholder et mellomrom.  Doble anførselstegn brukes når vi ikke refererer til verdien for et objekt, men i stedet snakker om det, spesielt i situasjoner der objektet ikke finnes ennå, som er tilfelle i **AddColumns**.

## <a name="disambiguation"></a>Tvetydighet

Feltnavnene som ble lagt til ved bruk av postområdet overstyrer de samme navnene fra ellers i appen.  Når dette skjer, har du fremdeles tilgang til verdiene som er utenfor postområdet ved bruk av operatoren [ **@** Tvetydighet](functions/operators.md):

* Hvis du vil ha tilgang til verdiene fra nestede postområder, bruker du **@** operatoren med samme navn som tabellen der operatoren arbeider ved bruk av mønsteret:<br>_Table_ **[@** _FieldName_ **]**
* Hvis du vil ha tilgang til globale verdier, som datakilder, samlinger og kontekstvariabler, bruker du mønsteret **[@** _ObjectName_ **]** (uten en tabellangivelse).

Hvis tabellen som styres er et uttrykk, for eksempel **Filter(** _Table_ **,** ... **)** , kan ikke tvetydighetsoperatoren brukes.  Bare det innerste postomfanget har tilgang til felt fra dette tabelluttrykket ved å ikke bruke operatoren Tvetydighet.

Anta for eksempel at du har en samling **X**:

![](media/working-with-tables/X.png)

Du kan opprette denne samlingen med **ClearCollect( X; \[1; 2\] )** .

Og en annen samling **Y**:

![](media/working-with-tables/Y.png)

Du kan opprette denne samlingen med **ClearCollect( Y; ["A"; "B"] )** .

I tillegg kan du definere en kontekst variabel kalt **Value** med denne formelen: **UpdateContext ({Value: "!"})**

La oss sette alt sammen. Følgende formel i denne konteksten:

```powerapps-comma
Ungroup(
    ForAll( X;
        ForAll( Y;
            Y[@Value] & Text( X[@Value] ) & [@Value]
        )
    );
    "Value"
)
```

gir denne tabellen:

![](media/working-with-tables/XY.png)

Hva skjer her?  Den ytterste **ForAll**-funksjonen definerer et postomfang for **X**, som gir tilgang til **Verdi**-feltet for hver post når det behandles.  Den blir tilgjengelig ved ganske enkelt å bruke ordet **Verdi**, eller ved å bruke **X [@Value]** .

Den innerste **ForAll**-funksjonen definerer et annen postomfang for **Y**.  Siden denne tabellen også har definert et **Verdi**-felt, refererer bruken av **Verdi** her til posten i feltet i **Y** og ikke lenger den fra **X**.  Vi må her bruke den lengre versjonen med tvetydighetsoperatoren for å få tilgang til **Verdi**-feltet for **X**.

Tilgang til feltene i denne tabellen krever ikke tvetydighet, siden **Y** er innerste postomfang, slik at vi kan bruke denne formelen med det samme resultatet:

```powerapps-comma
Ungroup(
    ForAll( X;
        ForAll( Y;
            Value & Text( X[@Value] ) & [@Value]
        )
    );
    "Value"
)
```

Alle **ForAll**-postomfang overstyrer det globale omfanget. **Verdien** kontekst variabel som ble angitt, er ikke tilgjengelig ved navn uten en detvetydighets operator. Bruk **[@Value]** for å få tilgang til denne verdien.

**Del opp gruppe** slår sammen resultatet fordi nestede **ForAll** -funksjoner resulterer i en nestet resultat tabell.

## <a name="single-column-tables"></a>Tabeller med én kolonne

Hvis du vil bruke en enkelt kolonne fra en tabell, bruker du **ShowColumns** -funksjonen som i dette eksemplet:

```powerapps-comma
ShowColumns( Products; "Product" )
```

Denne formelen produserer en enkelt Kol onne tabell:

![](media/working-with-tables/single-column.png)

For et kortere alternativ må du angi *Table. Column*, som trekker ut tabellen med én kolonne i bare *kolonnen* fra *tabellen*. Denne formelen gir for eksempel nøyaktig samme resultat som ved bruk av **ShowColumns**.

```powerapps-comma
Products.Product
```

## <a name="inline-records"></a>Linje bundne poster

Du kan uttrykke poster ved hjelp av klammeparenteser som inneholder navngitte feltverdier.  Du kan for eksempel uttrykke den første posten i tabellen i begynnelsen av dette emnet ved hjelp av denne formelen:

`{ Name: "Chocolate"; Price: 3,95; 'Quantity on Hand': 12; 'Quantity on Order': 10 }`

Du kan også bygge inn formler i andre formler, som dette eksemplet viser:

`{ Name: First(Products).Name; Price: First(Products).Price * 1,095 }`

Du kan neste poster ved å neste klammeparenteser, som dette eksemplet viser:

`{ 'Quantity': { 'OnHand': ThisItem.QuantOnHand; 'OnOrder': ThisItem.QuantOnOrder } }`

Omslutte hvert kolonnenavn som inneholder et spesialtegn, for eksempel et mellomrom eller et kolon, i enkle anførselstegn.  Du kan doble dem, hvis du vil bruke et enkelt sitat i et kolonnenavn.

Vær oppmerksom på at verdien i **Pris**-kolonnen ikke inneholder et valutasymbol, for eksempel et dollartegn. Denne formateringen vil bli brukt når verdien vises.  

## <a name="inline-tables"></a>Linje bundne tabeller
Du kan opprette en tabell ved hjelp av **[Table](functions/function-table.md)** -funksjonen og et sett med poster. Du kan uttrykke tabellen i begynnelsen av dette emnet ved hjelp av denne formelen:

```powerapps-comma
Table( 
    { Name: "Chocolate"; Price: 3,95; 'Quantity on Hand': 12; 'Quantity on Order': 10 };
    { Name: "Bread"; Price: 4,95; 'Quantity on Hand': 34; 'Quantity on Order': 0 };
    { Name: "Water"; Price: 4,95; 'Quantity on Hand': 10; 'Quantity on Order': 0 } 
)
```

Du kan også neste tabeller:

```powerapps-comma
Table( 
    { Name: "Chocolate"; 
      'Quantity History': Table( { Quarter: "Q1"; OnHand: 10; OnOrder: 10 };
                                 { Quarter: "Q2"; OnHand: 18; OnOrder: 0 } ) 
    }
)
```

## <a name="inline-value-tables"></a>Tabeller med innebygd verdi
Du kan opprette enkeltkolonne-tabeller ved å angi verdier i hakeparenteser. Den resulterende tabellen har én enkelt kolonne, kalt **Verdi**.

For eksempel `[ 1; 2; 3; 4 ]` `Table( { Value: 1 }; { Value: 2 }; { Value: 3 }; { Value: 4 } )` tilsvarer og returnerer denne tabellen:

![](media/working-with-tables/inline-table.png)

