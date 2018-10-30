---
title: Opprett et miljø | Microsoft Docs
description: I denne hurtiginnføringen finner du ut mer om hvordan du oppretter et miljø
author: jimholtz
ms.service: powerapps
ms.component: pa-admin
ms.topic: quickstart
ms.date: 08/29/2018
ms.author: jimholtz
search.audienceType:
- admin
search.app:
- D365CE
- PowerApps
- Powerplatform
ms.openlocfilehash: 9d7a2093c938658d6717157fc6bd683aa3a55bb6
ms.sourcegitcommit: b8eee36e680036accb0e7d9fc7a434906af1c4d2
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/30/2018
ms.locfileid: "43297478"
---
# <a name="create-an-environment"></a>Å opprette et miljø
Et miljø er et område der du kan lagre, administrere og dele organisasjonens forretningsdata, apper og flyter. De fungerer også som beholdere til å skille apper som kan ha ulike roller, sikkerhetskrav eller målgrupper. Ett enkelt standardmiljø blir automatisk opprettet av PowerApps for hver leietaker og deles av alle brukerne i denne tenanten.

Hvert miljø kan ha ingen eller én Common Data Service-database, som gir lagring for appene dine. Når brukerne oppretter en app i et miljø, kan appen koble til alle typer datakilder, inkludert tilkoblinger, gatewayer og flyter. Appen er imidlertid bare tillatt å koble seg til Common Data Service-databasene i det samme miljøet. Måten du velger å dra nytte av miljøer på avhenger av organisasjonen og appene du prøver å bygge. Hvis du vil ha mer informasjon, kan du se [Oversikt over miljøer](environments-overview.md).

Dette emnet tar for seg hvordan du oppretter et miljø og en database for dette miljøet.

## <a name="prerequisites"></a>Forutsetninger
 Følgende elementer er nødvendige for å følge dette emnet:
 * En lisens for enten et PowerApps 2-abonnement eller et Microsoft Flow 2-abonnement. Du kan også registrere deg for en [gratis prøveversjon av PowerApps (abonnement 2)](https://web.powerapps.com/signup?redirect=marketing&email=).
 * Miljøadministrator for PowerApps, global administrator for Office 365 eller administrasjonstillatelser for tenanten til Azure Active Directory. Hvis du vil ha mer informasjon, kan du se [Miljøadministrasjon i PowerApps](environments-administration.md).

## <a name="sign-in-to-the-powerapps-admin-center"></a>Å logge på administrasjonssenteret for PowerApps
Logg deg på administrasjonssenteret på [https://admin.powerapps.com](https://admin.powerapps.com).

## <a name="create-an-environment-and-database"></a>Å opprette et miljø og en database
1. Klikk eller trykk på **Miljøer** i navigasjonsruten, og klikk og trykk deretter på **Nytt miljø**.

    ![Fil og Del](./media/create-environment/new-environment.png)
2. Skriv inn et navn for miljø i dialogboksen **Nytt miljø**, og deretter velger du en region- og miljøtype fra rullegardinlistene. Standardregionen blir den lokale regionen til Azure Active Directory-tenanten, men du kan velge hvilken som helst region i rullegardinlisten. Du kan ikke endre regionen når miljøet er opprettet. Når du er ferdig, klikker eller trykker du på **Opprett miljø**.

    ![Fil og Del](./media/create-environment/new-environment-dialog.png)

    Velg **Forhåndsversjon (USA)** for å få tidlig tilgang til de kommende PowerApps-funksjonene. Lær om [forhåndsversjonsprogrammet for PowerApps](preview-environments.md).
3. Når miljøet er opprettet, mottar du en bekreftelsesmelding i dialogboksen, og du blir bedt om å opprette en database. Klikk eller trykk på **Opprett database** for å få tilgang til Common Data Service.

    **OBS!** Du kan for øyeblikket bare opprette en database i den lokale regionen til Azure Active Directory-tenanten.

    ![Fil og Del](./media/create-environment/create-database-dialog.png)
4. Velg valutaen og språket for dataene som er lagret i databasen. Du kan ikke endre valutaen eller språket når databasen er opprettet. Når du er ferdig, klikker eller trykker du på **Opprett database**.

    ![Fil og Del](./media/create-environment/create-database-dialog2.png)

    Det kan ta flere minutter å opprette databasen i Common Data Service. Når databasen er opprettet, vises det nye miljøet i listen over miljøer på **Miljøer**-siden.

    ![Fil og Del](./media/create-environment/new-environment-created.png)

    Klikk eller trykk på miljøet for å vise miljødetaljene.

## <a name="next-steps"></a>Neste trinn
Dette emnet har tatt for seg hvordan du oppretter et miljø og en database for dette miljøet. Nå får du mer informasjon om hvordan du administrerer miljøer i organisasjonen din.

> [!div class="nextstepaction"]
> [Å admnistrere miljøer i PowerApps](environments-administration.md)
