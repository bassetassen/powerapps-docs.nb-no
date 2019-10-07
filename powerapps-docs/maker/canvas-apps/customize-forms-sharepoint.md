---
title: Tilpass et skjema i en lerretsapp | Microsoft Docs
description: Angi hvilke data som skal vises i et lerretsappskjema i PowerApps, hvilken rekkefølge de skal vises i, og i hvilke kontroller.
author: tapanm-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 03/17/2018
ms.author: tapanm
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 67e7e0074259731bb1d3c50474e8020e3f4fcf1b
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/07/2019
ms.locfileid: "71993179"
---
# <a name="customize-a-canvas-app-form-in-powerapps"></a>Tilpass et lerretsappskjema i PowerApps

Tilpass en **Visningsskjema**-kontroll og en **Redigeringsskjema**-kontroll i en lerretsapp slik at de viser de viktigste dataene i den mest intuitive rekkefølgen, for å gjøre det enkelt for brukerne å forstå og oppdatere dataene.

Hvert skjema består av ett eller flere kort, som viser data fra en bestemt kolonne i datakilden. Ved å følge trinnene i dette emnet kan du angi hvilke kort som skal vises i et skjema og flytte kortene opp og ned innenfor et skjema.

Hvis du ikke er kjent med lerretet, kan du se [Hva er lerret-apper?](getting-started.md).

## <a name="prerequisites"></a>Forutsetninger

[Å genere en app](data-platform-create-app.md) fra Common Data Service, og deretter [tilpasse galleriet](customize-layout-sharepoint.md) i denne appen.

## <a name="show-and-hide-cards"></a>Å vise og skjule kort

1. Logg deg på [powerapps](http://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc), og åpne deretter appen du genererte og tilpasset.

1. Skriv eller lim inn **D** i søke feltet i navigasjons feltet til venstre for å filtrere listen over elementer, og velg deretter **DetailForm1**.

    > [!div class="mx-imgBorder"]
    > skjerm bilde for @no__t detaljer om 0Select @ no__t-1

1. Velg **Rediger felt** på **Egenskaper**-fanen i den høyre ruten for å åpne **Felt**-ruten.

    > [!div class="mx-imgBorder"]
    > @no__t – 0Open felt rute @ no__t-1

1. Skjul et felt, for eksempel **Beskrivelse**, ved å holde pekeren over det, velge ellipsen (...) som vises, og velg deretter **Fjern**.

    > [!div class="mx-imgBorder"]
    > @no__t – 0List av felt @ no__t-1

1. Vis et felt ved å velge **Legg til felt**, skrive inn eller lime inn de første bokstavene i feltets navn i søke boksen, merke av for feltet, og deretter velge **Legg til**.

    > [!div class="mx-imgBorder"]
    > @no__t – 0List av felt @ no__t-1

## <a name="reorder-the-cards"></a>Å endre rekkefølgen på kortene

1. I **felt** -ruten drar du **konto navn** -feltet til toppen av listen over felt.

    Kortene i **DetailForm1** reflekterer endringen.

    > [!div class="mx-imgBorder"]
    > @no__t – 0Reordered Cards @ no__t-1

1. valg fritt Endre rekkefølgen på de andre kortene til denne sekvensen:

    - Kontonavn
    - Antall ansatte
    - Årlig omsetning
    - Hovedtelefon
    - Adresse 1: Gateadresse 1
    - Adresse 1: Gate/vei 2
    - Adresse 1: Nummer
    - Adresse 1: Post nummer

1. Skriv eller lim inn **Ed** i søke feltet i det venstre navigasjons feltet, og velg deretter **EditForm1** for å velge den.

1. Gjenta trinnene i fremgangsmåten ovenfor og i denne, slik at feltene i **EditForm1** samsvarer med dem i **DetailForm1**.

## <a name="run-the-app"></a>Å kjøre appen

1. I det venstre navigasjons feltet skriver eller limer du inn **br** i søke feltet, og deretter velger du **BrowseScreen1** for å velge den.

1. Åpne forhåndsvisningsmodus ved å trykke på F5 (eller ved å velge **Forhåndsvisning**-ikonet nær hjørnet øverst til høyre).

    > [!div class="mx-imgBorder"]
    > ![Preview-ikon @ no__t-1

1. Velg pluss-ikonet i hjørnet øverst til høyre for å legge til en post i **EditScreen1**.

    > [!div class="mx-imgBorder"]
    > ![Add post @ no__t-1

1. Legg til de dataene du ønsker, og velg deretter merke ikonet i øvre høyre hjørne for å lagre endringene og gå tilbake til **BrowseScreen1**.

    > [!div class="mx-imgBorder"]
    > ![Save post @ no__t-1

1. Velg pilen for elementet du nettopp opprettet, for å vise detaljer om elementet i **DetailScreen1**.

    > [!div class="mx-imgBorder"]
    > @no__t – 0Right pil @ no__t-1

1. Velg Rediger-ikonet i hjørnet øverst til høyre for å oppdatere posten i **EditScreen1**.

    > [!div class="mx-imgBorder"]
    > ![Edit post @ no__t-1

1. Endre informasjonen i ett eller flere felt, og merk deretter av for Merk i øvre høyre hjørne for å lagre endringene og gå tilbake til **DetailScreen1**.

    > [!div class="mx-imgBorder"]
    > @no__t – 0Save endringer @ no__t-1

1. Velg papir kurv-ikonet nær hjørnet øverst til høyre for å slette posten du nettopp oppdaterte, og gå tilbake til **BrowseScreen1**.

    > [!div class="mx-imgBorder"]
    > ![Delete post @ no__t-1

1. Lukk forhånds visnings modus ved å trykke på ESC (eller ved å velge Lukk-ikonet nær hjørnet øverst til venstre).

## <a name="next-steps"></a>Neste trinn

- [Å lagre og publisere](save-publish-app.md) appen.
- [Å tilpasse et kort](customize-card.md) i appen.