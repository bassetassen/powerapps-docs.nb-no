---
title: Feilsøking for Power Query | Microsoft Docs
description: Løs problemer ved å bruke Power Query til å opprette en egendefinert entitet i Common Data Service for apper
services: ''
suite: powerapps
documentationcenter: na
author: mllopis
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 08/18/2017
ms.author: millopis
ms.openlocfilehash: dafed76565a4bd3fb3e2822319d344f49376b4fc
ms.sourcegitcommit: a9d33322228c398d29964429602dc3fe19fa67d2
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/28/2018
ms.locfileid: "30998097"
---
# <a name="troubleshooting-power-query"></a>Feilsøking for Power Query
Når du bruker Power Query til å opprette en egendefinert enhet som inneholder data fra eksterne kilder, kan denne feilen oppstå:

`Your Azure Active Directory administrator has set a policy that prevents you from using this feature. Please contact your administrator, who can grant permissions for this feature on your behalf.`

Feilmeldingen vises hvis Power Query ikke får tilgang til organisasjonens data i PowerApps eller Common Data Service. Dette problemet oppstår under to sett med omstendigheter:

* En Azure Active Directory (AAD)-tenantadministrator har ikke tillatt at brukere godtar at apper får tilgang til firmadata på deres vegne.
* Slik bruker du en ikke-administrert Active Directory-tenant. En ikke-administrert tenant er en mappe uten en global administrator som ble opprettet for å fullføre et selvbetjent tilbud om registrering. For å løse denne situasjonen må brukere først konverteres til en administrert tenant. Følg deretter én av de to løsningene for dette problemet, som beskrevet i delen nedenfor.

Hvis du vil løse dette problemet, må AAD-administratoren følge trinnene i én av fremgangsmåtene senere i dette emnet.

## <a name="allow-users-to-consent-to-apps-that-access-company-data"></a>Tillat at brukere kan samtykke til at apper får tilgang til firmadata
Dette er kanskje den enkleste måten, men den gir rom for mer omfattende tillatelser enn neste alternativ.

1. Åpne **Azure Active Directory**-bladet i [https://portal.azure.com](https://portal.azure.com), og velg deretter **Brukerinnstillinger**.
1. Velg **Ja** ved siden av **Brukere kan gi samtykke til at apper får tilgang til firmadata på deres vegne**, og velg deretter **Lagre**.

## <a name="allow-power-query-to-access-company-data"></a>Å gi Power Query tilgang til firmadata
En annen løsning er å be leieradministrator gi samtykke til Power Query uten å endre tillatelser for hele leieren.

1. Installer [Azure PowerShell](https://docs.microsoft.com/powershell/azure/install-azurerm-ps).
2. Kjør følgende PowerShell-kommandoer:
   * Logg på AzureRmAccount (og logg deg på som leieradministrator)
   * New-AzureRmADServicePrincipal -ApplicationId f3b07414-6bf4-46e6-b63f-56941f3f4128

Fordelen med denne fremgangsmåten (i motsetning til løsningen som endrer tillatelser for hele leieren) er at denne løsningen er svært målrettet. Den klargjør bare **Power Query**-hovedtjenesten, uten å endre andre tillatelser for tenanten.

