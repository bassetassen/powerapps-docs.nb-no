---
title: ShowError-funksjonen i Microsoft Docs
description: Referanseinformasjon for ShowError-funksjonen i PowerApps, inkludert syntaks og eksempler
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
ms.date: 03/21/2018
ms.author: gregli
ms.openlocfilehash: 7c1d5a8c7b35d316a2720d564977170029e28359
ms.sourcegitcommit: a9d33322228c398d29964429602dc3fe19fa67d2
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/28/2018
ms.locfileid: "30998057"
---
# <a name="showerror-function-in-powerapps"></a>ShowError-funksjonen i PowerApps
Viser en feil til brukeren.

## <a name="description"></a>Beskrivelse
**ShowError**-funksjonen viser en feil til brukeren.  Meldinger vises både når du redigerer appen og når sluttbrukerne bruker appen.

**ShowError** kan bare brukes i [formler for virkemåte](../working-with-formulas-in-depth.md).

**ShowError** returnerer alltid *sann*.

**ShowError** kan pares med [**IfError**](function-iferror.md)-funksjonen for å oppdage og rapportere feil med en feilmelding.

## <a name="syntax"></a>Syntaks
**ShowError**( *Message* )

* *Message* – obligatorisk.  Meldingen som skal vises til brukeren. 

## <a name="examples"></a>Eksempler

### <a name="step-by-step"></a>Trinn for trinn

1. Legg til en **Knapp**-kontroll på skjermen.

2. Angi **OnSelect**-egenskapen for **knappen** til:

    **ShowError( "Hello, World" )**

3. Klikk eller trykk på knappen.  

    Hver gang knappen trykkes, så vises **Hello, World** til brukeren.

    ![Viser Button.OnSelect, kaller ShowError og viser den resulterende Hello, World-meldingen som en rød bannermelding for brukeren, i redigeringsmiljøet](media/function-showerror/hello-world.png)
