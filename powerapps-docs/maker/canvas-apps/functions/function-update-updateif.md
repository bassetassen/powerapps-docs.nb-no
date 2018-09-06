---
title: Update- og UpdateIf-funksjonene | Microsoft Docs
description: Referanseinformasjon, inkludert syntaks og eksempler for Update- og UpdateIf-funksjonene i PowerApps
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 10/21/2015
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: d74f05c87cd5b9a3e7aed7891c6d2aaa54adfd1a
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/24/2018
ms.locfileid: "42834312"
---
# <a name="update-and-updateif-functions-in-powerapps"></a>Update- og UpdateIf-funksjonene i PowerApps
Oppdaterer [poster](../working-with-tables.md#records) i en [datakilde](../working-with-data-sources.md).

## <a name="description"></a>Beskrivelse
### <a name="update-function"></a>Update-funksjonen
Bruk **Update**-funksjonen til å erstatte en hel post i en datakilde. Funksjonene **UpdateIf** og **[Patch](function-patch.md)** endrer én eller flere verdier i en post, uten å røre de andre verdiene.

Hvis du vil oppdatere en [samling](../working-with-data-sources.md#collections), må hele posten gi treff. Samlinger tillater dupliserte poster, slik at flere poster kan gi treff. Du kan bruke **All**-argumentet for å oppdatere alle kopiene av en post. Ellers oppdateres bare en kopi av posten.

Hvis datakilden genererer en kolonnes verdi automatisk, må verdien til denne [kolonnen](../working-with-tables.md#columns) bekreftes.

### <a name="updateif-function"></a>UpdateIf-funksjonen
Bruk **UpdateIf**-funksjonen til å endre en eller flere verdier i en eller flere poster som oppfyller en eller flere betingelser. Betingelsen kan være enhver formel som gir **sann** eller **usann** som resultat og kan referere til kolonner i datakilden etter navn. Funksjonen evaluerer betingelsene for hver post og endrer alle poster hvor resultatet er **sann**.  

Bruk en endringspost som inneholder nye egenskapsverdier til å angi en endring. Hvis du angir denne endringsposten innebygd i klammeparenteser, kan egenskapsformlene referere til egenskaper til posten som blir endret. Du kan bruke denne virkemåten til å endre poster basert på en formel.

På samme måte som med **UpdateIf**, kan du også bruke **[Patch](function-patch.md)**-funksjonen til å endre bestemte kolonner i en post uten å påvirke andre kolonner.

Både **Update** og **UpdateIf** returnerer den endrede datakilden som en [tabell](../working-with-tables.md). Du må bruke en av funksjonene i en [formel for virkemåte](../working-with-formulas-in-depth.md).

### <a name="delegation"></a>Delegering
[!INCLUDE [delegation-no](../../../includes/delegation-no.md)]

## <a name="syntax"></a>Syntaks
**Update**( *DataSource*, *OldRecord*, *NewRecord* [, **All** ] )

* *DataSource* – obligatorisk. Datakilden som inneholder posten du vil erstatte.
* *OldRecord* – obligatorisk. Posten som du vil erstatte.
* *NewRecord* – obligatorisk. Posten som du vil erstatte den med. Dette er ikke en endringspost. Hele posten erstattes, og manglende egenskaper vil inneholde *tom*.
* **All** – valgfritt. I en samling kan den samme posten forekomme mer enn én gang. Angi argumentet **All** for å fjerne alle kopier av posten.

**UpdateIf**( *DataSource*, *Condition1*, *ChangeRecord1* [, *Condition2*, *ChangeRecord2*, ... ] )

* *DataSource* – obligatorisk. Datakilden som inneholder posten eller postene som du vil endre.
* *Condition(s)* – obligatorisk. En formel som gir resultatet **sann** for posten eller postene som du vil endre.  Du kan bruke kolonnenavnene fra *DataSource* i formelen.  
* *ChangeRecord(s)* – obligatorisk.  Angi en endringspost med nye egenskapsverdier som skal anvendes på postene i *DataSource* som oppfyller hver tilhørende betingelse. Hvis du angir posten innebygd i klammeparenteser, kan du bruke egenskapsverdiene til den eksisterende posten i egenskapsformlene.

## <a name="examples"></a>Eksempler
I disse eksemplene erstatter eller endrer du poster i en datakilde som heter **IceCream** og som starter med dataene i denne tabellen:

![](media/function-update-updateif/icecream.png)

| Formel | Beskrivelse | Resultat |
| --- | --- | --- |
| **Update(&nbsp;IceCream,<br>First(&nbsp;Filter(&nbsp;IceCream,&nbsp;Flavor="Chocolate"&nbsp;)&nbsp;), {&nbsp;ID:&nbsp;1,&nbsp;Flavor:&nbsp;"Mint&nbsp;Chocolate",&nbsp;Quantity:150&nbsp;} )** |Erstatter en post fra datakilden. |<style> img { max-width: none } </style> ![](media/function-update-updateif/icecream-mint.png)<br><br>Datakilden **IceCream** har blitt endret. |
| **UpdateIf(&nbsp;IceCream, Quantity > 175, {&nbsp;Quantity:&nbsp;Quantity&nbsp;+&nbsp;10&nbsp;} )** |Endrer poster hvor **Quantity** er større enn **150**.  **Quantity**-feltet økes med 10, og ingen andre felter blir endret. |![](media/function-update-updateif/icecream-mint-plus10.png)<br><br>Datakilden **IceCream** har blitt endret. |
| **Update(&nbsp;IceCream,<br>First(&nbsp;Filter(&nbsp;IceCream, Flavor="Strawberry"&nbsp;)&nbsp;),<br>{&nbsp;ID:&nbsp;3, Flavor:&nbsp;"Strawberry Swirl"} )** |Erstatter en post fra datakilden. Egenskapen **Quantity** er ikke angitt i erstatningsposten. Denne egenskapen vil derfor være *tom* i resultatet. |![](media/function-update-updateif/icecream-mint-swirl.png)<br><br>Datakilden **IceCream** har blitt endret. |
| **UpdateIf(&nbsp;IceCream, true, {&nbsp;Quantity:&nbsp;0&nbsp;} )** |Angir verdien 0 for **Quantity**-egenskapen til alle postene i datakilden. |![ ](./media/function-update-updateif/icecream-mint-zero.png)<br> <br>Datakilden **IceCream** har blitt endret. |

### <a name="step-by-step"></a>Trinn for trinn
1. Importer eller opprett en samling med navnet **Inventory**, og vis den i et galleri, som beskrevet i [Vis data i et galleri](../show-images-text-gallery-sort-filter.md).
2. Gi galleriet navnet **ProductGallery**.
3. Legg til en glidebryter med navnet **UnitsSold**, og angi glidebryterens **Max**-egenskap som dette uttrykket:<br>**ProductGallery.Selected.UnitsInStock**
4. Legg til en knapp, og angi knappens **[OnSelect](../controls/properties-core.md)**-egenskapen til denne formelen:<br>**UpdateIf(Inventory, ProductName = ProductGallery.Selected.ProductName, {UnitsInStock:UnitsInStock-UnitsSold.Value})**
5. Trykk på F5, velg et produkt i galleriet, angi en verdi med glidebryteren, og velg deretter knappen.
   
    Antall enheter på lager for produktet du anga reduseres med beløpet du anga.

