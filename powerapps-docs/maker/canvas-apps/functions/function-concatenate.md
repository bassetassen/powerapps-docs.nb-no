---
title: Funksjonene Concat og Concatenate | Microsoft Docs
description: Referanseinformasjon for funksjonene Concat og Concatenate i PowerApps, inkludert syntaks og eksempler
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 05/23/2019
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 0a56230539990ce51cc9270f71d8c2b7c9a1db73
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/07/2019
ms.locfileid: "71992873"
ms.PowerAppsDecimalTransform: true
---
# <a name="concat-and-concatenate-functions-in-powerapps"></a>Funksjonene Concat og Concatenate i PowerApps

Kjeder sammen individuelle tekststrenger og strenger i [tabeller](../working-with-tables.md).

## <a name="description"></a>Beskrivelse

**Concatenate**-funksjonen kjeder sammen en blanding av individuelle strenger og en enkeltkolonnetabell med strenger. Når du bruker denne funksjonen med individuelle strenger, er det det samme som å bruke **&-** [operatoren](operators.md).

**Concatenate**-funksjonen kjeder sammen resultatet i en formel som gjelder for alle [postene](../working-with-tables.md#records) i en tabell, og resultatet er en enkeltstreng. Bruk denne funksjonen til å summere strengene i en tabell, på samme måte som funksjonen **[Sum](function-aggregates.md)** brukes på tall.

[!INCLUDE [record-scope](../../../includes/record-scope.md)]

Bruk [**Split**](function-split.md) -eller [**MatchAll**](function-ismatch.md) -funksjonen til å dele inn en streng i en tabell med del strenger.

## <a name="syntax"></a>Syntaks

**Concat**( *Table*; *Formula* )

- *Tabell* – obligatorisk.  Tabell som skal arbeides på.
- *Formel* – obligatorisk.  Formel som angis for alle postene i en tabell.

**Concatenate**( *String1* [; *String2*; ...] )

- *Streng(er)* – obligatorisk.  Kombinasjon av individuelle strenger eller en enkeltkolonnetabell med strenger.

## <a name="examples"></a>Eksempler

Eksemplene i denne delen bruker disse globale variablene:

- **For navn** = "Janne"
- **Etternavn** = «Nordmann»
- **Produkter** =  @ No__t-2Table med to kolonner og fire rader @ no__t-3

Hvis du vil opprette disse globale variablene i en app, kan du sette inn en [**knapp**](../controls/control-button.md) -kontroll og angi **OnSelect** -egenskapen til denne formelen:

```powerapps-comma
Set( FirstName; "Jane" );; Set( LastName; "Doe" );;
Set( Products;
    Table(
        { Name: "Violin"; Type: "String" };
        { Name: "Cello"; Type: "String" };
        { Name: "Trumpet"; Type: "Wind" }
    )
)
```

Velg knappen (ved å klikke den mens du holder nede Alt-tasten).

### <a name="concatenate-function-and-the--operator"></a>Sammenkjeding, funksjon og &-operatoren

I disse eksemplene kan du angi **tekst** -egenskapen for en [**etikett**](../controls/control-text-box.md) -kontroll til en formel fra den første kolonnen i neste tabell.

| Formel | Beskrivelse | Resultat |
|---------|-------------|--------|
| **Sammenkjeding (&nbsp;LastName, &nbsp;», &nbsp;», &nbsp;FirstName @ no__t-5)** | Slår sammen verdien i **Etternavn**, strengen **,** (et komma etterfulgt av et mellomrom) og verdien i **for navn**. | «Nordmann, &nbsp;Jane» |
| **Etternavn @ no__t-1 @ no__t-2 @ no__t-3 ", &nbsp;" &nbsp; @ no__t-6 @ no__t-7FirstName** | Samme som det forrige eksemplet unntatt ved hjelp av operatoren **&** i stedet for funksjonen. | «Nordmann, &nbsp;Jane» |
| **Sammenkjeding (&nbsp;FirstName, &nbsp; "&nbsp;", &nbsp;LastName @ no__t-5)** | Setter sammen verdien i **for navn** **, strengen (** et enkelt mellomrom) og verdien i **etter navn**. | "Janne @ no__t-0Doe" |
| **For navn @ no__t-1 @ no__t-2 @ no__t-3 "&nbsp;" &nbsp; @ no__t-6 @ no__t-7LastName** | Samme som det forrige eksemplet, ved hjelp av **&-** operatoren i stedet for funksjonen. | "Janne @ no__t-0Doe" |

### <a name="concatenate-with-a-single-column-table"></a>Kjede sammen med en enkelt Kol onne tabell

I dette eksemplet kan du legge til en tom, loddrett [**Galleri**](../controls/control-gallery.md) -kontroll, angi **elementer** -egenskapen til formelen i den neste tabellen, og deretter legge til en etikett i Galleri malen.

| Formel | Beskrivelse | Resultat |
|---------|-------------|--------|
| **Sammenkjeding («navn: &nbsp;», &nbsp;Products.Name, ", &nbsp;Type: &nbsp;", &nbsp;Products. type)** | For hver post i **produkter** -tabellen sammenkobles strengen **«navn:»** , navnet på produktet, strengen **, type:»** og produkt typen.  | ![Tabell over produkter](media/function-concatenate/single-column.png) |

### <a name="concat-function"></a>Concat, funksjon

I disse eksemplene kan du angi **tekst** -egenskapen for en etikett til en formel fra den første kolonnen i neste tabell.

| Formel | Beskrivelse | Resultat |
|---------|-------------|--------|
| **Concat (produkter, navn &»)** | Evaluerer uttrykks **navnet & «,»** for hver **produkt** post, og setter sammen resultatene til én enkelt tekst streng.  | «Violin, &nbsp;Cello, &nbsp;Trumpet, &nbsp;» |
| **Concat (filter (&nbsp;Products, &nbsp;Type @ no__t-3 @ no__t-4 @ no__t-5 "string" &nbsp;), navn & ",")** | Evaluerer formel **navnet & «,»** for hver produkt post som Sams **varer** med filter **typen = "string"** , og slår sammen resultatene til én tekst streng.   | «Violin, &nbsp;Cello, &nbsp;» |

### <a name="trimming-the-end"></a>Trimme slutten

De to siste eksemplene inkluderer en ekstra «,» på slutten av resultatet. Funksjonen tilføyer et komma og et mellomrom til **navne** verdien for hver post i tabellen, inkludert den siste posten.

I noen tilfeller spiller ikke disse ekstra tegnene noen rolle. En enkel skille tegn vises for eksempel ikke hvis du viser resultatet i en etikett. Hvis du vil fjerne disse ekstra tegnene, bruker du funksjonen [**Left**](function-left-mid-right.md) eller [**match**](function-ismatch.md) .

I disse eksemplene kan du angi **tekst** -egenskapen for en etikett til en formel fra den første kolonnen i neste tabell.

| Formel | Beskrivelse | Resultat |
|---------|-------------|--------|
| **Left (concat (&nbsp;Products, &nbsp;Name @ no__t-3 @ no__t-4 @ no__t-5 ", &nbsp;" &nbsp;), len (&nbsp;Concat (&nbsp;Products, 0Name @ no__t-11 @ no__t-12 @ no__t-13», 4 "5) 7 @ no__t-18 @ no__t-192)** | Returnerer resultatet av **concat** , men fjerner de to siste tegnene, som utgjør det overflødige skille tegnet. | «Violin, &nbsp;Cello, &nbsp;Trumpet» |
| **Match (concat (&nbsp;Products, &nbsp;Name @ no__t-3 @ no__t-4 @ no__t-5 ", &nbsp;" &nbsp;) "," ^ (? &lt;trim @ no__t-9. *), @no__t-$10 "). trimme** | Returnerer tegnene fra **concat** fra begynnelsen av tekst strengen (^) til slutten ($), men inkluderer ikke det uønskede kommategnet og mellomrommet på slutten. | «Violin, &nbsp;Cello, &nbsp;Trumpet» |

### <a name="split-and-matchall"></a>Splitt og MatchAll

Hvis du har brukt **concat** med et skille tegn, kan du reversere operasjonen ved å kombinere funksjonene **Split** og **MatchAll** .

Legg til et tomt, loddrett galleri i disse eksemplene, angi **elementer** -egenskapen til en formel i den neste tabellen, og legg deretter til en etikett i Galleri malen.

| Formel | Beskrivelse | Resultat |
|---------|-------------|--------|
| **Split (concat (&nbsp;Products, &nbsp;Name @ no__t-3 @ no__t-4 @ no__t-5 ", &nbsp;" &nbsp;), ",")** | Deler tekst strengen med skille tegnet **,** . Strengen slutter med et komma og mellomrom, slik at den siste raden i resultatet er en tom streng.  | ![Table](media/function-concatenate/split.png) |
| **MatchAll (concat (&nbsp;Products; &nbsp;Name @ no__t-3 @ no__t-4 @ no__t-5 ", &nbsp;" &nbsp;); "[^ \s,] +"). FullMatch** | Deler tekst strengen basert på tegn som ikke er mellomrom eller komma. Denne formelen fjerner det ekstra kommategnet og mellomrommet på slutten av strengen. | ![Table](media/function-concatenate/matchall.png)