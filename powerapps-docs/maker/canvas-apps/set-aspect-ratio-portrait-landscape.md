---
title: Endring av skjermstørrelse og -retning for en lerretsapp | Microsoft Docs
description: Trinnvise instruksjoner for å endre innstillinger som skjermstørrelsen og -retningen for en lerretsapp i PowerApps
author: evchaki
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 11/07/2018
ms.author: evchaki
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 1d3bd48f658e31f795ca3489fa1973c48da94a22
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/07/2019
ms.locfileid: "71995624"
---
# <a name="change-screen-size-and-orientation-of-a-canvas-app-in-powerapps"></a>Endring av skjermstørrelse og -retning for en lerretsapp i PowerApps
Tilpass en lerretsapp ved å endre skjermstørrelsen og -retningen.

## <a name="prerequisites"></a>Forutsetninger

Opprett en app, eller åpne en for redigering, og velg deretter **program innstillinger** på **fil** -menyen.

## <a name="change-screen-size-and-orientation"></a>Endring av skjermstørrelse og -retning
1. Under **App-innstillinger**velger du **skjerm størrelse + retning**.

    ![Alternativ for å endre skjermstørrelsen og -retningen for en app](./media/set-aspect-ratio-portrait-landscape/size-orientation.png)

1. Velg **stående** eller **liggende**i **retning** -listen.

1. (Bare nett brett programmer) Under **størrelses forhold**utfører du ett av disse trinnene:

    - Velg forholdet som Sams varer med målenheten for denne appen.
    - Velg **egen definert** for å angi din egen størrelse, og angi deretter en bredde mellom 50-3840 og en høyde mellom 50-2160.

    ![Endring av størrelsesforholdet for en nettbrett-app](./media/set-aspect-ratio-portrait-landscape/aspect-tablet.png)
    
1. Angi enten på **eller** **på** under **Skaler til Tilpass**.

    Denne innstillingen er aktivert som standard, slik at app-skjermer endrer størrelse for å få plass til den tilgjengelige plassen på enheten. Når denne innstillingen er aktivert, Sams varer appens **Width** -egenskap med **DesignWidth**, og **høyden** på appen Sams varer med **DesignHeight**.

    Hvis du deaktiverer denne innstillingen, justeres appen til størrelses forholdet for enheten den kjører på, og den tar opp all tilgjengelig plass. Appen skaleres ikke, og derfor kan skjermer vise mer informasjon.

    Når denne innstillingen er deaktivert, deaktiveres **Lås størrelses forhold** automatisk og deaktivert. I tillegg er **Width** -egenskapen for alle skjermer satt til `Max(App.Width, App.DesignWidth)`, og **Height** -egenskapen er satt til `Max(App.Height, App.DesignHeight)` slik at de sporer dimensjonene i vinduet der appen kjører. Med denne endringen kan du opprette apper som svarer på ulike enheter og vindus dimensjoner. Mer informasjon: [Opprett svar oppsett](create-responsive-layout.md)

1. Angi enten **På** eller **Av** under **Lås størrelsesforhold**.

    Hvis denne innstillingen er aktivert, beholder appen skjerm retningen og størrelses forholdet som du angav i trinn 2 og 3, uansett hvilken enhet du har angitt. En telefon app som kjører i en nett leser, beholder for eksempel forholdet for en telefon, som viser en mørk stolpe på hver side i stedet for å fylle ut vinduet.

    Hvis denne innstillingen er deaktivert, justeres appen til størrelses forholdet for enheten den kjører på (og det er nødvendig å forvrenge bruker grensesnittet).

1. Under **Lås retning** angir du enten **På** eller **Av**.

    Hvis du låser appens retning, beholder appen retningen du angir. Hvis appen kjører på en enhet som skjerm bildet er i en annen retning, viser appen seg feil og kan vise uønskede resultater. Hvis du låser opp appens retning, justeres den til skjerm retningen for enheten den kjører på.

    Du kan også endre appens retning ved å aktivere aktivering av **app-innbygging av bruker opplevelse** i **Avanserte innstillinger**. Denne funksjonen øverst til venstre justerer appen når den er innebygd, og endrer bakgrunns fargen på verts lerretet til hvit.

1. Velg **Bruk** for å lagre endringene.

## <a name="next-step"></a>Neste trinn
Velg **Lagre** på **Fil**-menyen for å publisere appen på nytt med de nye innstillingene.