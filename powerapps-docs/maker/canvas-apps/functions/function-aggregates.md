---
title: Funksjonene Average, Max, Min, StdevP, Sum og VarP | Microsoft Docs
description: Referanseinformasjon for funksjonene Average, Max, Min, StdevP, Sum og VarP i PowerApps, inklusive syntaks og eksempler
documentationcenter: na
author: gregli-msft
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: reference
ms.component: canvas
ms.date: 08/15/2017
ms.author: gregli
ms.openlocfilehash: e488383acbd163383079b5078e464cab89e677ad
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/04/2018
ms.locfileid: "31829052"
---
# <a name="average-max-min-stdevp-sum-and-varp-functions-in-powerapps"></a>Funksjonene Average, Max, Min, StdevP, Sum og VarP i PowerApps
Aggregatfunksjoner som oppsummerer et sett med tall.

## <a name="description"></a>Beskrivelse
**Average**-funksjonen beregner gjennomsnittet, dvs. den aritmetiske middelverdien av argumentene.

**Max**-funksjonen finner den høyeste verdien.

**Min**-funksjonen finner den laveste verdien.

**Sum**-funksjonen beregner summen av argumentene.

**StdevP**-funksjonen beregner standardavviket for argumentene.

**VarP**-funksjonen beregner variansen for argumentene.

Du kan angi verdiene for disse funksjonene som:

* Separate argumenter. Eksempel: **Sum (1, 2, 3)** returnerer 6.
* En [tabell](../working-with-tables.md) og en formel som opererer på tabellen.  Aggregatet beregnes på verdiene av formelen for hver [post](../working-with-tables.md#records).  

[!INCLUDE [record-scope](../../../includes/record-scope.md)]

Disse funksjonene fungerer bare på numeriske verdier. Andre typer verdier, for eksempel strenger eller poster, blir oversett. Bruk **[Value](function-value.md)**-funksjonen til å konvertere en streng til et tall.

Funksjonene **Average**, **Max**, **Min** og **Sum** kan delegeres når de brukes med en [datakilde som støtter delegering for disse funksjonene](../delegation-list.md).  **StdevP** og **VarP** kan imidlertid ikke delegeres for noen datakilder.  Hvis delegering ikke støttes, hentes bare den første delen av dataene, og deretter brukes funksjonen lokalt.  Resultatet kan ikke representere den fullstendige historikken.  En blå prikk vises i redigeringsmodus for å minne deg på denne begrensningen, og for å foreslå at du bytter til delegerbare alternativer der det er mulig. Se [oversikten over delegering](../delegation-overview.md) for mer informasjon.

## <a name="syntax"></a>Syntaks
**Average**( *NumericalFormula1*, [ *NumericalFormula2*, ... ] )<br>**Max**( *NumericalFormula1*, [ *NumericalFormula2*, ... ] )<br>**Min**( *NumericalFormula1*, [ *NumericalFormula2*, ... ] )<br>**Sum**( *NumericalFormula1*, [ *NumericalFormula2*, ... ] )<br>**StdevP**( *NumericalFormula1*, [ *NumericalFormula2*, ... ] )<br>**VarP**( *NumericalFormula1*, [ *NumericalFormula2*, ... ] )

* *NumericalFormula* – obligatorisk.  Numeriske verdier funksjonen skal arbeide med.

**Average**( *Table*, *NumericalFormula* )<br>**Max**( *Table*, *NumericalFormula* )<br>**Min**( *Table*, *NumericalFormula* )<br>**Sum**( *Table*, *NumericalFormula* )<br>**StdevP**( *Table*, *NumericalFormula* )<br>**VarP**( *Table*, *NumericalFormula* )

* *Table* – obligatorisk.  Tabellen funksjonen skal arbeide med.
* *NumericalFormula* – obligatorisk. Formelen som skal evalueres for hver post. Resultatet av denne formelen brukes til aggregasjonen. Du kan bruke kolonnene i tabellen i formelen.

## <a name="examples"></a>Eksempler
### <a name="step-by-step"></a>Trinn for trinn
La oss anta at du har en [datakilde](../working-with-data-sources.md) kalt **Sales**, som inneholder en **CostPerUnit**-kolonne og en **UnitsSold**-kolonne, og at du angir **[Text](../controls/properties-core.md)**-egenskapen til en etikett som denne funksjonen:<br>
**Sum(Sales, CostPerUnit * UnitsSold)**

Etiketten vil vise totalt salg ved å multiplisere verdiene i disse kolonnene for hver post og deretter legge resultatene fra alle postene sammen:<br>![Å beregne totalt salg fra solgte enheter og kostnad per enhet](./media/function-aggregates/total-sales.png)

La oss som et annet eksempel anta at du har glidebrytere med navnene **Slider1**, **Slider2** og **Slider3** og en etikett med **[Text](../controls/properties-core.md)**-egenskapen angitt som denne formelen:<br>
**Sum(Slider1.Value, Slider2.Value, Slider3.Value)**

Etiketten viser summen av alle verdiene som ble angitt for glidebryterne.

