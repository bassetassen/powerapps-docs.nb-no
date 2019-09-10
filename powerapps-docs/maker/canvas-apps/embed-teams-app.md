---
title: Bygge inn en PowerApps-app i Teams | Microsoft Docs
description: Du kan bygge inn en app som er opprettet i PowerApps i Microsoft Teams, for å dele den.
author: jimholtz
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 09/09/2019
ms.author: jimholtz
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: ba08437dc144fc81aa9748163b1005222735cb69
ms.sourcegitcommit: 86ed3ad487f31721155758aa9d87134bb10f8437
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 09/09/2019
ms.locfileid: "70842250"
---
# <a name="embed-a-powerapps-app-in-teams"></a>Bygge inn en PowerApps-app i Teams 

Du kan dele en PowerApps som du har opprettet ved å bygge det inn direkte i Microsoft Teams. Når du er ferdig, kan **+** brukerne velge å legge til **appen din i en gruppe kanaler** eller samtaler i teamet du er i. Appen vises som en flis under **kategorier for teamet ditt**. 

En administrator kan laste opp appen slik at den vises for **alle** teamene i leieren under **alle faner-delen**. Se [dele en app i Microsoft Teams](https://docs.microsoft.com/en-us/power-platform/admin/embed-app-teams).

> [!NOTE]
> Egen definerte app-policyer for Team må være angitt til å tillate opplasting av egen definerte apper. Hvis du ikke kan bygge inn appen i Teams, må du kontakte administratoren for å finne ut om de har konfigurert [egen definerte App-innstillinger](https://docs.microsoft.com/MicrosoftTeams/teams-custom-app-policies-and-settings#custom-app-policy-and-settings). 

## <a name="prerequisites"></a>Forutsetninger

- [Få en PowerApps-lisens](https://docs.microsoft.com/power-platform/admin/pricing-billing-skus)
- Opprettet en lerrets app

## <a name="locate-your-powerapps-guid"></a>Finn din PowerApps GUID

Finn og noter deg PowerApp-GUID-en som skal brukes i et senere trinn.

1. Logg deg på [,ogvelgderetterapperi https://web.powerapps.com](https://web.powerapps.com)menyen.

   > [!div class="mx-imgBorder"] 
   > ![Vis liste over apper](./media/embed-teams-app/file-apps2.png "Vis liste over apper")

2. Velg **flere kommandoer** (...) for appen du vil dele i Teams, og velg deretter **detaljer**.

   > [!div class="mx-imgBorder"] 
   > ![Detaljer om app](./media/embed-teams-app/app-details.png "Detaljer om app")


3. Registrer **app-ID-** en for senere bruk.

   > [!div class="mx-imgBorder"] 
   > ![Detaljer om app](./media/embed-teams-app/app-details2.png "Detaljer om app")

## <a name="install-app-studio"></a>Installer app Studio

Du kan hoppe over disse trinnene hvis app Studio allerede er installert. 

1. I Teams velger du **apper** nederst til venstre på team-menyen (![apper-ikonet](./media/embed-teams-app/apps-icon.png "apps-ikonet")).

2. Søk etter «app Studio» i søke boksen, og velg det.

   > [!div class="mx-imgBorder"] 
   > ![App Studio](./media/embed-teams-app/store-app-studio.png "App Studio")

3. Velg **Installer**. 

   > [!div class="mx-imgBorder"] 
   > ![Installer app Studio](./media/embed-teams-app/install-app-studio.png "Installer app Studio")

4. Velg **Åpne** for app-funksjonen.

   > [!div class="mx-imgBorder"] 
   > ![Åpne app Studio](./media/embed-teams-app/open-app-studio.png "Åpne app Studio")

## <a name="create-a-teams-app-for-your-powerapp"></a>Opprett en team-app for PowerApp

1. Åpne app Studio i Teams.

   > [!div class="mx-imgBorder"] 
   > ![Åpne app Studio](./media/embed-teams-app/open-app-studio2.png "Åpne app Studio")

2. Velg kategorien **redigerings program for manifest** , og velg deretter **Opprett en ny app** under velkommen.

   > [!div class="mx-imgBorder"] 
   > ![Opprett ny app](./media/embed-teams-app/create-new-app.png "Opprett ny app")

3. Fyll ut informasjon om appen på siden for **app-detaljer** .  Du må bruke ID-en GUID for app-IDen du har registrert ovenfor, for GUID for app-ID.  Dette vil unngå duplisering av team apps for en bestemt PowerApp.
 
   > [!div class="mx-imgBorder"] 
   > ![Fyll ut informasjon](./media/embed-teams-app/fill-in-info-about-app.png "Fyll ut informasjon")

   |Felt  |Beskrivelse  |
   |---------|---------|
   |**Navn på apper** |    |
   |Kort navn     | Krevde. Navnet på den korte visningen for appen. 30 tegn grense.        |
   |Langt navn     | Det fullstendige navnet på appen, brukes hvis det fullstendige app-navnet overskrider 30 tegn.       | 
   |**Opplysninger**     |         |
   |App-ID     | Krevde. Den unike Microsoft-genererte identifikatoren for denne appen.        |
   |Pakke navn     | Krevde. En unik identifikator for denne appen. Vi anbefaler at du bruker omvendt domene-notasjon. for eksempel, com. eksempel. <AppName>.       |
   |Etterkalkuleringsversjonen     | Krevde. Versjonen av den bestemte appen. Hvis du oppdaterer noe i manifestet, må versjonen også økes.     |
   |**Skildring**    |     |
   | Kort beskrivelse    | Krevde. En kort beskrivelse av app-opplevelsen, brukes når plass er begrenset. grensen på 80 tegn.   |
   | Lang beskrivelse    | Krevde. Den fullstendige beskrivelsen av appen.     |
   | **Informasjon om utviklere**    |     |
   | navn    | Krevde. Visnings navnet for firmaet eller utvikle ren.     |
   | Web    | Krevde. Https://Netta dressen til nettstedet for appen din via powerapps.com. Når noen installerer appen din, vises siden om appen din. Den skal koble til Web versjonen av appen din på powerapps.com.   |
   | **Netta dresser for App**    | Disse koblingene vises i **om** -siden sammen med NETTa dressen for nettstedet.     |
   | Person vern erklæring    | Krevde. Https://Netta dressen til utvikle rens person vern policy. [Eksempel](https://go.microsoft.com/fwlink/p/?LinkID=698505).   |
   | vilkår for bruk    | Krevde. Https://Netta dressen til utviklers vilkår for bruk.  [Eksempel](https://go.microsoft.com/fwlink/p/?LinkID=698507).  |
   | **Merke**    |     |
   | Full farge    | En relativ filbane til et Full Color 192x192 PNG-ikon.    |
   | Gjennomsiktig kontur    |En relativ filbane til et gjennomsiktig 32 x 32 PNG-omriss.     |
   | Uthevings farge    | En farge som brukes i forbindelse med og som bakgrunn for disposisjons ikonene.     |

Hvis du vil ha mer informasjon, kan du se [manifest redigerings program](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio#manifest-editor) og [manifest skjema](https://docs.microsoft.com/microsoftteams/platform/resources/schema/manifest-schema).

4. Rull ned til merkings delen, og Legg til logoene og uthevings fargen du ønsker for appen.  Dette er logoene som vil vises for appen i Teams. 

   > [!div class="mx-imgBorder"] 
   > ![Merking og tabu lat Orer](./media/embed-teams-app/branding-tabs.png "Merking og tabu lat Orer")

5. Under **funksjoner**velger du **Kategorier**.

6. Velg **Legg til**under **gruppe-fanen** .

   > [!div class="mx-imgBorder"] 
   > ![Legg til gruppe-fane](./media/embed-teams-app/team-tab-add.png "Legg til gruppe-fane")

7. Legg til appens konfigurasjons-URL-adresse i inn data feltet for Konfigurasjons-URL-adresse ved hjelp av følgende format:`https://apps.powerapps.com/teams/settings/<PowerApp ID>`

   Erstatt `<PowerApp ID>` med GUID-en for app-ID-en du har registrert ovenfor.

   Velg [omfanget](https://docs.microsoft.com/microsoftteams/platform/concepts/tabs/tabs-overview#tab-scope) som appen skal vises i. Sørg for at det er merket av for **å oppdatere konfigurasjonen** , og velg deretter **Lagre**.

   > [!div class="mx-imgBorder"] 
   > ![Konfigurasjons-URL](./media/embed-teams-app/configuration-url.png "Konfigurasjons-URL")

8. Velg **gyldige domener**under **Fullfør**. Legg til **apps.powerapps.com** og **apps.preview.powerapps.com** som gyldige domener for Teams-programmet.

   > [!div class="mx-imgBorder"] 
   > ![Legg til gyldige domener](./media/embed-teams-app/add-valid-domains.png "Legg til gyldige domener")

9. Under **Fullfør**velger du **test og Distribuer**. Velg **Installer**under **Installer**.

   > [!div class="mx-imgBorder"] 
   > ![Velg Installer](./media/embed-teams-app/test-distribute-app.png "Velg Installer")

10. Velg teamet du vil appen skal installeres i, og velg deretter **Installer**.

    > [!div class="mx-imgBorder"] 
    > ![Legg til i team installasjon](./media/embed-teams-app/new-app-add-to-team.png "Legg til i team installasjon")
11. Hvis du vil legge til en forekomst av appen i en kanal umiddelbart, velger du kanalen du vil bruke appen i, og velger **Konfigurer**.

    > [!div class="mx-imgBorder"] 
    > ![Velg Konfigurer](./media/embed-teams-app/app-now-available.png "Velg Konfigurer")

12. Velg **Lagre**.

## <a name="add-the-app-as-a-tab"></a>Legg til appen som en fane

Hvis du vil legge til appen som en fane i en hvilken som helst **+** kanal eller samtale, velger du, og deretter velger du appen i **kategoriene for teamet** . 

> [!div class="mx-imgBorder"] 
> ![Legg til app som fane](./media/embed-teams-app/add-app-as-tab.png "Legg til app som fane")

Appen vises nå som en fane.

> [!div class="mx-imgBorder"] 
> ![App som-fane](./media/embed-teams-app/app-as-tab.png "App som-fane")

### <a name="see-also"></a>Se også
[Velkommen til Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-overview)<br />
[For administratorer: Bygge inn en app i Microsoft Teams](https://docs.microsoft.com/power-platform/admin/share-app-teams)
