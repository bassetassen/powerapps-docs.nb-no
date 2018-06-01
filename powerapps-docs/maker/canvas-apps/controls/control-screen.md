---
title: 'Skjermkontroll: referanse | Microsoft Docs'
description: Informasjon, inkludert egenskaper og eksempler, om en skjermkontroll
services: ''
suite: powerapps
documentationcenter: na
author: fikaradz
manager: anneta
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/25/2016
ms.author: fikaradz
ms.openlocfilehash: cd2e2a8c28fb894b1935b29bf80bf65eb631a266
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/22/2018
ms.locfileid: "30996522"
---
# <a name="screen-control-in-powerapps"></a>Skjermkontroll i PowerApps
Et brukergrensesnitt-element som inneholder én eller flere andre kontroller i en app.

## <a name="description"></a>Beskrivelse
De fleste apper har flere **skjerm**-kontroller som inneholder **[etikett](control-text-box.md)**-kontroller, **[knapp](control-button.md)**-kontroller og andre kontroller som viser data og støtter navigering.

## <a name="key-properties"></a>Nøkkelegenskaper
**[BackgroundImage](properties-visual.md)** – navnet på en bildefil som vises i bakgrunnen på en skjerm.

**[Fyll](properties-color-border.md)** – bakgrunnsfargen på kontrollen.

## <a name="additional-properties"></a>Tilleggsegenskaper
**[ImagePosition](properties-visual.md)** – posisjonen (**Fyll**, **Tilpass**, **Strekk**, **Flis** eller **Midtstill**) til et bilde på et skjermbilde eller i en kontroll hvis skjermbildet eller kontrollen ikke har samme størrelse som bildet.

**OnHidden** – virkemåten til en app når brukeren navigerer bort fra en skjerm.

**OnVisible** – virkemåten til en app når brukeren navigerer til et skjermbilde.

**OnStart** – virkemåten til appen når brukeren åpner appen.

* Formelen som er angitt for denne egenskapen kjøres før det første skjermbildet i appen vises. Kommuniser med [ **Naviger** ](../functions/function-navigate.md)-funksjonen for å endre hvilken skjerm som vises først når appen starter.
* Du kan ikke angi [kontekstvariabler](../working-with-variables.md) med [**UpdateContext**](../functions/function-updatecontext.md)-funksjonen, fordi ingen skjerm vises ennå. Du kan imidlertid overføre kontekstvariablene i **Navigate**-funksjonen og opprette og fylle ut en [samling](../working-with-variables.md) ved hjelp av [**Collect**](../functions/function-clear-collect-clearcollect.md)-funksjonen.
* Når du oppdaterer en app, vil formelen som denne egenskapen er angitt for kjøres når appen er lastet inn i PowerApps Studio. Hvis du vil se virkningen av å endre denne egenskapen, må du lagre, lukke og laste inn appen din på nytt.
* **OnStart**-egenskapen er faktisk en egenskap i appen og ikke på skjermen. I forbindelse med redigering kan du vise og endre det som en egenskap for det første skjermbildet i appen. Hvis du fjerner det første skjermbildet eller endrer rekkefølgen på skjermbilder, kan det bli vanskelig å finne denne egenskapen. I dette tilfellet lagrer, lukker og laster du inn appen, og egenskapen vil vises på nytt som en egenskap for det første skjermbildet.

## <a name="related-functions"></a>Relaterte funksjoner
[**Distinct**( *DataSource*, *ColumnName* )](../functions/function-distinct.md)

## <a name="example"></a>Eksempel
1. Legg til en **[rullegardin](control-radio.md)**-kontroll, gi den navnet **ChooseProduct**, og angi **[Elementer](properties-core.md)**-egenskapen til denne verdien:<br>
   **["Red", "Green"]**
   
    Vet du ikke hvordan du [legger til, gir navn til og konfigurerer en kontroll](../add-configure-controls.md)?
2. Gi standard **skjerm**-kontrollen navnet **Kilde**, legg til en annen **skjerm**-kontroll, og gi den navnet **Mål**.
3. Legg til en **[figur](control-shapes-icons.md)**-kontroll (som eksempelvis en pil) i **Kilde**, og angi **[OnSelect](properties-core.md)**-egenskapen til denne formelen:<br>
   **Navigate(Target, ScreenTransition.Fade)**
   
    Vil du ha mer informasjon om **[Navigate](../functions/function-navigate.md)**-funksjonen eller [andre funksjoner](../formula-reference.md)?
4. Legg til en **[figur](control-shapes-icons.md)**-kontroll (som eksempelvis en pil) i **Mål**, og angi **[OnSelect](properties-core.md)**-egenskapen til denne formelen:<br>
   **Navigate(Source, ScreenTransition.Fade)**
5. Angi **[Fyll](properties-color-border.md)**-egenskapen for **Mål** til denne formelen:<br>
   **If("Red" in ScreenFills.Selected.Value, RGBA(255, 0, 0, 1), RGBA(54, 176, 75, 1))**
6. Fra **kilde** trykker du på F5, klikker eller trykker på noen av alternativene i **[Radio](control-radio.md)**-kontrollen, og deretter klikker eller trykker du på **[Figur](control-shapes-icons.md)**-kontrollen.
   
    **Mål** vises i fargen du valgte.
7. Klikk eller trykk på **[Figur](control-shapes-icons.md)**-kontrollen på **Mål** for å gå tilbake til **Kilde**.
8. (valgfritt) Klikk eller trykk på det andre alternativet i **[Radio](control-radio.md)**-kontrollen, og deretter klikker eller trykker du på **[Figur](control-shapes-icons.md)**-kontrollen for å bekrefte at **Mål** vises i den andre fargen.
9. Trykk på ESC for å gå tilbake til standardarbeidsområdet.

