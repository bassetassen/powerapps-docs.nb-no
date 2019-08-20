---
title: Funksjonene IsMatch, match og MatchAll | Microsoft Docs
description: Referanse informasjon, inkludert syntaks, for funksjonene IsMatch, match og MatchAll i PowerApps
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 08/15/2019
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: b9496964b2a11195d3adb561817fec0f9bf11f47
ms.sourcegitcommit: 9163abbe9a24298f216f15139f977adfd2c3f2ae
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/16/2019
ms.locfileid: "69546002"
ms.PowerAppsDecimalTransform: true
---
# <a name="ismatch-match-and-matchall-functions-in-powerapps"></a>IsMatch-, match-og MatchAll-funksjoner i PowerApps
Tester om et treff eller trekker ut deler av en tekst streng basert på et mønster.

## <a name="description"></a>Beskrivelse
**IsMatch**-funksjonen tester om en tekststreng samsvarer med et mønster, som kan omfatte vanlige tegn, forhåndsdefinerte mønstre eller et [vanlig uttrykk](#regular-expressions).  **Treff** -og **MatchAll** -funksjonene returnerer det som ble samsvart, inkludert del treff.  

Bruk **IsMatch** til å validere det en bruker har skrevet inn i en **[tekstinndata](../controls/control-text-input.md)** -kontroll. Du kan for eksempel kontrollere om brukeren har angitt en gyldig e-postadresse før resultatet lagres i datakilden. Hvis oppføringen ikke samsvarer med vilkårene dine, kan du legge til andre kontroller som ber brukeren om å rette oppføringen.

Bruk **match** til å trekke ut den første tekst strengen som Sams varer med et mønster og **MatchAll** , for å trekke ut alle tekst strenger som Sams varer. Du kan også trekke ut under samsvar for å analysere kompliserte strenger.   

**Match** returnerer en oppføring med informasjon for det første treffet som ble funnet, og **MatchAll** returnerer en tabell med poster for hvert treff. Posten eller postene inneholder:

| Kolonne | Type | Beskrivelse |
|----|----|----|
| *navngitte&#8209;underordnede treff eller&#8209;under treff* | Text | Hver navngitte under treff får sin egen kolonne. Vil du opprette et navngitt under treff ved hjelp av **(?&lt; *navn* &gt;** ... **)** i det regulære uttrykket. Hvis et navngitt under treff har samme navn som en av de forhånds definerte Kol onnene (nedenfor), har del treff prioriteten, og det genereres en advarsel. Du unngår denne advarselen ved å gi nytt navn til under samsvaret. |
| **FullMatch** | Text | Alle tekst strengene som ble samsvart. |
| **StartMatch** | Tall | Start posisjonen for treffet i inn data strengen. Det første tegnet i strengen returnerer 1. | 
| **Under treff** | Tabell med én kolonne med tekst (Kol onne **verdi**) | Tabellen med navngitte og underordnede del treff i rekkefølgen de vises i det vanlige uttrykket. Det er vanligvis enklere å arbeide med navngitte under treff, og de oppfordres til. Bruk [**ForAll**](function-forall.md) -funksjonen eller [**Last**](function-first-last.md)inn ( [**FirstN**](function-first-last.md)( **...** ))-funksjonene til å arbeide med en individuell under treff. Hvis ingen underordnede treff er definert i det regulære uttrykket, vises denne tabellen, men er tom. |

Disse funksjonene støtter [**MatchOptions**](#match-options). Som standard: 
- Disse funksjonene utfører et treff som skiller mellom store og små bokstaver. Bruk **IgnoreCase** til å utføre treff som skiller mellom store og små bokstaver.    
- **IsMatch** Sams varer med hele tekst strengen (**fullstendig** MatchOption), mens **de Sams varer** og **MatchAll** søker etter et treff hvor som helst i tekst strengen (**inneholder** MatchOption). Bruk **fullstendig**, **inneholder**, **BeginsWith**eller **EndsWith** , avhengig av ditt scenario.

**IsMatch** returnerer *sann* hvis tekststrengen samsvarer med mønsteret eller *usann* hvis den ikke gjør det. **Match** returnerer *tom* hvis det ikke blir funnet noen treff som kan testes med [**IsBlank**](function-isblank-isempty.md) -funksjonen. **MatchAll** returnerer en tom tabell hvis det ikke blir funnet noen treff som kan testes med [**IsEmpty**](function-isblank-isempty.md) -funksjonen.

Hvis du bruker **MatchAll** til å dele en tekst streng, bør du vurdere å bruke **[Split](function-split.md)** -funksjonen, som er enklere å bruke og raskere.

## <a name="patterns"></a>Mønstre
Nøkkelen til å bruke disse funksjonene er i henhold til å beskrive mønsteret slik at den Sams varer. Du beskriver mønsteret i en tekststreng som en kombinasjon av:

* Vanlige tegn, for eksempel **abc** eller **123**.
* Forhåndsdefinerte mønstre, for eksempel **Letter**, **MultipleDigits** eller **Email**. (**Match**-enumeratoren definerer disse mønstrene.)
* Koder for vanlige uttrykk, for eksempel **"\d + \s + \d +"** eller **"[a-z] +"** .

Kombiner disse elementene ved hjelp av [operatoren **&** for streng sammenkobling ](operators.md). For eksempel: **abc & Digit & \s+** er et gyldig mønster som samsvarer med tegnene a, b og c, etterfulgt av et tall mellom 0 og 9, etterfulgt av minst ett mellomromstegn.

### <a name="ordinary-characters"></a>Vanlige tegn
Det enkleste mønsteret er en rekke vanlige tegn som skal samsvare nøyaktig.

For eksempel, når den brukes med **IsMatch** -funksjonen, Sams varer strengen "Hello" nøyaktig til mønsteret **"Hello"** . Ikke mer eller mindre. Strengen «hei!» Sams varer ikke med mønsteret på grunn av utrops tegnet på slutten, og fordi dekslet er feil for bokstaven h. (Se [MatchOptions](#match-options) for hvordan du kan endre denne virkemåten.)

Bestemte tegn er reservert for spesielle formål i mønsterspråket. Hvis du vil bruke disse tegnene, kan du enten forhånds vise tegnet med en **\\** (omvendt skrå strek) for å angi at tegnet skal brukes bokstavelig talt, eller bruke ett av de forhåndsinnstilte mønstrene som er beskrevet senere i dette emnet. Denne tabellen viser spesialtegnene:

| Spesialtegn | Beskrivelse |
| --- | --- |
| **.** |prikk eller punktum |
| **?** |spørsmålstegn |
| **&#42;** |stjerne |
| **\+** |pluss |
| **( )** |mellomrom |
| **[ ]** |hakeparenteser |
| **{ }** |klammeparenteser |
| **^** |cirkumflekstegn |
| **$** |dollartegn |
| **\|** |loddrett strek |
| **\\** |omvendt skråstrek |

Du kan for eksempel samsvare «Hei?» ved hjelp av mønsteret **Hei\\?** med en omvendt skråstrek foran spørsmålstegnet.

### <a name="predefined-patterns"></a>Forhåndsdefinerte mønstre
Forhånds definerte mønstre gir en enkel metode for å finne ett av et sett med tegn eller en sekvens med flere tegn. Bruk [operatoren **&** for streng sammenkobling](operators.md) til å kombinere dine egne tekst strenger med medlemmer av den **samsvarende** opplistingen:

| Samsvarende opplisting | Beskrivelse | Vanlig uttrykk |
| --- | --- | --- |
| **Any** |Samsvarer med et hvilket som helst tegn. |`.` |
| **Comma** |Samsvarer med et komma. |`;` |
| **Digit** |Samsvarer med ett enkelt siffer (fra 0 til 9). |`\d` |
| **Email** |Samsvarer med en e-postadresse som inneholder en krøllalfa (\@) og et domenenavn som inneholder et punktum (.) |`.+\@.+\\.[^\\.]{2;}` |
| **Hyphen** |Samsvarer med en bindestrek. |`\-` |
| **LeftParen** |Samsvarer med en venstreparentes «(». |`\(` |
| **Letter** |Samsvarer med en bokstav. |`\p{L}` |
| **MultipleDigits** |Sams varer med ett eller flere sifre. |`\d+` |
| **MultipleLetters** |Samsvarer med én eller flere bokstaver. |`\p{L}+` |
| **MultipleNonSpaces** |Sams varer med ett eller flere tegn som ikke legger til mellomrom, TAB eller ny linje. |`\S+` |
| **MultipleSpaces** |Sams varer med ett eller flere tegn som legger til mellomrom (mellomrom, TAB eller ny linje). |`\s+` |
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
Mønsteret som disse funksjonene bruker, er et [vanlig uttrykk](https://en.wikipedia.org/wiki/Regular_expression). De vanlige tegnene og forhånds definerte mønstre som er beskrevet tidligere i dette emnet, bidrar til å bygge vanlige uttrykk.  

Vanlige uttrykk er svært kraftige, er tilgjengelig i mange programmeringsspråk og brukes til en rekke ulike formål. De kan også se ofte ut som en tilfeldig rekkefølge av skille tegn. Denne artikkelen beskriver ikke alle aspekter ved vanlige uttrykk, men en rekke informasjon, opplæringer og verktøy er tilgjengelige på nettet.  

Vanlige uttrykk leveres i forskjellige dialekter, og PowerApps bruker en variant av JavaScript-dialekten. Se [syn tak sen for vanlig uttrykk](https://msdn.microsoft.com/library/1400241x.aspx) for å få en innføring i syn tak sen. Navngitte del treff (noen ganger kalt kalt opptaks grupper) støttes:

- Navngitte del treff: **(?&lt; *navn* &gt; ...)**
- Navngitte bak referanser:  **\\n&lt;-*navn*&gt;**

I den **samsvarende** opplistings tabellen tidligere i dette emnet vises hver opplisting i samme rad som det tilsvarende vanlige uttrykket.

## <a name="match-options"></a>Samsvarsalternativer
Du kan endre virke måten til disse funksjonene ved å angi ett eller flere alternativer, som du kan kombinere ved hjelp av operatoren for streng sammenkobling **&amp;** ().  

| MatchOptions-opplisting | Beskrivelse | Innvirkning på et regulært uttrykk |
| --- | --- | --- |
| **BeginsWith** |Mønsteret må samsvare med begynnelsen av teksten. |Legger til en **^** foran det vanlige uttrykket. |
| **Complete** |Standard for **IsMatch**. Mønsteret må samsvare med hele tekst strengen, fra begynnelse til slutt. |Legger til **^** en start og et **$** på slutten av det regulære uttrykket. |
| **Contains** |Standard for **match** -og **MatchAll**. Mønsteret må vises et sted i teksten, men det trenger ikke å være på starten eller slutten. |Endrer ikke det vanlige uttrykket. |
| **EndsWith** |Mønsteret må samsvare med slutten av tekst strengen. |Legger til en **$** på slutten av det vanlige uttrykket. |
| **IgnoreCase** |Behandler store og små bokstaver som identiske. Som standard skiller samsvar mellom små og store bokstaver. |Endrer ikke det vanlige uttrykket. Dette alternativet tilsvarer standard «i»-modifikator for vanlige uttrykk.  |
| **Multiline** |Samsvar på tvers av flere linjer. |Endrer ikke det vanlige uttrykket. Dette alternativet tilsvarer standard m-modifikatoren for vanlige uttrykk. |

Bruk av **MatchAll** er det samme som å bruke standard "g"-modifikator for vanlige uttrykk.

## <a name="syntax"></a>Syntaks
**IsMatch**( *Text*; *Pattern* [; *Options* ] )

* *Text* – obligatorisk. Tekststrengen som skal testes.
* *Pattern* – obligatorisk. Mønsteret som skal testes som en tekst streng. Slå sammen forhånds definerte mønstre som **Sams varer med** opplistingen definerer, eller angi et vanlig uttrykk. *Mønsteret* må være en konstant formel uten variabler, data kilder eller andre dynamiske referanser som endres når appen kjøres.
* *Options* – valgfritt. En tekst streng kombinasjon av **MatchOptions** -opplistings verdier. Som standard brukes **MatchOptions.Complete**.

**Treff** ( *Tekst*, *mønster* [, *Alternativer* ])

* *Text* – obligatorisk. Tekst strengen som skal samsvare.
* *Pattern* – obligatorisk. Mønsteret som Sams varer med en tekst streng. Slå sammen forhånds definerte mønstre som **Sams varer med** opplistingen definerer, eller angi et vanlig uttrykk. *Mønsteret* må være en konstant formel uten variabler, data kilder eller andre dynamiske referanser som endres når appen kjøres.
* *Options* – valgfritt. En tekst streng kombinasjon av **MatchOptions** -opplistings verdier. Som standard brukes **MatchOptions. contains** .

**MatchAll** ( *Tekst*, *mønster* [, *Alternativer* ])

* *Text* – obligatorisk. Tekst strengen som skal samsvare.
* *Pattern* – obligatorisk. Mønsteret som Sams varer med en tekst streng. Slå sammen forhånds definerte mønstre som **Sams varer med** opplistingen definerer, eller angi et vanlig uttrykk. *Mønsteret* må være en konstant formel uten variabler, data kilder eller andre dynamiske referanser som endres når appen kjøres.
* *Options* – valgfritt. En tekst streng kombinasjon av **MatchOptions** -opplistings verdier. Som standard brukes **MatchOptions. contains** .

## <a name="ismatch-examples"></a>IsMatch-eksempler
### <a name="ordinary-characters"></a>Vanlige tegn
Tenk deg at appen inneholder en kontroll for **tekstinndata** med navnet **TextInput1**. Brukeren skriver inn verdier i denne kontrollen som skal lagres i en database.   

Brukeren skriver inn **Hei, verden** i **TextInput1**.

| Formel | Beskrivelse | Resultat |
| --- | --- | --- |
| `IsMatch( TextInput1.Text; "Hello world" )` |Tester om brukerens inn data Sams varer nøyaktig med strengen "Hello World". |**sann** |
| `IsMatch( TextInput1.Text; "Good bye" )` |Tester om brukerens inn data Sams varer nøyaktig med strengen "Good bye". |**usann** |
| `IsMatch( TextInput1.Text; "hello"; Contains )` |Tester om brukerens inn data inneholder ordet «Hello» (skiller mellom store og små bokstaver). |**usann** |
| `IsMatch( TextInput1.Text; "hello"; Contains & IgnoreCase )` |Tester om brukerens inndata inneholder ordet «hei» (skiller ikke mellom store og små bokstaver). |**sann** |

### <a name="predefined-patterns"></a>Forhåndsdefinerte mønstre

|                                                            Formel                                                            |                                                                Beskrivelse                                                                |  Resultat   |
|-------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------|-----------|
| `IsMatch( "123-45-7890"; Digit & Digit & Digit & Hyphen & Digit & Digit & Hyphen & Digit & Digit & Digit & Digit )` |                                              Samsvarer med et personnummer for USA                                               | **sann**  |
|                                           `IsMatch( "joan@contoso.com"; Email )`                                            |                                                         Samsvarer med en e-postadresse                                                          | **sann**  |
|                              `IsMatch( "123.456"; MultipleDigits & Period & OptionalDigits )`                               |                                   Samsvarer med en rekke sifre, et punktum og deretter ingen eller flere sifre.                                   | **sann**  |
|                                `IsMatch( "123"; MultipleDigits & Period & OptionalDigits )`                                 | Samsvarer med en rekke sifre, et punktum og deretter ingen eller flere sifre. En periode vises ikke i teksten som Sams varer, så dette mønsteret Sams varer ikke. | **usann** |

### <a name="regular-expressions"></a>Vanlige uttrykk

|                                                                              Formel                                                                              |                                                                                                                                  Beskrivelse                                                                                                                                   |  Resultat   |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|
|                                                                    `IsMatch( "986"; "\d+" )`                                                                   |                                                                                                                    Sams varer med et hel tall større enn null.                                                                                                                     | **sann**  |
|                                                               `IsMatch( "1.02"; "\d+(\.\d\d)?" )`                                                              |                                        Samsvarer med et positivt valutabeløp. Hvis inn dataene inneholder et desimal tegn, må inn dataene også inneholde to sifre etter desimalt egnet. For eksempel er 3.00 gyldig, men ikke 3.1.                                         | **sann**  |
|                                                            `IsMatch( "-4.95"; "(-)?\d+(\.\d\d)?" )`                                                             |                                                        Samsvarer med et positivt eller negativt valutabeløp. Hvis inn dataene inneholder et desimal tegn, må inn dataene også inneholde to sifre etter desimalt egnet.                                                        | **sann**  |
|                                                         `IsMatch( "111-11-1111"; "\d{3}-\d{2}-\d{4}" )`                                                        | Samsvarer med et personnummer for USA. Validerer format, type og lengde for det angitte inndatafeltet. Strengen som skal samsvare, må bestå av tre numeriske tegn etterfulgt av en binde strek, deretter to numeriske tegn etterfulgt av en tanke strek og deretter fire numeriske tegn. | **sann**  |
|                                                         `IsMatch( "111-111-111"; "\d{3}-\d{2}-\d{4}" )`                                                         |                                                                                               Samme som det forrige eksemplet, men en av bindestrekene er på feil sted i inndataene.                                                                                               | **usann** |
|                                         `IsMatch( "AStrongPasswordNot"; "(?!^[0-9]\*$)(?!^[a-zA-Z]\*$)([a-zA-Z0-9]{8,10})" )`                                        |                                        Validerer et sterkt passord, som må inneholde åtte, ni eller 10 tegn, i tillegg til minst ett siffer og minst ett alfabetisk tegn. Strengen kan ikke inneholde spesialtegn.                                        | **usann** |
| `IsMatch( "<http://microsoft.com>"; "(ht&#124;f)tp(s?)\:\/\/\[0-9a-zA-Z\]([-.\w]\*[0-9a-zA-Z])\*(:(0-9)\*)\*(\/?)([a-zA-Z0-9\-\.\?\,\'\/\\\+&%\$#_]\*)?" )` |                                                                                                                     Validerer en nettadresse for HTTP, HTTPS eller FTP.                                                                                                                      | **sann**  |

## <a name="match-and-matchall-examples"></a>Treff-og MatchAll-eksempler

| Formel | Beskrivelse | Resultat |
|--------|------------|-----------|
| `Match( "Bob Jones <bob.jones@contoso.com>"; "<(?<email>" & Match.Email & ")>"` | Trekker ut bare e-postdelen av kontakt informasjonen.  | {<br>e-&nbsp;postbob.jones@contoso.com: "",<br>FullMatch:&nbsp;"&lt;>",bob.jones@contoso.com<br>Under treff:&nbsp;[&nbsp;"bob.jones@contoso.com"&nbsp;],<br>StartMatch: opptil<br>}  
| `Match( "Bob Jones <InvalidEmailAddress>"; "<(?<email>" & Match.Email & ")>"` | Trekker ut bare e-postdelen av kontakt informasjonen. Finner ingen juridisk adresse (det finnes ikke noe @ tegn), så funksjonen returnerer *tom*. | *tom* |  
| `Match( Language(); "(<language>\w{2})(?:-(?<script>\w{4}))?(?:-(?<region>\w{2}))?" )` | Trekker ut deler av språk, skript og område i språk koden som **[språk](function-language.md)** -funksjonen returnerer. Disse resultatene gjenspeiler USA. se dokumentasjonen for [ **språk** funksjoner](function-language.md) for flere eksempler.  **(?:-** Operatorene grupperer uten å opprette et nytt under treff. | {<br>språk: "en",<br>skript: *tomt*, <br>/regionkode «USA»,<br>FullMatch: "en-US", <br>Under treff: ["en", "", "US"], <br>StartMatch: 1<br>} 
| `Match( "PT2H1M39S"; "PT(?:<hours>\d+)H)?(?:(?<minutes>\d+)M)?(?:(?<seconds>\d+)S)?" )` | Trekker ut timer, minutter og sekunder fra en ISO 8601 Duration-verdi. De uttrukne tallene er fremdeles i en tekst streng. Bruk [**Value**](function-value.md) -funksjonen til å konvertere den til et tall før matematiske operasjoner utføres på den.  | {<br> langt "2",<br>antall "1",<br>mellomrom "39",<br>FullMatch: "PT2H1M39S",<br>Under&nbsp;treff:&nbsp;[&nbsp;"2",&nbsp;"1",&nbsp;"39"],<br>StartMatch: 1<br>} |

La oss gå til det siste eksemplet. Hvis du vil konvertere denne strengen til en dato/klokkeslett-verdi ved hjelp av **[time](function-date-time.md)** -funksjonen, må du sende inn de navngitte del treffene enkeltvis. Hvis du vil gjøre dette, kan du **[](function-with.md)** bruke funksjons bruken i oppføringen som **Sams varer med** retur:

``` powerapps-comma
With( 
    Match( "PT2H1M39S"; "PT(?:(?<hours>\d+)H)?(?:(?<minutes>\d+)M)?(?:(?<seconds>\d+)S)?" ); 
    Time( Value( hours ); Value( minutes ); Value( seconds ) )
)
```

Legg til en [knapp](../controls/control-button.md) -kontroll i disse eksemplene, angi **OnSelect** -egenskapen til denne formelen, og velg deretter knappen:

``` powerapps-comma
Set( pangram; "The quick brown fox jumps over the lazy dog." )
```
 
| Formel | Beskrivelse | Resultat |
|---------|-------------|--------|
| `Match( pangram; "THE"; IgnoreCase )` | Finn alle treff for «THE» i tekst strengen som **Pangram** -variabelen inneholder. Strengen inneholder to treff, men bare den første returneres fordi du bruker **match** og not **MatchAll**. Under Sams varer med kolonne er tom fordi ingen under samsvar ble definert.  | {<br>FullMatch: «The»,<br>Under treff: [&nbsp;],<br>StartMatch: 32<br>} |
| `MatchAll( pangram; "the" )` | Finn alle treff for «The» i tekst strengen som **Pangram** -variabelen inneholder. Testen skiller mellom store og små bokstaver, så bare den andre forekomsten av «den ble funnet. Under Sams varer med kolonne er tom fordi ingen under samsvar ble definert.  | <style> img { max-width: none } </style> ![](media/function-ismatch/pangram-the-one.png) |
| `MatchAll( pangram; "the"; IgnoreCase )` | Finn alle treff for «The» i tekst strengen som **Pangram** -variabelen inneholder. I dette tilfellet skiller testen seg mellom store og små bokstaver, slik at begge forekomster av ordet blir funnet. Under Sams varer med kolonne er tom fordi ingen under samsvar ble definert.  | <style> img { max-width: none } </style> ![](media/function-ismatch/pangram-the-two.png) |
| `MatchAll( pangram; "\b\wo\w\b" )` | Finner alle ord med tre bokstaver med en «o» i midten. Vær oppmerksom på at "brun" er utelukket fordi det ikke er et ord med tre bokstaver, og derfor ikke ikke Sams varer med «\b» (ord grense).  | <style> img { max-width: none } </style> ![](media/function-ismatch/pangram-fox-dog.png) |
| `Match( pangram; "\b\wo\w\b\s\*(?<between>\w.+\w)\s\*\b\wo\w\b" )` | Sams varer med alle tegnene mellom "Fox" og "eple". | {<br>mellom:&nbsp;"hopp&nbsp;over&nbsp;den&nbsp;late",<br>FullMatch:&nbsp;"Fox&nbsp;hopper&nbsp;over&nbsp;den&nbsp;latehunden",&nbsp;<br>Under treff: ["hopper over det som er"],<br>StartMatch: 17<br> } |

For å se resultatene av **MatchAll** i et galleri:

1. Sett inn en tom, loddrett **[Galleri](../controls/control-gallery.md)** -kontroll i en tom skjerm.

2. Angi **element** -egenskapen for galleriet til **MatchAll (Pangram, "\w +")** eller **MatchAll (Pangram, MultipleLetters)** .

    ![](media/function-ismatch/pangram-gallery1.png)

3. Velg Legg til et element fra sett inn-fanen i midten av Galleri-kontrollen for å velge malen i galleriet. 

5. Legg til en **[etikett](../controls/control-text-box.md)** -kontroll i galleriets mal.  

4. Angi etikettens **tekst** -egenskap til **ThisItem. FullMatch**.  
 
    Galleriet er fylt med hvert ord i eksempel teksten.  Endre størrelsen på Galleri malen og etikett-kontrollen for å se alle ordene på én skjerm.

    ![](media/function-ismatch/pangram-gallery2.png)
