---
title: Å opprette og oppdatere en samling | Microsoft Docs
description: Å opprette samlinger og legge til kolonner i eksisterende samlinger i PowerApps
author: lonu
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 11/30/2015
ms.author: lonu
ms.openlocfilehash: 27b5a3453c2c0a89239d3e319ee6f39afd034492
ms.sourcegitcommit: dfa0e1a7981814e15e6ca4720e2a5f930e859db1
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 07/13/2018
ms.locfileid: "39023279"
---
# <a name="create-and-update-a-collection-in-your-app"></a>Å opprette og oppdatere en samling i appen
Bruk en samling til å lagre data som kan brukes i en app. En samling er en gruppe lignende elementer. Du har for eksempel opprettet en MyImages-samling som inneholder alle produktbildene som firmaet selger. Du kan legge til MyImages-samlingen i PowerApps og opprette en app som viser alle bildene av disse produktene. I et annet eksempel kan du opprette en PriceList-samling som viser produktene og prisen for hvert produkt.

Du kan opprette og bruke samlingene i PowerApps. La oss komme i gang.

### <a name="prerequisites"></a>Forutsetninger
* [Registrer deg](../signup-for-powerapps.md) for PowerApps, og deretter [logger du deg på](https://web.powerapps.com) ved å angi samme legitimasjon som du brukte til å registrere deg.
* Opprett en app eller åpne en eksisterende app i PowerApps.
* Finn ut hvordan du [konfigurerer en kontroll](add-configure-controls.md) i PowerApps.
* Denne fremgangsmåten bruker [PriceList.zip](http://pwrappssamples.blob.core.windows.net/samples/PriceList.zip)-filen som eksempeldata. Zip-filen inneholder en XML-fil som kan konverteres til Excel. PowerApps leser ellers automatisk ZIP-filene og importerer dem. Du kan laste ned og bruke disse eksempeldataene eller importere dine egne.

## <a name="create-a-single-column-collection"></a>Å opprette en enkeltkolonne-samling
Følgende fremgangsmåte viser deg hvordan du oppretter en samling i appen ved hjelp av Innsamling-funksjonen, og hvordan du legger til elementer i samlingen din.

1. Å åpne appen.
2. Velg **Tekst** på **Sett inn**-fanen, og velg **Tekstinndata**:  
   ![][1]  
3. Velg **Text1** i hjørnet øverst til venstre, angi **Mål** som nytt navn for kontrollen:  
   ![][2]  
4. Velg **Knapp** på **Sett inn**-fanen for å legge til en knappkontroll i utformingen. **[OnSelect](controls/properties-core.md)**-egenskapen vises i rullegardinlisten. Konfigurer den til følgende funksjon:  
   
    ```Collect(Destinations, Destination!Text)```
   
    Den skal se slik ut:  
    ![][3]  
5. Velg knappeteksten, og angi **Legg til**:  
   ![][5]  
6. Velg **Legg til**-knappen, og flytt den under tekstkontrollen. Du kan flytte den hvor som helst:  
   ![][6]  

Du brukte Innsamling-funksjonen til å opprette en samling med navnet **Mål** i disse trinnene. Du har også lagt til en knappkontroll, og når den blir valgt, legger den til nye elementer i samlingen. Nå kan du se hva du har opprettet:

1. Velg Forhåndsvisning:  
   ![][7]  
2. Skriv inn et bynavn i boksen, og velg deretter **Legg til**-knappen.
3. Skriv inn noen flere bynavn, og velg **Legg til**-knappen hver gang.
4. Trykk på **ESC** for å lukke vinduet for forhåndsvisning.
5. Se Mål-samlingen og de angitte tekstverdiene. Velg **Samlinger** på **Fil**-fanen. Teksten du skrev inn, er oppført:  
   ![][8]

#### <a name="extra-credit"></a>Viderekomne
Nå skal vi binde Mål-samlingen til en liste:

1. Gå tilbake til utforming.
2. Velg **Kontroller** på **Sett inn**-fanen, og velg deretter **ListBox**:  
   ![][22]  
3. Flytt listeboksen slik at du enkelt kan se den. Angi kontrollens **[Element](controls/properties-core.md)**-egenskap til følgende uttrykk:  
   ```Destinations!Value```  <br/>
   
    Når du gjør dette, blir listeboksen automatisk fylt ut med elementer som du tidligere har angitt i Mål-samlingen:  
   ![][4]  

Forhåndsvis endringene: ![][7]. Du kan se de forskjellige byene du har skrevet inn i listeboksen. Angi en ny by i kontrollen for innskriving av tekst, og velg **Legg til**-knappen. Listeboksen oppdateres automatisk hvis du vil inkludere den nye byen du skrev inn.

## <a name="create-a-multi-column-collection"></a>Å opprette en samling med flere kolonner
Følgende fremgangsmåte viser deg hvordan du oppretter en samling i appen ved hjelp av Innsamling-funksjonen, og hvordan du legger til flere rader i samlingen din.

1. Åpne en ny skjerm på **Hjem**-fanen.
2. Velg **Tekst** på **Sett inn**-fanen, og velg **Tekstinndata**.
3. Angi **By** som nytt navn for tekst-kontrollen:  
   ![][9]  
4. Sett inn en annen kontroll for innskriving av tekst, og endre navnet til **Delstater**.
5. Flytt tekstkontrollene for By og Delstat slik at du kan se begge:  
   ![][10]  
   
    > [!NOTE]
   > Du kan erstatte «innskriving av tekst» med noe annet, som «By» eller «Delstat», slik det ble gjort i bildet.  
6. Velg **Knapp** på **Sett inn**-fanen. Angi knappens **[OnSelect](controls/properties-core.md)**-egenskap til følgende funksjon:  
   ```Collect(Destinations, {Cities:City!Text, States:States!Text})```  
   
    Den skal se slik ut:  
    ![][11]  
   
    > [!NOTE]
   > Du kan bruke den samme funksjonen til å legge til ekstra kolonner i denne samlingen. Du kan for eksempel legge til en annen kontroll for innskriving av tekst for Land for å legge til en Land-kolonne:
   
    `Collect(Destinations, {Cities:City!Text, States:States!Text}, {Countries:Country!Text})`
7. Gi nytt navn til knappekontrollen **AddCityStateButton**, og angi **Legg til by og delstat** for **[Tekst](controls/properties-core.md)**-egenskapen:  
   ![][12]  

I disse trinnene la du til en **Byer**-kolonne og en **Delstater**-kolonne i **Mål**-samlingen. Knappekontrollen legger til disse nye tekstelementene i samlingen. Nå kan du se hva du har opprettet:

1. Velg Forhåndsvisning:  
   ![][7]  
2. Skriv inn tekst i By- og Delstat-boksene, og velg deretter knappen **Legg til by og delstat**.
3. Å legge til flere byer og delstater.
4. Trykk på **ESC** for å lukke vinduet for forhåndsvisning.
5. Hvis du vil se alle elementene du har lagt til i Mål-samlingen, kan du velge **Fil**-fanen og deretter velge **Samlinger**:  
   ![][13]

## <a name="add-columns-to-a-collection"></a>Å legge til kolonner i en samling
Det finnes noen inndelinger i denne gjennomgangen. Når operasjonen er fullført, vet du hvordan du importerer data i en samling, oppretter et galleri som viser data i en prisliste og bruker en glidebryter som bestemmer antall for et produkt.

### <a name="import-the-price-list-and-create-the-collection"></a>Å importere prislisten og opprette samlingen
1. Last ned ZIP-filen [PriceList](http://pwrappssamples.blob.core.windows.net/samples/PriceList.zip).
2. Legg til en ny skjerm på **Hjem**-fanen.
3. Velg **Kontroller** på **Sett inn**-fanen, og velg deretter **Importer**:  
   ![][14]  
4. Velg **OnSelect** på **Handling**-fanen. Angi følgende funksjon:  
   
    ```Collect(PriceList, Import1!Data)```  
5. Forhåndsvis appen. Velg **Importdata**-knappen, velg PriceList.zip-filen, og velg **Åpne**.
6. Lukk Forhåndsvisning-vinduet.
7. Velg **Fil**-fanen, og velg deretter **Samlinger**. Prisliste-elementene du importerte, er oppført:  
   ![][15]

### <a name="add-the-gallery-to-show-the-collection-items"></a>Å legge til galleriet for å vise elementene i samlingen
1. Gå tilbake til utforming.
2. Gå til **Sett inn**-fanen, velg **Galleri**, bla ned til **Egendefinerte gallerier**, og velg deretter **Stående**:    
   ![][16]  
3. Angi **Prisgalleri** som nytt navn for galleriet, og angi **Prisliste** for **[Elementer](controls/properties-core.md)**-egenskapen:  
   ![][18]  
4. Flytt PriceList-galleriet under **Importdata**-kontrollen. Velg kantlinjene for galleriet, og bruk klikk-og-dra for å endre størrelsen på galleriet slik at tre ruter vises.
5. Velg den første firkanten i galleriet, og legg til tre etiketter (**Sett inn**-fanen > **Etikett**).
6. Endre størrelsen til etikettene og ordne dem i en rad nær toppen av i den første firkanten. Galleriet ser omtrent slik ut:  
   ![][19]
7. Angi følgende uttrykk for **[Tekst](controls/properties-core.md)**-egenskapen for hver etikett:  
   
   | Etikett | Angi følgende for Tekst-egenskapen |
   | --- | --- |
   | Etikett1 |``ThisItem!Name`` |
   | Etikett2 |``Text(ThisItem!Price, "$#")`` |
   | Etikett3 |``ThisItem!Maker`` |
   
    Når du gjør dette, oppdateres etikettene automatisk med verdier for navn, pris og produsent i PriceList-samlingen.
8. Endre størrelsen på etikettene og galleriet for å fjerne ekstra mellomrom. Skjermen ser omtrent slik ut:  
   ![][17]

### <a name="add-the-quantity-slider-and-update-the-collection"></a>Legge til glidebryteren for antall, og oppdater samlingen
1. Velg **Kontroller** på **Sett inn**-menyen, og velg **Glidebryter**. Angi det nye navnet **OrderQty** for glidebryteren, og flytt den til under galleriet.
2. Legg til en knapp, angi **Legg til** for **[Tekst](controls/properties-core.md)**-egenskapen, og flytt den til under glidebryteren **OrderQty**. Appen ser omtrent slik ut:  
   ![][20]
3. Angi følgende uttrykk for **[OnSelect](controls/properties-core.md)**-egenskapen for **Legg til**-knappen:  
   
    ```Collect(OrderList, {Name:PriceGallery!Selected!Name, Qty:OrderQty!Value, Cost:OrderQty!Value*LookUp(PriceList, PriceGallery!Selected!Name in Name, Price)});SaveData(OrderList, "orderfile")```  
   
    > [!NOTE]
   > Når du velger denne knappen senere i denne prosedyren, må du opprette og lagre en samling med navnet **OrderList**. Samlingen inneholder navnet på et produkt som du angir i galleriet, et antall som du velger med glidebryteren, og de totale kostnadene som beregnes ved å gange antallet med prisen på produktet.
4. Velg **Skjerm**-fanen og angi **[OnVisible](controls/control-screen.md)**-egenskapen til følgende uttrykk:  
   
    ```If(IsEmpty(PriceList), LoadData(PriceList, "pricefile"));If(IsEmpty(OrderList), LoadData(OrderList, "orderfile"))```

Nå kan du se hva du har opprettet:

1. Åpne **Forhåndsvisning**.
2. Velg et produkt i galleriet, flytt glidebryteren til ønsket antall og velg deretter **Legg til**-knappen.  
   
   > [!IMPORTANT]
   > Når du velger et produkt, blir ikke dette produktet uthevet for å indikere at du valgte den. Da vi opprettet galleriet, la vi ikke til denne funksjonaliteten. Vær oppmerksom på at du ikke velger produktet ved å klikke på det.  
   > 
   > 
3. Gjenta disse trinnene hvis du vil legge til flere produkter. Trykk på **ESC** for å lukke Forhåndsvisning-vinduet.
4. Velg **Samlinger** på **Fil**-fanen for å vise en forhåndsvisning av **Ordreliste**-samlingen du opprettet:  
   ![][21]

> [!TIP]
> Hvis du vil fjerne alle elementer fra listen, kan du legge til en knapp, angi **Fjern** for **[Tekst](controls/properties-core.md)**-egenskapen, og angi følgende uttrykk for **[OnSelect](controls/properties-core.md)**-egenskapen:  
> ```Clear(OrderList);SaveData(OrderList, "orderfile")```  
> Hvis du vil fjerne ett element om gangen, kan du vise **OrderList**-samlingen i galleriet, og deretter angi følgende uttrykk for **[OnSelect](controls/properties-core.md)**-egenskapen for en etikett i galleriet:  
> ```Remove(OrderList, ThisItem);SaveData(OrderList, "orderfile")```
> 
> 

## <a name="tips-and-tricks"></a>Tips og triks
* Du kan når som helst velge Forhåndsvisning-knappen (![][7]) for å vise diagrammer og for å se hvordan de ser ut med data.
* Når du utformer appen din, kan du endre størrelse på kontrollene og flytte dem rundt ved hjelp av klikk-og-dra.

## <a name="what-you-learned"></a>Det du lærte
I dette emnet har du gjort følgende:

* Du brukte Collect()-funksjonen til å opprette en samling i appen din.
* Du har lagt til en knappekontroll, og når den blir valgt, legger den til nye elementer i samlingen.
* Du brukte en listeboks til å legge til elementer i samlingen.
* Du la til en glidebryter for å oppdatere elementer i samlingen.

[1]: ./media/create-update-collection/insertmenu-inputtext.png
[2]: ./media/create-update-collection/renametext.png
[3]: ./media/create-update-collection/buttononselect.png
[4]: ./media/create-update-collection/listboxpreview.png
[5]: ./media/create-update-collection/buttontext.png
[6]: ./media/create-update-collection/buttonundertext.png
[7]: ./media/create-update-collection/preview.png
[8]: ./media/create-update-collection/existingcollections.png
[9]: ./media/create-update-collection/renametext-city.png
[10]: ./media/create-update-collection/citystate.png
[11]: ./media/create-update-collection/buttononselectcitystate.png
[12]: ./media/create-update-collection/buttononcitystate.png
[13]: ./media/create-update-collection/existingcollectionscitystate.png
[14]: ./media/create-update-collection/import.png
[15]: ./media/create-update-collection/pricelistcollection.png
[16]: ./media/create-update-collection/portrait.png
[17]: ./media/create-update-collection/resizedgallery.png
[18]: ./media/create-update-collection/galleryitems.png
[19]: ./media/create-update-collection/gallerylabels.png
[20]: ./media/create-update-collection/slider.png
[21]: ./media/create-update-collection/existingcollectionsorderlist.png
[22]: ./media/create-update-collection/listbox.png
