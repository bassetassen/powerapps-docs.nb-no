---
title: Funksjonene Concat og Concatenate | Microsoft Docs
description: Referanseinformasjon for funksjonene Concat og Concatenate i PowerApps, inkludert syntaks og eksempler
services: ''
suite: powerapps
documentationcenter: na
author: gregli-msft
manager: anneta
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 08/28/2017
ms.author: gregli
ms.openlocfilehash: 5f69d51fc1d018a48576cade665ebd19ec1d7c82
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/22/2018
ms.locfileid: "30995832"
---
# <a name="concat-and-concatenate-functions-in-powerapps"></a>Funksjonene Concat og Concatenate i PowerApps
Kjeder sammen individuelle tekststrenger og strenger i [tabeller](../working-with-tables.md).

## <a name="description"></a>Beskrivelse
**Concatenate**-funksjonen kjeder sammen resultatet i en formel som gjelder for alle [postene](../working-with-tables.md#records) i en tabell, og resultatet er en enkeltstreng. Bruk denne funksjonen til å summere strengene i en tabell, på samme måte som **[Sum](function-aggregates.md)**-funksjonen brukes på tall.

[!INCLUDE [record-scope](../../../includes/record-scope.md)]

Bruk **[Del](function-split.md)**-funksjonen til å fordele en streng om til en tabell med understrenger.

**Concatenate**-funksjonen kjeder sammen en blanding av individuelle strenger og en enkeltkolonnetabell med strenger. Hvis funksjonen brukes med individuelle strenger, tilsvarer den bruken av **&** [operator](operators.md). Du kan bruke en formel som inkluderer **[ShowColumns](function-table-shaping.md)**-funksjonen for å opprette en enkeltkolonnetabell ut fra en tabell som har flere kolonner.

## <a name="syntax"></a>Syntaks
**Concat**( *Table*, *Formula* )

* *Tabell* – obligatorisk.  Tabellen som funksjonen skal arbeide med.
* *Formel* – obligatorisk.  Formel som angis for alle postene i en tabell.

**Concatenate**( *String1* [, *String2*, ...] )

* *Streng(er)* – obligatorisk.  Blanding av individuelle strenger eller en enkeltkolonnetabell med strenger.

## <a name="examples"></a>Eksempler
#### <a name="concat"></a>Concat
1. Legg til en **[Knappekontroll](../controls/control-button.md)**, og sett **[OnSelect](../controls/properties-core.md)**-egenskapen til denne formelen:
   
    **Collect(Products, {String:"Violin", Wind:"Trombone", Percussion:"Bongos"}, {String:"Cello", Wind:"Trumpet", Percussion:"Tambourine"})**
2. Trykk på F5, klikk på knappen, og trykk deretter på ESC for å gå tilbake til utformingsområdet.
3. Legg til en **[Etikettkontroll](../controls/control-text-box.md)**, og sett **[Tekst](../controls/properties-core.md)**-egenskapen til denne formelen:
   
    **Concat(Products, String & " ")**
   
    Etiketten viser **Fiolin Cello**.

#### <a name="concatenate"></a>Concatenate
1. Legg til en **[Tekstinndata](../controls/control-text-input.md)**-kontroll, og gi den navnet **ForfatterNavn**.
2. Legg til en **[Etikettkontroll](../controls/control-text-box.md)**, og sett **[Tekst](../controls/properties-core.md)**-egenskapen til denne formelen:<br>
   **Concatenate("By ", AuthorName.Text)**
3. Skriv inn navnet ditt i **ForfatterNavn**.
   
    Etiketten viser **Av** etterfulgt av navnet ditt.

Hvis du har en **Ansatte**-tabell som inneholder en **Fornavn**-kolonne og en **Etternavn**-kolonne, vil denne formelen kjede sammen dataen i hver kolonnerad.
<br>**Concatenate(Employees.FirstName, " ", Employees.LastName)**

