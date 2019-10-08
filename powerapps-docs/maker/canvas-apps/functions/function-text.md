---
title: Text-funksjonen | Microsoft Docs
description: Referanseinformasjon, herunder syntaks og eksempler for Text-funksjonen i PowerApps
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 11/14/2018
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: ac0291abababb807628fa224ba8292daf1064d23
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/07/2019
ms.locfileid: "71991887"
ms.PowerAppsDecimalTransform: true
---
# <a name="text-function-in-powerapps"></a>Text-funksjonen i PowerApps
Konverterer enhver verdi og formaterer et tall eller en dato/klokkeslett-verdi til en tekst streng.

## <a name="description"></a>Beskrivelse
**Text**-funksjonen formaterer et tall eller en verdi for dato/klokkeslett som er basert på én av disse typene argumenter:

* Et forhåndsdefinert dato/klokkeslett-format, som du angir ved hjelp av opplistingen for **DateTimeFormat**. For datoer og klokkeslett foretrekkes denne Fremgangs måten når den justeres automatisk til hver brukers språk og område.
* Et egen definert format, som består av en streng med plassholdere som definerer for eksempel om tall viser et desimal skille tegn og datoer viser det fullstendige navnet på måneden, måneden som en forkortelse eller måneden som et tall. PowerApps støtter et delsett av plassholderne, i likhet med Microsoft Excel. I denne strengen angir språk plass holde ren et språk som de andre plassholderne skal tolkes i. Hvis det egen definerte formatet inneholder et punktum, angis for eksempel plass holde ren for språk format om perioden er et desimal skille tegn (Japan – JP) eller et tusen skille tegn (ES-ES).

Hvis du vil ha mer informasjon, kan du se[Slik arbeider du med datoer og klokkeslett](../show-text-dates-times.md).

**Text** -funksjonen kan også konvertere en hvilken som helst datatype til en tekst representasjon ved hjelp av et standard format. Bruk denne til å sende verdier uten tekst til tekstbaserte funksjoner, for eksempel [**len**](function-len.md), [**høyre**](function-left-mid-right.md)og [**IsMatch**](function-ismatch.md).

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
| **.** (*punktum*) |Viser desimaltegnet i et tall. Avhenger av språket for det egen definerte formatet. se [globale apper](#global-apps) for mer informasjon. |
| **,** (*komma*) |Viser skilletegnet for grupperinger i et tall, som ofte brukes for tusener. **Text** skiller grupper med komma, hvis formatet inneholder et komma som er omsluttet av nummertegn, ( **#** ) eller av nuller. Avhenger av språket for det egen definerte formatet. se [globale apper](#global-apps) for mer informasjon. |

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
|  **m**   |   Viser minuttet som et tall uten foranstilt null.<br><br>Denne plass holde ren må vises umiddelbart etter **h** -eller **HH** -koden, eller umiddelbart før **SS** -koden. Hvis ikke, returnerer **text** måneden i stedet for minutter.  |    
| **mm**   | Viser minuttet som et tall med foranstilt null når det passer.<br><br>Denne plass holde ren må vises umiddelbart etter **h** -eller **HH** -plassholderen, eller rett før **Start** plass holde ren. Hvis ikke, returnerer **text** måneden i stedet for minutter. |                                                                                                                   
| **s**   |  Viser sekundet som et tall uten foranstilt null.  |
| **ss**  | Viser sekundet som et tall med foranstilt null når det passer.                                                                        |
|                                                                                                    **f**                                                                                                     |                                                                                         Viser deler av sekunder.                                                                                          |
|                                                                                    **AM/PM**, **a/p**                                                                                    |               Viser timen basert på en 12-timers klokke. **Teksten** returnerer «am» eller «a» for klokkeslett fra midnatt til 12:00 og «PM» eller «p» for klokkeslett fra 12:00 til midnatt                |

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

* **Språket for det egen definerte formatet:** For en hvilken som helst egen definert format blir det tolket? Skilletegnene ( **.** og **,** ) har ulike betydninger på forskjellige språk. Hvis du angir et egen definert format, kan du inkludere en plassholder for språk eller ta standard verdien, som gjenspeiler språket som enheten er angitt på. Du kan også bruke ett av de [forhånds definerte formatene for dato/klokkeslett](#predefined-datetime-formats), som er språk agnostisk.
* **Språket for resultatet:** For brukere, hvilket språk skal funksjons resultatet vises? Navn på måneder og ukedager må være på det aktuelle språket for brukeren av appen, som du kan angi ved å legge til et tredje, valg fritt argument i **tekst** -funksjonen. 

For begge angir du språket ved hjelp av en [språk kode](function-language.md#language-tags). Hvis du vil se listen over støttede språk, skriver du inn **tekst (1234, «»,)** i formel linjen eller **Avansert** -fanen i ruten til høyre, og deretter blar du gjennom listen over nasjonale innstillinger som er foreslått for det tredje argumentet.

### <a name="language-placeholder"></a>Plassholder for språk
Hvis du vil angi språket for det egendefinerte formatet, kan du bruke:

| Plassholder | Beskrivelse |
| --- | --- |
| **[$-*LanguageTag*]** |*LanguageTag* er en språkkode som returneres fra **Language**-funksjonen. Den kan angi bare språket (for eksempel **[$-en]** for engelsk), eller det kan også angi området (for eksempel **[$-en-GB]** for ytterligere å angi Storbritannia). |

Plassholderen for språk kan forekomme hvor som helst i det egendefinerte formatet, men bare én gang.

Hvis du angir et egen definert format uten språk plass holde ren og formatet er tvetydig fra et globalt stå sted, settes språk koden for gjeldende språk inn automatisk.  

**[$-en-us]** antas Hvis denne plass holde ren ikke er til stede når appen kjøres. 

> [!NOTE]
> I en fremtidig versjon kan syn tak sen for denne plass holde ren endres for å unngå forvirring med lignende, men forskjellig, plassholder som Excel støtter.

### <a name="result-language-tag"></a>Språkkode for resultatet
Resultatet av **teksten** inneholder oversatte strenger for måneder, ukedager og AM/PM-betegnelser, i tillegg til passende gruppe-og desimal skille tegn.

**Text** bruker språket for brukeren som kjører appen som standard. **Language**-funksjonen returnerer språkkoden for gjeldende bruker. Du kan overstyre denne standard verdien ved å oppgi en språk kode for det tredje argumentet til **tekst**.

## <a name="syntax"></a>Syntaks
**Text**( *NumberOrDateTime*; *DateTimeFormatEnum* [; *ResultLanguageTag* ])

* *NumberOrDateTime* – obligatorisk. Tallet eller dato/klokkeslett-verdien som skal formateres.
* *DateTimeFormat* – obligatorisk.  Et medlem av opplistingen for **DateTimeFormat**.
* *ResultLanguageTag* – valgfritt. Språkkoden som skal brukes for resultatteksten. Språket for gjeldende bruker brukes som standard.

**Text**( *NumberOrDateTime*; *CustomFormat* [; *ResultLanguageTag* ])

* *Number* – obligatorisk. Tallet eller dato/klokkeslett-verdien som skal formateres.
* *CustomFormat* – obligatorisk. Én eller flere plassholdere omsluttet av doble anførselstegn.
* *ResultLanguageTag* – valgfritt. Språkkoden som skal brukes for resultatteksten. Språket for gjeldende bruker brukes som standard.

**Tekst**( *AnyValue* )

* *AnyValue* – obligatorisk. Verdi som skal konverteres til en tekst representasjon. Et standard format brukes.

## <a name="examples"></a>Eksempler
Hvis ikke annet er angitt, befinner brukeren som kjører disse formlene, i USA og har valgt engelsk som sitt språk.  **Language**-funksjonen returnerer "en-US".

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
| **Tekst (1448318857 * 1000, «mmm. dd, yyyy (hh: mm: ss AM/PM)»** | Viser en dato/klokkeslett-verdi for UNIX i et lesbart format hvis du multipliserer kilde verdien med 1 000. | «Nov. 23, 2015 (02:47:37 PM)» |

### <a name="global-apps"></a>Globale apper

| Formel | Beskrivelse | Resultat |
| --- | --- | --- |
| **Text (1234567,89; "[$-fr-FR] # # # #, # # &euro;"; "fr-FR")** | Viser et mellomrom som et grupperings skille tegn, kommaet som desimal skille tegn og **&euro;** som valuta symbol. |"1 @ no__t-0234 @ no__t-1567, 89 &euro;» |
| **Tekst (1234567; 89;; "[$-fr-FR] # # # #, # # &euro;")** | Hvis kilde dataene følger fransk egen definert for å bruke komma som desimal skille tegn, må du endre den nasjonale innstillingen til fransk og atskille argumentene med et semikolon i stedet for et komma for å få samme resultat som ovenfor. |"1 @ no__t-0234 @ no__t-1567, 89 &euro;» |
| **Text( Date(2016;1;31); "dddd mmmm d" )** |Returnerer ukedagen, måneden og dagen i måneden i språket for gjeldende bruker. Fordi ingen av plassholderne er språkavhengige, er det ikke behov for en språkkode for tekstformat. |"Lørdag @ no__t-0January @ no__t-131» |
| **Text( Date(2016;1;31); "dddd mmmm d"; "es-ES" )** |Returnerer ukedagen, måneden og dagen i måneden i "es-ES"-språket. |«Domingo @ no__t-0enero @ no__t-131» |

### <a name="converting-values-to-text"></a>Konvertere verdier til tekst

| Formel | Beskrivelse | Resultat |
| --- | --- | --- |
| **Tekst (&nbsp;1234567.89 @ no__t-2)** | Konverterer et tall til en streng. Det finnes ingen tusen skille tegn eller kontroll over antall sifre før eller etter desimal skille tegnet. Hvis du vil ha mer kontroll, kan du angi plassholdere for tall som det andre argumentet. | "1234567,89" |
| **Text (&nbsp;DateTimeValue (&nbsp; «01/04/2003» &nbsp;) &nbsp;)** | Konverterer en dato/klokkeslett-verdi til en tekst streng. Hvis du vil kontrollere konverteringen, kan du angi et medlem av DateTimeFormat-opplistingen eller en streng med egen definert format. | "1/4/2003 12:00" |
| **Tekst (&nbsp;true @ no__t-2)** | Konverterer en boolsk verdi til en streng. | like |
| **Tekst (&nbsp;GUID () &nbsp;)** | Konverterer en generert GUID-verdi til en streng.  | "f8b10550-0f12-4f08-9aa3-bb10958bc3ff" |
| **Left (&nbsp;Text (&nbsp;GUID () &nbsp;), &nbsp;4 @ no__t-5)** | Returnerer de fire første tegnene i en generert GUID. | "2d9c" | 
