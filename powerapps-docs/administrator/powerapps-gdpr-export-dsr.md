---
title: Svar på DSR-forespørsler om eksport av kundedata for PowerApps | Microsoft Docs
description: Svar på DSR-forespørsler om eksport av kundedata for PowerApps
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
ms.date: 04/18/2018
ms.author: jamesol
ms.openlocfilehash: 58edfa4d82f58094f12df47ed330783cd3c40a40
ms.sourcegitcommit: e3a2819c14ad67cc4ca6640b9064550d0f553d8f
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/20/2018
---
# <a name="responding-to-export-data-subject-rights-dsr-requests-for-powerapps-customer-data"></a>Svar på DSR-forespørsler om eksport av kundedata for PowerApps

*Retten til dataportabilitet* gir en bruker rett til å be om en kopi av personopplysningene sine i et elektronisk format (det vil si et strukturert, velkjent, maskinlesbart og interoperabelt format) som kan overføres til en annen datakontrollør:

* Nettstedstilgang: [PowerApps-utviklerområdet](https://web.powerapps.com), [PowerApps-administrasjonssenteret](https://admin.powerapps.com/) og [Office 365 Service Trust Portal](https://servicetrust.microsoft.com/)

* PowerShell-tilgang: PowerApps-cmdleter ([cmdleter for utviklere](https://go.microsoft.com/fwlink/?linkid=871448), [cmdleter for administratorer](https://go.microsoft.com/fwlink/?linkid=871804)) og [cmdleter for lokale gatewayer](https://go.microsoft.com/fwlink/?linkid=872238)

Nedenfor finner du et sammendrag av de ulike typene personopplysninger som PowerApps kan lagre for en bestemt bruker, samt hvordan du kan finne og eksportere dem.

Ressurser som inneholder personopplysninger | Nettstedstilgang |   PowerShell-tilgang
--- | --- | --
Miljø | Administrasjonssenteret for PowerApps |  PowerApps-cmdleter
Miljøtillatelser**   | Administrasjonssenteret for PowerApps    | PowerApps-cmdleter
Lerretsapp  | Administrasjonssenteret for PowerApps <br> Utviklerportalen for PowerApps |  PowerApps-cmdleter
Tillatelser for lerretsapper  | Administrasjonssenteret for PowerApps <br> Utviklerportalen for PowerApps    | PowerApps-cmdleter
Gateway | Utviklerportalen for PowerApps*** | Cmdleter for lokale gatewayer
Gatewaytillatelser | Utviklerportalen for PowerApps*** |
Egendefinert kobling | |    Utvikler: tilgjengelig <br> Administrator: under utvikling
Tillatelser for tilpasset kobling | |    Utvikler: tilgjengelig <br> Administrator: under utvikling
Tilkobling | | Utvikler: tilgjengelig <br> Administrator: under utvikling
Tilkoblingstillatelser  | | Utvikler: tilgjengelig <br> Administrator: under utvikling
PowerApps-brukerinnstillinger, brukerappinnstillinger og varslinger | | Utvikler: tilgjengelig <br> Administrator: under utvikling

> ** I Common Data Service for Apps blir miljøtillatelser og tillatelser for modelldrevne apper lagret som oppføringer i databaseinstansen for CDS for Apps hvis du har opprettet en database i miljøet. Se [Executing DSR requests against Common Data Service for Apps customer data](https://go.microsoft.com/fwlink/?linkid=872251) (Håndtering av DRS-forespørsler om kundedata for Common Data Service for Apps) for å få en veiledning i hvordan du svarer på DSR-forespørsler for brukere som bruker CDS for Apps.

> *** En administrator får bare tilgang til disse ressursene fra [PowerApps](https://web.powerapps.com) hvis eieren av ressursen uttrykkelig har gitt vedkommende tilgang.  Hvis det ikke er tilfelle, må administratoren bruke [PowerShell-cmdleter for PowerApps-administratorer](https://go.microsoft.com/fwlink/?linkid=871804).

## <a name="prerequisites"></a>Forutsetninger

### <a name="for-users"></a>For brukere
Alle brukere som har en gyldig PowerApps-lisens, kan utføre brukeroperasjonene som beskrevet i dette dokumentet, ved hjelp av [PowerApps](https://web.powerapps.com) eller [utvikler-cmdleter](https://go.microsoft.com/fwlink/?linkid=871448).

### <a name="for-admins"></a>For administratorer
For at du skal kunne utføre administrasjonsoperasjonene som er beskrevet i dette dokumentet, ved å bruke administrasjonssenteret for PowerApps, administrasjonssenteret for Microsoft Flow eller [PowerShell-cmdleter for PowerApps-administratorer](https://go.microsoft.com/fwlink/?linkid=871804), må du ha en konto med følgende tillatelser:

* En betalt PowerApps Plan 2-lisens eller en prøvelisens på PowerApps Plan 2. Du kan registrere deg for en 30-dagers prøvelisens på [http://web.powerapps.com/trial](http://web.powerapps.com/trial). Prøvelisenser kan fornyes hvis de har utløpt.

* Hvis du har behov for å søke gjennom en annen brukers ressurser, må du også ha tillatelser for [global Administrator for Office 365](https://support.office.com/article/assign-admin-roles-in-office-365-for-business-eac4d046-1afd-4f1a-85fc-8219c79e1504) eller [global administrator for Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles-azure-portal). Ellers får du bare tilgang til miljøene og miljøressursene der du har administratorrettigheter for miljøet.

## <a name="step-1-export-personal-data-contained-within-environments-created-by-the-user"></a>Trinn 1: Eksporter personopplysninger innenfor miljøer opprettet av brukeren

### <a name="powerapps-admin-center"></a>Administrasjonssenteret for PowerApps
Administratorer kan eksportere alle miljøer som er opprettet av en bestemt bruker, fra [administrasjonssenteret for PowerApps](https://admin.powerapps.com/) ved å følge disse trinnene:
1. Fra [administrasjonssenteret for PowerApps](https://admin.powerapps.com/) velger du hvert miljø i organisasjonen.

  ![Målside for administrasjonssenteret](./media/powerapps-gdpr-export-dsr/admin-center-landing.png)

2. Hvis miljøet ble opprettet av brukeren fra DSR-forespørselen, går du til **Details**-siden (Detaljer), kopierer detaljene og limer dem inn i et redigeringsprogram for dokumenter, for eksempel Microsoft Word.

  ![Miljødetaljer](./media/powerapps-gdpr-export-dsr/environment-details.png)

### <a name="powerapps-maker-powershell-cmdlets"></a>PowerShell-cmdleter for PowerApps-utviklere
Brukere kan eksportere miljøer de har tilgang til i PowerApps, ved hjelp av funksjonen **Get-PowerAppsEnvironment** i [PowerShell-cmdleter for PowerApps-utviklere](https://go.microsoft.com/fwlink/?linkid=871448):

~~~~
Add-PowerAppsAccount
Get-PowerAppsEnvironment | ConvertTo-Json | Out-File -FilePath "UserDetails.json"
~~~~

### <a name="powerapps-admin-powershell-cmdlets"></a>PowerShell-cmdleter for PowerApps-administratorer
Administratorer kan eksportere alle miljøer som har blitt opprettet av en bruker, ved hjelp av funksjonen **Get-AdminEnvironment** i [PowerShell-cmdleter for PowerApps-administratorer](https://go.microsoft.com/fwlink/?linkid=871804):

~~~~
Add-PowerAppsAccount
$userId = "7557f390-5f70-4c93-8bc4-8c2faabd2ca0"
Get-AdminEnvironment -CreatedBy $userId | ConvertTo-Json | Out-File -FilePath "UserDetails.json"
~~~~
 
## <a name="step-2-export-the-users-environment-permissions"></a>Trinn 2: Eksporter brukerens miljøtillatelser
Brukere kan tildeles tillatelser (for eksempel miljøadministrator, miljøoppretter og så videre) i et miljø, og disse lagres i PowerApps som en *rolletildeling*. I CDS for Apps blir disse rolletildelingene lagret som oppføringer i databaseinstansen for CDS for Apps hvis du har opprettet en database i miljøet. Du finner mer informasjon i [Administer environments within PowerApps](environments-administration.md) (Administrere miljøer i PowerApps).

### <a name="for-environments-without-a-cds-for-apps-database"></a>For miljøer uten en CDS for Apps-database

#### <a name="powerapps-admin-center"></a>Administrasjonssenteret for PowerApps
Administratorer kan eksportere en brukers miljøtillatelser fra [administrasjonssenteret for PowerApps](https://admin.powerapps.com/) ved å følge disse trinnene:

1. Fra [administrasjonssenteret for PowerApps](https://admin.powerapps.com/) velger du hvert miljø i organisasjonen. Du må være [global administrator for Office 365](https://support.office.com/article/assign-admin-roles-in-office-365-for-business-eac4d046-1afd-4f1a-85fc-8219c79e1504) eller [global administrator for Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles-azure-portal) for å kunne se gjennom alle miljøer som er opprettet i organisasjonen.

  ![Målside for administrasjonssenteret](./media/powerapps-gdpr-export-dsr/admin-center-landing.png)

2.  Velg **Security** (Sikkerhet).

    Hvis miljøet ditt ikke har en CDS for Apps-database, ser du en del med **Environment Roles** (Miljøroller).

3. Velg både **Environment Admin** (Miljøadministrator) og **Environment Maker** (Miljøoppretter), og søk deretter etter brukerens navn ved å bruke søkefeltet.

  ![Miljørollesiden](./media/powerapps-gdpr-export-dsr/admin-environment-role-share-page.png)

5. Hvis brukeren har tilgang til en av rollene, går du til siden **Users** (Brukere), kopierer detaljene og limer dem inn i et redigeringsprogram for dokumenter, for eksempel Microsoft Word.

#### <a name="powerapps-admin-powershell-cmdlets"></a>PowerShell-cmdleter for PowerApps-administratorer
Administratorer kan eksportere alle miljørolletildelinger for en bruker i alle miljøer uten en CDS for Apps-database ved hjelp av funksjonen **Get-AdminEnvironmentRoleAssignment** i [PowerShell-cmdleter for PowerApps-administratorer](https://go.microsoft.com/fwlink/?linkid=871804):

~~~~
Add-PowerAppsAccount
$userId = "0ecb1fcc-6782-4e46-a4c4-738c1d3accea"
Get-AdminEnvironmentRoleAssignment -UserId $userId | ConvertTo-Json | Out-File -FilePath "UserDetails.json"
~~~~

> [!IMPORTANT]
>  Denne funksjonen fungerer bare for miljøer som ikke har en databaseinstans for CDS for Apps.
>
>

### <a name="for-environments-with-a-cds-for-apps-database"></a>For miljøer MED en CDS for Apps-database
I CDS for Apps blir rolletildelingene lagret som oppføringer i databaseinstansen for CDS for Apps hvis du har opprettet en database i miljøet. Du finner informasjon om hvordan du fjerner personopplysninger fra en databaseinstans for CDS for Apps i [Common Data Service User personal data removal](https://go.microsoft.com/fwlink/?linkid=871886) (Fjerning av personopplysninger for Common Data Service-brukere).
 
## <a name="step-3-export-personal-data-contained-within-canvas-apps-created-by-the-user"></a>Trinn 3: Eksporter personopplysninger innenfor lerretsapper opprettet av brukeren

### <a name="powerapps-maker-portal"></a>Utviklerportalen for PowerApps
En bruker kan eksportere en app fra [PowerApps](https://web.powerapps.com). Du finner trinnvise instruksjoner om hvordan du eksporterer en app, i [Exporting an app](environment-and-tenant-migration.md#exporting-an-app) (Eksport av apper).

### <a name="powerapps-admin-center"></a>Administrasjonssenteret for PowerApps
Administratorer kan eksportere apper som er opprettet av en bruker, fra [administrasjonssenteret for PowerApps](https://admin.powerapps.com/) ved å følge disse trinnene:

1. Fra [administrasjonssenteret for PowerApps](https://admin.powerapps.com/) velger du hvert miljø i organisasjonen. Du må være [global administrator for Office 365](https://support.office.com/article/assign-admin-roles-in-office-365-for-business-eac4d046-1afd-4f1a-85fc-8219c79e1504) eller [global administrator for Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles-azure-portal) for å kunne se gjennom alle miljøer som er opprettet i organisasjonen.

  ![Målside for administrasjonssenteret](./media/powerapps-gdpr-export-dsr/admin-center-landing.png)

2.  Velg **Resources** (Ressurser) og deretter **Apps** (Apper).

3. Bruk søkefeltet til å søke etter navnet til brukeren. Dette viser alle apper som brukeren har opprettet i dette miljøet:

  ![Søk etter apper](./media/powerapps-gdpr-export-dsr/search-apps.png)

4. Velg **Share** (Del) for hver av appene som er opprettet av denne brukeren, og gi deg selv **Can edit**-tilgang (redigeringstilgang) til appen:

  ![Velg appdeling](./media/powerapps-gdpr-export-dsr/select-share.png)

  ![Gi en bruker tilgang](./media/powerapps-gdpr-export-dsr/grant-access.png)

5. Når du har tilgang til brukerens apper, kan du eksportere en app fra [PowerApps](https://web.powerapps.com). Du finner trinnvise instruksjoner om hvordan du eksporterer en app, i [Exporting an app](environment-and-tenant-migration.md#exporting-an-app) (Eksport av apper).

### <a name="powerapps-admin-powershell-cmdlets"></a>PowerShell-cmdleter for PowerApps-administratorer
Administratorer kan eksportere apper som har blitt opprettet av en bruker, ved hjelp av funksjonen **Get-AdminApp** i [PowerShell-cmdleter for PowerApps-administratorer](https://go.microsoft.com/fwlink/?linkid=871804):

~~~~
Add-PowerAppsAccount
$userId = "0ecb1fcc-6782-4e46-a4c4-738c1d3accea"
Get-AdminApp -Owner $userId | ConvertTo-Json | Out-File -FilePath "UserDetails.json"
~~~~

## <a name="step-4-export-the-users-permissions-to-canvas-apps"></a>Trinn 4: Eksporter brukerens tillatelser til lerretsapper
Når en app blir delt med en bruker, lagrer PowerApps en oppføring kalt en *rolletildeling*, som beskriver brukerens tillatelser (CanEdit eller CanUser), i programmet. Du finner mer informasjon i [Share an app](../maker/canvas-apps/share-app.md#share-an-app)(Deling av apper).

### <a name="powerapps-maker-powershell-cmdlets"></a>PowerShell-cmdleter for PowerApps-utviklere
Brukere kan eksportere approlletildelingene for alle apper de har tilgang til, ved hjelp av funksjonen **Get-RoleAssignment** i [PowerShell-cmdleter for PowerApps-utviklere](https://go.microsoft.com/fwlink/?linkid=871448):

~~~~
Add-PowerAppsAccount
Get-AppRoleAssignment | ConvertTo-Json | Out-File -FilePath "UserDetails.json"
~~~~

### <a name="powerapps-admin-center"></a>Administrasjonssenteret for PowerApps
Administratorer kan eksportere approlletildelinger for en bruker fra [administrasjonssenteret for PowerApps](https://admin.powerapps.com/) ved å følge disse trinnene:

1. Fra [administrasjonssenteret for PowerApps](https://admin.powerapps.com/) velger du hvert miljø i organisasjonen. Du må være [global administrator for Office 365](https://support.office.com/article/assign-admin-roles-in-office-365-for-business-eac4d046-1afd-4f1a-85fc-8219c79e1504) eller [global administrator for Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles-azure-portal) for å kunne se gjennom alle miljøer som er opprettet i organisasjonen.

  ![Målside for administrasjonssenteret](./media/powerapps-gdpr-export-dsr/admin-center-landing.png)

2. Velg **Resources** (Ressurser) og deretter **Apps** (Apper) for hvert miljø.

3. Velg **Share** (Del) for hver av appene i miljøet.

  ![Velg appdeling](./media/powerapps-gdpr-export-dsr/select-admin-share-nofilter.png)

4. Hvis brukeren har tilgang til appen, går du til siden **Share** (Del) for appen, kopierer detaljene og limer dem inn i et redigeringsprogram for dokumenter, for eksempel Microsoft Word.

  ![Appdelingssiden for administratorer](./media/powerapps-gdpr-export-dsr/admin-share-page.png)

### <a name="powerapps-admin-powershell-cmdlets"></a>PowerShell-cmdleter for PowerApps-administratorer
Administratorer kan eksportere alle approlletildelinger for en bruker i alle apper i leieren ved hjelp av funksjonen **Get-AdminAppRoleAssignment** i [PowerShell-cmdleter for PowerApps-administratorer](https://go.microsoft.com/fwlink/?linkid=871804):

~~~~
Add-PowerAppsAccount
$userId = "0ecb1fcc-6782-4e46-a4c4-738c1d3accea"
Get-AdminAppRoleAssignment -UserId $userId | ConvertTo-Json | Out-File -FilePath "UserDetails.json"
~~~~

## <a name="step-5-export-personal-data-contained-within-connections-created-by-the-user"></a>Trinn 5: Eksporter personopplysninger innenfor tilkoblinger opprettet av brukeren
Tilkoblinger brukes sammen med koblinger ved oppretting av tilkoblingsmuligheter med andre API-er og SaaS-systemer. Tilkoblinger inneholder blant annet referanser til brukeren som opprettet dem, og kan derfor slettes for å fjerne alle referanser til brukeren.

### <a name="powerapps-maker-powershell-cmdlets"></a>PowerShell-cmdleter for PowerApps-utviklere
Brukere kan eksportere alle tilkoblinger de har tilgang til, ved hjelp av funksjonen **Get-Connection** i [PowerShell-cmdleter for PowerApps-utviklere](https://go.microsoft.com/fwlink/?linkid=871448):

~~~~
Add-PowerAppsAccount
Get-Connection | ConvertTo-Json | out-file -FilePath "UserDetails.json"
~~~~

### <a name="powerapps-admin-powershell-cmdlets"></a>PowerShell-cmdleter for PowerApps-administratorer
Funksjonen administratorer kan bruke til å eksportere tilkoblinger som er opprettet av en bruker, ved hjelp av [PowerShell-cmdleter for PowerApps-administratorer](https://go.microsoft.com/fwlink/?linkid=871804), er under utvikling.
 
## <a name="step-6-export-the-users-permissions-to-shared-connections"></a>Trinn 6: Eksporter brukerens tillatelser til delte tilkoblinger
### <a name="powerapps-maker-powershell-cmdlets"></a>PowerShell-cmdleter for PowerApps-utviklere
Brukere kan eksportere tilkoblingsrolletildelingene for alle tilkoblinger de har tilgang til, ved hjelp av funksjonen **Get-ConnectionRoleAssignment** i [PowerShell-cmdleter for PowerApps-utviklere](https://go.microsoft.com/fwlink/?linkid=871448):

~~~~
Add-PowerAppsAccount
Get-ConnectionRoleAssignment | ConvertTo-Json | out-file -FilePath "UserDetails.json"
~~~~

### <a name="powerapps-admin-powershell-cmdlets"></a>PowerShell-cmdleter for PowerApps-administratorer
Funksjonen administratorer kan bruke til å eksportere tilkoblingsrolletildelinger for en bruker ved hjelp av [PowerShell-cmdleter for PowerApps-administratorer](https://go.microsoft.com/fwlink/?linkid=871804), er under utvikling.

## <a name="step-7-export-personal-data-contained-within-custom-connectors-created-by-the-user"></a>Trinn 7: Eksporter personopplysninger innenfor egendefinerte koblinger opprettet av brukeren
Egendefinerte koblinger er et supplement til eksisterende standardkoblinger og gir tilkoblingsmulighet til andre API-er, SaaS og spesialutviklede systemer.

### <a name="powerapps-maker-powershell-cmdlets"></a>PowerShell-cmdleter for PowerApps-utviklere
Brukere kan eksportere alle egendefinerte koblinger de har opprettet, ved hjelp av funksjonen **Get-Connector** i [PowerShell-cmdleter for PowerApps-utviklere](https://go.microsoft.com/fwlink/?linkid=871448):

~~~~
Add-PowerAppsAccount  
Get-Connector -FilterNonCustomConnectors | ConvertTo-Json | Out-File -FilePath "UserDetails.json"
~~~~

### <a name="powerapps-admin-powershell-cmdlets"></a>PowerShell-cmdleter for PowerApps-administratorer
Funksjonen administratorer kan bruke til å eksportere egendefinerte koblinger som er opprettet av en bruker, ved hjelp av [PowerShell-cmdleter for PowerApps-administratorer](https://go.microsoft.com/fwlink/?linkid=871804), er under utvikling.

## <a name="step-8-export-the-users-permissions-to-custom-connectors"></a>Trinn 8: Eksporter brukerens tillatelser til egendefinerte koblinger

### <a name="powerapps-maker-powershell-cmdlets"></a>PowerShell-cmdleter for PowerApps-utviklere
Brukere kan eksportere alle koblingsrolletildelingene for de egendefinerte koblingene de har tilgang til, ved hjelp av funksjonen **Get-ConnectorRoleAssignment** i [PowerShell-cmdleter for PowerApps-utviklere](https://go.microsoft.com/fwlink/?linkid=871448):

~~~~
Add-PowerAppsAccount  
Get-ConnectorRoleAssignment | ConvertTo-Json | Out-File -FilePath "UserDetails.json"
~~~~

### <a name="powerapps-admin-powershell-cmdlets"></a>PowerShell-cmdleter for PowerApps-administratorer
Funksjonen administratorer kan bruke til å eksportere rolletildelinger for egendefinerte koblinger for en bruker ved hjelp av [PowerShell-cmdleter for PowerApps-administratorer](https://go.microsoft.com/fwlink/?linkid=871804), er under utvikling.
 
## <a name="step-9-export-powerapps-notifications-user-settings-and-user-app-settings"></a>Trinn 9: Eksporter varslinger, brukerinnstillinger og brukerappinnstillinger for PowerApps
PowerApps sender flere typer varslinger til brukere, blant annet når en app deles med dem og når en eksport i CDS for Apps er fullført. Brukernes varslingshistorikk er synlig for dem i [PowerApps](https://web.powerapps.com).

PowerApps lagrer også flere forskjellige brukerinnstillinger og innstillinger som brukes til å levere kjøretiden og portalen for PowerApps, deriblant når en bruker åpnet et program sist, festet en app og så videre.

### <a name="powerapps-maker-powershell-cmdlets"></a>PowerShell-cmdleter for PowerApps-utviklere
Funksjonen for eksport av en brukers varslinger, brukerinnstillinger og brukerappinnstillinger for PowerApps ved hjelp av [PowerShell-cmdleter for PowerApps-administratorer](https://go.microsoft.com/fwlink/?linkid=871804) er under utvikling.

### <a name="powerapps-admin-powershell-cmdlets"></a>PowerShell-cmdleter for PowerApps-administratorer
Funksjonen administratorer kan bruke til å eksportere en brukers varslinger, brukerinnstillinger og brukerappinnstillinger for PowerApps ved hjelp av [PowerShell-cmdleter for PowerApps-administratorer](https://go.microsoft.com/fwlink/?linkid=871804), er under utvikling.

## <a name="step-10-export-personal-data-contained-for-a-user-stored-gateway-or-in-the-users-gateway-permissions"></a>Trinn 10: Eksporter personopplysningene for en brukerlagret gateway eller i brukerens gatewaytillatelser

### <a name="powerapps-maker-portal"></a>Utviklerportalen for PowerApps
Brukere kan eksportere personopplysningene lagret i gatewaytjenesten fra [PowerApps](https://web.powerapps.com) ved å følge disse trinnene:

1. I standardmiljøet for leieren i [PowerApps](https://web.powerapps.com) velger du **Gateways** (Gatewayer) og deretter **Details** (Detaljer) for hver gateway du har tilgang til.

  ![Målside for gateway](./media/powerapps-gdpr-export-dsr/gateway-select-details.png)

2. Hvis gatewaydetaljene omfatter personopplysninger, kopierer du detaljene på siden **Details** (Detaljer) og limer dem inn i et redigeringsprogram for dokumenter, for eksempel Microsoft Word.

  ![Gatewaydetaljer](./media/powerapps-gdpr-export-dsr/gateway-details-drillin.png)

3. Velg **Share** (Del), kopier innholdet på siden, og lim det inn i et redigeringsprogram for dokumenter, for eksempel Microsoft Word.

  ![Gatewaydetaljer](./media/powerapps-gdpr-export-dsr/gateway-details-share.png)

### <a name="gateway-powershell-cmdlets"></a>PowerShell-cmdleter for gatewayer
Det finnes også PowerShell-cmdleter som gjør det mulig å hente, behandle og slette personlige gatewayer. Du finner mer informasjon i [On-premise gateway cmdlets](https://go.microsoft.com/fwlink/?linkid=872238) (Cmdleter for lokale gatewayer).

## <a name="step-11-export-the-users-personal-data-in-microsoft-flow"></a>Trinn 11: Eksporter brukerens personopplysninger i Microsoft Flow
PowerApps-lisenser inkluderer alltid Microsoft Flow-funksjoner. I tillegg til å være inkludert i PowerApps-lisensene er Microsoft Flow også tilgjengelig som en frittstående tjeneste. Du finner informasjon om hvordan du svarer på DSR-forespørsler for brukere som bruker Microsoft Flow-tjenesten, i [Executing DSRs against Microsoft Flow Customer Data](https://go.microsoft.com/fwlink/?linkid=872250) (Håndtering av DSR-forespørsler om kundedata for Microsoft Flow).

> [!IMPORTANT] 
>  Vi anbefaler at administratorer utfører dette trinnet for PowerApps-brukere.
>
>

## <a name="step-12-export-the-users-personal-data-in-cds-for-apps-instances"></a>Trinn 12: Eksporter brukerens personopplysninger i CDS for Apps-instanser
Enkelte PowerApps-lisenser gir brukere i organisasjonen mulighet til å opprette CDS for Apps-instanser og opprette og utvikle apper på CDS for Apps. Et eksempel er PowerApps Community Plan, som er en gratislisens som gir brukere muligheten til å prøve CDS for Apps i et enkeltmiljø. Se siden med [PowerApps-priser](https://powerapps.microsoft.com/pricing) for informasjon om hvilke CDS for Apps-funksjoner som er inkludert i de ulike PowerApps-lisensene.

Se [Executing DSRs against Common Data Service Customer Data](https://go.microsoft.com/fwlink/?linkid=872251) (Håndtering av DSR-forespørsler om kundedata for Common Data Service) for å få en veiledning i hvordan du svarer på DSR-forespørsler for brukere som bruker CDS for Apps.

> [!IMPORTANT]
>  Vi anbefaler at administratorer utfører dette trinnet for PowerApps-brukere.
>
>
