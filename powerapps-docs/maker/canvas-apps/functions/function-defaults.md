---
title: Defaults-funksjonen | Microsoft Docs
description: Referanseinformasjon, inkludert syntaks og eksempler for Defaults-funksjonen i PowerApps
services: ''
documentationcenter: na
author: gregli-msft
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: reference
ms.component: canvas
ms.date: 11/01/2015
ms.author: gregli
ms.openlocfilehash: b62b2b8575d1ff0e5a55a97db6e6650af5a593c1
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/04/2018
ms.locfileid: "31825813"
---
# <a name="defaults-function-in-powerapps"></a>Defaults-funksjonen i PowerApps
Returnerer standardverdiene til en [datakilde](../working-with-data-sources.md).  

## <a name="description"></a>Beskrivelse
Bruk **Defaults**-funksjonen til å forhåndsutfylle et skjema for dataregistrering, noe som gjør det enklere å fylle ut.

Denne funksjonen returnerer en [post](../working-with-tables.md#records) som inneholder standardverdiene til datakilden.  Hvis [kolonnen](../working-with-tables.md#columns) i datakilden ikke har en standardverdi, vil posten ikke inneholde denne egenskapen.

Det varierer hvor mye standardinformasjon datakildene leverer, og det kan forekomme at de ikke leverer noe.  Når du arbeider med en [samling](../working-with-data-sources.md#collections) eller en annen datakilde som ikke støtter standardverdier, returnerer **Defaults**-funksjonen en [tom](function-isblank-isempty.md) post.

Du kan kombinere **Defaults**-funksjonen med **[Patch](function-patch.md)**-funksjonen for å [opprette en post](../working-with-data-sources.md).

## <a name="syntax"></a>Syntaks
**Defaults**( *DataSource* )

* *DataSource* – obligatorisk. Datakilden som du ønsker standardverdiene til.

## <a name="examples"></a>Eksempler
| Formel | Beskrivelse | Resultat |
| --- | --- | --- |
| **Defaults(&nbsp;Scores&nbsp;)** |Returnerer standardverdiene til en **datakilde**. |**{ Score: 0 }** |

