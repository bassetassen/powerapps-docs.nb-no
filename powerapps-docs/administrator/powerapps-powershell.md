---
title: PowerShell-støtte | Microsoft Docs
description: PowerShell-støtte for PowerApps
services: powerapps
suite: powerapps
documentationcenter: na
author: jamesol-msft
manager: kfile
editor: ''
tags: ''
ms-topic: article
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 04/17/2018
ms.author: jamesol
ms.openlocfilehash: 274d34ca56cc993ec26fa4f4ced77bb2aba9985f
ms.sourcegitcommit: e3a2819c14ad67cc4ca6640b9064550d0f553d8f
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/20/2018
---
# <a name="powershell-support-for-powerapps-preview"></a>PowerShell-støtte for PowerApps (forhåndsversjon)

Forhåndsversjonen av PowerShell-cmdleter for apputviklere og administratorer er lansert, og nå kan du automatisere mange av overvåkings- og administrasjonsoppgavene som det i dag bare er mulig å utføre manuelt på [PowerApps-området](https://web.powerapps.com) og [ PowerApps-administrasjonssenteret](https://admin.powerapps.com).

## <a name="installation"></a>Installasjon
Hvis du vil kjøre PowerShell-cmdleter for apputviklere, må du først utføre følgende trinn:

1. Last ned PowerShell-skriptfilen [her](https://go.microsoft.com/fwlink/?linkid=872358).

2. Pakk ut filen i en mappe.

3. Åpne et PowerShell-kommandovindu i samme mappe som administrator.

4. Kjør følgende PowerShell-engangskommando (dette forutsetter at du aldri har kjørt PowerShell-kommandoer på den gjeldende maskinen):

    ```
    Set-ExecutionPolicy -ExecutionPolicy Unrestricted -Force
    ```

5. Deretter importerer du de nødvendige modulene ved å bruke følgende kommandoer:

    ```
    Import-Module .\Microsoft.PowerApps.Administration.PowerShell.psm1 -Force
    Import-Module .\Microsoft.PowerApps.PowerShell.psm1 -Force
    ```

6. Til slutt må du, før du får tilgang til kommandoene, oppgi legitimasjonen din ved å bruke følgende kommando. Denne legitimasjonen er gyldig i opptil ca. 8 timer, og deretter må du logge deg på igjen for å kunne fortsette å bruke cmdletene.

    ```
    Add-PowerAppsAccount
    ```

## <a name="powerapps-cmdlets-for-app-makers-preview"></a>PowerApps-cmdleter for apputviklere (forhåndsversjon)

### <a name="prerequisite"></a>Forutsetning
Alle brukere med gyldig PowerApps-lisens kan utføre operasjonene i disse cmdletene. De får imidlertid bare tilgang til ressurser (for eksempel apper eller flyter) som er opprettet av eller delt med dem.

### <a name="cmdlet-list"></a>Cmdlet-liste
| Formål | Cmdlet |
| --- | --- |
| Les miljøer | Get-PowerAppsEnvironment <br> Get-FlowEnvironment
| Les, oppdater og slett en lerretsapp | Get-App <br> Remove-App <br> Publish-App <br> Set-AppDisplayName <br> Get-AppVersion <br> Restore-AppVersion
| Les, oppdater og slett tillatelser for lerretsapper | Get-AppRoleAssignment <br> Set-AppRoleAssignment <br> Remove-AppRoleAssignment
| Les, oppdater og slett en flyt | Get-Flow <br> Get-FlowRun <br> Enable-Flow <br> Disable-Flow <br> Remove-Flow
| Les, oppdater og slett flyttillatelser | Get-FlowOwnerRole <br> Set-FlowOwnerRole <br> Remove-FlowOwnerRole
| Les og svar på flytgodkjenninger | Get-FlowApprovalRequest <br> Get-FlowApproval <br> RespondTo-FlowApprovalRequest
| Les og slett tilkoblinger | Get-Connection <br> Remove-Connection
| Les, oppdater og slett tilkoblingstillatelser | Get-ConnectionRoleAssignment <br> Set-ConnectionRoleAssignment <br> Remove-ConnectionRoleAssignment
| Les og slett koblinger | Get-Connector <br> Remove-Connector
| Les, oppdater og slett tillatelser for egendefinerte koblinger | Get-ConnectorRoleAssignment <br> Set-ConnectorRoleAssignment <br> Remove-ConnectorRoleAssignment

> [!NOTE]
> Følgende kommandoer kan brukes til å forstå syntaksen og se eksempler på de ulike cmdletene:
>```
>Get-Help Get-PowerAppsEnvironment
>Get-Help Get-PowerAppsEnvironment -Examples
>Get-Help Get-PowerAppsEnvironment -Detailed
>```

## <a name="powerapps-cmdlets-for-administrators-preview"></a>PowerApps-cmdleter for administratorer (forhåndsversjon)

### <a name="prerequisite"></a>Forutsetning
For at du skal kunne utføre administrasjonsoperasjonene i administrator-cmdletene, må du ha en konto med følgende tillatelser:

- En betalt PowerApps Plan 2-lisens eller en prøvelisens på PowerApps Plan 2. Du kan registrere deg for en 30-dagers prøvelisens på [http://web.powerapps.com/trial](http://web.powerapps.com/trial). Prøvelisenser kan fornyes hvis de har utløpt.

- I tillegg kreves det rettigheter for [global administrator for Office 365](https://support.office.com/article/assign-admin-roles-in-office-365-for-business-eac4d046-1afd-4f1a-85fc-8219c79e1504) eller [global administrator for Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles-azure-portal) hvis du har behov for å søke via ressursene til en annen bruker. Ellers har du bare tilgang til de miljøene og miljøressursene der du har miljøadministratorrettigheter.

### <a name="cmdlet-list"></a>Cmdlet-liste
| Formål | Cmdleter
| --- | ---
| Les og slett miljøer | Get-AdminEnvironment <br> Remove-AdminEnvironment
| Les, oppdater og slett miljørettigheter <br><br> *Cmdleter fungerer bare for miljøer som ikke har en database for Common Data Service for Apps.* | Get-AdminEnvironmentRoleAssignment <br> Set-AdminEnvironmentRoleAssignment <br> Remove-AdminEnvironmentRoleAssignment
| Les og slett lerretsapper | Get-AdminApp <br> Remove-AdminApp
| Les, oppdater og slett tillatelser for lerretsapper | Get-AdminAppRoleAssignment <br> Remove-AdminAppRoleAssignment <br> Set-AdminAppRoleAssignment <br> Set-AdminAppOwner
| Les, oppdater og slett flyter | Get-AdminFlow <br> Enable-AdminFlow <br> Disable-AdminFlow <br> Remove-AdminFlow  <br> Remove-AdminFlowOwnerRole

> [!NOTE]
> Følgende kommandoer kan brukes til å forstå syntaksen og se eksempler på de ulike cmdletene:
>```
>Get-Help Get-AdminEnvironment
>Get-Help Get-AdminEnvironment -Examples
>Get-Help Get-AdminEnvironment -Detailed
>```

## <a name="questions"></a>Spørsmål?

Hvis du har kommentarer, forslag eller spørsmål, kan du sende dem til [fellesskapstavlen «Administering PowerApps»](https://powerusers.microsoft.com/t5/Administering-PowerApps/bd-p/Admin_PowerApps) (Administrasjon av PowerApps).
