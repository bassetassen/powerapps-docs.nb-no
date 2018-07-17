---
title: Administrer miljøer | Microsoft Docs
description: Finn ut hvordan du administrer miljøer i PowerApps, inkludert oppretting, tildeling av nytt navn, sletting og sikkerhet
author: manasmams
manager: kfile
ms.service: powerapps
ms.component: pa-admin
ms.topic: conceptual
ms.date: 03/21/2018
ms.author: manasma
ms.openlocfilehash: 7fb35c1c59062b892fdd8e3a905d3ee485f6cf61
ms.sourcegitcommit: 26932abc6fcdc5e6723b64b506532bb182ab3f8d
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/27/2018
ms.locfileid: "37026238"
---
# <a name="administer-environments-in-powerapps"></a>Administrer miljøer i PowerApps
I [administrasjonssenteret for PowerApps][1] kan du administrere miljøer du har opprettet, samt miljøer der du har blitt lagt til i rollen som miljøadministrator eller systemansvarlig. Du kan utføre disse administrative handlingene fra administrasjonssenteret:

* Opprett miljøer
* Gi nytt navn til miljøer
* Legg til eller fjern en bruker eller gruppe fra enten rollen miljøadministrator eller miljøoppretter.
* Klargjør en Common Data Service-database for miljøet.
* Angi policyer for hindring av datatap.
* Angi sikkerhetspolicyer for databasen (som åpen eller begrenset av databaseroller).
* Medlemmer av den globale administratorrollen for Azure AD-leieren (inkluderer globale administratorer for Office 365) kan også administrere alle miljøer som er opprettet i leieren, og angi policyer for hele leierområdet.

## <a name="access-the-powerapps-admin-center"></a>Få tilgang til administrasjonssenteret for PowerApps
Slik får du tilgang til administrasjonssenteret for PowerApps:

* Gå direkte til [admin.powerapps.com][1], ELLER

* Gå til [powerapps.com][2], og velg deretter tannhjulikonet i navigasjonstoppteksten.

    ![](./media/environment-admin/powerapps-gear-dropdown.png)

Hvis du vil behandle et miljø i administrasjonssenteret for PowerApps, må du ha en av disse rollene:

* Miljøadministrator- eller systemansvarligrollen for miljøet, ELLER

* Rollen som global administrator for din Azure AD- eller Office 365-leier.

Du må også ha en PowerApps Plan 2- eller Microsoft Flow Plan 2-lisens for å få tilgang til administrasjonssenteret. Hvis du vil ha mer informasjon, kan du se [PowerApps-prissiden][3].

> [!IMPORTANT]
> Eventuelle endringer du gjør i administrasjonssenteret for PowerApps, påvirker [administrasjonssenteret for Microsoft Flow][4] og omvendt.

## <a name="create-an-environment"></a>Opprette et miljø
For instruksjoner om hvordan du oppretter et miljø, kan du se [Hurtigstart: opprette et miljø](create-environment.md).

## <a name="view-your-environments"></a>Vis miljøene dine
Når du åpner administrasjonssenteret, vises Miljøer-fanen som standard. Den viser en liste over alle miljøene som du er miljøadministrator for (som vist under):

![](./media/environment-admin/environment-list-new.png)

Hvis du er medlem av rollen som global administrator for Azure AD- eller Office 365-leier, vises alle miljøer som har blitt opprettet av brukere i leieren din fordi du er automatisk miljøadministrator for alle.

## <a name="rename-your-environment"></a>Gi nytt navn til miljøet ditt

> [!IMPORTANT]
> Følg disse trinnene i denne inndelingen for å gi et nytt navn til et produksjonsmiljø som ikke inneholder en database. Du kan ikke gi nytt navn på prøveversjonsmiljøer, og du må bruke administrasjonssenteret for Dynamics 365 for å gi nytt navn på produksjonsmiljøer som inneholder en database.

1. Åpne [administrasjonssenteret for PowerApps][1], finn miljøet som du vil gi et nytt navn til, på listen, og klikk eller trykk på det.

    ![](./media/environment-admin/environment-list-updated3.png)

2. Klikk eller trykk på **Detaljer**.

    ![](./media/environment-admin/environment-rename-details-2.png)
3. Skriv inn navnet i tekstboksen **Navn**, og klikk deretter på **Lagre**.

    ![](./media/environment-admin/environment-rename-2.png)

    Hvis du har opprettet databasen i miljøet, vil du ikke se dette alternativet. Du kan gi miljøet nytt navn i administrasjonssenteret for Dynamics 365 ved å klikke på koblingen i **Detaljer**-fanen.

    ![](./media/environment-admin/Delete-D365AdminCenter.png)


## <a name="delete-your-environment"></a>Slett miljøet ditt
1. Klikk eller trykk på miljøet du vil slette, i [administrasjonssenteret for PowerApps][1].

    ![](./media/environment-admin/environment-list-updated3.png)
2. Klikk eller trykk på **Detaljer**.

    ![](./media/environment-admin/environment-rename-details-2.png)
3. Klikk eller trykk på **Slett miljø** for å slette miljøet ditt.

    ![](./media/environment-admin/delete-environment-2.png)


## <a name="create-a-common-data-service-database-for-an-environment"></a>Opprett en Common Data Service-database for et miljø
Hvis et miljø ikke allerede har en database, kan en miljøadministrator opprette en i [administrasjonssenteret for PowerApps][1] ved å følge disse trinnene. Bare brukere med en lisens for PowerApps Plan 2 kan opprette Common Data Service-databaser.

1. Velg et miljø i tabellen for miljøer.

    ![](./media/environment-admin/choose-environment-updated.png)
2. Velg fanen **Detaljer**.
3. Velg **Opprett en database**.

    ![](./media/environment-admin/Create-DB-From-Details.png)


Når du har opprettet en database, velger du en sikkerhetsmodell. Hvis du vil ha mer informasjon, kan du se [Configure environment security](database-security.md) (Konfigurer miljøsikkerhet).

## <a name="manage-security-for-your-environments"></a>Administrer sikkerhet for miljøene dine

### <a name="environment-permissions"></a>Miljøtillatelser
I et miljø er alle brukerne i Azure AD-leieren brukere av dette miljøet. Men hvis de skal kunne spille en mer privilegert rolle, må de legges til i en bestemt miljørolle. Miljøer har to innebygde roller som gir tilgang til tillatelser i et miljø:

* Rollen **Miljøadministrator** (eller rollen **Systemadministrator**) kan utføre alle administrative handlinger i et miljø, inkludert følgende:
    * Legg til eller fjern en bruker enten fra rollen Miljøadministrator eller Miljøoppretter.

    * Klargjør en Common Data Service-database for miljøet.

    * Vis og administrer alle ressurser som er opprettet i et miljø.

    * Angi policyer for hindring av datatap. Hvis du vil ha mer informasjon, kan du se [Policyer for hindring av datatap](prevent-data-loss.md).

  > [!NOTE]
  > Hvis miljøet har databasen, må du tilordne brukere rollen **Systemadministrator** i stedet for rollen **Miljøadministrator**.

* Rollen **Miljøoppretter** kan opprette ressurser i et miljø, inkludert apper, tilkoblinger, egendefinerte koblinger, gatewayer og flyter ved hjelp av Microsoft Flow. Miljøopprettere kan også distribuere apper de bygger i et miljø, til andre brukere i organisasjonen. De kan dele appen med individuelle brukere, sikkerhetsgrupper eller alle brukerne i organisasjonen. Hvis du vil ha mer informasjon, kan du se [Dele en app i PowerApps](../maker/canvas-apps/share-app.md).

Hvis du vil tilordne en bruker eller en sikkerhetsgruppe til en miljørolle, kan miljøadministratoren følge disse trinnene i [administrasjonssenteret for PowerApps][1]:

1. Velg miljøet i tabellen for miljøer.

    ![](./media/environment-admin/choose-environment-updated.png)
2. Velg **Sikkerhet**-fanen.
3. Hvis ingen database er opprettet i miljøet:

    a. Velg enten rollen **Miljøadministrator** eller **Miljøoppretter**.

    ![](./media/environment-admin/choose-environment-role.png)

    b. Angi navnene på en eller flere brukere eller sikkerhetsgrupper i Azure Active Directory, eller angi at du vil legge til hele organisasjonen.

    ![](./media/environment-admin/enter-name.png)

    c. Velg **Lagre** for å oppdatere tilordningene til miljørollen.

4. Hvis en database er opprettet i miljøet:

    a. Legg til brukeren i miljøet, og klikk på koblingen for å tilordne en rolle for brukeren.

    ![](./media/database-security/security-adduser.png)

    b. Velg brukeren fra listen over brukere i miljøet/forekomsten.

    ![](./media/environment-admin/D365-Select-User.png)

    c. Tilordne rollen til brukeren.

    ![](./media/environment-admin/D365-Assign-Role.png)

    d. Velg **OK** for å oppdatere tilordningene til miljørollen.


> [!NOTE]
> Brukere eller grupper som er tilordnet disse miljørollene, blir ikke automatisk gitt tilgang til miljøets database (hvis den finnes). De må gis tilgang separat av en eier av databasen. Hvis du vil ha mer informasjon, kan du se [Configure environment security](database-security.md) (Konfigurer miljøsikkerhet).  
>
>

### <a name="database-security"></a>Databasesikkerhet
Muligheten til å opprette og endre et databaseskjema og koble til dataene som er lagret i en database som er klargjort i miljøet ditt, styres av databasens brukerroller og tillatelsessett. Du kan administrere brukerroller og tillatelsessett for miljødatabasen fra **Brukerroller**- og **Tillatelsessett**-delen på **Sikkerhet**-fanen. Hvis du vil ha mer informasjon, kan du se [Konfigurer databasesikkerhet](database-security.md).

![](./media/environment-admin/D365-Assign-Role.png)

## <a name="data-policies"></a>Datapolicyer
Organisasjonens data må beskyttes slik at de ikke deles med grupper som ikke skal ha tilgang til dem. Hvis du vil beskytte disse dataene, kan du opprette og håndheve policyene som definerer hvilke tjenester for forbrukere og koblingsspesifikke forretningsdata som kan deles med andre. Policyer som angir hvordan data kan deles, er referert til som policyer for hindring av datatap (DLP). Du kan administrere policyene for hindring av datatap for miljøene dine i **Datapolicyer**-delen i [administrasjonssenteret for PowerApps][1].  Hvis du vil ha mer informasjon, kan du se [Policyer for hindring av datatap](prevent-data-loss.md).

![](./media/environment-admin/data-policies.png)

## <a name="frequently-asked-questions"></a>Ofte stilte spørsmål
### <a name="how-many-environments-and-databases-can-i-create"></a>Hvor mange miljøer og databaser kan jeg opprette?
Du kan opprette opptil to prøveversjonsmiljøer og to produksjonsmiljøer, avhengig av lisensen. [Se her](environments-overview.md#creating-an-environment) for mer informasjon. Hver bruker kan opprette opptil to prøveversjonsmiljøer og to produksjonsmiljøer, avhengig av lisensen. 

### <a name="which-license-includes-common-data-service"></a>Hvilken lisens inkluderer Common Data Service?
PowerApps Plan 2.  Se [PowerApps-prissiden][3] for mer informasjon om alle abonnementer som inkluderer denne lisensen.

### <a name="while-trying-to-create-a-new-environment-i-am-getting-an-error-how-should-i-resolve-it"></a>Jeg får en feil når jeg prøver å opprette et nytt miljø. Hvordan løser jeg det?
Hvis du får feilmeldingen «Enten så støtter ikke planen din den valgte miljøtypen, eller så har du nådd grensen for denne miljøtypen», kan det bety en av to ting:

1. Du har allerede brukt kvoten for å opprette en bestemt type miljøer. Hvis du for eksempel opprettet et prøveversjonsmiljø og fikk denne feilmeldingen, betyr det at du allerede har opprettet to prøveversjonsmiljøer. Du kan vise alle miljøer i [administrasjonssenteret for PowerApps ][1].
Hvis du vil, kan du slette det eksisterende miljøet av denne bestemte typen og opprette et nytt. Men pass på at du ikke mister data, apper, flyter og andre ressurser som du vil beholde.

2. Du har ikke en kvote for å opprette den bestemte typen av miljøet. [Her](environments-overview.md#creating-an-environment) kan du sjekke hvilket type miljø du kan opprette.

Hvis du får en annen feilmelding, eller hvis du har flere spørsmål, kan du ta kontakt med oss [her][5].

### <a name="while-trying-to-create-a-database-in-an-environment-i-am-getting-an-error-how-should-i-resolve-it"></a>Jeg får en feil når jeg prøver å opprette en database i et miljø. Hvordan løser jeg det?
Du kan få en feil når du prøver å opprette en database i følgende scenarioer:

1. **Standardmiljø**: For øyeblikket støttes ikke oppretting av en database i et standardmiljø i leieren. 

2. **Miljø for individuell bruk**: Du får et miljø for individuell bruk når du registrerer deg via PowerApps Community Plan. Hvis du ikke har opprettet databasen ennå, kan du for øyeblikket ikke klargjøre en database i miljøet for individuell bruk. 
    
Vi arbeider med å aktivere alle scenarioene over.
Hvis du får andre feilmeldinger, eller hvis du har flere spørsmål, kan du ta kontakt med oss [her][5]

### <a name="when-will-my-trial-environment-expire"></a>Når utløper prøveversjonsmiljøet mitt?   
Prøveversjonsmiljøet utløpet 30 dager etter at det ble opprettet. Hvis du ikke vil at miljøet ditt skal utløpe, vil det finnes metoder for å konvertere det til et produksjonsmiljø. Denne funksjonen kommer snart, og prøveversjonsmiljøer vil ikke utløpe før funksjonen er på plass.

### <a name="does-my-current-database-created-with-previous-version-of-the-common-data-service-also-gets-counted-in-the-quota"></a>Telles den nåværende databasen min (opprettet med tidligere versjon av Common Data Service) også i kvoten?
Hvis du hadde en database (opprettet med tidligere versjon av Common Data Service), telles også denne med i kvoten for produksjonsmiljøet ditt. Hvis du nå oppretter en database i et miljø (opprettet før 15. mars 2018), telles også denne med som produksjonsmiljø.

### <a name="can-i-rename-an-environment"></a>Kan jeg gi nytt navn til et miljø?
Ja, denne funksjonen er tilgjengelig i administrasjonssenteret for PowerApps. Se [Miljøadministrasjon](environments-administration.md#rename-your-environment) for mer informasjon.

### <a name="can-i-delete-an-environment"></a>Kan jeg slette et miljø?
Ja, denne funksjonen er tilgjengelig i administrasjonssenteret for PowerApps. Se [Miljøadministrasjon](environments-administration.md#delete-your-environment) for mer informasjon.
Obs! Du kan for øyeblikket ikke slette et produksjonsmiljø med en database (med siste versjon av Common Data Service). Denne funksjonen kommer snart!

### <a name="as-an-environment-admin-can-i-view-and-manage-all-resources-apps-flows-apis-etc-for-an-environment"></a>Kan jeg vise og behandle alle ressurser (apper, flyter, API-er og så videre) for et miljø som miljøadministrator?
Ja, muligheten til å vise apper og flyter for et miljø er tilgjengelig i administrasjonssenteret for PowerApps. Se [Vis apper](admin-view-apps.md) for mer informasjon.



<!--Reference links in article-->
[1]: https://admin.powerapps.com
[2]: https://web.powerapps.com
[3]: https://powerapps.microsoft.com/pricing/
[4]: https://admin.flow.microsoft.com
[5]: https://go.microsoft.com/fwlink/?linkid=871628