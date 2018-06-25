---
title: Å konfigurere miljøsikkerhet | Microsoft Docs
description: Dette emnet forklarer hvordan du konfigurerer miljøsikkerhet.
author: manasmams
manager: kfile
ms.service: powerapps
ms.component: pa-admin
ms.topic: conceptual
ms.date: 03/21/2018
ms.author: manasma
ms.openlocfilehash: d9bd70acaacbbeda98c14337035a233b7c70c181
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/04/2018
ms.locfileid: "34168163"
---
# <a name="configure-environment-security"></a>Å konfigurere miljøsikkerhet
Common Data Service bruker en rollebasert sikkerhetsmodell for å hjelpe med å sikre tilgang til databasen. Dette emnet forklarer hvordan du oppretter sikkerhetsartefaktene du trenger for å sikre en app. Brukeren kontrollerer kjøretidstilgang til data, og disse er adskilt fra miljørollene som styrer miljøadministratorer og miljøopprettere. Du kan se en oversikt over miljøer under [Oversikt over miljøer](environments-overview.md).

## <a name="assign-security-roles-to-users"></a>Å tilordne sikkerhetsroller til brukere
Sikkerhetsroller kontrollerer en brukers tilgang til data gjennom et sett med tilgangsnivåer og tillatelser. Kombinasjonen av tilgangsnivåer og tillatelser som er inkludert i en bestemt sikkerhetsrolle, angir begrensninger på brukerens visning av data og brukerens samhandling med disse dataene.

Hvis du vil tilordne en bruker eller en sikkerhetsgruppe til en miljørolle, kan miljøadministratoren følge disse trinnene i [administrasjonssenteret for PowerApps][1]:

1. Velg miljøet i tabellen for miljøer.

    ![](./media/environment-admin/environment-list-new.png)

2. Velg **Sikkerhet**-fanen.

3. Vis om brukeren allerede finnes i miljøet, ved å velge **vis listen over brukere i miljøet**.
    
    ![](./media/database-security/security-viewuser.png)

4. I tilfelle brukeren ikke finnes kan du legge til brukeren fra administrasjonssenteret for PowerApps. Legg til brukeren ved å oppgi e-postadressen for brukeren, i organisasjonen, og velge **Legg til bruker**.

    ![](./media/database-security/security-adduser.png)

    Vent noen minutter for å finne ut om brukeren er tilgjengelig i listen over brukere i miljøet.
  
5. Velg brukeren fra listen over brukere i miljøet.

    ![](./media/environment-admin/D365-Select-User.png)

6. Tilordne rollen til brukeren.

    ![](./media/environment-admin/D365-Assign-Role.png)

    > [!NOTE]
    > Roller kan for øyeblikket bare tilordnes til brukerne. Vi jobber med ennå med å muligheten om å tilordne en roller til en sikkerhetsgruppe.

7. Velg **OK** for å oppdatere tilordningene til miljørollen.

## <a name="predefined-security-roles"></a>Forhåndsdefinerte sikkerhetsroller
PowerApps-miljøet inneholder forhåndsdefinerte sikkerhetsroller som gjenspeiler vanlige brukeroppgaver med tilgangsnivåer som er definert for å samsvare med målet for beste praksis for sikkerhet, for å gi tilgang til minimum mengde forretningsdata som kreves for å bruke appen.

|Sikkerhetsrolle  |* Databasetillatelser  |Beskrivelse |
|---------|---------|---------|
|Systemadministrator     |  Opprette, lese, skrive, slette, tilpasninger, sikkerhetsroller       | Har full tilgang til å tilpasse eller administrere miljøet, inkludert å opprette, endre og tilordne sikkerhetsroller. Kan vise alle dataene i miljøet. Hvis du vil ha mer informasjon, kan du se [Rettigheter som kreves for tilpassing](https://docs.microsoft.com/dynamics365/customer-engagement/customize/privileges-required-customization)        |
|Å tilpasse et system     | Opprette (egen), lese (egen), skrive (egen), slette (egen), tilpasninger         | Har full tilgang til å tilpasse miljøet. Kan imidlertid bare vise poster for miljøenheter som de oppretter. Hvis du vil ha mer informasjon, kan du se [Rettigheter som kreves for tilpassing](https://docs.microsoft.com/dynamics365/customer-engagement/customize/privileges-required-customization)        |
|Miljøoppretter     |  Ingen       | Kan opprette nye ressurser tilknyttet et miljø, inkludert apper, tilkoblinger, egendefinerte API-er, gatewayer og flyter ved hjelp av Microsoft Flow. Har imidlertid ikke rettigheter til å få tilgang til data i et miljø. Hvis du vil ha mer informasjon, kan du se [Oversikt over miljøer](https://powerapps.microsoft.com/blog/powerapps-environments/)        |
|Common Data Service-bruker     |  Lese, opprette (egen), skrive (egen), slette (egen)       | Kan kjøre en app i miljøet og utføre vanlige oppgaver for postene som de eier.        |
|Representant     | Å handle på vegne av en annen bruker        | Tillater kode for å kjøre som en annen bruker eller representere den.  Brukes vanligvis med en annen sikkerhetsrolle for å gi tilgang til poster. Hvis du vil ha mer informasjon, kan du se [Å representere en annen bruker](https://docs.microsoft.com/dynamics365/customer-engagement/developer/org-service/impersonate-another-user)        |

*Rettighet har globalt omfang om ikke annet er angitt.

- Miljøoppretter-rollen kan ikke bare opprette ressurser i et miljø, men de kan også distribuere appene de bygger i et miljø til andre brukere i organisasjonen. De kan dele appen med individuelle brukere. Du finner mer informasjon i [Dele en app i PowerApps](../maker/canvas-apps/share-app.md).

- Brukerne som oppretter apper som kobles til databasen og som trenger å opprette eller oppdatere enheter og sikkerhetsroller, bør også tilordnes Systemtilpasser-rollen i tillegg til Miljøoppretter-rollen, da Miljøoppretter-rollen ikke har noen rettigheter i databasen.

## <a name="create-or-configure-a-custom-security-role"></a>Å opprette eller konfigurere en egendefinert sikkerhetsrolle
Hvis appen er basert på en egendefinert enhet, må rettigheter angis eksplisitt før brukere kan arbeide i den. Hvis du vil gjøre dette, kan du velge et av disse alternativene.
- Å utvide en eksisterende forhåndsdefinert sikkerhetsrolle, slik at den inkluderer rettigheter til poster basert på den egendefinerte enheten.
- Å opprette en egendefinert sikkerhetsrolle for å administrere rettigheter for brukere av appen.

Det kan hende at miljøet opprettholder postene som kan brukes av flere apper, så det kan hende du trenger flere sikkerhetsroller for å få tilgang til data med ulike rettigheter. Eksempel:
- Det kan hende at noen brukere (Type A) bare trenger å lese, oppdatere og legge ved andre poster slik at sikkerhetsrollen får rettigheter til å lese, skrive og tilføye.
- Andre brukere igjen kan ha behov for alle rettighetene som brukere i Type A har, i tillegg til muligheten til å opprette, legge til, slette og dele. Sikkerhetsrollen får dermed rettigheter til å opprette, lese, skrive, tilføye, slette, tilordne, tilføye til og dele.

Hvis du vil ha mer informasjon om tilgang- og omfangsrettigheter, kan du se [Sikkerhetsroller](https://docs.microsoft.com/dynamics365/customer-engagement/admin/security-roles-privileges#security-roles).

1. Velg miljøet hvor du ønsker å oppdatere en sikkerhetsrolle, i [administrasjonssenteret for PowerApps][1].

    ![](./media/environment-admin/choose-environment-updated.png)

2. Klikk på koblingen på **Details**-fanen for å administrere miljøet i administrasjonssenteret for Dynamics 365.

3. Velg forekomsten (med samme navn som miljøet), og klikk på Åpne.

    ![](./media/database-security/glados-instance-list.png)

4. Klikk på **Innstillinger** i overskriften, og velg **Sikkerhet**

    ![](./media/database-security/dyn365-settings-security.png)

5. Velg **Sikkerhetsroller**

    ![](./media/database-security/dyn365-securityroles.png)

6. Klikk på **Ny**

7. Velg handlinger, for eksempel omfanget lese, skrive eller slette fra utformingsverktøyet for sikkerhetsrolle for å utføre denne handlingen.

8. Velg fanen og søk etter enheten, for eksempel **Egendefinerte enheter**-fanen, for å angi tillatelser for en egendefinert enhet.

9. Velg rettighetene **Les, Skriv, Tilføy**

10. Velg **Lagre og lukk**.



<!--Reference links in article-->
[1]: https://admin.powerapps.com
