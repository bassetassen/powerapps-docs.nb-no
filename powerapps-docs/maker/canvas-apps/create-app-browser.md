---
title: Å opprette eller redigere apper i en nettleser | Microsoft Docs
description: Opprette eller redigere apper i en nettleser ved hjelp av PowerApps Studio for nett.
documentationcenter: na
author: aftowen
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: conceptual
ms.component: canvas
ms.date: 03/08/2018
ms.author: anneta
ms.openlocfilehash: 4add1e15c1a85b27b83295422dbb6472ac02ad9f
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/04/2018
ms.locfileid: "32329115"
---
# <a name="create-or-edit-apps-in-powerapps-studio-for-web"></a>Å opprette eller redigere apper i PowerApps Studio for nett
Opprette og redigere apper i PowerApps Studio for nett, som åpnes i et nettleservindu i Windows eller andre plattformer.

## <a name="prerequisites"></a>Forutsetninger
* [Registrer deg](../signup-for-powerapps.md) for PowerApps.
* Sørg for at du bruker en [nettleser som støttes](limits-and-config.md#supported-browsers-for-powerapps-studio).

## <a name="open-powerapps-studio-for-web"></a>Å åpne PowerApps Studio for nett
1. Å logge på [powerapps.com](http://go.microsoft.com/fwlink/p/?LinkId=708209).
2. Klikk eller trykk på **Ny app** nederst til venstre.

    ![Ny app i venstre navigasjonsfelt](./media/create-app-browser/left-nav.png)

PowerApps Studio for nett åpnes i en ny fane i nettleseren din, der du kan opprette og redigere apper på samme måte som i PowerApps Studio for Windows.

## <a name="known-limitations"></a>Kjente begrensninger
1. **Å opprette en tilkobling.**

    Hvis du vil [opprette en tilkobling](add-manage-connections.md) til en datakilde som krever godkjenning, kan du bruke [powerapps.com](https://web.powerapps.com), og deretter [legge til tilkoblingen](add-data-connection.md) til en app i PowerApps Studio for nett.
2. **Å redigere og lagre en app lokalt**.

    Bruk PowerApps Studio for Windows til å redigere og lagre apper lokalt for best resultat. Du kan ikke lagre endringer i en lokal app i en nettleser, eller du må lagre en ny fil i stedet for å erstatte filen som du åpnet.
3. **Å bruke signalfunksjoner.**

    Funksjonene **[Acceleration og Compass](functions/signals.md)** returnerer nøyaktige verdier i en publisert app, men disse funksjonene returnerer nullverdier når du oppretter eller endrer en app i en nettleser.
4. **Å eksportere og importere data.**

    Du kan [eksportere og importere data](controls/control-export-import.md) i en publisert app, men ikke når du oppretter eller endrer en app i en nettleser.
5. **Å kopiere en kontroll på tvers av to økter.**

    Du kan ikke kopiere kontroller fra én økt i PowerApps Studio for nett til en annen økt i PowerApps Studio for nett.

## <a name="next-steps"></a>Neste trinn
* Generer en app automatisk fra dataene i for eksempel [Excel](get-started-create-from-data.md) eller [SharePoint](app-from-sharepoint.md).
* Finn ut hvordan du kan [legge til en kontroll og angi egenskaper](add-configure-controls.md) som bestemmer hvordan appen vises og fungerer.
* Slipp løs kreativiteten din ved [å lage en app fra grunnen av](get-started-create-from-blank.md).
