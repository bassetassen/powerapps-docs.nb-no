---
title: Funksjonene Concat og Concatenate | Microsoft Docs
description: Referanseinformasjon for funksjonene Concat og Concatenate i PowerApps, inkludert syntaks og eksempler
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 05/23/2019
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 889f612f3da208d4edfccc43a579ced07933b40d
ms.sourcegitcommit: aa9f78c304fe46922aecfe3b3fadb6bda72dfb23
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 05/24/2019
ms.locfileid: "66216088"
ms.PowerAppsDecimalTransform: true
---
# <a name="concat-and-concatenate-functions-in-powerapps"></a>Funksjonene Concat og Concatenate i PowerApps

Kjeder sammen individuelle tekststrenger og strenger i [tabeller](../working-with-tables.md).

## <a name="description"></a>Beskrivelse

**Concatenate**-funksjonen kjeder sammen en blanding av individuelle strenger og en enkeltkolonnetabell med strenger. Når du bruker denne funksjonen med individuelle strenger, er det samme som å bruke den **&** [operatoren](operators.md).

**Concatenate**-funksjonen kjeder sammen resultatet i en formel som gjelder for alle [postene](../working-with-tables.md#records) i en tabell, og resultatet er en enkeltstreng. Bruk denne funksjonen til å summere strengene i en tabell, på samme måte som funksjonen **[Sum](function-aggregates.md)** brukes på tall.

[!INCLUDE [record-scope](../../../includes/record-scope.md)]

Bruk den [ **del** ](function-split.md) eller [ **MatchAll** ](function-ismatch.md) til å dele en streng i en tabell med delstrenger.

## <a name="syntax"></a>Syntaks

**Concat**( *Table*; *Formula* )

- *Tabell* – obligatorisk.  Tabell som skal arbeides på.
- *Formel* – obligatorisk.  Formel som angis for alle postene i en tabell.

**Concatenate**( *String1* [; *String2*; ...] )

- *Streng(er)* – obligatorisk.  Kombinasjon av individuelle strenger eller en enkeltkolonnetabell med strenger.

## <a name="examples"></a>Eksempler

Eksemplene i denne delen bruker disse globale variablene:

- **Fornavn** = "Jane"
- **Etternavn** = "Doe"
- **Produkter** = ![tabell med to kolonner og fire rader](media/function-concatenate/products.png)

For å opprette disse globale variablene i en app, kan du sette inn en [ **knappen** ](../controls/control-button.md) kontroll, og angi dens **OnSelect** egenskapen til denne formelen:

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

Velg knappen (ved å klikke på den mens du holder nede Alt-tasten).

### <a name="concatenate-function-and-the--operator"></a>Kjede sammen funksjonen og & operator

I disse eksemplene må angi den **tekst** -egenskapen for en [ **etikett** ](../controls/control-text-box.md) kontroll til en formel fra den første kolonnen i neste tabell.

| Formel | Beskrivelse | Resultat |
|---------|-------------|--------|
| **Kjede sammen (&nbsp;etternavn,&nbsp;»,&nbsp;»,&nbsp;Fornavn&nbsp;)** | Kjeder sammen verdien i **Etternavn**, strengen **","** (komma etterfulgt av et mellomrom), og verdien i **Fornavn**. | «Doe,&nbsp;Jane» |
| **Etternavn&nbsp;&&nbsp;»,&nbsp;"&nbsp;&&nbsp;Fornavn** | Samme som det forrige eksemplet bortsett fra ved hjelp av den **&** operatoren i stedet for funksjonen. | «Doe,&nbsp;Jane» |
| **Kjede sammen (&nbsp;fornavn,&nbsp;"&nbsp;»,&nbsp;Etternavn&nbsp;)** | Kjeder sammen verdien i **Fornavn**, strengen **""** (ett enkelt mellomrom), og verdien i **Etternavn**. | "Jane&nbsp;Doe" |
| **Fornavn&nbsp;&&nbsp;"&nbsp;"&nbsp;&&nbsp;etternavn** | Samme som det forrige eksemplet, ved hjelp av den **&** operatoren i stedet for funksjonen. | "Jane&nbsp;Doe" |

### <a name="concatenate-with-a-single-column-table"></a>Kjede sammen med en enkeltkolonne tabell

For eksempel legge til et tomt, loddrett [ **galleriet** ](../controls/control-gallery.md) kontroll, angi dens **elementer** egenskapen til formelen i neste tabell, og legg deretter til en etikett i gallerimalen.

| Formel | Beskrivelse | Resultat |
|---------|-------------|--------|
| **Kjede sammen («navn:&nbsp;»,&nbsp;Products.Name, ",&nbsp;Type:&nbsp;»,&nbsp;Products.Type)** | For hver post i den **produkter** tabellen, Kjeder sammen strengen **"navnet:"** , navnet på produktet, strengen **", Type:"** og typen for produktet.  | ![Tabell med produkter](media/function-concatenate/single-column.png) |

### <a name="concat-function"></a>Concat funksjonen

I disse eksemplene må angi den **tekst** egenskapen for en etikett til en formel fra den første kolonnen i neste tabell.

| Formel | Beskrivelse | Resultat |
|---------|-------------|--------|
| **Concat (produkter, navn og ",")** | Evaluerer uttrykket **navnet & ","** for hver post i **produkter** og setter resultatene sammen til én tekststreng.  | «Violin,&nbsp;Cello,&nbsp;Trumpet,&nbsp;» |
| **Concat (Filter (&nbsp;produkter,&nbsp;typen&nbsp;=&nbsp;"Streng"&nbsp;), navn på & ",")** | Evaluerer formelen **navnet & ","** for hver post i **produkter** som oppfyller filteret **Type = "Streng"** , og setter resultatene til én tekststreng.   | «Violin,&nbsp;Cello,&nbsp;» |

### <a name="trimming-the-end"></a>Trimming slutten

De to siste eksemplene inkluderer et ekstra "," på slutten av resultatet. Funksjonen legger til et komma og et mellomrom til den **navnet** verdien for hver post i tabellen, inkludert den siste posten.

I noen tilfeller kan rolle ikke disse ekstra tegn. For eksempel en enkel skilletegnet ikke vises hvis du viser resultatet i en etikett. Hvis du vil fjerne disse ekstra tegn, kan du bruke den [ **venstre** ](function-left-mid-right.md) eller [ **Match** ](function-ismatch.md) funksjonen.

I disse eksemplene må angi den **tekst** egenskapen for en etikett til en formel fra den første kolonnen i neste tabell.

| Formel | Beskrivelse | Resultat |
|---------|-------------|--------|
| **Venstre (Concat (&nbsp;produkter,&nbsp;navnet&nbsp;&&nbsp;»,&nbsp;"&nbsp;), Len (&nbsp;Concat (&nbsp;produkter,&nbsp;navnet&nbsp; & &nbsp;»,&nbsp;"&nbsp;)&nbsp;)&nbsp;-&nbsp;2)** | Returnerer resultatet av **Concat** fjerner i de to siste tegnene, som utgjør overflødige skilletegn. | «Violin,&nbsp;Cello,&nbsp;Trumpet» |
| **Match (Concat (&nbsp;produkter,&nbsp;navnet&nbsp;&&nbsp;»,&nbsp;"&nbsp;)," ^ (?&lt; Trim&gt;. *),&nbsp;$») .trim** | Returnerer tegnene i **Concat** fra begynnelsen av tekststrengen (^) til slutten ($), men ikke noe uønsket komma og plass på slutten. | «Violin,&nbsp;Cello,&nbsp;Trumpet» |

### <a name="split-and-matchall"></a>Del og MatchAll

Hvis du brukte **Concat** med et skilletegn og, du kan reversere operasjonen ved å kombinere den **del** og **MatchAll** funksjoner.

I disse eksemplene må legge til et tomt, loddrett galleri, angi dens **elementer** egenskapen til en formel i neste tabell, og legg deretter til en etikett i gallerimalen.

| Formel | Beskrivelse | Resultat |
|---------|-------------|--------|
| **Del (Concat (&nbsp;produkter,&nbsp;navnet&nbsp;&&nbsp;»,&nbsp;"&nbsp;),",")** | Deler opp tekststrengen med skilletegn **","** . Strengen slutter med et komma og et mellomrom, slik at den siste raden i resultatet er en tom streng.  | ![Table](media/function-concatenate/split.png) |
| **MatchAll (Concat (&nbsp;produkter;&nbsp;navnet&nbsp;&&nbsp;»;&nbsp;"&nbsp;)," [^ \s;]+»). FullMatch** | Deler opp tekststrengen basert på tegn som ikke er mellomrom eller komma. Denne formelen fjerner den ekstra komma og et mellomrom på slutten av strengen. | ![Table](media/function-concatenate/matchall.png)