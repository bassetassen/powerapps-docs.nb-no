---
title: Funksjonene And, Or og Not | Microsoft Docs
description: Referanseinformasjon for funksjonene And, Or og Not i PowerApps, inkludert syntaks og eksempler
documentationcenter: na
author: gregli-msft
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: reference
ms.component: canvas
ms.date: 11/07/2015
ms.author: gregli
ms.openlocfilehash: a2e62ef2aa0a52bde33ea3e40faf96889597b09b
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/04/2018
ms.locfileid: "31825905"
---
# <a name="and-or-and-not-functions-in-powerapps"></a>Funksjonene And, Or og Not i PowerApps
Funksjoner for boolsk logikk, som vanligvis brukes til å behandle resultatene av sammenligninger og tester.

## <a name="description"></a>Beskrivelse
**And**-funksjonen returnerer **sann** hvis alle argumentene er **sann**.  **&&**[Operatoren](operators.md) tilsvarer **And**.

**Or**-funksjonen returnerer **sann** hvis noen av argumentene er **sann**.  **||** Operatoren tilsvarer **Or**.

**Not**-funksjonen returnerer **sann** hvis argumentet er **usann**, og returnerer **usann** hvis argumentet er **sann**.  **!** operatoren tilsvarer **Not**.

Disse funksjonene fungerer med logiske verdier. Du kan ikke sende et tall eller en streng direkte til funksjonen. En sammenligning eller test må utføres først. En sammenligning som **x > 1** er et eksempel på en logisk formel som returnerer den boolske verdien **sann** hvis **x** er større enn **1**. Hvis **x** er mindre enn **1**, evalueres formelen som **usann.**

## <a name="syntax"></a>Syntaks
**And**( *LogicalFormula1*, *LogicalFormula2* [, *LogicalFormula3*, ... ] )<br>
**Or**( *LogicalFormula1*, *LogicalFormula2* [, *LogicalFormula3*, ... ] )<br>
**Not**( *LogicalFormula* )

* *LogicalFormula* – obligatorisk.  Logiske formler som skal evalueres og arbeides med.

## <a name="examples"></a>Eksempler
### <a name="step-by-step"></a>Trinn for trinn
Bruk denne funksjonen til å avgjøre om verdien til en glidebryter faller utenfor området fra 50 til 100:

**Or(Slider1.Value < 50, Slider1.Value> 100)**

Hvis en [tabell](../working-with-tables.md) inneholder en **Dept**-[kolonne](../working-with-tables.md#columns) og en **Salary**-kolonne, kan du bruke denne funksjonen i en **Result**-kolonne som skal vise **sann** i alle radene der verdien i **Dept**-kolonnen er **HR** eller verdien i **Lønn**-kolonnen er større enn **200000**:

**Or(Dept = HR, Salary >= 200000)**

Alternativt kan du bruke ||-operatoren til å få de samme resultatene som de forrige formlene returnerer:

**Slider1.Value < 50 || Slider1.Value> 100**

**Dept = "HR" || Salary > 200000**

