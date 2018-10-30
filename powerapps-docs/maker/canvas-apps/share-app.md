---
title: Del en lerretsapp | Microsoft Docs
description: Del lerretsappen ved å gi andre brukere tillatelse til å kjøre eller endre den
author: AFTOwen
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 07/11/2018
ms.author: anneta
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 926d2b4b0d24f07a9a4cd42216e7d737db57308c
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/24/2018
ms.locfileid: "42853846"
---
# <a name="share-a-canvas-app-in-powerapps"></a>Del en lerretsapp i PowerApps

Når du har utviklet en lerretsapp som skal ta seg av et forretningsbehov, angir du hvilke brukere i organisasjonen som kan kjøre appen, og hvilke som kan endre den og til og med dele den på nytt. Angi hver bruker etter navn, eller angi en sikkerhetsgruppe i Azure Active Directory. Hvis alle kan dra nytte av appen, angir du at hele organisasjonen kan kjøre den.

> [!IMPORTANT]
> Du må også administrere tillatelser for datakilden eller -kildene som appen er basert på, slik som [Common Data Service for apper](#common-data-service-for-apps) eller [Excel](share-app-data.md), for at en delt app skal fungere som forventet. Du må kanskje også dele [andre ressurser](share-app-resources.md) som appen avhenger av, for eksempel flyter, gatewayer eller tilkoblinger.

## <a name="prerequisites"></a>Forutsetninger

Du må lagre appen i skyen (ikke lokalt) og deretter publisere den før du deler den.

- Gi appen et meningsfylt navn og en klar beskrivelse, slik at alle kan se hva appen kan brukes til og det er lett å finne den i en liste. Velg **Appinnstillinger** på **Fil**-menyen i PowerApps Studio, angi et navn, og skriv eller lim deretter inn en beskrivelse.

- Når du gjør endringer, må du lagre og publisere appen på nytt hvis du vil at andre skal se disse endringene.

## <a name="share-an-app"></a>Å dele en app

1. [Logg deg på](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) PowerApps, og velg deretter **Apper** nær venstre kant.

    ![Vise listen over apper](./media/share-app/file-apps.png)

1. Velg ellipsen (...) for appen du vil dele, og velg deretter **Del**.

    ![Åpne delt skjerm](./media/share-app/ellipsis-share.png)

1. Angi hvilke brukere eller sikkerhetsgrupper i Azure Active Directory du vil dele appen med.

    > [!NOTE]
    > Du kan ikke dele apper med en distribusjonsgruppe i organisasjonen eller med andre brukere eller grupper utenfor organisasjonen.

    ![Angi brukere](./media/share-app/share-list.png)

    Du kan også dele appen med hele organisasjonen, slik at de kan kjøre appen, men de ikke vil kunne endre eller dele den.

1. (valgfritt) Du hjelper brukerne med å finne appen ved å merke av for å sende dem en e-postinvitasjon.

    Invitasjonen inneholder en kobling som brukerne kan velge for å kjøre appen.

    - Hvis en bruker velger koblingen på en stasjonær datamaskin, åpnes appen i [Dynamics 365](http://home.dynamics.com).
    - Hvis brukeren velger koblingen på en mobilenhet, åpnes appen i PowerApps Mobile.

    Hvis du gir brukere tillatelse til å endre appen, inneholder meldingen også en egen kobling for å åpne appen for redigering i PowerApps Studio.

    Uavhengig av om du sender en invitasjon, kan brukere kjøre appen fra AppSource på [Dynamics 365](http://home.dynamics.com). Brukere som har **Kan redigere**-tillatelse kan også redigere appen fra [PowerApps](http://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc).

1. Angi tillatelser for hver bruker eller sikkerhetsgruppe, og velg deretter **Lagre**.

    - **Kan bruke**: Brukere kan kjøre appen, men ikke dele den.
    - **Kan redigere**: Brukere kan kjøre appen, endre den og dele den tilpassede versjonen med andre brukere.

        ![Å angi tillatelser](./media/share-app/edit-use.png)

    Hvis du vil endre tillatelser for en bruker eller en sikkerhetsgruppe, velger du pil ned ved siden av tillatelsen brukeren eller gruppen allerede har, og angir deretter en annen tillatelse.

    Hvis du vil fjerne alle tillatelser for en bruker eller en gruppe, velger du **x**-ikonet for denne brukeren eller gruppen.

## <a name="security-group-considerations"></a>Sikkerhetsgruppevurderinger

- Hvis du deler en app med en sikkerhetsgruppe, får eksisterende medlemmer av denne gruppen og alle som blir med i den, tillatelsene du angir for denne gruppen. Alle som forlater gruppen mister denne tillatelsen, med mindre de tilhører en annen gruppe som har tilgang, eller du gir dem tillatelse som enkeltpersoner.
- Hvert medlem av en sikkerhetsgruppe har de samme tillatelsene for en app, som den overordnede gruppen har. Du kan imidlertid angi større tillatelser for ett eller flere medlemmer av gruppen, for å gi dem større tilgang. Du kan for eksempel gi sikkerhetsgruppen A **Kan bruke**-tillatelse, men du kan også gi bruker B, som tilhører denne gruppen, **Kan redigere**-tillatelsen. Hvert medlem av sikkerhetsgruppen kan kjøre appen, men bare bruker B kan redigere den. Hvis du gir sikkerhetsgruppe A **Kan redigere**-tillatelsen og bruker B **Kan bruke**-tillatelsen, kan vedkommende fremdeles redigere appen.

## <a name="manage-entity-permissions"></a>Slik administrerer du enhetstillatelser

### <a name="common-data-service-for-apps"></a>Common Data Service for apper

Hvis du oppretter en app basert på Common Data Service (CDS) for apper, må du også påse at brukerne som kjører den har riktige tillatelser for enheten eller enhetene appen er avhengig av. Disse brukerne må spesifikt tilhøre en sikkerhetsrolle som kan utføre oppgaver, som for eksempel oppretting, lesing, skriving og sletting av relevante poster. I mange tilfeller oppretter du én eller flere egendefinerte sikkerhetsroller, med nøyaktig de samme tillatelsene som brukerne trenger for å bruke appene. Du kan deretter tilordne rollen eller rollene til brukerne, ved behov. 

#### <a name="prerequisite"></a>Forutsetning

Hvis du vil utføre de to neste prosedyrene, må du ha **Systemadministrator**-tillatelser for en CDS for apper-database.

#### <a name="create-a-security-role"></a>Slik oppretter du en sikkerhetsrolle

1. [Logg deg på PowerApps](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc), og kontroller at du er i samme miljø som appen du vil dele.

1. Velg tannhjulikonet i hjørnet øverst til høyre, og velg deretter **Avanserte tilpassinger**.

    ![Åpne Avanserte tilpassinger-ruten](media/share-app/advanced-customizations.png)

1. Velg **Sikkerhetsroller**-koblingen.

    ![Åpne sikkerhetsroller](media/share-app/security-roles.png)

1. Velg **Ny** under **Alle roller**, og skriv eller lim deretter inn et navn for rollen du oppretter.

    ![Slik oppretter du en sikkerhetsrolle](media/share-app/new-role.png)

1. Velg én eller flere faner for å finne enheten eller enhetene appen bruker, og velg deretter tillatelsene du vil gi sikkerhetsrollen.

    Denne grafikken viser for eksempel at en sikkerhetsrolle kan opprette, lese, skrive og slette poster i kontoenheten, som vises på **Kjernepost**-fanen.

    ![Å angi tillatelser](media/share-app/grant-access.png)

1. Velg **Lagre og lukk**.

#### <a name="assign-a-user-to-a-role"></a>Slik tilordner du en bruker til en rolle

1. Åpne **Avanserte tilpassinger**-ruten, som den forrige prosedyren beskriver, og velg deretter **Brukere**-koblingen.

    ![Brukere-koblingen](media/share-app/open-users.png)

1. I hjørnet øverst til høyre skriver eller limer du inn navnet på brukeren du vil tilordne rollen til, og velger deretter søkeikonet.

    ![Å søke etter brukere](media/share-app/search-users.png)

1. Pek på resultatet du vil ha i søkeresultatene, og merk deretter avmerkingsboksen som vises.

1. Velg **Administrere roller** i det øverste banneret.

1. Merk av for **Common Data Service-bruker** og rollen brukerne trenger for appen, i dialogboksen som vises, og velg deretter **OK.**

    ![Slik tilordner du en bruker til en rolle](media/share-app/assign-users.png)

### <a name="common-data-service-previous-version"></a>Common Data Service (forrige versjon)

Når du deler en app som er basert på en eldre versjon av Common Data Service, må du dele tillatelse for kjøretid til Common Data Service separat. Hvis du ikke har tillatelse til å gjøre dette, kan du kontakte miljøadministratoren.
