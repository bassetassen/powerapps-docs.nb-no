---
title: Remove- og RemoveIf-funksjonene | Microsoft Docs
description: Referanseinformasjon, inkludert syntaks og eksempler for funksjonene Remove og RemoveIf i PowerApps
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 10/21/2015
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 57432024254598ff8216d6fefafa5354844bb7a4
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/07/2019
ms.locfileid: "71984298"
---
# <a name="remove-and-removeif-functions-in-powerapps"></a>Remove- og RemoveIf-funksjonene i PowerApps
Fjerner [poster](../working-with-tables.md#records) fra en [datakilde](../working-with-data-sources.md).

## <a name="description"></a>Beskrivelse
### <a name="remove-function"></a>Remove-funksjonen
Bruk **Remove**-funksjonen til å fjerne en bestemt post eller poster fra en datakilde.  

Hvis du vil fjerne en [samling](../working-with-data-sources.md#collections), må hele posten gi treff. Du kan bruke **All**-argumentet for å fjerne alle kopier av en post. Ellers fjernes bare én kopi av posten.

### <a name="removeif-function"></a>RemoveIf-funksjonen
Bruk **RemoveIf**-funksjonen til å fjerne en post eller poster basert på en betingelse eller et sett med betingelser. Betingelsen kan være enhver formel som gir **sann** eller **usann** som resultat og kan referere til [kolonner](../working-with-tables.md#columns) i datakilden etter navn. Hver betingelse evalueres separat for hver post, og posten fjernes hvis alle betingelsene gir resultatet **sann**.

Både **Remove** og **RemoveIf** returnerer den endrede datakilden som en [tabell](../working-with-tables.md). Du kan kun bruke begge funksjonene i [formler for virkemåte](../working-with-formulas-in-depth.md).

Du kan også bruke **[Clear](function-clear-collect-clearcollect.md)** -funksjonen til å fjerne alle postene i en datakilde.

### <a name="delegation"></a>Delegering
[!INCLUDE [delegation-no](../../../includes/delegation-no.md)]

## <a name="syntax"></a>Syntaks
**Remove**( *DataSource*, *Record1* [, *Record2*, ... ] [, **All** ] )

* *DataSource* – obligatorisk. Datakilden som inneholder posten eller postene som du vil fjerne.
* *Record(s)* – obligatorisk. Posten eller postene du vil fjerne.
* **All** – valgfritt. I en samling kan den samme posten forekomme mer enn én gang.  Du kan angi argumentet **All** for å fjerne alle kopier av posten.

**Remove**( *DataSource*, *Table* [, **All** ] )

* *DataSource* – obligatorisk. Datakilden som inneholder postene som du vil fjerne.
* *Table* – obligatorisk. En tabell med poster som du vil fjerne.
* **All** – valgfritt. I en samling kan den samme posten forekomme mer enn én gang.  Du kan angi argumentet **All** for å fjerne alle kopier av posten.

**RemoveIf**( *DataSource*, *Condition* [, ... ] )

* *DataSource* – obligatorisk. Datakilden som inneholder posten eller postene som du vil fjerne.
* *Condition(s)* – obligatorisk. En formel som gir resultatet **sann** for posten eller postene som du vil endre.  Du kan bruke kolonnenavnene fra *DataSource* i formelen.  Hvis du angir flere *Conditions*, må alle gi resultatet **sann** for posten eller postene som skal fjernes.

## <a name="examples"></a>Eksempler
I disse eksemplene fjerner du poster i en datakilde som heter **IceCream** og som starter med dataene i denne tabellen:

![](media/function-remove-removeif/icecream.png)

| Formel | Beskrivelse | Resultat |
| --- | --- | --- |
| **Remove(&nbsp;IceCream,<br>First(&nbsp;Filter(&nbsp;IceCream,&nbsp;Flavor="Chocolate"&nbsp;)&nbsp;) )** |Fjerner **Chocolate**-posten fra datakilden. |<style> img { max-width: none } </style> ![](media/function-remove-removeif/icecream-no-chocolate.png)<br><br>Datakilden **IceCream** har blitt endret. |
| **Remove(&nbsp;IceCream,<br>First(&nbsp;Filter(&nbsp;IceCream,&nbsp;Flavor="Chocolate"&nbsp;)&nbsp;) First(&nbsp;Filter(&nbsp;IceCream,&nbsp;Flavor="Strawberry"&nbsp;)&nbsp;) )** |Fjerner to poster fra datakilden. |![](media/function-remove-removeif/icecream-only-vanilla.png)<br><br>Datakilden **IceCream** har blitt endret. |
| **RemoveIf(&nbsp;IceCream, Quantity&nbsp;>&nbsp;150 )** |Fjerner poster hvor **Quantity** er større enn **150**. |![](media/function-remove-removeif/icecream-only-chocolate.png)<br><br>Datakilden **IceCream** har blitt endret. |
| **RemoveIf(&nbsp;IceCream, Quantity&nbsp;>&nbsp;150, Left(&nbsp;Flavor,&nbsp;1&nbsp;) = "S" )** |Fjerner poster som har en **Quantity** som er større enn 150 og en **Flavor** som begynner på **S**. |![](media/function-remove-removeif/icecream-no-strawberry.png)<br><br><br>Datakilden **IceCream** har blitt endret. |
| **RemoveIf(&nbsp;IceCream, true )** |Fjerner alle postene fra datakilden. |![](media/function-remove-removeif/icecream-empty.png)<br><br>Datakilden **IceCream** har blitt endret. |

### <a name="step-by-step"></a>Trinn for trinn
1. Importer eller opprett en samling med navnet **Inventory**, og vis den i et galleri, som beskrevet i [Vis data i et galleri](../show-images-text-gallery-sort-filter.md).
2. I galleriet kan du angi **[OnSelect](../controls/properties-core.md)** -egenskapen til bildet som dette uttrykket:<br>**Remove(Inventory, ThisItem)**
3. Trykk på F5, og velg et bilde i galleriet.<br>Elementet fjernes fra galleriet og samlingen.

