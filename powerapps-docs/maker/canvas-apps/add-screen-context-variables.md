---
title: Legg til en skjerm i en lerretsapp og naviger mellom skjermer | Microsoft Docs
description: Legg til en skjerm i en lerretsapp og bruk neste- og tilbake-pilene til å veksle mellom skjermer i PowerApps
author: AFTOwen
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 07/10/2017
ms.author: anneta
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: f7e03402690cb448a10c64882fdb6d79713cffcb
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/24/2018
ms.locfileid: "42858911"
---
# <a name="add-a-screen-to-a-canvas-app-and-navigate-between-screens"></a>Legg til en skjerm i en lerretsapp og naviger mellom skjermer

Opprett en lerretsapp med flere skjermer, og legg til måter brukerne kan navigere mellom dem på.

## <a name="prerequisites"></a>Forutsetninger

* Finn ut hvordan du kan [konfigurere en kontroll](add-configure-controls.md).
* Å opprette eller åpne en app.

## <a name="add-and-rename-a-screen"></a>Å legge til og gi nytt navn til en skjerm

1. Klikk eller trykk på **Hjem** på **Ny skjerm**-fanen.

    ![Å legge til Skjerm-alternativet på Hjem-fanen](./media/add-screen-context-variables/add-screen.png)

2. Klikk eller trykk på navnet på skjermen (rett over **Egenskaper**-fanen) i høyre rute, og skriv deretter inn det nye navnet **Kilde**.

    ![Å gi nytt navn til standardskjermen](./media/add-screen-context-variables/name-source-screen.png)

3. Legg til en annen skjerm, og gi den navnet **Mål**.

    ![To skjermer i navigasjonsfeltet til venstre](./media/add-screen-context-variables/two-screens-in-nav.png)

## <a name="add-navigation"></a>Å legge til navigasjon
1. Velg **Kilde**-skjermen, og åpne **Sett inn**-fanen. Klikk eller trykk deretter på **Ikoner**, og klikk eller trykk på **Neste pil**.  

    ![Alternativet Figurer på Sett inn-fanen](./media/add-screen-context-variables/add-next-arrow.png)

2. (valgfritt) Flytt pilen slik at den vises nede til høyre på skjermen.

3. Med pilen fremdeles merket klikker eller trykker du på **Handling**-fanen, og deretter klikker eller trykker du på **Navigate**.

    **[OnSelect](controls/properties-core.md)** -egenskapen for pilen settes automatisk til en **Naviger**-funksjon.  

    ![OnSelect-egenskapen satt til Navigate-funksjon](./media/add-screen-context-variables/onselect-default.png)

    Når en bruker klikker på eller trykker på pilen, tones **Mål**-skjermen inn.

4. På **Target**-skjermen legger du til en **Tilbake-pil** og angir **[OnSelect](controls/properties-core.md)**-egenskapen til denne formelen:
   <br>**Navigate(Source, ScreenTransition.Fade)**

5. Åpne forhåndsvisningsmodus (![](./media/add-screen-context-variables/preview.png) eller trykk på F5), og bytt deretter mellom skjermene ved å klikke eller trykke på pilene som du har lagt til.

6. Trykk på **ESC** for å gå tilbake til standardarbeidsområdet.
