---
title: Bygge inn en PowerApps-app i Teams | Microsoft Docs
description: Du kan bygge inn en app som er opprettet i PowerApps i Microsoft Teams til å dele den.
author: jimholtz
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 05/29/2019
ms.author: jimholtz
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: d17b02cc87bb219474aade955a2910f12fcf7f27
ms.sourcegitcommit: 2376c1f1f3431bca52a8deb9b966ce1fe9f88da0
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 05/30/2019
ms.locfileid: "66381390"
---
# <a name="embed-a-powerapps-app-in-teams"></a>Bygge inn en PowerApps-app i Teams 

Du kan dele en PowerApps du har opprettet ved å bygge inn den direkte inn i Microsoft Teams. Når du er ferdig, kan brukere velge **+** til å legge til appen din i **din** team kanaler eller samtaler i gruppen du er i. Appen vises som en flis under **fanene for teamet ditt**. 

En administrator kan laste opp appen slik at den viser deg for **alle** grupper i tenanten under den **alle kategorier delen**. Se [dele en app i Microsoft Teams](https://review.docs.microsoft.com/en-us/power-platform/admin/embed-app-teams?branch=JimHoltzWorkBranch).

> [!NOTE]
> Egendefinert app-policyer for Team må angis til å tillate laster opp egendefinerte apper. Hvis kan ikke bygge inn appen din i Teams, må du kontrollere med systemansvarlig for å se hvis de har etablert [egendefinerte appinnstillinger](https://docs.microsoft.com/MicrosoftTeams/teams-custom-app-policies-and-settings#custom-app-policy-and-settings). 

## <a name="prerequisites"></a>Forutsetninger

- [Har en PowerApps-lisens](https://docs.microsoft.com/power-platform/admin/pricing-billing-skus)
- Opprettet en lerretsapp

## <a name="locate-your-powerapps-guid"></a>Finn din PowerApp GUID

Finn og noter din PowerApp GUID for bruk i et senere trinn.

1. Logg deg på [ https://web.powerapps.com ](https://web.powerapps.com), og velg deretter **apper** i menyen.

   > [!div class="mx-imgBorder"] 
   > ![Vis liste over apper](./media/embed-teams-app/file-apps2.png "visningslisten over apper")

2. Velg **flere kommandoer** (...) for appen du vil dele i grupper, og velg deretter **detaljer**.

   > [!div class="mx-imgBorder"] 
   > ![Appdetaljer](./media/embed-teams-app/app-details.png "appdetaljer")

3. Post den **App-ID** for senere bruk.

   > [!div class="mx-imgBorder"] 
   > ![Appdetaljer](./media/embed-teams-app/app-details2.png "appdetaljer")

## <a name="install-app-studio"></a>Installer App Studio

Du kan hoppe over denne fremgangsmåten hvis App Studio er allerede installert. 

1. Velg i Teams **apper** i nedre venstre hjørne av Team-menyen (![apper-ikonet](./media/embed-teams-app/apps-icon.png "apper-ikonet")).

2. Søk etter «App Studio» i søkeboksen, og velg den.

   > [!div class="mx-imgBorder"] 
   > ![App Studio](./media/embed-teams-app/store-app-studio.png "App Studio")

3. Velg **installere**. 

   > [!div class="mx-imgBorder"] 
   > ![Installer App Studio](./media/embed-teams-app/install-app-studio.png "Installer App Studio")

4. Velg **åpne** for App-funksjonen.

   > [!div class="mx-imgBorder"] 
   > ![Åpne App Studio](./media/embed-teams-app/open-app-studio.png "åpne App Studio")

## <a name="create-a-teams-app-for-your-powerapp"></a>Opprett en Teams-app for din PowerApp

1. Åpne App Studio i Teams.

   > [!div class="mx-imgBorder"] 
   > ![Åpne App Studio](./media/embed-teams-app/open-app-studio2.png "åpne App Studio")

2. Velg den **Manifest editor** fanen, og velg deretter **opprette en ny app** under Velkommen.

   > [!div class="mx-imgBorder"] 
   > ![Opprett ny app](./media/embed-teams-app/create-new-app.png "Opprett ny app")

3. Fyll ut informasjonen om appen din i den **Appdetaljer** siden.  For App-ID-GUID, bør du bruke din PowerApp App-ID GUID du registrerte ovenfor.  Dette vil unngå duplisering av teamene apper for en bestemt PowerApp.
 
   > [!div class="mx-imgBorder"] 
   > ![Fyll ut informasjonen](./media/embed-teams-app/fill-in-info-about-app.png "fylle ut informasjon")

   |Felt  |Beskrivelse  |
   |---------|---------|
   |**Appnavn** |    |
   |Kortnavn     | Nødvendig. Kort visningsnavnet for appen. grensen for 30 tegn.        |
   |Det lange navnet     | Det fullstendige navnet på appen, brukes hvis fullstendig app overstiger 30 tegn.       | 
   |**Identifikasjon**     |         |
   |App-ID     | Nødvendig. Den unike Microsoft-genererte identifikatoren for denne appen.        |
   |Pakkenavn     | Nødvendig. En unik identifikator for denne appen. Vi anbefaler at du bruker omvendt domene notasjon; for eksempel com.example. <AppName>.       |
   |Versjon     | Nødvendig. Versjonen av bestemte appen. Hvis du oppdaterer noe i din manifestet, må versjonen økes også.     |
   |**Beskrivelser**    |     |
   | Kort beskrivelse    | Nødvendig. En kort beskrivelse av appen din, brukes når du har begrenset med plass. grensen for 80 tegn.   |
   | Lang beskrivelse    | Nødvendig. Fullstendig beskrivelse av appen din.     |
   | **Informasjon for utviklere**    |     |
   | navn    | Nødvendig. Visningsnavnet for firmaet eller utvikler.     |
   | Nettstedet    | Nødvendig. Https:// URL-adressen til webområdet for appen din via powerapps.com. Når noen installerer appen, en «om appen din» vises siden. Det bør koble til web-versjonen av appen din på powerapps.com.   |
   | **URL-adresser til App**    | Disse koblingene vises i den **om** siden sammen med nettstedet URL-adressen.     |
   | Personvernerklæring    | Nødvendig. Https:// URL-adressen til utviklerens personvernpolicy. [Eksempel](https://go.microsoft.com/fwlink/p/?LinkID=698505).   |
   | Vilkår for bruk    | Nødvendig. Https:// URL-adressen utviklerens vilkårene for bruk.  [Eksempel](https://go.microsoft.com/fwlink/p/?LinkID=698507).  |
   | **For varemerking**    |     |
   | Full farge    | En relativ filbane til en full farge 192 x 192 PNG-ikonet.    |
   | Gjennomsiktig disposisjon    |En relativ filbane til en gjennomsiktig 32 x 32 PNG disposisjon-ikonet.     |
   | Uthevingsfarge    | En farge som brukes i forbindelse med, og som bakgrunn for disposisjonen ikonene.     |

Hvis du vil ha mer informasjon, se [Manifest Editor](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio#manifest-editor) og [Manifest skjemaet](https://docs.microsoft.com/microsoftteams/platform/resources/schema/manifest-schema).

4. Rull ned til avsnittet varemerking og legge til dine logoer og uthevingsfarge ønsket for appen din.  Disse er logoene som skal vises for appen i Teams. 

   > [!div class="mx-imgBorder"] 
   > ![Varemerking og oversikten](./media/embed-teams-app/branding-tabs.png "varemerking og oversikten")

5. Under **funksjoner**, og velg **fanene**.

6. Under **Team fanen** Velg **Legg til**.

   > [!div class="mx-imgBorder"] 
   > ![Team-fanen Legg til](./media/embed-teams-app/team-tab-add.png "Team fanen Legg til")

7. Legg til URL-adresse for appens i inndata «URL-adresse for»-feltet i følgende format: `https://web.powerapps.com/webplayer/teamsapptabsettings?appid=<PowerApp ID>`

   Erstatt `<PowerApp ID>` med App-ID-GUID som du registrerte ovenfor.

   Velg den [omfanget](https://docs.microsoft.com/microsoftteams/platform/concepts/tabs/tabs-overview#tab-scope) for appen skal vises i. Sikre **kan oppdatere konfigurasjonen** er merket, og velg deretter **lagre**.

   > [!div class="mx-imgBorder"] 
   > ![URL-adresse for](./media/embed-teams-app/configuration-url.png "URL-adresse")

8. Under **Fullfør**, og velg **gyldige domener**. Legg til **apps.powerapps.com** og **apps.preview.powerapps.com** som gyldige domener for Team-programmet.

   > [!div class="mx-imgBorder"] 
   > ![Legg til gyldige domener](./media/embed-teams-app/add-valid-domains.png "legge til gyldige domener")

9. Under **Fullfør**, og velg **Test og Distribuer**. Under **installere**, og velg **installere**.

   > [!div class="mx-imgBorder"] 
   > ![Velg Installer](./media/embed-teams-app/test-distribute-app.png "Velg installasjon")

10. Velg gruppen du vil appen installert i, og velg deretter **installere**.

    > [!div class="mx-imgBorder"] 
    > ![Legg til i team Installer](./media/embed-teams-app/new-app-add-to-team.png "Legg til i team installasjon")

11. Hvis du vil legge til en forekomst av appen til en kanal med en gang, velger du kanalen du ønsker å bruke appen i og velg **konfigurere**.

    > [!div class="mx-imgBorder"] 
    > ![Velg Konfigurer](./media/embed-teams-app/app-now-available.png "Velg Konfigurer")

12. Velg **Lagre**.

## <a name="add-the-app-as-a-tab"></a>Legge til appen som en kategori

Hvis du vil legge til appen som en kategori på en kanal eller samtalen, kan du velge **+** , og deretter under **fanene for teamet ditt** Velg appen din. 

> [!div class="mx-imgBorder"] 
> ![Legg til app som kategori](./media/embed-teams-app/add-app-as-tab.png "Legg til app som kategori")

Appen vises nå som en kategori.

> [!div class="mx-imgBorder"] 
> ![App som kategori](./media/embed-teams-app/app-as-tab.png "App som kategori")

### <a name="see-also"></a>Se også
[Velkommen til Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-overview)<br />
[For administratorer: Bygge inn en app i Microsoft Teams](https://docs.microsoft.com/power-platform/admin/share-app-teams)