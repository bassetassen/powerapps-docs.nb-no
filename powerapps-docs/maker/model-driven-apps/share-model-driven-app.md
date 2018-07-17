---
title: Opplæring for deling av en modelldrevet app med PowerApps | Microsoft Docs
description: Finn ut hvordan du deler en modelldrevet app i denne opplæringen
documentationcenter: ''
author: Mattp123
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: conceptual
ms.component: model
ms.date: 03/21/2018
ms.author: matp
ms.openlocfilehash: 134ae4dfb5fe111c4c40e96efa1e79a3993c4a46
ms.sourcegitcommit: 79b8842fb0f766a0476dae9a537a342c8d81d3b3
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 07/07/2018
ms.locfileid: "37899759"
---
# <a name="tutorial-share-a-model-driven-app-with-powerapps"></a>Opplæring: Å dele en modelldrevet app med PowerApps

[!INCLUDE [powerapps](../../includes/powerapps.md)]-apper bruker rollebasert sikkerhet for deling. De grunnleggende begrepene i rollebasert sikkerhet er at en sikkerhetsrolle inneholder rettigheter som definerer et sett med handlinger som kan utføres i appen. Alle appbrukere må tilordnes til én eller flere forhåndsdefinerte eller egendefinerte roller. Roller kan også tilordnes til grupper. Når en bruker eller gruppe er tilordnet til én av disse rollene, får denne personen eller gruppemedlemmene et sett med rettigheter som er tilknyttet denne rollen. 

I denne opplæringen skal du utføre oppgaver for å dele en modelldrevet app slik at andre kan bruke den. Du lærer hvordan du gjør følgende:
- Å opprette en egendefinert sikkerhetsrolle
- Å tilordne brukere til den egendefinerte sikkerhetsrollen
- Å legge til sikkerhetsrollen i appen

## <a name="prerequisites"></a>Forutsetninger
Hvis du vil dele en app, må du ha [!INCLUDE [powerapps](../../includes/powerapps.md)] rollen miljøadministrator eller systemadministrator. 

## <a name="sign-in-to-powerapps"></a>Logg deg på PowerApps
Logg deg på [PowerApps](https://powerapps.microsoft.com/). Hvis du ikke allerede har en [!INCLUDE [powerapps](../../includes/powerapps.md)]-konto, velger du koblingen **Kom i gang gratis**.

## <a name="share-an-app"></a>Dele en app 
Denne opplæringen følger firmaet Contoso, som driver med pleie og stell av hunder og katter. En app som inneholder en egendefinert enhet for å spore virksomheten med pleie og stell av kjæledyr er allerede opprettet og publisert. Nå må appen deles slik at ansatte av firmaet kan bruke den. Administratoren eller den som opprettet appen kan tilordne én eller flere sikkerhetsroller for brukere og for appen for å dele den. 

## <a name="create-or-configure-a-security-role"></a>Å opprette eller konfigurere en sikkerhetsrolle
[!INCLUDE [powerapps](../../includes/powerapps.md)]Miljøet inneholder [forhåndsdefinerte sikkerhetsroller](#about-predefined-security-roles) som gjenspeiler vanlige brukeroppgaver med tilgangsnivåer som er definert for å samsvare med målet for beste praksis for sikkerhet, for å gi tilgang til minimum mengde forretningsdata som kreves for å bruke appen. Husk at Contoso-appen for pleie og stell av kjæledyr er basert på en egendefinert enhet. Fordi enheten er egendefinert, må rettigheter angis eksplisitt før brukere kan arbeide i den. Hvis du vil gjøre dette, kan du velge et av disse alternativene.
- Å utvide en eksisterende forhåndsdefinert sikkerhetsrolle, slik at den inkluderer rettigheter til poster basert på den egendefinerte enheten. 
- Å opprette en egendefinert sikkerhetsrolle for å administrere rettigheter for brukere av appen. 

Fordi miljøet som opprettholder dyrefrisørpostene, også brukes for andre apper som Contoso-virksomheten driver, opprettes en egendefinert sikkerhetsrolle som er spesifikk for dyrefrisørappen. I tillegg er to forskjellige sett med tilgangsrettigheter nødvendig.
- Dyrefrisørteknikere trenger bare å lese, oppdatere og legge ved andre poster slik at sikkerhetsrollen får rettigheter til å lese, skrive og tilføye. 
- Dyrefrisørplanleggere trenger alle rettighetene som teknikerne har, i tillegg til muligheten til å opprette, legge til, slette og dele. Sikkerhetsrollen får dermed rettigheter til å opprette, lese, skrive, tilføye, slette, tilordne, tilføye til og dele.

Hvis du vil ha mer informasjon om tilgang- og omfangsrettigheter, kan du se [Sikkerhetsroller](https://docs.microsoft.com/dynamics365/customer-engagement/admin/security-roles-privileges#security-roles).

## <a name="create-a-custom-security-role"></a>Å opprette en egendefinert sikkerhetsrolle
1. Velg **Modelldrevne** > **apper** > **…**> **Delingskobling** på [!INCLUDE [powerapps](../../includes/powerapps.md)]-området.
2. Velg **Sikkerhetsinnstilling** fra dialogboksen **Del denne appen** under **Opprett en sikkerhetsrolle**.
3. Velg **Ny** på **Innstillinger**-siden.  

4. Velg handlinger, for eksempel omfanget lese, skrive eller slette fra utformingsverktøyet for sikkerhetsrolle for å utføre denne handlingen. Omfang avgjør hvor dypt eller høyt i miljøets hierarki brukeren kan utføre en bestemt handling. Skriv inn *Dyrefrisørteknikere* i **Rollenavn**-boksen.
5. Velg **Egendefinerte enheter**-fanen, og finn deretter den egendefinerte enheten du vil bruke. I dette eksemplet brukes den egendefinerte enheten med navnet **Kjæledyr**. 
6. Velg hver av følgende rettigheter fire ganger på **Kjæledyr**-raden til globalt organisasjonsomfang ![Globalt organisasjonsomfang](media/share-model-driven-app/organizational-scope-privilege.png) er valgt: **Lese, skrive og tilføye**
   ![Ny sikkerhetsrolle](media/share-model-driven-app/custom-security-role.png)
7. Fordi dyrefrisørappen også har en relasjon med kontoenheten, velger du **Kjernepost**-fanen, og på **Konto**-raden velger du **Les** fire ganger til globalt organisasjonsomfang ![Globalt organisasjonsomfang](media/share-model-driven-app/organizational-scope-privilege.png) er valgt. 
8. Velg **Lagre og lukk**. 
9. Skriv inn *Dyrefrisørplanleggere* i **Rollenavn**-boksen i sikkerhetsrolleutformingen. 
10. Velg **Egendefinerte enheter**-fanen, og finn deretter **Kjæledyr**-enheten. 
11. Velg hver av disse rettighetene fire ganger på **Kjæledyr**-raden til globalt organisasjonsomfang ![Globalt organisasjonsomfang](media/share-model-driven-app/organizational-scope-privilege.png) er valgt: **Opprette, lese, skrive, slette, tilføye, tilføye til, tilordne, dele**
12. Ettersom dyrefrisørappen også har en relasjon med kontoenheten og planleggerne må kunne opprette og endre kontoposter, velger du **Kjernepost**-fanen, og på **Konto**-raden velger du hver av følgende rettigheter fire ganger til globalt organisasjonsomfang ![Globalt organisasjonsomfang](media/share-model-driven-app/organizational-scope-privilege.png) er valgt. 
    **Opprette, lese, skrive, slette, tilføye, tilføye til, tilordne, dele**
13. Velg **Lagre og lukk**.

## <a name="assign-security-roles-to-users"></a>Å tilordne sikkerhetsroller til brukere
Sikkerhetsroller kontrollerer en brukers tilgang til data gjennom et sett med tilgangsnivåer og tillatelser. Kombinasjonen av tilgangsnivåer og tillatelser som er inkludert i en bestemt sikkerhetsrolle, angir begrensninger på brukerens visning av data og brukerens samhandling med disse dataene.

> [!IMPORTANT]
> Hvis du vil bruke en modelldrevet app, må alle brukerne i miljøet minst ha sikkerhetsrollen Common Data Service User. Dette er uavhengig av andre sikkerhetsroller som du måtte tilordne. Sikkerhetsrollen Common Data Service User gir tilstrekkelig rettigheter for å utføre de grunnleggende oppgavene som kreves for å bruke en app.
> Vær oppmerksom på at de som har sikkerhetsrollen Common Data Service User også har skrivetilgang til standardposter for konto-, kontakt- og tilkoblingsenhet, uavhengig av hvem som eier dem. Hvis du ikke ønsker at appbrukerne skal ha rettigheter til disse postene, oppretter du en egendefinert sikkerhetsrolle. Den enkleste måten er å kopiere sikkerhetsrollen Common Data Service User og fjerne de nødvendige rettighetene. Hvis du vil ha mer informasjon, kan du se [Å kopiere en sikkerhetsrolle](https://docs.microsoft.com/dynamics365/customer-engagement/admin/copy-security-role)

### <a name="assign-a-security-role-to-pet-grooming-technicians"></a>Tilordne en sikkerhetsrolle til dyrefrisørteknikere
1. Velg **Sikkerhetsbrukere** fra dialogboksen **Del denne appen** under **Tilordne brukere til sikkerhetsrollen**.
2. Velg dyrefrisørene fra listen som vises.
3. Velg **Behandle roller**.

    ![Behandle roller](media/share-model-driven-app/select-users-for-security-roles.png)

4. Når dialogboksen **Administrer brukerroller** vises, velger du sikkerhetsrollen **Dyrefrisørteknikere** som du opprettet tidligere, og velger deretter **OK**.

### <a name="assign-a-security-role-to-pet-grooming-schedulers"></a>Tilordne en sikkerhetsrolle til dyrefrisørplanleggere
1. Velg **Sikkerhetsbrukere** fra dialogboksen **Del denne appen** under **Tilordne brukere til en sikkerhetsrolle**.
2. Velg dyrefrisørplanleggerne fra listen som vises.
3. Velg **Behandle roller**.
4. Når dialogboksen **Administrer brukerroller** vises, velger du sikkerhetsrollen **Planleggere i dyrefrisørvirksomheten** som du opprettet tidligere, og velger deretter **OK**.


## <a name="add-security-roles-to-the-app"></a>Legge til sikkerhetsroller i appen
Deretter må en eller flere sikkerhetsroller tilordnes til appen. Brukere får tilgang til appene basert på sikkerhetsroller som de er tilordnet til.
1. Velg **Mine apper** fra dialogboksen **Del denne appen** under **Legg til sikkerhetsrollen i appen**.
2. Velg **Flere alternativer (...)**  og deretter **Behandle roller** i nedre høyre hjørne av appflisen for Contoso-appen for dyrefrisørvirksomheten.

    ![Behandle roller for appen](media/share-model-driven-app/manage-roles.png)

4. Du kan bruke **Roller**-delen til velge om du vil gi apptilgang til alle sikkerhetsroller eller valgte roller. Velg rollene **Dyrefrisørplanleggere** og **Dyrefrisørteknikere** som du opprettet tidligere.

    ![Velge sikkerhetsroller for appen](media/share-model-driven-app/app-security-roles.png)

5. Velg **Lagre**.
 
## <a name="share-the-link-to-your-app"></a>Dele koblingen til appen
1. Kopier nettadressen som vises i dialogboksen **Del denne appen** under **Del koblingen til appen direkte med brukere**.
 
2. Velg **Lukk**.
3. Lim inn appens nettadresse slik at brukerne kan få tilgang til den, for eksempel på et SharePoint-område eller sende det via e-post.

![Dele koblingen](media/share-model-driven-app/share-model-driven-URL.PNG)

Du kan også finne appens nettadresse på **Egenskaper**-fanen i apputformingen. 
    
![Kopiere nettadressen til en app](media/share-model-driven-app/app-designer-copy-web-url.png)

## <a name="about-predefined-security-roles"></a>Om forhåndsdefinerte sikkerhetsroller
Disse forhåndsdefinerte rollene er tilgjengelige med et [!INCLUDE [powerapps](../../includes/powerapps.md)]-miljø.


|Sikkerhetsrolle  |*Rettigheter  |Beskrivelse |
|---------|---------|---------|
|Miljøoppretter     |  Ingen       | Kan opprette nye ressurser tilknyttet et miljø, inkludert apper, tilkoblinger, egendefinerte API-er, gatewayer og flyter ved hjelp av Microsoft Flow. Har imidlertid ikke rettigheter til å få tilgang til data i et miljø. Hvis du vil ha mer informasjon, kan du se [Oversikt over miljøer](https://powerapps.microsoft.com/blog/powerapps-environments/)        |
|Systemadministrator     |  Opprette, lese, skrive, slette, tilpasninger, sikkerhetsroller       | Har full tilgang til å tilpasse eller administrere miljøet, inkludert å opprette, endre og tilordne sikkerhetsroller. Kan vise alle dataene i miljøet. Hvis du vil ha mer informasjon, kan du se [Rettigheter som kreves for tilpassing](https://docs.microsoft.com/dynamics365/customer-engagement/customize/privileges-required-customization)        |
|Å tilpasse et system     | Opprette (egen), lese (egen), skrive (egen), slette (egen), tilpasninger         | Har full tilgang til å tilpasse miljøet. Kan imidlertid bare vise poster for miljøenheter som de oppretter. Mer informasjon: [Rettigheter som kreves for tilpassing](https://docs.microsoft.com/dynamics365/customer-engagement/customize/privileges-required-customization)        |
|Common Data Service-bruker     |  Lese, opprette (egen), skrive (egen), slette (egen)       | Kan kjøre en app i miljøet og utføre vanlige oppgaver for postene som de eier.        |
|Representant     | Å handle på vegne av en annen bruker        | Tillater kode for å kjøre som en annen bruker eller representere den.  Brukes vanligvis med en annen sikkerhetsrolle for å gi tilgang til poster. Hvis du vil ha mer informasjon, kan du se [Å representere en annen bruker](https://docs.microsoft.com/dynamics365/customer-engagement/developer/org-service/impersonate-another-user)        |

*Rettighet har globalt omfang om ikke annet er angitt.

## <a name="next-steps"></a>Neste trinn
[Hurtigstart: Kjøre en modelldreven app på en mobilenhet](../../user/run-app-client-model-driven.md)



