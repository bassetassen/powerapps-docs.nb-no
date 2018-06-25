---
title: Å dele en app i Microsoft Docs
description: Del appen ved å gi andre brukere tillatelse til å kjøre eller endre den
documentationcenter: na
author: AFTOwen
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: conceptual
ms.component: canvas
ms.date: 03/18/2018
ms.author: anneta
ms.openlocfilehash: c87f0e644668e9b9804b001560402972fd3d4531
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/04/2018
ms.locfileid: "32329138"
---
# <a name="share-an-app-in-powerapps"></a>Å dele en app i PowerApps
Det er flott å utvikle apper som er rettet mot bedriftens behov, men den virkelige magien ved PowerApps kommer fra å dele disse appene med andre. I dette emnet lærer du hvordan du deler apper med bestemte brukere eller sikkerhetsgrupper, og du kan i tillegg dele dem med hele organisasjonen.

## <a name="specify-an-app"></a>Angi en app
1. Logg inn i PowerApps, og klikk deretter på **Apper** nær venstre kant.

    ![Vise listen over apper](./media/share-app/file-apps.png)

1. Klikk eller trykk på ellipsen (...) for appen du vil dele, og klikk eller trykk deretter på **Del**.

    ![Åpne delt skjerm](./media/share-app/ellipsis-share.png)

## <a name="share-an-app"></a>Dele en app
1. Angi hvilke brukere eller sikkerhetsgrupper i Azure Active Directory du vil dele appen med, og om du vil sende et e-postvarsel til disse personene.

    Du kan også dele appen med hele organisasjonen, slik at de kan kjøre appen, men de ikke vil kunne endre eller dele den.

    ![Angi brukere](./media/share-app/share-list.png)

1. Angi tilgangsnivået, og klikk eller trykk på **Lagre**.

    * **Kan bruke**: Brukere eller grupper kan kjøre appen, men ikke dele den.
    * **Kan redigere**: Brukere eller grupper kan kjøre appen, tilpasse den og dele den tilpassede versjonen videre med andre brukere.

        ![Å angi tillatelser](./media/share-app/edit-use.png)

Hvis du vil endre tillatelser for en bruker eller en gruppe, gjentar du trinn 1 i denne prosedyren og angir et annet alternativ i listen over tillatelser for denne brukeren eller gruppen. Hvis du vil fjerne alle tillatelser for en bruker eller gruppe, kan du klikke eller trykke på **x**-ikonet for denne brukeren eller gruppen.

### <a name="send-email-notification"></a>Å sende en e-postvarsling
Når du deler en app, kan du velge om du vil varsle brukere eller en sikkerhetsgruppe via e-post, eller ikke. Hvis du velger dette alternativet, vil en e-post bli sendt for å varsle brukeren eller brukerne, eller sikkerhetsgruppene. E-postmeldingen inneholder en kobling brukerne kan bruke til å få tilgang til appen. Hvis det er aktuelt, blir brukerne bedt om å registrere seg for PowerApps.

Meldingen inneholder en annen type kobling som er basert på hvilken tillatelse du tilordner:

- Når du deler appen med **Kan bruke**-tillatelse, inneholder e-postmeldingen koblingen for å kjøre appen.
- Når du deler på appen med **Kan redigere**-tillatelse, inneholder e-postmeldingen koblingen for å kjøre eller redigere appen.

### <a name="how-do-my-users-see-the-app-i-shared"></a>Hvordan ser brukerne appen jeg delte?
Når du deler en app med én eller flere brukere eller sikkerhetsgrupper, bestemmer tillatelsen du brukte da du delte appen, hvordan de kan se appen.

##### <a name="if-you-shared-an-app-with-can-use-permission"></a>Hvis du delte en app med *Kan bruke*-tillatelse
Personene du har delt appen med, mottar en e-postmelding hvis du valgte den avmerkingsboksen i skjermbildet for appdeling. Brukerne kan klikke eller trykke på en kobling i e-posten for å kjøre appen på [Dynamics 365](http://home.dynamics.com). Vi vil snart støtte universelle koblinger, noe som betyr at hvis du har PowerApps Studio eller PowerApps Mobile installert, åpnes appen i PowerApps Studio eller PowerApps Mobile.

Brukere kan også finne appen i AppSource på [Dynamics 365](http://home.dynamics.com) (hvis du for eksempel ikke sendte en e-post). [Finn ut mer](../../user/app-source.md) om hvordan brukere kan få apper via AppSource.

##### <a name="if-you-shared-an-app-with-can-edit-permission"></a>Hvis du delte en app med *Kan redigere*-tillatelse
Personene du har delt appen med, mottar en e-postmelding hvis du valgte den avmerkingsboksen i skjermbildet for appdeling. De kan klikke eller trykke på en kobling i e-posten som åpner appen direkte for redigering ved hjelp av PowerApps Studio. Det finnes også en kobling for å kjøre appen på [Dynamics 365](http://home.dynamics.com). Vi vil snart støtte universelle koblinger, noe som betyr at hvis du har PowerApps Studio eller PowerApps for mobilenheter installert, åpnes appen i PowerApps Studio eller PowerApps for mobilenheter.

Brukere kan også finne appen i [powerapps.com](http://web.powerapps.com) (hvis du for eksempel ikke sendte e-post). Dette er hjemmesiden for apputviklere der de kan bla gjennom alle appene de har opprettet, eller som har blitt delt med dem med **Bidragsyter**-tillatelse. Men med [Dynamics 365](http://home.dynamics.com) kan brukere raskt kjøre apper fra PowerApps og andre forretningsapper.

## <a name="other-things-to-know"></a>Andre ting du bør vite
* Hvis du vil dele en app, må du lagre den i skyen, ikke lokalt.
* Før du deler en app, bør du vurdere hvilke brukere og sikkerhetsgrupper du har tenkt å dele den med, og hvilken rolle hver enkelt skal ha: **Kan redigere** eller **Kan bruke**. Hvis du deler en app med en gruppe, får eksisterende medlemmer av denne gruppen og alle som blir med i den, tillatelsene du angir. Hvis noen forlater gruppen, mister de disse tillatelsene med mindre de er medlemmer av en annen gruppe som har tilgang, eller du gir dem eksplisitte tillatelser.
* Hvert medlem av en gruppe har de samme tillatelsene for en app, som den overordnede gruppen har. Du kan imidlertid angi større tillatelser for ett eller flere medlemmer av gruppen for å gi dem større tilgang. Du kan for eksempel gi sikkerhetsgruppen A **Kan bruke**-tillatelse, men du kan også gi bruker B, som tilhører denne gruppen, **Kan redigere**-tillatelsen. Hvert medlem av sikkerhetsgruppen kan kjøre appen, men bare bruker B kan redigere den. Hvis du gir sikkerhetsgruppe A **Kan redigere**-tillatelsen og bruker B **Kan bruke**-tillatelsen, kan vedkommende fremdeles redigere appen.
* Du kan dele en app med hele organisasjonen, men vurder nøye om alle trenger tilgang til appen din.
* Vær oppmerksom på at eventuelle endringer du gjør i en delt app, flyter gjennom til personene du har delt den med så snart du lagrer endringene. Hvis du forbedrer en app, drar alle nytte av det. Hvis du bryter appen, påvirkes alle.
* Før du deler en app, kan du gi den et meningsfylt navn og en beskrivelse slik at brukerne vet hva appen handler om og enkelt kan velge den fra en liste. Klikk eller trykk på **Appinnstillinger** på **Fil**-menyen i PowerApps Studio, og skriv deretter inn en beskrivelse.

### <a name="app-sharing-and-the-resources-the-app-uses"></a>Deling av apper og ressurser som appen bruker
De fleste apper er avhengige av minst én av disse ressurstypene:

* En kobling til en datakilde
* En lokal datagateway
* En egendefinert kobling
* En Excel-arbeidsbok eller en annen tjeneste
* En flyt

Brukere og bidragsytere må ha tilgang til alle datatilkoblinger og gatewayer som appen bruker. Noen tillatelser leveres implisitt med appen, mens andre må gis eksplisitt. Du finner mer informasjon i [Ressurser for deling av apper](share-app-resources.md).

Når du deler en app som bruker en eldre versjon av Common Data Service, må du dele tillatelse for kjøretid til Common Data Service separat. Hvis du ikke har tillatelse til å gjøre dette, kan du kontakte miljøadministratoren. Når du deler en app som bruker den nyeste versjonen av Common Data Service, må du opprette en egendefinert rolle og tilordne brukere til den. [Les mer](../../administrator/database-security.md) om sikkerhet for Common Data Service.

### <a name="what-isnt-supported"></a>Hva støttes ikke?
* Du kan dele til en sikkerhetsgruppe, men ikke til en distribusjonsgruppe.
* Du kan dele apper med brukere i organisasjonen, men ikke brukere i en annen leietaker.
* Du kan dele en app på nytt hvis du har tilgangen **Kan redigere** (ikke **Kan bruke**) til appen.
