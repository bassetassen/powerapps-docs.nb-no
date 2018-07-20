---
title: Set-funksjonen | Microsoft Docs
description: Referanseinformasjon for Set-funksjonen i PowerApps, inkludert syntaks og eksempler
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 06/29/2017
ms.author: gregli
ms.openlocfilehash: cbc66609e07492c0ac492a6260e9fdd91e5210f2
ms.sourcegitcommit: dfa0e1a7981814e15e6ca4720e2a5f930e859db1
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 07/13/2018
ms.locfileid: "39022566"
---
# <a name="set-function-in-powerapps"></a>Set-funksjonen i PowerApps
Angir verdien for en global variabel.

## <a name="overview"></a>Oversikt
Bruk **Set**-funksjonen til å angi verdien for en global variabel, som inneholder midlertidig informasjon, for eksempel hvor mange ganger brukeren har valgt en knapp eller resultatet av en dataoperasjon.  

Globale variablene er tilgjengelig i hele appen din, i alle skjermbildene.  Dette er den enkleste typen variabler og oppfylle behovene i de fleste tilfeller.  Det finnes også kontekstvariabler, som er begrenset til ett enkelt skjermbilde, og samlinger som tillater endringer i tabeller på radnivå.  Hvis du vil ha mer informasjon om disse alternativene, kan du se [Slik arbeider du med variabler](../working-with-variables.md).

PowerApps er basert på formler som automatisk beregnes på nytt når brukeren samhandler med en app.  Globale variabler tilbyr ikke denne fordelen og kan gjøre appen vanskeligere å opprette og forstå.  Før du bruker en variabel, se gjennom [Slik arbeider du med variabler](../working-with-variables.md).

## <a name="description"></a>Beskrivelse
Globale variablene opprettes implisitt ved hjelp av **Set**-funksjonen.  Det kreves ingen eksplisitt deklarasjon.  Hvis du fjerner alle **Set**-funksjonene for en global variabel, opphører variabelen å eksistere.  Angi variabelens verdi som resultatet av [**Blank**-funksjonen](function-isblank-isempty.md) for å tømme variabelen.

Du kan se variablenes verdier, definisjoner og bruk ved hjelp av Variables-visningen under Fil-menyen i redigeringsmiljøet.

I eksemplene senere i dette emnet ser du at de globale variablene kan inneholde flere typer informasjon, deriblant disse:

* en enkelt verdi
* en post
* en tabell
* en objektreferanse
* et resultat av en formel

En global variabel inneholder verdien til appen lukkes.  Når appen lukkes, går verdien til den globale variabelen tapt, og den må opprettes på nytt når appen er lastet inn på nytt.

Globale variabler kan ikke bruke samme navn som en eksisterende samling eller kontroll.  Den kan bruke samme navn som en kontekst-variabel.  Du kan du bruke [entydighetsoperatoren](operators.md#disambiguation-operator) for å skille mellom de to.

**Set** har ingen returverdi, og du kan bruke den i en [formel for virkemåte](../working-with-formulas-in-depth.md).

## <a name="syntax"></a>Syntaks
**Set**( *VariableName*, *Value* )

* *VariableName* – obligatorisk.  Navnet på en global variabel som skal opprettes eller oppdateres.
* *Value* – obligatorisk.  Verdien som skal tilordnes kontekstvariabelen.

## <a name="examples"></a>Eksempler

| Formel | Beskrivelse | Resultat |
| --- | --- | --- |
| **Set(&nbsp;Counter,&nbsp;1&nbsp;)** |Oppretter eller endrer den globale variabelen **Counter**, og angir verdien dens til **1**. |**Counter** har verdien **1**. Du kan referere til denne variabelen med navnet **Counter** i en formel på enhver skjerm. |
| **Set(&nbsp;Counter,&nbsp;2&nbsp;)** |Angir verdien for den global variabelen **Counter** fra det forrige eksemplet som **2**. |**Counter** har verdien **2**. |
| **Set(&nbsp;Counter,&nbsp;Counter + 1&nbsp;)** |Øker verdien til den global variabelen **Counter** fra det forrige eksemplet til **3**. |**Counter** har verdien **3**. |
| **Set(&nbsp;Name,&nbsp;"Lily" )** |Oppretter eller endrer den globale variabelen **Name**, og angir verdien dens til **Lily**. |**Name** har verdien **Lily**. |
| **Set(&nbsp;Person,&nbsp;{&nbsp;Name:&nbsp;"Milton", Address:&nbsp;"1&nbsp;Main&nbsp;St"&nbsp;} )** |Oppretter eller endrer den globale variabelen **Person**, og angir verdien dens som en post. Posten inneholder to kolonner, kalt **Name** og **Address**. Verdien til **Name**-kolonnen er **Milton**, og verdien til **Address**-kolonnen er **1 Main St**. |**Person** har posten **{&nbsp;Name:&nbsp;"Milton", Address:&nbsp;"1&nbsp;Main&nbsp;St"&nbsp;}** som verdi.<br><br>Du kan referere til denne posten som helhet med navnet **Person** eller referer til en individuell kolonne for denne posten med **Person.Name** eller **Person.Address**. |
| **Set(&nbsp;Person, Patch(&nbsp;Person,&nbsp;{Address:&nbsp;"2&nbsp;Main&nbsp;St"&nbsp;}&nbsp;)&nbsp;)** |Fungerer med **[Patch](function-patch.md)**-funksjonen for å oppdatere den globale variabelen **Person** ved å angi verdien til **Address**-kolonnen som **2 Main St**. |**Person** har nå posten **{&nbsp;Name:&nbsp;"Milton", Address:&nbsp;"2&nbsp;Main&nbsp;St"&nbsp;}** som verdi. |

