---
title: Opprett et diagram i en lerretsapp | Microsoft Docs
description: Vis datakategorier som linjediagrammer, sektordiagrammer eller liggende stolpediagrammer i en lerretsapp i PowerApps
author: fikaradz
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 10/23/2016
ms.author: fikaradz
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 0b710346c5e264fc13ee3cacb00073a32a4de0f0
ms.sourcegitcommit: 4ed29d83e90a2ecbb2f5e9ec5578e47a293a55ab
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/23/2019
ms.locfileid: "63318309"
---
# <a name="show-data-in-a-line-pie-or-bar-chart-in-powerapps"></a>Å vise data i en linje, sektor- eller liggende stolpediagram i PowerApps

Bruk linjediagrammer, sektordiagrammer og liggende stolpediagrammer til å vise dataene dine i en lerretsapp. Når du arbeider med diagrammer, bør dataene du importerer, struktureres basert på disse kriteriene:

* Hver serie bør være i den første raden.
* Etiketter må være i kolonnen lengst til venstre.

Skjermen burde for eksempel se omtrent slik ut:

![][9]

Du kan opprette og bruke disse diagrammene i PowerApps. La oss komme i gang.

## <a name="prerequisites"></a>Forutsetninger

* [Registrer deg](../signup-for-powerapps.md) for PowerApps, og deretter [logger du deg på](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) ved å oppgi samme legitimasjon som du brukte til å registrere deg.
* Opprett en app fra en [mal](get-started-test-drive.md), fra [data](get-started-create-from-data.md) eller fra [bunnen av](get-started-create-from-blank.md).
* Finn ut hvordan du [konfigurerer en kontroll](add-configure-controls.md) i PowerApps.
* Last ned [ChartData.zip](http://pwrappssamples.blob.core.windows.net/samples/ChartData.zip), som inneholder eksempeldata som en XML-fil. Følg trinnene i dette emnet for å importere den direkte til appen. Som et alternativ, dekomprimer ZIP-filen, åpne XML-filen i Excel og lagre det i en [skylagringskonto](connections/cloud-storage-blob-connections.md).

## <a name="import-the-sample-data"></a>Å importere eksempeldataene
I disse trinnene importerer vi eksempeldataene til en samling, kalt **ProductRevenue**.

1. Velg **Kontroller** på **Sett inn**-fanen, og velg deretter **Importer**:  

    ![][11]  

2. Angi kontrollens **[OnSelect](controls/properties-core.md)**-egenskap til følgende funksjon:  

   ```Collect(ProductRevenue, Import1.Data)```

3. Trykk F5 for å åpne forhåndsvisningsmodus, og velg deretter **Importer data**-knappen.

4. Velg ChartData.zip i dialogboksen **Åpne**, velg **Åpne** og trykk deretter Esc.

5. Velg **samlinger** på **Fil**-menyen.

    Samlingen ProductRevenue er oppført med diagramdataene du importerte:

    ![][1]  

   > [!NOTE]
   > Importkontrollen brukes til å importere Excel-lignende data og opprette samlingen. Importkontrollen importerer data når du oppretter appen, og forhåndsviser appen. Importkontrollen importer for øyeblikket ikke data når du publiserer appen.
   >

6. Trykk på ESC for å gå tilbake til standardarbeidsområdet.

## <a name="add-a-pie-chart"></a>Å legge til et sektordiagram
1. Velg **Diagrammer** på **Sett inn**-fanen, og velg deretter **Sektordiagram**.

2. Flytt sektordiagrammet under **Importer data**-knappen.

3. Velg midten av sektordiagrammet i sektordiagram-kontrollen:   

    ![][10]

4. Angi **[Element](controls/properties-core.md)**-egenskapen til sektordiagrammet til dette uttrykket: `ProductRevenue.Revenue2014`

    ![][2]  

    Sektordiagrammet viser omsetningsdata fra 2014.

    ![][3]  

## <a name="add-a-bar-chart-to-display-your-data"></a>Å legge til et liggende stolpediagram for å vise dataene
Nå skal vi bruke denne ProductRevenue-samlingen i et liggende stolpediagram:

1. Legg til en ny skjerm på **Hjem**-fanen.]

2. Velg **Diagrammer** på **Sett inn**-fanen, og velg deretter **Stolpediagram**.

3. Velg midten av dette stolpediagrammet. Angi **[Element](controls/properties-core.md)**-egenskapen for stolpediagrammet til ```ProductRevenue```:

    ![][12]  

    Stolpediagrammet viser omsetningsdata fra 2012:

    ![][4]  

4. Velg den midtstilte firkanten i stolpediagrammet:

    ![][5]

5. Velg **Antall serier** på **Diagram**-fanen, og skriv deretter inn **3** på formellinjen:

    ![][6]  

    Stolpediagrammet viser omsetningsdata for hvert produkt over tre år:

    ![][7]  

[1]: ./media/use-line-pie-bar-chart/productrevenuecollection.png
[2]: ./media/use-line-pie-bar-chart/itemsexpression.png
[3]: ./media/use-line-pie-bar-chart/piechart.png
[4]: ./media/use-line-pie-bar-chart/columnchart.png
[5]: ./media/use-line-pie-bar-chart/columnchartseries.png
[6]: ./media/use-line-pie-bar-chart/columnchartseriesfunction.png
[7]: ./media/use-line-pie-bar-chart/columnchartthreeyears.png
[8]: ./media/use-line-pie-bar-chart/preview.png
[9]: ./media/use-line-pie-bar-chart/tableformat.png
[10]: ./media/use-line-pie-bar-chart/middlepiechart.png
[11]: ./media/use-line-pie-bar-chart/import.png
[12]: ./media/use-line-pie-bar-chart/itemscolumnchart.png
