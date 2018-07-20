---
title: Funksjonene Concat og Concatenate | Microsoft Docs
description: Referanseinformasjon for funksjonene Kjed.sammen og Kjede.sammen i PowerApps, inkludert syntaks og eksempler
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 08/28/2017
ms.author: gregli
ms.openlocfilehash: 2ead46b4b34e2013205a412eacd86197a3c3b552
ms.sourcegitcommit: dfa0e1a7981814e15e6ca4720e2a5f930e859db1
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 07/13/2018
ms.locfileid: "39015827"
---
# <a name="concat-and-concatenate-functions-in-powerapps"></a>Funksjonene Concat og Concatenate i PowerApps
Kjeder sammen individuelle tekststrenger og strenger i [tabeller](../working-with-tables.md).

## <a name="description"></a>Beskrivelse
**Concatenate**-funksjonen kjeder sammen resultatet i en formel som gjelder for alle [postene](../working-with-tables.md#records) i en tabell, og resultatet er en enkeltstreng. Bruk denne funksjonen til å summere strengene i en tabell, på samme måte som funksjonen **[Sum](function-aggregates.md)** brukes på tall.

[!INCLUDE [record-scope](../../../includes/record-scope.md)]

Bruk funksjonen **[Del](function-split.md)** til å dele en streng inn i en tabell med understrenger.

**Concatenate**-funksjonen kjeder sammen en blanding av individuelle strenger og en enkeltkolonnetabell med strenger. Hvis funksjonen brukes med individuelle strenger, tilsvarer den bruken av **&**-[operatoren](operators.md). Du kan bruke en formel som inkluderer **[ShowColumns](function-table-shaping.md)**-funksjonen for å opprette en enkeltkolonnetabell ut fra en tabell som har flere kolonner.

## <a name="syntax"></a>Syntaks
**Concat**( *Table*, *Formula* )

* *Tabell* – obligatorisk.  Tabell som skal arbeides på.
* *Formel* – obligatorisk.  Formel som angis for alle postene i en tabell.

**Concatenate**( *String1* [, *String2*, ...] )

* *Streng(er)* – obligatorisk.  Kombinasjon av individuelle strenger eller en enkeltkolonnetabell med strenger.

## <a name="examples"></a>Eksempler
#### <a name="concat"></a>Concat
1. Legg til en **[Knappekontroll](../controls/control-button.md)**, og sett **[OnSelect](../controls/properties-core.md)**-egenskapen til denne formelen:
   
    **Collect(Products, {String:"Violin", Wind:"Trombone", Percussion:"Bongos"}, {String:"Cello", Wind:"Trumpet", Percussion:"Tambourine"})**
2. Trykk på F5, klikk på knappen, og trykk deretter på ESC for å gå tilbake til utformingsområdet.
3. Legg til en **[Etikettkontroll](../controls/control-text-box.md)**, og sett **[Tekst](../controls/properties-core.md)**-egenskapen til denne formelen:
   
    **Concat(Products, String & " ")**
   
    Etiketten viser **Violin Cello**.

#### <a name="concatenate"></a>Concatenate
1. Legg til en **[Tekstinndata](../controls/control-text-input.md)**-kontroll, og gi den navnet **ForfatterNavn**.
2. Legg til en **[Etikettkontroll](../controls/control-text-box.md)**, og sett **[Tekst](../controls/properties-core.md)**-egenskapen til denne formelen:<br>
   **Concatenate("By ", AuthorName.Text)**
3. Skriv inn navnet ditt i **ForfatterNavn**.
   
    Etiketten viser **Av** etterfulgt av navnet ditt.

Hvis du hadde en **Ansatte**-tabell som inneholdt en **Fornavn**-kolonne og en **Etternavn**-kolonne, vil denne formelen kjede sammen dataene i hver rad til disse kolonnene.
<br>**Concatenate(Employees.FirstName, " ", Employees.LastName)**

