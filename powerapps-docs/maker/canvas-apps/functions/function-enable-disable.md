---
title: Funksjonene Enable og Disable| Microsoft Docs
description: Referanseinformasjon for funksjonene Enable og Disable i PowerApps, inkludert syntaks og eksempler
documentationcenter: na
author: gregli-msft
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: reference
ms.component: canvas
ms.date: 11/07/2015
ms.author: gregli
ms.openlocfilehash: b35d819730715917f3092ca803b9a38ea9173edc
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/04/2018
ms.locfileid: "31825123"
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

