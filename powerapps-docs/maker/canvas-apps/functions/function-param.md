---
title: Last ned-, Start- og Param-funksjoner | Microsoft Docs
description: Referanseinformasjon, inkludert syntaks og eksempler, for funksjonene Last ned, Start og Param i PowerApps
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
ms.date: 11/07/2015
ms.author: gregli
ms.openlocfilehash: 4ed646431263e96a079483bc514c8154b6d9b653
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/22/2018
ms.locfileid: "30995837"
---
# <a name="download-launch-and-param-functions-in-powerapps"></a>Last ned-, Start- og Param-funksjoner i PowerApps
Laster ned eller åpner en nettside eller en app med parametere.  

## <a name="description"></a>Beskrivelse
**Download**-funksjonen laster ned en fil fra nettet til den lokale enheten.  Brukeren blir bedt om å angi en plassering til å lagre filen.  **Download** returnerer plasseringen der filen ble lagret lokalt som en streng.  

**Launch**-funksjonen åpner en nettside eller en app.  Denne funksjonen kan alternativt også sende parametere til appen.  

**Param**-funksjonen henter et parameter som ble sendt til appen når den ble startet.  Hvis det navngitte parameteret ikke ble sendt, returnerer **Param** med *tom*.

## <a name="syntax"></a>Syntaks
**Last ned** ( *Adresse* )

* *Adresse* – obligatorisk.  Adressen til en nettressurs som skal lastes ned.

**Start**( *Adresse* [, *ParameterName1*, *ParameterValue1*,...])

* *Adresse* – obligatorisk.  Adressen til en nettside eller ID-en til en app som skal startes.
* *Parameternavn* – valgfritt.  Parameternavn.
* *Parameterverdi(er)* – valgfritt.  Tilsvarende parameterverdier som skal sendes til appen eller nettsiden.

**Param**( *ParameterName* )

* *ParameterName* – nødvendig.  Navnet på parameteret som er sendt til appen.

