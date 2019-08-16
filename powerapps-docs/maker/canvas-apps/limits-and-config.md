---
title: Systemkrav, grenser og konfigurasjonsverdier for lerretsapper | Microsoft Docs
description: Systemkrav, grenser og konfigurasjonsverdier for lerretsapper som er bygget i PowerApps
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 03/07/2018
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 03c520d1cdf8655e93b1f5b74d687cd0abfa533f
ms.sourcegitcommit: 94ec67b283b9b03aa24cdc0ab43dd448b11b0547
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/16/2019
ms.locfileid: "69529791"
---
# <a name="system-requirements-limits-and-configuration-values-for-canvas-apps"></a>Systemkrav, grenser og konfigurasjonsverdier for lerretsapper
Dette emnet inneholder krav til enhetsplattform og nettleser samt grenser og konfigurasjonsverdier for PowerApps.

## <a name="supported-platforms-for-running-canvas-apps-using-the-powerapps-app"></a>Støttede plattformer for å kjøre lerretsapper ved hjelp av PowerApps-appen

| **Minimumskrav** | **Anbefalt** |
| --- | --- |
| iOS 9.3 eller senere |iOS 10 eller senere med minst 2GB RAM |
| Android 5 eller senere |Android 7 eller senere med minst 4GB RAM |
| Windows 8.1 eller senere (bare PC) |Windows 10 Fall Creators Update med minst 8 GB RAM)|

## <a name="supported-browsers-for-running-canvas-apps"></a>Støttede nettlesere for å kjøre lerretsapper

| **Nettleser** | **Operativsystem** |
| --- | --- |
| Google Chrome (siste versjon)<br>(anbefalt) |Windows 7 SP1, 8.1 og 10 <br>Android 5 eller senere <br>iOS 8 eller senere<br>macOS |
| Microsoft Edge (siste versjon)<br>(anbefalt) |Windows 10 |
| Microsoft Internet Explorer 11 (med kompatibilitetsmodus for visning av) |Windows 7 SP1, 8.1 og 10 |
| Mozilla Firefox (siste versjon) |Windows 7 SP1, 8.1 og 10 <br> Android 5 eller senere <br>iOS 8 eller senere <br>macOS |
| Apple Safari (siste versjon) |iOS 8 eller senere <br>macOS |

## <a name="supported-browsers-for-powerapps-studio"></a>Nettlesere som støttes for PowerApps Studio

| **Nettleser** | **Operativsystem** |
| --- | --- |
| Google Chrome (siste versjon)<br>(anbefalt) |Windows 7 SP1, 8.1 og 10 <br>macOS |
| Microsoft Edge (siste versjon)<br>(anbefalt) |Windows 10 |
| Microsoft Internet Explorer 11 (med kompatibilitetsmodus for visning av) |Windows 7 SP1, 8.1 og 10 |

## <a name="request-limits"></a>Be om grenser
Disse begrensningene gjelder for hver enkelt utgående forespørsel:

| navn | Begrenser |
| --- | --- |
| Tidsavbrudd |180 sekunder |
| Nye tilkoblingsforsøk |4 |

> [!NOTE]
> Prøv på nytt-verdien kan variere. Ved visse feil er det ikke nødvendig å prøve på nytt.

## <a name="ip-addresses"></a>IP-adresser
Forespørsler fra PowerApps bruker IP-adresser som avhenger av området for [miljøet](../../administrator/environments-overview.md) som appen er i. Vi kunngjør ikke fullstendig kvalifiserte domenenavn som er tilgjengelige for PowerApps-scenarioer.

Samtaler fra en API som er koblet til via en app (for eksempel SQL-API-en, eller SharePoint-API-en), kommer fra IP-adressen angitt senere i dette emnet.

Du bør bruke disse adressene hvis du for eksempel må hviteliste IP-adresser for en Azure SQL-database.

> [!IMPORTANT]
>   Hvis du har eksisterende konfigurasjoner, kan du oppdatere dem så snart som mulig før 30. september 2018, slik at de inkluderer og samsvarer med IP-adresser i denne listen for områdene der PowerApps-apper finnes.

| /Regionkode | Utgående IP |
| --- | --- |
| Asia | 13.75.36.64 - 13.75.36.79, 13.67.8.240 - 13.67.8.255, 52.175.23.169, 52.187.68.19 |
| Norge  | 13.70.72.192 - 13.70.72.207, 13.72.243.10, 13.77.50.240 - 13.77.50.255, 13.70.136.174 |
| Brasil | 191.233.203.192 - 191.233.203.207, 104.214.19.48 - 104.214.19.63, 13.65.86.57, 104.41.59.51 |
| Canada | 13.71.170.208 - 13.71.170.223, 13.71.170.224 - 13.71.170.239, 52.237.24.126, 40.69.106.240 - 40.69.106.255, 52.242.35.152|
| Europa | 13.69.227.208 - 13.69.227.223, 52.178.150.68, 13.69.64.208 - 13.69.64.223, 52.174.88.118, 137.117.161.181|
| India  | 104.211.81.192 - 104.211.81.207, 52.172.211.12, 40.78.194.240 - 40.78.194.255, 13.71.125.22, 104.211.146.224 - 104.211.146.239, 104.211.189.218 |
| Japan | 13.78.108.0 - 13.78.108.15, 13.71.153.19, 40.74.100.224 - 40.74.100.239, 104.215.61.248 |
| Sør-Amerika | 191.233.203.192 - 191.233.203.207, 104.214.19.48 - 104.214.19.63, 13.65.86.57, 104.41.59.51 |
| Storbritannia | 51.140.148.0 - 51.140.148.15, 51.140.80.51, 51.140.211.0 - 51.140.211.15, 51.141.47.105 |
| USA | 13.89.171.80 - 13.89.171.95, 52.173.245.164, 40.71.11.80 - 40.71.11.95, 40.71.249.205, 40.70.146.208 - 40.70.146.223, 52.232.188.154, 52.162.107.160 - 52.162.107.175, 52.162.242.161, 40.112.243.160 - 40.112.243.175, 104.42.122.49 |
| USA (tidlig tilgang)  | 13.71.195.32 - 13.71.195.47, 52.161.102.22, 13.66.140.128 - 13.66.140.143, 52.183.78.157 |

## <a name="required-services"></a>Nødvendige tjenester
Denne listen identifiserer alle tjenester som PowerApps Studio kommuniserer med, og deres bruksområder. Nettverket må **ikke** blokkere disse tjenestene.

| Domene(r) | Protokollen | Bruker |
| --- | --- | --- |
| management.azure.com |https |RP |
| msmanaged-na.azure-apim.net |https |Kjøretiden for koblinger/API-er |
| login.microsoft.com<br>login.windows.net<br>login.microsoftonline.com<br>secure.aadcdn.microsoftonline-p.com |https |ADAL |
| graph.microsoft.com<br>graph.windows.net |https |Azure Graph – for å få bruker informasjon (f.eks. profil bilde) |
| gallery.azure.com |https |Eksempel og mal-apper |
| \*. azure-apim.net |https |API-huber – forskjellige underdomener for hver nasjonale innstilling |
| \*. powerapps.com |https | create.powerapps.com, make.powerapps.com, content.powerapps.com og web.powerapps.com |
| \*. azureedge.net |https | create.powerapps.com, make.powerapps.com, content.powerapps.com og web.powerapps.com |
| \*. blob.core.windows.net |https | Blob-lagring |
| \*. flow.microsoft.com | https | create.powerapps.com, make.powerapps.com, content.powerapps.com og web.powerapps.com |
| vortex.data.microsoft.com |https |Telemetri |
| verten | https | PowerApps Mobile

> [!NOTE]
> Hvis du bruker et virtuelt privat nettverk, må det være konfigurert for å utelate localhost fra tunnelering for PowerApps Mobile.

## <a name="size-limits"></a>Størrelses grenser

Du kan finne informasjon om størrelses grenser for tekst, hyperkoblinger, bilder og medier i [data typer](functions/data-types.md#text-hyperlink-image-and-media).
