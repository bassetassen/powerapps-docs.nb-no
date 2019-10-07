---
title: Legg til en liste, en rullegardinliste eller alternativknapper i en lerretsapp| Microsoft Docs
description: Opprett eller konfigurer alternativer for flervalg i en lerretsapp i PowerApps
author: fikaradz
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 10/24/2018
ms.author: fikaradz
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 211a5be4a97780a440bf151157576a5ab56933a5
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/07/2019
ms.locfileid: "71987510"
---
# <a name="add-a-list-box-a-drop-down-list-or-radio-buttons-to-a-canvas-app"></a>Legg til en liste, en rullegardinliste eller alternativknapper i en lerretsapp

Vis en enkelt kolonne med data (for eksempel fra en flerkolonnetabell) i en lerretsapp, slik at brukere kan velge ett eller flere elementer i en liste.

- Legg til en listeboks for å tillate brukere å velge mer enn ett alternativ.
- Legg til en rullegardinliste for å ta opp mindre plass på skjermen.
- Legg til et sett med alternativknapper for å oppnå en bestemt effekt på utformingen.

Dette emnet fokuserer på lister og alternativknapper, men de samme prinsippene gjelder for rullegardinlistene.

[!INCLUDE [app-customization-requirements](../../includes/app-customization-requirements.md)]

## <a name="create-a-simple-list"></a>Opprett en enkel liste

1. Legg til en **Liste**-kontroll, gi den navnet **MyListBox**, og angi **Elementer**-egenskapen som denne formelen:

    ```["circle","triangle","rectangle"]```  <br/>

    Utformingen ser omtrent slik ut:

    ![][4]

4. Velg **Ikoner** på **Sett inn**-fanen, velg sirkelen og flytt den under **MyListBox**:

    ![][5]  

5. Legg til en trekant og et rektangel, og deretter arranger du figurene i en rad under **MyListBox**:

    ![][6]  

6. Angi **[Synlig](controls/properties-core.md)** -egenskapen hos de følgende figurene til følgende funksjoner:  

   | Figur | Angi Synlig-funksjonen til |
   | --- | --- |
   | sirkel |```If("circle" in MyListBox.SelectedItems.Value, true)``` |
   | trekant |```If("triangle" in MyListBox.SelectedItems.Value, true)``` |
   | rektangel |```If("rectangle" in MyListBox.SelectedItems.Value, true)``` |

7. Velg én eller flere figurer i **MyListBox** mens du holder nede ALT-tasten.

    Kun figuren eller figurene du har valgt, vil vises.

I disse trinnene brukte du et uttrykk for å opprette en liste over elementer. Du kan bruke dette for andre elementer i virksomheten din. Du kan for eksempel bruke en **rullegardin**-kontroll til å vise produktbilder, produktbeskrivelser og så videre.

## <a name="add-radio-buttons"></a>Å legge til alternativknapper
1. Velg **Ny skjerm**, og velg deretter **Tom**, på **Hjem**-fanen.

2. Velg **Kontroller** på **Sett inn**-fanen, og velg deretter **Alternativ**.

    ![][10]  

3. Endre navnet på **Alternativ**-kontrollen til **Valg**, og deretter angir du kontrollens **[Element](controls/properties-core.md)** -egenskap til denne formelen:  
   ```["red","green","blue"]```  <br/>

    ![][12]  

    Du kan endre størrelsen på kontrollen for å vise alle alternativene om nødvending.

4. Velg **Ikoner** på **Sett inn**-fanen, og deretter velger du sirkelen.

5. Angi sirkelens **[Fyll](controls/properties-color-border.md)** -egenskap til følgende funksjon:  
   ```If(Choices.Selected.Value = "red", Red, Choices.Selected.Value = "green", Green, Choices.Selected.Value = "blue", Blue)```  

    I denne formelen endrer sirkelen farge avhengig av hvilken alternativknapp du velger.

6. Flytt sirkelen under **Alternativ**-kontrollen som i dette eksempelet:

    ![][14]  

7. Velg en annen alternativknapp mens du holder nede ALT-tasten for å endre fargen på sirkelen.

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
