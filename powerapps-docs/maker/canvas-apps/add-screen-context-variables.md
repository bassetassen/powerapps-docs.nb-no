---
title: Legge til en skjerm og navigere mellom skjermer | Microsoft Docs
description: Legge til en skjerm i en app og bruke neste- og tilbake-pilene til å gå mellom skjermbildene i PowerApps
services: ''
suite: powerapps
documentationcenter: na
author: skjerland
manager: anneta
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 07/10/2017
ms.author: sharik
ms.openlocfilehash: 64c38e561be90cbebabe17f73377e4d754d99c54
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/22/2018
ms.locfileid: "30997057"
---
# <a name="add-a-screen-and-navigate-between-screens"></a>Legge til en skjerm og navigere mellom skjermer
Opprett en app med flere skjermer, og legg til måter for brukere å navigere mellom dem på.

## <a name="prerequisites"></a>Forutsetninger
* Finn ut hvordan du kan [konfigurere en kontroll](add-configure-controls.md).
* Opprette eller åpne en app.

## <a name="add-and-rename-a-screen"></a>Legge til en skjerm, og gi den nytt navn
1. Klikk eller trykk på **Ny skjerm** på **Hjem-fanen**.

    ![Legge til Skjerm-alternativet i Hjem-fanen](./media/add-screen-context-variables/add-screen.png)

2. Klikk eller trykk på navnet på skjermen (rett over **Egenskaper**-fanen) i høyre fane, og skriv deretter inn det nye navnet **Kilde**.

    ![Gi nytt navn til standardskjermen](./media/add-screen-context-variables/name-source-screen.png)

3. Legge til en annen skjerm, og gi den navnet **Target**.

    ![To skjermer i navigasjonsfeltet til venstre](./media/add-screen-context-variables/two-screens-in-nav.png)

## <a name="add-navigation"></a>Legg til navigasjon
1. Med **Kilde**-skjermen valgt, åpner du **Sett inn**-fanen, klikker eller trykker på **Ikoner** og klikker eller trykker på **Neste pil**.  

    ![Alternativet Figurer i Sett inn-fanen](./media/add-screen-context-variables/add-next-arrow.png)

2. (valgfritt) Flytte pilen slik at den vises i nedre høyre hjørne av skjermen.

3. Med pilen fremdeles merket klikker eller trykker du på **Handling**-fanen, og deretter klikker eller trykker du på **Naviger**.

    **[OnSelect](controls/properties-core.md)** -egenskapen for pilen settes automatisk til en **Naviger**-funksjon.  

    ![OnSelect-egenskapen satt til Naviger-funksjon](./media/add-screen-context-variables/onselect-default.png)

    Når en bruker klikker på eller berører pilen, tones **Target**-skjermen inn.

4. På **Target**-skjermen legger du til en **Tilbake-pil** og angir **[OnSelect](controls/properties-core.md)**-egenskapen til denne formelen:
   <br>**Navigate(Source, ScreenTransition.Fade)**

5. Åpne forhåndsvisningsmodus (![](./media/add-screen-context-variables/preview.png) eller trykk på F5), og bytt deretter mellom skjermene ved å klikke eller trykke på pilene som du har lagt til.

6. Trykk på **Esc** for å gå tilbake til standardarbeidsområdet.
