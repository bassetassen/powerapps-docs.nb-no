---
title: Funksjonene Enable og Disable| Microsoft Docs
description: Referanseinformasjon for funksjonene Enable og Disable i PowerApps, inkludert syntaks og eksempler
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 11/07/2015
ms.author: gregli
ms.openlocfilehash: 1b5395459dd5833d054755dadca37bc9b39785c9
ms.sourcegitcommit: dfa0e1a7981814e15e6ca4720e2a5f930e859db1
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 07/13/2018
ms.locfileid: "39019070"
---
# <a name="enable-and-disable-functions-in-powerapps"></a>Funksjonene Enable og Disable i PowerApps
Aktiverer eller deaktiverer et [signal](signals.md).

## <a name="overview"></a>Oversikt
Noen signaler kan endres ofte, og krever at appen beregner på nytt i henhold til dette.  Raske endringer over en lengre periode kan gjøre at batteriet går tomt. Du kan bruke disse funksjonene til å manuelt aktivere eller deaktivere et signal.

Når et signal ikke brukes, blir det automatisk deaktivert.

## <a name="description"></a>Beskrivelse
Funksjonene **Enable** og **Disable** slår signalet henholdsvis på og av.

Disse funksjonene fungerer for øyeblikket kun på **[Plassering](signals.md)**-signalet.

Disse funksjonene har ingen returverdi. Du kan bare bruke dem i [formler for virkemåte](../working-with-formulas-in-depth.md).

## <a name="syntax"></a>Syntaks
**Enable**( *Signal* )<br>**Disable**( *Signal* )

* *Signal* – obligatorisk.  Signalet for å slå av eller på.

