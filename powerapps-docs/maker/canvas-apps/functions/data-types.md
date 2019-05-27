---
title: Datatypene | Microsoft Docs
description: Datatyper i lerret-apper
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 05/19/2019
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: f9acc04a9159349075647ca4e318f15939a230f7
ms.sourcegitcommit: aa9f78c304fe46922aecfe3b3fadb6bda72dfb23
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 05/24/2019
ms.locfileid: "66216643"
---
# <a name="data-types-in-canvas-apps"></a>Datatyper i lerret-apper

Informasjon flyter gjennom en app i små, diskret verdier, som svært mye cellene i et regneark. For eksempel data i en **fødselsdag** felt og en **jubileum** feltet vil begge flyte gjennom som et **dato** verdi som inneholder året, måneden og dagen. Appen vet hvordan du formaterer disse verdiene, begrense inndata til det som er aktuelle for hver og dele verdiene med en database. Fødselsdager skiller seg fra jubileer til personer, men systemet håndterer dem på nøyaktig samme måte. I dette tilfellet **dato** er et eksempel på en [datatypen](https://en.wikipedia.org/wiki/Data_type).

Denne artikkelen inneholder detaljer om datatypene som lerret apper støtte. Når en app kobler til en ekstern datakilde, vil hver datatype i denne kilden er tilordnet til en datatype for lerret-apper.

| Datatype | Beskrivelse | Eksempler |
|-----------|-------------|---------|
| **Boolsk** | A *SANN* eller *USANN* verdi.  Kan brukes direkte i **Hvis**, **Filter** og andre funksjoner uten en sammenligning.  | *sann* |
| **Hyperkobling** | En tekststreng som inneholder en hyperkobling. | **"http://powerapps.microsoft.com"** |
| **Valuta** | En valutaverdi som er lagret i et flyttall. Valutaverdiene er de samme som antall verdier med Valutaformatering alternativer.  | **123**<br>**4.56** |
| **Bilde** | A [Universal Resource Identifier (URI)](https://en.wikipedia.org/wiki/Uniform_Resource_Identifier) formaterer tekststreng til et bilde i JPEG, PNG, SVG, GIF og andre vanlige web-bilde. | **MyImage** lagt til som en app-ressurs<br>**"https://northwindtraders.com/logo.jpg"**<br>**«appres://blobmanager/7b12ffa2...»** |
| **Farge** | En fargespesifikasjon, inkludert en alfa-kanal. | **Color.Red**<br>**ColorValue ("#102030»)**<br>**RGBA (255, 128, 0, 0,5)** |
| **Dato** | En dato uten et klokkeslett, i tidssonen til appens brukeren. | **Dato (2019, 5, 16)** |
| **Dato og klokkeslett** | En dato med et klokkeslett, i tidssonen til appens brukeren. | **DateTimeValue («mai 16 2019 1:23:09 PM")** |
| **GUID** | A [globalt unik identifikator](https://en.wikipedia.org/wiki/Universally_unique_identifier). | **GUID()**<br>**GUID( "123e4567-e89b-12d3-a456-426655440000" )** |
| **Media** | En URI-tekststreng til en video eller lyd registrering. | **MyVideo** lagt til som en app-ressurs<br>**"https://northwindtraders.com/intro.mp4"**<br>**«appres://blobmanager/3ba411c...»** |
| **Tall** | Et flyttall. | **123**<br>**-4.567**<br>**8.903e121** |
| **Alternativsett** | Et valg mellom en rekke alternativer, støttet av et tall. Denne datatypen kombinerer en lokaliserbare tekstetikett med en numerisk verdi. Etiketten vises i appen, og den numeriske verdien som er lagret og brukes til sammenligninger. | **ThisItem.OrderStatus** |
| **Post** | En oversikt over dataverdier. Denne sammensatte datatypen inneholder forekomster av andre datatyper som er oppført i dette emnet. Mer informasjon: [Å arbeide med tabeller](../working-with-tables.md). | **{Selskapet: «Northwind Traders»,<br>ansatte: 35, <br>NonProfit: false}** |
| **Registrer referanse** | En referanse til en post i en enhet. Slike referanser brukes ofte med polymorfisk oppslag. Mer informasjon: [Arbeide med referanser](../working-with-references.md).| **First(accounts). Eier** |
| **Tabell** | En tabell med poster.  Alle postene må ha samme navn for sine felt med samme datatyper, og utelatt felt som skal behandles som *tom*. Denne sammensatte datatypen inneholder forekomster av andre datatyper som er oppført i dette emnet. Mer informasjon: [Å arbeide med tabeller](../working-with-tables.md). | **Tabellen ({fornavn: «Sidney»,<br>etternavn: "Higa"}, <br>{fornavn: «Nancy»,<br>etternavn: "Anderson" } )**
| **Tekst** | En streng til Unicode-tekst. | **"Hello, World"** |
| **Tid** | En periode uten en dato i tidssonen til appens brukeren. | **Tid (11, 23, 45)** |
| **To alternativet** | Et valg fra et sett med to alternativer, støttet av en boolsk verdi. Denne datatypen kombinerer en lokaliserbare tekstetikett med en boolsk verdi. Etiketten vises i appen, og den boolske verdien er lagret og brukes til sammenligninger. | **ThisItem.Taxable** |

Mange av disse datatypene ligner og har samme underliggende representasjon, for eksempel en **hyperkobling** feltet som blir behandlet som **tekst**.  Ekstra datatypene gir bedre standard opplevelser i skjemaer og andre kontroller.

## <a name="blank"></a>Blank

Alle datatyper kan ha en verdi av *tom* (med andre ord, ingen verdi). Begrepet "null" brukes ofte i databaser for dette konseptet.  

Bruk den **tom** funksjonen med den **angi** eller **Patch** funksjonen til å angi en variabel eller felt som skal *tom*. For eksempel **Set (x, Blank())** fjerner enhver verdi i den globale variabelen **x**.  

Test for en *tom* verdi ved hjelp av den [ **IsBlank** ](function-isblank-isempty.md) funksjonen. Erstatt mulig *tom* verdier med ikke -*tom* verdier ved hjelp av den [ **Coalesce** ](function-isblank-isempty.md) funksjonen.

Fordi alle datatyper støtter *tom*, **boolsk** og **to alternativet** datatyper effektivt har tre verdier.

## <a name="text-hyperlink-image-and-media"></a>Tekst, hyperkobling, bilde og Media

Alle de fire disse datatypene er basert på en [Unicode](https://en.wikipedia.org/wiki/Unicode) tekststreng.

### <a name="image-and-media-resources"></a>Bilde- og Media ressurser

Gjennom den **filen** -menyen, kan du legge til bilde, video og lyd filer som app-ressurser. Navnet på den importerte filen blir ressursnavnet i appen. I denne grafikken Northwind Traders logoen, som heter **nwindlogo**, har blitt lagt til en app:

![](media/data-types/nwind-resource.png)

Hvis du vil bruke denne ressursen i en app, angir du den i den **bilde** -egenskapen for en [ **bilde** ](../controls/control-image.md) kontroll:

![](media/data-types/nwind-image.png)

### <a name="uris-for-images-and-other-media"></a>URI-er for bilder og andre medier

Du kan gå litt dypere inn i det siste eksemplet ved å angi den **tekst** -egenskapen for en [ **etikett** ](../controls/control-text-box.md) kontrollen til **nwindlogo**. Etiketten viser en tekststreng:

![](media/data-types/nwind-text.png)

Lerretsapper referere til hvert bilde eller andre mediefil, enten den er i skyen eller lagt til som en app-ressurs, av en tekststreng for URI.

For eksempel den **bilde** -egenskapen for en bildekontroll godtar ikke bare app-ressurser, men også koblinger til bilder på nettet, som « https://northwindtraders.com/logo.jpg». Egenskapen godtar også innebygde bilder som bruker den [data-URI-skjemaet](https://en.wikipedia.org/wiki/Data_URI_scheme), som i dette eksemplet:

```powerapps-dot
"data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAkAAAAFAQMAAACtnVQoAAAABlBMVEUAAAB0J3UMNU6VAAAAAXRSTlMAQObYZgAAABRJREFUCNdjUGJgCGVg6GgAkkA2AA8/AffqCEBsAAAAAElFTkSuQmCC"
```

Denne URI-en vises en skaleres opp versjon to lilla ruter:

![](media/data-types/double-diamonds.png)

Du kan vise de nyeste bildet som i en [ **kamera** ](../controls/control-camera.md) kontroll hvis du angir den **bilde** -egenskapen for en kontroll til den **Photo** egenskapen for kamera-kontrollen. Appen inneholder bildet i minnet, og den **Photo** -egenskapen for kamera-kontrollen returnerer en URI-referanse til bildet. Du kan for eksempel ta et bilde, og i kameraet **Photo** egenskapen kan returnere **"appres://blobmanager/7b12ffa2ea4547e5b3812cb1c7b0a2a0/1"** .

Du bruker en URI for å referere til et bilde eller en annen mediefil som er lagret i en database. På den måten ikke appen hente de faktiske dataene før det faktisk er nødvendig. For eksempel et vedlegg i en Common Data Service-enhet kan returnere **«appres://datasources/Contacts/table/...»** Du kan vise dette bildet som i eksemplet kamera, ved å angi den **bilde** -egenskapen for en kontroll til denne, som henter de binære dataene.

Når du lagrer en media-datatype, for eksempel et bilde, en database, sender appen til selve bildet eller media data, ikke URI-referanse.

### <a name="size-limits"></a>Begrensninger for filstørrelse

Som tekststrenger og URIer har disse datatypene ingen forhåndsangitte grensen på deres lengde.

De binære dataene som disse datatypene refererer også har ingen forhåndsinnstilte grense på størrelsen. For eksempel et bilde som registreres via kamera-kontrollen som nå er referert til som **"appres: / /..."** kan være som store og høy oppløsning, som kan komme enhetens kamera. Oppløsningen, bildefrekvensen og andre attributter for mediefiler ikke er begrenset av datatypen, men bestemte kontroller for å spille og registrering av media kan ha sin egen begrensninger.

Alle datastørrelser er imidlertid underlagt mengden tilgjengelig minne i appen. Weblesere som kjører på en stasjonær datamaskin vanligvis støtter mer enn 100 MB med data. Mengden tilgjengelig minne på en enhet som for eksempel en telefon kan imidlertid være langt lavere, vanligvis i området 30 – 70 megabyte. Hvis du vil finne ut om appen din kjører i disse grensene, kan du teste vanlige scenarier på alle enheter som den skal kjøres.

Som en anbefalt fremgangsmåte, holder du data i minnet bare så lang etter behov. Laste opp bilder til en database, så snart som mulig; Last ned bilder bare når appens brukeren ber om.

## <a name="number-and-currency"></a>Tall og valuta

**Tall** og **valuta** datatypene Bruk den [IEEE 754 flyttallet med dobbel presisjon-standard](https://en.wikipedia.org/wiki/IEEE_754). Denne standarden tilbyr et stort utvalg av tallene som skal fungere, fra –1.79769 x 10<sup>308</sup> til 1.79769 x 10<sup>308</sup>. Den minste verdien som kan vises er 5 x 10<sup>–324</sup>.

Lerretsapper kan nøyaktig representere hele tall (eller heltall) mellom –9,007,199,254,740,991 (– (2<sup>53</sup> – 1)) og 9,007,199,254,740,991 (2<sup>53</sup> – 1), inklusiv. Dette området er større enn 32-biters (eller 4-byte) heltallsdatatypene som vanligvis bruker databaser. Imidlertid kan ikke lerretsapper representere datatyper for 64-biters (eller 8-byte) heltall. Du ønsker kanskje å lagre nummeret i et tekstfelt eller bruke en beregnet kolonne til å lage en kopi av tallet i et tekstfelt, slik at den er tilordnet til en **tekst** datatype i lerret-app. På denne måten, kan du holde, vise, og angi disse verdiene, i tillegg til sammenligning dem for å finne ut om de er like. men kan ikke du utføre numeriske beregninger på dem i dette skjemaet.

Flyttall aritmetisk er tilnærmet, slik at det noen ganger kan gi uventede resultater med mange dokumenterte eksempler. Du kan forvente formelen **55 / 100 * 100** til å returnere nøyaktig 55 og **(55 / 100 * 100) – 55** til å returnere nøyaktig null. Sistnevnte formelen returnerer imidlertid 7.1054 x 10<sup>–15</sup>, som er svært liten, men ikke er null. Den svært liten forskjellen vanligvis føre til ikke et problem, og appen Runder av den unna når viser resultatet. Små forskjeller kan imidlertid sammensatte i etterfølgende beregninger og ser ut til å gi feil svar.

Databasesystemer ofte lagre valutaer og utfører beregninger ved hjelp av desimal matematiske, som tilbyr et mindre område, men større kontroll over presisjonen. Som standard lerret apper kartet valutaer inn og ut flyttallet med verdier. Resultatet kan derfor være forskjellig fra beregninger som utføres i en opprinnelig decimal-datatype. Hvis denne typen avvik vil føre til problemer, kan du arbeide med disse verdiene som **tekst**, på samme måte som du kanskje med store heltall som er beskrevet tidligere i denne delen.

## <a name="date-time-and-datetime"></a>Dato, klokkeslett og dato/klokkeslett

### <a name="time-zones"></a>Tidssoner

Dato/klokkeslett verdier fall i disse kategoriene:

- **Brukeren lokal**: Disse verdiene er lagret i [UTC (universaltid)](https://en.wikipedia.org/wiki/Coordinated_Universal_Time), men appen brukerens tidssone påvirker hvordan appen viser disse verdiene, og hvordan appen brukeren angir dem. For eksempel vises for samme øyeblikket på en annen måte til en bruker i Canada enn det gjør til en bruker i Japan.
- **Uavhengig av tidssone**: Appen viser disse verdiene på samme måte, og appen brukeren angir dem på samme måte, uavhengig av tidssone. Det samme øyeblikket vises på samme måte for en bruker i Canada som den gjør til en bruker i Japan. App-forfattere som forventer ikke at deres apper som kjører i ulike tidssoner bruke disse verdiene fordi de er samlet enklere.

Denne tabellen viser noen eksempler:

| Dato/klokkeslett-type | Verdien som er lagret i databasen | Verdien som vises, og angitt 7 timer west of UTC | Verdien som vises, og angitt 4 timer east of UTC |
|--------------------------|------------------------------|------------------------------|
| **Lokal bruker** | Søndag,&nbsp;kan&nbsp;19,&nbsp;2019<br>04:00:00 | Lørdag,&nbsp;kan&nbsp;18,&nbsp;2019<br>9:00 PM | Søndag,&nbsp;kan&nbsp;19,&nbsp;2019<br>8.00 |
| **Uavhengig av tidssone** | Søndag,&nbsp;kan&nbsp;19,&nbsp;2019<br>04:00:00 | Søndag,&nbsp;kan&nbsp;19,&nbsp;2019<br>04:00:00 | Søndag,&nbsp;kan&nbsp;19,&nbsp;2019<br>04:00:00 | 

For **bruker lokal** dato/klokkeslett, lerret-apper bruker tidssonen for nettleser eller enhet, men modelldrevne apper Bruk brukerens innstillingen i Common Data Service. Disse innstillingene vanligvis samsvare med, men resultatene vil variere Hvis disse innstillingene er forskjellige.

### <a name="numeric-equivalents"></a>Numeriske tilsvarende

Lerretsapper holder og beregne alle dato/klokkeslett verdier, om **bruker lokal** eller **uavhengig av tidssone** i UTC. Appen oversetter verdiene basert på app brukerens tidssone ved visning av dem og når appen brukeren angir dem.

Når en lerretsapp leser en **uavhengig av tidssone** verdi fra en datakilde eller skrivinger slike en verdi til en datakilde, appen automatisk justerer verdien som skal kompenserer for tidssonen for appens brukeren. Appen behandler deretter verdien som en UTC-verdi, som med alle andre dato/klokkeslett-verdier i appen. På grunn av denne kompensasjon, opprinnelige **uavhengig av tidssone** verdien som vises når appen justerer UTC-verdien for appen brukerens tidssone.

Du kan se denne virkemåte nærmere ved hjelp av den [ **verdien** ](function-value.md) funksjonen til å få tilgang til den underliggende numeriske verdien for en dato/klokkeslett-verdi. Denne funksjonen returnerer dato/klokkeslett-verdi som antall millisekunder siden 1. januar 1970 00:00:00.000 UTC.

Fordi hver dato/klokkeslett-verdi er i bruk i UTC, formelen **verdi (dato (1970, 1, 1))** ikke returnere null i de fleste deler av verden fordi den **dato** -funksjonen returnerer en dato i UTC. For eksempel vil formelen returnere 28,800,000 i en tidssone som skal forskyves fra UTC åtte timer. Dette nummeret gjenspeiler antall millisekunder i åtte timer.

Gå tilbake til vårt eksempel fra ovenfor:

| Dato/klokkeslett-type | Verdien som er lagret i databasen | Verdien som vises, og angitt 7 timer west of UTC | **Verdien** -funksjonen returnerer |
|--------------------------|------------------------------|------------------------------|
| **Lokal bruker** | Søndag,&nbsp;kan&nbsp;19,&nbsp;2019<br>04:00:00 | Lørdag,&nbsp;kan&nbsp;18,&nbsp;2019<br>9:00 PM | 1,558,238,400,000<br> (Søndag,&nbsp;kan&nbsp;19,&nbsp;2019<br>04:00:00 UTC) |
| **Uavhengig av tidssone** | Søndag,&nbsp;kan&nbsp;19,&nbsp;2019<br>04:00:00 | Søndag,&nbsp;kan&nbsp;19,&nbsp;2019<br>04:00:00 |1,558,263,600,000<br> (Søndag,&nbsp;kan&nbsp;19,&nbsp;2019<br>11:00 AM UTC) |

### <a name="converting-unix-times"></a>Konvertering av Unix ganger

UNIX ganger gjenspeiler antallet sekunder siden 1. januar 1970 00:00:00 UTC. Ettersom lerret-apper bruker millisekunder i stedet for sekunder, kan du konvertere mellom to ved å multiplisere eller å dele på 1000.

Unix-tid viser for eksempel 9. September 2001 på 01:46:40 UTC som 1 000 000 000. Å vise som dato/klokkeslett-verdi i en lerretsapp, multiplisere dette nummeret med 1000 å konvertere den til millisekunder, og deretter bruke den i en [ **tekst** ](function-text.md) funksjonen. Formelen **tekst (1000000000 * 1000, DateTimeFormat.UTC)** returnerer strengen **2001-09-09T01:46:40.000Z**.

Denne funksjonen returnerer imidlertid **lørdag 8. September 2001 18:46:40** Hvis du bruker den **DateTimeFormat.LongDateTime24** format i en tidssone som skal forskyves-7 timer fra UTC (7 timer west of UTC). Dette resultatet viser den **DateTime** verdi basert på riktig måte på den lokale tidssonen.

Hvis du vil konvertere til en Unix-tid, kan du dele resultatet fra **verdien** ved 1000:
<br>**RoundDown (verdi (UnixTime) / 1000, 0)**

Hvis du trenger Unix-tid i en **dato** verdien for ytterligere beregninger eller vise i PowerApps, bruker du denne formelen:
<br>**DateAdd (dato (1970,1,1), UnixTime, sekunder)**

### <a name="sql-server"></a>SQL Server

SQL Server har [ **Datetime**, **Datetime2**, og andre dato/klokkeslett-datatyper](https://docs.microsoft.com/sql/t-sql/functions/date-and-time-data-types-and-functions-transact-sql?view=sql-server-2017) som inkluderer ikke en Tidssoneforskyvning og ikke indikerer hvilken tidssone de er i. Lerretsapper antar disse verdiene er lagret i UTC og behandle dem som **bruker lokal**. Hvis verdiene er ment å være tidssone uavhengig, korrigere for UTC-oversettelser ved hjelp av den [ **TimeZoneOffset** ](function-dateadd-datediff.md#converting-to-utc) funksjonen.

Lerret-apper bruker inkludert tidssone informasjonen i **Datetimeoffset** felt under konvertering av en verdi til appens intern UTC-representasjonen. Appene alltid bruke UTC som tidssonen (null Tidssoneforskyvning) når de skriver data.

Lerretsapper lese og skrive til verdiene i den [ **tid** ](https://docs.microsoft.com/en-us/sql/t-sql/data-types/time-transact-sql) datatype i SQL Server som tekststrenger i den [ISO 8601-format for varighet](https://en.wikipedia.org/wiki/ISO_8601#Durations). Du må for eksempel analysere denne strengformat og bruke den [ **tid** ](function-date-time.md) funksjonen til å konvertere tekststrengen **"PT2H1M39S"** til en **tid** verdi:

```powerapps-dot
First(
    ForAll(
        MatchAll( "PT2H1M39S", "PT(?:(?<hours>\d+)H)?(?:(?<minutes>\d+)M)?(?:(?<seconds>\d+)S)?" ),
        Time( Value( hours ), Value( minutes ), Value( seconds ) )
    )
).Value
```

### <a name="mixing-date-and-time-information"></a>Blanding av informasjon om dato og klokkeslett

**Dato**, **tid**, og **DateTime** har forskjellige navn, men alle inneholder samme informasjon om datoer og klokkeslett. 

A **dato** verdi kan inkludere informasjon om klokkeslett med den, som vanligvis er midnatt. A **tid** verdi kan overføre datoinformasjon som, som vanligvis er 1. januar 1970. Common Data Service-lagrer også informasjon om klokkeslett med en **bare dato** feltet viser men bare datoinformasjonen som standard. På samme måte vil lerretsapper noen ganger skille mellom disse datatypene til å bestemme standardformater og kontroller.

Å legge til og trekke dato- og klokkeslettverdier direkte er ikke anbefalt fordi tidssone og andre konverteringer kan føre til at forvirrende resultater. Enten å bruke den **verdien** funksjonen til å konvertere dato/klokkeslett-verdiene til millisekunder først og tar hensyn til app brukerens tidssone, eller bruk den [ **DateAdd** ](function-dateadd-datediff.md) og [ **DateDiff** ](function-dateadd-datediff.md) funksjoner for å legge til eller trekke fra en av disse verdiene.

## <a name="option-sets-and-two-options"></a>Alternativsett og to alternativer

Alternativsett og datatyper for to-alternativet gir deg en to eller flere alternativer for en appbruker til å velge. For eksempel en **ordrestatus** alternativsett kan tilby valgene **ny**, **levert**, **fakturert**, og **lukket** . Datatypen for to-alternativet gir bare to valg.

Begge disse datatypene Vis etikettene i en tekststreng kontekst. For eksempel en etikettkontrollen viser ett av alternativene ordrestatus Hvis kontrollens **tekst** egenskapen er satt til en formel som refererer til denne alternativsett. Alternativet etiketter lokaliseres for app-brukere på forskjellige steder.

Når en appbruker velger et alternativ, og lagrer denne endringen, overfører appen data til databasen, som lagrer dataene i en representasjon som er uavhengig av språk. Et alternativ i et alternativsett er overført og lagret som et tall, og et alternativ i en datatype for to-alternativet er overført og lagret som en boolsk verdi.

Etikettene er bare for visning. Du kan ikke utføre direkte sammenligninger med etikettene fordi de er spesifikk for et språk. Hver alternativsett har i stedet en opplisting som fungerer med den underliggende tall eller en boolsk verdi. Du kan for eksempel bruke denne formelen:

`If( ThisItem.OrderStatus = "Active", ...`

Men du kan bruke denne formelen:

`If( ThisItem.OrderStatus = OrderStatus.Active, ...`

For globale alternativsett (hvilke enheter dele), navnet på alternativsett opplistingen tilsvarer navnet på det globale alternativsettet. For lokale alternativsett (som er begrenset til en enhet), navnet kan inneholde navnet på enheten. Denne virkemåten unngår konflikter hvis flere enheter har alternativsett som har samme navn. For eksempel den **kontoer** enheten kan ha en **OrderStatus** alternativsett, og navnet kan være **OrderStatus (kontoer)** . Dette navnet inneholder én eller flere mellomrom og parenteser, slik at du må omslutte den med enkle anførselstegn hvis du henvise til i en formel.

I tillegg to-verdiene kan også oppfører seg som boolske verdier. For eksempel en to-alternativ verdi med navnet **TaxStatus** kanskje etikettene **avgiftspliktig** og **ikke-avgiftspliktig**, som tilsvarer *SANN* og *USANN* henholdsvis. For å demonstrere, kan du bruke denne formelen:

`If( ThisItem.Taxable = TaxStatus.Taxable, ...`

Du kan også bruke denne tilsvarende formelen:

`If( ThisItem.Taxable, ...`