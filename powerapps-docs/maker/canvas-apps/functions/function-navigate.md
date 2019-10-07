---
title: Funksjonene Back og Navigate | Microsoft Docs
description: Referanseinformasjon for funksjonene Back og Navigate i PowerApps, inkludert syntaks og eksempler
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 05/16/2019
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 8f63321b128214d14cd2f4e521d7cc1b85c7b98f
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/07/2019
ms.locfileid: "71984492"
---
# <a name="back-and-navigate-functions-in-powerapps"></a>Funksjonene Back og Navigate i PowerApps

Endre hvilken skjerm som vises.

## <a name="overview"></a>Oversikt

De fleste appene inneholder flere skjermer.  Bruk **Back**- og **Navigate**-funksjonene til å endre hvilken skjerm som vises. Du kan for eksempel angi **[OnSelect](../controls/properties-core.md)** -egenskapen til en knapp til en formel som inkluderer en **Navigate**-funksjon, hvis du ønsker å vise en annen skjerm når en bruker velger den knappen. I denne formelen kan du angi en visuell overgang, som **Nedtoning**, for å kontrollere hvordan en skjerm endres til en annen.  

**Back** og **Navigate** endrer bare hvilken skjerm som vises. Skjermer som ikke vises for øyeblikket fortsetter å operere i bakgrunnen. Du kan bygge formler som refererer til egenskaper for kontroller på andre skjermer. En bruker kan for eksempel endre verdien for en glidebryter på én skjerm, navigere til en annen skjerm som bruker denne verdien i en formel, og få rede hvordan den påvirker hva som skjer i den nye skjermen. Brukeren kan deretter navigere tilbake til den opprinnelige skjermen og bekrefte at Glide bryte ren har beholdt verdien.

[Kontekstvariabler](../working-with-variables.md#use-a-context-variable) beholdes også når en bruker navigerer mellom skjermer. Du kan bruke **Navigate** for å angi én eller flere kontekstvariabler for skjermen som formelen skal vise. Dette er den eneste måten du kan angi kontekstvariabler utenfor skjermen på. Du kan bruke denne fremgangsmåten for å sende parametre til en skjerm. Hvis du har brukt et annet programmeringsverktøy, er denne fremgangsmåten lik den for å sende parametre til prosedyrer.

Du kan bruke begge funksjonene i en [formel for virke måte](../working-with-formulas-in-depth.md).

## <a name="navigate"></a>Navigate

Angi navnet på den første skjermen som skal vises i det første argumentet.  

 I det andre argumentet angir du hvordan den gamle skjermen endres til den nye:

| Overgangsargument | Beskrivelse | Multimediedemonstrasjonen |
| --- | --- | --- |
| **ScreenTransition.Cover** |De nye skjerm lysbildene i visningen, som går fra høyre mot venstre, for å dekke gjeldende skjerm bilde. | ![animasjon av skjerm overgang](media/function-navigate/cover.gif) |
| **ScreenTransition. CoverRight** |De nye skjerm lysbildene i visningen, som går fra venstre mot høyre, for å dekke gjeldende skjerm bilde. | ![hurtig animasjon for skjerm overgang](media/function-navigate/coverright.gif) |
| **ScreenTransition.Fade** |Gjeldende skjerm tones bort for å vise den nye skjermen. | ![skjerm overgang tones animasjon](media/function-navigate/fade.gif) |
| **ScreenTransition. None** (standard) |Den nye skjermen erstatter raskt gjeldende skjerm bilde. | ![skjerm overgang ingen animasjon](media/function-navigate/none.gif) |
| **ScreenTransition.UnCover** | Gjeldende skjerm lysbilder i visningen, som går fra høyre mot venstre, for å avdekke den nye skjermen. | ![å avdekke animasjon for skjerm overgang](media/function-navigate/uncover.gif) |
| **ScreenTransition. UnCoverRight** | Gjeldende skjerm lysbilder utenfor visningen, fra venstre mot høyre, for å avdekke den nye skjermen. | ![skjerm overgang Avdekk hurtig animasjon](media/function-navigate/uncoverright.gif) |

Du kan bruke **Navigate** til å opprette eller oppdatere kontekstvariabler på den nye skjermen. Som et valgfritt tredje argument kan du sende en [post](../working-with-tables.md#records) som inneholder kontekstvariabelnavnet som et [kolonnenavn](../working-with-tables.md#columns) og den nye verdien for kontekstvariabelen.  Denne posten er den samme som posten du brukte med **[UpdateContext](function-updatecontext.md)** -funksjonen.

Angi **[OnHidden](../controls/control-screen.md)** -egenskapen til den forrige skjermen, **[OnVisible](../controls/control-screen.md)** -egenskapen til den nye skjermen, eller begge, for å foreta flere endringer i løpet av overgangen. **App.ActiveScreen**-egenskapen oppdateres for å gjenspeile endringen.

**Navigasjonen** returnerer vanligvis **sann** , men returnerer **False** hvis det oppstår en feil.

## <a name="back"></a>Back

**Tilbake** -funksjonen returnerer til skjermen som sist ble vist.

For hvert **navigasjons** kall sporer appen skjermen som ble vist og overgangen. Du kan bruke etterfølgende **tilbake** kall for å returnere hele veien til skjermen som ble vist da brukeren startet appen.

Når **back** -funksjonen kjøres, brukes den inverse overgangen som standard. Hvis en skjerm for eksempel ble vist gjennom **CoverRight** -overgangen, bruker du **tilbake** **slag** (som er til venstre) for å returnere.  **Toning** og **ingen** er sine egne inverser. Send et valg fritt argument til **tilbake** for å fremtvinge en bestemt overgang.

**Back** returnerer vanligvis **sann** , men returnerer **Usann** hvis brukeren ikke har navigert til en annen skjerm siden oppstart av appen.

## <a name="syntax"></a>Syntaks

**Tilbake**([ *Overgang* ])

* *Overgang* – valg fritt. Den visuelle overgangen som skal brukes mellom gjeldende skjerm og forrige skjerm. Se listen over gyldige verdier for dette argumentet tidligere i dette emnet. Som standard er overgangen som vises når et skjerm bilde returneres er den inverse av overgangen der den ble vist.

**Naviger**( *skjerm* [, *Overgang* [, *UpdateContextRecord* ]])

* *Screen* – obligatorisk. Skjermen som skal vises.
* *Overgang* – valg fritt.  Den visuelle overgangen som skal brukes mellom gjeldende skjerm og den nye skjermen. Se listen over gyldige verdier for dette argumentet tidligere i dette emnet. Standard verdien er **ingen**.
* *UpdateContextRecord* – valgfritt.  En post som inneholder navnet på minst én kolonne og en verdi for hver kolonne. Denne posten oppdaterer kontekstvariablene til den nye skjermen som om den ble sendt til **[UpdateContext](function-updatecontext.md)** -funksjonen.

## <a name="examples"></a>Eksempler

| Formel | Beskrivelse | Resultat |
| --- | --- | --- |
| **Naviger (detaljer)** |Viser **Details**-skjermen uten overgang eller endring i verdi for en kontekstvariabel. |**Detaljer**-skjermen vises raskt. |
| **Navigate( Details, ScreenTransition.Fade )** |Viser **Detaljer**-skjermen med en **Tone**-overgang.  Ingen verdier for en kontekstvariabel endres. |Den gjeldede skjermen tones ned for å vise **Details**-skjermen. |
| **Navigate( Details, ScreenTransition.Fade, {&nbsp;ID:&nbsp;12&nbsp;} )** |Viser **Details**-skjermen med en **Fade**-overgang, og oppdaterer verdien til kontekstvariabelen **ID** til **12**. |Den gjeldende skjermen tones ned for å vise **Details**-skjermen, og kontekstvariabelen **ID** på den skjermen som angis til **12**. |
| **Navigate( Details, ScreenTransition.Fade, {&nbsp;ID:&nbsp;12&nbsp;,&nbsp;Shade:&nbsp;Color.Red&nbsp;} )** |Viser **Detaljer**-skjermen med en **Tone**-overgang. Oppdaterer verdien til kontekstvariabelen **ID** til **12**, og oppdaterer verdien til kontekstvariabelen **Shade** til **Color.Red**. |Den gjeldede skjermen tones ned for å vise **Details**-skjermen. Kontekstvariabelen **ID** på **Detaljer**-skjermen angis til **12**, og kontekstvariabelen **Nyanse** angis til **Color.Red**. Hvis du angir **Fyll**-egenskapen til en kontroll på **Detaljer**-skjermen til **Nyanse**, vises denne kontrollen i rødt. |
| **Back()** | Viser forrige skjerm bilde med standard retur overgang. | Viser forrige skjerm bilde ved hjelp av den omvendte overgangen til overgangen som den gjeldende skjermen kom frem til. |
| **Tilbake (ScreenTransition. Cover)** |  Viser forrige skjerm bilde med **omslags** overføringen. | Viser forrige skjerm bilde gjennom **omslaget** , uavhengig av overgangen som den gjeldende skjermen ble vist gjennom. |

### <a name="step-by-step"></a>Trinnvis

1. Opprett en tom app.

1. Legg til et annet skjerm bilde.

    Appen inneholder to tomme skjermer: **Screen1** og **Screen2**.

1. Angi **Fill** -egenskapen for **Screen2** til verdien `Gray`.

1. Legg til en knapp på **Screen2**, og angi **[OnSelect](../controls/properties-core.md)** -egenskapen til denne formelen:

    ```powerapps-dot
    Navigate( Screen1, ScreenTransition.Cover )
    ```

1. Velg knappen når du holder nede **alt** .

    **Screen1** vises med hvit bakgrunn gjennom en overgang som dekker til venstre.

1. Legg til en knapp på **Screen1**, og angi **OnSelect** -egenskapen til denne formelen:

    ```powerapps-dot
    Back()
    ```

1. Velg knappen når du holder nede **alt** .

    Den andre skjermen vises med en grå bakgrunn gjennom en overgang som dekker til høyre (det motsatte av **forsiden**).

1. Velg knappen på hvert skjerm bilde gjentatte ganger for å sprette frem og tilbake.

[Et annet eksempel](../add-screen-context-variables.md)
