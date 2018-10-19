---
title: Slett en modelldrevet app | MicrosoftDocs
description: Finn ut hvordan du sletter eller fjerner en modelldrevet app fra PowerApps-miljøet.
keywords: ''
ms.date: 05/31/2018
ms.service: crm-online
ms.custom: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
ms.assetid: e82e7f64-37ad-41e5-acd7-16309881c6a2
author: Mattp123
ms.author: matp
manager: kvivek
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
caps.latest.revision: 9
topic-status: Drafting
ms.openlocfilehash: 9512c0b1c13f408b92c0c18f08946ea9afa1e62b
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/08/2018
ms.locfileid: "39696055"
---
# <a name="delete-a-model-driven-app"></a>Slett en modelldreven app

Slett eller fjern apper som er foreldet i miljøet.

1. Logg deg på [PowerApps](https://web.powerapps.com/).
2. Åpne [løsningsutforsker](advanced-navigation.md#solution-explorer). 
3. Velg **Apper** under **Komponenter** i løsningsvinduet.
4. Velg appen du vil slette, og velg deretter **Slett** på kommandolinjen.

    ![Slett en app](media/app-module-solution-window.png "Slett en app")

5. Velg **Slett** i bekreftelsesmeldingen som vises.

   Appen slettes fra miljøet ditt.
  
Hvis komponenten har avhengigheter (for eksempel relasjoner), må du fjerne avhengighetene før du kan slette appen. Hvis du vil se avhengighetene for en app, velger du appen, og deretter velger du **Vis avhengigheter** på kommandolinjen.

> [!NOTE]
> Når du sletter appen, anbefaler vi at du sletter det tilknyttede områdekartet. Hvis du ikke sletter det tilknyttede områdekartet, vises det en feilmelding for utforming av områdekart første gang du prøver å opprette en ny app med samme navn. Du kan imidlertid ignorere feilmeldingen, og feilen vises ikke når du prøver å opprette appen på nytt.


