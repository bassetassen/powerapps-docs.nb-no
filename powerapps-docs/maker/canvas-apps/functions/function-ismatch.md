---
title: IsMatch-funksjonen | Microsoft Docs
description: Referanseinformasjon, inkludert syntaks, for IsMatch-funksjonen i PowerApps
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 02/05/2017
ms.author: gregli
ms.openlocfilehash: ac13b62e77b5d8ed35939983b3989b5edb13361c
ms.sourcegitcommit: dfa0e1a7981814e15e6ca4720e2a5f930e859db1
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 07/13/2018
ms.locfileid: "39018012"
---
# <a name="ismatch-function-in-powerapps"></a>IsMatch-funksjonen i PowerApps
Tester om en tekststreng samsvarer med et mønster.

## <a name="description"></a>Beskrivelse
**IsMatch**-funksjonen tester om en tekststreng samsvarer med et mønster, som kan omfatte vanlige tegn, forhåndsdefinerte mønstre eller et [vanlig uttrykk](#regular-expressions).  

Bruk **IsMatch** til å validere det en bruker har skrevet inn i en **[tekstinndata](../controls/control-text-input.md)**-kontroll. Du kan for eksempel kontrollere om brukeren har angitt en gyldig e-postadresse før resultatet lagres i datakilden. Hvis oppføringen ikke samsvarer med vilkårene dine, kan du legge til andre kontroller som ber brukeren om å rette oppføringen.

Som standard utfører **IsMatch** en samsvarstest som skiller mellom store og små bokstaver for hele tekststrengen. Du kan endre denne virkemåten ved å angi ett eller flere [**MatchOptions**](#match-options).

**IsMatch** returnerer *sann* hvis tekststrengen samsvarer med mønsteret eller *usann* hvis den ikke gjør det.

## <a name="patterns"></a>Mønstre
Nøkkelen til å bruke **IsMatch** er å beskrive mønsteret teksten skal samsvare med. Du beskriver mønsteret i en tekststreng som en kombinasjon av:

* Vanlige tegn, for eksempel **abc** eller **123**.
* Forhåndsdefinerte mønstre, for eksempel **Letter**, **MultipleDigits** eller **Email**. (**Match**-enumeratoren definerer disse mønstrene.)
* Vanlige uttrykkskoder, for eksempel **\d+\s+\d+** eller **[a-z]+**.

Kombiner disse elementene ved hjelp av [operator for sammenslåing av streng **&**](operators.md). For eksempel: **abc & Digit & \s+** er et gyldig mønster som samsvarer med tegnene a, b og c, etterfulgt av et tall mellom 0 og 9, etterfulgt av minst ett mellomromstegn.

### <a name="ordinary-characters"></a>Vanlige tegn
Det enkleste mønsteret er en rekke vanlige tegn som skal samsvare nøyaktig.

For eksempel: Strengen «Hei» samsvarer nøyaktig med mønsteret **Hei**. Ikke mer eller mindre. Strengen «hei!» samsvarer ikke med mønsteret på grunn av utropstegnet på slutten, og bruk av stor bokstav er feil for bokstaven h. (Se [MatchOptions](#match-options) for hvordan du kan endre denne virkemåten.)

Bestemte tegn er reservert for spesielle formål i mønsterspråket. Hvis du vil bruke disse tegnene, kan du enten foranstille tegnet med en **\\** (omvendt skråstrek) for å angi at tegnet skal tas bokstavelig, eller bruke et av de forhåndsdefinerte mønstrene. Denne tabellen viser spesialtegnene:

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
| **&#124;** |loddrett strek |
| **\\** |omvendt skråstrek |

Du kan for eksempel samsvare «Hei?» ved hjelp av mønsteret **Hei\\?** med en omvendt skråstrek foran spørsmålstegnet.

### <a name="predefined-patterns"></a>Forhåndsdefinerte mønstre
Med forhåndsdefinerte mønstre er det enkelt å samsvare med et sett med tegn eller en sekvens med flere tegn. Bruk [operator for sammenslåing av streng **&**](operators.md) til å kombinere egne tekststrenger med medlemmer av **Match**-enumeratoren:

| Match-enumerator | Beskrivelse | Vanlig uttrykk |
| --- | --- | --- |
| **Any** |Samsvarer med et hvilket som helst tegn. |**.** |
| **Comma** |Samsvarer med et komma. |**,** |
| **Digit** |Samsvarer med ett enkelt siffer (fra 0 til 9). |**\\d** |
| **Email** |Samsvarer med en e-postadresse som inneholder en krøllalfa (@) og et domenenavn som inneholder et punktum (.) |**.+@.+\\.[^\\.]{2,}** |
| **Hyphen** |Samsvarer med en bindestrek. |**\\-** |
| **LeftParen** |Samsvarer med en venstreparentes «(». |**\\(** |
| **Letter** |Samsvarer med en bokstav. |**\\p{L}** |
| **MultipleDigits** |Samsvarer med ett eller flere siffer. |**\\d+** |
| **MultipleLetters** |Samsvarer med én eller flere bokstaver. |**\\p{L}+** |
| **MultipleNonSpaces** |Samsvarer med ett eller flere tegn som ikke legger til mellomrom (mellomrom, tabulator, linjeskift). |**\\S+** |
| **MultipleSpaces** |Samsvarer med ett eller flere tegn som legger til mellomrom (mellomrom, tabulator, linjeskift). |**\\S+** |
| **NonSpace** |Samsvarer med ett enkelt tegn som ikke legger til mellomrom. |**\\S** |
| **OptionalDigits** |Samsvarer med ingen, ett eller flere siffer. |**\\d** |
| **OptionalLetters** |Samsvarer med ingen, én eller flere bokstaver. |**\\p{L}** |
| **OptionalNonSpaces** |Samsvarer med ingen, ett eller flere tegn som ikke legger til mellomrom. |**\\S** |
| **OptionalSpaces** |Samsvarer med ingen, ett eller flere tegn som legger til mellomrom. |**\\s** |
| **Period** |Samsvarer med et punktum eller en prikk (.). |**\\.** |
| **RightParen** |Samsvarer med en høyreparentes «)». |**\\)** |
| **Space** |Samsvarer med et tegn som legger til mellomrom. |**\\s** |

For eksempel samsvarer mønsteret **A & MultipleDigits** med bokstaven A etterfulgt av ett eller flere sifre.  

### <a name="regular-expressions"></a>Vanlige uttrykk
Mønsteret som brukes av **IsMatch**, er et *vanlig uttrykk*. Vanlige tegn og forhåndsdefinerte mønstre som er beskrevet ovenfor, hjelper deg med å bygge vanlige uttrykk.  

Vanlige uttrykk er svært kraftige, er tilgjengelig i mange programmeringsspråk og brukes til en rekke ulike formål. Denne artikkelen kan ikke beskrive alle aspektene ved vanlige uttrykk, men en mengde informasjon og opplæringer er publisert på nettet for å hjelpe deg.  

Vanlige uttrykk har forskjellige dialekter, og PowerApps bruker en variant av JavaScript-dialekten. Hvis du vil ha mer informasjon, kan du se [Syntaks for vanlig uttrykk](http://msdn.microsoft.com/library/1400241x.aspx).

I tabellen for **Match**-enumeratoren ovenfor utvides hver enumerator til et vanlig uttrykk, og tekststrengen i kolonnen Vanlig uttrykk definerer dette uttrykket.

## <a name="match-options"></a>Samsvarsalternativer
Du kan endre virkemåten til **IsMatch** ved å angi ett eller flere alternativer, som du kan kombinere ved hjelp av operatoren for strengsammenkobling (**&amp;**).  

Som standard tester **IsMatch** for et fullstendig samsvar med hele tekststrengen.

| MatchOptions-enumerator | Beskrivelse | Innvirkning på vanlig uttrykk |
| --- | --- | --- |
| **BeginsWith** |Mønsteret må samsvare med begynnelsen av teksten. |Legger til en **^** foran det vanlige uttrykket. |
| **Complete** |Standard.  Mønsteret må samsvare med hele teksten, fra begynnelse til slutt. |Legger til en **^** foran det vanlige uttrykket og **$** på slutten av det. |
| **Contains** |Mønsteret må vises et sted i teksten, men det trenger ikke å være på starten eller slutten. |Endrer ikke det vanlige uttrykket. |
| **EndsWith** |Mønsteret må samsvare med slutten av teksten. |Legger til en **$** på slutten av det vanlige uttrykket. |
| **IgnoreCase** |Behandler samsvaret mellom bokstaver på en måte som ikke skiller mellom små og store bokstaver. Som standard skiller samsvar mellom små og store bokstaver. |Endrer ikke det vanlige uttrykket. |
| **Multiline** |Samsvar på tvers av flere linjer. |Endrer ikke det vanlige uttrykket. |

## <a name="syntax"></a>Syntaks
**IsMatch**( *Text*, *Pattern* [, *Options* ] )

* *Text* – obligatorisk.  Tekststrengen som skal testes.
* *Pattern* – obligatorisk.  Mønsteret som skal testes, som en tekststreng.  Kjed sammen forhåndsdefinerte mønstre som **Match**-enumeratoren definerer, eller angi et vanlig uttrykk.
* *Options* – valgfritt.  En tekststrengkombinasjon av enumeratorverdier for **MatchOptions**.  Som standard brukes **MatchOptions.Complete**.

## <a name="examples"></a>Eksempler
### <a name="ordinary-characters"></a>Vanlige tegn
Tenk deg at appen inneholder en kontroll for **tekstinndata** med navnet **TextInput1**.  Brukeren skriver inn verdier i denne kontrollen som skal lagres i en database.   

Brukeren skriver inn **Hei, verden** i **TextInput1**.

| Formel | Beskrivelse | Resultat |
| --- | --- | --- |
| **IsMatch( TextInput1.Text, "Hei, verden" )** |Tester om brukerens inndata samsvarer nøyaktig med strengen «Hei, verden» |**sann** |
| **IsMatch( TextInput1.Text, "Far vel" )** |Tester om brukerens inndata samsvarer nøyaktig med strengen «Farvel» |**usann** |
| **IsMatch( TextInput1.Text, "hei", Contains )** |Tester om brukerens inndata inneholder ordet «hei» (skiller mellom store og små bokstaver). |**usann** |
| **IsMatch( TextInput1.Text, "hei", Contains & IgnoreCase )** |Tester om brukerens inndata inneholder ordet «hei» (skiller ikke mellom store og små bokstaver). |**sann** |

### <a name="predefined-patterns"></a>Forhåndsdefinerte mønstre

|                                                            Formel                                                            |                                                                Beskrivelse                                                                |  Resultat   |
|-------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------|-----------|
| **IsMatch( "123-45-7890", Digit & Digit & Digit & Hyphen & Digit & Digit & Hyphen & Digit & Digit & Digit & Digit & Digit )** |                                              Samsvarer med et personnummer for USA                                               | **sann**  |
|                                           **IsMatch( "joan@contoso.com", Email )**                                            |                                                         Samsvarer med en e-postadresse                                                          | **sann**  |
|                              **IsMatch( "123.456", MultipleDigits & Period & OptionalDigits )**                               |                                   Samsvarer med en rekke sifre, et punktum og deretter ingen eller flere sifre.                                   | **sann**  |
|                                **IsMatch( "123", MultipleDigits & Period & OptionalDigits )**                                 | Samsvarer med en rekke sifre, et punktum og deretter ingen eller flere sifre. Et punktum vises ikke i teksten, så dette mønsteret samsvarer ikke. | **usann** |

### <a name="regular-expressions"></a>Vanlige uttrykk

|                                                                              Formel                                                                              |                                                                                                                                  Beskrivelse                                                                                                                                   |  Resultat   |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|
|                                                                    **IsMatch( "986", "\d+" )**                                                                    |                                                                                                                    Samsvarer med et heltall større enn null.                                                                                                                     | **sann**  |
|                                                               **IsMatch( "1.02", "\d+(\.\d\d)?" )**                                                               |                                        Samsvarer med et positivt valutabeløp. Hvis inndataene inneholder et desimaltegn, må inndataene også inneholde to numeriske tegn etter desimaltegnet. For eksempel er 3.00 gyldig, men ikke 3.1.                                         | **sann**  |
|                                                            **IsMatch( "-4.95", "(-)?\d+(\.\d\d)?" )**                                                             |                                                        Samsvarer med et positivt eller negativt valutabeløp. Hvis inndataene inneholder et desimaltegn, må inndataene også inneholde to numeriske tegn etter desimaltegnet.                                                        | **sann**  |
|                                                         **IsMatch( "111-11-1111", "\d{3}-\d{2}-\d{4}" )**                                                         | Samsvarer med et personnummer for USA.  Validerer format, type og lengde for det angitte inndatafeltet. Strengen som skal samsvare, må bestå av tre numeriske tegn etterfulgt av en bindestrek og deretter to numeriske tegn etterfulgt av en bindestrek, og deretter fire numeriske tegn. | **sann**  |
|                                                         **IsMatch( "111-111-111", "\d{3}-\d{2}-\d{4}" )**                                                         |                                                                                               Samme som det forrige eksemplet, men en av bindestrekene er på feil sted i inndataene.                                                                                               | **usann** |
|                                         **IsMatch( "weakpassword", "(?!^[0-9]\*$)(?!^[a-zA-Z]\*$)([a-zA-Z0-9]{8,10})" )**                                         |                                        Validerer et sterkt passord, som må inneholde 8, 9 eller 10 tegn, i tillegg til minst ett siffer og minst én bokstav. Strengen kan ikke inneholde spesialtegn.                                        | **usann** |
| **IsMatch( "<http://microsoft.com>", "(ht&#124;f)tp(s?)\:\/\/\[0-9a-zA-Z\]([-.\w]\*[0-9a-zA-Z])\*(:(0-9)\*)\*(\/?)([a-zA-Z0-9\-\.\?\,\'\/\\\+&amp;%\$#_]\*)?" )** |                                                                                                                     Validerer en nettadresse for HTTP, HTTPS eller FTP.                                                                                                                      | **sann**  |

