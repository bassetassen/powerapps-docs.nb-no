---
title: Feilsøking for Power Query | Microsoft Docs
description: Løs problemer ved å bruke Power Query til å opprette en egendefinert enhet i Common Data Service for apper.
author: mllopis
manager: kfile
ms.service: powerapps
ms.component: cds
ms.topic: conceptual
ms.date: 05/16/2018
ms.author: millopis
ms.openlocfilehash: b89d7a59406d19759b84c34dbda84b98b10d5e58
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/04/2018
ms.locfileid: "34445733"
---
# <a name="troubleshooting-power-query"></a>Feilsøking for Power Query
Når du bruker Power Query til å opprette en egendefinert enhet som inneholder data fra eksterne kilder, kan denne feilen oppstå:

`Your Azure Active Directory administrator has set a policy that prevents you from using this feature. Please contact your administrator, who can grant permissions for this feature on your behalf.`

Feilmeldingen vises hvis Power Query ikke får tilgang til organisasjonens data i PowerApps eller Common Data Service for apper. Dette problemet oppstår under to sett med omstendigheter:

* En Azure Active Directory (AAD)-tenantadministrator har ikke tillatt at brukere godtar at apper får tilgang til firmadata på deres vegne.
* Slik bruker du en ikke-administrert Active Directory-tenant. En ikke-administrert tenant er en mappe uten en global administrator som ble opprettet for å fullføre et selvbetjent tilbud om registrering. For å løse denne situasjonen må brukere først konverteres til en administrert tenant. Følg deretter én av de to løsningene for dette problemet, som beskrevet i delen nedenfor.

Hvis du vil løse dette problemet, må AAD-administratoren følge trinnene i én av fremgangsmåtene beskrevet senere i dette emnet.

## <a name="allow-users-to-consent-to-apps-that-access-company-data"></a>Tillat at brukere kan samtykke til at apper får tilgang til firmadata
Dette er kanskje den enkleste måten, men den gir rom for mer omfattende tillatelser enn neste alternativ.

1. Åpne **Azure Active Directory**-bladet i [https://portal.azure.com](https://portal.azure.com), og velg deretter **Brukerinnstillinger**.
2. Velg **Ja** ved siden av **Brukere kan gi samtykke til at apper får tilgang til firmadata på deres vegne**, og velg deretter **Lagre**.

## <a name="allow-power-query-to-access-company-data"></a>Å gi Power Query tilgang til firmadata
En annen løsning er å be leieradministrator gi samtykke til Power Query uten å endre tillatelser for hele leieren.

1. Installer [Azure PowerShell](https://docs.microsoft.com/powershell/azure/install-azurerm-ps).
2. Kjør følgende PowerShell-kommandoer:
   * Logg på AzureRmAccount (og logg deg på som leieradministrator)
   * New-AzureRmADServicePrincipal -ApplicationId f3b07414-6bf4-46e6-b63f-56941f3f4128

Fordelen med denne fremgangsmåten (i motsetning til løsningen som endrer tillatelser for hele leieren) er at denne løsningen er svært målrettet. Den klargjør bare **Power Query**-hovedtjenesten, uten å endre andre tillatelser for tenanten.

## <a name="updating-personal-data"></a>Oppdatering av persondata

Brukere kan oppdatere nettfletting og annen informasjon (for eksempel spørringsnavn og metadata for nettfletting) gjennom redigeringsprogrammet for spørring og gjennom `Options`-dialogboksen som er tilgjengelig fra redigeringsprogrammet for spørring.

Redigeringsprogrammet for spørring kan åpnes i PowerApps ved å gå til Data-ruten, utvide den og deretter klikke på menyelementet Enheter-ruten. Så snart du er der, klikker du på «...»-menyen og velger Rediger spørringer. Deretter klikker du på `Options`-knappen på båndet og på `Export Diagnostics`-knappen.


## <a name="deleting-personal-data"></a>Sletting av persondata

De fleste data slettes automatisk innen 30 dager. Brukeren må fjerne alle sine nettflettinger via PowerApps for dataene og metadataene rundt nettflettinger. Alle de tilknyttede dataene og metadataene blir slettet innen 30 dager.

Nettflettinger kan fjernes fra Power Apps ved å fjerne Data Integrator-prosjekter, som kan fjernes fra fanen med samme navn, klikke på knappen «...» og merke `Delete`-alternativet.

Hvis du har opprettet en nettfletting gjennom funksjonen «nye enheter fra data (teknisk forhåndsvisning)», kan du fjerne den ved å klikke på «...»-knappen, velge Rediger spørringer og deretter velge Alternativer på båndet. Til slutt klikker du på knappen «Fjern alle spørringer». Når du bekrefter at du vil slette spørringer, vil de bli slettet.


## <a name="exporting-personal-data"></a>Eksport av persondata

Brukere kan åpne redigeringsprogrammet for spørring, klikke på `Options`-knappen på båndet og klikke på `Export Diagnostics`-knappen.

Redigeringsprogrammet for spørring kan åpnes i PowerApps ved å gå til Data-ruten, utvide den og deretter klikke på menyelementet Enheter-ruten. Så snart du er der, klikker du på «...»-menyen og velger Rediger spørringer. Deretter klikker du på `Options`-knappen på båndet og på `Export Diagnostics`-knappen.

Systemgenererte logger angående brukerhandlinger i brukergrensesnittet (UI) er tilgjengelige i Azure Portal.


