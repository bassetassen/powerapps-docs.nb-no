---
title: Legg til en skjerm med rulling i en lerretsapp | Microsoft Docs
description: Opprett en skjerm i PowerApps der brukerne kan rulle for å vise flere typer innhold enn skjermen kan vise om gangen, i en lerretsapp.
author: lonu
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 10/25/2016
ms.author: lonu
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 4d9e72f51927d57611ece0a5583de9f6f50f843e
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/24/2018
ms.locfileid: "42863647"
---
# <a name="add-a-scrolling-screen-to-a-canvas-app-in-powerapps"></a>Legg til en skjerm med rulling i en lerretsapp i PowerApps

Opprett en skjerm der brukerne kan rulle for å vise ulike elementer, i en lerretsapp. Du kan for eksempel opprette en telefonapp som viser data i flere diagrammer, som brukerne kan vise hvis de ruller.

Når du legger til flere kontroller i en inndeling, opprettholder kontrollene sine relative plasseringen i denne inndelingen, uansett om det er en app for telefon eller nettbrett. Merk at skjermstørrelsen og skjermretningen kan bestemme hvordan avsnittene er ordnet.  

[!INCLUDE [app-customization-requirements](../../includes/app-customization-requirements.md)]

## <a name="create-a-scrolling-screen"></a>Å legge til en skjerm med rulling

1. Klikk eller trykk på **Ny skjerm** på **Hjem**-fanen:

    ![Alternativ for å legge til en skjerm i en app][1]

2. Klikk eller trykk på **Oppsett** på **Hjem**-fanen, og klikk eller trykk på alternativet om å legge til et uendelig rullende lerret:  
   
    ![Alternativ for å legge til et uendelig rulling lerret][2]
   
    Arbeidssonen er lagt til:  
   
    ![En skjerm med en uendelig rullende arbeidssone, slik det vises som standard][3]

## <a name="add-elements"></a>Å legge til elementer
Nå legger vi noen kontroller på arbeidssonen for å se hvordan den rullende skjermen fungerer.

1. Klikk eller trykk på **Legg til et element fra fanen Sett inn** i arbeidssonen du la til.
   
    ![][4]
2. Klikk eller trykk på **Diagrammer** på **Sett inn**-fanen, og klikk eller trykk deretter på **Stolpediagram**.
   
    ![Alternativ for å legge til et stolpediagram][5]
   
    Det vises et stolpediagram i det første kortet på skjermen:  
   
    ![Standard stolpediagram][7]
3. Klikk eller trykk på **Tekst** på **Sett inn**-fanen, og klikk eller trykk deretter på **Penneinndata**:  
   
    ![Alternativ for å legge til en pennekontroll][8]
4. Flytt pennekontrollen til nedenfor diagrammet, og endre størrelsen på pennekontrollen, slik at den dekker den nedre delen av kortet:  
   
    ![Flytt og juster størrelsen på pennekontrollen][9]

## <a name="add-a-section"></a>Å legge til en inndeling
La oss legge til et annet kort med en annen kontroll.

1. Klikk eller trykk på **Legg til inndeling** nær bunnen av skjermen:  
   
    ![Alternativ for å legge til en inndeling][10]
   
    Et nytt kort legges til på skjermen:  
   
    ![Et nytt kort nedenfor standardinndelingen][11]
2. Mens kortet fortsatt er valgt, kan du gå til **Sett inn**-fanen, klikke eller trykke på **Diagrammer** og deretter på **Linjediagram**.
   
    Det nye diagrammet er for stort til å vises på skjermen med de andre kontrollene:  
   
    ![Et linjediagram som er lagt til i bunnen av det nye kortet][12]
3. Åpne forhåndsvisningsmodus ved å trykke på F5 (eller ved å klikke på avspillingsikonet nær hjørnet øverst til høyre).
   
    ![Å åpne forhåndsvisningsmodus](./media/add-scrolling-screen/open-preview.png)
4. Rull ned for å vise det nye linjediagrammet.  
   
    ![Forhåndsvisningen viser linjediagrammet][13]

[1]: ./media/add-scrolling-screen/add-screen.png
[2]: ./media/add-scrolling-screen/add-canvas.png
[3]: ./media/add-scrolling-screen/default-canvas.png
[4]: ./media/add-scrolling-screen/insert-visual.png
[5]: ./media/add-scrolling-screen/add-chart.png
[7]: ./media/add-scrolling-screen/default-chart.png
[8]: ./media/add-scrolling-screen/add-pen.png
[9]: ./media/add-scrolling-screen/move-resize-pen.png
[10]: ./media/add-scrolling-screen/add-section.png
[11]: ./media/add-scrolling-screen/new-card.png
[12]: ./media/add-scrolling-screen/add-line-chart.png
[13]: ./media/add-scrolling-screen/line-chart-preview.png
