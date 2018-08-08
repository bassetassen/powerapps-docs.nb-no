---
title: Integrering av PowerApps på nettsteder og andre tjenester| Microsoft Docs
description: Bygg inn lerretsapper på nettsteder og i andre tjenester.
author: mgblythe
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 10/20/2017
ms.author: mblythe
ms.openlocfilehash: e48da773f34eb2abedd65c3ea88aab1bb184da02
ms.sourcegitcommit: e3f5a2bef64085d02aec82e62ff94ae8a4d01d24
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/02/2018
ms.locfileid: "39470780"
---
# <a name="integrate-powerapps-into-websites-and-other-services"></a>Integrering av PowerApps på nettsteder og andre tjenester
Appene du utvikler er gjerne mest nyttige når de er tilgjengelige direkte hvor arbeidet utføres. Med PowerApps kan du bygge inn lerretsapper i en iframe, slik at du kan integrere disse appene på nettsteder og i andre tjenester, for eksempel Power BI eller SharePoint.

I dette emnet viser vi deg hvordan du angir parametere for innebygging av apper. Deretter bygger vi inn ressursbestillingsappen på et nettsted.

![Power BI-instrumentbord med innebygde apper](./media/embed-apps-dev/embed-dashboard.png)

Husk på følgende restriksjoner:

* Bare PowerApps-brukere i samme tenant har tilgang til den innebygde appen.
* Hvis du vil ha tilgang til PowerApps ved hjelp av Internet Explorer 11, må du deaktivere kompatibilitetsmodus for visning.

Du kan også integrere PowerApps i SharePoint Online (uten å bruke en iframe). Hvis du vil ha mer informasjon, kan du se [Generer en app fra SharePoint ved hjelp av PowerApps](../canvas-apps/generate-app-from-sharepoint-list-interface.md).

## <a name="set-uri-parameters-for-your-app"></a>Å angi URI-parametere for appen din
Hvis du har en app du vil bygge inn, er det første trinnet å angi parametere for Uniform Resource Identifier (URI), slik at iframe finner appen. URI-en finnes i følgende format:

```
https://web.powerapps.com/webplayer/iframeapp?source=iframe
&appId=/providers/Microsoft.PowerApps/apps/[AppID]
```

> [!NOTE]
> Vi har lagt til et linjeskift slik at URI-en vises bedre på siden.

Det eneste du trenger å gjøre er å erstatte ID-en til appen din med [AppID] i URI-en (inkludert ' [' & ']'). Vi skal straks vise deg hvordan du får denne verdien, men først kan du se hvilke parametere som er tilgjengelige i URI-en:

* **[appID]**  – er i formatet `/providers/Microsoft.PowerApps/apps/[AppID]`. Den angir ID-en til appen som skal kjøre.
* **screenColor** – brukes til å angi en mer smidig innlasting av appen for brukerne. Denne parameteren er i formatet [RGBA (rød verdi, grønn verdi, blå verdi, alfa)](../canvas-apps/functions/function-colors.md) og kontrollerer skjermfargen mens appen lastes inn. Det er best å angi den til samme farge som app-ikonet ditt.
* **kilde** – har ingen innvirkning på appen, men vi foreslår at du legger til et beskrivende navn for å referere til kilden for innebyggingen.
* Til slutt kan du legge til de egendefinerte parameterne du ønsker ved å bruke [Param()-funksjonen](../canvas-apps/functions/function-param.md), og disse verdiene kan brukes av appen din. De legges til på slutten av URI-en, for eksempel `[AppID]&amp;param1=value1`. Disse parameterne leses bare når du starter appen. Hvis du trenger å endre dem, må du starte appen på nytt.

### <a name="get-the-app-id"></a>Å hente App-ID-en
App-ID-en er tilgjengelig på powerapps.com. For appen du vil bygge inn:

1. På **Apper**-fanen, på [powerapps.com](https://powerapps.microsoft.com), klikker eller trykker du på ellipsen ( **. . .** ), deretter **Detaljer**.
   
    ![Gå til appdetaljer](./media/embed-apps-dev/details.png)
2. Kopier **App-ID-en**.
   
    ![Kopiering av app-ID fra detaljer](./media/embed-apps-dev/app-id.png)
3. Erstatt `[AppID]`-verdien i URI-en. URI-en ser slik ut for ressursbestillingsappen vår:
   
    ```
    https://web.powerapps.com/webplayer/iframeapp?source=iframe&appId=/providers/Microsoft.PowerApps/apps/76897698-91a8-b2de-756e-fe2774f114f2
    ```

## <a name="embed-your-app-in-a-website"></a>Slik bygger du inn appen din på et nettsted
Å bygge inn appen din er nå like enkelt som å legge til iframe i HTML-koden for nettstedet ditt (eller andre tjenester som støtter iframer, for eksempel Power BI eller SharePoint):

```
<iframe width="[W]" height="[H]" src="https://web.powerapps.com/webplayer/iframeapp?source=website&screenColor=rgba(165,34,55,1)&appId=/providers/Microsoft.PowerApps/apps/[AppID]" allow="geolocation; microphone; camera"/>
```

Angi verdier for bredden og høyden for iframe, og erstatt ID-en til appen din for `[AppID]`.

> [!NOTE]
> Inkluder `allow="geolocation; microphone; camera"` i HTML-koden i iframe for å tillate appene å bruke disse funksjonene på Google Chrome.

Bildet nedenfor viser ressursbestillingsappen innebygd i et eksempelnettsted for Contoso.

![Et Contoso-nettsted med innebygd app](./media/embed-apps-dev/contoso-website.png)

Husk følgende punkter når du skal godkjenne brukere av appen:

* Hvis nettstedet bruker Azure Active Directory (AAD)-basert godkjenning, kreves det ingen ekstra pålogging.
* Hvis nettstedet ditt bruker en annen påloggingsmetode, eller ikke er godkjent, vil brukerne se en påloggingsmelding på iframe. Etter de er pålogget, vil de kunne kjøre appen så lenge oppretteren av appen har delt den med dem.

Som du ser, er det enkelt og kraftfullt å bygge inn apper. Innebygging gjør det mulig å flytte appene direkte til stedene der du og kundene dine arbeider – nettsteder Power BI-instrumentbord, SharePoint-sider og mer.

