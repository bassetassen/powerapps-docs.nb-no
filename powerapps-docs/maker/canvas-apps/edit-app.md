---
title: Rediger en app | Microsoft Docs
description: Trinnvise instruksjoner for hvordan du redigerer apper og scenarioer med låste økter.
services: ''
suite: powerapps
documentationcenter: na
author: karthik-1
manager: anneta
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 05/19/2017
ms.author: sharik
ms.openlocfilehash: a71aa71ec80a60f2aec4ce179abcade3f9eef964
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/22/2018
ms.locfileid: "30997082"
---
# <a name="edit-an-app-in-powerapps"></a>Rediger en app i PowerApps
Du kan redigere alle apper du har utviklet, som du eier eller har **Kan redigere**-tillatelse for. Du kan redigere en app i enten PowerApps Studio for nett eller PowerApps Studio for Windows. Hvis du prøver å redigere en app som er åpnet for redigering et annet sted, vil du motta en beskjed om at du eller en annen bruker allerede har den åpen.

## <a name="verify-your-permissions"></a>Bekreft tillatelsen din
1. Logg på [PowerApps](https://web.powerapps.com), og klikk eller trykk deretter på **Apper** i **Fil**-menyen (nær venstre kant).
   
    ![Alternativ for apper i Fil-menyen](./media/edit-app/file-apps.png)
2. Åpne appkategori-velgeren, og deretter klikk eller trykk på enten **Apper jeg eier** eller **Apper jeg bidrar til**.
   
    ![Appkategori-velger](./media/edit-app/app-category.png)
   
    Du kan redigere enhver app i listen som vises. Du kan også søke etter en app ved å skrive inn en eller flere tegn i søkefeltet nær hjørnet øverst til høyre.
   
    > [!NOTE]
> Hvis du fortsatt ikke ser appen du vil redigere, må du bekrefte at du har valgt det riktige miljøet nær hjørnet øverst til høyre.
   
    ![Liste over miljøer](./media/edit-app/environment-list.png)

## <a name="edit-an-app-in-powerapps-studio-for-web"></a>Rediger en app i PowerApps Studio for nett
1. Følg trinnene i forrige fremgangsmåte for å finne appen du vil redigere.
2. Klikk eller trykk på Info-ikonet til appen nær høyre kant.
   
    ![Info-ikon](./media/edit-app/app-edit.png)
3. Klikk eller trykk på **Rediger**-ikonet nær hjørnet øverst til høyre, og klikk eller trykk deretter på **Rediger på nettet**.
   
    ![Rediger-ikon](./media/edit-app/edit-icon.png)

## <a name="edit-an-app-in-powerapps-studio-for-windows"></a>Rediger en app i PowerApps Studio for Windows
1. Åpne PowerApps Studio for Windows.
2. Finn appen du vil redigere på siden som vises som standard.
   
    Du kan enkelt finne en app ved å klikke eller trykke på søkeikonet nær hjørnet øverst til høyre og deretter skrive inn et eller flere tegn fra appens navn. Du kan også sortere listen etter navn, dato for sist endret eller dato for sist åpnet. Hvis appen du leter etter fortsatt ikke vises, må du bekrefte at du er i det riktige PowerApps-miljøet, som beskrevet i den første prosedyren.
   
    ![](./media/edit-app/sort-filter.png)
3. Klikk eller trykk på blyantikonet for appen du vil redigere, nær høyre kant.
   
    Du kan redigere alle apper hvor blyantikonet er svart og ikke grått.
   
    ![](./media/edit-app/app-editstudio.png)

## <a name="collaborate-on-an-app"></a>Samarbeide på en app
Alle som har **Kan redigere**-tillatelse for en app, kan redigere den, men kun én person kan redigere appen av gangen. Hvis du prøver å redigere en app som noen andre allerede redigerer, vises denne meldingen. Du kan ikke fortsette før den andre personen lukker appen (eller personens økt blir tidsavbrutt).

![](./media/edit-app/applock-otheruser.png)

Denne meldingen vises også hvis du åpner en app for redigering og deretter prøver å åpne appen på en annen enhet eller i et annet nettleservindu. Du kan overstyre den forrige økten, men det gjør at du kanskje mister eventuelle endringer som du ikke har lagret.

![](./media/edit-app/applock-selfuser.png)

## <a name="next-steps"></a>Neste trinn
Finn ut mer om hvordan du legger til en [skjerm](add-screen-context-variables.md), en [kontroll](add-configure-controls.md) eller en [datatilkobling](add-data-connection.md).

