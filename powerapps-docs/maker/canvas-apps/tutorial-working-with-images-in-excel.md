---
title: Lagring av bilder i en Excel-fil | Microsoft Docs
description: Slik lagrer du bilder i en Excel-tabell på en skylagringskonto
author: AFTOwen
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 06/15/2016
ms.author: anneta
ms.openlocfilehash: 5c84da8bb0873fd42f5d352ae463f013113d8fcd
ms.sourcegitcommit: dfa0e1a7981814e15e6ca4720e2a5f930e859db1
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 07/13/2018
ms.locfileid: "39023877"
---
# <a name="how-to-save-images-in-an-excel-file-and-then-add-these-images-to-your-app"></a>Slik lagrer du bilder i en Excel-fil, og deretter legger disse bildene inn i appen

I denne opplæringen skal vi:

* Opprette en Excel-fil og formatere den som en tabell
* Opprette en tilkobling til OneDrive for Business. En hvilken som helst skylagringskonto vil fungere. OneDrive for Business brukes i denne gjennomgangen.
* Lage en app med en kontroll for penneinndata
* Lagre bildene som er blitt opprettet fra kontrollen for penneinndata til en Excel-fil
* Vise bilder fra en Excel-fil i appen din

[!INCLUDE [app-customization-requirements](../../includes/app-customization-requirements.md)]
* Slik finner du ut hvordan du [legger til en datakilde](add-data-connection.md)

## <a name="create-the-excel-file-as-a-table"></a>Slik oppretter du en Excel-fil som en tabell

1. Gi navnet **Bilde [bilde]** til en kolonne i en tom Excel-fil.
2. Oppretting av en tabell ved å gjøre følgende:    
   
   1. Velg en hvilken som helst type data i en hvilken som helst rad og kolonne. Velg for eksempel **Bilde**.
   2. Velg **Tabell** på **Sett inn**-båndet.
   3. Velg **Tabellen min har overskrifter**i dialogvinduet, og velg deretter **OK**.
      
      Excel-filen er nå i tabellformat. [Slik formaterer du dataene som en tabell](https://support.office.com/article/Format-an-Excel-table-6789619F-C889-495C-99C2-2F971C0E2370) gir ytterligere informasjon om tabellformatering i Excel.
   4. Gi tabellen navnet **Tegninger**:  
      
      ![Slik ender du navnet på tabellen til Tegninger](./media/tutorial-working-with-images-in-excel/drawings-table.png)
3. Gi navn til Excel-filen **SavePen.xlsx**, og lagre filen i skylagringskontoen (OneDrive for Business, Dropbox og så videre).

## <a name="create-an-app-with-the-pen-control"></a>Oppretting av en app med pennekontrollen
1. Opprett en [tom app](get-started-create-from-blank.md) i PowerApps.
2. Legg til en skylagringskonto som en [datakilde](add-data-connection.md) i appen din. Når du har lagt den til som en datakilde, kan du legge til **SavePen.xlsx** som en tilkobling, og deretter velge tabellen **Tegninger**:  
   ![Koble til](./media/tutorial-working-with-images-in-excel/savepen.png)  
   
   Nå er Tegninger-tabellen oppført som en datakilde.
3. Velg **Tekst** på **Sett inn**-menyen, og velg deretter **Penneinndata**. Gi den det nye navnet **MyPen**:  
   
   ![Gi nytt navn](./media/tutorial-working-with-images-in-excel/rename-mypen.png)
4. Legg til en **Knapp** (**Sett inn**-menyen), og angi **OnSelect**-egenskapen til denne formelen:  
   `Patch(Drawings, Defaults(Drawings), {Image:MyPen.Image})`
5. Legg til en **Bildegalleri**-kontroll (**Sett inn**-meny > **Galleri**), og angi kontrollens **Items**-egenskap til `Drawings`. Gallerikontrollens **Image**-egenskap angis automatisk til `ThisItem.Image`.
   
   Skjermen burde se omtrent slik ut:  
   
   ![Eksempel på skjerm](./media/tutorial-working-with-images-in-excel/screen.png)  
6. Trykk på F5, eller velg Forhåndsvisning (![](./media/tutorial-working-with-images-in-excel/preview.png)). Tegn noe i MyPen, og velg deretter knappen. Det første bildet i gallerikontrollen viser det du tegnet. Legg til noe mer på tegningen, og velg knappen. Det andre bildet i gallerikontrollen viser det du tegnet.
   
   Lukk forhåndsvisningsvinduet.
7. Gå til skylagringskontoen. Det er en ny **SavePen_images**-mappe der som ble opprettet automatisk. Du må kanskje oppdatere for å se den nye mappen. Denne mappen inneholder de lagrede bildene, sammen med ID-ene for filnavnene deres.
   
    Slik åpner du SavePen.xlsx. Bilde-kolonnen inneholder banen til disse nye bildene.

## <a name="add-the-image-in-an-excel-file-to-your-app"></a>Slik legger du til bildet i en Excel-fil i appen din
I et annet eksempel kan du lagre bilder i en skylagringskonto, og deretter bruke en Excel-tabell til å vise bildene i appen.

I dette eksemplet bruker vi [CreateFirstApp.zip](http://pwrappssamples.blob.core.windows.net/samples/CreateFirstApp.zip), som inneholder noen .jpeg files.

> [!NOTE]
> Når du viser bilder fra en Excel-fil, må banen til disse bildene bruke skråstreker. Når PowerApps lagrer bilder i en Excel-tabell (som i de forrige trinnene), bruker banen omvendte skråstreker. Så du kan også bruke **SavePen_images** fra det forrige eksemplet. Hvis du gjør dette, må du endre banene i Excel-tabellen slik at de bruker skråstreker i stedet for omvendte skråstreker. Ellers vil ikke bildene vises.  

1. Last ned [CreateFirstApp.zip](http://pwrappssamples.blob.core.windows.net/samples/CreateFirstApp.zip), og pakk ut **Ressurs**-mappen i skylagringskontoen.
2. I et Excel-regneark kan du opprette en tabell som ser omtrent slik ut:
   
    ![Jakke-tabell](./media/tutorial-working-with-images-in-excel/jackets.png)
3. Gi tabellen navnet **Jakker**. Gi Excel-filen navnet **Aktiva.xlsx**. Du kan også endre navnet på **Aktiva**-mappen til **Assets_images**.
4. Legg **Jakker**-tabellen til som en datakilde i appen.  
5. Legg til en **Kun bilde**-kontroll (**Sett inn**-menyen > **Galleri**), og angi **Items**-egenskapen til `Jackets`:  
   
    ![Items-egenskap](./media/tutorial-working-with-images-in-excel/items-jackets.png)
   
    Galleriet oppdateres automatisk med bildene:  
   
    ![Bilder av jakker](./media/tutorial-working-with-images-in-excel/images.png)

Når du angir Items-egenskapen, legges det automatisk til en kolonne med navnet **PowerAppsId** i Excel-tabellen.

I Excel-tabellen kan bildebanen også være nettadressen til et bilde. Last ned eksempelfilen [Beregning av gulvbelegg](http://pwrappssamples.blob.core.windows.net/samples/FlooringEstimates.xlsx) til skylagringskontoen din, legg til `FlooringEstimates`-tabellen som en datakilde i appen din, og angi gallerikontrollen til `FlooringEstimates`. Galleriet oppdateres automatisk med bildene.

## <a name="learn-more"></a>Mer informasjon
[Slik legger du til et bilde, en video eller lyd](add-images-pictures-audio-video.md)  
[Visning av data i et linje-, sektor- eller liggende stolpediagram i appen din](use-line-pie-bar-chart.md)  
[Slik fungerer tabeller og poster i PowerApps](working-with-tables.md)

