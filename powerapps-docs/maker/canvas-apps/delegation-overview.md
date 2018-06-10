---
title: Delegering i Microsoft Docs
description: Bruk delegering for prosessering av store datasett på en effektiv måte.
documentationcenter: na
author: gregli-msft
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: conceptual
ms.component: canvas
ms.date: 03/27/2018
ms.author: gregli
ms.openlocfilehash: 0800adf43f5a7d74d0334e9f39216a70b9350d6d
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/04/2018
ms.locfileid: "31838060"
---
# <a name="understand-delegation"></a>Å forstå delegering
PowerApps inneholder et kraftig sett med funksjoner for filtrering, sortering og forming av datatabeller, blant annet funksjonene **[Filter](functions/function-filter-lookup.md)**, **[Sort](functions/function-sort.md)** og **[AddColumns](functions/function-table-shaping.md)**.  Med disse funksjonene kan du gi brukerne fokusert tilgang til informasjonen de trenger.  For de med databasebakgrunn vil bruk av disse funksjonene tilsvare skriving av en databasespørring.  

Nøkkelen til utvikling av effektive apper er å minimere datamengden som sendes til enheten din.  Det er kanskje nok med noen få poster blant flere millioner, eventuelt kan én enkelt akkumulert verdi representere tusener av poster.  Det kan også hende det bare er mulig å hente det første settet med poster, og resten føres inn når brukeren viser at det trengs flere.  Fokus kan kraftig redusere prosesskraften, minnet og nettverksbåndbredden som appen trenger, noe som resulterer i raskere svartider for brukerne, selv på telefoner som er tilkoblet via et mobilnettverk.  

*Delegering* er der omfattende PowerApps-formler oppfyller behovet for å minimere datamengden som flyttes over nettverket.  I korte trekk betyr dette at PowerApps delegerer behandlingen av data til datakilden, i stedet for å flytte data til appen for lokal behandling.  

Når dette begynner å bli komplisert, hvilket er grunnen til at denne artikkelen finnes, er det fordi ikke alt som kan uttrykkes i en PowerApps-formel kan delegeres til alle datakilder.  PowerApps-språket etterligner Excels formelspråk, utformet med komplett og umiddelbar tilgang til en fullstendig arbeidsbok i minnet, med et bredt utvalg manipuleringsfunksjoner for tall og tekst.  Derfor er PowerApps-språket mer omfattende enn det som støttes av de fleste datakilder, inkludert robuste databasemotorer som SQL Server.

**Arbeid med store datasett krever at du bruker datakilder og formler som kan delegeres.**  Dette er den eneste måten å sikre at appen fungerer bra på, og at brukere får tilgang til informasjonen de trenger. Legg merke til [forslag med blå prikk](delegation-overview.md#blue-dot-suggestions), som flagger steder der delegering ikke er mulig.  Hvis du arbeider med små datasett (færre enn 500 poster), kan du bruke alle datakilder og formler, ettersom behandling kan gjøres lokalt hvis formelen ikke kan delegeres. 

## <a name="delegable-data-sources"></a>Datakilder som kan delegeres
Gå til [delegeringslisten](delegation-list.md) for å se den fullstendige listen over hvilke datakilder som støtter delegering, og i hvilken grad.

Vi fortsetter å legge til delegeringsstøtte i eksisterende datakilder, i tillegg til å legge til flere datakilder.

Importerte Excel-arbeidsbøker (som bruker datakilden «Legg til statiske data i appen»), samlinger og tabeller som er lagret i kontekstvariabler, krever ikke delegering. Alle disse dataene ligger allerede i minnet, og det fullstendige PowerApps-språket kan brukes.

## <a name="delegable-functions"></a>Funksjoner som kan delegeres
Neste trinn er å bruke bare de formlene som kan delegeres. Formelelementene som kan delegeres er inkludert her.  Alle datakilder er imidlertid forskjellige, og det er ikke alle som støtter alle disse elementene. Kontroller om det finnes forslag med blå prikk i den aktuelle formelen.

Disse listene endres over tid. Vi arbeider mot å støtte flere funksjoner og operatorer med delegering.

### <a name="filter-functions"></a>Filtreringsfunksjoner
**[Filter](functions/function-filter-lookup.md)**, **[Search](functions/function-filter-lookup.md)** og **[LookUp](functions/function-filter-lookup.md)** kan delegeres.  

Følgende kan brukes med kolonner i tabellen for å velge riktige poster i funksjonene **Filter** og **LookUp**:

* **[And](functions/function-logicals.md)** (inkludert **[&&](functions/operators.md)**), **[Or](functions/function-logicals.md)** (inkludert **[||](functions/operators.md)**), **[Not](functions/function-logicals.md)** (inkludert **[!](functions/operators.md)**)
* **[In](functions/operators.md)**
* **[=](functions/operators.md)**, **[<>](functions/operators.md)**, **[>=](functions/operators.md)**, **[<=](functions/operators.md)**, **[>](functions/operators.md)**, **[<](functions/operators.md)**
* **[+](functions/operators.md)**, **[-](functions/operators.md)**
* **[TrimEnds](functions/function-trim.md)**
* **[IsBlank](functions/function-isblank-isempty.md)**
* **[StartsWith](functions/function-startswith.md)**
* Konstante verdier som er de samme i alle postene, for eksempel kontrollegenskaper og [globale variabler og kontekstvariabler](working-with-variables.md).

Deler av formelen som evalueres som en konstant verdi for alle poster, kan også brukes.  **Left( Language(), 2 )** avhenger for eksempel ikke av andre kolonner i posten, og returner derfor samme verdi for alle poster.  Dette er en konstant.  Bruk av kontekstvariabler, samlinger og signaler er kanskje ikke konstant og vil derfor hindre at **Filter** og **LookUp** delegeres.  

Noen viktige elementer som mangler i listen ovenfor:

* **[If](functions/function-if.md)**
* **[*](functions/operators.md)**, **[/](functions/operators.md)**, **[Mod](functions/function-mod.md)**
* **[Concatenate](functions/function-concatenate.md)** (inkludert **[&](functions/operators.md)**)
* **[ExactIn](functions/operators.md)**
* Funksjoner for strengmanipulering: **[Lower](functions/function-lower-upper-proper.md)**, **[Upper](functions/function-lower-upper-proper.md)**, **[Left](functions/function-left-mid-right.md)**, **[Mid](functions/function-left-mid-right.md)**, **[Len](functions/function-left-mid-right.md)**,...
* Signaler: **[Plassering](functions/signals.md)**, **[Akselerasjon](functions/signals.md)**, **[Kompass](functions/signals.md)**, ...
* Flyktige: **[Now](functions/function-now-today-istoday.md)**, **[Today](functions/function-now-today-istoday.md)**, **[Rand](functions/function-rand.md)**, ...
* [Samlinger](working-with-variables.md)

### <a name="sorting-functions"></a>Sorteringsfunksjoner
**[Sort](functions/function-sort.md)** og **[SortByColumns](functions/function-sort.md)** kan delegeres.  

I **Sort** kan formelen bare inneholde navnet til en enkeltkolonne og kan ikke inneholde andre operatorer eller funksjoner.

### <a name="aggregate-functions"></a>Mengdefunksjoner
**[Sum](functions/function-aggregates.md)**, **[Average](functions/function-aggregates.md)**, **[Min](functions/function-aggregates.md)**, and **[Max](functions/function-aggregates.md)** kan delegeres.  Bare et begrenset antall datakilder støtter denne delegeringen nå. Kontroller [delegeringslisten](delegation-list.md) for å finne mer informasjon.

Tellingsfunksjoner som **[CountRows](functions/function-table-counts.md)**, **[CountA](functions/function-table-counts.md)** og **[Count](functions/function-table-counts.md)** kan ikke delegeres.

Andre mengdefunksjoner, for eksempel **[StdevP](functions/function-aggregates.md)** og**[VarP](functions/function-aggregates.md)**, kan ikke delegeres.

## <a name="non-delegable-functions"></a>Funksjoner som ikke kan delegeres
Ingen andre funksjoner støtter delegering, herunder disse viktige funksjonene:

* Tabellbearbeiding: **[AddColumns](functions/function-table-shaping.md)**, **[DropColumns](functions/function-table-shaping.md)**, **[ShowColumns](functions/function-table-shaping.md)**, ...
* **[First](functions/function-first-last.md)**, **[FirstN](functions/function-first-last.md)**, **[Last](functions/function-first-last.md)**, **[LastN](functions/function-first-last.md)**
* **[Concat](functions/function-concatenate.md)**
* **[Collect](functions/function-clear-collect-clearcollect.md)**, **[ClearCollect](functions/function-clear-collect-clearcollect.md)**
* **[CountIf](functions/function-table-counts.md)**, **[RemoveIf](functions/function-remove-removeif.md)**, **[UpdateIf](functions/function-update-updateif.md)**
* **[GroupBy](functions/function-groupby.md)**, **[Ungroup](functions/function-groupby.md)**

Et vanlig mønster er å bruke **AddColumns** og **LookUp** for å slå sammen informasjon fra én tabell til en annen. Dette kalles vanligvis Sammenføyning på dataspråket.  Eksempel:

**AddColumns( Products, "Supplier Name", LookUp( Suppliers, Suppliers.ID = Product.SupplierID ).Name )**

Selv om **Produkter** og **Leverandører** er datakilder som kan delegeres, og **Lookup** er en funksjon som kan delegeres, kan ikke funksjonen **AddColumns** delegeres.  Resultatet av hele formelen begrenses til den første delen av **Produkter**-datakilden.  

Siden **LookUp** og tilhørende datakilde kan delegeres, finnes det treff for **Leverandører** overalt i datakilden, selv om den er stor.  En potensiell ulempe er at **LookUp** oppretter separate kall til datakilden for hver av disse første postene i **Produkter**, noe som forårsaker mye støy på nettverket.  Hvis **Leverandører** er liten nok, og ikke endres ofte, kan datakilden bufres i appen med et **Collect**-kall når appen starter opp (ved hjelp av [**OnVisible**](controls/control-screen.md) på åpningsskjermen), og bruke **Oppslag** i stedet.  

## <a name="non-delegable-limits"></a>Grenser for ikke-delegering
Formler som ikke kan delegeres, behandles lokalt.  Dette gjør det mulig å bruke hele formelspråket til PowerApps.  Dette har likevel sin pris. Alle dataene må sendes til enheten først, noe som innebærer å hente en stor mengde data over nettverket.  Dette kan ta tid, noe som kan gi inntrykk av at appen er treg eller har hengt seg opp.

For å unngå dette har PowerApps satt en grense for hvor mye data som kan behandles lokalt, på 500 poster.  Vi har valgt dette antallet slik at du fremdeles har full tilgang til små datasett, og du har mulighet til å finjustere bruken av store datasett, slik at du kan se delvise resultater.

Du må naturligvis være forsiktig når du bruker denne funksjonen, ettersom det kan være forvirrende for brukerne.  Overvei for eksempel en **Filter**-funksjon med en Selection-formel som ikke kan delegeres, en datakilde med over en million poster.  Siden filtreringen utføres lokalt, skannes bare de 500 første av de over en million postene.  Hvis ønsket post er post 501 eller 500.001, regnes den ikke med og returneres ikke av **Filter**.

Et annet sted hvor dette kan skape forvirring, er i mengdefunksjoner.  Ta **Gjennomsnitt** over en kolonne for datakilden for den samme millionposten.  Siden **Gjennomsnitt** fremdeles ikke kan delegeres, beregnes gjennomsnitt bare for de 500 første postene.  Du må være forsiktig så ikke et delvis svar feilaktig forstås som et fullstendig svar av en av brukerne av appen.

## <a name="changing-the-limit"></a>Å endre grensen

500 er standardnummeret for antallet poster.  Dette nummeret kan endres ved å gå til Fil-fanen, velge Appinnstillinger i navigasjonsruten til venstre, og se under Eksperimentelle funksjoner.  Her finner du innstillingen Dataradgrense for ikke-delegerbare spørringer, som du kan endre fra 1 til 2000.  Denne innstillingen gjelder for hele appen.

I enkelte tilfeller vet du at 2000 (eller 1000 eller 1500) er nok i ditt scenario.  Du kan med forsiktighet øke dette antallet for å passe med ditt scenario.  Vær oppmerksom på at mens du øker dette antallet, kan det hende at appytelsen forringes, spesielt for brede tabeller med mange kolonner.  Det beste svaret er fremdeles å alltid delegere det du kan.

Hvis du vil forsikre deg om at appen kan skalerer til store datasett, reduserer du denne innstillingen ned til 1.  Alt som ikke kan delegeres returnerer nå bare én enkelt post, og det bør være enkelt å oppdage når du tester appen.  Dette kan føre til at du ikke får noen overraskelser når du skal ta appkonseptet ditt videre til produksjon.

## <a name="blue-dot-suggestions"></a>Forslag med blå prikk
For å gjøre det enklere å vite hva som delegeres og hva som ikke delegeres, vises forslag i redigeringsopplevelsen med blå prikk når en formel inneholder noe som ikke kan delegeres.

Blå prikker vises bare på formler som opererer på datakilder som kan delegeres.  Hvis ikke du ser en blå prikk, og du tror formelen ikke delegeres riktig, kan du sammenligne datakildetypen med listen over <a href="#delegable-data-sources">datakilder som kan delegeres</a> ovenfor.

## <a name="examples"></a>Eksempler
I dette eksemplet bruker vi en SQL Server-tabell som inneholder produkter, i bestemte frukt, navn **[dbo].[Products]**.  PowerApps kan opprette en grunnleggende app på den nye skjermen med tre skjermer, som er koblet til denne datakilden:

![App med tre skjermer](./media/delegation-overview/products-afd.png)

Legg merke til formelen for **Elementer**-egenskapen til galleriet.  Den bruker funksjonene **SortByColumns** og **Search**, som begge kan delegeres.

Vi skriver inn **Apple** i kontrollen for innskriving av søketekst.  Hvis vi ser nøye etter, ser vi hvert øyeblikk prikker som beveger seg øverst på skjermen, mens den nye oppføringen i det nye søket behandles.  Prikkene som beveger seg indikerer at vi kommuniserer med SQL Server:

![Kontroll for innskriving av søketekst](./media/delegation-overview/products-apple.png)

Siden alt dette kan delegeres, selv om **[dbo].[Products]**-tabellen inneholder millioner av poster, finner vi dem likevel og ser raskt gjennom sidene i galleriet etter hvert som brukeren ruller gjennom resultatene.

Du vil oppdage at vi får treff for både «Apple» og «Pineapple».  **Search**-funksjonen finner et søkeord uansett hvor du er i en tekstkolonne.  La oss si at vi bare vil finne søkeordet i begynnelsen av navnet på frukten.  Vi kan bruke en annen funksjon som kan delegeres, **Filter**, med et mer komplisert søkeord (for enkelhets skyld fjerner vi **SortByColumns**-kallet):

![Å fjerne SortByColumns-kall](./media/delegation-overview/products-apple-bluedot.png)

Dette ser ut til å fungere. Det er bare **Apples** som vises nå, og ikke **Pineapple**.  Det vises imidlertid en blå prikk ved siden av galleriet, og det er en blå bølgete linje under deler av formelen.  Det vises også en blå prikk i miniatyrbildet for skjermen.  Hvis vi holder markøren over den blå prikken ved siden av galleriet, ser vi følgende:

![Slik holder du markøren over den blå prikken](./media/delegation-overview/products-apple-bluepopup.png)

Selv om vi bruker **Filter**, en funksjon som kan delegeres, med SQL Server som er en datakilde som kan delegeres, kan ikke formelen vi brukte i **Filter** delegeres.  **Mid** og **Len** kan ikke delegeres til en datakilde.

Likevel virket det, ikke sant?  Jo, på en måte.  Og dette er grunnen til at det vises en blå prikk og ikke et gult fareikon eller en rød bølgete feilmelding.  Hvis **[dbo].[Products]**-tabellen inneholder færre enn 500 poster, har dette fungert som det skulle.   Alle poster ble sendt til enheten, og **Filter** ble brukt lokalt.  

Hvis tabellen inneholder mer enn 500 poster, vises bare frukt som begynner med **Apple** *i de 500 første postene i tabellen* i galleriet.  Hvis **Apple, Fuji** vises som et navn i post 501 eller 500.001, blir ikke dette funnet.
