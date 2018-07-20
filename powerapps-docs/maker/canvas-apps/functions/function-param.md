---
title: Download-, Launch- og Param-funksjoner | Microsoft Docs
description: Referanseinformasjon, inkludert syntaks og eksempler, for funksjonene Last ned, Start og Param i PowerApps
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 11/07/2015
ms.author: gregli
ms.openlocfilehash: f2af4fef413aa5502c57e7158d9efdddd36757c9
ms.sourcegitcommit: dfa0e1a7981814e15e6ca4720e2a5f930e859db1
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 07/13/2018
ms.locfileid: "39021876"
---
# <a name="download-launch-and-param-functions-in-powerapps"></a>Download-, Launch- og Param-funksjoner i PowerApps
Laster ned eller åpner en nettside eller en app med parametere.  

## <a name="description"></a>Beskrivelse
**Download**-funksjonen laster ned en fil fra nettet til den lokale enheten.  Brukeren blir bedt om å angi en plassering til å lagre filen.  **Download** returnerer plasseringen der filen ble lagret lokalt som en streng.  

**Launch**-funksjonen åpner en nettside eller en app.  Denne funksjonen kan alternativt også sende parametere til appen.  

**Param**-funksjonen henter et parameter som ble sendt til appen når den ble startet.  Hvis det navngitte parameteret ikke ble sendt, returnerer **Param** som *tom*.

## <a name="syntax"></a>Syntaks
**Download** ( *adresse* )

* *Adresse* – obligatorisk.  Adressen til en nettressurs som skal lastes ned.

**Launch**( *Adresse* [, *ParameterName1*, *ParameterValue1*,...])

* *Adresse* – obligatorisk.  Adressen til en nettside eller ID-en til en app som skal startes.
* *Parameternavn* – valgfritt.  Parameternavn.
* *Parameterverdi(er)* – valgfritt.  Tilsvarende parameterverdier som skal sendes til appen eller nettsiden.

**Param**( *ParameterName* )

* *ParameterName* – nødvendig.  Navnet på parameteret som er sendt til appen.

