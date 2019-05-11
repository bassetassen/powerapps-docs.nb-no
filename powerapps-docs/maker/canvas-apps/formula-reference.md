---
title: Funksjoner, signaler og opplistinger | Microsoft Docs
description: Referanseinformasjon for funksjoner, signaler og opplistinger i PowerApps.
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
ms.openlocfilehash: c801a67cc7944d32a6a0a93e8b8566618b66da98
ms.sourcegitcommit: f6c9e525130a03b8c76f0a4b4e90419604c5823c
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 05/10/2019
ms.locfileid: "65525645"
---
# <a name="formula-reference-for-powerapps"></a>Formelreferanse for PowerApps
Formler kombinerer mange elementer.  Dette er listet opp under:

* **Funksjoner** bruker parametere, utfører en operasjon og returnerer en verdi. Eksempel: **Sqrt(25)** returnerer **5**. Funksjonene er modellert etter funksjoner i Microsoft Excel.  Noen funksjoner har begrensninger, for eksempel **SubmitForm**. Denne passer kun i en [formel for virkemåte](working-with-formulas-in-depth.md), som for eksempel **Button.OnSelect**.
* **Signals** returnerer informasjon om miljøet. **[Location](functions/signals.md)** returnerer for eksempel enhetens gjeldende GPS-koordinater. Signaler bruker ikke parametere og har ikke bivirkninger.
* **Enumerations** returnerer en forhåndsdefinert konstant verdi. **[Color](functions/function-colors.md)** er for eksempel en opplisting som har forhåndsdefinerte verdier for **Color.Red**, **Color.Blue**og så videre.  Vanlige opplistinger er inkludert her. Funksjonsspesifikke opplistinger beskrives sammen med funksjonen.
* **Navngitt operator**, for eksempel **[ThisItem](functions/operators.md#thisitem-operator)** og **[Overordnet](functions/operators.md#parent-operator)**, gir tilgang til informasjon fra en beholder.

Andre elementer omfatter:

* [Alle operatorer](functions/operators.md)
* [Kontroller og egenskapene](reference-properties.md)

## <a name="a"></a>A
**[Abs](functions/function-numericals.md)**  – absoluttverdien til et tall.  

**[Acceleration](functions/signals.md)** – leser av akselerasjonssensoren på enheten.

**[Acos](functions/function-trig.md)** – returnerer arccosinusen for et tall, i radianer.

**[Acot](functions/function-trig.md)** – returnerer arccotangensen for et tall, i radianer.

**[AddColumns](functions/function-table-shaping.md)** – returnerer en tabell med [kolonner](working-with-tables.md#columns) lagt til.

**[And](functions/function-logicals.md)** – boolsk logikk (AND).  Returnerer **sann** hvis alle argumentene er **sann**.  Du kan også bruke [**&&**-operatoren](functions/operators.md).

**[App](functions/signals.md)** – returnerer informasjon om den kjørende appen, for eksempel hvilken skjerm den vises på for øyeblikket.

**[Asin](functions/function-trig.md)** – returnerer arcsinusen for et tall i radianer.

**[AsType](functions/function-astype-istype.md)**  – behandler en postreferanse som en bestemt enhet-type.

**[Atan](functions/function-trig.md)** – returnerer arctangensen for et tall i radianer.

**[Atan2](functions/function-trig.md)** – returnerer arctangensen basert på en (*x*,*y*)-koordinat i radianer.

**[Average](functions/function-aggregates.md)** – beregner gjennomsnittet av et tabelluttrykk eller et sett med argumenter.

## <a name="b"></a>B
**[Back](functions/function-navigate.md)** – viser forrige skjerm.  

**[Blank](functions/function-isblank-isempty.md)** – returnerer en *tom* verdi som kan brukes til å sette inn en nullverdi i en datakilde.

## <a name="c"></a>C
**[Calendar](functions/function-clock-calendar.md)** – henter informasjon om kalenderen for gjeldende nasjonale innstillinger.

**[Char](functions/function-char.md)** – oversetter en tegnkode til en streng.

**[Choices](functions/function-choices.md)** – returnerer en tabell med de mulige verdiene for en oppslagskolonne.

**[Clear](functions/function-clear-collect-clearcollect.md)** – sletter alle data fra en [samling](working-with-data-sources.md#collections).

**[ClearCollect](functions/function-clear-collect-clearcollect.md)** – sletter alle data fra en samling og legger deretter til et sett med [poster](working-with-tables.md#records).

**[Clock](functions/function-clock-calendar.md)** – henter informasjon om klokken for gjeldende nasjonale innstillinger.

**[Coalesce](functions/function-isblank-isempty.md)** – erstatter *tom*-verdier mens verdier som ikke er *tom* forblir uendret.

**[Collect](functions/function-clear-collect-clearcollect.md)** – oppretter en samling eller legger til data i en datakilde.

**[Color](functions/function-colors.md)** – angir en egenskap til en innebygd fargeverdi.

**[ColorFade](functions/function-colors.md)** – toner ut en fargeverdi.

**[ColorValue](functions/function-colors.md)**  – oversetter et CSS-fargenavn eller en heksadesimalkode til en fargeverdi.  

**[Compass](functions/signals.md)** – returnerer kompassoverskriften.

**[Concat](functions/function-concatenate.md)** – kjeder sammen strenger i en datakilde.  

**[Concatenate](functions/function-concatenate.md)** – kjeder sammen strenger.

**[Concurrent](functions/function-concurrent.md)** – evaluerer flere formler samtidig mot hverandre. 

**[Connection](functions/signals.md)** – returnerer informasjon om nettverkstilkoblingen.

**[Count](functions/function-table-counts.md)** – teller postene i tabellen som inneholder tall.

**[Cos](functions/function-trig.md)** – returnerer cosinusen for en vinkel spesifisert i radianer.

**[Cot](functions/function-trig.md)** – returnerer contangensen for en vinkel spesifisert i radianer.

**[CountA](functions/function-table-counts.md)** – teller postene i tabellen som ikke er [tom](functions/function-isblank-isempty.md).

**[CountIf](functions/function-table-counts.md)** – teller tabellposter som oppfyller en betingelse.  

**[CountRows](functions/function-table-counts.md)** – teller postene i tabellen.   

## <a name="d"></a>D
**[DataSourceInfo](functions/function-datasourceinfo.md)** – gir informasjon om en datakilde.

**[Date](functions/function-date-time.md)** – returnerer en dato-/klokkeslett-verdi, basert på **år**, **måned** og **dag** som verdier.  

**[DateAdd](functions/function-dateadd-datediff.md)**  – legger til dager, måneder, kvartaler eller år i en dato-/klokkeslett-verdi.

**[DateDiff](functions/function-dateadd-datediff.md)** – trekker fra to datoverdier, og viser resultatet i dager, måneder, kvartaler eller år.

**[DateTimeValue](functions/function-datevalue-timevalue.md)** – konverterer en dato- og klokkeslettverdi i en tekststreng til en dato-/klokkeslett-verdi.

**[DateValue](functions/function-datevalue-timevalue.md)** – konverterer en dato- og klokkeslettverdi i en tekststreng til en dato-/klokkeslett-verdi.

**[Day](functions/function-datetime-parts.md)** – henter datodelen fra en dato-/klokkeslett-verdi.  

**[Defaults](functions/function-defaults.md)** – returnerer standardverdiene for en datakilde.

**[Degrees](functions/function-trig.md)** – konverterer radianer til grader.

**[Disable](functions/function-enable-disable.md)** – deaktiverer et signal, for eksempel  **[Plassering](functions/signals.md)**, for å lese GPS-en.

**[Distinct](functions/function-distinct.md)** – oppsummerer poster i en tabell og fjerner duplikater.  

**[Download](functions/function-param.md)** – laster ned en fil fra nettet til den lokale enheten.

**[DropColumns](functions/function-table-shaping.md)** – returnerer en tabell med én eller flere kolonner som er fjernet.

## <a name="e"></a>E
**[EditForm](functions/function-form.md)** – tilbakestiller en skjemakontroll for redigering av et element.

**[Enable](functions/function-enable-disable.md)** – aktiverer et signal, for eksempel  **[Plassering](functions/signals.md)**, for å lese GPS-en.

**[EndsWith](functions/function-startswith.md)** – kontrollerer om en tekststreng slutter med en annen tekststreng.

**[Errors](functions/function-errors.md)** – gir feilinformasjon om tidligere endringer for en datakilde.

**[EncodeUrl](functions/function-encode-decode.md)** – koder spesialtegn ved hjelp av URL-koding.

**[Exit](functions/function-exit.md)** – avslutter appen som kjører.

**[Exp](functions/function-numericals.md)** – returnerer *e* opphøyd i en potens.

## <a name="f"></a>F
**[Filter](functions/function-filter-lookup.md)** – returnerer en filtrert tabell basert på ett eller flere vilkår.

**[Find](functions/function-find.md)** – kontrollerer om én streng vises sammen med en annen, og returnerer plasseringen.

**[First](functions/function-first-last.md)** – returnerer den første posten i en tabell.

**[FirstN](functions/function-first-last.md)**  – returnerer det første settet med poster (N poster) i en tabell.

**[ForAll](functions/function-forall.md)** – beregner verdier og utfører handlinger for alle poster i en tabell.

## <a name="g"></a>G
**[GroupBy](functions/function-groupby.md)**  – returnerer en tabell med poster gruppert sammen.

**[GUID](functions/function-guid.md)** – Konverterer en GUID-streng til en GUID-verdi, eller oppretter en ny GUID-verdi.

## <a name="h"></a>H
**[HashTags](functions/function-hashtags.md)** – henter ut emneknagger (#strenger) fra en streng.

**[Hour](functions/function-datetime-parts.md)**  – returnerer time-delen av en dato-/klokkeslett-verdi.

## <a name="i"></a>I
**[If](functions/function-if.md)** – returnerer én verdi hvis en betingelse er sann og en annen verdi hvis den ikke er det. 

**[IfError](functions/function-iferror.md)** – oppdager feil, og oppgir en alternativ verdi eller utfører en handling. 

**[IsBlank](functions/function-isblank-isempty.md)** – søker etter en [tom](functions/function-isblank-isempty.md) verdi.

**[IsEmpty](functions/function-isblank-isempty.md)** – søker etter en tom tabell.

**[IsMatch](functions/function-ismatch.md)** – kontrollerer en streng mot et mønster.  Vanlige uttrykk kan brukes.

**[IsNumeric](functions/function-isnumeric.md)** – leter etter en numerisk verdi.

**[IsToday](functions/function-now-today-istoday.md)** – kontrollerer om en dato-/klokkeslett-verdi er i løpet av denne dagen.

**[IsType](functions/function-astype-istype.md)**  – kontrollerer om en postreferanse refererer til en bestemt enhet-type.  

## <a name="l"></a>L
**[Language](functions/function-language.md)** – returnerer språkkoden for gjeldende bruker.

**[Last](functions/function-first-last.md)** – returnerer den siste posten i en tabell.

**[LastN](functions/function-first-last.md)** – returnerer det siste settet med poster (N poster) i en tabell.

**[Launch](functions/function-param.md)** – starter en nettadresse eller en app.

**[Left](functions/function-left-mid-right.md)** – returnerer delen lengst til venstre i en streng.

**[Len](functions/function-len.md)** – returnerer lengden på en streng.

**[Ln](functions/function-numericals.md)** – returnerer den naturlige loggen.

**[LoadData](functions/function-savedata-loaddata.md)** – laster inn en samling fra PowerApps private lagring.

**[Location](functions/signals.md)** – returnerer plasseringen din som et kartkoordinat ved hjelp av GPS-data og annen informasjon.

**[LookUp](functions/function-filter-lookup.md)** – slår opp én enkelt post i en tabell basert på ett eller flere vilkår.

**[Lower](functions/function-lower-upper-proper.md)** – konverterer bokstaver i en tekststreng slik at alle bokstavene blir små.

## <a name="m"></a>M
**[Match](functions/function-ismatch.md)**  – trekker ut en delstreng basert på et mønster.  Vanlige uttrykk kan brukes.

**[MatchAll](functions/function-ismatch.md)**  – trekker ut flere delstrenger basert på et mønster.  Vanlige uttrykk kan brukes.

**[Max](functions/function-aggregates.md)** – maksimumsverdien av et tabelluttrykk eller et sett med argumenter.

**[Mid](functions/function-left-mid-right.md)** – returnerer den midterste delen av en streng.

**[Min](functions/function-aggregates.md)** – minimumsverdien av et tabelluttrykk eller et sett med argumenter.

**[Minute](functions/function-datetime-parts.md)** – henter minutt-delen av en dato-/klokkeslett-verdi.  

**[Mod](functions/function-mod.md)** – returnerer det som gjenstår når en divident er dividert med en divisor.

**[Month](functions/function-datetime-parts.md)** – henter måned-delen av en dato-/klokkeslett-verdi.

## <a name="n"></a>N
**[Navigate](functions/function-navigate.md)** – endrer hvilken skjem som vises.

**[NewForm](functions/function-form.md)** – tilbakestiller en skjemakontroll for oppretting av et element.

**[Not](functions/function-logicals.md)** – boolsk logikk (NOT).  Returnerer **sann** hvis argumentet er **usant**, og returnerer **usann** hvis argumentet er **sant**.  Du kan også bruke [**!**-operatoren](functions/operators.md).

**[Notify](functions/function-showerror.md)** – viser en bannermelding til brukeren.

**[Now](functions/function-now-today-istoday.md)** – returnerer gjeldende dato-/klokkeslett-verdi.

## <a name="o"></a>O
**[Or](functions/function-logicals.md)** – boolsk logikk (OR).  Returnerer **sann** hvis noen av argumentene dens er **sann**.  Du kan også bruke [**||**-operatoren](functions/operators.md).

## <a name="p"></a>P
**[Param](functions/function-param.md)** – gir tilgang til parametere sendt til appen når brukeren åpnet den.

**[Parent](functions/operators.md#parent-operator)** – gir tilgang til kontrollegenskaper for en beholder.

**[Patch](functions/function-patch.md)** – endrer eller oppretter en post i en datakilde, eller slår sammen poster utenfor en datakilde.

**[Pi](functions/function-trig.md)** – returnerer tallet &pi;.

**[PlainText](functions/function-encode-decode.md)** – fjerner HTML- og XML-koder fra en streng.

**[Power](functions/function-numericals.md)** – returnerer et tall opphøyd i en potens.  Du kan også bruke [**^**-operatoren](functions/operators.md).

**[Proper](functions/function-lower-upper-proper.md)** – konverterer den første bokstaven i hvert ord i en streng til store bokstaver, og konverterer resten til små bokstaver.

## <a name="r"></a>R
**[Radians](functions/function-trig.md)** – konverterer grader til radianer.

**[Rand](functions/function-rand.md)** – returnerer et pseudo-tilfeldig tall.

**[Refresh](functions/function-refresh.md)** – oppdaterer postene for en datakilde.

**[Relatert](functions/function-relate-unrelate.md)**  – er relatert poster med to enheter via en én-til-mange eller mange-til-mange-relasjon.

**[Remove](functions/function-remove-removeif.md)** – fjerner én eller flere bestemte poster fra en datakilde.

**[RemoveIf](functions/function-remove-removeif.md)** – fjerner poster fra en datakilde basert på en betingelse.

**[RenameColumns](functions/function-table-shaping.md)** – gir nytt navn til kolonner i en tabell.

**[Replace](functions/function-replace-substitute.md)** – erstatter deler av en streng med en annen streng, fra startposisjonen for strengen.

**[Reset](functions/function-reset.md)** – tilbakestiller en inndatakontroll til sin standardverdi, og forkaster brukerendringer.

**[ResetForm](functions/function-form.md)** – tilbakestiller en skjemakontroll for redigering av et eksisterende element.

**[Revert](functions/function-revert.md)** – laster inn på nytt og fjerner feil for postene i en datakilde.

**[RGBA](functions/function-colors.md)** – returnerer en fargeverdi for et sett med rød-, grønn-, blå- og alfa-komponenter.

**[Right](functions/function-left-mid-right.md)** – returnerer delen lengst til venstre i en streng.

**[Round](functions/function-round.md)** – runder av til nærmeste tall.

**[RoundDown](functions/function-round.md)** – runder ned til det høyeste forrige tallet.

**[RoundUp](functions/function-round.md)** – runder opp til det minste etterfølgende tallet.

## <a name="s"></a>S
**[SaveData](functions/function-savedata-loaddata.md)** – lagrer en samling i privat PowerApps-lagring.

**[Search](functions/function-filter-lookup.md)** – finner poster i en tabell som inneholder en streng i én av kolonnene.  

**[Second](functions/function-datetime-parts.md)** – henter den andre delen av en dato-/klokkeslett-verdi.

**[Select](functions/function-select.md)** – simulerer en valgt handling på en kontroll som fører til at **OnSelect**-formelen evalueres.

**[Set](functions/function-set.md)** – angir verdien til en global variabel.

**[ShowColumns](functions/function-table-shaping.md)** – returnerer en tabell med bare valgte kolonner.

**[Shuffle](functions/function-shuffle.md)** – omorganiserer postene i en tabell i tilfeldig rekkefølge.

**[Sin](functions/function-trig.md)** – returnerer sinusen for en vinkel angitt i radianer.

**[Sort](functions/function-sort.md)** – returnerer en sortert tabell basert på en formel.

**[SortByColumns](functions/function-sort.md)** – returnerer en sortert tabell basert på én eller flere kolonner.

**[Split](functions/function-split.md)** – deler en tekststreng i en tabell med delstrenger.

**[Sqrt](functions/function-numericals.md)** – returnerer kvadratroten av et tall.

**[StartsWith](functions/function-startswith.md)** – kontrollerer om en tekststreng begynner med en annen tekststreng.

**[StdevP](functions/function-aggregates.md)** – returnerer standardavviket for argumentene.  

**[Substitute](functions/function-replace-substitute.md)** – erstatter en del av en streng med en annen streng ved å sammenligne strenger.

**[SubmitForm](functions/function-form.md)** – lagrer elementet i en skjemakontroll til datakilden.

**[Sum](functions/function-aggregates.md)** – beregner summen for et tabelluttrykk eller et sett med argumenter.  

**[Switch](functions/function-if.md)** – samsvarer med et sett med verdier og evaluerer deretter en tilsvarende formel.

## <a name="t"></a>T
**[Table](functions/function-table.md)** – oppretter en midlertidig tabell.  

**[Tan](functions/function-trig.md)** – returnerer tangensen for en vinkel angitt i radianer.

**[Tekst](functions/function-text.md)**  – konverterer en verdi og formaterer en tall- eller dato/klokkeslett-verdi til en tekststreng.

**[ThisItem](functions/operators.md#thisitem-operator)** – dataene for gjeldende element for en beholder returneres når man er i et galleri eller skjema.

**[Time](functions/function-date-time.md)** – returnerer en dato-/klokkeslett-verdi, basert på **Time-**, **Minutt-** og **Sekund**-verdier.  

**[TimeValue](functions/function-datevalue-timevalue.md)** – konverterer en streng som bare inneholder klokkeslett til en dato-/tid-verdi.

**[TimeZoneOffset](functions/function-dateadd-datediff.md)** – returnerer forskjellen mellom UTC og brukerens lokaltid i minutter.

**[Today](functions/function-now-today-istoday.md)** – returnerer gjeldende dato-/klokkeslett-verdi.

**[Trim](functions/function-trim.md)** – fjerner ekstra mellomrom fra endene og øvrig innhold i en tekststreng.

**[TrimEnds](functions/function-trim.md)** – fjerner ekstra mellomrom fra slutten av en streng med bare tekst.

## <a name="u"></a>U
**[Ungroup](functions/function-groupby.md)** – fjerner en gruppering.

**[Unrelate](functions/function-relate-unrelate.md)**  – Unrelates postene i to enheter fra en én-til-mange eller mange-til-mange-relasjon.

**[Update](functions/function-update-updateif.md)** – erstatter en post i en datakilde.

**[UpdateContext](functions/function-updatecontext.md)** – angir verdien for én eller flere [kontekstvariabler](working-with-variables.md#use-a-context-variable) for den gjeldende skjermen.

**[UpdateIf](functions/function-update-updateif.md)** – endrer et sett med poster i en datakilde basert på en betingelse.

**[Upper](functions/function-lower-upper-proper.md)** – konverterer bokstaver i en tekststreng til kun store bokstaver.

**[User](functions/function-user.md)** – returnerer informasjon om den gjeldende brukeren.

## <a name="v"></a>V
**[Validate](functions/function-validate.md)** – kontrollerer hvorvidt verdien for en enkeltkolonne eller en fullstendig post er gyldig for en datakilde.

**[Value](functions/function-value.md)** – konverterer en streng til et tall.

**[VarP](functions/function-aggregates.md)** – returnerer variansen for de tilknyttede argumentene.  

**[ViewForm](functions/function-form.md)** – tilbakestiller en skjemakontroll for visning av et eksisterende element.

## <a name="w"></a>W
**[Weekday](functions/function-datetime-parts.md)** – henter ukedag-delen av en dato-/klokkeslett-verdi.

## <a name="y"></a>Y
**[Year](functions/function-datetime-parts.md)** – henter år-delen av en dato-/klokkeslett-verdi.  

