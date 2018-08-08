---
title: Last ned en liste over aktive brukere i leieren | Microsoft Docs
description: I denne hurtiginnføringen lærer du hvordan du laster ned en liste over aktive brukere i tenanten
author: jimholtz
ms.service: powerapps
ms.component: pa-admin
ms.topic: quickstart
ms.date: 03/21/2018
ms.author: jimholtz
ms.openlocfilehash: e2c00f4ab10b2dc6cecc63d9539ffcf86a5bfcb8
ms.sourcegitcommit: 2e7b621066cdc3e7be329d5213ecfee0b4223641
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 07/30/2018
ms.locfileid: "39348861"
---
# <a name="download-a-list-of-active-users-in-your-tenant"></a>Last ned en liste over aktive brukere i leieren
Hvis du er en global 365-administrator eller administrator for tenanten til Azure Active Directory, kan du laste ned en liste over aktive brukere i tenanten, slik at du ikke bare kan se hvem som har tilgang til PowerApps, Microsoft Flow eller begge, men også lisensene tilordnet til disse brukerne.

Dette emnet tar for seg hvordan du laster ned en liste over aktive brukere til en CSV-fil, og deretter viser denne listen i Excel.

Du må være global administrator for Office 365 eller ha administrasjonstillatelser for leieren i Azure Active Directory for å følge denne fremgangsmåten.

## <a name="sign-in-to-the-powerapps-admin-center"></a>Å logge på administrasjonssenteret for PowerApps
Logg på administrasjonssenteret på [https://admin.powerapps.com]([https://admin.powerapps.com).

## <a name="download-the-list-of-users"></a>Å laste ned listen over brukere
I navigasjonsruten klikker eller trykker du på **Brukerlisenser**, og deretter klikker eller trykker du på **Laste ned en liste med aktive brukerlisenser**.

![Fil og Del](./media/admin-view-user-licenses/download-list.png)

Listen over brukere er lastet ned til en CSV-fil. Denne prosessen kan ta flere minutter. Kontroller at du ikke lukker vinduet før listen er lastet helt ned, ellers må du kanskje starte prosessen på nytt.

## <a name="view-the-list"></a>Å vise listen
Når CSV-filen er opprettet, kan du åpne den i Excel. Listen inneholder brukernes navn, e-postadresse, lisenstype og annen informasjon.

En bruker som har åpnet et produkt minst én gang regnes som en *aktiv bruker*. Siden denne listen inneholder aktive brukere, inneholder den ikke brukere som har lisenser for PowerApps og Microsoft Flow men som aldri har benyttet seg av dem. Du kan vise alle brukerlisenser fra [administrasjonssenteret for Office 365](https://support.office.com/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc).

Dette eksemplet viser to brukere som har lisenser for både PowerApps og Microsoft Flow. Kari Nordmann har tilgang via et Office 365-abonnement, og Ola Nordmann fikk en prøvelisens for hvert produkt.

![Fil og Del](./media/admin-view-user-licenses/table2.png)

Hvis en bruker har forlatt organisasjonen, vil listen vise **Ukjent** i kolonner som **Brukernavn** og **E-postadresse**. Hvis listen viser **Ukjent** men ingen har forlatt organisasjonen, kan du vente et par minutter og deretter laste ned listen på nytt.

Hvis du vil legge til brukerlisenser, kan du åpne [administrasjonssenteret for Office 365](https://support.office.com/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc).

## <a name="next-steps"></a>Neste trinn
Dette emnet har tatt for seg hvordan du laster ned en liste over aktive brukere i leieren din. Hvis du finne ut hvordan du laster ned og viser en liste over apper som er opprettet i miljøene dine, fortsetter du til neste emne.

> [!div class="nextstepaction"]
> [Last ned en liste over apper som er opprettet i miljøene dine](admin-view-apps.md)
