---
title: Del en lerretsapp | Microsoft Docs
description: Del lerretsappen ved å gi andre brukere tillatelse til å kjøre eller endre den
author: AFTOwen
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 11/28/2018
ms.author: anneta
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: c1107fd96070e62ffc8df53ad756dea01da7c5f7
ms.sourcegitcommit: db2d38f0351fd41f74fa44f7a1d80703a6b38527
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/06/2019
ms.locfileid: "66723930"
---
# <a name="share-a-canvas-app-in-powerapps"></a>Del en lerretsapp i PowerApps

Når du har utviklet en lerretsapp som skal ta seg av et forretningsbehov, angir du hvilke brukere i organisasjonen som kan kjøre appen, og hvilke som kan endre den og til og med dele den på nytt. Angi hver bruker etter navn, eller angi en sikkerhetsgruppe i Azure Active Directory. Hvis alle kan dra nytte av appen, angir du at hele organisasjonen kan kjøre den.

> [!IMPORTANT]
> For en delt app skal fungere som forventet, må du også administrere tillatelser for datakilden eller kilder som appen er basert på, slik som [Common Data Service-](#common-data-service) eller [Excel](share-app-data.md). Du må kanskje også dele [andre ressurser](share-app-resources.md) som appen avhenger av, for eksempel flyter, gatewayer eller tilkoblinger.

## <a name="prerequisites"></a>Forutsetninger

Du må lagre appen i skyen (ikke lokalt) og deretter publisere den før du deler den.

- Gi appen et meningsfylt navn og en klar beskrivelse, slik at alle kan se hva appen kan brukes til og det er lett å finne den i en liste. Velg **Appinnstillinger** på **Fil**-menyen i PowerApps Studio, angi et navn, og skriv eller lim deretter inn en beskrivelse.

- Når du gjør endringer, må du lagre og publisere appen på nytt hvis du vil at andre skal se disse endringene.

## <a name="share-an-app"></a>Å dele en app

1. [Logg deg på](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) PowerApps, og velg deretter **Apper** nær venstre kant.

    ![Vise listen over apper](./media/share-app/file-apps.png)

1. Velg appen du vil dele ved å velge ikonet.

    ![Velg en app](./media/share-app/select-app.png)

1. Velg i banneret, **del**.

    ![Åpne delt skjerm](./media/share-app/banner-share.png)

1. Angi etter navn eller alias brukere eller sikkerhetsgrupper i Azure Active Directory du vil dele appen.

    - Tillat hele organisasjonen til å kjøre appen (men ikke endre eller dele den), skriver du inn **alle** i deling-panelet.
    - Du kan dele en app med en liste over aliaser, egendefinerte navn eller en kombinasjon av disse (for eksempel **Kari Nordmann &lt; jane.doe@contoso.com>** ) Hvis dataene er atskilt med semikolon. Hvis mer enn én person har samme navn, men forskjellige aliaser, den første personen som er funnet blir lagt til i listen. Et verktøytips vises hvis et navn eller alias som allerede har tillatelse eller ikke kan løses. 

    ![Angi brukere og Medeiere](./media/share-app/share-everyone.png)

    > [!NOTE]
    > Du kan ikke dele en app med en distribusjonsgruppe i organisasjonen din eller med en bruker eller gruppe utenfor organisasjonen.

1. Hvis du vil tillate de du deler appen for å redigere og dele den (i tillegg til å kjøre den), med Velg den **medeier** avmerkingsboks.

    Du kan ikke gi **medeier** tillatelse til en security gruppere Hvis du [opprettet appen fra en løsning](add-app-solution.md).

    > [!NOTE]
    > Ingen to personer kan redigere en app om gangen, uavhengig av tillatelser. Hvis én person åpner appen for redigering, vil andre personer kan kjøre den, men ikke redigere data.

1. Hvis appen din kobles til data som brukere trenger tilgangstillatelser, angir du dem.

    Appen din kan for eksempel koble til en enhet i Common Data Service-database. Når du deler en slik app, deling panelet ber deg om å administrere sikkerhet for denne enheten.

    > [!div class="mx-imgBorder"]
    > ![Tilordne en sikkerhetsrolle](media/share-app/cds-assign-security-role.png)

    Hvis du vil ha mer informasjon om administrasjon av sikkerhet for en enhet, kan du se [behandle tillatelser for enheten](share-app.md#manage-entity-permissions) senere i dette emnet.

1. Hvis du vil finne appen, velg den **Send en e-postinvitasjon til nye brukere** avmerkingsboks.

1. Nederst i del-panelet, velg **dele**.

    Alle du har delt appen som kan kjøre den i PowerApps Mobile på en mobil enhet eller i AppSource på [Dynamics 365](https://home.dynamics.com) i en nettleser. Medeiere kan redigere og dele appen i [PowerApps](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc).

    Hvis du har sendt en e-postinvitasjon, kan alle som du har delt appen kjøre den ved å velge en kobling i invitasjonen.

    - Hvis en bruker velger koblingen på en mobil enhet, åpnes appen i PowerApps Mobile.
    - Hvis en bruker velger koblingen på en stasjonær datamaskin, åpnes appen i en nettleser.

    Medeiere som mottar en invitasjon få en ny kobling som åpner appen for redigering i PowerApps Studio.

Du kan endre tillatelsene for en bruker eller en sikkerhetsgruppe ved å velge navnet sitt, og deretter utfører en av disse trinnene:

- Fjern for å tillate Medeiere til å kjøre den appen, men ikke lenger redigere eller dele den, den **medeier** avmerkingsboks.
- Hvis du vil stoppe deling appen med denne brukeren eller gruppen, velger du ikonet Fjern (x).

## <a name="security-group-considerations"></a>Sikkerhetsgruppevurderinger

- Hvis du deler en app med en sikkerhetsgruppe, får eksisterende medlemmer av denne gruppen og alle som blir med i den, tillatelsene du angir for denne gruppen. Alle som forlater gruppen mister denne tillatelsen, med mindre de tilhører en annen gruppe som har tilgang, eller du gir dem tillatelse som enkeltpersoner.

- Hvert medlem av en sikkerhetsgruppe har de samme tillatelsene for en app, som den overordnede gruppen har. Du kan imidlertid angi større tillatelser for ett eller flere medlemmer av gruppen, for å gi dem større tilgang. For eksempel kan du gi sikkerhetsgruppen A tillatelse til å kjøre en app, men du kan også gi bruker B, som tilhører denne gruppen, **medeier** tillatelse. Hvert medlem av sikkerhetsgruppen kan kjøre appen, men bare bruker B kan redigere den. Hvis du gir sikkerhetsgruppe A **medeier** tillatelsen og bruker B tillatelse til å kjøre appen, kan vedkommende fremdeles redigere appen.

## <a name="manage-entity-permissions"></a>Slik administrerer du enhetstillatelser

### <a name="common-data-service"></a>Common Data Service

Hvis du oppretter en app basert på Common Data Service, må du også kontrollere at brukerne du deler appen med har de nødvendige tillatelsene for enheten eller enheter som appen er basert på. Disse brukerne må spesielt, tilhøre en sikkerhetsrolle som kan utføre oppgaver som oppretting, lesing, skriving og sletting av relevante poster. I mange tilfeller vil du opprette én eller flere egendefinerte sikkerhetsroller med de nøyaktige tillatelsene som brukerne trenger å kjøre appen. Deretter kan du tilordne en rolle til hver bruker etter behov.

> [!NOTE]
> I skrivende stund, kan du tilordne sikkerhetsroller til individuelle brukere og sikkerhetsgrupper i Azure Active Directory, men ikke til Office-grupper.

#### <a name="prerequisite"></a>Forutsetning

Hvis du vil tilordne en rolle, må du ha **systemansvarlig** tillatelser for en Common Data Service-database.

#### <a name="assign-a-security-group-in-azure-ad-to-a-role"></a>Tilordne en sikkerhetsgruppe i Azure AD til en rolle

1. Deling panelet, velg **tilordne en sikkerhetsrolle** under **Data tillatelser**.

1. Velg rollen eller roller i Common Data Service som du vil tilordne til brukeren eller sikkerhetsgruppen i Azure AD som du vil dele appen.

    ![Sikkerhet role-listen](media/share-app/cds-assign-security-role-list.png)

### <a name="common-data-service-previous-version"></a>Common Data Service (forrige versjon)

Når du deler en app som er basert på en eldre versjon av Common Data Service, må du dele tillatelse for kjøretid til tjenesten separat. Hvis du ikke har tillatelse til å gjøre dette, systemansvarlig miljø.
