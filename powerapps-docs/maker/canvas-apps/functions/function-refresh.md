---
title: Funksjonen Refresh | Microsoft Docs
description: Referanseinformasjon for funksjonen Refresh i PowerApps, inkludert syntaks og eksempel
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
ms.date: 10/21/2015
ms.author: gregli
ms.openlocfilehash: 631b0c8fbfc98d73cf1d944c2a0f3933f8f10c11
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/22/2018
ms.locfileid: "30995857"
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

