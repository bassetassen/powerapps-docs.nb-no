---
title: Generer en lerretsapp fra en SharePoint-liste | Microsoft Docs
description: Generer en lerretsapp i PowerApps automatisk for å behandle data i en SharePoint-liste
author: AFTOwen
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 08/09/2018
ms.author: anneta
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 15aa49787d6b2c3d3981e374aeb43c54a2d7a7ec
ms.sourcegitcommit: 02d0234bd84352bf1c43d0fc9225ab60947a0add
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/15/2018
ms.locfileid: "49317095"
---
# <a name="generate-a-canvas-app-in-powerapps-from-a-sharepoint-list"></a>Generer en lerretsapp i PowerApps fra en SharePoint-liste

Dette emnet beskriver hvordan du bruker PowerApps til å generere en lerretsapp automatisk basert på elementer i en SharePoint-liste. Du kan generere appen fra PowerApps eller SharePoint Online. Fra PowerApps kan du også generere en app basert på en liste i et lokalt SharePoint-område, hvis du [kobler deg til området](connect-to-sharepoint.md) gjennom en datagateway.

Appen du genererer, inneholder tre skjermbilder:

- Du kan bla gjennom alle elementene i listen, på bla gjennom-skjermen.
- Du kan vise all informasjonen om et enkelt element i listen, på detaljer-skjermen.
- Du kan opprette et element eller oppdatere informasjon om et eksisterende element, på rediger-skjermen.

Du kan ta i bruk konseptene og teknikkene i dette emnet i enhver liste i SharePoint. Slik gjør du det:

1. Opprett en liste med navn **SimpleApp** i et SharePoint Online-område.
2. I kolonnen med navnet **Tittel** kan du opprette oppføringer for **Vanilje**, **Sjokolade** og **Jordbær**.

Prinsippene for å generere en app endres ikke selv om du oppretter en liste som er mye mer komplisert med mange kolonner av ulike typer, for eksempel tekst, datoer, tall og valuta.

> [!IMPORTANT]
> PowerApps støtter ikke alle typer SharePoint-data. Hvis du vil ha mer informasjon, kan du se [Kjente problemer](connections/connection-sharepoint-online.md#known-issues).

## <a name="generate-an-app-from-within-powerapps"></a>Generer en app i PowerApps

1. Logg deg på [PowerApps](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc).

1. Hold pekeren over **Begynn fra data** under **Lag din egen app**, og velg deretter **Lag denne appen**.

    ![Alternativ for å opprette en app](./media/app-from-sharepoint/start-from-data.png)

1. Velg Telefonoppsett på **SharePoint**-flisen.

    ![Alternativ for å opprette en app](./media/app-from-sharepoint/sharepoint-tile.png)

1. Med alternativet **Koble til direkte** valgt velger du **Opprett**.

    ![Opprette tilkobling](./media/app-from-sharepoint/create-connection.png)

1. Under **Koble til et SharePoint-område** skriver du eller limer inn nettadressen for SharePoint Online-området, og deretter velger du **Gå**.

    Inkluder bare nettadressen (ikke navnet på listen), som i dette eksemplet:<br>`https://microsoft.sharepoint.com/teams/Contoso`

1. Under **Velg en liste** velger du **SimpleApp**, og deretter velger du **Koble**.

    Etter noen minutter åpnes appen til Bla gjennom-skjermen, som viser elementene du opprettet i listen. Hvis listen har data i flere kolonner enn bare **Tittel**, viser appen disse dataene. Nær toppen av skjermen viser en tittellinje ikoner for å oppdatere listen, sortere listen og opprette et element i listen. Under tittellinjen inneholder en søkeboks muligheten til å filtrere listen basert på teksten du skriver eller limer inn. 

    ![Bla gjennom-skjermen](./media/app-from-sharepoint/browse-screen.png)

    Du vil sannsynligvis gjøre flere endringer før du bruker denne appen eller deler den med andre. Som en anbefalt fremgangsmåte lagrer du arbeidet ditt så langt ved å trykke på Ctrl-S før du fortsetter. Gi appen et navn, og velg deretter **Lagre**.

## <a name="generate-an-app-from-within-sharepoint-online"></a>Generer en app i SharePoint Online

Hvis du fra kommandolinjen i SharePoint Online oppretter en app basert på en egendefinert liste, vises appen som en visning av den aktuelle listen. Du kan også kjøre appen på iOS- og Android-enheter, og i nettlesere.

1. Åpne en egendefinert liste i SharePoint Online, åpne en egendefinert liste, velg **PowerApps** på kommandolinjen. Deretter velger du **Opprett en app**.

    ![Å opprette en app](./media/app-from-sharepoint/generate-new-app.png)

2. Skriv inn navn på appen i panelet som vises, og velger deretter **Opprett**.

    ![Gi navn til appen](./media/app-from-sharepoint/app-name.png)

    En ny fane vises i nettleseren som viser appen som du genererte automatisk ved hjelp av SharePoint-listen. Appen vises i PowerApps Studio, der du kan tilpasse den.

    ![Standardapp](./media/app-from-sharepoint/default-app.png)

3. (Valgfritt) Oppdater nettleserfanen for SharePoint-listen (ved å velge den og for eksempel trykke på F5), og følg deretter denne fremgangsmåten for å kjøre eller administrere appen:

    - Hvis du vil kjøre appen (i en separat nettleserfane), velger du **Åpne**.
    - Hvis du vil la andre i organisasjonen kjøre appen, velger du **Gjør denne visningen offentlig**.

        Hvis du vil la andre redigere appen, [deler du den](share-app.md) med **Kan redigere**-tillatelser.

    - Hvis du vil fjerne visningen fra SharePoint, velger du **Fjern denne visningen**.

        Hvis du vil fjerne appen fra PowerApps, [sletter du appen](delete-app.md).

## <a name="next-steps"></a>Neste trinn
I dette emnet opprettet du en app for å behandle data i en SharePoint-liste. Som et neste trinn kan du generere en app fra en mer komplisert liste og deretter tilpasse appen (fra skjermbildet Bla gjennom og videre) for å passe bedre til dine behov.

> [!div class="nextstepaction"]
> [Tilpasse et standard Bla gjennom-skjermbilde](customize-layout-sharepoint.md)
