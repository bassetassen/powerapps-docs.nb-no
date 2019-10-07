---
title: Data typer | Microsoft Docs
description: Data typer i lerret apper
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 05/19/2019
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 592399e6b5a95d27e5c0afe48541d04d444528bb
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/07/2019
ms.locfileid: "71985578"
---
# <a name="data-types-in-canvas-apps"></a>Data typer i lerret apper

Informasjons flyter gjennom en app i små, diskrete verdier, svært mye som cellene i et regne ark. For eksempel vil data i et **fødsels dag** -felt og et **jubileums** felt begge flyte gjennom som en **dato** verdi som inkluderer året, måneden og dagen. Appen vet hvordan du formaterer disse verdiene, begrenser inn data til det som passer for hver, og deler verdiene med en database. Fødsels dager er forskjellig fra jubileer til personer, men systemet håndterer dem på nøyaktig samme måte. I dette tilfellet er **dato** et eksempel på en [datatype](https://en.wikipedia.org/wiki/Data_type).

Denne artikkelen inneholder detaljer om data typene som lerret apps støtter. Når en app kobler til en ekstern data kilde, tilordnes hver datatype i denne kilden til en datatype for lerrets apper.

| Datatype | Beskrivelse | Eksempler |
|-----------|-------------|---------|
| **Verdien** | En *sann* -eller *Usann* -verdi.  Kan brukes direkte i **IF**, **filter** og andre funksjoner uten sammenligning.  | *sann* |
| **Farge** | En farge spesifikasjon, inkludert en alfa kanal. | **Color.Red**<br>**ColorValue ("#102030")**<br>**RGBA (255, 128, 0, 0,5)** |
| **Valuta** | En valuta verdi som lagres i et flyt tall. Valuta verdier er de samme som tall verdier med valuta formaterings alternativer.  | **123**<br>**4,56** |
| **Aktivabokføringsdato** | En dato uten et klokkeslett, i tids sonen til appens bruker. | **Date (2019, 5, 16)** |
| **DateTime** | En dato med et klokkeslett i tids sonen til appens bruker. | **DateTimeValue (» 16. mai 2019 1:23:09 PM)** |
| **OBJEKT** | En [globalt unik identifikator](https://en.wikipedia.org/wiki/Universally_unique_identifier). | **GUID ()**<br>**GUID ("123e4567-e89b-12d3-A456-426655440000")** |
| **Hyperkobling** | En tekst streng som inneholder en hyperkobling. | **"http://powerapps.microsoft.com "** |
| **Bilde** | En [URI (Universal Resource Identifier)-](https://en.wikipedia.org/wiki/Uniform_Resource_Identifier) tekst streng til et bilde i JPEG, PNG, SVG, GIF eller andre vanlige web bilde formater. | **MyImage** lagt til som en app-ressurs<br>**"https://northwindtraders.com/logo.jpg "**<br>**"appres://blobmanager/7b12ffa2..."** |
| **Mediefil** | En URI-tekst streng til en video-eller lyd innspilling. | **MyVideo** lagt til som en app-ressurs<br>**"https://northwindtraders.com/intro.mp4 "**<br>**"appres://blobmanager/3ba411c..."** |
| **Rekke** | Et flyt tall. | **123**<br>**-4,567**<br>**8.903e121** |
| **Alternativ sett** | Et valg fra et sett med alternativer, som støttes av et tall. Denne data typen kombinerer en tekst etikett som lokaliseres, med en numerisk verdi. Etiketten vises i appen, og den numeriske verdien lagres og brukes for sammenligninger. | **ThisItem. OrderStatus** |
| **Registrerer** | En post med data verdier. Denne sammensatte data typen inneholder forekomster av andre data typer som er oppført i dette emnet. Mer informasjon: Å [arbeide med tabeller](../working-with-tables.md). | **{Company: «Gas tro nor delikat Esser» <br>Staff: 35, <br>NonProfit: False}** |
| **Post referanse** | En referanse til en post i en enhet. Slike referanser brukes ofte med polymorfiske oppslag. Mer informasjon: [Arbeid med referanser](../working-with-references.md).| **Først (kontoer). Ren** |
| **Tegn** | En tabell med poster.  Alle postene må ha samme navn for feltene med de samme data typene, og utelatte felt behandles som *tomme*. Denne sammensatte data typen inneholder forekomster av andre data typer som er oppført i dette emnet. Mer informasjon: Å [arbeide med tabeller](../working-with-tables.md). | **Table ({for navn: «Sidney», <br>LastName: "Higa"}, <br> {for navn: "Nina", <br>LastName: «Anderson»})**
| **Tekst** | En Unicode-tekst streng. | **"Hello, World"** |
| **Tid** | Et tidspunkt uten dato, i tids sonen til appens bruker. | **Klokkeslett (11, 23, 45)** |
| **To alternativer** | Et valg fra et sett med to alternativer, som støttes av en boolsk verdi. Denne data typen kombinerer en tekst etikett som lokaliseres, med en boolsk verdi. Etiketten vises i appen, og den boolske verdien lagres og brukes til sammenligninger. | **ThisItem. avgiftspliktig** |

Mange av disse data typene er like og har samme underliggende representasjon, for eksempel et **hyperkoblingsfelt** som behandles som **tekst**.  Tilleggs data typene gir bedre standard opplevelser i skjemaer og andre kontroller.

## <a name="blank"></a>Blank

Alle data typer kan ha en *tom* verdi (med andre ord, ingen verdi). Ordet "null" brukes ofte i databaser for dette konseptet.  

Bruk **tom** -funksjonen med **Set** eller **patch** -funksjonen til å angi en variabel eller et felt som *tom*. For eksempel: **Set (x, blank ())** fjerner alle verdier i den globale variabelen **x**.  

Test for en *tom* verdi ved hjelp av [**IsBlank**](function-isblank-isempty.md) -funksjonen. Erstatt mulige *tomme* verdier med ikke-*tomme* verdier ved hjelp av [**oppsamlings**](function-isblank-isempty.md) funksjonen.

Fordi alle data typer støtter *tom*, har de **boolske** og to data typene for **alternativ** effektiv tre mulige verdier.

## <a name="text-hyperlink-image-and-media"></a>Tekst, hyperkobling, bilde og Media

Alle fire disse data typene er basert på en [Unicode](https://en.wikipedia.org/wiki/Unicode) -tekst streng.

### <a name="image-and-media-resources"></a>Bilde-og medie ressurser

Gjennom **fil** -menyen kan du legge til bilde-, video-og lyd filer som program ressurser. Navnet på den importerte filen blir ressurs navnet i appen. I denne grafikken er logoen for Gas tro nor delikat Esser, som heter **nwindlogo**, lagt til i en app:

![](media/data-types/nwind-resource.png)

Hvis du vil bruke denne ressursen i en app, angir du den i **bilde** -egenskapen til en [**bilde**](../controls/control-image.md) -kontroll:

![](media/data-types/nwind-image.png)

### <a name="uris-for-images-and-other-media"></a>URIer for bilder og andre medier

Du kan se litt dypere inn i det siste eksemplet ved å angi **tekst** -egenskapen for en [**etikett**](../controls/control-text-box.md) -kontroll til **nwindlogo**. Etiketten viser en tekst streng:

![](media/data-types/nwind-text.png)

Lerret apper refererer til hvert bilde eller en annen mediefil, enten det er i skyen eller lagt til som en app-ressurs, av en URI-tekst streng.

**Bilde** -egenskapen til en bilde kontroll godtar for eksempel ikke bare program ressurser, men også koblinger til bilder på nettet, for eksempel « https://northwindtraders.com/logo.jpg ». Egenskapen godtar også innebygde bilder som bruker data- [URI-skjemaet](https://en.wikipedia.org/wiki/Data_URI_scheme), som i dette eksemplet:

```powerapps-dot
"data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAkAAAAFAQMAAACtnVQoAAAABlBMVEUAAAB0J3UMNU6VAAAAAXRSTlMAQObYZgAAABRJREFUCNdjUGJgCGVg6GgAkkA2AA8/AffqCEBsAAAAAElFTkSuQmCC"
```

Denne URIEN viser en skalert versjon av to lilla romber:

![](media/data-types/double-diamonds.png)

Du kan vise det nyeste bildet som er fanget opp i en [**kamera**](../controls/control-camera.md) kontroll, hvis du angir **bilde** -egenskapen for en bilde-kontroll til **Foto** -egenskapen til kamera-kontrollen. Appen inneholder bildet i minnet, og **Foto** -egenskapen for kamera kontrollen returnerer en URI-referanse til bildet. Du kan for eksempel ta et bilde, og kameraets **Foto** egenskap kan returnere **«appres://blobmanager/7b12ffa2ea4547e5b3812cb1c7b0a2a0/1»** .

Du bruker en URI til å referere til et bilde eller en annen medie fil som er lagret i en database. På den måten henter ikke appen de faktiske dataene før den faktisk er nødvendig. Et vedlegg i en Common Data Service enhet kan for eksempel returnere **«appres://DataSources/Contacts/Table/...»** Som i kamera eksempelet kan du vise dette bildet ved å angi **bilde** -egenskapen for en bilde-kontroll til denne referansen, som henter binær dataene.

Når du lagrer en medie data type, for eksempel et bilde, i en database, sender appen de faktiske bilde-eller medie dataene, ikke URI-referansen.

### <a name="size-limits"></a>Størrelses grenser

Som tekst strenger og URIer har disse data typene ingen forhåndsinnstilt grense på lengden.

De binære dataene som disse data typene refererer til, har ingen forhånds definert grense for størrelse. Et bilde som for eksempel er spilt inn gjennom kamera-kontrollen som nå er referert som **«appres://...»** , kan være så stor og høy oppløsning som om enhetens kamera kan ha det. Oppløsningen, bilde frekvensen og andre attributter for medie filer begrenses ikke av data typen, men spesifikke kontroller for avspilling og registrering av medier kan ha sine egne begrensninger.

Alle data størrelser er imidlertid underlagt mengden tilgjengelig minne i appen. Nett lesere som kjører på en stasjonær data maskin, støtter vanligvis mer enn 100 MB data. Mengden tilgjengelig minne på en enhet, for eksempel en telefon, kan imidlertid være langt lavere, vanligvis i området 30-70 megabyte. Hvis du vil finne ut om appen kjører innenfor disse grensene, kan du teste vanlige scenarier på alle enheter den skal kjøre.

Som en anbefalt Fremgangs måte kan du bare oppbevare data i minnet så lenge som nødvendig. Last opp bilder til en database så snart du kan; Last bare ned avbildninger når appens bruker ber om dem.

## <a name="number-and-currency"></a>Tall og valuta

Data typene **tall** og **valuta** bruker [IEEE 754 Double-Precision-standarden for flyt tall](https://en.wikipedia.org/wiki/IEEE_754). Denne standarden gir et svært stort utvalg av tall der du kan jobbe, fra – 1,79769 x 10<sup>308</sup> til 1,79769 x 10<sup>308</sup>. Den minste verdien som kan representeres, er 5 x 10<sup>– 324</sup>.

Lerret apps kan nøyaktig representere hele tall (eller hel tall) mellom – 9 007 199 254 740 991 (– (2<sup>53</sup> -1)) og 9 007 199 254 740 991 (2<sup>53</sup> – 1), inkludert. Dette området er større enn 32-biters hel talls data typene (eller 4-bytes) som databaser brukes ofte. Lerret-apper kan imidlertid ikke representere data typene 64-biters (eller 8-byte). Du vil kanskje lagre nummeret i et tekst felt eller bruke en beregnet kolonne for å lage en kopi av tallet i et tekst felt, slik at det er tilordnet en **tekst** data type i lerret-appen. På denne måten kan du holde, vise og angi disse verdiene, i tillegg til å sammenligne dem for å avgjøre om de er like. Du kan imidlertid ikke utføre numeriske beregninger i dette skjemaet.

Flyt talls aritmetikk er omtrentlig, så den kan noen ganger gi uventede resultater med mange dokumenterte eksempler. Du forventer kanskje at formelen **55/100 * 100** for å returnere nøyaktig 55 og **(55/100 * 100)-55** til å returnere nøyaktig null. Den sistnevnte formelen returnerer imidlertid 7,1054 x 10<sup>– 15</sup>, som er svært liten, men ikke null. Denne små forskjellen fører vanligvis ikke til et problem, og appen runder den av når resultatet vises. Små forskjeller kan imidlertid sammensatte i etterfølgende beregninger og vises for å gi feil svar.

Database systemer lagrer ofte valutaer og utfører beregninger ved hjelp av en desimal matematikk, som gir et mindre område, men større kontroll over presisjonen. Som standard tilordner lerrets programmer valutaer i og utenfor flyt talls verdier. resultatet kan derfor avvike fra beregninger som utføres i en opprinnelig desimal data type. Hvis denne typen avviker vil føre til problemer, kan det hende du vil arbeide med disse verdiene som **tekst**, akkurat som du kan med store hel tall som er beskrevet tidligere i denne delen.

## <a name="date-time-and-datetime"></a>Dato, klokkeslett og DateTime

### <a name="time-zones"></a>Tids soner

Dato/klokkeslett-verdier er i følgende kategorier:

- **Bruker lokal**: Disse verdiene lagres i [UTC (Coordinated Universal Time)](https://en.wikipedia.org/wiki/Coordinated_Universal_Time), men brukerens tidssone påvirker hvordan appen viser disse verdiene og hvordan appen bruker angi dem. Som et eksempel vises samme øyeblikk for en bruker i Canada enn det som er en bruker i Japan.
- Tidssone **uavhengig**: Appen viser disse verdiene på samme måte, og appen angir dem på samme måte, uavhengig av tidssone. Det samme ser ut på samme måte som en bruker i Canada som den gjør for en bruker i Japan. App-forfattere som ikke forventer at appene deres kan kjøres i forskjellige tids soner, bruker disse verdiene fordi de er enklere.

Denne tabellen viser noen eksempler:

| Dato/klokkeslett-type | Verdi lagret i databasen | Verdi som vises og angis 7 timer, vest for UTC | Verdi vist og angitt 4 timer øst-UTC |
|--------------------------|------------------------------|------------------------------|
| **Bruker lokal** | Søndag, &nbsp;May @ no__t-119, &nbsp;2019<br>4:00 AM | Lørdag, &nbsp;May @ no__t-118, &nbsp;2019<br>9:00 PM | Søndag, &nbsp;May @ no__t-119, &nbsp;2019<br>8:00 AM |
| **Tidssone uavhengig** | Søndag, &nbsp;May @ no__t-119, &nbsp;2019<br>4:00 AM | Søndag, &nbsp;May @ no__t-119, &nbsp;2019<br>4:00 AM | Søndag, &nbsp;May @ no__t-119, &nbsp;2019<br>4:00 AM | 

For **lokal bruker** dato/klokkeslett bruker lerret apper tids sonen for nett leseren eller enheten, men modell drevne apper bruker brukerens innstilling i Common data service. Disse innstillingene Sams varer vanligvis, men resultatene vil være forskjellige hvis disse innstillingene er forskjellige.

Bruk funksjonene [**DateAdd**](function-dateadd-datediff.md) og [**TimeZoneInformation**](function-dateadd-datediff.md) til å konvertere lokal tid til UTC og tilbake igjen.  Se eksemplene på slutten av dokumentasjonen for disse funksjonene.

### <a name="numeric-equivalents"></a>Tall tilsvarende

Lerret apper inneholder og beregner alle dato/klokkeslett-verdier, enten en **bruker lokal** eller **TIDSSONE uavhengig** i UTC. Appen oversetter verdiene basert på tids sonen til appen, når de viser dem og når appen bruker angi dem.

Når en lerret-app leser en **tids sone uavhengig** verdi fra en data kilde eller skriver en slik verdi til en data kilde, justerer appen automatisk verdien for å kompensere for tids sonen til appens bruker. Deretter behandler appen verdien som en UTC-verdi, konsekvent med alle andre dato/klokkeslett-verdier i appen. På grunn av denne kompensasjonen, vises den opprinnelige **tids sonens uavhengige** verdi når APPEN justerer UTC-verdien for brukerens tidssone.

Du kan observere dette ved å bruke [**Value**](function-value.md) -funksjonen til å få tilgang til den underliggende numeriske verdien for en dato/klokkeslett-verdi. Denne funksjonen returnerer dato/klokkeslett-verdien som antall millisekunder, siden 1. januar 1970 00:00:00.000 UTC.

Fordi hver dato/klokkeslett-verdi holdes i UTC, returnerer ikke formel **verdien (Date (1970, 1, 1))** null i de fleste delene av verden fordi **Date** -funksjonen returnerer en dato i UTC. Formelen vil for eksempel returnere 28 800 000 i en tidssone som forskyves fra UTC med åtte timer. Dette tallet gjenspeiler antallet millisekunder i åtte timer.

Går tilbake til eksemplet våre fra ovenfor:

| Dato/klokkeslett-type | Verdi lagret i databasen | Verdi som vises og angis 7 timer, vest for UTC | **Value** -funksjonen returnerer |
|--------------------------|------------------------------|------------------------------|
| **Bruker lokal** | Søndag, &nbsp;May @ no__t-119, &nbsp;2019<br>4:00 AM | Lørdag, &nbsp;May @ no__t-118, &nbsp;2019<br>9:00 PM | 1 558 238 400 000<br> (Søndag, &nbsp;May @ no__t-119, &nbsp;2019<br>4:00 AM. UTC) |
| **Tidssone uavhengig** | Søndag, &nbsp;May @ no__t-119, &nbsp;2019<br>4:00 AM | Søndag, &nbsp;May @ no__t-119, &nbsp;2019<br>4:00 AM |1 558 263 600 000<br> (Søndag, &nbsp;May @ no__t-119, &nbsp;2019<br>11:00 AM. UTC) |

### <a name="converting-unix-times"></a>Konverterer UNIX-tider

UNIX-tider gjenspeiler antall sekunder siden 1. januar 1970 00:00:00 UTC. Fordi lerret apps bruker millisekunder i stedet for sekunder, kan du konvertere mellom de to ved å multiplisere eller dele på 1 000.

Unix Time viser for eksempel 9. september 2001, med 01:46:40 UTC AS 1 000 000 000. Hvis du vil vise denne dato/klokkeslett-verdien i en lerret-app, multipliserer du dette tallet med 1 000 for å konvertere den til millisekunder, og deretter bruker du den i en [**tekst**](function-text.md) funksjon. Formel **teksten (1000000000 * 1000, DateTimeFormat. UTC)** Returnerer strengen **2001-09-09T01:46:40.000 z**.

Denne funksjonen returnerer imidlertid **lørdag, 8. September 2001 18:46:40** hvis du bruker **DateTimeFormat. LongDateTime24** -formatet i en tidssone som er-7 timer forskyvning fra UTC (7 timer, Vest UTC). Dette resultatet viser **datetime** -verdien riktig, basert på den lokale tids sonen.

Hvis du vil konvertere til en UNIX-tid, deler du resultatet fra **verdien** av 1 000:
<br>**RoundDown (verdi (UnixTime)/1000, 0)**

Hvis du trenger UNIX-tid i en **dato** verdi for videre beregning eller visning i powerapps, kan du bruke denne formelen:
<br>**DateAdd (Date (1970, 1, 1), UnixTime, Seconds)**

### <a name="sql-server"></a>SQL Server

SQL Server har [ **datetime**, **Datetime2**og andre data typer for dato/klokkeslett](https://docs.microsoft.com/sql/t-sql/functions/date-and-time-data-types-and-functions-transact-sql?view=sql-server-2017) som ikke inkluderer en tids sone forskyvning, og som ikke angir hvilken tidssone de er i. Lerret apper forutsetter at disse verdiene er lagret i UTC og behandler dem som en **lokal bruker**. Hvis verdiene er ment som tids soner uavhengig, må du korrigere for UTC-oversettelsene ved hjelp av [**TimeZoneOffset**](function-dateadd-datediff.md#converting-to-utc) -funksjonen.

Lerret apper bruker tids sone informasjonen i **Datetimeoffset** -felt ved konvertering av en verdi til appens interne UTC-representasjon. Appene bruker alltid UTC som tids sone (null tids sone forskyvning) når de skriver data.

Lerrets programmer leser og skriver verdier av [**time**](https://docs.microsoft.com/sql/t-sql/data-types/time-transact-sql) -data typen i SQL Server som tekst strenger i [formatet ISO 8601 Duration](https://en.wikipedia.org/wiki/ISO_8601#Durations). Du må for eksempel analysere dette streng formatet og bruke [**klokkeslett**](function-date-time.md) -funksjonen til å konvertere tekst strengen **"PT2H1M39S"** til en **klokkeslett** verdi:

```powerapps-dot
First(
    ForAll(
        MatchAll( "PT2H1M39S", "PT(?:(?<hours>\d+)H)?(?:(?<minutes>\d+)M)?(?:(?<seconds>\d+)S)?" ),
        Time( Value( hours ), Value( minutes ), Value( seconds ) )
    )
).Value
```

### <a name="mixing-date-and-time-information"></a>Blande informasjon om dato og klokkeslett

**Dato**, **klokkeslett**og **datetime** har ulike navn, men de inneholder bare den samme informasjonen om datoer og klokkeslett. 

En **dato** verdi kan inneholde tids informasjon med den, som vanligvis er midnatt. En **tids** verdi kan inneholde dato informasjon, som vanligvis er 1. januar 1970. Common Data Service lagrer også klokkeslett informasjon med et **dato** -felt, men viser bare dato informasjonen som standard. På samme måte kan det hende at lerret apper skiller mellom disse data typene for å bestemme standard formater og kontroller.

Det anbefales ikke å legge til og trekke fra verdier for dato og klokkeslett direkte, fordi tids soner og andre konverteringer kan føre til forvirrende resultater. Bruk **Value** -funksjonen til å konvertere dato/klokkeslett-verdier til millisekunder først, og ta i bruk appens brukerens tidssone, eller Bruk funksjonene [**DateAdd**](function-dateadd-datediff.md) og [**DateDiff**](function-dateadd-datediff.md) til å legge til eller trekke fra én av disse verdiene.

## <a name="option-sets-and-two-options"></a>Alternativ sett og to alternativer

Alternativ sett og data typer med to alternativer gir deg to eller flere alternativer som en app-bruker kan velge. Et alternativ sett for **ordre status** kan for eksempel tilby alternativene **nytt**, **sendt**, **fakturert**og **lukket**. Data typen med to alternativer tilbyr bare to valg.

Begge disse data typene viser etikettene i en tekst streng kontekst. En etikett-kontroll viser for eksempel ett av alternativene for ordre status hvis kontrollens **tekst** -egenskap er angitt til en formel som refererer til dette alternativ settet. Alternativ etiketter kan være lokalisert for App-brukere på forskjellige plasseringer.

Når en app-bruker velger et alternativ og lagrer denne endringen, overfører appen dataene til databasen, som lagrer dataene i en representasjon som er uavhengig av språk. Et alternativ i et alternativ sett overføres og lagres som et tall, og et alternativ i en data type med to alternativer overføres og lagres som en boolsk verdi.

Etikettene er bare til visnings formål. Du kan ikke utføre direkte sammenligninger med etikettene fordi de er spesifikke for et språk. I stedet har hvert alternativ sett en opplisting som fungerer med det underliggende antallet eller den boolske verdien. Du kan for eksempel ikke bruke denne formelen:

`If( ThisItem.OrderStatus = "Active", ...`

Men du kan bruke denne formelen:

`If( ThisItem.OrderStatus = OrderStatus.Active, ...`

For globale alternativ sett (hvilke enheter som deler), er navnet på tilgangs angivelses opplistingen lik navnet på det globale alternativ settet. For lokale alternativ sett (som er tilknyttet en enhet), kan navnet inneholde navnet på enheten. Denne virke måten unngår konflikter hvis flere enheter har et alternativ sett som har samme navn. **Kontoer** -enheten kan for eksempel ha et **OrderStatus** alternativ sett, og navnet kan være **OrderStatus (kontoer)** . Dette navnet inneholder ett eller flere mellomrom og parenteser, så du må omslutte det med enkle anførsels tegn hvis du refererer til det i en formel.

I tillegg kan verdiene for to alternativer også oppføre seg som boolske verdier. En verdi med to alternativer kalt **TaxStatus** kan for eksempel ha etikettene **avgiftspliktig** og **ikke-avgiftspliktig**, som Sams varer med henholdsvis *sann* og *Usann* . Hvis du vil demonstrere, kan du bruke denne formelen:

`If( ThisItem.Taxable = TaxStatus.Taxable, ...`

Du kan også bruke den tilsvarende formelen:

`If( ThisItem.Taxable, ...`