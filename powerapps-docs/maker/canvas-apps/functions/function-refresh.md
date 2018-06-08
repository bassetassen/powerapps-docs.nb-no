---
title: Funksjonen Refresh | Microsoft Docs
description: Referanseinformasjon for funksjonen Refresh i PowerApps, inkludert syntaks og eksempel
documentationcenter: na
author: gregli-msft
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: reference
ms.component: canvas
ms.date: 10/21/2015
ms.author: gregli
ms.openlocfilehash: 9ec2711c4a38f26fec2d44681b2606b4a8ecba29
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/04/2018
ms.locfileid: "31825376"
---
# <a name="refresh-function-in-powerapps"></a>Funksjonen Refresh i PowerApps
Oppdaterer [postene](../working-with-tables.md#records) i en [datakilde](../working-with-data-sources.md).

## <a name="description"></a>Beskrivelse
Funksjonen **Refresh** henter en ny kopi av en datakilde.  Du får se endringer utført av andre brukere.

**Refresh** har ingen returverdi, og du kan kun bruke den i [formler for virkemåte](../working-with-formulas-in-depth.md).

## <a name="syntax"></a>Syntaks
**Refresh**( *DataSource* )

* *DataSource* – obligatorisk. Datakilden som du vil oppdatere.

## <a name="example"></a>Eksempel
I dette eksemplet skal du oppdatere datakilden med navnet **IceCream**, som starter med disse dataene:

![](media/function-refresh/icecream.png)

En bruker på en annen enhet endrer **antallet** i **Jordbær**-posten til **400**.  Denne endringen vises ikke før du utfører denne formelen:

**Refresh( IceCream )**

Etter at formelen utføres, vil gallerier som er knyttet til datakilden **IceCream** vise den oppdaterte verdien for **Jordbær**:

![](media/function-refresh/icecream-after.png)

