---
title: Hurtigstart for å laste ned en liste over apper som er opprettet i miljøene dine | Microsoft Docs
description: I denne hurtigveiledningen lærer du hvordan du laster ned en liste over apper som er opprettet i miljøene dine
services: powerapps
suite: powerapps
documentationcenter: na
author: skjerland
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: quickstart
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/21/2018
ms.author: sharik
ms.openlocfilehash: debe9dd0ab3aa948537820cccd3304a6b4225c54
ms.sourcegitcommit: c5e3991e0e4e9f22a1e094d699f35adabfb97c6c
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/03/2018
ms.locfileid: "30998247"
---
# <a name="quickstart-download-a-list-of-apps-created-in-your-environments"></a>Hurtigstart: å laste ned en liste over apper som er opprettet i miljøene dine
Hvis du er miljøadministrator, kan du vise og laste ned en liste over apper som er opprettet i miljøer som du administrerer. Hvis du er global administrator for Office 365 eller tenantadministrator for Azure Active Directory, kan du laste ned en liste over apper som er opprettet i alle miljøer i organisasjonen din.

I denne hurtigveiledningen vil du lære hvordan du laster ned en liste over apper som er opprettet i et enkelt miljø til en CSV-fil og deretter viser listen i Excel.

## <a name="prerequisites"></a>Forutsetninger
 Følgende elementer kreves for å følge denne hurtigveiledningen:
 * En lisens for enten et PowerApps 2-abonnement eller et Microsoft Flow 2-abonnement. Du kan også registrere deg for en [gratis prøveversjon av PowerApps (abonnement 2)](https://web.powerapps.com/signup?redirect=marketing&email=).
 * Miljøadministrator for PowerApps, global administrator for Office 365 eller administrasjonstillatelser for tenanten til Azure Active Directory. Hvis du vil ha mer informasjon, kan du se [Miljøadministrasjon i PowerApps](environments-administration.md).

## <a name="sign-in-to-the-powerapps-admin-center"></a>Slik får du tilgang til administrasjonssenteret for PowerApps
Logg deg på administrasjonssenteret på [https://admin.powerapps.com]([https://admin.powerapps.com).

## <a name="download-the-list-of-apps"></a>Å laste ned listen over apper
1. I navigasjonsruten klikker eller trykker du på **Miljøer**, og deretter klikker eller trykker du på miljøet du ønsker å laste ned listen over apper for.

    ![Fil og Del](./media/admin-view-apps/environment.png)
2. På **Ressurser**-fanen klikker eller trykker du på **Apper**, og deretter klikker eller trykker du på **Last ned listen over apper**.

    ![Fil og Del](./media/admin-view-apps/resources-app.png)

    Listen over apper er lastet ned til en CSV-fil. Denne prosessen kan ta flere minutter. Kontroller at du ikke lukker vinduet før listen er lastet helt ned, ellers må du kanskje starte prosessen på nytt.

## <a name="view-the-list"></a>Å vise listen
Når CSV-filen er opprettet, kan du åpne den i Excel. Listen inneholder navnet på appen, eieren av appen, alle koblinger som appen bruker til å koble til datakilder, og annen informasjon.

![Fil og Del](./media/admin-view-apps/excel-view.png)

## <a name="next-steps"></a>Neste trinn
I denne hurtigveiledningen lærte du hvordan du laster ned og viser en liste over apper som er opprettet i et miljø i organisasjonen. Deretter kan du lære hvordan du administrerer apper som er opprettet i organisasjonen.

> [!div class="nextstepaction"]
> [Administrere apper som er opprettet i organisasjonen](admin-manage-apps.md)
