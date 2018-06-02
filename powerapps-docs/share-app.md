---
title: Å dele en app i Microsoft Docs
description: Del appen ved å gi andre brukere tillatelse til å kjøre eller endre den
services: ''
suite: powerapps
documentationcenter: na
author: linhtranms
manager: anneta
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/28/2016
ms.author: litran
ms.openlocfilehash: 1d32873009c337a835a047df38b9ef18d5bf2064
ms.sourcegitcommit: 33099e6197c0139679cd08c42e9e2a5717904c92
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 01/12/2018
ms.locfileid: "30986567"
---
# <a name="share-an-app-in-powerapps"></a>Å dele en app i PowerApps
Det er flott å bygge apper som er rettet mot bedriftens behov, men den virkelige magien ved PowerApps kommer når du deler disse appene med andre. I dette emnet lærer du hvordan du deler apper med bestemte brukere, sikkerhetsgrupper, eller du kan dele dem med hele organisasjonen.

## <a name="open-the-share-app-screen"></a>Å åpne skjermbildet for app-deling
Hvis du vil dele en app, må du åpne powerapps.com. Vi støtter ikke lenger deling av apper i PowerApps Studio, eller PowerApps Mobile.

**Fra PowerApps Studio**

* Alternativ 1 – klikk eller trykk på **del** på **Fil**-menyen.
  
    ![Fil og Del](./media/share-app/studio-share.png)
* Alternativ 2 – klikk eller trykk på **Åpne** på **Fil**-menyen, og klikk eller trykk deretter på Del-ikonet for en app.
  
    ![Ellipser og Del](./media/share-app/studio-share-icon.png)

**Fra [powerapps.com](http://web.powerapps.com)**

* Klikk eller trykk på **Apper** i det venstre navigasjonsfeltet, klikk eller trykk på ellipsen (...), og klikk eller trykk deretter på **Del**.
  
   ![Ellipse på portalen](./media/share-app/portal-share.png)

## <a name="share-an-app"></a>Å dele en app
Herfra kan du dele en app ved å følge disse trinnene.

1. Angi navnene på en, eller flere brukere eller sikkerhetsgrupper, i Azure Active Directory, eller angi at du vil dele appen med hele organisasjonen. Vær oppmerksom på at du bare kan dele med **Bruker**-tillatelse når du deler til hele organisasjonen.
   
    ![Å angi brukere i powerapps.com](./media/share-app/portal-users.png)
2. Angi tilgangsnivået:
   
   * **Bruker**: Brukere eller grupper kan kjøre appen, men ikke dele den.
   * **Bidragsyter**: Brukere eller grupper kan kjøre appen, tilpasse den, og dele den tilpassede versjonen ytterligere til andre brukere.
     
       ![Å dele app-portalen](./media/share-app/portal-permissions.png)
3. Klikk eller trykk på **Lagre**.

Hvis du vil endre tillatelser for en bruker eller en gruppe, gjentar du trinn 1 i denne prosedyren, og angir et annet alternativ i listen over tillatelser for denne brukeren eller gruppen. Hvis du vil fjerne alle tillatelser for en bruker eller gruppe, kan du klikke eller trykke på **x**-ikonet for denne brukeren eller gruppen.

### <a name="send-email-notification"></a>Sende en e-postvarsling
Når du deler en app, kan du velge om du vil varsle brukere eller en sikkerhetsgruppe via e-post, eller ikke. Hvis du velger dette alternativet, vil en e-post bli sendt for å varsle brukeren eller brukerne, eller sikkerhetsgruppene. E-postmeldingen inneholder en kobling som gjør at de kan få tilgang til appen. Hvis det er aktuelt, blir brukere bedt om å registrere seg for og installere PowerApps.

Vær oppmerksom på at forskjellige e-postmaler sendes avhengig av tillatelsen du velger å dele appen med. E-postmeldingen inneholder koblingen for å kjøre appen, når du deler appen med **Bruker**-tillatelse. E-postmeldingen inneholder koblingen til å redigere appen i PowerApps Studio, eller til å kjøre programmet, når du deler appen med **Bidragsyter**-tillatelse.

### <a name="how-do-my-users-see-the-app-i-shared"></a>Hvordan ser brukerne appen jeg delte?
Når du har delt en app med én eller flere brukere, eller sikkerhetsgrupper, avhenger hvordan de kan se appen av tillatelsen du brukte da du delte appen.

##### <a name="if-you-shared-app-with-user-permission"></a>Hvis du delte en app med *Bruker*-tillatelse
Personene du har delt appen med, mottar en e-postmelding hvis du valgte den avmerkingsboksen i skjermbildet for appdeling. Brukerne kan klikke eller trykke på en kobling i e-posten for å kjøre appen på [Dynamics 365](http://home.dynamics.com). Vi vil snart støtte universelle koblinger, noe som betyr at hvis du har PowerApps Studio eller PowerApps Mobile installert, åpnes appen i PowerApps Studio eller PowerApps Mobile.

Brukere kan også finne appen i AppSource på [Dynamics 365](http://home.dynamics.com) (hvis du for eksempel ikke sendte en e-post). [Finn ut mer](app-source.md) om hvordan brukere kan få apper via AppSource.

##### <a name="if-you-shared-an-app-with-contributor-permission"></a>Hvis du delte en app med *Bidragsyter*-tillatelse
Personene du har delt appen med, mottar en e-postmelding hvis du valgte den avmerkingsboksen i skjermbildet for appdeling. De kan klikke eller trykke på en kobling i e-posten som åpner appen direkte for redigering ved hjelp av PowerApps Studio for nettet. Det finnes også en kobling for å kjøre appen på [Dynamics 365](http://home.dynamics.com). Vi vil snart støtte universelle koblinger, noe som betyr at hvis du har PowerApps Studio eller PowerApps Mobile installert, åpnes appen i PowerApps Studio eller PowerApps Mobile.

Brukere kan også finne appen i [powerapps.com](http://web.powerapps.com) (hvis du for eksempel ikke sendte en e-post). Dette er hjemmesiden for apputviklere der de kan bla gjennom alle apper de har opprettet, eller som har blitt delt med dem via **Bidragsyter**-tillatelse. I motsetning er [Dynamics 365](http://home.dynamics.com) der brukere raskt kan kjøre apper fra PowerApps og andre forretningsapper.

## <a name="other-things-to-know"></a>Andre ting du bør vite
* Hvis du vil dele en app, må du lagre den i skyen, ikke lokalt.
* Før du deler en app, bør du vurdere hvilke brukere og sikkerhetsgrupper som du har tenkt å dele den med, og hvilken rolle du vil at hver bruker skal ha – bruker eller bidragsyter. Hvis du deler en app med en gruppe, får eksisterende medlemmer av denne gruppen og alle som blir med i den, tillatelsene du angir. Alle som forlater gruppen mister disse tillatelsene, med mindre de er medlemmer av en annen gruppe som har tilgang, eller du gir dem eksplisitte tillatelser.
* Hvert medlem av en gruppe har de samme tillatelsene for en app, som den overordnede gruppen har. Du kan imidlertid angi større tillatelser for ett eller flere medlemmer av gruppen, for å gi dem større tilgang. Du kan for eksempel dele en app med sikkerhetsgruppe A, med brukertillatelse. Hvert medlem av sikkerhetsgruppe A kan kjøre appen. Nå deler du appen med bruker B, som er en del av sikkerhetsgruppe A, med bidragsyter-tillatelse. Bruker B kan nå redigere appen, mens alle andre i sikkerhetsgruppe A bare kan bruke appen. Hvis du angir færre tillatelser til ett eller flere medlemmer av en gruppe, har de fortsatt alle tillatelsene som du har gitt til den overordnede gruppen.
* Du kan dele en app med hele organisasjonen, men vurder nøye om alle trenger tilgang til appen.
* Vær oppmerksom på at eventuelle endringer du gjør i en delt app, vil flyte gjennom til personene du har delt den med, så snart du lagrer endringene. Dette kan være bra, hvis du forbedrer appen, men kan også påvirke andre hvis du fjerner, eller gjør betydelige endringer på funksjoner.
* Før du deler en app, kan du gi den et meningsfylt og beskrivende navn, slik at brukerne vet hva appen handler om og enkelt kan velge den fra en liste. Klikk eller trykk på **Appinnstillinger** på **Fil**-menyen i PowerApps Studio, og skriv deretter inn en beskrivelse.
  
  ![Appbeskrivelse](./media/share-app/description.png)

### <a name="app-sharing-and-the-resources-the-app-uses"></a>Deling av apper og ressurser som appen bruker
De fleste apper er avhengige av minst én av disse ressurstypene:

* en kobling til en datakilde
* en lokal datagateway
* en egendefinert kobling
* en Excel-arbeidsbok, eller en annen tjeneste
* en flyt

Brukere og bidragsytere må ha tilgang til alle datatilkoblinger og gatewayer som appen bruker. Noen tillatelser leveres implisitt med appen, mens andre må gis eksplisitt. Hvis du vil ha mer informasjon, kan du se [Ressurser for deling av apper](share-app-resources.md).

Legg merke til informasjonslinjen som indikerer at du må dele tillatelse for kjøretid til Common Data Service separat, når du deler en app som bruker en eldre versjon av Common Data Service. Hvis du ikke har tillatelse til å gjøre dette, kan du kontakte miljøadministratoren. [Les mer](database-security.md) om sikkerhet for Common Data Service.

![App-ressurser når du deler](./media/share-app/app-sharing-resources.png)

### <a name="what-isnt-supported"></a>Hva støttes ikke?
* Du kan dele til en sikkerhetsgruppe, men ikke til en distribusjonsgruppe.
* Du kan dele apper med brukere i organisasjonen, men ikke brukere i en annen tenant.
* Du kan dele en app fra [powerapps.com](http://web.powerapps.com), men ikke fra PowerApps Studio. (Klikk eller trykk på Del-ikonet i PowerApps Studio for å åpne [powerapps.com](http://web.powerapps.com)).
* Du kan dele en app på nytt, hvis du har Bidragsyter-tillatelse (ikke Bruker-tillatelse) til appen.

