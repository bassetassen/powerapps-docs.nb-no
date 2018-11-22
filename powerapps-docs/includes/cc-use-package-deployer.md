Verktøyet Package Deployer er tilgjengelig som en [NuGet-pakke](https://go.microsoft.com/fwlink/?linkid=859205). Hvis du vil bruke Package Deployer, må du laste ned og pakke ut verktøyet til den lokale datamaskinen ved hjelp av **nuget.exe.**<br/><br/>

Last ned **nuget.exe** fra <https://www.nuget.org/downloads>, og lagre filen på datamaskinen, for eksempel på stasjon **d:\\**. Kjør deretter følgende kommando på kommandolinjen for å pakke ut innholdet i en mappe, for eksempel **PD**, på datamaskinen:<br/>

`d:\nuget install Microsoft.CrmSdk.XrmTooling.PackageDeployment.Wpf -Version [VERSION] -O d:\PD`<br/><br/>
    
Når du har pakket ut verktøyet Package Deployer, kan du gå til `[ExtractedLocation]\tools`-mappen for å finne filen **PackageDeployer.exe**. 
