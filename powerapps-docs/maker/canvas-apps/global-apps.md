---
title: Global støtte | Microsoft Docs
description: Bygg apper som brukes over hele verden.
documentationcenter: na
author: gregli-msft
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: conceptual
ms.component: canvas
ms.date: 10/25/2016
ms.author: gregli
ms.openlocfilehash: 68f81dffa4ba861978dacb1b7ad6830b0736ed6e
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/04/2018
ms.locfileid: "31837152"
---
# <a name="global-support"></a>Global støtte
PowerApps er et globalt produkt.  Du kan bygge og bruke apper på mange ulike språk og i mange ulike områder.

Teksten som vises i PowerApps har blitt oversatt til en rekke språk, både når du bygger og kjører apper.  Du ser menyelementer, dialogbokser, båndfaner og annen tekst på ditt eget språk.  Innskriving og visning av datoer og tall er også tilpasset for ditt bestemte språk og område.  For eksempel bruker enkelte områder i verden «.» som et desimalskilletegn mens andre bruker «,».  

Appene du oppretter kan også være globalt følsomme.  Bruk funksjonene **[Language](functions/function-language.md)**, **[Text](functions/function-text.md)**, **[Value](functions/function-value.md)**, **[DateValue](functions/function-datevalue-timevalue.md)** og andre funksjoner til å tilpasse hva som vises og brukes som inndata på forskjellige språk.   

## <a name="language-settings"></a>Språkinnstillinger
Når du bruker det opprinnelige studioet eller en innebygd spiller, får du språket som brukes av vertsoperativsystemet.  For Windows kan dette styres under «Alle innstillinger» og deretter innstillingene «Tid og språk».  Med Windows kan du også angi tegn som skal brukes for desimaltegnet, og slik overstyre språkinnstillingen.  

Når du bruker Internett-versjonene, angir nettleseren språket som brukes.  De fleste nettlesere bruker innstillingen for vertsoperativsystemet som standard, men noen tilbyr også en måte for å angi språket manuelt.

## <a name="authoring-environment"></a>Redigeringsmiljø
Redigeringsmiljøet tilpasser seg språkinnstillingen til forfatteren.  Selve appen er lagret på en språkagnostisk måte, slik at forfattere som bruker ulike språk kan redigere samme app.

### <a name="names-in-formulas"></a>Navn i formler
De fleste elementene i formelen er alltid på engelsk:

* Funksjonsnavn: **If**, **Navigate**, **Collect**, ...
* Navn på kontrollegenskaper: **Screen.Fill**, **Button.OnSelect**, **Textbox.Font**, ...
* Opplistingsnavn: **Color.Aqua**, **DataSourceInfo.MaxValue**, **FontWeight.Bold**...
* Signalposter: **Compass.Heading**, **Location. Latitude**, **App.ActiveScreen**, ...
* Operatorer: **Overordnet**, **i**, **exactIn**, ...

Fordi redigeringsopplevelsen er lokalisert, vises kontroller og andre objektnavn på forfatterens opprinnelige språk.  På spansk vises noen av kontrollnavnene som:

![](media/global-apps/insert-controls-es.png)

Når du setter inn en av disse i appen din, blir navnet på engelsk som standard.  Dette gjøres for konsekvens med navnene for kontrollegenskapene og resten av formelen.  For eksempel: **Casilla**, oppført ovenfor, er satt inn som **Checkbox1**.  

Når en kontroll er satt inn, kan du endre navnet til det du måtte ønske.  Når kontrollen er merket, vises navnet på kontrollen helt til venstre på Innhold-båndet.  Hvis du velger dette navnet, vises en tekstboks der du kan redigere navnet:

![](media/global-apps/control-rename.png)

Hvis du vil, kan du bruke denne til å endre kontrollens navn til **Casilla1**.  Den røde bølgete linjen, i dette tilfellet vist av en nettleser, vises fordi navnet ikke er et spansk ord, men dette er ikke noe problem.

Du kan bruke et hvilket som helst navn for:

* Kontrollnavn
* Samlingsnavn
* Navn på kontekstvariabler

### <a name="formula-separators-and-chaining-operator"></a>Skilletegn og sammenkjedingsoperator for formler
Noen [skilletegn og operatorer](functions/operators.md) flyttes basert på desimalskilletegnet på forfatterens språk:

| Desimalskilletegn på forfatterens språk | Desimalskilletegn i PowerApps | Skilletegn for lister i PowerApps | Sammenkjedingsoperator i PowerApps |
| --- | --- | --- | --- |
| **.** (punktum) |**.** (punktum) |**,** (komma) |**;** (semikolon) |
| **,** (komma) |**,** (komma) |**;** (semikolon) |**;;** (doble semikolon) |

Endringen av listeskilletegn i PowerApps samsvarer med det som skjer med listeskilletegn i Excel.  Det påvirker:

* Argumenter i funksjonsoppkall.
* Felter i en [post](working-with-tables.md#elements-of-a-table).
* Poster i en [verditabell](working-with-tables.md#inline-syntax).

Tenk for eksempel på følgende formel i en-US:

**If( Slider1.Value > 12.59, UpdateContext( { Validation: true, MovingOn: 1 } ); Navigate( "NextScreen", "" ), UpdateContext( { Validation: false } ) )**

På et annet språk, der «,» brukes som desimaltegn, vises dette i redigeringsvisningen som:

**If( Slider1.Value > 12,59; UpdateContext( { Validation: true; MovingOn: 1 } );; Navigate( "NextScreen", "" ); UpdateContext( { Validation: false } ) )**

Vær oppmerksom på at operatoren for egenskapsvalg **.** i **Slider1.Value** alltid er den samme, uansett hva desimalskilletegnet er.

Formelen endres ikke internt, det eneste som endres er hvordan den vises og redigeres av forfatteren.  To ulike forfattere som bruker to forskjellige språk, kan vise og redigere den samme formelen, og begge ser riktig skilletegn og operatorer for språket sitt.

## <a name="creating-a-global-app"></a>Å opprette en global app
Appen du oppretter, kan tilpasses til ulike språk, noe som gir en flott brukeropplevelse over hele verden.

### <a name="language-function"></a>Language-funksjonen
**[Language](functions/function-language.md)**-funksjonen returnerer språkkoden for gjeldende bruker.  Denne funksjonen returnerer for eksempel **en-GB** for brukere i Storbritannia og **de-DE** for brukere i Tyskland.  

Du kan bruke **Language**-funksjonen blant annet til å vise oversatt tekst for brukerne dine.  Appen kan inneholde en tabell med oversatte verdier i appen din:

![](media/global-apps/loc-table.png)

Du kan deretter bruke følgende formel til å hente oversatte strenger fra tabellen:

**LookUp( Table1, TextID = "Hello" && (LanguageTag = Left( Language(), 2 ) || IsBlank( LanguageTag ))).LocalizedText**  

Vær oppmerksom på at oversatte strenger på andre språk kan være betydelig lengre enn de er på ditt språk.  I mange tilfeller må etiketter og andre elementer som viser strengene i brukergrensesnittet, være bredere for å få plass.

Se dokumentasjonen for **[Language](functions/function-language.md)**-funksjonen for mer informasjon.

### <a name="formatting-numbers-dates-and-times"></a>Formater tall, datoer og klokkeslett
Tall, datoer og klokkeslett skrives i forskjellige formater i ulike deler av verden.  Betydningen av komma, desimaler og rekkefølgen for år, måned og dato varierer fra sted til sted.   

**[Text](functions/function-text.md)**-funksjonen formaterer tall og datoer etter språkinnstillingen til brukeren.

**Text** krever en formatstreng for å vite hvordan du vil formatere tall eller datoer.  Denne formatstrengen kan ha én av to former:

* **En globalt gjeldende opplisting.**  For eksempel: **Text( Now(), DateTimeFormat.LongDate )**.  Denne formelen vil formatere gjeldende dato i et format som er riktig for det aktuelle språket.  Dette er den beste måten å angi formatstrengen på.
* **En egendefinert formatstreng.**  For eksempel: **Text( Now(), "[$-en-US]dddd, mmmm dd, yyyy" )** viser den samme teksten som opplistingen når den brukes på språket en-US.  Fordelen med strengen for egendefinert format er at du kan angi nøyaktig hva du ønsker.

[$-en-US] fremst i den egendefinerte formatstrengen forteller **Text** hvilket språk som skal brukes for å tolke den egendefinerte formatstrengen.  Dette blir satt inn for deg og blir brukt som ditt redigeringsspråk som standard.  Vanligvis trenger du ikke endre dette.  Dette er nyttig når forfattere med ulike språk redigerer samme app.

Det tredje argumentet for **Text** angir hvilket språk som skal brukes for resultatet av funksjonen.  Som standard brukes språkinnstillingen for gjeldende brukeren.

Se dokumentasjonen for **[Text](functions/function-text.md)**-funksjonen for mer informasjon.      

### <a name="reading-numbers-dates-and-times"></a>Å lese tall, datoer og klokkeslett
Det finnes fire funksjoner for lesing av tall, datoer og klokkeslett som er angitt av brukeren:

* **[Value](functions/function-value.md)**: konverterer et tall i en tekststreng til en tallverdi.
* **[DateValue](functions/function-datevalue-timevalue.md)**: konverterer en datoverdi i en tekststreng til en dato/klokkeslett-verdi.  Alle tidspunkt som er angitt i tekststrengen ignoreres.
* **[TimeValue](functions/function-datevalue-timevalue.md)**: konverterer en klokkeslettverdi i en tekststreng til en dato/klokkeslett-verdi.  Alle datoer som er angitt i tekststrengen ignoreres.
* **[DateTimeValue](functions/function-datevalue-timevalue.md)**: konverterer en dato- og klokkeslettverdi i en tekststreng til en dato/klokkeslett-verdi.  

Hvis du har brukt Excel, kan alle disse funksjonene kombineres i **Value**-funksjonen.  De er delt opp her fordi PowerApps har ulike typer for dato/klokkeslett-verdier og tall.

Alle disse funksjonene har de samme argumentene:

* *Streng, obligatorisk*: en streng fra brukeren. En streng skrives for eksempel inn i en **tekstinndata**-kontroll og leser fra kontrollen med **Tekst**-egenskapen.
* *Språk, valgfritt*: språket som skal brukes til å tolke *strengen*.  Språkinnstillingen til brukeren, som standard.

Eksempel:

* **Value( "12,345.678", "en-US" )** eller **Value( "12,345.678" )** på en plassering der en-US er brukerspråket, returnerer tallet **12345,678**, klar for beregninger.
* **DateValue( "1/2/01", "es-ES" )** eller **DateValue( "1/2/01" )** på en plassering der es-ES er brukerspråket, returnerer dato/klokkeslett-verdien **01. februar 2001 ved midnatt**.
* **TimeValue( "11:43:02", "fr-FR" )** eller **DateValue( "11:43:02" )** på en plassering der fr-FR er brukerspråket, returnerer dato/klokkeslett-verdien **01. januar 1970 kl. 11:43:02**.
* **TimeDateValue( "11:43:02 1/2/01", "de-DE" )** eller **DateValue( "11:43:02" )** på en plassering der de-DE er brukerspråket, returnerer dato/klokkeslett-verdien **01. februar 2001 kl. 11:43:02**.

Hvis du vil ha mer informasjon, kan du se dokumentasjonen for funksjonene **[Value](functions/function-value.md)** og **[DateValue, TimeValue og DateTimeValue](functions/function-datevalue-timevalue.md)** og [Å arbeide med datoer og klokkeslett](show-text-dates-times.md).

### <a name="calendar-and-clock-information"></a>Kalender- og klokkeinformasjon
**[Calendar](functions/function-clock-calendar.md)**- og **[Clock](functions/function-clock-calendar.md)**-funksjonene gir deg informasjon fra kalenderen og klokken på brukerens gjeldende språk.  

Blant annet kan du bruke disse funksjonene til å hente en **Rullegardin**-kontroll med en liste over valg.  

Se dokumentasjonen for **[Calendar](functions/function-clock-calendar.md)**- og **[Clock](functions/function-clock-calendar.md)**-funksjonene for mer informasjon.
