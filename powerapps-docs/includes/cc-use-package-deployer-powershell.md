---
ms.openlocfilehash: 215a6d9fb0890bd6d93843b0b649ada4203e5600
ms.sourcegitcommit: ad203331ee9737e82ef70206ac04eeb72a5f9c7f
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/18/2019
ms.locfileid: "67224194"
---
PowerShell-filer for Package Deployer-verktøyet som er tilgjengelig som en [NuGet-pakke](https://go.microsoft.com/fwlink/?linkid=859211). Hvis du vil bruke dem, må du laste ned og trekke det ut til den lokale datamaskinen ved hjelp av **nuget.exe.**<br/><br/>

Last ned **nuget.exe** fra <https://www.nuget.org/downloads>, og lagre den på datamaskinen, for eksempel på **d:\\** . Kjør deretter følgende kommando når du ser ledeteksten, for å trekke ut pakkeinnholdet til en mappe, for eksempel **PD PowerShell**, på datamaskinen:<br/>

`d:\nuget install Microsoft.CrmSdk.XrmTooling.PackageDeployment.PowerShell -Version [VERSION] -O d:\PD-PowerShell`<br/><br/>
    
Når du har trukket ut PowerShell-filene for Package Deployer-verktøyet, blar du til `[ExtractedLocation]\tools`-mappen for å finne de nødvendige PackageDeployer.exe-filene. 
