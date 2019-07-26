---
ms.openlocfilehash: a108a9ee6f9033851b2f55beb071a1e7cae254dd
ms.sourcegitcommit: ad203331ee9737e82ef70206ac04eeb72a5f9c7f
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/18/2019
ms.locfileid: "67224254"
---
Pakkedistributørverktøyet er tilgjengelig som en [NuGet-pakke](https://go.microsoft.com/fwlink/?linkid=859205). Hvis du vil bruke Pakkedistributør, må du laste ned og trekke det ut til den lokale datamaskinen ved hjelp av **nuget.exe.**<br/><br/>

Last ned **nuget.exe** fra <https://www.nuget.org/downloads>, og lagre den på datamaskinen, for eksempel på **d:\\** . Kjør deretter følgende kommando når du ser ledeteksten, for å trekke ut pakkeinnholdet til en mappe, for eksempel **PD**, på datamaskinen:<br/>

`d:\nuget install Microsoft.CrmSdk.XrmTooling.PackageDeployment.Wpf -Version [VERSION] -O d:\PD`<br/><br/>
    
Når du har trukket ut pakkedistributørverktøyet, går du til `[ExtractedLocation]\tools`-mappen for å finne **PackageDeployer.exe**-filen. 
