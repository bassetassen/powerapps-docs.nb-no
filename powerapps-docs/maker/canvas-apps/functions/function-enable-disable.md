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
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: f3932d21683b83008e95f03ba2aae646d2b8e491
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/24/2018
ms.locfileid: "42836465"
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

