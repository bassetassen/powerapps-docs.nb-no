---
title: Opprett en policy for hindring av datatap (DLP) | Microsoft Docs
description: I denne hurtiginnføringen lærer du hvordan du oppretter en policy for hindring av tap av data (DLP) i PowerApps
author: jimholtz
ms.service: powerapps
ms.component: pa-admin
ms.topic: quickstart
ms.date: 03/30/2018
ms.author: jimholtz
ms.openlocfilehash: 49898aed97e2361704c88bcc1cd098a8fc0f101e
ms.sourcegitcommit: 2e7b621066cdc3e7be329d5213ecfee0b4223641
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 07/30/2018
ms.locfileid: "39349459"
---
# <a name="create-a-data-loss-prevention-dlp-policy"></a>Opprett en policy for hindring av datatap (DLP)
Hvis du vil beskytte dataene i organisasjonen, kan du i PowerApps opprette og håndheve DLP-policyene, som angir hvilke forbrukerkoblinger bestemte forretningsdata kan deles med. Disse policyene som angir hvordan data kan deles, er referert til som policyer for hindring av tap av data (DLP). DLP-policyer kontroller at dataene behandles på en ensartet måte på tvers av organisasjonen, og hindrer viktige forretningsdata fra å utilsiktet bli publisert til koblinger som sosiale medier.

Dette emnet tar for seg hvordan du oppretter en DLP-policy for et enkeltmiljø som hindrer at data som er lagret i Common Data Service- og SharePoint-databasene, publiseres på Twitter.

## <a name="prerequisites"></a>Forutsetninger
**Ett** av følgende elementer er nødvendig for å følge denne fremgangsmåten:
* Administratortillatelser for tenanten til Azure Active Directory
* Globale administratortillatelser for Office 365
* Administratortillatelser for PowerApps-miljøet pluss et PowerApps-abonnement 2, Microsoft Flow-abonnement 2 eller en [prøveversjon av en PowerApps-abonnement 2](https://web.powerapps.com/signup?redirect=marketing&email=)-lisens

Hvis du vil ha mer informasjon, kan du se [Miljøadministrasjon i PowerApps](environments-administration.md).

## <a name="sign-in-to-the-powerapps-admin-center"></a>Å logge på administrasjonssenteret for PowerApps
Logg på administrasjonssenteret på [https://admin.powerapps.com]([https://admin.powerapps.com).

## <a name="create-a-dlp-policy"></a>Å opprette en DLP-policy
1. I navigasjonsruten klikker eller trykker du på **Datapolicyer**, og deretter klikker eller trykker du på **Ny policy**.

    ![](./media/create-dlp-policy/new-data-policy.png)
2. **Navn på datapolicy**-feltet fylles automatisk ut med et navn basert på datoen og klokkeslettet policyen er opprettet. Erstatt dette med **Sikker datatilgang for Contoso**.

    ![](./media/create-dlp-policy/policy-name.png)
3. Alternativene på **Miljøer**-fanen varierer avhengig av om du er en administrator for miljøet eller en tenantadministrator. Hvis du er miljøadministrator, velger du et miljø fra rullegardinlisten, og deretter klikker eller trykker du på **Fortsett**.

    ![](./media/create-dlp-policy/select-environment.png)

    Hvis du er en tenantadministrator, kan du opprette DLP-policyer som gjelder for én eller flere miljøer, eller for alle miljøer i tenanten (inkludert de som er opprettet ved hjelp av en prøveversjon av en lisens). Klikk eller trykk på **Bruk bare på utvalgte miljøer** for dette emnet. Velg et miljø fra rullegardinlisten, og klikk eller trykk på **Fortsett**.

    ![](./media/create-dlp-policy/select-environment-tenant.png)

    Vær oppmerksom på at miljømessige DLP-policyer kan ikke overstyre DLP-policyer som omfatter hele tenanten.
4. Klikk eller trykk på **Legg til** på **Datagrupper**-fanen under **Bare forretningsdata**.

    ![](./media/create-dlp-policy/data-groups.png)
5. Velg **Common Data Service** og **SharePoint** i **Legg til koblinger**-vinduet (du må kanskje bla ned eller søke for å finne dem), og deretter klikker eller trykker du på **Legg til koblinger** for å legge dem til datagruppen **Bare forretningsdata**.

    ![](./media/create-dlp-policy/add-connectors.png)

    Koblinger kan ligge i bare én datagruppe om gangen, og legges som standard til gruppen **Ingen forretningsdata tillatt**. Ved å flytte Common Data Service og SharePoint til gruppen **Bare forretningsdata**, hindrer du brukere i å opprette flyter og apper som kombinerer disse to koblingene med noen av koblingene i gruppen **Ingen forretningsdata tillatt**.

6. Klikk på **Lagre policy**.

    ![](./media/create-dlp-policy/save-policy.png)

Sikker datatilgang for Contoso-policyen opprettes og vises i listen over policyer for hindring av tap av data. Siden Twitter-koblingen befinner seg i datagruppen **Ingen forretningsdata tillatt**, sikrer denne policyen at Common Data Service og SharePoint ikke deler sine data til Twitter.

Det er god praksis for administratorer å dele en liste over DLP-policyer med sin organisasjon, slik at brukere er klar over policyer før oppretting av apper.

## <a name="next-steps"></a>Neste trinn
Dette emnet har tatt for seg hvordan du oppretter en DLP-policy for et enkeltmiljø for å hindre at viktige forretningsdata ved et uhell publiseres til koblinger som for eksempel Twitter. Hvis du vil lære mer om DLP-policyer, kan du se artikkelen om hvordan du administrerer dem.

> [!div class="nextstepaction"]
> [Å behandle policyer for hindring av datatap](prevent-data-loss.md)
