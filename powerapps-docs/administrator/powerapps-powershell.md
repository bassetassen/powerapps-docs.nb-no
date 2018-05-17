---
title: PowerShell-støtte | Microsoft Docs
description: Beskrivelse av ulike PowerShell-cmdleter og en gjennomgang av hvordan du installerer og kjører dem
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
ms.date: 04/23/2018
ms.author: jamesol
ms.openlocfilehash: 69508b2127c5c919db4a334045c6eed3bb9374af
ms.sourcegitcommit: 0a781b50a8551f2e61c22725ef1c43ba4fdf752a
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/27/2018
---
# <a name="powershell-support-for-powerapps-preview"></a>PowerShell-støtte for PowerApps (forhåndsversjon)
Forhåndsversjonen av PowerShell-cmdleter for apputviklere og administratorer er lansert, og nå kan du automatisere mange av overvåkings- og administrasjonsoppgavene som det i dag bare er mulig å utføre manuelt på [PowerApps](https://web.powerapps.com) eller [ PowerApps-administrasjonssenteret](https://admin.powerapps.com).

## <a name="installation"></a>Installasjon
Hvis du vil kjøre PowerShell-cmdleter for applagere, gjør du følgende:

1. Last ned[PowerShell-skriptfilen](https://go.microsoft.com/fwlink/?linkid=872358).

2. Pakk ut filen i en mappe.

3. Åpne et PowerShell-kommandovindu (som administrator) i den samme mappen.

4. Kjør følgende PowerShell-engangskommando (dette forutsetter at du aldri har kjørt PowerShell-kommandoer på den gjeldende maskinen):

    ```
    Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Force
    ```

5. Importer de nødvendige modulene ved å bruke følgende kommandoer:

    ```
    Import-Module .\Microsoft.PowerApps.Administration.PowerShell.psm1 -Force
    Import-Module .\Microsoft.PowerApps.PowerShell.psm1 -Force
    ```

6. Før du får tilgang til kommandoene, må du oppgi legitimasjonen din ved å bruke følgende kommando. Denne legitimasjonen er gyldig i opptil ca. 8 timer, og deretter må du logge deg på igjen for å kunne fortsette å bruke cmdletene.

    ```
    Add-PowerAppsAccount
    ```

7.  Det er et [kjent problem](https://powerusers.microsoft.com/t5/Administering-PowerApps/Getting-errors-when-I-try-to-import-the-preview-powerapps/td-p/109036) i dag som også kan kreve at du manuelt fjerner blokkeringen av PowerShell-filer ved hjelp av følgende kommando:

    ```
    dir . | Unblock-File
    ```

## <a name="powerapps-cmdlets-for-app-makers-preview"></a>PowerApps-cmdleter for apputviklere (forhåndsversjon)

### <a name="prerequisite"></a>Forutsetning
Brukere med en gyldig lisens for PowerApps kan utføre operasjoner i disse cmdletene, men de vil bare ha tilgang til ressurser (for eksempel apper, flyt osv.) som har blitt opprettet eller delt med dem.

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
> Bruk følgende kommandoer for å forstå syntaksen og se eksempler på de ulike cmdletene:
>```
>Get-Help Get-PowerAppsEnvironment
>Get-Help Get-PowerAppsEnvironment -Examples
>Get-Help Get-PowerAppsEnvironment -Detailed
>```

## <a name="powerapps-cmdlets-for-administrators-preview"></a>PowerApps-cmdleter for administratorer (forhåndsversjon)

### <a name="prerequisite"></a>Forutsetning
For å utføre administrasjonsoperasjonene i administrator-cmdletene må du ha følgende:

* En betalt PowerApps Plan 2-lisens eller en prøvelisens på PowerApps Plan 2. Du kan registrere deg for en 30-dagers prøvelisens på [http://web.powerapps.com/trial](http://web.powerapps.com/trial). Prøvelisenser kan fornyes hvis de har utløpt.

* I tillegg kreves det tillatelser for [global administrator for Office 365](https://support.office.com/article/assign-admin-roles-in-office-365-for-business-eac4d046-1afd-4f1a-85fc-8219c79e1504) eller [global administrator for Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles-azure-portal) hvis du har behov for å søke via ressursene til en annen bruker. (Merk at miljøadministrator bare har tilgang til miljøer og miljøressurser de har tillatelser til.)

### <a name="cmdlet-list"></a>Cmdlet-liste
| Formål | Cmdleter
| --- | ---
| Les og slett miljøer | Get-AdminEnvironment <br> Remove-AdminEnvironment
| Les, oppdater og slett miljøtillatelser <br><br> *Cmdleter fungerer bare for miljøer som ikke har en database for Common Data Service (CDS) for Apps.* | Get-AdminEnvironmentRoleAssignment <br> Set-AdminEnvironmentRoleAssignment <br> Remove-AdminEnvironmentRoleAssignment
| Les og slett lerretsapper | Get-AdminApp <br> Remove-AdminApp
| Les, oppdater og slett tillatelser for lerretsapper | Get-AdminAppRoleAssignment <br> Remove-AdminAppRoleAssignment <br> Set-AdminAppRoleAssignment <br> Set-AdminAppOwner
| Les, oppdater og slett flyter | Get-AdminFlow <br> Enable-AdminFlow <br> Disable-AdminFlow <br> Remove-AdminFlow  <br> Remove-AdminFlowOwnerRole

> [!NOTE]
> Bruk følgende kommandoer for å forstå syntaksen og se eksempler på de ulike cmdletene:
>```
>Get-Help Get-AdminEnvironment
>Get-Help Get-AdminEnvironment -Examples
>Get-Help Get-AdminEnvironment -Detailed
>```

## <a name="questions"></a>Spørsmål?

Hvis du har kommentarer, forslag eller spørsmål, kan du legge dem ut på [fellesskapstavlen «Administrasjon av PowerApps»](https://powerusers.microsoft.com/t5/Administering-PowerApps/bd-p/Admin_PowerApps).
