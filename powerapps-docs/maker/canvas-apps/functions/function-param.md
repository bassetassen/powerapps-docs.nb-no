---
title: Download-, Launch- og Param-funksjoner | Microsoft Docs
description: Referanseinformasjon, inkludert syntaks og eksempler, for funksjonene Last ned, Start og Param i PowerApps
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
ms.openlocfilehash: 146372c723df6089890100abd67d1175ba4b4a04
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/04/2018
ms.locfileid: "31828754"
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

