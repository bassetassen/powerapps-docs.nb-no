---
title: IsMatch, samsvar og MatchAll | Microsoft Docs
description: Referanseinformasjon, inkludert syntaks, for funksjonene IsMatch, sammenligne og MatchAll i PowerApps
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 01/15/2019
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 7141d3b9a2ba6bf18bffe1756d0d7de048606cad
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/23/2019
ms.locfileid: "61563247"
---
# <a name="ismatch-match-and-matchall-functions-in-powerapps"></a>IsMatch, sammenligne og MatchAll funksjoner i PowerApps
Tester for en match eller trekker ut deler av en tekststreng som er basert på et mønster.

## <a name="description"></a>Beskrivelse
**IsMatch**-funksjonen tester om en tekststreng samsvarer med et mønster, som kan omfatte vanlige tegn, forhåndsdefinerte mønstre eller et [vanlig uttrykk](#regular-expressions).  Den **Match** og **MatchAll** funksjonene returnerer hva ble samsvart, inkludert deloverensstemmelser.  

Bruk **IsMatch** til å validere det en bruker har skrevet inn i en **[tekstinndata](../controls/control-text-input.md)**-kontroll. Du kan for eksempel kontrollere om brukeren har angitt en gyldig e-postadresse før resultatet lagres i datakilden. Hvis oppføringen ikke samsvarer med vilkårene dine, kan du legge til andre kontroller som ber brukeren om å rette oppføringen.

Bruk **samsvarer med** til å trekke ut den første tekststrengen som samsvarer med et mønster og **MatchAll** til å trekke ut alle tekststrenger som samsvarer med. Du kan også trekke ut deloverensstemmelser for å analysere komplekse strenger.   

**Samsvarer med** returnerer en post med informasjon for det første treffet den finner, og **MatchAll** returnerer en tabell med poster for hver treff. Posten eller postene inneholder:

| Kolonne | Type | Beskrivelse |
|----|----|----|
| *med navnet sub&#8209;samsvarer med eller sub&#8209;samsvarer med* | Text | Hvert navngitte delrapport treff skal ha sin egen kolonne. Opprette et navngitt delrapport treff ved hjelp av **(?&lt; *navnet*&gt;**... **)** i det vanlige uttrykket. Hvis et navngitt delrapport treff har samme navn som en av de forhåndsdefinerte kolonnene (nedenfor), en delrapport lik prioriteres, og en advarsel genereres. Hvis du vil unngå denne advarselen, gi nytt navn til en delrapport lik. |
| **FullMatch** | Text | Alle tekststrengen som ble samsvart. |
| **StartMatch** | Tall | Startposisjonen for treff i inndata tekststrengen. Det første tegnet i strengen returnerer 1. | 
| **SubMatches** | Tabell med én kolonne med tekst (kolonnen **verdien**) | Tabellen med med og uten navn deloverensstemmelser i rekkefølgen de vises i det vanlige uttrykket. Generelt, navngitte deloverensstemmelser er enklere å arbeide med og oppfordres. Bruk den [ **ForAll** ](function-forall.md) funksjonen eller [ **siste**](function-first-last.md)( [ **FirstN**](function-first-last.md)() **...**  )) funksjoner til å fungere med et enkelt delrapport treff. Hvis ingen deloverensstemmelser er definert i det vanlige uttrykket, er denne tabellen tilgjengelig, men tom. |

Disse funksjonene støtter [ **MatchOptions**](#match-options). Som standard: 
- Disse funksjonene kan du utføre et samsvar for små og store bokstaver. Bruk **IgnoreCase** til å utføre store bokstaver treff.    
- **IsMatch** samsvarer med hele tekststrengen (**fullført** MatchOption), mens **samsvarer med** og **MatchAll** Søk etter et treff hvor som helst i tekststrengen ( **Inneholder** MatchOption). Bruk **fullført**, **Contains**, **BeginsWith**, eller **EndsWith** som passer ditt scenario.

**IsMatch** returnerer *sann* hvis tekststrengen samsvarer med mønsteret eller *usann* hvis den ikke gjør det. **Samsvarer med** returnerer *tom* Hvis ingen forekomst blir funnet som kan testes med den [ **IsBlank** ](function-isblank-isempty.md) funksjonen. **MatchAll** returnerer en tom tabell hvis ingen treff som kan testes med den [ **IsEmpty** ](function-isblank-isempty.md) funksjonen.

Hvis du bruker **MatchAll** Hvis du vil dele en tekststreng, bør du bruke den **[del](function-split.md)** -funksjonen, som er enklere å bruke og raskere.

## <a name="patterns"></a>Mønstre
Nøkkelen til å bruke disse funksjonene er beskrive mønsteret teksten skal samsvare med. Du beskriver mønsteret i en tekststreng som en kombinasjon av:

* Vanlige tegn, for eksempel **abc** eller **123**.
* Forhåndsdefinerte mønstre, for eksempel **Letter**, **MultipleDigits** eller **Email**. (**Match**-enumeratoren definerer disse mønstrene.)
* Vanlige uttrykk koder, som **"\d+\s+\d+"** eller **"[a-z] + «**.

Kombiner disse elementene ved hjelp av den [Strengsammensetning operatoren **&** ](operators.md). For eksempel: **abc & Digit & \s+** er et gyldig mønster som samsvarer med tegnene a, b og c, etterfulgt av et tall mellom 0 og 9, etterfulgt av minst ett mellomromstegn.

### <a name="ordinary-characters"></a>Vanlige tegn
Det enkleste mønsteret er en rekke vanlige tegn som skal samsvare nøyaktig.

For eksempel når den brukes med den **IsMatch** -funksjonen, strengen «Hei» samsvarer med mønsteret **«Hello»** nøyaktig. Ikke mer eller mindre. Strengen «hei!» samsvarer ikke med mønsteret på grunn av utropstegnet på slutten, og fordi bokstav er feil for bokstaven "h". (Se [MatchOptions](#match-options) for hvordan du kan endre denne virkemåten.)

Bestemte tegn er reservert for spesielle formål i mønsterspråket. Hvis du vil bruke disse tegnene, enten foranstille tegnet med en **\\** (omvendt skråstrek) for å angi at tegnet skal tas bokstavelig, eller bruk en av de forhåndsdefinerte mønstrene som er beskrevet senere i dette emnet. Denne tabellen viser spesialtegnene:

| Spesialtegn | Beskrivelse |
| --- | --- |
| **.** |prikk eller punktum |
| **?** |spørsmålstegn |
| **&#42;** |stjerne |
| **\+** |pluss |
| **( )** |parentes |
| **[ ]** |hakeparenteser |
| **{ }** |klammeparenteser |
| **^** |cirkumflekstegn |
| **$** |dollartegn |
| **\|** |loddrett strek |
| **\\** |omvendt skråstrek |

Du kan for eksempel samsvare «Hei?» ved hjelp av mønsteret **Hei\\?** med en omvendt skråstrek foran spørsmålstegnet.

### <a name="predefined-patterns"></a>Forhåndsdefinerte mønstre
Forhåndsdefinerte mønstre er det enkelt å samsvare med enten av et sett med tegn eller en sekvens med flere tegn. Bruk den [Strengsammensetning operatoren **&** ](operators.md) til å kombinere egne tekststrenger med medlemmer av den **Match** enum:

| Match-Enumerator | Beskrivelse | Vanlig uttrykk |
| --- | --- | --- |
| **Any** |Samsvarer med et hvilket som helst tegn. |`.` |
| **Comma** |Samsvarer med et komma. |`,` |
| **Digit** |Samsvarer med ett enkelt siffer (fra 0 til 9). |`\d` |
| **Email** |Samsvarer med en e-postadresse som inneholder en krøllalfa (\@) og et domenenavn som inneholder et punktum (.) |`.+\@.+\\.[^\\.]{2,}` |
| **Hyphen** |Samsvarer med en bindestrek. |`\-` |
| **LeftParen** |Samsvarer med en venstreparentes «(». |`\(` |
| **Letter** |Samsvarer med en bokstav. |`\p{L}` |
| **MultipleDigits** |Samsvarer med ett eller flere sifre. |`\d+` |
| **MultipleLetters** |Samsvarer med én eller flere bokstaver. |`\p{L}+` |
| **MultipleNonSpaces** |Samsvarer med ett eller flere tegn som ikke legger til mellomrom (ikke mellomrom, tabulator eller ny linje). |`\S+` |
| **MultipleSpaces** |Samsvarer med ett eller flere tegn som legger til mellomrom (mellomrom, tabulator eller ny linje). |`\s+` |
| **NonSpace** |Samsvarer med ett enkelt tegn som ikke legger til mellomrom. |`\S` |
| **OptionalDigits** |Samsvarer med ingen, ett eller flere siffer. |`\d*` |
| **OptionalLetters** |Samsvarer med ingen, én eller flere bokstaver. |`\p{L}*` |
| **OptionalNonSpaces** |Samsvarer med ingen, ett eller flere tegn som ikke legger til mellomrom. |`\S*` |
| **OptionalSpaces** |Samsvarer med ingen, ett eller flere tegn som legger til mellomrom. |`\s*` |
| **Period** |Samsvarer med et punktum eller en prikk (.). |`\.` |
| **RightParen** |Samsvarer med en høyreparentes «)». |`\)` |
| **Space** |Samsvarer med et tegn som legger til mellomrom. |`\s` |

For eksempel samsvarer mønsteret **A & MultipleDigits** med bokstaven A etterfulgt av ett eller flere sifre.  

### <a name="regular-expressions"></a>Vanlige uttrykk
Mønsteret som bruker disse funksjonene er en [RegEx](https://en.wikipedia.org/wiki/Regular_expression). Vanlige tegn og forhåndsdefinerte mønstre som er beskrevet tidligere i dette emnet bidrar til å bygge vanlige uttrykk.  

Vanlige uttrykk er svært kraftige, er tilgjengelig i mange programmeringsspråk og brukes til en rekke ulike formål. De kan også ofte ser ut som en tilfeldig sekvens med skilletegn. Denne artikkelen beskrive ikke alle aspektene ved vanlige uttrykk, men en overflod av informasjon, opplæringer, og verktøy som er tilgjengelige på nettet.  

Vanlige uttrykk leveres i forskjellige dialekter, og PowerApps bruker en variant av JavaScript-dialekten. Se [vanlige uttrykk syntaksen](http://msdn.microsoft.com/library/1400241x.aspx) for en innføring i syntaksen. Navngitt deloverensstemmelser (også kalt navngitte opphentingsforekomsten grupper) støttes:

- Med navnet deloverensstemmelser: **(?&lt; *navnet* &gt; ...)**
- Med navnet backreferences:  **\\k&lt;*navn*&gt;**

I den **Match** enum tabellen tidligere i dette emnet, hver enum vises i den samme raden som den tilsvarende RegEx.

## <a name="match-options"></a>Samsvarsalternativer
Du kan endre virkemåten til disse funksjonene ved å angi én eller flere alternativer, som du kan kombinere ved hjelp av Strengsammensetning operatoren (**&amp;**).  

| MatchOptions-Enumerator | Beskrivelse | Innvirkning på et vanlig uttrykk |
| --- | --- | --- |
| **BeginsWith** |Mønsteret må samsvare med begynnelsen av teksten. |Legger til en **^** foran det vanlige uttrykket. |
| **Complete** |Standard for **IsMatch**. Mønsteret må samsvare med hele tekststrengen, fra begynnelse til slutt. |Legger til en **^** foran og en **$** til slutten av det vanlige uttrykket. |
| **Contains** |Standard for **Match** og **MatchAll**. Mønsteret må vises et sted i teksten, men det trenger ikke å være på starten eller slutten. |Endrer ikke det vanlige uttrykket. |
| **EndsWith** |Mønsteret må samsvare med slutten av strengen med tekst. |Legger til en **$** på slutten av det vanlige uttrykket. |
| **IgnoreCase** |Behandler store og små bokstaver som identiske. Som standard skiller samsvar mellom små og store bokstaver. |Endrer ikke det vanlige uttrykket. Dette alternativet tilsvarer standard "i" modifikatoren for vanlige uttrykk.  |
| **Multiline** |Samsvar på tvers av flere linjer. |Endrer ikke det vanlige uttrykket. Dette alternativet tilsvarer standard «m»-modifikator for vanlige uttrykk. |

Ved hjelp av **MatchAll** tilsvarer bruk av standard «g» modifikatoren for vanlige uttrykk.

## <a name="syntax"></a>Syntaks
**IsMatch**( *Text*, *Pattern* [, *Options* ] )

* *Text* – obligatorisk. Tekststrengen som skal testes.
* *Pattern* – obligatorisk. Mønsteret som skal testes som en tekststreng. Kjed sammen forhåndsdefinerte mønstre som den **Match** enumeratoren definerer, eller angi et vanlig uttrykk. *Mønsteret* må være en konstant formel uten variabler, datakilder eller andre dynamisk refererer til denne endringen som app-kjøringer.
* *Options* – valgfritt. En tekststreng kombinasjon av **MatchOptions** opplistingsverdier. Som standard brukes **MatchOptions.Complete**.

**Match**( *tekst*, *mønsteret* [, *alternativer* ])

* *Text* – obligatorisk. Tekststrengen som samsvarer med.
* *Pattern* – obligatorisk. Mønsteret som skal samsvare med som en tekststreng. Kjed sammen forhåndsdefinerte mønstre som den **Match** enumeratoren definerer, eller angi et vanlig uttrykk. *Mønsteret* må være en konstant formel uten variabler, datakilder eller andre dynamisk refererer til denne endringen som app-kjøringer.
* *Options* – valgfritt. En tekststreng kombinasjon av **MatchOptions** opplistingsverdier. Som standard **MatchOptions.Contains** brukes.

**MatchAll**( *tekst*, *mønsteret* [, *alternativer* ])

* *Text* – obligatorisk. Tekststrengen som samsvarer med.
* *Pattern* – obligatorisk. Mønsteret som skal samsvare med som en tekststreng. Kjed sammen forhåndsdefinerte mønstre som den **Match** enumeratoren definerer, eller angi et vanlig uttrykk. *Mønsteret* må være en konstant formel uten variabler, datakilder eller andre dynamisk refererer til denne endringen som app-kjøringer.
* *Options* – valgfritt. En tekststreng kombinasjon av **MatchOptions** opplistingsverdier. Som standard **MatchOptions.Contains** brukes.

## <a name="ismatch-examples"></a>IsMatch-eksempler
### <a name="ordinary-characters"></a>Vanlige tegn
Tenk deg at appen inneholder en kontroll for **tekstinndata** med navnet **TextInput1**. Brukeren skriver inn verdier i denne kontrollen som skal lagres i en database.   

Brukeren skriver inn **Hei, verden** i **TextInput1**.

| Formel | Beskrivelse | Resultat |
| --- | --- | --- |
| `IsMatch( TextInput1.Text, "Hello world" )` |Tester om brukerens inndata samsvarer nøyaktig med strengen «Hello world». |**sann** |
| `IsMatch( TextInput1.Text, "Good bye" )` |Tester om brukerens inndata samsvarer nøyaktig med strengen «Farvel». |**usann** |
| `IsMatch( TextInput1.Text, "hello", Contains )` |Tester om brukerens inndata inneholder ordet «Hei» (bokstaver). |**usann** |
| `IsMatch( TextInput1.Text, "hello", Contains & IgnoreCase )` |Tester om brukerens inndata inneholder ordet «hei» (skiller ikke mellom store og små bokstaver). |**sann** |

### <a name="predefined-patterns"></a>Forhåndsdefinerte mønstre

|                                                            Formel                                                            |                                                                Beskrivelse                                                                |  Resultat   |
|-------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------|-----------|
| `IsMatch( "123-45-7890", Digit & Digit & Digit & Hyphen & Digit & Digit & Hyphen & Digit & Digit & Digit & Digit )` |                                              Samsvarer med et personnummer for USA                                               | **sann**  |
|                                           `IsMatch( "joan@contoso.com", Email )`                                            |                                                         Samsvarer med en e-postadresse                                                          | **sann**  |
|                              `IsMatch( "123.456", MultipleDigits & Period & OptionalDigits )`                               |                                   Samsvarer med en rekke sifre, et punktum og deretter ingen eller flere sifre.                                   | **sann**  |
|                                `IsMatch( "123", MultipleDigits & Period & OptionalDigits )`                                 | Samsvarer med en rekke sifre, et punktum og deretter ingen eller flere sifre. Et punktum vises ikke i teksten som samsvarer med, så dette mønsteret ikke samsvarer. | **usann** |

### <a name="regular-expressions"></a>Vanlige uttrykk

|                                                                              Formel                                                                              |                                                                                                                                  Beskrivelse                                                                                                                                   |  Resultat   |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|
|                                                                    `IsMatch( "986", "\d+" )`                                                                   |                                                                                                                    Samsvarer med et heltall større enn null.                                                                                                                     | **sann**  |
|                                                               `IsMatch( "1.02", "\d+(\.\d\d)?" )`                                                              |                                        Samsvarer med et positivt valutabeløp. Hvis inndataene inneholder et desimaltegn, må inndataene også inneholde to numeriske tegn etter desimaltegnet. For eksempel er 3.00 gyldig, men ikke 3.1.                                         | **sann**  |
|                                                            `IsMatch( "-4.95", "(-)?\d+(\.\d\d)?" )`                                                             |                                                        Samsvarer med et positivt eller negativt valutabeløp. Hvis inndataene inneholder et desimaltegn, må inndataene også inneholde to numeriske tegn etter desimaltegnet.                                                        | **sann**  |
|                                                         `IsMatch( "111-11-1111", "\d{3}-\d{2}-\d{4}" )`                                                        | Samsvarer med et personnummer for USA. Validerer format, type og lengde for det angitte inndatafeltet. Strengen som skal samsvare må bestå av tre numeriske tegn etterfulgt av en bindestrek og deretter to numeriske tegn etterfulgt av en bindestrek, og deretter fire numeriske tegn. | **sann**  |
|                                                         `IsMatch( "111-111-111", "\d{3}-\d{2}-\d{4}" )`                                                         |                                                                                               Samme som det forrige eksemplet, men en av bindestrekene er på feil sted i inndataene.                                                                                               | **usann** |
|                                         `IsMatch( "AStrongPasswordNot", "(?!^[0-9]\*$)(?!^[a-zA-Z]\*$)([a-zA-Z0-9]{8,10})" )`                                        |                                        Validerer et sterkt passord, som må inneholde 8, 9 eller 10 tegn, i tillegg til minst ett siffer og minst én bokstav. Strengen kan ikke inneholde spesialtegn.                                        | **usann** |
| `IsMatch( "<http://microsoft.com>", "(ht&#124;f)tp(s?)\:\/\/\[0-9a-zA-Z\]([-.\w]\*[0-9a-zA-Z])\*(:(0-9)\*)\*(\/?)([a-zA-Z0-9\-\.\?\,\'\/\\\+&%\$#_]\*)?" )` |                                                                                                                     Validerer en nettadresse for HTTP, HTTPS eller FTP.                                                                                                                      | **sann**  |

## <a name="match-and-matchall-examples"></a>Match og MatchAll eksempler

| Formel | Beskrivelse | Resultat |
|--------|------------|-----------|
| `Match( "Bob Jones <bob.jones@contoso.com>", "<(?<email>" & Match.Email & ")>"` | Trekker ut bare e-delen av kontaktinformasjonen.  | {<br>e-post:&nbsp;"bob.jones@contoso.com",<br>FullMatch:&nbsp;"&lt;bob.jones@contoso.com>",<br>SubMatches:&nbsp;[&nbsp;"bob.jones@contoso.com"&nbsp;],<br>StartMatch: 11<br>}  
| `Match( "Bob Jones <InvalidEmailAddress>", "<(?<email>" & Match.Email & ")>"` | Trekker ut bare e-delen av kontaktinformasjonen. Finner ingen juridiske adressen (det er ikke @-tegnet), slik at funksjonen returnerer *tom*. | *tom* |  
| `Match( Language(), "(<language>\w{2})(?:-(?<script>\w{4}))?(?:-(?<region>\w{2}))?" )` | Trekker ut de språk, skriptet og området delene av språket merke som den **[språk](function-language.md)** -funksjonen returnerer. Disse resultatene gjenspeiler USA. Se den [ **språk** funksjonen dokumentasjonen](function-language.md) flere eksempler.  Den **(?:** operatoren grupperer tegn uten å opprette en annen delrapport treff. | {<br>språk: "no",<br>skriptet: *tom*, <br>Område: «OSS»<br>FullMatch: "en-US", <br>SubMatches: ["no", "", "US"], <br>StartMatch: 1<br>} 
| `Match( "PT2H1M39S", "PT(?:(<hours>\d+)H)?(?:(?<minutes>\d+)M)?(?:(?<seconds>\d+)S)?" )` | Trekker ut den timer, minutter og sekunder fra en ISO 8601-varighetsverdi. Uttrukket tallene er fremdeles i en tekststreng; Bruk den [ **verdien** ](function-value.md) funksjonen til å konvertere den til et tall før matematiske operasjoner utføres på den.  | {<br> timer: "2",<br>minutter: "1",<br>sekunder: "39",<br>FullMatch: "PT2H1M39S",<br>SubMatches:&nbsp;[&nbsp;"2",&nbsp;"1",&nbsp;"39"&nbsp;],<br>StartMatch: 1<br>} |

La oss drille ned i det siste eksemplet. Hvis du vil konvertere denne strengen til en dato/klokkeslett-verdi ved hjelp av den **[tid](function-date-time.md)** -funksjonen, du må sende i de navngitte deloverensstemmelser enkeltvis. Hvis du vil gjøre dette, kan du bruke den **[ForAll](function-forall.md)** funksjonen er i drift på først registrere at **MatchAll** returnerer:

``` powerapps-dot
First( 
    ForAll( 
        MatchAll( "PT2H1M39S", "PT(?:(?<hours>\d+)H)?(?:(?<minutes>\d+)M)?(?:(?<seconds>\d+)S)?" ), 
        Time( Value( hours ), Value( minutes ), Value( seconds ) )
    )
).Value
```

For disse eksemplene, legge til en [knappen](../controls/control-button.md) kontroll, angi dens **OnSelect** egenskapen til denne formelen, og velg deretter knappen:

``` powerapps-dot
Set( pangram, "The quick brown fox jumps over the lazy dog." )
```
 
| Formel | Beskrivelse | Resultat |
|---------|-------------|--------|
| `Match( pangram, "THE", IgnoreCase )` | Søk etter alle forekomster av "Av" i teksten streng som den **pangram** variabel inneholder. Strengen inneholder to treff, men bare første returneres fordi du bruker **Match** og ikke **MatchAll**. Kolonnen SubMatches er tomt fordi ingen deloverensstemmelser ble definert.  | {<br>FullMatch: "Den"<br>SubMatches: [&nbsp;],<br>StartMatch: 32<br>} |
| `MatchAll( pangram, "the" )` | Søk etter alle forekomster av "the" i tekststrengen som den **pangram** variabel inneholder. Testen er bokstaver, slik at bare den andre forekomsten av "the" blir funnet. Kolonnen SubMatches er tomt fordi ingen deloverensstemmelser ble definert.  | <style> img { max-width: none } </style> ![](media/function-ismatch/pangram-the-one.png) |
| `MatchAll( pangram, "the", IgnoreCase )` | Søk etter alle forekomster av "the" i tekststrengen som den **pangram** variabel inneholder. I dette tilfellet er testen bokstaver, slik at begge forekomstene av ordet blir funnet. Kolonnen SubMatches er tomt fordi ingen deloverensstemmelser ble definert.  | <style> img { max-width: none } </style> ![](media/function-ismatch/pangram-the-two.png) |
| `MatchAll( pangram, "\b\wo\w\b" )` | Søker etter alle tre bokstaver ord med en «o» i midten. Vær oppmerksom på at «brune» er utelatt fordi den er ikke et tre bokstaver ord, og derfor ikke kan samsvarer med "\b» (grenselinje for ord).  | <style> img { max-width: none } </style> ![](media/function-ismatch/pangram-fox-dog.png) |
| `Match( pangram, "\b\wo\w\b\s\*(?<between>\w.+\w)\s\*\b\wo\w\b" )` | Samsvarer med alle tegn mellom «fox» og "eple". | {<br>mellom:&nbsp;"hopper&nbsp;over&nbsp;den&nbsp;sakte",<br>FullMatch:&nbsp;"fox&nbsp;hopper&nbsp;over&nbsp;den&nbsp;sakte&nbsp;hund",<br>SubMatches: ["hopper over den sakte"],<br>StartMatch: 17<br> } |

Å se resultatene av **MatchAll** i et galleri:

1. Sett inn en tom loddrett i en tom skjerm, **[galleriet](../controls/control-gallery.md)** kontroll.

2. Angi galleriets **elementer** egenskapen til **MatchAll (pangram, «\w+»)** eller **MatchAll (pangram, MultipleLetters)**.

    ![](media/function-ismatch/pangram-gallery1.png)

3. Velg "Legg til et element fra kategorien Sett inn «midt i galleri-kontrollen til å velge malen i galleriet. 

5. Legg til en **[etikett](../controls/control-text-box.md)** kontrollen til malen i galleriet.  

4. Angi etikettens **tekst** egenskapen til **ThisItem.FullMatch**.  
 
    Galleriet fylles med hvert ord i vårt eksempeltekst.  Endre størrelsen på malen i galleriet og etikettkontrollen for å kunne se alle ordene på ett skjermbilde.

    ![](media/function-ismatch/pangram-gallery2.png)
