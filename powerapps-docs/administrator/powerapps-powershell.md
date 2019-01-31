---
title: PowerShell-støtte (forhåndsvisning) | Microsoft Docs
description: Beskrivelse av ulike PowerShell-cmdleter og en gjennomgang av hvordan du installerer og kjører dem.
author: jamesol-msft
manager: kvivek
ms.service: powerapps
ms.component: pa-admin
ms.topic: reference
ms.date: 01/18/2019
ms.author: jamesol
search.audienceType:
- admin
search.app:
- D365CE
- PowerApps
- Powerplatform
ms.openlocfilehash: 0152296adbe01abae2b831576c312a43d1f2a2b8
ms.sourcegitcommit: 3ce7c17f90f87756a072210c8abfbd93733a6d4c
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 01/18/2019
ms.locfileid: "54397771"
---
# <a name="powershell-support-for-powerapps-preview"></a>PowerShell-støtte for PowerApps (forhåndsversjon)
Forhåndsversjonen av PowerShell-cmdleter for apputviklere og administratorer er lansert, og nå kan du automatisere mange av overvåkings- og administrasjonsoppgavene som det i dag bare er mulig å utføre manuelt på [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) eller [ PowerApps-administrasjonssenteret](https://admin.powerapps.com).

## <a name="cmdlets"></a>Cmdleter
[Cmdleter](https://docs.microsoft.com/powershell/developer/cmdlet/writing-a-windows-powershell-cmdlet) er funksjoner som er skrevet i PowerShell-skriptspråk, som utfører kommandoer i Windows PowerShell-miljøet. Hvis du kjører disse PowerApps-cmdletene, kan du samhandle med forretningsprogramplattformen uten å måtte gå gjennom administrasjonsportalen i en nettleser. Du kan kombinere disse cmdletene med andre funksjoner i PowerShell for å skrive komplekse skript som kan optimalisere arbeidsflyten. Vær oppmerksom på at du fortsatt kan bruke cmdletene hvis du ikke er administrator på leieren, men du vil være begrenset til ressursene du eier. Cmdleter som begynner med ordet «Admin», er beregnet for bruk av en administrativ brukerkonto.

Cmdleter er tilgjengelige fra PowerShell-galleriet som to separate moduler: 
- [Administrator](https://www.powershellgallery.com/packages/Microsoft.PowerApps.Administration.PowerShell/2.0.1)
- [Oppretter](https://www.powershellgallery.com/packages/Microsoft.PowerApps.PowerShell/1.0.1) 

## <a name="installation"></a>Installasjon
Hvis du vil kjøre PowerShell-cmdleter for app-utviklere, gjør du følgende:

1. Kjør PowerShell som administrator.

   > [!div class="mx-imgBorder"] 
   > ![Kjør PowerShell som administrator](media/open-powershell-as-admin75.png "kjør PowerShell som administrator")

2. Importer de nødvendige modulene ved å bruke følgende kommandoer:

    ```
    Install-Module -Name Microsoft.PowerApps.Administration.PowerShell
    Install-Module -Name Microsoft.PowerApps.PowerShell -AllowClobber
    ```
3. Hvis du blir bedt om å godta endringen av *InstallationPolicy*-verdien av repositoriet, kan du godta [A] Ja til alle moduler ved å skrive inn A og trykke på **Enter** for hver modul.

   ![Godta InstallationPolicy-verdien](media/accept-installationpolicy-value75.png "Godta InstallationPolicy-verdien")

4. Før du får tilgang til kommandoene, har du muligheten til å oppgi legitimasjonen din ved å bruke følgende kommando. Denne legitimasjonen er gyldig i opptil cirka 8 timer, og deretter må du logge deg på igjen for å kunne fortsette å bruke cmdletene.

    ```
    # This call opens prompt to collect credentials (Azure Active Directory account and password) used by the commands 
    Add-PowerAppsAccount
    ```

    ```
    # Here is how you can pass in credentials (avoiding opening a prompt)
    $pass = ConvertTo-SecureString "password" -AsPlainText -Force
    Add-PowerAppsAccount -Username foo@bar.com -Password $pass
    ```

## <a name="powerapps-cmdlets-for-app-creators-preview"></a>PowerApps-cmdleter for app-utviklere (forhåndsversjon)

### <a name="prerequisite"></a>Forutsetning
Brukere med en gyldig lisens for PowerApps kan utføre operasjoner i disse cmdletene, men de vil bare ha tilgang til ressurser (for eksempel apper, flyt osv.) som har blitt opprettet eller delt med dem.

### <a name="cmdlet-list---maker-cmdlets"></a>Cmdlet-liste – cmdleter for opprettere
> [!NOTE]
> Vi har oppdatert noen av funksjonsnavnene til cmdletene i den nyeste versjonen for å kunne legge til passende prefikser for å forhindre konflikter. Se tabellen nedenfor for en oversikt over hva som er endret.

| Formål | Cmdlet |
| --- | --- |
| Les miljøer | Get-PowerAppEnvironment *(tidligere Get-PowerAppsEnvironment)* <br> Get-FlowEnvironment |
| Les, oppdater og slett en lerretsapp | Get-PowerApp *(tidligere Get-App)* <br> Remove-PowerApp *(tidligere Remove-App)* <br> Publish-PowerApp *(tidligere Publish-App)* <br> Set-AppDisplayName *(tidligere Set-PowerAppDisplayName)*<br> Get-PowerAppVersion *(tidligere Get-AppVersion)* <br> Restore-PowerAppVersion *(tidligere Restore-AppVersion)* |
| Les, oppdater og slett tillatelser for lerretsapper | Get-PowerAppRoleAssignment *(tidligere Get-AppRoleAssignment)* <br> Set-PowerAppRoleAssignment *(tidligere Set-AppRoleAssignment)* <br> Remove-PowerAppRoleAssignment *(tidligere Remove-AppRoleAssignment)* |
| Les, oppdater og slett en flyt | Get-Flow <br> Get-FlowRun <br> Enable-Flow <br> Disable-Flow <br> Remove-Flow |
| Les, oppdater og slett flyttillatelser | Get-FlowOwnerRole <br> Set-FlowOwnerRole <br> Remove-FlowOwnerRole |
| Les og svar på flytgodkjenninger | Get-FlowApprovalRequest <br> Get-FlowApproval <br> RespondTo-FlowApprovalRequest |
| Les og slett tilkoblinger | Get-PowerAppConnection *(tidligere Get-Connection)* <br> Remove-PowerAppConnection *(tidligere Remove-Connection)* |
| Les, oppdater og slett tilkoblingstillatelser | Get-PowerAppConnectionRoleAssignment *(tidligere Get-ConnectionRoleAssignment)* <br> Set-PowerAppConnectionRoleAssignment *(tidligere Set-ConnectionRoleAssignment)* <br> Remove-PowerAppConnectionRoleAssignment *(tidligere Remove-ConnectionRoleAssignment)* |
| Les og slett koblinger | Get-PowerAppConnector *(tidligere Get-Connector)* <br> Remove-PowerAppConnector *(tidligere Remove-Connector)* |
| Les, oppdater og slett tillatelser for egendefinerte koblinger | Get-PowerAppConnectorRoleAssignment *(tidligere Get-ConnectorRoleAssignment)* <br> Set-PowerAppConnectorRoleAssignment *(tidligere Set-ConnectorRoleAssignment)* <br> Remove-PowerAppConnectorRoleAssignment *(tidligere Remove-ConnectorRoleAssignment)* |

## <a name="powerapps-cmdlets-for-administrators-preview"></a>PowerApps-cmdleter for administratorer (forhåndsversjon)

### <a name="prerequisite"></a>Forutsetning
For å utføre administrasjonsoperasjonene i administrator-cmdletene må du ha følgende:

* En betalt PowerApps Plan 2-lisens eller en prøvelisens på PowerApps Plan 2. Du kan registrere deg for en 30-dagers prøvelisens på [http://web.powerapps.com/trial](http://web.powerapps.com/trial). Prøvelisenser kan fornyes hvis de har utløpt.

* I tillegg kreves det tillatelser for [global administrator for Office 365](https://support.office.com/article/assign-admin-roles-in-office-365-for-business-eac4d046-1afd-4f1a-85fc-8219c79e1504) eller [global administrator for Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles-azure-portal) hvis du har behov for å søke via ressursene til en annen bruker. (Merk at miljøadministrator bare har tilgang til miljøer og miljøressurser de har tillatelser til.)

### <a name="cmdlet-list---admin-cmdlets"></a>Cmdlet-liste – cmdleter for administratorer

| Formål | Cmdleter
| --- | ---
| Les, oppdater og slett miljøer og databaser for Common Data Service for apper | New-AdminPowerAppEnvironment <br> Set-AdminPowerAppEnvironmentDisplayName <br> Get-AdminPowerAppEnvironment *(tidligere Get-AdminEnvironment)* <br> Remove-AdminPowerAppEnvironment *(tidligere Remove-AdminEnvironment)* <br> New-AdminPowerAppCdsDatabase <br> Get-AdminPowerAppCdsDatabaseLanguages <br> Get-AdminPowerAppCdsDatabaseCurrencies <br> Get-AdminPowerAppEnvironmentLocations |
| Slett CDS-database | Remove-LegacyCDSDatabase **\*Ny\*** | 
| Les, oppdater og slett miljøtillatelser <br><br> *Cmdleter fungerer for øyeblikket bare for miljøer som ikke har en database for Common Data Service (CDS) for apper.* | Get-AdminPowerAppEnvironmentRoleAssignment *(tidligere Get-AdminEnvironmentRoleAssignment)* <br> Set-AdminPowerAppEnvironmentRoleAssignment *(tidligere Set-AdminEnvironmentRoleAssignment)* <br> Remove-AdminPowerAppEnvironmentRoleAssignment *(tidligere Remove-AdminEnvironmentRoleAssignment)* |
| Les, oppdater og slett lerretsapper | Get-AdminPowerApp *(tidligere Get-AdminApp)* <br> Remove-AdminPowerApp *(tidligere Remove-AdminApp)* <br> Get-AdminPowerAppConnectionReferences <br> Set-AdminPowerAppAsFeatured <br> Clear-AdminPowerAppAsFeatured <br> Set-AdminPowerAppAsHero <br> Clear-AdminPowerAppAsHero <br> Set-AdminPowerAppApisToBypassConsent <br> Clear-AdminPowerAppApisToBypassConsent |
| Les, oppdater og slett tillatelser for lerretsapper | Get-AdminPowerAppRoleAssignment *(tidligere Get-AdminAppRoleAssignment)* <br> Remove-AdminPowerAppRoleAssignment *(tidligere Remove-AdminAppRoleAssignment)* <br> Set-AdminPowerAppRoleAssignment *(tidligere Set-AdminAppRoleAssignment)* <br> Set-AdminPowerAppOwner *(tidligere Set-AdminAppOwner)* |
| Les, oppdater og slett flyter | Get-AdminFlow <br> Enable-AdminFlow <br> Disable-AdminFlow <br> Remove-AdminFlow <br> Remove-AdminFlowApprovals |
| Les, oppdater og slett flyttillatelser | Get-AdminFlowOwnerRole <br> Set-AdminFlowOwnerRole <br> Remove-AdminFlowOwnerRole |
| Les og slett tilkoblinger | Get-AdminPowerAppConnection *(tidligere Get-AdminConnection)* <br> Remove-AdminPowerAppConnection *(tidligere Remove-AdminConnection)* |
| Les, oppdater og slett tilkoblingstillatelser | Get-AdminPowerAppConnectionRoleAssignment *(tidligere Get-AdminConnectionRoleAssignment)* <br> Set-AdminPowerAppEnvironmentConnectionRoleAssignment *(tidligere Set-AdminConnectionRoleAssignment)* <br> Remove-AdminPowerAppConnectionRoleAssignment *(tidligere Remove-AdminConnectionRoleAssignment)* |
| Å lese og slette egendefinerte koblinger | Get-AdminPowerAppConnector *(tidligere Get-AdminConnector)* <br> Remove-AdminPowerAppConnector *(tidligere Remove-AdminConnector)* |
| Les, oppdater og slett tillatelser for egendefinerte koblinger | Get-AdminPowerAppConnectorRoleAssignment *(tidligere Get-AdminConnectorRoleAssignment)*<br> Set-AdminPowerAppConnectorRoleAssignment *(tidligere Set-AdminConnectorRoleAssignment)* <br> Remove-AdminPowerAppConnectorRoleAssignment *(tidligere Remove-AdminConnectorRoleAssignment)* |
| Les PowerApps-brukerinnstillinger for en bruker samt bruker-appinnstillinger og varslinger | Get-AdminPowerAppsUserDetails |
| Å lese og slette en brukers Microsoft Flow-innstillinger, som ikke er synlige for brukeren, men som støtter kjøring av flyten | Get-AdminFlowUserDetails <br> Remove-AdminFlowUserDetails |
| Å opprette, lese, oppdatere og slette policyer for hindring av tap av data for organisasjonen | Get-AdminDlpPolicy *(tidligere Get-AdminApiPolicy)* <br> New-AdminDlpPolicy *(tidligere Add-AdminApiPolicy)* <br> Remove-AdminDlpPolicy *(tidligere Remove-AdminApiPolicy)* <br> Set-AdminDlpPolicy *(tidligere Set-AdminApiPolicy)* <br> Add-ConnectorToBusinessDataGroup <br>  Remove-ConnectorFromBusinessDataGroup <br/>Add-CustomConnectorToPolicy<br/> Remove-CustomConnectorFromPolicy|

## <a name="tips"></a>Tips

- Bruk Get-Help «Cmdlet-navn» for å få en liste med eksempler.

     ![Kommandoen Get-Help](media/get-help-cmdlet.png "Kommandoen Get-Help")

- Hvis du vil bla gjennom mulige alternativer for inndatakoder, klikker du på TAB når du har skrevet tankestrek (-) etter cmdlet-navnet.

Eksempel-kommandoer:

```
Get-Help Get-AdminPowerAppEnvironment
Get-Help Get-AdminPowerAppEnvironment -Examples
Get-Help Get-AdminPowerAppEnvironment -Detailed
```

## <a name="operation-examples"></a>Eksempler på operasjoner

Nedenfor finner du noen vanlige scenarioer som viser hvordan du bruker nye og eksisterende PowerApps-cmdleter.

- [Miljøkommandoer](#environments-commands)
- [PowerApps-kommandoer](#powerapps-commands)
- [Flyt-kommandoer](#flow-commands)
- [API-tilkobling-kommandoer](#api-connection-commands)
- [Policy for hindring av datatap (DLP)-kommandoer](#data-loss-prevention-dlp-policy-commands)

### <a name="environments-commands"></a>Miljøkommandoer

Bruk disse kommandoene til å få mer informasjon om og oppdatere miljøer i leieren.

#### <a name="display-a-list-of-all-environments"></a>Vis en liste over alle miljøer

```
Get-AdminPowerAppEnvironment
```

Returnerer en liste over alle miljøene i leieren, med informasjon om hvert (for eksempel miljønavnet (GUID), visningsnavn, plassering, oppretter og så videre).

#### <a name="display-details-of-your-default-environment"></a>Vis informasjon om standardmiljøet ditt

```
Get-AdminPowerAppEnvironment –Default
```

Returnerer informasjon bare om standardmiljøet for leieren.

#### <a name="display-details-of-a-specific-environment"></a>Vis informasjon om et bestemt miljø

```
Get-AdminPowerAppEnvironment –EnvironmentName ‘EnvironmentName’
```

**Obs!** *EnvironmentName*-feltet er en unik identifikator som er forskjellig fra *DisplayName* (se første og andre felter i utdataene i bildet nedenfor).

![Kommandoen Get-AdminEnvironment](media/get-adminenvironment.png "Kommandoen Get-AdminEnvironment")

### <a name="powerapps-commands"></a>PowerApps-kommandoer

Disse operasjonene brukes til å lese og endre data for PowerApps i leieren.

#### <a name="display-a-list-of-all-powerapps"></a>Vis en liste over alle PowerApps

```
Get-AdminPowerApp
```

Returnerer en liste over alle PowerApps i leieren, med informasjon om hver (for eksempel navn (GUID), visningsnavn, oppretter og så videre).

#### <a name="display-a-list-of-all-powerapps-that-match-the-input-display-name"></a>Vis en liste over alle PowerApps som samsvarer med visningsnavnet for inndataene

```
Get-AdminPowerApp 'DisplayName'
```

Returnerer en liste over alle PowerApps i leieren som samsvarer med visningsnavnet. 

**Obs!** Bruk anførselstegn (”) rundt inndataverdier som inneholder mellomrom.

#### <a name="feature-an-application"></a>Fremhev et program

```
Set-AdminPowerAppAsFeatured –AppName 'AppName'
```

Utvalgte programmer samles og legges i toppen av listen i PowerApps Mobile-spilleren.

**Obs!** På samme måte som med miljøer er *AppName*-feltet en unik identifikator som er forskjellig fra *DisplayName*. Hvis du vil utføre operasjoner som er basert på visningsnavnet, kan du med enkelte funksjoner bruke et datasamlebånd (se neste funksjon).

#### <a name="make-an-application-a-hero-app-using-the-pipeline"></a>Gjør et program til en Hero-app ved hjelp av et datasamlebånd

```
Get-AdminPowerApp 'DisplayName' | Set-AdminPowerAppAsHero
```

En Hero-app vil vises på toppen av listen i PowerApps Mobile-spilleren. Det kan bare være én Hero-app.

Et datasamlebånd (representert som |-tegnet mellom to cmdleter) tar utdata fra den første cmdleten og sender dem som inndataverdi for den andre, forutsatt at funksjonen er skrevet med tanke på datasamlebåndet.

**Obs**! En app må være en utvalgt app før den endres til en Hero.

#### <a name="display-the-number-of-apps-each-user-owns"></a>Vis antallet apper hver bruker eier

```
Get-AdminPowerApp | Select –ExpandProperty Owner | Select –ExpandProperty displayname | Group
```

Du kan kombinere opprinnelige PowerShell-funksjoner med PowerApps-cmdleter for å manipulere data enda mer. Vi bruker her Select-funksjonen til å isolere Owner-attributtet (et objekt) fra Get-AdminApp-objektet. Vi isolerer deretter navnet på Owner-objektet ved å sende disse utdataene til en annen Select-funksjon. Til slutt, ved at utdataene til den andre Select-funksjonen sendes til Group-funksjonen, returneres en fin tabell som inneholder antallet apper for hver eier.

![Kommandoen Get-AdminPowerApp](media/get-adminpowerapp.png "Kommandoen Get-AdminPowerApp")

#### <a name="display-the-number-of-apps-in-each-environment"></a>Vis antallet apper i hvert miljø

```
Get-AdminPowerApp | Select -ExpandProperty EnvironmentName | Group | %{ New-Object -TypeName PSObject -Property @{ DisplayName = (Get-AdminPowerAppEnvironment -EnvironmentName $_.Name | Select -ExpandProperty displayName); Count = $_.Count } }
```

![Kommandoen Get-AdminPowerApp](media/get-adminpowerapp-environment.png "Kommandoen Get-AdminPowerApp")

#### <a name="download-powerapps-user-details"></a>Last ned informasjon om PowerApps-bruker

```
Get-AdminPowerAppsUserDetails -OutputFilePath '.\adminUserDetails.txt' –UserPrincipalName ‘admin@bappartners.onmicrosoft.com’
```

Kommandoen over lagrer informasjon om PowerApps-brukere (grunnleggende bruksinformasjon om inndatabrukeren via brukerhovednavnet) i den angitte tekstfilen. Dette oppretter en ny fil hvis det ikke finnes en eksisterende fil med dette navnet, og overskriver tekstfilen hvis den allerede finnes.

#### <a name="set-logged-in-user-as-the-owner-of-a-powerapp"></a>Angi pålogget bruker som eier av en PowerApp

```
Set-AdminPowerAppOwner –AppName 'AppName' -AppOwner $Global:currentSession.userId –EnvironmentName 'EnvironmentName'
```

Endrer eierrollen for en PowerApp til den gjeldende brukeren, og endrer den opprinnelige eieren til en «kan vise»-rolletype.

**Obs!** Feltene AppName og EnvironmentName er de unike identifikatorene (GUID-er), ikke visningsnavnene.

### <a name="flow-commands"></a>Flyt-kommandoer

Bruk disse kommandoene til å vise og endre data knyttet til Microsoft Flow.

#### <a name="display-all-flows"></a>Vis alle flyter

```
Get-AdminFlow
```

Returnerer en liste over alle flyter i leieren.

#### <a name="display-flow-owner-role-details"></a>Vis informasjon om eieren av flyten

```
Get-AdminFlowOwnerRole –EnvironmentName 'EnvironmentName' –FlowName ‘FlowName’
```

Returnerer informasjon om eieren av den angitte flyten.

**Obs!** På samme måte som med *miljøer* og *PowerApps* er *FlowName* en unik identifikator (GUID), som er forskjellig fra visningsnavnet på flyten.

#### <a name="display-flow-user-details"></a>Vis informasjon om brukeren av flyten

```
Get-AdminFlowUserDetails –UserId $Global:currentSession.userId
```

Returnerer brukerinformasjon som gjelder bruk av flyten. I dette eksemplet bruker vi bruker-ID for den gjeldende påloggede brukeren av PowerShell-økten som inndata.

#### <a name="remove-flow-user-details"></a>Fjern informasjon om brukeren av flyten

```
Remove-AdminFlowUserDetails –UserId 'UserId'
```

Sletter helt informasjonen om en bruker av flyten fra Microsoft-databasen. Alle flyter som eies av inndatabrukeren, må slettes før informasjonen om brukeren kan slettes.

**Obs!** UserID-feltet er objekt-ID-en i brukerens Azure Active Directory-post, som finnes i [Azure Portal](https://portal.azure.com) under **Azure Active Directory** > **Brukere** > **Profil** > **Objekt-ID**. Du må være administrator for å få tilgang til disse dataene herfra.

#### <a name="export-all-flows-to-a-csv-file"></a>Eksporter alle flyter til en CSV-fil

```
Get-AdminFlow | Export-Csv -Path '.\FlowExport.csv'
```

Eksporterer alle flyter i leieren til tabellvisning av en CSV-fil.

### <a name="api-connection-commands"></a>API-tilkobling-kommandoer

Vis og administrer API-tilkoblinger i leieren.

#### <a name="display-all-native-connections-in-your-default-environment"></a>Vis alle opprinnelige tilkoblinger i standardmiljøet ditt

```
Get-AdminPowerAppEnvironment -Default | Get-AdminConnection
```

Viser en liste over alle API-tilkoblinger som du har i standardmiljøet. Opprinnelige tilkoblinger blir funnet under fanen **Data-** > **tilkoblinger** i oppretter-portalen.

#### <a name="display-all-custom-connectors-in-the-tenant"></a>Vis alle egendefinerte koblinger i leieren

```
Get-AdminPowerAppConnector
```

Returnerer en liste med informasjon om alle egendefinerte koblinger i leieren.

### <a name="data-loss-prevention-dlp-policy-commands"></a>Policy for hindring av datatap (DLP)-kommandoer

Disse cmdletene styrer DLP-policyene i leieren.

#### <a name="display-all-policies"></a>Vis alle policyer

```
Get-AdminDlpPolicy
```

Returnerer en liste over alle policyene.

#### <a name="display-a-filtered-list-of-policies"></a>Vis en filtrert liste over policyer

```
Get-AdminDlpPolicy 'DisplayName'
```

Bruker visningsnavnet til å filtrere policyene

#### <a name="display-all-business-data-only-api-connectors-in-a-policy"></a>Vis alle API-koblinger med bare forretningsdata i en policy

```
Get-AdminDlpPolicy 'PolicyName' | Select –ExpandProperty BusinessDataGroup
```

Viser en liste over API-tilkoblinger som er i *Bare forretningsdata*(eller *BusinessDataGroup*)-feltet i en policy for inndata.

#### <a name="add-a-connector-to-the-business-data-only-group"></a>Legg til en kobling i Bare forretningsdata-gruppen

```
Add-ConnectorToBusinessDataGroup -PolicyName 'PolicyName' –ConnectorName 'ConnectorName'
```

Legger til en kobling i Bare forretningsdata-gruppen i en gitt DLP-policy. Se listen over koblinger etter *DisplayName* og *ConnectorName* (brukes som inndata) her.

## <a name="version-history"></a>Versjonslogg
| Versjon | Date | Oppdateringer |
| --- | --- | --- |
| 1.0 | 23.04.2018 | <ol> <li> Første oppstart av PowerApps-cmdleter for apputviklere (forhåndsversjon) inkludert administrative cmdleter for miljøer, apper, flyter, flytgodkjenning, tilkoblinger og egendefinerte koblinger </li> <li> Første start av PowerApps-cmdleter for administratorer (forhåndsversjon) inkludert administrative cmdleter for miljøer, apper og flyter </li></ol>|
| 2.0 | 24.05.2018 | <ol> <li> Mindre feilrettinger i både cmdletene for apputviklere og administratorer </li> <li> La til følgende nye administrative cmdleter: <br> Get-AdminConnection <br> Remove-AdminConnection <br> Get-AdminConnectionRoleAssignment <br> Set-AdminConnectionRoleAssignment <br>Remove-AdminConnectionRoleAssignment <br>Get-AdminConnector  <br>Remove-AdminConnector <br>Set-AdminConnectorRoleAssignment  <br>Get-AdminConnectorRoleAssignment  <br>Remove-AdminConnectorRoleAssignment <br>Get-AdminPowerAppsUserDetails <br>Get-AdminFlowUserDetails <br>Remove-AdminFlowUserDetails <br>Get-AdminApiPolicy  <br>Add-AdminApiPolicy <br>Remove-AdminApiPolicy <br>Set-AdminApiPolicy <br>Add-ConnectorToBusinessDataGroup  <br>Remove-ConnectorFromBusinessDataGroup </li> </ol>
| 3.0 | 30.07.2018 | <ol> <li> La til muligheten om å sende legitimasjon til Add-PowerAppsAccount (for å aktivere regelmessige skripting) </li> <li>  Mindre feilrettinger i både cmdletene for apputviklere og administratorer </li> <li> La til prefikset for «PowerApp» eller «Flyt» i hver cmdlet for apputviklere </li> <li>  La til prefikset for «AdminPowerApp» eller «Flyt» i hver cmdlet for administratorer </li> <li> La til følgende nye administrative cmdleter: <br> New-AdminPowerAppEnvironment <br> Set-AdminPowerAppEnvironmentDisplayName <br> New-AdminPowerAppCdsDatabase <br> Get-AdminPowerAppCdsDatabaseLanguages <br> Get-AdminPowerAppCdsDatabaseCurrencies <br> Get-AdminPowerAppEnvironmentLocations <br> Get-AdminPowerAppConnectionReferences <br> Set-AdminPowerAppAsFeatured <br> Clear-AdminPowerAppAsFeatured <br> Set-AdminPowerAppAsHero <br> Clear-AdminPowerAppAsHero <br> Set-AdminPowerAppApisToBypassConsent <br> Clear-AdminPowerAppApisToBypassConsent <br> Remove-AdminFlowApprovals </li></ol>
| 4.0 | 15.08.2018 | La til en valgfri parameter i New-AdminPowerAppCdsDatabase for å gjøre funksjonen synkron, som standard (det vil si, den returnerer ikke før databasen er klargjort)
| 5.0 | 24.08.2018 | Løste et problem der admin-cdmleter for Flow ikke returnerte data for enkelte brukere, basert på deres sikkerhetsinnstillinger
| 6.0 | 01/09/2019 | <ol><li>Cmdleter er nå tilgjengelige fra PowerShell-galleriet som to separate moduler: administrator og oppretter.</li> <li>Lagt til den administrative cmdleten: Remove-LegacyCDSDatabase</li><li> Lagt til eksempler på operasjoner</li><li>Lagt til muligheten til å administrere HTTP og egendefinerte koblinger i hindring av datatap (DLP)</li></ol>|

## <a name="questions"></a>Spørsmål?

Hvis du har kommentarer, forslag eller spørsmål, kan du legge dem ut på [fellesskapstavlen «Administrasjon av PowerApps»](https://powerusers.microsoft.com/t5/Administering-PowerApps/bd-p/Admin_PowerApps).
