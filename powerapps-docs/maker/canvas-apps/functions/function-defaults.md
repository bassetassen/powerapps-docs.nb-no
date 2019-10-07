---
title: Defaults-funksjonen | Microsoft Docs
description: Referanseinformasjon, inkludert syntaks og eksempler for Defaults-funksjonen i PowerApps
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 11/01/2015
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: b51d956f2c188e0b877530b28dec933d42c905a6
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/07/2019
ms.locfileid: "71992844"
---
# <a name="defaults-function-in-powerapps"></a>Defaults-funksjonen i PowerApps
Returnerer standardverdiene til en [datakilde](../working-with-data-sources.md).  

## <a name="description"></a>Beskrivelse
Bruk **Defaults**-funksjonen til å forhåndsutfylle et skjema for dataregistrering, noe som gjør det enklere å fylle ut.

Denne funksjonen returnerer en [post](../working-with-tables.md#records) som inneholder standardverdiene til datakilden.  Hvis [kolonnen](../working-with-tables.md#columns) i datakilden ikke har en standardverdi, vil posten ikke inneholde denne egenskapen.

Det varierer hvor mye standardinformasjon datakildene leverer, og det kan forekomme at de ikke leverer noe.  Når du arbeider med en [samling](../working-with-data-sources.md#collections) eller en annen datakilde som ikke støtter standardverdier, returnerer **Defaults**-funksjonen en [tom](function-isblank-isempty.md) post.

Du kan kombinere **Defaults**-funksjonen med **[Patch](function-patch.md)** -funksjonen for å [opprette en post](../working-with-data-sources.md).

## <a name="syntax"></a>Syntaks
**Defaults**( *DataSource* )

* *DataSource* – obligatorisk. Datakilden som du ønsker standardverdiene til.

## <a name="examples"></a>Eksempler

| Formel | Beskrivelse | Resultat |
| --- | --- | --- |
| **Defaults(&nbsp;Scores&nbsp;)** |Returnerer standardverdiene til en **datakilde**. |**{score: 0}** |

