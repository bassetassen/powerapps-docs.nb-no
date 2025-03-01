---
title: Integrer lerretsapper på nettsteder og andre tjenester | Microsoft Docs
description: Bygg inn lerretsapper på nettsteder og i andre tjenester.
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 08/28/2019
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: ac4699818c7f5b3a136db122fad9621d865bf5f1
ms.sourcegitcommit: f296922b8039b573e5adb81423a544f70c56c1ee
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 09/25/2019
ms.locfileid: "71256097"
---
# <a name="integrate-canvas-apps-into-websites-and-other-services"></a>Integrer lerretsapper på nettsteder og andre tjenester
Appene du bygger, er ofte nyttig når de er tilgjengelige akkurat der brukerne gjør det. Ved å bygge inn lerret programmer i en iframe, kan du integrere disse appene på nett steder og andre tjenester, for eksempel Power BI eller SharePoint.

I dette emnet viser vi deg hvordan du angir parametere for innebygging av apper. Deretter bygger vi inn ressursbestillingsappen på et nettsted.

![Power BI-instrumentbord med innebygde apper](./media/embed-apps-dev/embed-dashboard.png)

Husk på følgende restriksjoner:

- Bare PowerApps-brukere i samme tenant har tilgang til den innebygde appen.
- Hvis du vil ha tilgang til PowerApps ved hjelp av Internet Explorer 11, må du deaktivere kompatibilitetsmodus for visning.

Du kan også integrere lerret-apper i SharePoint Online uten å bruke en iframe. Mer informasjon: [Bruk powerapps-webdelen](https://support.office.com/article/use-the-powerapps-web-part-6285f05e-e441-408a-99d7-aa688195cd1c).

## <a name="set-uri-parameters-for-your-app"></a>Å angi URI-parametere for appen din
Hvis du har en app du vil bygge inn, er det første trinnet å angi parametere for Uniform Resource Identifier (URI), slik at iframe finner appen. URI-en finnes i følgende format:

```
https://apps.powerapps.com/play/[AppID]?source=iframe
```

> [!IMPORTANT]
> Fra august 2019 er URI-formatet endret fra https://web.powerapps.com/webplayer til. https://apps.powerapps.com/play Oppdater eventuelle innebygde iframes for å bruke det nye URI-formatet. Referanser til det forrige formatet blir omdirigert til den nye URI-en for å sikre kompatibilitet.
>
> Forrige format:
> 
> https\://Web.powerapps.com/WebPlayer/iframeapp? kilde = iframe & AppID =/Providers/Microsoft.PowerApps/Apps/[AppID]

Det eneste du trenger å gjøre er å erstatte ID-en til appen din med [AppID] i URI-en (inkludert ' [' & ']'). Vi skal straks vise deg hvordan du får denne verdien, men først kan du se hvilke parametere som er tilgjengelige i URI-en:

* **[appID]** -den angir ID-en til appen som skal kjøres.
* **tenantid** – er en valg fri parameter som støtter gjeste tilgang og avgjør hvilken Tenant du vil åpne appen fra. 
* **screenColor** – brukes til å angi en mer smidig innlasting av appen for brukerne. Denne parameteren er i formatet [RGBA (rød verdi, grønn verdi, blå verdi, alfa)](../canvas-apps/functions/function-colors.md) og kontrollerer skjermfargen mens appen lastes inn. Det er best å angi den til samme farge som app-ikonet ditt.
* **kilde** – har ingen innvirkning på appen, men vi foreslår at du legger til et beskrivende navn for å referere til kilden for innebyggingen.
* Til slutt kan du legge til de egendefinerte parameterne du ønsker ved å bruke [Param()-funksjonen](../canvas-apps/functions/function-param.md), og disse verdiene kan brukes av appen din. De legges til på slutten av URI-en, for eksempel `[AppID]&amp;param1=value1`. Disse parameterne er skrivebeskyttet når appen startes. Hvis du trenger å endre dem, må du starte appen på nytt. Vær oppmerksom på at bare det første elementet etter at [AppID] skal ha «?»; etter dette bruker du «&» som illustrert her. 

### <a name="get-the-app-id"></a>Å hente App-ID-en
App-ID-en er tilgjengelig på powerapps.com. For appen du vil bygge inn:

1. På **Apper**-fanen, på [powerapps.com](https://powerapps.microsoft.com), klikker eller trykker du på ellipsen ( **. . .** ), deretter **Detaljer**.
   
    ![Gå til appdetaljer](./media/embed-apps-dev/details.png)
1. Kopier **App-ID-en**.
   
    ![Kopiering av app-ID fra detaljer](./media/embed-apps-dev/app-id.png)
1. Erstatt `[AppID]`-verdien i URI-en. URI-en ser slik ut for ressursbestillingsappen vår:
   
    ```
    https://apps.powerapps.com/play/76897698-91a8-b2de-756e-fe2774f114f2?source=iframe
    ```

## <a name="embed-your-app-in-a-website"></a>Slik bygger du inn appen din på et nettsted
Å bygge inn appen din er nå like enkelt som å legge til iframe i HTML-koden for nettstedet ditt (eller andre tjenester som støtter iframer, for eksempel Power BI eller SharePoint):

```html
<iframe width="[W]" height="[H]" src="https://apps.powerapps.com/play/[AppID]?source=website&screenColor=rgba(165,34,55,1)" allow="geolocation; microphone; camera"/>
```

Angi verdier for bredden og høyden for iframe, og erstatt ID-en til appen din for `[AppID]`.

> [!NOTE]
> Inkluder `allow="geolocation; microphone; camera"` i HTML-koden i iframe for å tillate appene å bruke disse funksjonene på Google Chrome.

Bildet nedenfor viser ressursbestillingsappen innebygd i et eksempelnettsted for Contoso.

![Et Contoso-nettsted med innebygd app](./media/embed-apps-dev/contoso-website.png)

Husk følgende punkter når du skal godkjenne brukere av appen:

- Hvis nettstedet bruker Azure Active Directory (AAD)-basert godkjenning, kreves det ingen ekstra pålogging.
- Hvis nettstedet ditt bruker en annen påloggingsmetode, eller ikke er godkjent, vil brukerne se en påloggingsmelding på iframe. Etter de er pålogget, vil de kunne kjøre appen så lenge oppretteren av appen har delt den med dem.

Som du ser, er det enkelt og kraftfullt å bygge inn apper. Innebygging gjør det mulig å flytte appene direkte til stedene der du og kundene dine arbeider – nettsteder Power BI-instrumentbord, SharePoint-sider og mer.
