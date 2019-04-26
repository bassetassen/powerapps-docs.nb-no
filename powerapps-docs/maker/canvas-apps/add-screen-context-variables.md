---
title: Legg til en skjerm i en lerretsapp og naviger mellom skjermer | Microsoft Docs
description: Legg til en skjerm i en lerretsapp og bruk neste- og tilbake-pilene til å veksle mellom skjermer i PowerApps
author: emcoope-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 02/03/2019
ms.author: emcoope
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: b6f83d21b2964dac7c4925d45efdf11a3a1e6b02
ms.sourcegitcommit: 4ed29d83e90a2ecbb2f5e9ec5578e47a293a55ab
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/23/2019
ms.locfileid: "63321375"
---
# <a name="add-a-screen-to-a-canvas-app-and-navigate-between-screens"></a>Legg til en skjerm i en lerretsapp og naviger mellom skjermer

Opprett en lerretsapp med flere skjermer, og legg til måter brukerne kan navigere mellom dem på.

## <a name="add-and-rename-a-screen"></a>Å legge til og gi nytt navn til en skjerm

1. På den **Hjem** fanen og velge **ny skjerm**, og velg deretter typen skjermen som du vil legge til.

    ![Å legge til Skjerm-alternativet på Hjem-fanen](./media/add-screen-context-variables/add-screen.png)

2. I den høyre ruten, velger du navnet på skjermen (rett over den **Egenskaper** fanen), og skriv deretter inn **kilde**.

    ![Å gi nytt navn til standardskjermen](./media/add-screen-context-variables/name-source-screen.png)

3. Legg til en annen skjerm, og gi den navnet **Mål**.

    ![To skjermer i navigasjonsfeltet til venstre](./media/add-screen-context-variables/two-screens-in-nav.png)

## <a name="reorder-screens"></a>Endre rekkefølgen på skjermer

Hold pekeren over en skjerm som du ønsker å flytte opp eller ned, velg ellipseknappen som vises i navigasjonsfeltet til venstre, og velg deretter **Flytt opp** eller **Flytt ned**.

![Endre rekkefølgen på skjermen](./media/add-screen-context-variables/reorder-screen.png)

> [!NOTE]
> Når du åpner appen, vises vanligvis skjermen på toppen av den hierarkiske listen over kontroller først. Men du kan angi en annen skjerm ved å angi den **[OnStart](controls/control-screen.md)** egenskapen til en formel som inneholder den **[Navigate](functions/function-navigate.md)** funksjonen.

## <a name="add-navigation"></a>Å legge til navigasjon

1. Med den **kilde** skjermen, og åpne den **Sett inn** fanen og velge **ikoner**, og velg deretter **neste-pilen**.  

    ![Alternativet Figurer på Sett inn-fanen](./media/add-screen-context-variables/add-next-arrow.png)

2. (valgfritt) Flytt pilen slik at den vises nede til høyre på skjermen.

3. Med pilen fortsatt er valgt, velger du **handlingen** fanen, og velg deretter **Navigate**.

    **[OnSelect](controls/properties-core.md)** -egenskapen for pilen settes automatisk til en **Naviger**-funksjon.

    ![OnSelect-egenskapen satt til Navigate-funksjon](./media/add-screen-context-variables/onselect-default.png)

    Når en bruker velger du pilen, den **Target** skjermen tones.

4. På **Target**-skjermen legger du til en **Tilbake-pil** og angir **[OnSelect](controls/properties-core.md)**-egenskapen til denne formelen:

    `Navigate(Source, ScreenTransition.Fade)`

5. Mens du holder nede Alt-tasten, kan du veksle mellom skjermer ved å velge pilen på hver skjerm.

## <a name="more-information"></a>Vil ha mer informasjon

[Skjermkontroll referanse](controls/control-screen.md)