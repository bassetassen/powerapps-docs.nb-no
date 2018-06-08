---
title: Å legge til en liste, en rullegardinliste og alternativknapper | Microsoft Docs
description: Å opprette eller konfigurer alternativer for flervalg i PowerApps
documentationcenter: ''
author: lonu
manager: kfile
editor: ''
ms.service: powerapps
ms.devlang: na
ms.topic: conceptual
ms.component: canvas
ms.date: 10/23/2016
ms.author: lonu
ms.openlocfilehash: 1fbaf4f9d740084a1ed0d630b94d1cd41713ba03
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/04/2018
ms.locfileid: "31825560"
---
# <a name="add-a-list-box-a-drop-down-list-or-radio-buttons"></a>Å legge til en liste, en rullegardinliste eller alternativknapper
PowerApps inkluderer alternativer for enkeltvalg og flervalg, inkludert en liste, en rullegardinliste og alternativknapper. I dette emnet legger vi til disse kontrollene og bruker en **Tabell**-formel for å lage listene. Når et element velges i listen, oppdateres andre kontroller.

[!INCLUDE [app-customization-requirements](../../includes/app-customization-requirements.md)]

## <a name="add-a-list-box"></a>Å legge til en listeboks
1. Velg **Kontroller** på **Sett inn**-fanen, og velg deretter **Listeboks**:  

    ![][2]  

2. Endre navnet på **Liste**-kontrollen til **MyListBox**:  

    ![][3]

3. Angi kontrollens **[Element](controls/properties-core.md)**-egenskaper til følgende uttrykk:  
   ```["circle","triangle","rectangle"]```  <br/>

    Utformingen ser omtrent slik ut:

    ![][4]

4. Velg **Ikoner** på **Sett inn**-fanen, velg sirkelen og flytt den under **Listeboks**-kontrollen:

    ![][5]  

5. Legg til en trekant og et rektangel, og deretter arranger du figurene i en rad under **Listeboks**-kontrollen:

    ![][6]  

6. Angi **[Synlig](controls/properties-core.md)**-egenskapen hos de følgende figurene til følgende funksjoner:  

   | Figur | Angi Synlig-funksjonen til |
   | --- | --- |
   | sirkel |```If("circle" in MyListBox.SelectedItems.Value, true)``` |
   | trekant |```If("triangle" in MyListBox.SelectedItems.Value, true)``` |
   | rektangel |```If("rectangle" in MyListBox.SelectedItems.Value, true)``` |

7. Forhåndsvis det du har opprettet ![][1]. Velg de forskjellige figurene i **Liste**-kontrollen. Kun figuren eller figurene du har valgt, vil vises. Trykk på ESC eller velg **X** for å gå tilbake til skjermen din.

I disse trinnene brukte du et uttrykk for å opprette en liste over elementer i en **Listeboks**-kontroll. Forskjellige figurer vil vises avhengig av hva du velger i **Listeboks**-kontrollen. Du kan bruke dette for andre elementer i virksomheten din. Du kan for eksempel bruke en **Listeboks**-kontroll til å vise produktbilder, produktbeskrivelser og så videre.

## <a name="add-radio-buttons"></a>Å legge til alternativknapper
1. Velg **Ny skjerm** på **Hjem**-fanen.

2. Velg **Kontroller** på **Sett inn**-fanen, og velg deretter **Alternativ**.

    ![][10]  

3. Endre navnet på **Alternativ**-kontrollen til **Valg**, og deretter angir du kontrollens **[Element](controls/properties-core.md)**-egenskap til denne formelen:  
   ```["red","green","blue"]```  <br/>

    ![][12]  

    Du kan endre størrelsen på kontrollen for å vise alle alternativene om nødvending.

4. Velg **Ikoner** på **Sett inn**-fanen, og deretter velger du sirkelen.

5. Angi sirkelens **[Fyll](controls/properties-color-border.md)**-egenskap til følgende funksjon:  
   ```If(Choices.Selected.Value = "red", RGBA(192, 0, 0, 1), Choices.Selected.Value = "green", RGBA(0, 176, 80, 1), Choices.Selected.Value = "blue", RGBA(0, 32, 96, 1))```  

    I denne formelen endrer sirkelen farge avhengig av hvilken alternativknapp du velger.

6. Flytt sirkelen under **Alternativ**-kontrollen som i dette eksempelet:

    ![][14]  

7. Forhåndsvis det du har opprettet: ![][1]. Velg en annen alternativknapp for å endre fargen på sirkelen. Trykk på ESC eller velg **X** for å gå tilbake til skjermen din.

## <a name="add-a-drop-down-list"></a>Å legge til en rullegardinliste
1. Legg til en skjerm, og deretter legger du til en **Rullegardin**-kontroll.

    ![][15]  

2. Endre navnet på kontrollen til **DDChoices** og angi kontrollens **[Element](controls/properties-core.md)**-egenskap til denne formelen:<br>
   **["red","green","blue"]**

3. Legg til en sirkel, flytt den under **Rullegardin**-kontrollen, og angi deretter sirkelens **[Fyll](controls/properties-color-border.md)**-egenskap til denne formelen:  
   ```If(DDChoices.Selected.Value = "red", RGBA(192, 0, 0, 1), DDChoices.Selected.Value = "green", RGBA(0, 176, 80, 1), DDChoices.Selected.Value = "blue", RGBA(0, 32, 96, 1))```

4. Forhåndsvis det du har opprettet: ![][1]. Velg de forskjellige alternativene for å endre farge på sirkelen.

[1]: ./media/add-list-box-drop-down-list-radio-button/preview.png
[2]: ./media/add-list-box-drop-down-list-radio-button/listbox.png
[3]: ./media/add-list-box-drop-down-list-radio-button/renamelistbox.png
[4]: ./media/add-list-box-drop-down-list-radio-button/itemslistbox.png
[5]: ./media/add-list-box-drop-down-list-radio-button/circle.png
[6]: ./media/add-list-box-drop-down-list-radio-button/allshapes.png
[10]: ./media/add-list-box-drop-down-list-radio-button/radiobutton.png
[12]: ./media/add-list-box-drop-down-list-radio-button/itemsradio.png
[14]: ./media/add-list-box-drop-down-list-radio-button/radiocircle.png
[15]: ./media/add-list-box-drop-down-list-radio-button/dropdown.png
