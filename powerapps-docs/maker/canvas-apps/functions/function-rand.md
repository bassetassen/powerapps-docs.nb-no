---
title: Rand-funksjonen | Microsoft Docs
description: Referanseinformasjon for Rand-funksjonen i PowerApps, inkludert syntaks og eksempler
author: gregli-msft
ms.service: powerapps
ms.topic: reference
ms.component: canvas
ms.date: 06/09/2018
ms.author: gregli
ms.openlocfilehash: 3bf29a3df235d669de2f2862f11b19f428378123
ms.sourcegitcommit: 6bfb002180148a3f22a4d1d8d750fc442489ebe4
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/11/2018
ms.locfileid: "35291770"
---
# <a name="rand-function-in-powerapps"></a>Rand-funksjonen i PowerApps
Returnerer et pseudo-tilfeldig tall.

## <a name="description"></a>Beskrivelse
**Rand**-funksjonen returnerer et pseudo-tilfeldig tall som er større eller tilsvarende 0, og mindre enn 1.

## <a name="volatile-functions"></a>Flyktige funksjoner
**Rand** er en flyktig funksjon.  Hver gang en av disse funksjonene evalueres returnerer den en annen verdi.  

En flyktig funksjon returnerer en annen verdi når den brukes i en formel for dataflyt, hvis formelen den viser, ser ut til å være evaluert på nytt.  Hvis ingenting annet endres i formelen, vil den ha samme verdi i hele kjøringen av appen.

En etikett med **Label1.Text = Rand()** vil for eksempel ikke endres mens appen er aktiv.  Å bare lukke og åpne appen vil resultere i en ny verdi.

Funksjonen vil evalueres på nytt hvis den er en del av en formel der noe annet er endret.  Hvis vi for eksempel endrer eksemplet til å omfatte en glidebryter med **Label1.Text = Slider1.Value + Rand()**, blir et tilfeldig tall generert hver gang verdien for glidebryteren endres og tekstegenskapen for etiketten evalueres på nytt.  Nedenfor finner du et eksempel.

Når den brukes i en [virkemåteformel](../working-with-formulas-in-depth.md) blir **Rand** evaluert hver gang virkemåteformelen evalueres.  Nedenfor finner du et eksempel.

## <a name="syntax"></a>Syntaks
**Rand**()

## <a name="examples"></a>Eksempler

#### <a name="display-a-different-random-number-as-user-input-changes"></a>Vis et annet tilfeldig tall når brukerinndata endres
1. Legg til en kontroll for **[glidebryteren](../controls/control-slider.md)**, og gi den det nye navnet **Slider1** hvis den har et annet navn.

1. Legg til en **[Etikett](../controls/control-text-box.md)**, og angi **Tekst**-egenskapen til denne formelen:

    **Slider1.Value + Rand()**

    Etiketten viser **50** (standardverdien for glidebryteren) pluss et tilfeldig desimal:

    ![En skjerm som viser en etikett med 50.741](media/function-rand/rand-slider-1.png)

1. Du kan endre verdien av glidebryteren mens du holder nede ALT.

    Desimaldelen av etiketten viser et nytt tilfeldig tall hver gang du endrer verdien for glidebryteren:

    ![Fire skjermer som viser en etikett med fire forskjellige, tilfeldige desimalverdier for hver av fire forskjellige innstillinger for glidebryteren 70.899, 84.667, 90.134, 99.690](media/function-rand/rand-slider-results.png)

#### <a name="create-a-table-of-random-numbers"></a>Slik oppretter du en tabell med tilfeldige tall
1. Legg til en **[Knapp](../controls/control-button.md)**, og angi **[OnSelect](../controls/properties-core.md)**-egenskapen til denne formelen:

    **ClearCollect( RandomNumbers, ForAll( [ 1, 2, 3, 4, 5 ], Rand() ))**

    Denne formelen oppretter én kolonnetabell som brukes til å oppdatere fem ganger, noe som resulterer i fem tilfeldige tall.

1. Legg til en **[Datatabell](../controls/control-data-table.md)**, angi egenskapen for **Elementer** til **RandomNumbers** og vis deretter **Verdi**-feltet.

    ![En skjerm som viser en tabell med fem forskjellige desimalverdier 0.857, 0.105, 0.979, 0.167, 0.814](media/function-rand/set-show-data.png)

1. Velg knappen ved å klikke eller trykke på den mens du holder nede ALT.

    Datatabellen viser fem tilfeldige desimaltall:

    ![En skjerm som viser en tabell med fem forskjellige desimalverdier 0.857, 0.105, 0.979, 0.167, 0.814](media/function-rand/rand-collection-1.png)

1. Velg knappen igjen for å vise en annen liste med tilfeldige tall:

    ![Den samme skjermen som viser en datatabell med et nytt sett med fem forskjellige desimalverdier0.414, 0.128, 0.860, 0.303, 0.568](media/function-rand/rand-collection-2.png)

Hvis du vil generere et enkelt tilfeldig tall i stedet for en tabell, kan du bruke **Set( RandomNumber, Rand() )**.
