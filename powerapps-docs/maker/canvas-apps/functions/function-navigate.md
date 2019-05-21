---
title: Funksjonene Back og Navigate | Microsoft Docs
description: Referanseinformasjon for funksjonene Back og Navigate i PowerApps, inkludert syntaks og eksempler
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 05/16/2019
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: e57cc541c753ff3f24f66a78c6e30d6e5683b41a
ms.sourcegitcommit: 57dfad065318263e162e949e26b5c2684ba0dccb
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 05/17/2019
ms.locfileid: "65828169"
ms.PowerAppsDecimalTransform: true
---
# <a name="back-and-navigate-functions-in-powerapps"></a>Funksjonene Back og Navigate i PowerApps

Endre hvilken skjerm som vises.

## <a name="overview"></a>Oversikt

De fleste appene inneholder flere skjermer.  Bruk **Back**- og **Navigate**-funksjonene til å endre hvilken skjerm som vises. Du kan for eksempel angi **[OnSelect](../controls/properties-core.md)**-egenskapen til en knapp til en formel som inkluderer en **Navigate**-funksjon, hvis du ønsker å vise en annen skjerm når en bruker velger den knappen. I denne formelen kan du angi en visuell overgang, som **Nedtoning**, for å kontrollere hvordan en skjerm endres til en annen.  

**Back** og **Navigate** endrer bare hvilken skjerm som vises. Skjermer som ikke vises for øyeblikket fortsetter å operere i bakgrunnen. Du kan opprette formler og henvise til egenskaper for kontroller på andre skjermer. En bruker kan for eksempel endre verdien for en glidebryter på en skjerm, navigere til en annen skjerm som bruker den verdien i en formel og få rede hvordan de påvirker hva som skjer i den nye skjermen. Brukeren kan deretter gå tilbake til den opprinnelige skjermen og Bekreft at glidebryteren har beholdt verdien.

[Kontekstvariabler](../working-with-variables.md#use-a-context-variable) beholdes også når en bruker navigerer mellom skjermer. Du kan bruke **Navigate** for å angi én eller flere kontekstvariabler for skjermen som formelen skal vise. Dette er den eneste måten du kan angi kontekstvariabler utenfor skjermen på. Du kan bruke denne fremgangsmåten for å sende parametre til en skjerm. Hvis du har brukt et annet programmeringsverktøy, er denne fremgangsmåten lik den for å sende parametre til prosedyrer.

Du kan bruke en av funksjonene i en [formel for virkemåte](../working-with-formulas-in-depth.md).

## <a name="navigate"></a>Navigate

Angi navnet på den første skjermen som skal vises i det første argumentet.  

 I det andre argumentet angir du hvordan den gamle skjermen endres til den nye:

| Overgangsargument | Beskrivelse | Demonstrasjon |
| --- | --- | --- |
| **ScreenTransition.Cover** |Den nye skjermen glir inn, flytte høyre mot venstre, slik at den dekker den gjeldende skjermen. | ![skjermen overgang cover animasjon](media/function-navigate/cover.gif) |
| **ScreenTransition.CoverRight** |De nye skjermen lysbildene inn, og flytte fra venstre mot høyre, slik at den dekker den gjeldende skjermen. | ![skjermen overgang cover høyre animasjon](media/function-navigate/coverright.gif) |
| **ScreenTransition.Fade** |De gjeldende skjermen tones ned med en gang til vise den nye skjermen. | ![skjermen overgang fade animasjon](media/function-navigate/fade.gif) |
| **ScreenTransition.None** (standard) |Den nye skjermen erstattes raskt den gjeldende skjermen. | ![skjermen overgang Ingen animasjon](media/function-navigate/none.gif) |
| **ScreenTransition.UnCover** | Den gjeldende skjermen glir ut av visningen, flytte høyre mot venstre, å avdekke den nye skjermen. | ![skjermen overgang Avdekk animasjon](media/function-navigate/uncover.gif) |
| **ScreenTransition.UnCoverRight** | De gjeldende skjermen lysbildene utenfor visningen, flytte fra venstre mot høyre, å avdekke den nye skjermen. | ![skjermen overgang Avdekk høyre animasjon](media/function-navigate/uncoverright.gif) |

Du kan bruke **Navigate** til å opprette eller oppdatere kontekstvariabler på den nye skjermen. Som et valgfritt tredje argument kan du sende en [post](../working-with-tables.md#records) som inneholder kontekstvariabelnavnet som et [kolonnenavn](../working-with-tables.md#columns) og den nye verdien for kontekstvariabelen.  Denne posten er den samme som posten du brukte med **[UpdateContext](function-updatecontext.md)**-funksjonen.

Angi **[OnHidden](../controls/control-screen.md)**-egenskapen til den forrige skjermen, **[OnVisible](../controls/control-screen.md)**-egenskapen til den nye skjermen, eller begge, for å foreta flere endringer i løpet av overgangen. **App.ActiveScreen**-egenskapen oppdateres for å gjenspeile endringen.

**Navigere** returnerer som regel **SANN** , men returnerer **USANN** Hvis det oppstår en feil.

## <a name="back"></a>Back

Den **tilbake** -funksjonen returnerer til skjermen som sist ble vist.

For hver **Navigate** kall, appen sporer skjermen som ble vist og overgangen. Du kan bruke etterfølgende **tilbake** kall til å returnere helt til skjermen som vises når brukeren startet appen.

Når den **tilbake** funksjonen kjører, eller INVERS overgangen brukes som standard. For eksempel, hvis en skjerm vises gjennom den **CoverRight** overgang, **tilbake** bruker **UnCover** (som er til venstre) til å returnere.  **Ton** og **ingen** er sine egne inverses. Sende et valgfritt argument til **tilbake** tvinge en bestemt overgang.

**Tilbake** returnerer som regel **SANN** , men returnerer **USANN** Hvis brukeren ikke har navigert til en annen skjerm etter at du startet appen.

## <a name="syntax"></a>Syntaks

**Tilbake**([ *overgang* ])

* *Overgang* – valgfritt. Den visuelle overgangen som skal brukes mellom gjeldende skjerm og forrige skjermbilde. Se listen over gyldige verdier for dette argumentet tidligere i dette emnet. Som standard er overgangen en skjerm som returnerer inverse av overgangen som det har vært.

**Navigere**( *skjermen* [; *overgang* [; *UpdateContextRecord* ]])

* *Screen* – obligatorisk. Skjermen som skal vises.
* *Overgang* – valgfritt.  Den visuelle overgangen som skal brukes mellom gjeldende skjerm og den nye skjermen. Se listen over gyldige verdier for dette argumentet tidligere i dette emnet. Standardverdien er **ingen**.
* *UpdateContextRecord* – valgfritt.  En post som inneholder navnet på minst én kolonne og en verdi for hver kolonne. Denne posten oppdaterer kontekstvariablene til den nye skjermen som om den ble sendt til **[UpdateContext](function-updatecontext.md)**-funksjonen.

## <a name="examples"></a>Eksempler

| Formel | Beskrivelse | Resultat |
| --- | --- | --- |
| **Navigere (detaljer)** |Viser **Details**-skjermen uten overgang eller endring i verdi for en kontekstvariabel. |**Detaljer**-skjermen vises raskt. |
| **Navigate( Details; ScreenTransition.Fade )** |Viser **Detaljer**-skjermen med en **Tone**-overgang.  Ingen verdier for en kontekstvariabel endres. |Den gjeldede skjermen tones ned for å vise **Details**-skjermen. |
| **Navigate( Details; ScreenTransition.Fade; {&nbsp;ID:&nbsp;12&nbsp;} )** |Viser **Details**-skjermen med en **Fade**-overgang, og oppdaterer verdien til kontekstvariabelen **ID** til **12**. |Den gjeldende skjermen tones ned for å vise **Details**-skjermen, og kontekstvariabelen **ID** på den skjermen som angis til **12**. |
| **Navigate( Details; ScreenTransition.Fade; {&nbsp;ID:&nbsp;12&nbsp;;&nbsp;Shade:&nbsp;Color.Red&nbsp;} )** |Viser **Detaljer**-skjermen med en **Tone**-overgang. Oppdaterer verdien til kontekstvariabelen **ID** til **12**, og oppdaterer verdien til kontekstvariabelen **Shade** til **Color.Red**. |Den gjeldede skjermen tones ned for å vise **Details**-skjermen. Kontekstvariabelen **ID** på **Detaljer**-skjermen angis til **12**, og kontekstvariabelen **Nyanse** angis til **Color.Red**. Hvis du angir **Fyll**-egenskapen til en kontroll på **Detaljer**-skjermen til **Nyanse**, vises denne kontrollen i rødt. |
| **Back()** | Viser forrige skjerm med standard return overgangen. | Viser forrige skjerm gjennom INVERS overgangen for overføringen som den gjeldende skjermen vises. |
| **Tilbake (ScreenTransition.Cover)** |  Viser forrige skjerm med den **dekker** overgang. | Viser forrige skjerm gjennom den **dekker** overgang, uavhengig av overgangen som den gjeldende skjermen vises. |

### <a name="step-by-step"></a>Trinnvis

1. Opprett en tom app.

1. Legg til en skjerm til den.

    Appen inneholder to tomme skjermer: **Screen1** og **skjerm2**.

1. Angi den **Fyll** -egenskapen for **Screen2** til verdien `Gray`.

1. På **Screen2**, Legg til en knapp, og angi dens **[OnSelect](../controls/properties-core.md)** egenskapen til denne formelen:

    ```powerapps-comma
    Navigate( Screen1; ScreenTransition.Cover )
    ```

1. Mens du holder nede den **Alt** nøkkel, velg knappen.

    **Screen1** vises med en hvit bakgrunn gjennom en overgang som dekker til venstre.

1. På **Screen1**, Legg til en knapp, og angi dens **OnSelect** egenskapen til denne formelen:

    ```powerapps-comma
    Back()
    ```

1. Mens du holder nede den **Alt** nøkkel, velg knappen.

    Det andre skjermbildet vises med en grå bakgrunn gjennom en overgang som avdekker til høyre (inverse av **dekker**).

1. Velg knappen på hver skjerm flere ganger for å bytte.

[Et annet eksempel](../add-screen-context-variables.md)
