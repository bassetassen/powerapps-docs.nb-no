---
title: Funksjonene And, Or og Not | Microsoft Docs
description: Referanseinformasjon for funksjonene And, Or og Not i PowerApps, inkludert syntaks og eksempler
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
ms.openlocfilehash: a2b04e6a752ade561ec1b95658bcacda759b1a1c
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/07/2019
ms.locfileid: "71992569"
ms.PowerAppsDecimalTransform: true
---
# <a name="and-or-and-not-functions-in-powerapps"></a>Funksjonene And, Or og Not i PowerApps

Funksjoner for boolsk logikk, som vanligvis brukes til å behandle resultatene av sammenligninger og tester.

## <a name="description"></a>Beskrivelse

**And**-funksjonen returnerer **sann** hvis alle argumentene er **sann**.

**Or**-funksjonen returnerer **sann** hvis noen av argumentene er **sann**.

**Not**-funksjonen returnerer **sann** hvis argumentet er **usann**, og returnerer **usann** hvis argumentet er **sann**.

Disse funksjonene fungerer på samme måte som i Excel. Du kan også bruke [operatorer](operators.md) til å utføre samme operasjoner ved hjelp av Visual Basic eller JavaScript-syntaks:

| Funksjons notasjon | Visual Basic-operator | JavaScript-operator |
| -------------|------------|--------|
| **Og (x, y)** | **x og y** | **x & & y** |
| **Eller (x, y)** | **x eller y** | **x &#124; &#124; y** |
| **Not (x)** | **Not x** | **! krysset** |

Disse funksjonene fungerer med logiske verdier. Du kan ikke sende dem et tall eller en streng direkte. i stedet må du foreta en sammenligning eller en test. Denne logiske formelen **x > 1** evalueres for eksempel til den boolske verdien **sann** Hvis **x** er større enn **1**. Hvis **x** er mindre enn **1**, evalueres formelen som **Usann**.

## <a name="syntax"></a>Syntaks

**And**( *LogicalFormula1*; *LogicalFormula2* [; *LogicalFormula3*; ... ] )<br>
**Or**( *LogicalFormula1*; *LogicalFormula2* [; *LogicalFormula3*; ... ] )<br>
**Not**( *LogicalFormula* )

- *LogicalFormula* – obligatorisk.  Logiske formler som skal evalueres og arbeides med.

## <a name="examples"></a>Eksempler

Eksemplene i denne delen bruker disse globale variablene:

- **en** = -*Usann*
- **b** = *sann*
- **x** = 10
- **y** = 100
- **s** = "Hello World"

Hvis du vil opprette disse globale variablene i en app, kan du sette inn en [**knapp**](../controls/control-button.md) -kontroll og angi **OnSelect** -egenskapen til denne formelen:

```powerapps-comma
Set( a; false );; Set( b; true );; Set( x; 10 );; Set( y; 100 );; Set( s; "Hello World" )
```

Velg knappen (ved å klikke den mens du holder nede Alt-tasten), og angi deretter **tekst** -egenskapen for en [**etikett**](../controls/control-text-box.md) -kontroll til en formel i den første kolonnen i neste tabell.

| Formel | Beskrivelse | Resultat |
|---------|-------------|--------|
| **Og (a, b)** | Tester verdiene i **a** og **b**.  Ett av argumentene er *Usann*, så funksjonen returnerer *Usann*. | *usann* |
| **a og b** | Samme som det forrige eksemplet, ved hjelp av Visual Basic NOTATION. | *usann* |
| **en & & b** | Samme som det forrige eksemplet, ved hjelp av JavaScript-notasjon. | *usann* |
| **Eller (a, b)** | Tester verdiene i **a** og **b**. Ett av argumentene er *True*, og funksjonen returnerer *sann*. | *sann* |
| **a eller b** | Samme som det forrige eksemplet, ved hjelp av Visual Basic NOTATION. | *sann* |
| **a &#124; &#124; b** | Samme som det forrige eksemplet, ved hjelp av JavaScript-notasjon. | *sann* |
| **Not (a)** | Tester verdien til **a**. Argumentet er *Usann*, slik at funksjonen returnerer det motsatte resultatet. | *sann* |
| **Ikke en** | Samme som det forrige eksemplet, ved hjelp av Visual Basic NOTATION. | *sann* |
| **! av** | Samme som det forrige eksemplet, ved hjelp av JavaScript-notasjon. | *sann* |
| **Len (&nbsp; @ no__t-2) &nbsp; @ no__t-4 @ no__t-520 og @ no__t-6Not @ no__t-7IsBlank (&nbsp;s @ no__t-9)** | Tester om lengden på **s** er mindre enn 20, og om det ikke er en **tom** verdi. Lengden er mindre enn 20, og verdien er ikke tom. Resultatet er derfor *sant*. | *sann* |
| **Eller (&nbsp;Len (&nbsp;s @ no__t-3) &nbsp; @ no__t-5 @ no__t-610, x @ no__t-7 @ no__t-8 @ no__t-9100, y @ no__t-10 @ no__t-11 @ no__t-12100 @ no__t-13)** | Tester om lengden på **s** er mindre enn 10, om **x** er mindre enn 100, og om **y** er mindre enn 100. Første og tredje argument er USANN, men det andre er sant. Derfor returnerer funksjonen *sann*. | *sann* |
| **Not IsBlank (&nbsp;s @ no__t-2)** | Tester om **s** er *tom*, som returnerer *Usann*. Returnerer **ikke** det motsatte av dette resultatet, som er *sant*. | *sann* |