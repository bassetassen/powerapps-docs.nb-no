---
title: 'Skjermkontroll: referanse | Microsoft Docs'
description: Informasjon, inkludert egenskaper og eksempler, om en skjermkontroll
author: fikaradz
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 10/25/2016
ms.author: fikaradz
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 15264a783922891a84e805cea211f2945bca3f3e
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/24/2018
ms.locfileid: "42863901"
---
# <a name="screen-control-in-powerapps"></a>Skjermkontroll i PowerApps
Et brukergrensesnitt-element som inneholder én eller flere andre kontroller i en app.

## <a name="description"></a>Beskrivelse
De fleste apper har flere **skjerm**-kontroller som inneholder **[etikett](control-text-box.md)**-kontroller, **[knapper](control-button.md)** og andre kontroller som viser data og støtter navigering.

## <a name="key-properties"></a>Nøkkelegenskaper
**[BackgroundImage](properties-visual.md)** – navnet på en bildefil som vises i bakgrunnen på en skjerm.

**[Fyll](properties-color-border.md)** – bakgrunnsfargen på kontrollen.

## <a name="additional-properties"></a>Tilleggsegenskaper
**[ImagePosition](properties-visual.md)** – posisjonen (**Fyll**, **Tilpass**, **Strekk**, **Flis** eller **Midtstill**) til et bilde på en skjerm eller i en kontroll hvis skjermen eller kontrollen ikke har samme størrelse som bildet.

**OnHidden** – virkemåten til en app når brukeren navigerer bort fra en skjerm.

**OnVisible** – virkemåten til en app når brukeren navigerer til en skjerm.

**OnStart** – virkemåten til appen når brukeren åpner appen.

* Formelen som er angitt for denne egenskapen kjøres før den første skjermen i appen vises. Ta i bruk [**Navigate** ](../functions/function-navigate.md)-funksjonen for å endre hvilken skjerm som vises først når appen starter.
* Du kan ikke angi [kontekstvariabler](../working-with-variables.md) med [**UpdateContext**](../functions/function-updatecontext.md)-funksjonen, siden ingen skjerm vises ennå. Du kan imidlertid overføre kontekstvariablene i **Navigate**-funksjonen og opprette og fylle ut en [samling](../working-with-variables.md) ved hjelp av [**Collect**](../functions/function-clear-collect-clearcollect.md)-funksjonen.
* Når du oppdaterer en app, vil formelen som denne egenskapen er angitt for kjøres når appen er lastet inn i PowerApps Studio. Hvis du vil se virkningen av å endre denne egenskapen, må du lagre, lukke og laste inn appen på nytt.
* **OnStart**-egenskapen er faktisk en egenskap for appen og ikke for skjermen. I forbindelse med redigering kan du vise og endre det som en egenskap for den første skjermen i appen. Hvis du fjerner den første skjermen eller endrer rekkefølgen på skjermer, kan det bli vanskelig å finne denne egenskapen. I dette tilfellet lagrer, lukker og laster du inn appen, og egenskapen vil vises på nytt som en egenskap for den første skjermen.

## <a name="related-functions"></a>Relaterte funksjoner
[**Distinct**( *DataSource*, *ColumnName* )](../functions/function-distinct.md)

## <a name="example"></a>Eksempel
1. Legg til en **[Radio](control-radio.md)**-kontroll, gi den navnet **ScreenFills**, og angi **[Elementer](properties-core.md)**-egenskapen dens til denne verdien:<br>
   **["Red", "Green"]**
   
    Vet du ikke hvordan du [legger til, gir navn til og konfigurerer en kontroll](../add-configure-controls.md)?
2. Gi standard-**skjerm**-kontrollen navnet **Kilde**, legg til en annen **skjerm**-kontroll, og gi den navnet **Mål**.
3. Legg til en **[figur](control-shapes-icons.md)**-kontroll (som eksempelvis en pil) i **Kilde**, og angi **[OnSelect](properties-core.md)**-egenskapen til denne formelen:<br>
   **Navigate(Target, ScreenTransition.Fade)**
   
    Vil du ha mer informasjon om **[Navigate](../functions/function-navigate.md)**-funksjonen eller [andre funksjoner](../formula-reference.md)?
4. Legg til en **[figur](control-shapes-icons.md)**-kontroll (som for eksempel en pil) i **Mål**, og angi **[OnSelect](properties-core.md)**-egenskapen til denne formelen:<br>
   **Navigate(Source, ScreenTransition.Fade)**
5. Angi **[Fyll](properties-color-border.md)**-egenskapen for **Mål** til denne formelen:<br>
   **If("Red" in ScreenFills.Selected.Value, RGBA(255, 0, 0, 1), RGBA(54, 176, 75, 1))**
6. Fra **Kilde** trykker du på F5, klikker eller trykker på noen av alternativene i **[Radio](control-radio.md)**-kontrollen, og deretter klikker eller trykker du på **[Figur](control-shapes-icons.md)**-kontrollen.
   
    **Mål** vises i fargen du valgte.
7. Klikk eller trykk på **[Figur](control-shapes-icons.md)**-kontrollen på **Mål** for å gå tilbake til **Kilde**.
8. (valgfritt) Klikk eller trykk på det andre alternativet i **[Radio](control-radio.md)**-kontrollen, og deretter klikker eller trykker du på **[Figur](control-shapes-icons.md)**-kontrollen for å bekrefte at **Mål** vises i den andre fargen.
9. Trykk på ESC for å gå tilbake til standardarbeidsområdet.


## <a name="accessibility-guidelines"></a>Retningslinjer for tilgjengelighet
### <a name="color-contrast"></a>Fargekontrast
Når **skjermen** er den fungerende bakgrunnen for tekst, må det være tilstrekkelig med fargekontrast mellom:
* **[Fyll](properties-color-border.md)** og tekst
* **[BackgroundImage](properties-visual.md)** og tekst (hvis aktuelt)

Hvis for eksempel en **skjerm** inneholder en **[etikett](control-text-box.md)**  og etiketten har gjennomsiktig fyll, blir skjermens **[fyll](properties-color-border.md)** den fungerende bakgrunnsfargen for etiketten.

I tillegg til tekst, bør du vurdere å kontrollere fargekontrast med viktige grafiske objekter, for eksempel stjerneikonene i en **[vurdering](control-rating.md)**-kontroll.

### <a name="screen-reader-support"></a>Kundestøtte for skjermlesere
* Det må foreligge et beskrivende navn for hver **skjerm**. Skjermnavnet kan vises og redigeres på samme måte som andre kontroller: i trevisningen i Kontroller-ruten eller i toppteksten i Egenskaper-ruten.

    > [!NOTE]
  > Når en ny **skjerm** er lastet inn, vil skjermlesere lese opp navnet. 
