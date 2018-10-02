---
title: Slette en modelldrevet app | MicrosoftDocs
description: Lær hvordan du kan slette eller fjerne en modelldrevet app fra PowerApps-miljøet.
keywords: ''
ms.date: 05/31/2018
ms.service: crm-online
ms.custom: null
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
ms.assetid: e82e7f64-37ad-41e5-acd7-16309881c6a2
author: Mattp123
ms.author: matp
manager: kvivek
ms.reviewer: null
ms.suite: null
ms.tgt_pltfrm: null
caps.latest.revision: 9
topic-status: Drafting
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="delete-a-model-driven-app"></a>Slette en modelldrevet app

Du kan slette eller fjerne apper som er foreldede, fra miljøet ditt.

1. Logg på [PowerApps](https://web.powerapps.com/).
2. Åpne [løsningsutforskeren](advanced-navigation.md#solution-explorer). 
3. Velg **Apper** under **Komponenter** i løsningsvinduet.
4. Velg appen du vil slette, og velg deretter **Slett** på kommandolinjen.

    ![Slette en app](media/app-module-solution-window.png "Slette en app")

5. Velg **Slett** i bekreftelsesmeldingen som vises.

   Appen slettes fra miljøet.
  
Hvis komponenten har avhengigheter (for eksempel relasjoner), må du først fjerne avhengighetene før du kan slette appen. Hvis du vil vise avhengighetene for en app, velger du appen og deretter **Vis avhengigheter** på kommandolinjen.

> [!NOTE]
> Når du sletter appen, anbefales det å slette det tilknyttede områdekartet. Hvis du ikke sletter det tilknyttede områdekartet, viser utforming av områdekart en feil den første gangen du prøver å opprette en ny app med samme navn. Du kan imidlertid ignorere feilen, og feilen vises ikke når du prøver å opprette appen på nytt.


