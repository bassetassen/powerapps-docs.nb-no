---
title: Revert-funksjonen | Microsoft Docs
description: Referanseinformasjon for Revert-funksjonen i PowerApps, inkludert syntaks og eksempel
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
ms.openlocfilehash: 08cb0690904a4b63645828678232769b66a439a1
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/04/2018
ms.locfileid: "31828222"
---
# <a name="revert-function-in-powerapps"></a>Revert-funksjonen i PowerApps
Oppdaterer og fjerner feil for [postene](../working-with-tables.md#records) til en [datakilde](../working-with-data-sources.md).

## <a name="description"></a>Beskrivelse
**Revert**-funksjonen oppdaterer hele datakilden eller én enkelt post i datakilden. Du får se endringer utført av andre brukere.

For postene som tilbakestilles, fjerner **Revert** også eventuelle feil fra [tabellen](../working-with-tables.md) som **[Errors](function-errors.md)**-funksjonen returnerte.

Hvis **[Errors](function-errors.md)**-funksjonen rapporterer en konflikt etter en **[Patch](function-patch.md)** eller en annen dataoperasjonen, kan du bruke **Revert** på posten for å starte med versjonen som gir konflikt gjøre endringen på nytt.

**Revert** har ingen returverdi. Du kan bare bruke dem i [formler for virkemåte](../working-with-formulas-in-depth.md).

## <a name="syntax"></a>Syntaks
**Revert**( *DataSource* [, *Record* ] )

* *DataSource* – obligatorisk. Datakilden som du vil gjenopprette.
* *Post* – valgfritt.  Posten du vil gjenopprette.  Hvis du ikke angir en post, gjenopprettes hele datakilden.

## <a name="example"></a>Eksempel
I dette eksemplet skal du gjenopprette datakilden med navnet **IceCream**, som starter med dataene i denne tabellen:

![](media/function-revert/icecream.png)

En bruker på en annen enhet endrer **Quantity**-egenskapen til **Strawberry**-posten til **400**.  Omtrent samtidig endrer du den samme egenskapen til den samme posten til **500** uten å vite om den andre endringen.

Du bruker **[Patch](function-patch.md)**-funksjonen til å oppdatere posten:<br>
**Patch( IceCream, First( Filter( IceCream, Flavor = "Strawberry" ) ), { Quantity: 500 } )**

Du sjekker **[Feil](function-errors.md)**-tabellen og finner en feil:

| Post | [Kolonne](../working-with-tables.md#columns) | Melding | Feil |
| --- | --- | --- | --- |
| **{ ID: 1, Flavor: "Strawberry", Quantity: 300 }** |*tom* |**«The record you are trying to modify has been modified by another user.  Please revert the record and try again.»** |**ErrorKind.Conflict** |

Basert på **Feil**-kolonnen har du en **Last inn på nytt**-knapp som har **[OnSelect](../controls/properties-core.md)** -egenskapen angitt som denne formelen:<br>
**Revert( IceCream, First( Filter( IceCream, Flavor = "Strawberry" ) ) )**

Når du har valgt **Last inn på nytt**-knappen, er **[Feil](function-errors.md)**-tabellen [tom](function-isblank-isempty.md) og den nye verdien for **Strawberry** har blitt lastet:

![](media/function-revert/icecream-after.png)

Du gjør endringen på nytt oppå den forrige endringen, og endringen lykkes fordi konflikten har blitt løst.

![](media/function-revert/icecream-success.png)

