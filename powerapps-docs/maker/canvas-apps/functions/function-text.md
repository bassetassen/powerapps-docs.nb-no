---
title: Text-funksjonen | Microsoft Docs
description: Referanseinformasjon, herunder syntaks og eksempler for Text-funksjonen i PowerApps
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 11/14/2018
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 67c0e83245b60345f74912f2f005295c94cc0dd1
ms.sourcegitcommit: aa9f78c304fe46922aecfe3b3fadb6bda72dfb23
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 05/24/2019
ms.locfileid: "66215943"
ms.PowerAppsDecimalTransform: true
---
# <a name="text-function-in-powerapps"></a>Text-funksjonen i PowerApps
Konverterer en verdi og formaterer en tall- eller dato/klokkeslett-verdi til en tekststreng.

## <a name="description"></a>Beskrivelse
**Text**-funksjonen formaterer et tall eller en verdi for dato/klokkeslett som er basert på én av disse typene argumenter:

* Et forhåndsdefinert dato/klokkeslett-format, som du angir ved hjelp av opplistingen for **DateTimeFormat**. Denne tilnærmingen er foretrukket for datoer og klokkeslett, da den automatisk justeres til hver brukers språk og område.
* Et egendefinert format, som består av en streng med plassholdere, som definerer, for eksempel om tall Vis desimalskilletegn og datoer Vis det fullstendige navnet på måneden, måneden som en forkortelse eller måneden som et tall. PowerApps støtter et delsett av plassholderne, i likhet med Microsoft Excel. Angir språket som å tolke andre plassholderne i denne strengen, plassholderen for språk. Hvis det egendefinerte formatet inneholder et punktum, for eksempel plassholderen for språk-format Angir om perioden er et desimalskilletegn (Japan) eller et skilletegn (es-ES).

Hvis du vil ha mer informasjon, kan du se[Slik arbeider du med datoer og klokkeslett](../show-text-dates-times.md).

Den **tekst** funksjonen kan også konvertere enhver datatype til en tekstrepresentasjon ved hjelp av et standardformat. Bruk denne til å sende verdier uten tekst til tekstbaserte funksjoner som [ **Len**](function-len.md), [ **høyre**](function-left-mid-right.md), og [  **IsMatch**](function-ismatch.md).

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
| **.** (*punktum*) |Viser desimaltegnet i et tall. Avhengig av språket for det egendefinerte formatet; Se [globale apper](#global-apps) for mer informasjon. |
| **,** (*komma*) |Viser skilletegnet for grupperinger i et tall, som ofte brukes for tusener. **Text** skiller grupper med komma, hvis formatet inneholder et komma som er omsluttet av nummertegn, ( **#** ) eller av nuller. Avhengig av språket for det egendefinerte formatet; Se [globale apper](#global-apps) for mer informasjon. |

Tallet blir avrundet til så mange desimaler som det er plassholdere hvis et tall har flere sifre til høyre for desimaltegnet enn det er plassholdere i formatet. De ekstra sifrene vises hvis det er flere sifre til venstre for desimaltegnet enn det er plassholdere. Tall som er mindre enn 1 starter med et desimaltegn (for eksempel **,47**), hvis formatet bare inneholder nummertegn (#) til venstre for desimaltegnet.

### <a name="date-and-time-placeholders"></a>Plassholdere for dato og klokkeslett

|   Plassholder    |   Beskrivelse                                                  |
|------------------|----------------------------------------------------------------|
|  **m**   |   Viser måneden som et tall uten foranstilt null.               |
|  **mm**  |   Viser måneden som et tall med foranstilt null når det passer. |
|  **mmm** |   Viser måneden som en forkortelse (**jan.** til **des.** ).          |
|                                                                                                   **mmmm**                                                                                                   |                                                                          Viser måneden med fullt navn (**januar** til **desember**).                                                                           |
|                                                                                                    **d**                                                                                                     |                                                                                Viser dagen som et tall uten foranstilt null.                                                                                 |
|                                                                                                    **dd**                                                                                                    |                                                                         Viser dagen som et tall med foranstilt null når det passer.                                                                          |
|                                                                                                   **ddd**                                                                                                    |                                                                              Viser dagen som en forkortelse (**sø.** til **lø.** ).                                                                              |
|                                                                                                   **dddd**                                                                                                   |                                                                            Viser dagen med fullt navn (**søndag** til **lørdag**).                                                                            |
|                                                                                                    **yy**                                                                                                    |                                                                                      Viser året som et tosifret tall.                                                                                       |
|                                                                                                   **yyyy**                                                                                                   |                                                                                      Viser året som et firesifret tall.                                                                                      |
|                                                                                                    **h**                                                                                                     |                                                                                Viser timen som et tall uten foranstilt null.                                                                                |
|   **hh** | Viser timen som et tall med foranstilt null når det passer. Hvis formatet inneholder **AM** eller **PM**, blir timen vist basert på 12-timers klokken. Ellers vises timen basert på 24-timers klokken. | 
|  **m**   |   Viser minuttet som et tall uten foranstilt null.<br><br>Denne plassholderen må stå umiddelbart etter den **h** eller **hh** kode eller rett før den **ss** koden, ellers **tekst** returnerer måneden i stedet for minutter.  |    
| **mm**   | Viser minuttet som et tall med foranstilt null når det passer.<br><br>Denne plassholderen må stå umiddelbart etter den **h** eller **hh** plassholder eller rett før den **ss** plassholder. Ellers **tekst** Returnerer måneden i stedet for minutter. |                                                                                                                   
| **s**   |  Viser sekundet som et tall uten foranstilt null.  |
| **ss**  | Viser sekundet som et tall med foranstilt null når det passer.                                                                        |
|                                                                                                    **f**                                                                                                     |                                                                                         Viser deler av sekunder.                                                                                          |
|                                                                                    **AM/PM**, **en / p**                                                                                    |               Viser timen basert på en 12-timers klokke. **Tekst** returnerer "AM" eller "a" for klokkeslett fra midnatt til midt på dagen og "PM" eller "p" for klokkeslett fra midt på dagen frem til midnatt                |

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
**Text**-funksjonen er globalavhengig. Den vet hvordan du skal skrive ut datoer, klokkeslett, valuta og tall for en lang rekke språk. Den er avhengig av to typer informasjon for å fungere:

* **Språket for det egendefinerte formatet:** Produsentene, hvordan skal et egendefinert format tolkes? Skilletegnene ( **.** og **,** ) har ulike betydninger på forskjellige språk. Hvis du angir et egendefinert format, kan du ta med en plassholder for språk eller ta standardverdien, som gjenspeiler språket som er angitt for enheten. Enklere, kan du bruke ett av de [forhåndsdefinerte formater for dato/klokkeslett](#predefined-datetime-formats), som er språkagnostisk.
* **Språket for resultatet:** For brukere, hvilket språk skal funksjonen resultatet vises? Navn på måneder og ukedager må være i det aktuelle språket for brukeren av appen, som du kan angi ved å legge til en tredje, valgfritt argument til den **tekst** funksjonen. 

For begge, angi språket ved hjelp av en [språkkode](function-language.md#language-tags). Hvis du vil se listen over støttede språk, skriver du inn **tekst (1234, "",)** i formellinjen eller **avansert** fanen i den høyre ruten, og deretter Bla gjennom listen over språk som foreslås for det tredje argumentet.

### <a name="language-placeholder"></a>Plassholder for språk
Hvis du vil angi språket for det egendefinerte formatet, kan du bruke:

| Plassholder | Beskrivelse |
| --- | --- |
| **[$-*LanguageTag*]** |*LanguageTag* er en språkkode som returneres fra **Language**-funksjonen. Det kan angi bare språket (som **[$-en]** for engelsk), eller det kan også angi området (som **[$-en-GB]** for ytterligere å spesifisere Storbritannia). |

Plassholderen for språk kan forekomme hvor som helst i det egendefinerte formatet, men bare én gang.

Hvis du angir et egendefinert format uten en plassholder for språk og formatet er tvetydig fra et global ståsted, settes inn automatisk språkkoden for gjeldende språk.  

**[$-en-US]**  antas Hvis dette plassholder er ikke finnes når appen kjøres. 

> [!NOTE]
> Syntaksen for denne plassholderen kan endres for å unngå forvirring med en lignende, men forskjellig, plassholder som støtter Excel i en fremtidig versjon.

### <a name="result-language-tag"></a>Språkkode for resultatet
Resultatet av **tekst** inkluderer oversatte strenger for måneder, ukedager, og angivelser av AM/PM samt en passende gruppe og desimalskilletegn.

**Text** bruker språket for brukeren som kjører appen som standard. **Language**-funksjonen returnerer språkkoden for gjeldende bruker. Du kan overstyre denne standardverdien ved å oppgi en språkkode for det tredje argumentet for **tekst**.

## <a name="syntax"></a>Syntaks
**Text**( *NumberOrDateTime*; *DateTimeFormatEnum* [; *ResultLanguageTag* ] )

* *NumberOrDateTime* – obligatorisk. Tallet eller dato/klokkeslett-verdien som skal formateres.
* *DateTimeFormat* – obligatorisk.  Et medlem av opplistingen for **DateTimeFormat**.
* *ResultLanguageTag* – valgfritt. Språkkoden som skal brukes for resultatteksten. Språket for gjeldende bruker brukes som standard.

**Tekst**( *NumberOrDateTime*; *CustomFormat* [; *ResultLanguageTag* ])

* *Number* – obligatorisk. Tallet eller dato/klokkeslett-verdien som skal formateres.
* *CustomFormat* – obligatorisk. Én eller flere plassholdere omsluttet av doble anførselstegn.
* *ResultLanguageTag* – valgfritt. Språkkoden som skal brukes for resultatteksten. Språket for gjeldende bruker brukes som standard.

**Tekst**( *AnyValue* )

* *AnyValue* – obligatorisk. Verdien som skal konverteres til en tekstrepresentasjon. Et standardformat som brukes.

## <a name="examples"></a>Eksempler
Med mindre annet er angitt, vil brukeren som kjører disse formlene befinner seg i USA og har valgt engelsk som språket sitt.  **Language**-funksjonen returnerer "en-US".

### <a name="number"></a>Tall

| Formel | Beskrivelse | Resultat |
| --- | --- | --- |
| **Text(&nbsp;1234,59;&nbsp;"####.#"&nbsp;)** |Formaterer tallet med én desimal. |"1234.6" |
| **Text(&nbsp;8,9;&nbsp;"#.000"&nbsp;)** |Pakker, om nødvendig, inn desimaldelen av tallet med etterfølgende nuller. |"8.900" |
| **Text(&nbsp;0,631;&nbsp;"0.#"&nbsp;)** |Pakker, om nødvendig, inn hele delen av tallet med foranstilte nuller. |"0.6" |
| **Text(&nbsp;12;&nbsp;"#.0#"&nbsp;)**<br>**Text(&nbsp;1234,568;&nbsp;"#.0#"&nbsp;)** |Pakker inn desimaldelen av tallet med nuller for en desimalplass, og inneholder en andre desimal, hvis angitt. |"12.0"<br>"1234.57" |
| **Text(&nbsp;12000;&nbsp;"$ #,###"&nbsp;)**<br>**Text(&nbsp;1200000;&nbsp;"$&nbsp;#,###"&nbsp;)** |Plasserer et skilletegn for tusener for hvert tredje siffer, og inkluderer et valutasymbol. |"$&nbsp;12,000"<br>"$&nbsp;1,200,000" |

### <a name="datetime"></a>Dato/klokkeslett
* At **2:37:47 PM** på **Monday, November 23, 2015**
* Tidssonen for USA (UTC-8)

| Formel | Beskrivelse | Resultat |
| --- | --- | --- |
| **Text( Now(); DateTimeFormat.LongDate )** |Formateres som en lang datostreng i språk- og nasjonale innstillinger for gjeldende bruker. |"Monday, November 23, 2015" |
| **Text( Now(); DateTimeFormat.LongDateTime )** |Formateres som en lang dato- og klokkeslett-streng i språk- og nasjonale innstillinger for gjeldende bruker, ved bruk av en 12-timers klokke. |"Monday, November 23, 2015 2:37:47 PM" |
| **Text( Now(); DateTimeFormat.LongTime24 )** |Formateres som en streng over lang tid, ved hjelp av en 24-timers klokke. |"14:37:47" |
| **Text( Now(); DateTimeFormat.ShortDate )** |Formateres som en kort datostreng i språk- og nasjonale innstillinger for gjeldende bruker. |"11/23/2015" |
| **Text( Now(); "d-mmm-yy" )** |Formateres ved hjelp av plassholdertegn: <ul><li>**d** for en ensifret eller tosifret dag i måneden<li>**-** kopiert til resultatet som et litteralt tegn<li>**mmm** for en forkortelse av måneden på tre bokstaver<li>**-** kopiert til resultatet som et annet litteralt tegn<li>**yy** for en tosifret forkortelse for året</ul> |"23-Nov-15" |
| **Tekst (1448318857 * 1000, "mmm. dd, åååå (tt: mm: ss AM/PM)»)** | Viser en Unix dato / klokkeslett-verdi i lesbar format hvis du for å multiplisere kildeverdien etter 1000. | «. November 23, 2015 (02:47:37 PM)» |

### <a name="global-apps"></a>Globale apper

| Formel | Beskrivelse | Resultat |
| --- | --- | --- |
| **Tekst (1234567,89; "[$-fr-FR] # ###, ## &euro;"; "fr-FR")** | Viser et mellomrom som et skilletegn for grupperinger, komma som desimalskilletegn, og **&euro;** som valutasymbol. |"1&nbsp;234&nbsp;567,89 &euro;" |
| **Tekst (1234567;89;; «[$-fr-FR] # ###; ## &euro;»)** | Hvis kildedataene følger det franske egendefinert ved å bruke et komma som desimaltegn, må du endre de nasjonale innstillingene til fransk og skiller argumentene med et semikolon i stedet for et komma til får du samme resultat som ovenfor. |"1&nbsp;234&nbsp;567,89 &euro;" |
| **Text( Date(2016;1;31); "dddd mmmm d" )** |Returnerer ukedagen, måneden og dagen i måneden i språket for gjeldende bruker. Fordi ingen av plassholderne er språkavhengige, er det ikke behov for en språkkode for tekstformat. |«Lørdag&nbsp;januar&nbsp;31» |
| **Text( Date(2016;1;31); "dddd mmmm d"; "es-ES" )** |Returnerer ukedagen, måneden og dagen i måneden i "es-ES"-språket. |"domingo&nbsp;enero&nbsp;31" |

### <a name="converting-values-to-text"></a>Konvertering av verdier til tekst

| Formel | Beskrivelse | Resultat |
| --- | --- | --- |
| **Tekst (&nbsp;1234567.89&nbsp;)** | Konverterer et tall til en streng. Det finnes ingen tusenvis skilletegn eller kontroll over hvor mange sifre før eller etter desimaltegnet; for større kontroll, angi plassholdere for tall som det andre argumentet. | "1234567.89" |
| **Tekst (&nbsp;DateTimeValue (&nbsp;"01/04/2003"&nbsp;)&nbsp;)** | Konverterer en dato/klokkeslett-verdi til en tekststreng. For å styre konverteringen, gir du enten et medlem av opplistingen DateTimeFormat eller en egendefinert formatstreng. | "1/4/2003 12:00 AM" |
| **Tekst (&nbsp;SANN&nbsp;)** | Konverterer en boolsk verdi til en streng. | "true" |
| **Text(&nbsp;GUID()&nbsp;)** | Konverterer en generert GUID-verdi til en streng.  | "f8b10550-0f12-4f08-9aa3-bb10958bc3ff" |
| **Left(&nbsp;Text(&nbsp;GUID()&nbsp;);&nbsp;4&nbsp;)** | Returnerer de første fire tegnene i en generert GUID. | «2d9c» | 
