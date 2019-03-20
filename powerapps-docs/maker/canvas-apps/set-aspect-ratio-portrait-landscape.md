---
title: Endring av skjermstørrelse og -retning for en lerretsapp | Microsoft Docs
description: Trinnvise instruksjoner for å endre innstillinger som skjermstørrelsen og -retningen for en lerretsapp i PowerApps
author: evchaki
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 11/07/2018
ms.author: evchaki
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: c4d9f648a4519ef30887d8d0739d7dc3d940555b
ms.sourcegitcommit: 0dbbf53aea319e53edadc1d3a9efa5728856ebd8
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/19/2019
ms.locfileid: "58172683"
---
# <a name="change-screen-size-and-orientation-of-a-canvas-app-in-powerapps"></a>Endring av skjermstørrelse og -retning for en lerretsapp i PowerApps
Tilpass en lerretsapp ved å endre skjermstørrelsen og -retningen.

## <a name="prerequisites"></a>Forutsetninger

Opprette en app eller åpne en for redigering, og velg deretter **appinnstillinger** på den **filen** menyen.

## <a name="change-screen-size-and-orientation"></a>Endring av skjermstørrelse og -retning
1. Under **appinnstillinger**, og velg **skjermstørrelse og retning**.

    ![Alternativ for å endre skjermstørrelsen og -retningen for en app](./media/set-aspect-ratio-portrait-landscape/size-orientation.png)

1. I den **retning** listen, velg **stående** eller **liggende**.

1. (Bare nettbrettapper) Under **størrelsesforholdet**, følg ett av disse trinnene:

    - Velg forholdet som samsvarer med målenheten for denne appen.
    - Velg **egendefinert** til å angi din egen størrelse, og deretter angi en bredde mellom 50-3840 og en høyde mellom 50-2160.

    ![Endring av størrelsesforholdet for en nettbrett-app](./media/set-aspect-ratio-portrait-landscape/aspect-tablet.png)
    
1. Under **Tilpass til**, angi enten **på** eller **av**.

    Denne innstillingen er aktivert som standard slik at app-skjermer størrelsen den tilgjengelige plassen på enheten. Når denne innstillingen er aktivert, appens **bredde** egenskapen treff sin **DesignWidth**, og appens **høyde** samsvarer med den **DesignHeight**.

    Hvis du deaktiverer denne innstillingen, justerer appen størrelsesforhold for enheten den kjøres, tar opp all tilgjengelig plass. Appen Skaler ikke, og derfor skjermer kan vise mer informasjon.

    Når denne innstillingen er deaktivert, **Lås størrelsesforhold** er deaktivert og automatisk deaktivert. I tillegg den **bredde** -egenskapen for alle skjermer er satt til `Max(App.Width, App.DesignWidth)`, og deres **høyde** egenskapen er satt til `Max(App.Height, App.DesignHeight)` slik at de kan spore dimensjonene i vinduet som appen kjører. Med denne endringen, kan du opprette apper som svarer til forskjellige enheter og vinduet dimensjoner. Mer informasjon: [Opprett responsivt oppsett](create-responsive-layout.md)

1. Angi enten **På** eller **Av** under **Lås størrelsesforhold**.

    Hvis denne innstillingen er på, beholder appen retningen på skjermen og størrelsesforholdet som er angitt i trinn 2 og 3, uansett enheten. For eksempel beholder en telefonapp som kjører i en nettleser forholdet for en telefon, viser en mørk stolpe på hver side i stedet for å fylle vinduet.

    Hvis denne innstillingen er deaktivert, justerer appen størrelsesforhold for enheten som er den kjører (og forvrenge Brukergrensesnittet om nødvendig).

1. Under **Lås retning** angir du enten **På** eller **Av**.

    Hvis du låser appens retning, beholder appen retningen du angir. Hvis appen kjøres på en enhet hvor skjermen er i en annen retning, appen viser feil og kan vise uønskede resultater. Hvis du låser opp appens retning, justeres den til retningen på skjermen for enheten den kjøres på.

    Du kan også endre appens retning ved å aktivere **Aktiver appinnebygging** i **avanserte innstillinger**. Denne funksjonen øverst til venstre justerer appen når den er innebygd og endrer bakgrunnsfargen for driftslerretet til hvit.

1. Velg **Bruk** for å lagre endringene.

## <a name="next-step"></a>Neste trinn
Velg **Lagre** på **Fil**-menyen for å publisere appen på nytt med de nye innstillingene.