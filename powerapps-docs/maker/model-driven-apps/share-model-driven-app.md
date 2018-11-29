---
title: Opplæring for deling av en modelldrevet app med PowerApps | MicrosoftDocs
description: I denne opplæringen kan du lære hvordan du deler en modelldrevet app
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
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="tutorial-share-a-model-driven-app-with-powerapps"></a>Opplæring: Dele en modelldrevet app med PowerApps

[!INCLUDE [powerapps](../../includes/powerapps.md)]-apper bruker rollebasert sikkerhet for deling. Det grunnleggende konseptet i rollebasert sikkerhet er at en sikkerhetsrolle inneholder rettighetene som angir et sett med handlinger som kan utføres i appen. Alle appbrukere må være tilordnet til én eller flere forhåndsdefinerte eller egendefinerte roller. Roller kan også tilordnes til team. Når en bruker eller et team er tilordnet en av disse rollene, får personen eller teammedlemmene settet med rettigheter som er tilknyttet denne rollen. 

I denne opplæringen utfører du oppgavene for deling av en modelldrevet app, slik at andre kan bruke den. Du lærer hvordan du gjør følgende.
- Opprette en egendefinert sikkerhetsrolle
- Tilordne brukere til den egendefinerte sikkerhetsrollen
- Tilordne sikkerhetsrollen til en app

## <a name="prerequisites"></a>Forhåndskrav
For å dele en app må du ha rollen som [!INCLUDE [powerapps](../../includes/powerapps.md)]-miljøadministrator eller -systemansvarlig. 

## <a name="sign-in-to-powerapps"></a>Logg på PowerApps
Logg på [PowerApps](https://powerapps.microsoft.com/). Hvis du ikke allerede har en [!INCLUDE [powerapps](../../includes/powerapps.md)]-konto, velger du **Kom i gang gratis**-koblingen.

## <a name="share-an-app"></a>Del en app 
Opplæringen følger selskapet Contoso, som er en virksomhet for kjæledyrstell som pleier hunder og katter. En app som inneholder en egendefinert enhet for å spore virksomheten for kjæledyrstell, er allerede opprettet og publisert. Nå må appen deles slik at de ansatte i virksomheten kan bruke den. For å dele appen tilordner en administrator eller apputvikler én eller flere sikkerhetsroller til brukerne og appen. 

## <a name="create-or-configure-a-security-role"></a>Opprette eller konfigurere en sikkerhetsrolle
[!INCLUDE [powerapps](../../includes/powerapps.md)]-miljøet omfatter [forhåndsdefinerte sikkerhetsroller](#about-predefined-security-roles) som gjenspeiler vanlige kundeoppgaver med tilgangsnivåer definert slik at de passer målet sikkerhet gode fremgangsmåter for å gi tilgang til minimumsmengden av forretningsdata som kreves for å bruke programmet. Husk at Contoso-appen for kjæledyrstell er basert på en egendefinert enhet. Siden enheten er egendefinert, må rettigheter angis eksplisitt før brukere kan arbeide med den. Du kan velge ett av følgende for å gjøre dette.
- Vis en eksisterende forhåndsdefinert sikkerhetsrolle, slik at den inneholder rettigheter til oppføringer som er basert på den egendefinerte enheten. 
- Opprett en egendefinert sikkerhetsrolle for å administrere tilgangsrettigheter for brukere av appen. 

Fordi miljøet som opprettholder oppføringene for kjæledyrstell, også brukes til andre apper Contoso-virksomheten kjører, opprettes en egendefinert sikkerhetsrolle spesifikk for appen for kjæledyrstell. I tillegg kreves to forskjellige sett med tilgangsrettigheter.
- Teknikere hos kjæledyrforretningen trenger bare å lese, oppdatere og tilknytte andre oppføringer, slik at sikkerhetsrollen har lese-, skrive- og tilføyingsrettigheter. 
- Planleggere trenger alle rettigheter som teknikerne har, pluss muligheten til å opprette, legge til, slette og dele, slik at sikkerhetsrollen deres har rettigheter til å opprette, lese, skrive, tilføye, slette, tilordne, tilføye i og dele rettigheter.

Hvis du vil ha mer informasjon om tilgangs- og omfangsrettigheter, kan du se [Sikkerhetsroller](https://docs.microsoft.com/dynamics365/customer-engagement/admin/security-roles-privileges#security-roles).

## <a name="create-a-custom-security-role"></a>Opprette en egendefinert sikkerhetsrolle
1. På [!INCLUDE [powerapps](../../includes/powerapps.md)]-nettstedet velger du **Apper** > **…**> **Del kobling**.
2. Fra dialogboksen **Del denne appen** under **Opprett en sikkerhetsrolle** velger du **Sikkerhetsinnstilling**.
3. På **Innstillinger**-siden velger du **Ny**.  

4. Fra designeren for sikkerhetsrolle kan du velge handlinger, for eksempel lese, skrive eller slette, og omfanget for å utføre handlingen. Omfang avgjør hvor dypt eller høy i miljøhierarkiet brukeren kan utføre en bestemt handling. I **Rollenavn**-boksen angir du *Teknikere hos kjæledyrforretning*.
5. Velg kategorien **Egendefinerte enheter**, og deretter finner du den egendefinerte enheten du vil ha. I dette eksemplet brukes den egendefinerte enheten kalt **Kjæledyr**. 
6. På **Kjæledyr**-raden, velg hver av følgende rettigheter fire ganger til det globale organisasjonsomfanget ![globalt organisasjonsomfang](media/share-model-driven-app/organizational-scope-privilege.png) er valgt: **Les, Skriv og Tilføy**
> [!div class="mx-imgBorder"] 
> ![Ny sikkerhetsrolle.](media/share-model-driven-app/custom-security-role.png)
7. Fordi kjæledyrappen også har en relasjon til forretningsforbindelsesenheten, kan du velge kategorien **Kjerneoppføringer** og på den **Forretningsforbindelse**-raden velge **Lese** fire ganger til det globale organisasjonsomfanget ![globalt organisasjonsomfang](media/share-model-driven-app/organizational-scope-privilege.png) er valgt. 
8. Velg **Lagre og lukk**. 
9. I redigeringsprogrammet for sikkerhetsrolle i **Rollenavn**-boksen skriver du inn *Planleggere hos kjæledyrforretning*. 
10. Velg kategorien **Egendefinerte enheter**, og deretter finner du **Kjæledyr**-enheten. 
11. På **Kjæledyr**-raden, velg hver av følgende rettigheter fire ganger til det globale organisasjonsomfanget ![globalt organisasjonsomfang](media/share-model-driven-app/organizational-scope-privilege.png) er valgt: **Opprett, Les, Skriv, Slett, Tilføy, Tilføy i, Tilordne, Del**
12. Fordi kjæledyrappen også har en relasjon til forretningsforbindelsesenheten, og planleggere må kunne opprette og endre forretningsforbindelsesoppføringer, kan du velge kategorien **Kjerneoppføringer** og på den **Forretningsforbindelse**-raden velge hver av følgende rettigheter fire ganger til det globale organisasjonsomfanget ![globalt organisasjonsomfang](media/share-model-driven-app/organizational-scope-privilege.png) er valgt. 
    **Opprette, Lese, Skrive, Slette, Tilføye, Tilføye i, Tilodrne, Dele**
13. Velg **Lagre og lukk**.

## <a name="assign-security-roles-to-users"></a>Tilordne sikkerhetsroller til brukere
Sikkerhetsroller kontrollere en brukers tilgang til data via et sett med tilgangsnivåer og tillatelser. Kombinasjonen av tilgangsnivåer og tillatelser som er inkludert i en bestemt sikkerhetsrolle, angir begrensninger for brukerens visning av data og samhandling med disse dataene.

### <a name="assign-a-security-role-to-pet-grooming-technicians"></a>Tilordne en sikkerhetsrolle til teknikere i kjæledyrforretningen
1. Fra dialogboksen **Del denne appen** under **Tilordne brukere til sikkerhetsrollen** velger du **Sikkerhetsbrukere**.
2. I listen som vises, velger du kjæledyrpleierne.
3. Velg **Behandle roller**.

    > [!div class="mx-imgBorder"] 
    > ![Behandle roller](media/share-model-driven-app/select-users-for-security-roles.png)

4. I dialogboksen **Behandle brukerroller** velger du sikkerhetsrollen **Teknikere hos kjæledyrforretning** du opprettet tidligere, og deretter velger du **OK**.

### <a name="assign-a-security-role-to-pet-grooming-schedulers"></a>Tilordne en sikkerhetsrolle til planleggere i kjæledyrforretningen
1. Fra dialogboksen **Del denne appen** under **Tilordne brukere til en sikkerhetsrolle** velger du **Sikkerhetsbrukere**.
2. I listen som vises, velger du planleggerne hos kjæledyrforretningen.
3. Velg **Behandle roller**.
4. I dialogboksen **Behandle brukerroller** velger du sikkerhetsrollen **Planleggere hos kjæledyrforretning** du opprettet tidligere, og deretter velger du **OK**.


## <a name="add-security-roles-to-the-app"></a>Legge til sikkerhetsroller for appen
Nå må én eller flere sikkerhetsroller tilordnes i appen. Brukerne vil ha tilgang til apper basert på sikkerhetsrollene som de er tilordnet.
1. Fra dialogboksen **Del denne appen** under **Legg til sikkerhetsrollen i appen** velger du **Mine apper**.
2. I nedre høyre hjørne av appflisen i Contoso-appen for kjæledyrstell velger du **Flere alternativer (...)** og deretter **Behandle roller**.

    ![Behandle roller for appen](media/share-model-driven-app/manage-roles.png)

4. I **Roller**-delen kan du velge om du vil gi appen til alle sikkerhetsroller eller utvalgte roller. Velg rollene **Planleggere hos kjæledyrforretning** og **Teknikere hos kjæledyrforretning** du opprettet tidligere.

    > [!div class="mx-imgBorder"] 
    > ![Velge sikkerhetsroller for appen](media/share-model-driven-app/app-security-roles.png)

5. Velg **Lagre**.
 
## <a name="share-the-link-to-your-app"></a>Dele koblingen til appen
1. Fra dialogboksen **Del denne appen** under **Del koblingen til appen din direkte med brukere** kopierer du URL-adressen som vises.
 
2. Velg **Lukk**.
3. Lim inn URL-adressen til appen på et sted slik at brukerne dine kan få tilgang til den, for eksempel ved å legge den inn på et SharePoint-område eller sende via e-post.

> [!div class="mx-imgBorder"] 
> ![Del koblingen](media/share-model-driven-app/share-model-driven-URL.PNG)

Du kan også finne URL-adressen til appen i kategorien **Egenskaper** i apputformingen. 

> [!div class="mx-imgBorder"] 
> ![Kopier URL-adresse for app](media/share-model-driven-app/app-designer-copy-web-url.png)

## <a name="about-predefined-security-roles"></a>Om forhåndsdefinerte sikkerhetsroller
Disse forhåndsdefinerte rollene er tilgjengelig med et [!INCLUDE [powerapps](../../includes/powerapps.md)]-miljø.


|Sikkerhetsrolle  |*Rettigheter  |Beskrivelse |
|---------|---------|---------|
|Miljøoppretter     |  Ingen       | Kan opprette nye ressurser som er knyttet til et miljø, inkludert apper, tilkoblinger, egendefinerte API-er, gatewayer og strømmer, ved hjelp av Microsoft Flow. Har imidlertid ikke rettigheter til å få tilgang til data i et miljø. Mer informasjon: [Oversikt over miljøer](https://powerapps.microsoft.com/blog/powerapps-environments/)        |
|Systemansvarlig     |  Opprette, lese, skrive, slette, tilpassinger, sikkerhetsroller       | Har full tillatelse til å tilpasse eller administrere miljøet, inkludert opprette, endre og tilordne sikkerhetsroller. Kan vise alle data i miljøet Mer informasjon: [Rettigheter som kreves for tilpassing](https://docs.microsoft.com/dynamics365/customer-engagement/customize/privileges-required-customization)        |
|Systemtilpasser     | Opprette (selv), lese (selv), skrive (selv), slette (selv), tilpassinger         | Har alle tillatelser til å tilpasse miljøet Kan imidlertid bare vise oppføringer for miljøenheter de oppretter. Mer informasjon: [Rettigheter som kreves for tilpassing](https://docs.microsoft.com/dynamics365/customer-engagement/customize/privileges-required-customization)        |
|Common Data Service-bruker     |  Lese, opprette (selv), skrive (selv), slette (selv)       | Kan kjøre en app i miljøet og utføre vanlige oppgaver for oppføringene som de eier.        |
|Representant     | Handle på vegne av en annen bruker        | Kan kjøre kode som en annen bruker eller representere.  Brukes vanligvis med en annen sikkerhetsrolle for å gi tilgang til oppføringer. Mer informasjon: [Representere en annen bruker](https://docs.microsoft.com/dynamics365/customer-engagement/developer/org-service/impersonate-another-user)        |

*Rettighet er globalt omfang, med mindre annet er oppgitt.

## <a name="next-steps"></a>Neste trinn
[Kjør en modelldrevet app på en mobilenhet](../../user/run-app-client-model-driven.md)



