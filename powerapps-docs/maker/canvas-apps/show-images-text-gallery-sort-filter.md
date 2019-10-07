---
title: Å vise, sortere og filtrere data i et galleri | Microsoft Docs
description: Bruk et galleri for å vise bilder og tekst. Sorter og filtrer bildene i PowerApps.
author: adrianorth
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 06/02/2015
ms.author: aorth
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 3a25654f0304fce9978ae1f7b1410cfb557ef32c
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/07/2019
ms.locfileid: "71995591"
---
# <a name="show-sort-and-filter-data-in-a-powerapps-gallery"></a>Å vise, sortere og filtrere data i et PowerApps-galleri
Opprett et galleri for å vise bilder og tekst om flere produkter, og sorter og filtrer informasjonen.

I PowerApps kan du bruke et galleri for å vise flere relaterte elementer, akkurat som du ser i en katalog. Gallerier er flott for å vise informasjon om produkter, for eksempel navn og priser. Vi oppretter et galleri, og sorterer og filtrerer informasjonen ved hjelp av Excel-lignende funksjoner i dette emnet. En kantlinje plasseres også rundt elementet når et element er valgt.

> [!NOTE]
> Dette emnet bruker en nettbrett-app. Du kan bruke en telefon-app, men du må endre størrelsen på noen av kontrollene.
> 
> 

### <a name="prerequisites"></a>Forutsetninger
* [Registrer deg](../signup-for-powerapps.md) for PowerApps, og deretter [logger du deg på](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) ved å oppgi samme legitimasjon som du brukte til å registrere deg.
* Opprett en nettbrett-app fra en [mal](get-started-test-drive.md), fra [data](get-started-create-from-data.md), eller fra [bunnen av](get-started-create-from-blank.md).
* Finn ut hvordan du kan [konfigurere en kontroll](add-configure-controls.md).
* Disse trinnene bruker [CreateFirstApp](http://pwrappssamples.blob.core.windows.net/samples/CreateFirstApp.zip) som eksempel for inndata, som inkluderer JPG-bilder. ZIP-filen inneholder en XML-fil som kan konverteres til Excel. PowerApps leser ellers automatisk ZIP-filene og importerer dem. Du kan laste ned og bruke disse eksempeldataene, eller importere dine egne.

## <a name="show-data-in-a-gallery"></a>Å vise data i et galleri
1. Opprett en samling med navnet **Beholdning** ved å bruke eksempeldataene. Trinnene inkluderer:  
   
   1. Velg **Kontroller** på **Sett inn**-fanen, og velg deretter **Importer**:
      
      ![][1]  
   2. Angi **[OnSelect](controls/properties-core.md)** -egenskapen for importkontrollen til følgende formel:  
      **Samle inn (beholdning, Import1. data)**
      
      ![][12]  
   3. Velg **Importdata**-knappen for å åpne Windows Utforsker. Velg *CreateFirstApp.zip*, og velg **Åpne**.
   4. Velg **samlinger** på **Fil**-menyen. Samlingen for beholdning er oppført med dataene du har importert:
      
      ![][3]  
      
      Du har nettopp opprettet samlingen for beholdningen, som inneholder informasjon om fem produkter, inkludert et design-bilde, navnet på produktet og antall enheter på lager.
      
      > [!NOTE]
      > Importkontrollen brukes til å importere Excel-lignende data og opprette samlingen. Importkontrollen importerer data når du oppretter appen, og forhåndsviser appen. Importkontrollen importer for øyeblikket ikke data når du publiserer appen.
      > 
      > 
2. Velg tilbake-pilen for å gå tilbake til utformeren.
3. Klikk eller trykk på **Galleri** på **Sett inn**-fanen, og klikk eller trykk deretter på **Vannrett**-galleriet.
   
    ![][4]
4. Klikk eller trykk på alternativet i den høyre ruten, der tittelen og undertittelen overlapper grafikken:
   
    ![][15]
5. Angi **[Element](controls/properties-core.md)** -egenskapen for galleriet til **Beholdning**:
   
    ![][5]
6. Gi nytt navn til galleriet for **ProductGallery** og flytt galleriet, slik at det ikke blokkerer andre kontroller. Endre størrelsen på galleriet, slik at den viser tre produkter:
   
    ![][6]
7. velg den nederste etiketten i det første elementet i galleriet:  
   
    ![][7]  
   
   > [!NOTE]
   > Du endrer automatisk alle andre elementer i galleriet når du endrer det første elementet i et hvilket som helst galleri.  
   > 
   > 
8. Angi **[Tekst](controls/properties-core.md)** -egenskapen for etiketten til følgende uttrykk:  
    **ThisItem. EnheterPåLager** <br/>
   
    Etiketten viser enhetene på lager for hvert produkt når du gjør dette:

![][8]  

> [!NOTE]
> **[Tekst](controls/properties-core.md)** -egenskapen til den øverste etiketten er satt til ```ThisItem.ProductName``` som standard. Du kan endre den til hvilket som helst element i samlingen. Hvis samlingen for eksempel har *ProductDescription*- eller *Pris*-felt, kan du angi etiketten til ```ThisItem.ProductDescription``` eller ```ThisItem.Price```.
> 
> 

Ved hjelp av disse trinnene importerte du data som inneholder JPG-bilder til en samling. Du la deretter til et galleri som viser dataene og konfigurerte en etikett for å vise enhetene på lager for hvert produkt.

## <a name="highlight-the-gallery-item-you-select"></a>Å utheve gallerielementet du har valgt
1. Velg et hvilket som helst element i galleriet *unntatt* det første. Rediger-ikonet vises (øvre til venstre). Velg rediger-ikonet:  
   ![][9]  
2. Velg **Figurer** på **Sett inn**-fanen, og velg deretter rektanglet. Et fylt, blått rektangel vises i hvert gallerielement.
3. Velg **Fyll**, og velg deretter **Uten fyll** på **Hjem**-fanen.
4. Velg **Kantlinje**, velg **Kantlinjestil**, og velg deretter heltrukket linje.
5. Velg **Kantlinje** på nytt, og angi tykkelsen til 3. Endre størrelsen på rektanglet slik at den omslutter gallerielementet. Elementene i galleriet har nå en blå kantlinje og bør se ut omtrent som følgende:  
   ![][10]  
6. Velg **Synlig** på **Figur**-fanen, og skriv deretter inn følgende formel i formellinjen:  
   
    **If (ThisItem. IsSelected, True)**
   
    Et blått rektangel omslutter det gjeldende utvalget i et galleri. Velg noen gallerielementer for å bekrefte at rektanglet vises rundt hvert element du velger. Husk at du kan også åpne **Forhåndsvisning**![][2] for å se og teste det du oppretter.

> [!TIP]
> Velg rektanglet, velg **Omorganiser** på **Hjem**-fanen, og velg deretter **Plasser lengst bak**. Med denne funksjonen kan du velge et gallerielement uten at kantlinjen blokkerer noe.
> 
> 

Du la til en kantlinje rundt det merkede området i galleriet, ved hjelp av disse trinnene.

## <a name="sort-and-filter-items-in-the-gallery"></a>Å sortere og filtrere elementer i galleriet
I denne fremgangsmåten skal vi sortere elementene i galleriet i stigende og synkende rekkefølge. Vi skal også legge til en glidebryter for å «filtrere» gallerielementer etter enhetene på lager som du velger.

#### <a name="sort-in-ascending-or-descending-order"></a>Sortering i stigende eller synkende rekkefølge
1. Velg et hvilket som helst element i galleriet *unntatt* det første.
2. **[Element](controls/properties-core.md)** -egenskapen er satt til Beholdning (navnet på samlingen). Endre det til følgende:  
   
    **Sort(Inventory, ProductName)**
   
    Når du gjør dette er elementene i galleriet allerede sortert etter navnet på produktet i stigende rekkefølge:  ![][11]  
   
    Prøv synkende rekkefølge. Angi **[Element](controls/properties-core.md)** -egenskapen for galleriet til følgende formel:  
   
    Sort(Inventory, ProductName, Descending)  

#### <a name="add-a-slider-control-and-filter-items-in-the-gallery"></a>Å legge til en glidebryter-kontroll og filtrere elementer i galleriet
1. Legg til en glidebryter (**Sett inn**-fanen > **Kontroller**), endre navnet til **StockFilter**, og flytt den under galleriet.
2. Konfigurer glidebryteren slik at brukere ikke kan angi en verdi utenfor området for enheter på lager:  
   
   1. Velg **Min** på **Innhold**-fanen, og skriv deretter inn følgende uttrykk:  
      ```Min(Inventory, UnitsInStock)```  
   2. Velg **Maks** på **Innhold**-fanen, og skriv deretter inn følgende uttrykk:  
      ```Max(Inventory, UnitsInStock)```
3. Velg et hvilket som helst element i galleriet *unntatt* det første. Angi **[Element](controls/properties-core.md)** -egenskapen for galleriet til følgende uttrykk:  
   ```Filter(Inventory, UnitsInStock<=StockFilter.Value)```
4. Juster glidebryteren I **Forhåndsvisning** til en verdi som er mellom det høyeste og laveste antallet i galleriet. Galleriet viser bare de produktene som er mindre enn verdien du har valgt i galleriet når du justerer glidebryteren:  
   ![][13]  

La oss nå legge til filteret:

1. Gå tilbake til utformeren.
2. Velg **Tekst** på **Sett inn**-fanen, velg **Tekstinndata**, og endre navnet på den nye kontrollen til **NameFilter**. Flytt tekst-kontrollen nedenfor glidebryteren.
3. Angi **[Element](controls/properties-core.md)** -egenskapen for galleriet til følgende uttrykk:  
   ```Filter(Inventory, UnitsInStock<=StockFilter.Value && NameFilter.Text in ProductName)```
4. Angi glidebryteren til *30* i **Forhåndsvisning**, og skriv bokstaven *g* i kontrollen for tekstinndata. Galleriet viser det eneste produktet med mindre enn 30 enheter på lager *og* som har et navn med bokstaven «g»:  
   ![][14]  

## <a name="tips-and-tricks"></a>Tips og triks
* Du kan når som helst velge knappen for forhåndsvisning (![][2]) for å se hva du har opprettet, og for å teste det.
* Når du utformer appen, kan du endre størrelse på kontrollene og flytte dem rundt ved hjelp av klikk og dra.
* Trykk på **ESC** eller velg **X**-en for å lukke vinduet for forhåndsvisning.
* Velg det første elementet i galleriet når du bruker et galleri for å endre alle elementene i galleriet. Velg for eksempel det første elementet for å legge til en kantlinje til alle elementer i galleriet.
* Velg et element i galleriet, *unntatt* det første, hvis du vil oppdatere egenskapene for galleriet. Velg for eksempel det andre elementet til å oppdatere *Elementer*, *ShowScrollbar*, og andre egenskaper som gjelder for galleriet (ikke elementer i galleriet).  

## <a name="what-you-learned"></a>Hva du har lært
I dette emnet har du:

* Opprettet en samling, importert dataene som inkluderer JPG-bilder til samlingen, og vist dataene i et galleri.
* Under hvert bilde i galleriet, har du konfigurert en etikett som viser en liste over enheter på lager for dette elementet.
* Lagt til en kantlinje rundt elementet du velger.
* Sortert elementene etter produktnavn i stigende og synkende rekkefølge.
* Lagt til en glidebryter og en inndatatekst-kontroll for å filtrere produktene etter enheter på lager og produktnavn.

[1]: ./media/show-images-text-gallery-sort-filter/import.png
[2]: ./media/show-images-text-gallery-sort-filter/preview.png
[3]: ./media/show-images-text-gallery-sort-filter/inventorycollection.png
[4]: ./media/show-images-text-gallery-sort-filter/insert-vertical.png
[5]: ./media/show-images-text-gallery-sort-filter/itemsinventory.png
[6]: ./media/show-images-text-gallery-sort-filter/threeimages.png
[7]: ./media/show-images-text-gallery-sort-filter/firstitem.png
[8]: ./media/show-images-text-gallery-sort-filter/bottomlabel.png
[9]: ./media/show-images-text-gallery-sort-filter/editgallery.png
[10]: ./media/show-images-text-gallery-sort-filter/border.png
[11]: ./media/show-images-text-gallery-sort-filter/sort.png
[12]: ./media/show-images-text-gallery-sort-filter/onselect.png
[13]: ./media/show-images-text-gallery-sort-filter/slider.png
[14]: ./media/show-images-text-gallery-sort-filter/inputandslider.png
[15]: ./media/show-images-text-gallery-sort-filter/select-overlay.png
