PowerShell-filer for verktøyet Package Deployer er tilgjengelig som en [NuGet-pakke](https://go.microsoft.com/fwlink/?linkid=859211). Hvis du vil bruke filene, må du laste ned og pakke ut verktøyet til den lokale datamaskinen ved hjelp av **nuget.exe.**<br/><br/>

Last ned **nuget.exe** fra <https://www.nuget.org/downloads>, og lagre filen på datamaskinen, for eksempel på stasjon **d:\\**. Kjør deretter følgende kommando på kommandolinjen for å pakke ut innholdet i en mappe, for eksempel **PD PowerShell**, på datamaskinen:<br/>

`d:\nuget install Microsoft.CrmSdk.XrmTooling.PackageDeployment.PowerShell -Version [VERSION] -O d:\PD-PowerShell`<br/><br/>
    
Når du har pakket ut PowerShell-filene for verktøyet Package Deployer, kan du gå til `[ExtractedLocation]\tools`-mappen for å finne de nødvendige filene. 
