---
title: Tekst-funksjonen | Microsoft Docs
description: Referanseinformasjon, herunder syntaks og eksempler for Tekst-funksjonen i PowerApps
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 10/25/2016
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: dab6004afe7350b2375ade21871efe9144b6325b
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/24/2018
ms.locfileid: "42849297"
---
# <a name="text-function-in-powerapps"></a>Text-funksjonen i PowerApps
Formaterer et tall eller en verdi for dato/klokkeslett, til visning som en tekststreng.

## <a name="description"></a>Beskrivelse
**Text**-funksjonen formaterer et tall eller en verdi for dato/klokkeslett som er basert på én av disse typene argumenter:

* Et forhåndsdefinert dato/klokkeslett-format, som du angir ved hjelp av opplistingen for **DateTimeFormat**.  Denne fremgangsmåten foretrekkes for datoer og klokkeslett, da den automatisk justeres til hver brukers språk og plassering.
* Et egendefinert format, en tekststreng som består av plassholdere, som beskriver hvordan du formaterer tallet, eller verdien for dato/klokkeslett. Plassholdere definerer hvor mange sifre som skal vises, om skilletegnet for grupperinger skal brukes og hvordan du viser navnet på en måned. PowerApps støtter et delsett av plassholderne, i likhet med Microsoft Excel.

Hvis du vil ha mer informasjon, kan du se[Slik arbeider du med datoer og klokkeslett](../show-text-dates-times.md).

### <a name="predefined-datetime-formats"></a> Forhåndsdefinerte formater for dato/klokkeslett

| Forhåndsdefinert format | Beskrivelse |
| --- | --- |
| **DateTimeFormat.LongDate** |År, måned, dag i måneden og dagen i uken. Navnet på måneden og dagen i uken forkortes ikke. |
| **DateTimeFormat.LongDateTime** |År, måned, dag i måneden og dagen i uken, pluss time (12-timers klokke), minutter, sekunder og AM/PM-betegnelse. Navnet på måneden og dagen i uken forkortes ikke. |
| **DateTimeFormat.LongDateTime24** |År, måned, dag i måneden og dagen i uken, pluss time (24-timers klokke), minutter og sekunder. Navnet på måneden og dagen i uken forkortes ikke. |
| **DateTimeFormat.LongTime** |Time (12-timers klokke), minutter, sekunder og AM/PM-betegnelse. Samme som ShortTime. |
| **DateTimeFormat.LongTime24** |Time (24-timers klokke), minutter og sekunder. Samme som ShortTime24. |
| **DateTimeFormat.ShortDate** |Firesifret år med tosifret måned og dag i måneden. |
| **DateTimeFormat.ShortDateTime** |Firesifret år med tosifret måned og dag i måneden, pluss time (12-timers klokke), minutter, sekunder og AM/PM-betegnelse. |
| **DateTimeFormat.ShortDateTime24** |Firesifret år med tosifret måned og dag i måneden, pluss time (24-timers klokke), minutter og sekunder. |
| **DateTimeFormat.ShortTime** |Time (12-timers klokke), minutter, sekunder og AM/PM-betegnelse.  Samme som LongTime. |
| **DateTimeFormat.ShortTime24** |Time (24-timers klokke), minutter og sekunder.  Samme som LongTime24. |
| **DateTimeFormat.UTC** |Verdien for dato/klokkeslett konverteres til UTC basert på tidssonen til den gjeldende brukeren, og blir formatert i henhold til ISO 8601-standarden. |

### <a name="number-placeholders"></a>Plassholdere for tall

| Plassholder | Beskrivelse |
| --- | --- |
| **0** (*null*) |Viser ubetydelige nuller hvis et tall har færre sifre enn det er nuller i formatet. For eksempel kan du bruke formatet **#,00**, hvis du vil vise **8,9** som **8,90**. |
| **#** |Følger de samme reglene som **0** (null). **Tekst** returnerer imidlertid ikke ekstra nuller når tallet har færre sifre på hver side av desimaltegnet enn det er #-symboler i formatet. For eksempel vises **8,9** hvis det egendefinerte formatet er **#,##** og tallet som skal formateres er **8,9**. |
| **.** (*punktum*) |Viser desimaltegnet i et tall.  Avhengig av språket til det egendefinerte formatet, kan du se [Globale apper](#global-apps) for mer informasjon. |
| **,** (*komma*) |Viser skilletegnet for grupperinger i et tall, som ofte brukes for tusener. **Text** skiller grupper med komma, hvis formatet inneholder et komma som er omsluttet av nummertegn, (**#**) eller av nuller.  Avhengig av språket til det egendefinerte formatet, kan du se [Globale apper](#global-apps) for mer informasjon. |

Tallet blir avrundet til så mange desimaler som det er plassholdere hvis et tall har flere sifre til høyre for desimaltegnet enn det er plassholdere i formatet. De ekstra sifrene vises hvis det er flere sifre til venstre for desimaltegnet enn det er plassholdere. Tall som er mindre enn 1 starter med et desimaltegn (for eksempel **,47**), hvis formatet bare inneholder nummertegn (#) til venstre for desimaltegnet.

### <a name="date-and-time-placeholders"></a>Plassholdere for dato og klokkeslett

|                                                                                                 Plassholder                                                                                                  |                                                                                                     Beskrivelse                                                                                                     |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                                                                                    **m**                                                                                                     |                                                                               Viser måneden som et tall uten foranstilt null.                                                                                |
|                                                                                                    **mm**                                                                                                    |                                                                        Viser måneden som et tall med foranstilt null når det passer.                                                                         |
|                                                                                                   **mmm**                                                                                                    |                                                                             Viser måneden som en forkortelse (**jan.** til **des.**).                                                                             |
|                                                                                                   **mmmm**                                                                                                   |                                                                          Viser måneden med fullt navn (**januar** til **desember**).                                                                           |
|                                                                                                    **d**                                                                                                     |                                                                                Viser dagen som et tall uten foranstilt null.                                                                                 |
|                                                                                                    **dd**                                                                                                    |                                                                         Viser dagen som et tall med foranstilt null når det passer.                                                                          |
|                                                                                                   **ddd**                                                                                                    |                                                                              Viser dagen som en forkortelse (**sø.** til **lø.**).                                                                              |
|                                                                                                   **dddd**                                                                                                   |                                                                            Viser dagen med fullt navn (**søndag** til **lørdag**).                                                                            |
|                                                                                                    **yy**                                                                                                    |                                                                                      Viser året som et tosifret tall.                                                                                       |
|                                                                                                   **yyyy**                                                                                                   |                                                                                      Viser året som et firesifret tall.                                                                                      |
|                                                                                                    **h**                                                                                                     |                                                                                Viser timen som et tall uten foranstilt null.                                                                                |
|                                                                                                    **hh**                                                                                                    | Viser timen som et tall med foranstilt null når det passer. Hvis formatet inneholder **AM** eller **PM**, blir timen vist basert på 12-timers klokken. Ellers vises timen basert på 24-timers klokken. |
|                                                                                                    **m**                                                                                                     |                                                                         Viser minuttet som et tall uten foranstilt null.  > [!NOTE]                                                                          |
|            > **m**- eller **mm**-koden må stå umiddelbart etter **h**- eller **hh**-koden, eller rett før **ss**-koden, hvis ikke returnerer **Text** måneden i stedet for minutter.            |                                                                                                                                                                                                                     |
|                                                                                                    **mm**                                                                                                    |                                                                   Viser minuttet som et tall med foranstilt null når det passer. > [!NOTE]                                                                   |
| > **m**- eller **mm**-plassholderen må stå umiddelbart etter **h**- eller **hh**-plassholderen, eller umiddelbart foran **ss**-plassholderen. Ellers returnerer **Text** måneden i stedet for minutter. |                                                                                                                                                                                                                     |
|                                                                                                    **s**                                                                                                     |                                                                               Viser sekundet som et tall uten foranstilt null.                                                                               |
|                                                                                                    **ss**                                                                                                    |                                                                        Viser sekundet som et tall med foranstilt null når det passer.                                                                        |
|                                                                                                    **f**                                                                                                     |                                                                                         Viser deler av sekunder.                                                                                          |
|                                                                                    **AM/PM**, **am/pm**, **A/P**, **a/p**                                                                                    |               Viser timen basert på en 12-timers klokke. **Text** returnerer "AM", "am", "A" eller "a" for klokkeslett fra midnatt til midt på dagen, og "PM", "pm", "P" eller "p" for klokkeslett fra midt på dagen frem til midnatt                |

### <a name="literal-placeholders"></a>Litterale plassholdere
Du kan inkludere hvilke som helst av disse tegnene i formatstrengen.  De vil vises i resultatet av **Text** i nåværende tilstand. Ekstra tegn er reservert for fremtidige plassholdere, så du bør ikke bruke dem.

| Tegn | Beskrivelse |
| --- | --- |
| Alle valutasymboler |Dollartegn, centtegn, eurotegn og så videre. |
| **+** |Plusstegn |
| **(** |Venstre parentes |
| **:** |Kolon |
| **^** |Circumfleks (innsettingspunkt) |
| **'** |Apostrof |
| **{** |Venstre klammeparentes |
| **<** |Mindre enn-tegn |
| **=** |Likhetstegn |
| **-** |Minustegn |
| **/** |Skråstrek |
| **)** |Høyre parentes |
| **&** |&-tegn |
| **~** |Tilde |
| **}** |Høyre klammeparentes |
| **>** |Større enn-tegn |
| &nbsp; |Mellomrom-tegn |

## <a name="global-apps"></a>Globale apper
**Text**-funksjonen er globalavhengig.  Den vet hvordan du skal skrive ut datoer, klokkeslett, valuta og tall for en lang rekke språk.  Den er avhengig av to typer informasjon for å fungere:

* **Språket for det egendefinerte formatet:** Hvordan skal et egendefinert format tolkes av forfattere?  Skilletegnene (**.** og **,**) har ulike betydninger på forskjellige språk.  Dette håndteres med en spesiell plassholder som inneholder en språkkode.  [Forhåndsdefinerte formater for dato/klokkeslett](#predefined-datetime-formats) er språkagnostisk, for å gjøre det enda enklere.
* **Språket for resultatet:** Hvilket språk skal brukes i resultatet av funksjonen for brukere?  Navn for måneder og ukedager må være på det aktuelle språket for brukeren av appen.  Dette håndteres med et valgfritt, tredje argument til **Text**-funksjonen. 

Språket er angitt med en [språkkode](function-language.md#language-tags) for begge.  Hvis du vil se listen over støttede språk, kan du skrive inn **Text( 1234, "", )** i formellinjen eller avansert visning og bla gjennom listen over nasjonale innstillinger for det tredje argumentet.

#### <a name="custom-format-language-placeholder"></a>Egendefinert språkformat for plassholder
Hvis du vil angi språket for det egendefinerte formatet, kan du bruke:

| Plassholder | Beskrivelse |
| --- | --- |
| **[$-*LanguageTag*]** |*LanguageTag* er en språkkode som returneres fra **Language**-funksjonen.  Det kan være i form av bare språket, som **[$-en]** for engelsk, eller den kan også inkludere området, som eksempelvis **[$-en-GB]** for ytterligere å spesifisere Storbritannia. |

Plassholderen for språk kan forekomme hvor som helst i det egendefinerte formatet, men bare én gang.

Redigeringsverktøyet setter automatisk inn en språkkode for gjeldende språk hvis du ikke angir en plassholder for språk og formatstrengen er tvetydig fra et global ståsted mens du skriver en formel.  

**[$-en-US]**  antas, hvis plassholderen ikke er til stede når appen kjøres. 

> [!NOTE]
> Syntaksen for denne plassholderen kan endres for å unngå forvirring med en lignende, men forskjellig, plassholder som støttes av Excel i en fremtidig versjon.

#### <a name="result-language-tag"></a>Språkkode for resultatet
Oversatte strenger for måned, ukedag, og angivelser av AM/PM samt en passende gruppe og desimalskilletegn, vises i resultatet av **Text**.

**Text** bruker språket for brukeren som kjører appen som standard.  **Language**-funksjonen returnerer språkkoden for gjeldende bruker.  Du kan overstyre denne standardinnstillingen ved å oppgi en språkkode for det valgfrie tredje argumentet for **Text**.

## <a name="syntax"></a>Syntaks
**Text**( *Number*, *DateTimeFormatEnum* [, *ResultLanguageTag* ] )

* *Number* – obligatorisk. Tallet eller dato/klokkeslett-verdien som skal formateres.
* *DateTimeFormat* – obligatorisk.  Et medlem av opplistingen for **DateTimeFormat**.
* *ResultLanguageTag* – valgfritt.  Språkkoden som skal brukes for resultatteksten.  Språket for gjeldende bruker brukes som standard.

**Text**( *Number*, *CustomFormat* [, *ResultLanguageTag* ] )

* *Number* – obligatorisk. Tallet eller dato/klokkeslett-verdien som skal formateres.
* *CustomFormat* – obligatorisk. Én eller flere plassholdere omsluttet av doble anførselstegn.
* *ResultLanguageTag* – valgfritt.  Språkkoden som skal brukes for resultatteksten.  Språket for gjeldende bruker brukes som standard.

## <a name="examples"></a>Eksempler
Brukeren som kjører disse formlene befinner seg i USA og har valgt engelsk som språket sitt.  **Language**-funksjonen returnerer "en-US".

### <a name="number"></a>Tall

| Formel | Beskrivelse | Resultat |
| --- | --- | --- |
| **Text(&nbsp;1234.59,&nbsp;"####.#"&nbsp;)** |Formaterer tallet med én desimal. |"1234.6" |
| **Text(&nbsp;8.9,&nbsp;"#.000"&nbsp;)** |Pakker, om nødvendig, inn desimaldelen av tallet med etterfølgende nuller. |"8.900" |
| **Text(&nbsp;0.631,&nbsp;"0.#"&nbsp;)** |Pakker, om nødvendig, inn hele delen av tallet med foranstilte nuller. |"0.6" |
| **Text(&nbsp;12,&nbsp;"#.0#"&nbsp;)**<br>**Text(&nbsp;1234.568,&nbsp;"#.0#"&nbsp;)** |Pakker inn desimaldelen av tallet med nuller for en desimalplass, og inneholder en andre desimal, hvis angitt. |"12.0"<br>"1234.57" |
| **Text(&nbsp;12000,&nbsp;"$ #,###"&nbsp;)**<br>**Text(&nbsp;1200000,&nbsp;"$&nbsp;#,###"&nbsp;)** |Plasserer et skilletegn for tusener for hvert tredje siffer, og inkluderer et valutasymbol. |"$&nbsp;12,000"<br>"$&nbsp;1,200,000" |

### <a name="datetime"></a>Dato/klokkeslett
* At **2:37:47 PM** på **Monday, November 23, 2015**
* Tidssonen for USA (UTC-8)

| Formel | Beskrivelse | Resultat |
| --- | --- | --- |
| **Text( Now(), DateTimeFormat.LongDate )** |Formateres som en lang datostreng i språk- og nasjonale innstillinger for gjeldende bruker. |"Monday, November 23, 2015" |
| **Text( Now(), DateTimeFormat.LongDateTime )** |Formateres som en lang dato- og klokkeslett-streng i språk- og nasjonale innstillinger for gjeldende bruker, ved bruk av en 12-timers klokke. |"Monday, November 23, 2015 2:37:47 PM" |
| **Text( Now(), DateTimeFormat.LongTime24 )** |Formateres som en streng over lang tid, ved hjelp av en 24-timers klokke. |"14:37:47" |
| **Text( Now(), DateTimeFormat.ShortDate )** |Formateres som en kort datostreng i språk- og nasjonale innstillinger for gjeldende bruker. |"11/23/2015" |
| **Text( Now(), "d-mmm-yy" )** |Formateres ved hjelp av plassholdertegn: <ul><li>**d** for en ensifret eller tosifret dag i måneden<li>**-** kopiert til resultatet som et litteralt tegn<li>**mmm** for en forkortelse av måneden på tre bokstaver<li>**-** kopiert til resultatet som et annet litteralt tegn<li>**yy** for en tosifret forkortelse for året</ul> |"23-Nov-15" |

### <a name="global-apps"></a>Globale apper

| Formel | Beskrivelse | Resultat |
| --- | --- | --- |
| **Text( 1234567.89, "[$-en-US]$ #,###" )** |Tolkes **,** som et skilletegn for grupperinger, plassert for hvert tredje tegn og **$** som det gjeldende valutasymbolet. Siden ingen desimaler skal vises, er verdien avrundet oppover til neste heltall. **[$-en-US]** er valgfritt i dette tilfellet, da dette er standard. |"$ 1,234,568" |
| **Text( 1234567.89, "[$-es-ES]&euro; #,###" )** |Tolker **,** som et desimalskilletegn og **&euro;** som valutasymbolet.  Fordi **[$-fr-FR]** bare avgjør hvordan formatstrengen tolkes, vil resultatet bruke tegn fra standard språkkode for "en-US": **.** (punktum) for desimalskilletegn og **$** for valutasymbol. |"$ 1234567.89" |
| **Text( 1234567.89, "[$-es-ES]&euro; #,###", "es-ES" )** |Tolker **,** som et desimalskilletegn.  Språkkoden for resultatet er satt til "fr-FR" som vil resultere i at **,** (komma) blir brukt som desimalskilletegn og **&euro;** som valutasymbol. |"&euro; 1234567,89" |
| **Text( Date(2016,1,31), "dddd mmmm d" )** |Returnerer ukedagen, måneden og dagen i måneden i språket for gjeldende bruker. Fordi ingen av plassholderne er språkavhengige, er det ikke behov for en språkkode for tekstformat. |"Saturday January 31" |
| **Text( Date(2016,1,31), "dddd mmmm d", "es-ES" )** |Returnerer ukedagen, måneden og dagen i måneden i "es-ES"-språket. |"domingo enero 31" |

