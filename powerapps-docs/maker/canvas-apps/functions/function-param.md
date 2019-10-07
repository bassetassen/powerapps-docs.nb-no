---
title: Download-, Launch- og Param-funksjoner | Microsoft Docs
description: Referanse informasjon, inkludert syntaks og eksempler, for funksjonene Last ned, start og param i lerret apper
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 11/07/2015
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: c6fb3c5ef002ed0355cc8061603e4f4b1f438e6e
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/07/2019
ms.locfileid: "71992483"
---
# <a name="download-launch-and-param-functions-in-canvas-apps"></a>Funksjonene Last ned, start og param i lerret-apper
Laster ned eller åpner en nettside eller en app med parametere.  

## <a name="description"></a>Beskrivelse
**Download**-funksjonen laster ned en fil fra nettet til den lokale enheten. Brukeren blir bedt om å angi en plassering til å lagre filen.  **Download** returnerer plasseringen der filen ble lagret lokalt som en streng.  

**Launch**-funksjonen åpner en nettside eller en app.  Denne funksjonen kan alternativt også sende parametere til appen.

I Internet Explorer og Microsoft Edge åpner **Start** funksjonen et nettsted eller en app bare hvis sikkerhets innstillingene er de samme eller høyere enn dem i appen som inneholder funksjonen. Hvis du for eksempel legger til **Start** -funksjonen i en app som kjører i sikkerhets sonen **Klarerte områder** , må du forsikre deg om at Netts IDen eller appen du vil at funksjonen skal åpne, befinner seg i sonen **klarerte nett steder** eller **lokalt intranett** (ikke i  **Begrensede områder**). Mer informasjon: [Endre innstillinger for sikkerhet og person vern for Internet Explorer 11](https://support.microsoft.com/en-us/help/17479/windows-internet-explorer-11-change-security-privacy-settings).  

**Param**-funksjonen henter et parameter som ble sendt til appen når den ble startet. Hvis det navngitte parameteret ikke ble sendt, returnerer **Param** som *tom*.

## <a name="syntax"></a>Syntaks
**Download** ( *adresse* )

* *Adresse* – obligatorisk.  Adressen til en nettressurs som skal lastes ned.

**Launch**( *Adresse* [, *ParameterName1*, *ParameterValue1*,...])

* *Adresse* – obligatorisk.  Adressen til en nettside eller ID-en til en app som skal startes.
* *Parameternavn* – valgfritt.  Parameternavn.
* *Parameterverdi(er)* – valgfritt.  Tilsvarende parameterverdier som skal sendes til appen eller nettsiden.

**Param**( *ParameterName* )

* *ParameterName* – nødvendig.  Navnet på parameteret som er sendt til appen.

