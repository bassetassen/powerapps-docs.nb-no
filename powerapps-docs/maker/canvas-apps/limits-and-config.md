---
title: Systemkrav, grenser og konfigurasjonsverdier | Microsoft Docs
description: Systemkrav, grenser og konfigurasjonsverdier for PowerApps
services: ''
suite: PowerApps
documentationcenter: na
author: skjerland
manager: kfile
editor: ''
tags: ''
ms.service: PowerApps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/07/2018
ms.author: sharik
ms.openlocfilehash: 84115ea98ec5d7d0fd60d36fc0cd3cc9196980ff
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/22/2018
ms.locfileid: "30997312"
---
# <a name="system-requirements-limits-and-configuration-values"></a>Systemkrav, grenser og konfigurasjonsverdier
Dette emnet inneholder krav til enhetsplattform og nettleser samt grenser og konfigurasjonsverdier for PowerApps.

## <a name="supported-platforms-for-running-apps-using-the-powerapps-app"></a>Støttede plattformer for å kjøre apper ved hjelp av PowerApps-appen
| **Minimumskrav** | **Anbefalt** |
| --- | --- |
| iOS 9.3 eller senere |iOS 10 eller senere med minst 2GB RAM |
| Android 5 eller senere |Android 7 eller senere med minst 4GB RAM |
| Windows 8.1 eller senere (bare PC) |Windows 10 Fall Creators Update med minst 8 GB RAM)|

## <a name="supported-browsers-for-running-apps"></a>Støttede nettlesere for kjørende apper
| **Nettleser** | **Operativsystem** |
| --- | --- |
| Google Chrome (siste versjon)<br>(anbefalt) |Windows 7 SP1, 8.1 og 10 <br>Android 5 eller senere <br>iOS 8 eller senere<br>macOS |
| Microsoft Edge (siste versjon)<br>(anbefalt) |Windows 10 |
| Microsoft Internet Explorer 11 (med kompatibilitetsmodus for visning av) |Windows 7 SP1, 8.1 og 10 |
| Mozilla Firefox (siste versjon) |Windows 7 SP1, 8.1 og 10 <br> Android 5 eller senere <br>iOS 8 eller senere <br>macOS |
| Apple Safari (siste versjon) |iOS 8 eller senere <br>macOS |

## <a name="supported-browsers-for-powerapps-studio-for-web"></a>Nettlesere som støttes for PowerApps Studio for nett
| **Nettleser** | **Operativsystem** |
| --- | --- |
| Google Chrome (siste versjon)<br>(anbefalt) |Windows 7 SP1, 8.1 og 10 <br>macOS |
| Microsoft Edge (siste versjon)<br>(anbefalt) |Windows 10 |
| Microsoft Internet Explorer 11 (med kompatibilitetsmodus for visning av) |Windows 7 SP1, 8.1 og 10 |

## <a name="request-limits"></a>Be om grenser
Disse begrensningene gjelder for hver enkelt utgående forespørsel:

| Navn | Grense |
| --- | --- |
| Tidsavbrudd |180 sekunder |
| Nye tilkoblingsforsøk |4 |

> [!NOTE]
> Prøv på nytt-verdien kan variere. Ved visse feil er det ikke nødvendig å prøve på nytt.

## <a name="ip-addresses"></a>IP-adresser
Forespørsler fra PowerApps bruker IP-adresser som avhenger av området for [miljøet](../../administrator/environments-overview.md) som appen er i. Vi kunngjør ikke fullstendig kvalifiserte domenenavn som er tilgjengelige for PowerApps-scenarioer.

Samtaler fra en API som er koblet til via en app (for eksempel SQL-API-en, eller SharePoint-API-en), kommer fra IP-adressen angitt senere i dette emnet.

Du bør bruke disse adressene hvis du for eksempel må hviteliste IP-adresser for en Azure SQL-database.

| Område | Utgående IP |
| --- | --- |
| Asia |52.163.91.227, 52.163.89.40, 52.163.89.65, 52.163.95.29, 13.75.89.9, 13.75.91.198, 13.75.92.202, 13.75.92.124 |
| Australia |13.77.7.172, 13.70.191.49, 13.70.189.7, 13.70.187.251, 13.70.82.210, 13.73.203.158, 13.73.207.42, 13.73.205.35 |
| Canada |52.233.30.222, 52.233.30.148, 52.233.30.199, 52.233.29.254, 52.232.130.205, 52.229.126.118, 52.229.126.28, 52.229.123.56 |
| Europa |52.166.241.149, 52.166.244.232, 52.166.245.173, 52.166.243.169, 40.69.45.126, 40.69.45.11, 40.69.45.93, 40.69.42.254 |
| India |52.172.54.172, 52.172.55.107, 52.172.55.84, 52.172.51.70, 52.172.158.185, 52.172.159.100, 52.172.158.2, 52.172.155.245 |
| Japan |104.214.137.186, 104.214.139.29, 104.214.140.23, 104.214.138.174, 13.78.85.193, 13.78.84.73, 13.78.85.200, 13.78.86.229 |
| USA |104.43.232.28, 104.43.232.242, 104.43.235.249, 104.43.234.211, 52.160.93.247, 52.160.91.66, 52.160.92.131, 52.160.95.100, 40.117.101.91, 40.117.98.246, 40.117.101.120, 40.117.100.191 |
| USA (tidlig tilgang) |52.161.26.191, 52.161.27.42, 52.161.29.40, 52.161.26.33, 13.66.213.240, 13.66.214.51, 13.66.210.166, 13.66.213.29 |

## <a name="required-services"></a>Nødvendige tjenester
Denne listen identifiserer alle tjenester som PowerApps Studio kommuniserer med, og deres bruksområder. Nettverket må **ikke** blokkere disse tjenestene.

| Domene(r) | Protokoller | Bruker |
| --- | --- | --- |
| management.azure.com |https |RP |
| msmanaged-na.azure-apim.net |https |Kjøretiden for koblinger/API-er |
| login.microsoft.com<br>login.windows.net<br>login.microsoftonline.com<br>secure.aadcdn.microsoftonline-p.com |https |ADAL |
| graph.microsoft.com<br>graph.windows.net |https |Azure Graph – for å hente brukerinformasjon (f.eks. profilbilde) |
| gallery.azure.com |https |Eksempel og mal-apper |
| *.azure-apim.net |https |API-huber – forskjellige underdomener for hver nasjonale innstilling |
| *.powerapps.com |https |WebAuth + Portal |
| *.azureedge.net |https |WebAuth |
| *. blob.core.windows.net |https |Blob-lagring |
| vortex.data.microsoft.com |https |Telemetri |
