---
title: Forstå delegering i en lerretsapp | Microsoft Docs
description: Bruk delegering for behandling av store datasett på en effektiv måte, i en lerretsapp.
author: lancedMicrosoft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 07/05/2018
ms.author: lanced
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 0ac78340f344ce42fd68d18940b1aaca41412a96
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/24/2018
ms.locfileid: "42829755"
---
# <a name="understand-delegation-in-a-canvas-app"></a>Forstå delegering i en lerretsapp
PowerApps inneholder et kraftig sett med funksjoner for filtrering, sortering og forming av datatabeller i en lerretsapp, blant annet funksjonene: **[Filter](functions/function-filter-lookup.md)**, **[Sort](functions/function-sort.md)** og **[AddColumns](functions/function-table-shaping.md)**. Med disse funksjonene kan du gi brukerne fokusert tilgang til informasjonen de trenger. For de med databasebakgrunn vil bruk av disse funksjonene tilsvare skriving av en databasespørring.

Nøkkelen til utvikling av effektive apper er å minimere datamengden som sendes til enheten din. Det er kanskje nok med noen få poster blant flere millioner, eventuelt kan én enkelt akkumulert verdi representere tusener av poster. Det kan også hende det bare er mulig å hente det første settet med poster, og resten føres inn når brukeren viser at det trengs flere. Fokus kan kraftig redusere prosesskraften, minnet og nettverksbåndbredden som appen trenger, noe som resulterer i raskere svartider for brukerne, selv på telefoner som er tilkoblet via et mobilnettverk. 

*Delegering* er der omfattende PowerApps-formler oppfyller behovet for å minimere datamengden som flyttes over nettverket. I korte trekk betyr dette at PowerApps delegerer behandlingen av data til datakilden, i stedet for å flytte data til appen for lokal behandling.

Når dette begynner å bli komplisert, hvilket er grunnen til at denne artikkelen finnes, er det fordi ikke alt som kan uttrykkes i en PowerApps-formel kan delegeres til alle datakilder. PowerApps-språket etterligner Excels formelspråk, utformet med komplett og umiddelbar tilgang til en fullstendig arbeidsbok i minnet, med et bredt utvalg manipuleringsfunksjoner for tall og tekst. Derfor er PowerApps-språket mer omfattende enn det som støttes av de fleste datakilder, inkludert robuste databasemotorer som SQL Server.

**Arbeid med store datasett krever at du bruker datakilder og formler som kan delegeres.**  Dette er den eneste måten å sikre at appen fungerer bra på, og at brukere får tilgang til informasjonen de trenger. Vær oppmerksom på delegeringsadvarsler som identifiserer steder der delegering ikke er mulig. Hvis du arbeider med små datasett (færre enn 500 poster), kan du bruke alle datakilder og formler siden appen kan behandle data lokalt hvis formelen ikke kan delegeres. 

> [!NOTE]
> Delegeringsadvarsler ble tidligere flagget i PowerApps som «blå prikk»-forslag, men delegeringsforslag har i ettertid blitt klassifisert på nytt som advarsler. Hvis dataene i datakilden overskrider 500 poster og en funksjon ikke kan delegeres, kan det hende at PowerApps ikke kan hente alle dataene og at appen har feilaktige resultater. Delegeringsadvarsler hjelper deg med å behandle appen slik at den har riktige resultater.

## <a name="delegable-data-sources"></a>Datakilder som kan delegeres
Gå til [delegeringslisten](delegation-list.md) for å se den fullstendige listen over hvilke datakilder som støtter delegering, og i hvilken grad.

Vi fortsetter å legge til delegeringsstøtte i eksisterende datakilder, i tillegg til å legge til flere datakilder.

Importerte Excel-arbeidsbøker (som bruker datakilden «Legg til statiske data i appen»), samlinger og tabeller som er lagret i kontekstvariabler, krever ikke delegering. Alle disse dataene ligger allerede i minnet, og det fullstendige PowerApps-språket kan brukes.

## <a name="delegable-functions"></a>Funksjoner som kan delegeres
Neste trinn er å bruke bare de formlene som kan delegeres. Formelelementene som kan delegeres er inkludert her. Alle datakilder er imidlertid forskjellige, og det er ikke alle som støtter alle disse elementene. Se etter delegeringsadvarsler i en bestemt formel.

Disse listene endres over tid. Vi arbeider mot å støtte flere funksjoner og operatorer med delegering.

### <a name="filter-functions"></a>Filtreringsfunksjoner
**[Filter](functions/function-filter-lookup.md)**, **[Search](functions/function-filter-lookup.md)** og **[LookUp](functions/function-filter-lookup.md)** kan delegeres.  

Du kan bruke disse med kolonner i tabellen for å velge riktige poster i funksjonene **Filter** og **LookUp**:

* **[And](functions/function-logicals.md)** (inkludert **[&&](functions/operators.md)**), **[Or](functions/function-logicals.md)** (inkludert **[||](functions/operators.md)**), **[Not](functions/function-logicals.md)** (inkludert **[!](functions/operators.md)**)
* **[In](functions/operators.md)**
* **[=](functions/operators.md)**, **[<>](functions/operators.md)**, **[>=](functions/operators.md)**, **[<=](functions/operators.md)**, **[>](functions/operators.md)**, **[<](functions/operators.md)**
* **[+](functions/operators.md)**, **[-](functions/operators.md)**
* **[TrimEnds](functions/function-trim.md)**
* **[IsBlank](functions/function-isblank-isempty.md)**
* **[StartsWith](functions/function-startswith.md)**
* Konstante verdier som er de samme i alle postene, for eksempel kontrollegenskaper og [globale variabler og kontekstvariabler](working-with-variables.md).

Du kan også bruke deler av formelen som evalueres som en konstant verdi for alle poster. **Left( Language(), 2 )** avhenger for eksempel ikke av andre kolonner i posten, og returner derfor samme verdi for alle poster. Dette er en konstant. Bruk av kontekstvariabler, samlinger og signaler er kanskje ikke konstant og vil derfor hindre at **Filter** og **LookUp** delegeres.  

Den forrige listen inkluderer ikke disse viktige elementene:

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
**[Sum](functions/function-aggregates.md)**, **[Average](functions/function-aggregates.md)**, **[Min](functions/function-aggregates.md)**, and **[Max](functions/function-aggregates.md)** kan delegeres. Bare et begrenset antall datakilder støtter denne delegeringen nå. Kontroller [delegeringslisten](delegation-list.md) for å finne mer informasjon.

Tellingsfunksjoner som **[CountRows](functions/function-table-counts.md)**, **[CountA](functions/function-table-counts.md)** og **[Count](functions/function-table-counts.md)** kan ikke delegeres.

Andre mengdefunksjoner, for eksempel **[StdevP](functions/function-aggregates.md)** og**[VarP](functions/function-aggregates.md)**, kan ikke delegeres.

## <a name="non-delegable-functions"></a>Funksjoner som ikke kan delegeres
Ingen andre funksjoner støtter delegering, herunder disse viktige funksjonene:

* Tabellbearbeiding: **[AddColumns](functions/function-table-shaping.md)**, **[DropColumns](functions/function-table-shaping.md)**, **[ShowColumns](functions/function-table-shaping.md)**, ...
* **[First](functions/function-first-last.md)**, **[FirstN](functions/function-first-last.md)**, **[Last](functions/function-first-last.md)**, **[LastN](functions/function-first-last.md)**
* **[Valg](functions/function-choices.md)**
* **[Concat](functions/function-concatenate.md)**
* **[Collect](functions/function-clear-collect-clearcollect.md)**, **[ClearCollect](functions/function-clear-collect-clearcollect.md)**
* **[CountIf](functions/function-table-counts.md)**, **[RemoveIf](functions/function-remove-removeif.md)**, **[UpdateIf](functions/function-update-updateif.md)**
* **[GroupBy](functions/function-groupby.md)**, **[Ungroup](functions/function-groupby.md)**

Et vanlig mønster er å bruke **AddColumns** og **LookUp** for å slå sammen informasjon fra én tabell til en annen. Dette kalles vanligvis Sammenføyning på dataspråket.  Eksempel:

**AddColumns( Products, "Supplier Name", LookUp( Suppliers, Suppliers.ID = Product.SupplierID ).Name )**

Selv om **Produkter** og **Leverandører** er datakilder som kan delegeres, og **Lookup** er en funksjon som kan delegeres, kan ikke funksjonen **AddColumns** delegeres.  Resultatet av hele formelen begrenses til den første delen av **Produkter**-datakilden.  

Siden **LookUp**-funksjonen og tilhørende datakilde kan delegeres, finnes det treff for **Leverandører** overalt i datakilden, selv om den er stor. En potensiell ulempe er at **LookUp** oppretter separate kall til datakilden for hver av disse første postene i **Produkter**, noe som forårsaker mye støy på nettverket. Hvis **Leverandører** er liten nok, og ikke endres ofte, kan datakilden bufres i appen med et **Collect**-kall når appen starter opp (ved hjelp av [**OnVisible**](controls/control-screen.md) på åpningsskjermen), og bruke **Oppslag** i stedet.  

## <a name="non-delegable-limits"></a>Grenser for ikke-delegering
Formler som ikke kan delegeres, behandles lokalt. Dette gjør det mulig å bruke hele formelspråket til PowerApps. Dette har likevel sin pris. Alle dataene må sendes til enheten først, noe som innebærer å hente en stor mengde data over nettverket. Dette kan ta tid, noe som kan gi inntrykk av at appen er treg eller har krasjet.

For å unngå dette har PowerApps satt en grense for hvor mye data som kan behandles lokalt, på 500 poster.  Vi har valgt dette antallet slik at du fremdeles har full tilgang til små datasett, og du har mulighet til å finjustere bruken av store datasett, slik at du kan se delvise resultater.

Du må naturligvis være forsiktig når du bruker denne funksjonen, ettersom det kan være forvirrende for brukerne. Overvei for eksempel en **Filter**-funksjon med en Selection-formel som ikke kan delegeres, i stedet for en datakilde med over en million poster. Siden filtreringen utføres lokalt, skannes bare de 500 første postene. Hvis ønsket post er post 501 eller 500.001, regnes den ikke med, og det returneres ikke av **Filter**.

Mengdefunksjoner kan også føre til forvirring. Ta **Gjennomsnitt** over en kolonne for den samme datakilden med en million poster. **Gjennomsnitt** kan ikke delegeres for øyeblikket, derfor beregnes gjennomsnitt bare for de 500 første postene. Du må være forsiktig så ikke et delvis svar feilaktig forstås som et fullstendig svar av en av brukerne av appen.

## <a name="changing-the-limit"></a>Å endre grensen
500 er standardantallet poster, men du kan endre dette nummeret i hele appen:

1. Velg **Appinnstillinger** på **Fil**-fanen.
2. Endre innstillingen **Dataradgrense for ikke-delegerbare spørringer** under **Eksperimentelle funksjoner** fra 1 til 2000.

I enkelte tilfeller vet du at 2000 (eller 1000 eller 1500) er nok i ditt scenario. Du kan med forsiktighet øke dette antallet for å passe med ditt scenario. Mens du øker dette antallet, kan det hende at appytelsen forringes, spesielt for brede tabeller med mange kolonner. Det beste svaret er fremdeles å delegere så mye du kan.

Hvis du vil forsikre deg om at appen kan skalerer til store datasett, reduserer du denne innstillingen ned til 1. Alt som ikke kan delegeres returnerer én enkelt post, og det bør være enkelt å oppdage når du tester appen. Dette kan føre til at du ikke får noen overraskelser når du skal ta appkonseptet ditt videre til produksjon.

## <a name="delegation-warnings"></a>Delegeringsadvarsler
For at det skal bli enklere å vite hva som blir og ikke blir delegert, gir PowerApps en advarsel (gul trekant) når du oppretter en formel som inneholder noe som ikke kan delegeres.

Delegeringsadvarsler vises bare på formler som opererer på datakilder som kan delegeres. Hvis ikke du ser en advarsel, og du tror formelen ikke delegeres riktig, kan du sammenligne datakildetypen med listen over [datakilder som kan delegeres](delegation-overview.md#delegable-data-sources) tidligere i dette emnet.

## <a name="examples"></a>Eksempler
I dette eksemplet skal du automatisk generere en app med tre skjermer basert på en SQL Server-tabell med navn **[dbo].[Fruit]**. Hvis du vil ha informasjon om hvordan du genererer en app, kan du ta i bruk lignende prinsipper i [emnet om Common Data Service for Apps](data-platform-create-app.md) for SQL Server.

![App med tre skjermer](./media/delegation-overview/products-afd.png)

**Elementer**-egenskapen til galleriet er angitt til en formel som inneholder funksjonene **SortByColumns** og **Search**, og begge kan delegeres.

Skriv inn **Eple** i søkeboksen.

Bevegelige prikker vises kjapt nær toppen av skjermen mens appen kommuniserer med SQL Server for å behandle søkeforespørselen. Alle postene som oppfyller søkekriteriene vises, selv om datakilden inneholder flere millioner poster.

![Kontroll for innskriving av søketekst](./media/delegation-overview/products-apple.png)

Søkeresultatene inkluderer **Epler**, **Villepler**, and **Ananas** fordi **Search**-funksjonen søker over alt i en tekstkolonne. Hvis du ønsket å finne poster som bare inneholdt søkeordet i starten av navnet på frukten, kan du bruke en annen delegerbar funksjon**Filter**, med mer kompliserte søkeord. (Fjern for enkelhets skyld **SortByColumns**-kallet.)

![Å fjerne SortByColumns-kall](./media/delegation-overview/products-apple-delegationwarning.png)

De nye resultatene inneholder nå **Epler**, men ikke **Villepler** eller **Ananas**.  En gul trekant vises imidlertid ved siden av galleriet (og i miniatyrbildet for skjermen hvis navigasjonsfeltet til venstre vises miniatyrbilder) og en blå, bølgete linje vises under en del av formelen. Hver av disse elementene angir en advarsel. Hvis du beveger pekeren over den gule trekanten ved siden av galleriet, vises denne meldingen:

![Å bevege pekeren over en delegeringsadvarsel](./media/delegation-overview/products-apple-yellowwarning.png)

SQL Server er en delegerbar datakilde og **Filter** er en delegerbar funksjon. **Mid** og **Len** kan imidlertid ikke delegeres til en datakilde.

Likevel virket det, ikke sant? Jo, på en måte. Og det er grunnen til at dette er en advarsel og ikke en rød, bølgete krusedull.

- Hvis tabellen inneholder færre enn 500 poster, fungerer formelen perfekt. Alle poster ble sendt til enheten, og **Filter** ble brukt lokalt.
- Hvis tabellen inneholder mer enn 500 poster, returnerer ikke formelen 501 eller høyere, selv om den samsvarer med vilkårene.
