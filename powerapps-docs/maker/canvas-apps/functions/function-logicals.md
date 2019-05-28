---
title: Funksjonene And, Or og Not | Microsoft Docs
description: Referanseinformasjon for funksjonene And, Or og Not i PowerApps, inkludert syntaks og eksempler
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
ms.openlocfilehash: 4eb020d854549b6dc8878f07ae26390523a1bc03
ms.sourcegitcommit: aa9f78c304fe46922aecfe3b3fadb6bda72dfb23
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 05/24/2019
ms.locfileid: "66215968"
ms.PowerAppsDecimalTransform: true
---
# <a name="and-or-and-not-functions-in-powerapps"></a>Funksjonene And, Or og Not i PowerApps

Funksjoner for boolsk logikk, som vanligvis brukes til å behandle resultatene av sammenligninger og tester.

## <a name="description"></a>Beskrivelse

**And**-funksjonen returnerer **sann** hvis alle argumentene er **sann**.

**Or**-funksjonen returnerer **sann** hvis noen av argumentene er **sann**.

**Not**-funksjonen returnerer **sann** hvis argumentet er **usann**, og returnerer **usann** hvis argumentet er **sann**.

Disse funksjonene fungerer på samme måte som de gjør i Excel. Du kan også bruke [operatorer](operators.md) til å utføre disse samme operasjoner, ved hjelp av enten Visual Basic eller JavaScript-syntaks:

| Funksjonen notasjon | Visual Basic-operatoren notasjon | JavaScript-operatoren notasjon |
| -------------|------------|--------|
| **And( x; y )** | **x og y** | **x && y** |
| **Or( x; y )** | **x eller y** | **x &#124; &#124; y** |
| **Ikke (x)** | **Ikke x** | **! x** |

Disse funksjonene fungerer med logiske verdier. Du kan ikke sende dem et tall eller en streng direkte. i stedet, må du gjøre en sammenligning eller en test. For eksempel denne logiske formelen **x > 1** returnerer den boolske verdien **SANN** Hvis **x** er større enn **1**. Hvis **x** er mindre enn **1**, evalueres formelen som **USANN**.

## <a name="syntax"></a>Syntaks

**And**( *LogicalFormula1*; *LogicalFormula2* [; *LogicalFormula3*; ... ] )<br>
**Or**( *LogicalFormula1*; *LogicalFormula2* [; *LogicalFormula3*; ... ] )<br>
**Not**( *LogicalFormula* )

- *LogicalFormula* – obligatorisk.  Logiske formler som skal evalueres og arbeides med.

## <a name="examples"></a>Eksempler

Eksemplene i denne delen bruker disse globale variablene:

- **a** = *false*
- **b** = *true*
- **x** = 10
- **y** = 100
- **s** = "Hello World"

For å opprette disse globale variablene i en app, kan du sette inn en [ **knappen** ](../controls/control-button.md) kontroll, og angi dens **OnSelect** egenskapen til denne formelen:

```powerapps-comma
Set( a; false );; Set( b; true );; Set( x; 10 );; Set( y; 100 );; Set( s; "Hello World" )
```

Velg knappen (ved å klikke den mens du holder nede Alt-tasten), og angi deretter det **tekst** -egenskapen for en [ **etikett** ](../controls/control-text-box.md) kontroll til en formel i den første kolonnen i neste tabell.

| Formel | Beskrivelse | Resultat |
|---------|-------------|--------|
| **And( a; b )** | Tester verdiene for **en** og **b**.  Ett av argumentene er *USANN*, slik at funksjonen returnerer *USANN*. | *usann* |
| **en And b** | Samme som det forrige eksemplet, ved hjelp av Visual Basic-notasjon. | *usann* |
| **a && b** | Samme som det forrige eksemplet, ved hjelp av JavaScript-notasjon. | *usann* |
| **Or( a; b )** | Tester verdiene for **en** og **b**. Ett av argumentene er *SANN*, slik at funksjonen returnerer *SANN*. | *sann* |
| **en Or-b** | Samme som det forrige eksemplet, ved hjelp av Visual Basic-notasjon. | *sann* |
| **a &#124;&#124; b** | Samme som det forrige eksemplet, ved hjelp av JavaScript-notasjon. | *sann* |
| **Ikke (a)** | Tester verdien for **en**. Argumentet er *USANN*, slik at funksjonen returnerer det motsatte resultat. | *sann* |
| **Ikke en** | Samme som det forrige eksemplet, ved hjelp av Visual Basic-notasjon. | *sann* |
| **! a** | Samme som det forrige eksemplet, ved hjelp av JavaScript-notasjon. | *sann* |
| **Len (&nbsp;s&nbsp;)&nbsp;<&nbsp;20 og&nbsp;ikke&nbsp;IsBlank (&nbsp;s&nbsp;)** | Tester om lengden på **s** er mindre enn 20 og om det er ikke en **tom** verdi. Lengden er mindre enn 20, og verdien er ikke tom. Resultatet er derfor *SANN*. | *sann* |
| **Eller (&nbsp;Len (&nbsp;s&nbsp;)&nbsp;<&nbsp;10, x&nbsp;<&nbsp;100, y&nbsp;<&nbsp;100&nbsp;)** | Tester om lengden på **s** er mindre enn 10, om **x** er mindre enn 100, og om **y** er mindre enn 100. De første og tredje argumentene er false, men den andre er SANN. Derfor, returnerer funksjonen *SANN*. | *sann* |
| **Ikke IsBlank (&nbsp;s&nbsp;)** | Tester om **s** er *tom*, som returnerer *USANN*. **Ikke** returnerer motsatt av dette resultatet, som er *SANN*. | *sann* |