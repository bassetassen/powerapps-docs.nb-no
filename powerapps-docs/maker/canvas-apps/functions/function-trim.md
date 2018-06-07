---
title: Funksjonene Trim og TrimEnds | Microsoft Docs
description: Referanseinformasjon for funksjonene Trim og TrimEnds i PowerApps, inkludert syntaks og et eksempel
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
ms.date: 09/09/2016
ms.author: gregli
ms.openlocfilehash: 7dc9372071b905cf2b95f7355864276d8f344d9c
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/22/2018
ms.locfileid: "30997357"
---
# <a name="trim-and-trimends-functions-in-powerapps"></a>Funksjonene Trim og TrimEnds i PowerApps
Fjerner ekstra mellomrom fra en tekststreng.

## <a name="description"></a>Beskrivelse
**Trimfunksjonen** fjerner alle mellomrom fra en tekststreng bortsett fra enkle mellomrom mellom ord.  

Funksjonen **TrimEnds** fjerner alle mellomrom fra starten og slutten av en tekststreng, men lar mellomrom mellom ord forbli intakt.

Hvis du angir en enkelt tekststreng, vil returverdien for begge funksjonene være strengen der de ekstra mellomrommene er fjernet. Hvis du angir en [enkeltkolonnetabell](../working-with-tables.md) som inneholder strenger, vil returverdien være en enkeltkolonnetabell med trimmede strenger. Hvis du har en flerkolonnetabell, kan du gjøre den om til en enkeltkolonnetabell, som beskrevet i [arbeide med tabeller](../working-with-tables.md).

Ved trimming av mellomrom mellom ord samsvarer **Trim** med funksjonen med samme navn i Microsoft Excel. **TrimEnds** samsvarer imidlertid med programmeringsverktøy som kun trimmer mellomrom fra starten og slutten av hver streng.

## <a name="syntax"></a>Syntaks
**Trim**( *String* )<br>**TrimEnds**( *String* )

* *String* – obligatorisk. Tekststrengen det skal fjernes mellomrom fra.

**Trim**( *SingleColumnTable* )<br>**TrimEnds**( *SingleColumnTable* )

* *SingleColumnTable* – obligatorisk. En enkeltkolonnetabell med strenger som mellomrom skal fjernes fra.

## <a name="example"></a>Eksempel
| Formel | Beskrivelse | Resultat |
| --- | --- | --- |
| **Trim(&nbsp;"&nbsp;&nbsp;&nbsp;Hello&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;World&nbsp;&nbsp;&nbsp;"&nbsp;)** |Fjerner alle mellomrom fra starten og slutten av en streng, og ekstra mellomrom inne i strengen. |"Hello World" |
| **TrimEnds(&nbsp;"&nbsp;&nbsp;&nbsp;Hello&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;World&nbsp;&nbsp;&nbsp;"&nbsp;)** |Fjerner alle mellomrom fra starten og slutten av en streng. |"Hello&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;World" |

Følgende eksempler bruker en enkeltkolonnesamling kalt **Mellomrom**, som inneholder disse strengene:

![](media/function-trim/input-strings.png)

Hvis du vil opprette denne samlingen, angir du **OnSelect**-egenskapen til en **[Knapp](../controls/control-button.md)**-kontroll til denne formelen, åpner Forhåndsvisningsmodus, og deretter klikker eller trykker du på knappen:
<br>**ClearCollect( Spaces, [ "&nbsp;&nbsp;&nbsp;Jane&nbsp;&nbsp;&nbsp;Doe&nbsp;&nbsp;&nbsp;", "&nbsp;&nbsp;&nbsp;&nbsp;Jack&nbsp;&nbsp;&nbsp;and&nbsp;&nbsp;&nbsp;Jill", "Already&nbsp;trimmed", "&nbsp;&nbsp;&nbsp;Venus,&nbsp;&nbsp;&nbsp;Earth,&nbsp;&nbsp;&nbsp;Mars&nbsp;&nbsp;", "Oil&nbsp;and&nbsp;Water&nbsp;&nbsp;&nbsp;" ] )**

| Formel | Beskrivelse | Resultat |
| --- | --- | --- |
| **Trim(&nbsp;Spaces&nbsp;)** |Trimmer alle mellomrom fra starten og slutten av hver streng og ekstra mellomrom inne i hver streng i **Mellomrom**-samlingen. |<style> img { max-width: none } </style> ![](media/function-trim/output-trim.png) |
| **TrimEnds(&nbsp;Spaces&nbsp;)** |Trimmer alle mellomrom fra starten og slutten av hver streng i **Mellomrom**-samlingen. |<style> img { max-width: none } </style> ![](media/function-trim/output-trimends.png) |

> [!NOTE]
> Ekstra mellomrom vises ikke hvis du viser en samling ved å klikke eller trykke på **Samlinger** på **Fil**-menyen. Hvis du vil kontrollere lengden, kan du bruke **[Lengde](function-len.md)**-funksjonen.

