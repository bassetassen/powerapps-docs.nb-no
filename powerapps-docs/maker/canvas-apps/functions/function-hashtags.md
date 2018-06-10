---
title: HashTags-funksjonen | Microsoft Docs
description: Referanseinformasjon for HashTags-funksjonen i PowerApps, inkludert syntaks og eksempler
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
ms.date: 11/07/2015
ms.author: gregli
ms.openlocfilehash: b2f79c55724d9dc0bc9cfaf9e2e462c646cddb85
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/22/2018
ms.locfileid: "30995822"
---
# <a name="hashtags-function-in-powerapps"></a>HashTags-funksjonen i PowerApps
Henter ut emneknaggene (#strenger) fra en streng.

## <a name="description"></a>Beskrivelse
**HashTags**-funksjonen skanner en streng etter emneknagger. Emneknaggene starter med et nummertegn (#), etterfulgt av en kombinasjon av:

* store og små bokstaver
* tall
* understrekingstegn
* valutasymboler (for eksempel $)

**HashTags** returnerer en [tabell](../working-with-tables.md) med én kolonne som inneholder emneknaggene i strengen.  Hvis strengen ikke inneholder noen emneknagger, returnerer funksjonen en tabell med én kolonne som er [tom](function-isblank-isempty.md).

## <a name="syntax"></a>Syntaks
**HashTags**( *String* )

* *String* – obligatorisk.  Streng som du vil skanne etter emneknagger i.

## <a name="examples"></a>Eksempler
### <a name="step-by-step"></a>Trinn for trinn
1. Legg til en **[Tekstinndata](../controls/control-text-input.md)**-kontroll, gi den navnet **Tweet**, og skriv inn denne setningen:
   
    **This #app is #AMAZING and can #coUnt123 or #123abc but not #1-23 or #$\*(#@")**
2. Legg til et loddrett egendefinert galleri, og angi **[Elementer](../controls/properties-core.md)**-egenskapen som denne funksjonen:
   
    **HashTags(Tweet.Text)**
3. Legg til en **[Etikett](../controls/control-text-box.md)**-kontroll i malgalleriet.
   
    Galleriet viser disse emneknaggene:
   
   * **\#app**
   * **\#AMAZING**
   * **\#coUnt123**
   * **\#123abc**
   * **\#1**

