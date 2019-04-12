---
title: Download-, Launch- og Param-funksjoner | Microsoft Docs
description: Referanseinformasjon, inkludert syntaks og eksempler for funksjonene Last ned, start og Param i lerret-apper
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
ms.openlocfilehash: 4a53d8c20bd4b7784cb94daa574682c041f104ea
ms.sourcegitcommit: b316e0eee9946ef09e0512577ce2d11cd27aa864
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/11/2019
ms.locfileid: "59508313"
---
# <a name="download-launch-and-param-functions-in-canvas-apps"></a>Last ned, start og Param-funksjoner i lerret-apper
Laster ned eller åpner en nettside eller en app med parametere.  

## <a name="description"></a>Beskrivelse
**Download**-funksjonen laster ned en fil fra nettet til den lokale enheten. Brukeren blir bedt om å angi en plassering til å lagre filen.  **Download** returnerer plasseringen der filen ble lagret lokalt som en streng.  

**Launch**-funksjonen åpner en nettside eller en app.  Denne funksjonen kan alternativt også sende parametere til appen.

I Internet Explorer og Microsoft Edge, den **Start** -funksjonen åpner en nettstedet eller appen bare hvis sikkerhetsinnstillingene er de samme eller høyere enn for appen som inneholder funksjonen. Hvis for eksempel legger du til den **Start** funksjonen til en app som kjører i den **klarerte områder** sikkerhet sone, må du kontrollere at nettstedet eller appen som du vil at funksjonen til å åpne er i den **klarerte områder** eller **lokalt intranett** sone (ikke i **begrensede områder**). Mer informasjon: [Endre innstillinger for sikkerhet og personvern for Internet Explorer 11](https://support.microsoft.com/en-us/help/17479/windows-internet-explorer-11-change-security-privacy-settings).  

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

