---
title: Del en lerretsapp | Microsoft Docs
description: Del lerretsappen ved å gi andre brukere tillatelse til å kjøre eller endre den
author: AFTOwen
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 08/09/2019
ms.author: anneta
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: ecb3e7aa6db1100f33a3c80a0518166b035d2b32
ms.sourcegitcommit: 988aa08353864f8177725262468c07abe75549f5
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/13/2019
ms.locfileid: "68961492"
---
# <a name="share-a-canvas-app-in-powerapps"></a>Del en lerretsapp i PowerApps

Når du har utviklet en lerretsapp som skal ta seg av et forretningsbehov, angir du hvilke brukere i organisasjonen som kan kjøre appen, og hvilke som kan endre den og til og med dele den på nytt. Angi hver bruker etter navn, eller angi en sikkerhetsgruppe i Azure Active Directory. Hvis alle kan dra nytte av appen, angir du at hele organisasjonen kan kjøre den.

> [!IMPORTANT]
> For at en delt app skal fungere som forventet, må du også administrere tillatelser for data kilden eller kildene som appen er basert på, for eksempel [Common data service](#common-data-service) eller [Excel](share-app-data.md). Du må kanskje også dele [andre ressurser](share-app-resources.md) som appen avhenger av, for eksempel flyter, gatewayer eller tilkoblinger.

## <a name="prerequisites"></a>Forutsetninger

Du må lagre appen i skyen (ikke lokalt) og deretter publisere den før du deler den.

- Gi appen et meningsfylt navn og en klar beskrivelse, slik at alle kan se hva appen kan brukes til og det er lett å finne den i en liste. Velg **Appinnstillinger** på **Fil**-menyen i PowerApps Studio, angi et navn, og skriv eller lim deretter inn en beskrivelse.

- Når du gjør endringer, må du lagre og publisere appen på nytt hvis du vil at andre skal se disse endringene.

## <a name="share-an-app"></a>Å dele en app

1. [Logg deg på](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) PowerApps, og velg deretter **Apper** nær venstre kant.

    ![Vise listen over apper](./media/share-app/file-apps.png)

1. Velg appen du vil dele, ved å velge ikonet for den.

    ![Velg en app](./media/share-app/select-app.png)

1. Velg **del**i banneret.

    ![Åpne delt skjerm](./media/share-app/banner-share.png)

1. Angi etter navn eller alias til brukerne eller sikkerhets gruppene i Azure Active Directory som du vil dele appen med.

    - Hvis du vil tillate at hele organisasjonen kjører appen (men ikke endre eller dele den), kan du skrive **alle** i Delings panelet.
    - Du kan dele en app med en liste over aliaser, egen definerte navn eller en kombinasjon av dem (for eksempel  **&lt;Janne Nordmann jane.doe@contoso.com>** ) hvis elementene er atskilt med semikolon. Hvis mer enn én person har samme navn, men forskjellige aliaser, blir den første personen som ble funnet, lagt til i listen. Et verktøy tips vises hvis et navn eller alias allerede har tillatelse eller ikke kan løses. 

    ![Angi brukere og medeiere](./media/share-app/share-everyone.png)

    > [!NOTE]
    > Du kan ikke dele en app med en distribusjons gruppe i organisasjonen eller med en bruker eller gruppe utenfor organisasjonen.

1. Hvis du vil tillate de du deler appen med, til å redigere og dele den (i tillegg til å kjøre den), merker du av for medeier.

    Du kan ikke gi **eier** tillatelse til en sikkerhets gruppe hvis du [opprettet appen fra i en løsning](add-app-solution.md).

    > [!NOTE]
    > Uansett tillatelser, kan ingen personer redigere en app samtidig. Hvis én person åpner appen for redigering, kan andre brukere kjøre den, men ikke redigere den.

1. Hvis appen din kobler til data som brukere trenger tilgangs tillatelser for, kan du angi dem.

    Appen din kan for eksempel koble til en enhet i en Common Data Service database. Når du deler en slik app, ber Delings panelet deg om å administrere sikkerhet for enheten.

    > [!div class="mx-imgBorder"]
    > ![Tilordne en sikkerhets rolle](media/share-app/cds-assign-security-role.png)

    Hvis du vil ha mer informasjon om hvordan du administrerer sikkerhet for en enhet, kan du se [administrere enhets tillatelser](share-app.md#manage-entity-permissions) senere i dette emnet.

1. Hvis du vil hjelpe brukerne med å finne appen din, merker du av for **Send en e-postmelding til nye brukere** .

1. Velg **del**nederst i Delings panelet.

    Alle du har delt appen, kan kjøre den i PowerApps Mobile på en mobilen het eller i AppSource på [Dynamics 365](https://home.dynamics.com) i en nett leser. Medeiere kan redigere og dele appen i [powerapps](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc).

    Hvis du sendte en e-postinvitasjon, kan alle du har delt appen, kjøre den ved å velge en kobling i invitasjonen.

    - Hvis en bruker velger koblingen på en mobilen het, åpnes appen i PowerApps Mobile.
    - Hvis en bruker velger koblingen på en stasjonær data maskin, åpnes appen i en nett leser.

    Med medeiere som mottar en invitasjon, får en annen kobling som åpner appen for redigering i PowerApps Studio.

Du kan endre tillatelser for en bruker eller en sikkerhets gruppe ved å velge navnet og deretter utføre ett av disse trinnene:

- Hvis du vil tillate at medeiere kjører appen, men ikke lenger redigerer eller deler den, fjerner du merket i avmerkings boksen for medeier.
- Hvis du vil stoppe delingen av appen med denne brukeren eller gruppen, velger du Fjern (x)-ikonet.

## <a name="security-group-considerations"></a>Sikkerhetsgruppevurderinger

- Hvis du deler en app med en sikkerhetsgruppe, får eksisterende medlemmer av denne gruppen og alle som blir med i den, tillatelsene du angir for denne gruppen. Alle som forlater gruppen mister denne tillatelsen, med mindre de tilhører en annen gruppe som har tilgang, eller du gir dem tillatelse som enkeltpersoner.

- Hvert medlem av en sikkerhetsgruppe har de samme tillatelsene for en app, som den overordnede gruppen har. Du kan imidlertid angi større tillatelser for ett eller flere medlemmer av gruppen, for å gi dem større tilgang. Du kan for eksempel gi sikkerhets gruppe tillatelse til å kjøre en app, men du kan også gi bruker B som tilhører denne gruppen, tillatelse til å **eie** . Hvert medlem av sikkerhetsgruppen kan kjøre appen, men bare bruker B kan redigere den. Hvis du gir sikkerhets gruppen en tillatelse med medeier og bruker B tillatelse til å kjøre appen, kan denne brukeren fremdeles redigere appen.

## <a name="manage-entity-permissions"></a>Slik administrerer du enhetstillatelser

### <a name="common-data-service"></a>Common Data Service

Hvis du oppretter en app basert på Common Data Service, må du også sørge for at brukerne som du deler appen med, har de nødvendige tillatelsene for enheten eller enhetene som appen er avhengig av. Nærmere bestemt må disse brukerne tilhøre en sikkerhets rolle som kan utføre oppgaver som å opprette, lese, skrive og slette relevante poster. I mange tilfeller må du opprette én eller flere egen definerte sikkerhets roller med de nøyaktige tillatelsene som brukere trenger for å kjøre appen. Deretter kan du tilordne en rolle til hver bruker etter behov.

> [!NOTE]
> Ved denne skriving kan du tilordne sikkerhets roller til individuelle brukere og sikkerhets grupper i Azure Active Directory, men ikke til Office-grupper.

#### <a name="prerequisite"></a>Nødvendig

Hvis du vil tilordne en rolle, må du ha **system administrator** tillatelser for en Common data service database.

#### <a name="assign-a-security-group-in-azure-ad-to-a-role"></a>Tilordne en sikkerhets gruppe i Azure AD til en rolle

1. Velg **tilordne en sikkerhets rolle** under **data tillatelser**i Delings panelet.

1. Velg rollen eller rollene i Common Data Service som du vil tilordne til brukeren eller sikkerhets gruppen i Azure AD, som du vil dele appen med.
     > [!div class="mx-imgBorder"] 
     > ![Sikkerhets rolle liste](media/share-app/cds-assign-security-role-list.png "Sikkerhets rolle liste")

### <a name="common-data-service-previous-version"></a>Common Data Service (forrige versjon)

Når du deler en app som er basert på en eldre versjon av Common Data Service, må du dele kjøre tids tillatelsen for tjenesten separat. Hvis du ikke har tillatelse til å gjøre dette, kan du se miljø administratoren.

## <a name="share-with-guests"></a>Del med gjester

> [!IMPORTANT]
> - Funksjoner for forhåndsvisning er ikke ment for produksjonsformål og kan ha begrenset funksjonalitet. Disse funksjonene er tilgjengelig før en offisiell lansering, slik at kundene får tidlig tilgang og kan gi tilbakemeldinger. 
> - Forhånds visnings funksjoner har begrenset støtte av Microsoft-støtte og kan bare være tilgjengelige i utvalgte geografiske områder. 

Apper for PowerApps-lerret kan deles med gjeste brukere av en Azure Active Directory Tenant. Dette gjør det mulig å invitere eksterne forretnings partnere, oppdragstakere og tredje parter til å kjøre firmaets lerret apper. 

> [!NOTE]
> Gjester kan bare tilordnes **bruker** rollen, og ikke medeier -rollen, for apper som er delt med dem.

### <a name="prerequisites"></a>Forutsetninger
1. I Azure Active Directory (Azure AD) kan du aktivere B2B eksternt samarbeid for leieren. Mer informasjon: [Aktiver B2B eksternt samarbeid og administrer hvem som kan invitere gjester](/azure/active-directory/b2b/delegate-invitations)
    - Gjør at B2B eksternt samarbeid er aktivert som standard. Innstillingene kan imidlertid endres av en leier administrator.  Hvis du vil ha mer informasjon om Azure AD B2B, kan du se [Hva er gjeste bruker tilgang i Azure ad B2B?](/azure/active-directory/b2b/what-is-b2b)  
2. Tilgang til en konto som kan legge til gjeste brukere i en Azure AD-Tenant. Administratorer og brukere med gjeste invitasjons rollen kan legge til gjester i en Tenant.   
3. En PowerApps-lisens må tilordnes til gjeste brukeren i tenanten appen som deles, er tilknyttet. Før du er generell tilgjengelighet av gjeste tilgang til lerretet, må gjester med en PowerApps-lisens i hjem-leieren ikke være tilordnet en lisens i leieren de er en gjest.

### <a name="steps-to-grant-guest-access"></a>Trinn for å gi gjeste tilgang
1. Velg **ny gjeste bruker** for å legge til gjeste brukere i Azure ad. Mer informasjon: [Hurtigstart: Legg til en ny gjeste bruker i](/azure/active-directory/b2b/b2b-quickstart-add-guest-users-portal)Azure ad.
    > [!div class="mx-imgBorder"] 
    > ![Legg til gjest i Azure ad](media/share-app/guest_access_doc_1.png "Legg til gjest i Azure ad")
2. Tilordne en lisens til gjeste brukeren. 
   - Hvis du vil tilordne gjeste brukere fra admin.microsoft.com, kan du se [Tilordne lisenser til én bruker](/office365/admin/subscriptions-and-billing/assign-licenses-to-users).
   - Hvis du vil tilordne gjeste brukere fra portal.azure.com, kan du se [tilordne eller fjerne lisenser](/azure/active-directory/fundamentals/license-users-groups).
 
   > [!IMPORTANT]
   > Du må kanskje deaktivere forhånds visningen av Microsoft 365 administrasjons senteret for å tilordne en lisens til en gjest. 

3. Del lerret-appen. 
    1. Logg deg på https://make.powerapps.com  
    2. Gå til **apper**, Velg en lerrets app, og velg **del**i kommando linjen. 
    3. Skriv inn en e-postadresse for en gjeste bruker fra en Azure AD-Tenant. Mer informasjon: [Hva er gjeste bruker tilgang i Azure AD B2B?](/azure/active-directory/b2b/what-is-b2b)
          > [!div class="mx-imgBorder"] 
          > ![Del med gjest](media/share-app/guest_access_doc_2.png "Del med gjest")
 
Når du har delt en app for gjeste tilgang, kan gjestene oppdage og få tilgang til apper som er delt med dem fra e-postmeldingen som sendes til dem, som en del av delingen.

> [!div class="mx-imgBorder"]  
> ![Gjester mottar e-post med app-deling](media/share-app/guest_access_doc_4.png "Gjester mottar e-post med app-deling")

### <a name="frequently-asked-questions"></a>Vanlige spørsmål

#### <a name="whats-the-difference-between-canvas-app-guest-access-and-powerapps-portals"></a>Hva er forskjellen mellom appens gjeste tilgang og PowerApps-portaler? 
Med C#lerret apper kan du bygge en app, skreddersydd for å digitalisere en forretnings prosess, uten å skrive kode i et tradisjonelt programmerings språk, for eksempel. Gjeste tilgang for lerret apper gjør det mulig for teamene til enkelt personer som består av forskjellige organisasjoner som deltar i en felles forretnings prosess for å få tilgang til de samme program ressursene som kan integreres med en rekke Microsoft-og tredje parts kilder. Mer informasjon: [Oversikt over lerret – app-koblinger for powerapps](/powerapps/maker/canvas-apps/connections-list).

[Powerapps](/powerapps/maker/portals/overview) -portaler gir mulighet til å utvikle lav kode, svar nett steder som gir eksterne brukere mulighet til å samhandle med dataene som er lagret i Common data service. Det gjør det mulig for organisasjoner å opprette nett steder som kan deles med brukere eksternt til organisasjonen enten anonymt eller gjennom påloggings leverandøren for deres valg, som for eksempel LinkedIn, Microsoft-konto eller andre kommersielle påloggings tjenester. 

I tabellen nedenfor finner du en oversikt over noen kjerne funksjoner i PowerApps-portaler og lerrets apper.  

| | Grensesnitt | Godkjenning | Tilgjengelige data kilder |
|------|--------|----------|-------------------|
| PowerApps-portaler | Bare nett leser opplevelsen | Tillater anonym og godkjent tilgang | Common Data Service |
| Lerretsapper | Nett leser og Mobilapper | Krever godkjenning via Azure AD | Alle ~ 150 koblinger som er foreldet, og enhver egen definert kobling  |
||

#### <a name="can-guests-access-customized-forms-in-sharepoint"></a>Kan gjester få tilgang til egen definerte skjemaer i SharePoint?
ja. Alle brukere som har tilgang til en SharePoint-liste med et tilpasset skjema, kan opprette og redigere elementer i listen ved hjelp av skjemaet, uten PowerApps-lisens.

#### <a name="can-guests-access-apps-embedded-in-sharepoint"></a>Kan gjester få tilgang til apper som er innebygd i SharePoint? 
ja. Men tilgang til fritt stående arbeidsom råde apper krever en PowerApps-lisens, inkludert apper som er innebygd. Skriv inn app-ID-en når du bygger inn en lerret-app i SharePoint via Microsoft PowerApps embed-kontrollen. Hvis du vil gjøre dette, skriver du inn app-ID-en i **nett koblingen for appen eller i ID** -boksen. 

> [!div class="mx-imgBorder"]  
> ![Bygg inn lerrets app i SharePoint for gjester](media/share-app/guest_access_doc_5.PNG "Bygg inn lerrets app i SharePoint for gjester")

Når du bygger inn en lerret-app i SharePoint via HTML-koden iFrame, kan du referere til appen ved hjelp av den fullstendige Netta DRESSen. Hvis du vil finne Netta dressen, kan du gå til http://make.powerapps.com, velge en app, velge **detaljer** -fanen, og URL-adressen vises under **nett kobling**.

> [!div class="mx-imgBorder"]  
> ![Detaljer om lerrets app](media/share-app/guest_access_doc_6.PNG "Detaljer om lerrets app")

#### <a name="how-come-guests-can-launch-the-app-shared-with-them-but-connections-fail-to-be-created"></a>Hvordan kan gjester starte appen som er delt med dem, men tilkoblinger blir ikke opprettet?
Som med ikke-gjester, må de underliggende data kildene som brukes av appen også gjøres tilgjengelige for gjesten.

#### <a name="what-license-must-be-assigned-to-my-guest-so-they-can-run-an-app-shared-with-them"></a>Hvilken lisens må tilordnes til gjesten, slik at de kan kjøre en app som er delt med dem?
Den samme lisensen som er nødvendig for at ikke-gjester skal kunne kjøre en app. Hvis for eksempel appen ikke bruker Premium-tilkoblingene, er en PowerApps P1-lisens nok til å tilordne til gjesten.  

Før gjeste tilgang til arbeidsom råde er generell tilgjengelighet, trenger ikke gjester med en PowerApps-lisens i hjem-leieren tilordnes en lisens i leieren de er en gjest.

|                                 | Egen definert SharePoint-skjema | Fritt stående lerret ved bruk av ikke-Premium-koblinger | Fritt stående lerret-app med Premium-koblinger | Modell drevet app |
|---------------------------------|----------------------------|----------------------------------------------------|------------------------------------------------|------------------|
| SharePoint-bruker (ingen PA-lisens) | x                          |                                                    |                                                |                  |
| PowerApps inkludert i/kontor    | x                          |                                                    |                                                |                  |
| PowerApps-abonnement 1                | x                          | x                                                  |                                                |                  |
| PowerApps-Plan2                 | x                          | x                                                  | x                                              | x                |

#### <a name="in-powerapps-mobile-how-does-a-guest-see-apps-for-their-home-tenant"></a>I PowerApps Mobile kan en gjest se apper for deres hjem leier?
Alle brukere som har fått tilgang til en lerret app, på mobilen heten, som er publisert i en Azure AD-leier som ikke er hjem-leieren, må ikke logge seg av PowerApps og logge på PowerApps Mobile.  

Før gjeste tilgang til arbeidsom råde er generell tilgjengelighet, vil en organisasjons velger gi brukeren mulighet til å endre Azure AD-leieren de er logget på uten å eksplisitt logge seg av appen.  

#### <a name="must-a-guest-accept-the-azure-ad-guest-invitation-prior-to-sharing-an-app-with-the-guest"></a>Må en gjest godta gjeste invitasjonen for Azure AD før du deler en app med gjesten?
nei. Hvis en gjest starter en app som er delt med dem før de godtar en gjeste invitasjon, blir gjesten bedt om å godta invitasjonen som en del av påloggings opplevelsen mens du starter appen.  

#### <a name="what-azure-ad-tenant-are-connections-for-a-guest-user-created-in"></a>Hvilken Azure AD-Tenant er tilkoblinger for en gjeste bruker opprettet i?
Tilkoblinger for en app opprettes alltid i konteksten til Azure AD-leieren appen er tilknyttet. Hvis en app for eksempel er opprettet i contoso-leieren, blir tilkoblinger som er opprettet for Contosos interne og gjeste brukere, opprettet i konteksten til contoso-leieren.

#### <a name="can-guests-use-microsoft-graph-via-microsoft-security-graph-connector-or-a-custom-connector-using-microsoft-graph-apis"></a>Kan gjester bruke Microsoft Graph via Microsoft Security Graph Connector eller en egen definert kobling ved hjelp av Microsoft Graph API-er?
Nei, Azure AD-gjester kan ikke spørre Microsoft Graph om å hente informasjon for en Tenant der de er gjest.

#### <a name="what-intune-policies-apply-to-guests-using-my-powerapps"></a>Hvilke InTune-policyer gjelder gjester ved hjelp av PowerApps?
InTune bruker bare policyer for en brukers hjem Tenant. Hvis Alice@Contoso.com du for eksempel deler en app med Vikram@Fabrikam.com, fortsetter InTune å bruke fabrikam.com-policyer på Virkam-enheten, uansett hvilke powerapps som kjører.

#### <a name="what-connectors-support-guest-access"></a>Hvilke koblinger støtter gjeste tilgang?
Alle koblinger som ikke utfører Azure AD-godkjenning av noen typer, støtter gjeste tilgang. Tabellen nedenfor lister opp alle koblinger som utfører Azure AD-godkjenning og hvilke koblinger som for øyeblikket støtter tilgang til gjester. Mange av disse vil bli oppdatert opp til generell tilgjengelighet.

| **Kobling**                                     | **Støtter gjeste tilgang**                                              |
|---------------------------------------------------|------------------------------------------------------------------------|
| Planlegging av 10to8-avtaler                      | nei                                                                     |
| Adobe Creative Cloud                              | nei                                                                     |
| Adobe Sign                                        | nei                                                                     |
| Asana                                             | nei                                                                     |
| AtBot-administrator                                       | nei                                                                     |
| AtBot Logic                                       | nei                                                                     |
| Azure AD                                          | ja                                                                    |
| Azure Automation                                  | ja                                                                    |
| Azure container Instance                          | ja                                                                    |
| Azure Data Factory                                | ja                                                                    |
| Azure Data Lake                                   | ja                                                                    |
| Azure-DevOps                                      | nei                                                                     |
| Azure Event Grid                                  | nei                                                                     |
| Azure IoT Central                                 | ja                                                                    |
| Azure Key Vault                                   | nei                                                                     |
| Azure-Kusto                                       | ja                                                                    |
| Azure Log Analytics                               | ja                                                                    |
| Azure Resource Manager                            | ja                                                                    |
| Basecamp 2                                        | nei                                                                     |
| Bitbucket                                         | nei                                                                     |
| Bitly                                             | nei                                                                     |
| bttn                                              | nei                                                                     |
| Buffer                                            | nei                                                                     |
| Forretnings sentralt                                  | nei                                                                     |
| CandidateZip                                      | nei                                                                     |
| Capsule CRM                                       | nei                                                                     |
| Sky-administrasjon for PKI                              | nei                                                                     |
| Cognito Forms                                     | nei                                                                     |
| Common Data Service                               | nei                                                                     |
| Common Data Service (eldre)                      | nei                                                                     |
| D & B-optimalisering                                     | nei                                                                     |
| Derdack SIGNL4                                    | nei                                                                     |
| Disqus                                            | nei                                                                     |
| Flett dokument                                    | nei                                                                     |
| Dynamics 365                                      | nei                                                                     |
| Dynamics 365 AI for salg                         | ja                                                                    |
| Dynamics 365 for fin & OPS                        | nei                                                                     |
| Enadoc                                            | nei                                                                     |
| Eventbrite                                        | nei                                                                     |
| Excel online (Business)                           | nei                                                                     |
| Excel online (OneDrive)                           | nei                                                                     |
| Påminnelse om utløp                               | nei                                                                     |
| FreshBooks                                        | nei                                                                     |
| GoToMeeting                                       | nei                                                                     |
| GoToTraining                                      | nei                                                                     |
| GoToWebinar                                       | nei                                                                     |
| Harvest                                           | nei                                                                     |
| HTTP med Azure AD                                | nei                                                                     |
| Infusionsoft                                      | nei                                                                     |
| Inoreader                                         | nei                                                                     |
| Intercom                                          | nei                                                                     |
| JotForm                                           | nei                                                                     |
| kintone                                           | nei                                                                     |
| LinkedIn                                          | nei                                                                     |
| Hub for markedsførings innhold                             | nei                                                                     |
| Middels                                            | nei                                                                     |
| Metatask                                          | nei                                                                     |
| Microsoft Forms                                   | nei                                                                     |
| Microsoft Forms Pro                               | nei                                                                     |
| Microsoft Graph sikkerhet                          | nei                                                                     |
| Microsoft-Kaizala                                 | nei                                                                     |
| Microsoft-synkronisering for skole data                        | nei                                                                     |
| Microsoft StaffHub                                | nei                                                                     |
| Microsoft Forms                                   | ja                                                                    |
| Microsoft to-do (Business)                        | nei                                                                     |
| Muhimbi PDF                                       | nei                                                                     |
| NetDocuments                                      | nei                                                                     |
| Office 365 Grupper                                 | ja                                                                    |
| Office 365 Outlook                                | nei                                                                     |
| Office 365-brukere                                  | ja                                                                    |
| Office 365 Video                                  | nei                                                                     |
| OneDrive                                          | nei                                                                     |
| OneDrive for Business                             | nei                                                                     |
| OneNote (bedrift)                                | nei                                                                     |
| Outlook Customer Manager                          | nei                                                                     |
| Outlook-oppgaver                                     | ja                                                                    |
| Outlook.com                                       | nei                                                                     |
| Paylocity                                         | nei                                                                     |
| Planner                                           | nei                                                                     |
| Plumsail-skjemaer                                    | nei                                                                     |
| Power BI                                          | ja                                                                    |
| Project Online                                    | nei                                                                     |
| ProjectWise utformings integrasjon                    | nei                                                                     |
| ProjectWise-deling                                 | nei                                                                     |
| Services                                        | ja                                                                    |
| SignNow                                           | nei                                                                     |
| Skype for business online                         | nei                                                                     |
| Soft1                                             | nei                                                                     |
| Stormboard                                        | nei                                                                     |
| Survey123                                         | nei                                                                     |
| SurveyMonkey                                      | nei                                                                     |
| Toodledo                                          | nei                                                                     |
| Typeform                                          | nei                                                                     |
| Vimeo                                             | nei                                                                     |
| WebEx-team                                       | nei                                                                     |
| Windows Defender Advanced Threat Protection (ATP) | nei                                                                     |
| Word Online (Business)                            | nei                                                                     |
