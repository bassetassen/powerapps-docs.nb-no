---
title: Oversikt for utviklere – Common Data Service for Apps I Microsoft Docs
description: Finn ut hvordan utviklere kan legge til verdien ved hjelp av Common Data Service for Apps.
services: ''
suite: powerapps
documentationcenter: na
author: JimDaly
manager: faisalmo
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/19/2018
ms.author: jdaly
search.audienceType:
- developer
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: 3b0e2d70a9295bdf1a8a6d6a71cb6075677bb991
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/24/2018
ms.locfileid: "42844058"
---
# <a name="common-data-service-for-apps-developer-overview"></a>Oversikt for utviklere – Common Data Service for Apps

PowerApps tilbyr firmaer, uavhengige programvareleverandører og systemintegratorer en kraftig plattform for å bygge apper for forretningsområde. Det nye tillegget til PowerApps i denne versjonen er utvidelsen av Common Data Service, nå kalt Common Data Service for Apps. Det inneholder nå kjernefunksjonaliteten for Dynamics 365-plattformen som driver Dynamics 365 for salg, markedsføring og kundeservice.


## <a name="get-started"></a>Kom i gang

Hvis du allerede har erfaring med Dynamics 365 for salg, markedsføring eller kundeserviceapper, vil du se at du kan bruke din erfaring for å tilpasse og utvide Common Data Service for Apps.

Hvis du er ny i Dynamics 365 for salg, markedsføring eller kundeserviceapper, gir følgende emner en overordnet oversikt over viktige konsepter som hjelper deg i gang med arbeidet med Common Data Service for Apps.

> [!NOTE]
> - Modelldrevne apper kobler til Common Data Service for Apps. Hvis du vil ha mer informasjon om hvordan utviklere kan legge til verdi på programnivå, kan du se [Modelldrevne apper – Oversikt for utviklere](../model-driven-apps/overview.md). Innholdet i denne delen gjelder bare utvidelser som utviklere kan gjøre på tjenestenivå. 
> - Fordi Common Data Service for Apps er samme plattform som benyttes av Dynamics 365 for salg, markedsføring eller kundeserviceapper, finner du mer fullstendig informasjon for utviklere i [Dynamics 365 Customer Engagement – Veiledning for utviklere](/dynamics365/customer-engagement/developer/developer-guide). Disse emnene gir en oversikt med koblinger til veiledning for utviklere og andre støttelinjer for mer informasjon.


## <a name="tools-and-resources-for-developers"></a>Verktøy og ressurser for utviklere

Utviklere bruker følgende verktøy og ressurser når de arbeider med løsninger ved hjelp av Common Data Service for Apps.

### <a name="tools-available-for-download-from-nuget"></a>Verktøyene er tilgjengelige for nedlasting fra NuGet

Følgende verktøy er distribuert i NuGet-pakker. [Veiledning for utviklere: Å laste ned verktøy fra NuGet](/dynamics365/customer-engagement/developer/download-tools-nuget) emnet inneholder et PowerShell-skript som du kan bruke til å laste ned og trekke ut de nyeste versjonene av disse verktøyene.

|Verktøy  |Beskrivelse  |
|---------|---------|
|Kodegenereringsverktøy `CrmSvcUtil.exe`|Et kodegenereringsverktøy for kommandolinjen som genererer tidlig bundete. NET Framework-klasser, som representerer enhetsdatamodellen som brukes av organisasjonstjenesten. <br />Mer informasjon: <br />[Organisasjonstjeneste](use-web-services.md#organization-service)<br />[Dynamics 365 Customer Engagement – Veiledning for utviklere: Å opprette tidlig bundete enhetsklasser med kodegeneringsverktøy ](/dynamics365/customer-engagement/developer/org-service/create-early-bound-entity-classes-code-generation-tool)|
|Verktøy for konfigurasjonsoverføring `DataMigrationUtility.exe`|Brukes til å flytte konfigurasjonsdata på tvers av miljøer. Konfigurasjonsdata brukes til å definere egendefinert funksjonalitet, og lagres vanligvis i egendefinerte enheter. Dette verktøyet er ikke utformet for å flytte forretningsdata. <br /> Hvis du vil ha mer informasjon, kan du se [Veiledning for administrator – Dynamics 365 Customer Engagement: Å flytte konfigurasjonsdata på tvers av forekomster og organisasjoner med verktøy for konfigurasjonsoverføring](/dynamics365/customer-engagement/admin/manage-configuration-data)|
|Pakkedistributør `PackageDeployer.exe`|Brukes til å distribuere pakker på Common Data Service for Apps-forekomster. En pakke er en installerbar enhet som inkluderer løsninger. <br /> Mer informasjon: <br />[Distribuere løsningspakker](introduction-solutions.md#deploy-solution-packages)<br />[Dynamics 365 Customer Engagement – Veiledning for utviklere: Å opprette pakker for Dynamics 365 Package Deployer](/dynamics365/customer-engagement/developer/create-packages-package-deployer)|
|Registreringsverktøy for programtillegg `PluginRegistration.exe`|Verktøy som brukes til å abonnere .NET-samling for programtilleggklasser i serverhendelser. <br />Mer informasjon: <br />[Opprette et programtillegg](apply-business-logic-with-code.md#create-a-plug-in)<br />[Dynamics 365 Customer Engagement – Veiledning for utviklere: Gjennomgang: Registrere et programtillegg ved hjelp av registreringsverktøy for programtillegg](/dynamics365/customer-engagement/developer/walkthrough-register-plugin-using-plugin-registration-tool)|
|SolutionPackager-verktøy `SolutionPackager.exe`|Et verktøy som kan reversere oppdeling av en komprimert løsningsfil for Common Data Service for Apps til flere XML-filer og andre filer slik at disse filene kan enkelt administreres av et system for kildekontroll.<br /> Mer informasjon: <br />[Teamutvikling av løsninger](introduction-solutions.md#team-development-of-solutions)<br />[Dynamics 365 Customer Engagement – Veiledning for utviklere: Å bruke verktøyet SolutionPackager for å komprimerer og trekke ut en løsningsfil](/dynamics365/customer-engagement/developer/compress-extract-solution-file-solutionpackager)|

### <a name="net-sdk-assemblies"></a>.NET SDK-samlinger

Følgende er samlinger .NET-utviklere kan bruke. De nyeste versjonene er tilgjengelige for nedlasting i de tilsvarende NuGet-pakkene.

#### <a name="work-with-data"></a>Arbeid med data

Bruk disse samlingene for å samhandle med organisasjonstjenesten og tjenester for oppdagelse.

Hvis du vil ha mer informasjon, kan du se [Dynamics 365 Customer Engagement – Veiledning for utviklere: Å bruke organisasjonstjenesten i Dynamics 365](/dynamics365/customer-engagement/developer/use-microsoft-dynamics-365-organization-service)

**NuGet-pakke**: [Microsoft.CrmSdk.CoreAssemblies](https://www.nuget.org/packages/Microsoft.CrmSdk.CoreAssemblies/)

|Samling  |Navneområder  |
|---------|---------|
|Microsoft.Crm.Sdk.Proxy.dll|[Microsoft.Crm.Sdk](/dotnet/api/microsoft.crm.sdk)<br />[Microsoft.Crm.Sdk.Messages](/dotnet/api/microsoft.crm.sdk.messages)|
|Microsoft.Xrm.Sdk.dll|[Microsoft.Xrm.Sdk](/dotnet/api/microsoft.xrm.sdk)<br />[Microsoft.Xrm.Sdk.Client](/dotnet/api/microsoft.xrm.sdk.client)<br />[Microsoft.Xrm.Sdk.Discovery](/dotnet/api/microsoft.xrm.sdk.discovery)<br />[Microsoft.Xrm.Sdk.Messages](/dotnet/api/microsoft.xrm.sdk.messages)<br />[Microsoft.Xrm.Sdk.Metadata](/dotnet/api/microsoft.xrm.sdk.metadata)<br />[Microsoft.Xrm.Sdk.Metadata.Query](/dotnet/api/microsoft.xrm.sdk.metadata.query)<br />[Microsoft.Xrm.Sdk.Organization](/dotnet/api/microsoft.xrm.sdk.organization)<br />[Microsoft.Xrm.Sdk.Query](/dotnet/api/microsoft.xrm.sdk.query)<br />[Microsoft.Xrm.Sdk.WebServiceClient](/dotnet/api/microsoft.xrm.sdk.webserviceclient)|

#### <a name="create-process-designer-workflow-extensions"></a>Å opprette utvidelser for prosessdesigner (arbeidsflyt)

Bruk denne samlingen til å legge til egendefinerte aktiviteter i prosessdesigner. 

Hvis du vil ha mer informasjon, kan du se [Dynamics 365 Customer Engagement – Veiledning for utviklere: Egendefinerte arbeidsflytaktiviteter (arbeidsflytsamlinger)](/dynamics365/customer-engagement/developer/custom-workflow-activities-workflow-assemblies)

**NuGet-pakke**: [Microsoft.CrmSdk.CoreAssemblies](https://www.nuget.org/packages/Microsoft.CrmSdk.Workflow/) 

|Samling|Navneområder|
|---------|---------|
|Microsoft.Xrm.Sdk.Workflow.dll|[Microsoft.Xrm.Sdk.Workflow](/dotnet/api/microsoft.xrm.sdk.workflow)<br />[Microsoft.Xrm.Sdk.Workflow.Activities](/dotnet/api/microsoft.xrm.sdk.workflow.activities)<br />[Microsoft.Xrm.Sdk.Workflow.Designers](/dotnet/api/microsoft.xrm.sdk.workflow.designers)|

#### <a name="build-windows-client-applications"></a>Å bygge Windows-klientprogrammer

Bruk disse samlingene til å gjøre det enklere å koble til organisasjonstjenesten og bygge Windows-klientprogrammer. 

Hvis du vil ha mer informasjon, kan du se [Dynamics 365 Customer Engagement – Veiledning for utviklere: Å bygge Windows-klientprogrammer ved hjelp av XRM-verktøy](/dynamics365/customer-engagement/developer/build-windows-client-applications-xrm-tools)

**NuGet-pakker**:
- [Microsoft.CrmSdk.XrmTooling.CoreAssembly](https://www.nuget.org/packages/Microsoft.CrmSdk.XrmTooling.CoreAssembly/) (Microsoft.Xrm.Tooling.Connector.dll)
- [Microsoft.CrmSdk.XrmTooling.WpfControls](https://www.nuget.org/packages/Microsoft.CrmSdk.XrmTooling.WpfControls/) 

|Samling|Navneområder  |
|---------|---------|
|Microsoft.Xrm.Tooling.Connector.dll|[Microsoft.Xrm.Tooling.Connector](/dotnet/api/microsoft.xrm.tooling.connector)<br />[Microsoft.Xrm.Tooling.Connector.Model](/dotnet/api/microsoft.xrm.tooling.connector.model)|
|Microsoft.Xrm.Tooling.CrmConnectControl.dll|[Microsoft.Xrm.Tooling.CrmConnectControl](/dotnet/api/microsoft.xrm.tooling.crmconnectcontrol)<br />[Microsoft.Xrm.Tooling.CrmConnectControl.Model](/dotnet/api/microsoft.xrm.tooling.crmconnectcontrol.model)<br />[Microsoft.Xrm.Tooling.CrmConnectControl.Properties](/dotnet/api/microsoft.xrm.tooling.crmconnectcontrol.properties)<br />[Microsoft.Xrm.Tooling.CrmConnectControl.Utility](/dotnet/api/microsoft.xrm.tooling.crmconnectcontrol.utility)|
|Microsoft.Xrm.Tooling.WebResourceUtility.dll|[Microsoft.Xrm.Tooling.WebResourceUtility](/dotnet/api/microsoft.xrm.tooling.webresourceutility)|

#### <a name="create-packages"></a>Å opprette pakker

Bruk disse samlingene til å opprette pakker for pakkedistributør.

Hvis du vil ha mer informasjon, kan du se [Dynamics 365 Customer Engagement – Veiledning for utviklere: Å opprette pakker for Dynamics 365 Pakkedistributør](/dynamics365/customer-engagement/developer/create-packages-package-deployer)

**NuGet Package**: [Microsoft.CrmSdk.XrmTooling.PackageDeployment](https://www.nuget.org/packages/Microsoft.CrmSdk.XrmTooling.PackageDeployment/)

|Samling|Navneområde  |
|---------|---------|
|Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.dll|[Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase](/dotnet/api/microsoft.xrm.tooling.packagedeployment.crmpackageextentionbase)|

#### <a name="create-custom-virtual-entity-data-providers"></a>Å opprette egendefinert virtuell enhet for dataleverandører

Bruk denne samlingen til å opprette egendefinert virtuell enhet for dataleverandører. 

Hvis du vil ha mer informasjon, kan du se [Dynamics 365 Customer Engagement – Veiledning for utviklere: Å komme i gang med virtuelle enheter](/dynamics365/customer-engagement/developer/virtual-entities/get-started-ve)

**NuGet Package**: [Microsoft.CrmSdk.Data](https://www.nuget.org/packages/Microsoft.CrmSdk.Data/)

|Samling  |Navneområder  |
|---------|---------|
|Microsoft.Xrm.Sdk.Data.dll|[Microsoft.Xrm.Sdk.Data](/dotnet/api/microsoft.xrm.sdk.data)<br />[Microsoft.Xrm.Sdk.Data.CodeGen](/api/microsoft.xrm.sdk.data.codegen)<br />[Microsoft.Xrm.Sdk.Data.Converters](/dotnet/api/microsoft.xrm.sdk.data.converters)<br />[Microsoft.Xrm.Sdk.Data.Exceptions](/dotnet/api/microsoft.xrm.sdk.data.exceptions)<br />[Microsoft.Xrm.Sdk.Data.Expressions](/dotnet/api/microsoft.xrm.sdk.data.expressions)<br />[Microsoft.Xrm.Sdk.Data.Infra](/dotnet/api/microsoft.xrm.sdk.data.infra)<br />[Microsoft.Xrm.Sdk.Data.Mappings](/dotnet/api/microsoft.xrm.sdk.data.mappings)|

#### <a name="extend-outlook-client"></a>Å utvide Outlook-klienten

Bruk denne samlingen til å samhandle med Microsoft Dynamics 365 for Outlook og Microsoft Dynamics 365 for Microsoft Office Outlook med frakoblet tilgang. 

Hvis du vil ha mer informasjon, kan du se [Dynamics 365 Customer Engagement – Veiledning for utviklere: Dynamics 365 Customer Engagement for Outlook](/dynamics365/customer-engagement/developer/extend-customer-engagement-outlook)

**NuGet Package**: [Microsoft.CrmSdk.Outlook](https://www.nuget.org/packages/Microsoft.CrmSdk.Outlook/)

|Samling|Navneområde|
|---------|---------|
|Microsoft.Crm.Outlook.Sdk.dll|[Microsoft.Crm.Outlook.Sdk](/dotnet/api/microsoft.crm.outlook.sdk)|



## <a name="community-tools-for-common-data-service-for-apps"></a>Fellesskapsverktøy for Common Data Service for Apps

Oppretterverktøy for Dynamics 365-fellesskapet! Mange av de mest populære distribueres i [XrmToolBox](https://www.xrmtoolbox.com/). XrmToolBox er et Windows-program som kobler til Common Data Service for apper, som leverer verktøy for å forenkle tilpasning, konfigurering og operasjonsoppgaver. Den leveres med mer enn 30 programtillegg for gjøre administrasjons-, tilpassings- eller konfigurasjonsoppgaver enklere og mindre tidkrevende.

Følgende er en valgt liste med fellesskapsverktøy distribuert via XrmToolBox som du kan bruke når du arbeider med Common Data Service for Apps.

|Verktøy  |Beskrivelse  |
|---------|---------|
|[Attribute Manager](https://www.xrmtoolbox.com/plugins/DLaB.Xrm.AttributeManager/)|Brukes til å gi nytt navn/slette/eller endre attributt-typen.|
|[Tidlig bundet generator](https://www.xrmtoolbox.com/plugins/DLaB.Xrm.EarlyBoundGenerator/)|Genererer tidlig bundet enheter/alternativsett/handlinger. Bruker CrmSvcUtil fra SDK, og viser kommandolinjen som brukes til å opprette klassene.|
|[Eksporter til Excel](https://www.xrmtoolbox.com/plugins/Ryr.XrmToolBox.ExportToExcel/)|Enkel eksport av poster fra den valgte visningen/fetchxml til Excel.|
|[FetchXML Builder](https://www.xrmtoolbox.com/plugins/Cinteros.Xrm.FetchXmlBuilder/)|Å opprette og teste FetchXml-spørringer|
|[Metadataleser](https://www.xrmtoolbox.com/plugins/MsCrmTools.MetadataBrowser/)|Å bla gjennom metadata fra organisasjonen Dynamics CRM|
|[Sporingsvisning av programtillegg](https://www.xrmtoolbox.com/plugins/Cinteros.XrmToolBox.PluginTraceViewer/)|Å undersøke sporingsloggen til programtillegg med enkel filtrering og vise mulighetene|
|[Brukerinnstillingsverktøy](https://www.xrmtoolbox.com/plugins/MsCrmTools.UserSettingsUtility/)|Å administrere brukernes personlige innstillinger i bulk|

> [!NOTE]
> Verktøy som er laget av fellesskapet støttes ikke av Microsoft. Hvis du har spørsmål eller problemer med fellesskapsverktøy, kan du kontakte utgiveren av verktøyet.
