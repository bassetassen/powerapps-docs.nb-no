---
title: Funksjonen Refresh | Microsoft Docs
description: Referanseinformasjon for funksjonen Refresh i PowerApps, inkludert syntaks og eksempel
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 10/21/2015
ms.author: gregli
ms.openlocfilehash: aad4f24c692053cf450104e22bf039fc8dbe32d0
ms.sourcegitcommit: dfa0e1a7981814e15e6ca4720e2a5f930e859db1
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 07/13/2018
ms.locfileid: "39015339"
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

