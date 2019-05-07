---
title: 'Skjermkontroll: referanse | Microsoft Docs'
description: Informasjon, inkludert egenskaper og eksempler, om en skjermkontroll
author: emcoope-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 10/25/2016
ms.author: emcoope
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 6fedff6d6ffc34fe390ec6978672d699480a7cb9
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/23/2019
ms.locfileid: "61548735"
ms.PowerAppsDecimalTransform: true
---
# <a name="screen-control-in-powerapps"></a>Skjermkontroll i PowerApps

Et brukergrensesnitt-element som inneholder én eller flere andre kontroller i en app.

## <a name="description"></a>Beskrivelse

De fleste apper har flere **skjerm**-kontroller som inneholder **[etikett](control-text-box.md)**-kontroller, **[knapper](control-button.md)** og andre kontroller som viser data og støtter navigering. For informasjon om hvordan du kan legge til en skjerm, endre rekkefølgen på skjermer og konfigurere navigasjon, kan du se gjennom [legge til en skjerm](../add-screen-context-variables.md).

## <a name="key-properties"></a>Nøkkelegenskaper

**[BackgroundImage](properties-visual.md)** – navnet på en bildefil som vises i bakgrunnen på en skjerm.

**[Fyll](properties-color-border.md)** – bakgrunnsfargen på kontrollen.

## <a name="additional-properties"></a>Tilleggsegenskaper

**Høyde** – høyden på skjermen. Hvis appen er responsiv ([**Tilpass til** ](../set-aspect-ratio-portrait-landscape.md#change-screen-size-and-orientation) er **av**) og enheten som kjører appen er kortere enn denne egenskapen, skjermen kan rulle loddrett.

**[ImagePosition](properties-visual.md)** – plasseringen (**Fyll**, **Tilpass**, **Strekk**, **Fylle side ved side** eller **Midtstill**) til et bilde på en skjerm eller en kontroll hvis det ikke har samme størrelse som bildet.

**Navnet** -navnet på skjermen.

**OnHidden** – virkemåten til en app når brukeren navigerer bort fra en skjerm.

**OnStart** – virkemåten til appen når brukeren åpner appen.

- Formelen som er angitt for denne egenskapen kjøres før den første skjermen i appen vises. Ta i bruk [**Navigate** ](../functions/function-navigate.md)-funksjonen for å endre hvilken skjerm som vises først når appen starter.
- Du kan ikke angi [kontekstvariabler](../working-with-variables.md) med [**UpdateContext**](../functions/function-updatecontext.md)-funksjonen, siden ingen skjerm vises ennå. Du kan imidlertid overføre kontekstvariablene i **Navigate**-funksjonen og opprette og fylle ut en [samling](../working-with-variables.md) ved hjelp av [**Collect**](../functions/function-clear-collect-clearcollect.md)-funksjonen.
- Når du oppdaterer en app, vil formelen som denne egenskapen er angitt for kjøres når appen er lastet inn i PowerApps Studio. Hvis du vil se virkningen av å endre denne egenskapen, må du lagre, lukke og laste inn appen på nytt.
- **OnStart**-egenskapen er faktisk en egenskap for appen og ikke for skjermen. I forbindelse med redigering kan du vise og endre det som en egenskap for den første skjermen i appen. Hvis du fjerner den første skjermen eller endrer rekkefølgen på skjermer, kan det bli vanskelig å finne denne egenskapen. I dette tilfellet lagrer, lukker og laster du inn appen, og egenskapen vil vises på nytt som en egenskap for den første skjermen.

**OnVisible** – virkemåten til en app når brukeren navigerer til en skjerm.

**Retning** -retningen på skjermen. Hvis den **bredde** er større enn sin **høyde**, retningen blir **Layout.Horizontal**; Hvis ikke, vil det være **Layout.Vertical** .

**Størrelse** -et positivt heltall som klassifiserer størrelsen på skjermen. Klassifiseringen bestemmes ved å sammenligne skjermens **bredde** egenskapen til verdiene i den [ **App.SizeBreakpoints** ](../functions/signals.md) egenskapen. Den **ScreenSize** typen består av fire verdier (**små**, **middels**, **stor**, og **ExtraLarge** ) som samsvarer med heltallene fra 1 til 4.

**Bredde** -bredden på skjermen. Hvis appen er responsiv ([**Tilpass til** ](../set-aspect-ratio-portrait-landscape.md#change-screen-size-and-orientation) er **av**) og enheten som kjører appen er mer presist enn denne egenskapen, skjermen kan rulle vannrett.

## <a name="related-functions"></a>Relaterte funksjoner

[**Distinct**( *DataSource*; *ColumnName* )](../functions/function-distinct.md)

## <a name="example"></a>Eksempel

1. Legg til en **[Radio](control-radio.md)**-kontroll, gi den navnet **ScreenFills**, og angi **[Elementer](properties-core.md)**-egenskapen dens til denne verdien:

    `["Red"; "Green"]`

    Vet du ikke hvordan du [legger til, gir navn til og konfigurerer en kontroll](../add-configure-controls.md)?

1. Gi standard-**skjerm**-kontrollen navnet **Kilde**, legg til en annen **skjerm**-kontroll, og gi den navnet **Mål**.

1. I **kilde**, legge til en **[figur](control-shapes-icons.md)** kontroll (for eksempel en pil), og angi dens **[OnSelect](properties-core.md)** egenskapen til Denne formelen:

    `Navigate(Target; ScreenTransition.Fade)`

    Vil du ha mer informasjon om **[Navigate](../functions/function-navigate.md)**-funksjonen eller [andre funksjoner](../formula-reference.md)?

1. Legg til en **[figur](control-shapes-icons.md)**-kontroll (som for eksempel en pil) i **Mål**, og angi **[OnSelect](properties-core.md)**-egenskapen til denne formelen:

    `Navigate(Source; ScreenTransition.Fade)`

1. Angi **[Fyll](properties-color-border.md)**-egenskapen for **Mål** til denne formelen:

    `If("Red" in ScreenFills.Selected.Value; RGBA(255; 0; 0; 1); RGBA(54; 176; 75; 1))`

1. Velg den **kilde** skjermbildet, og velg deretter et alternativ i mens du holder nede Alt-tasten, den **[Radio](control-radio.md)** kontroll, og velg deretter den **[Figur](control-shapes-icons.md)** kontroll.

    **Target** vises i fargen du valgte.

1. I **Target**, og velg den **[figur](control-shapes-icons.md)** kontrollen for å gå tilbake til **kilde**.

1. (valgfritt) Velg det andre alternativet i den **[Radio](control-radio.md)** kontroll, og velg deretter den **[figur](control-shapes-icons.md)** kontroll for å bekrefte at **mål**  vises i den andre fargen.

1. (valgfritt) Endre rekkefølgen på skjermene ved å hvile over **Target** i navigasjonsfeltet til venstre, å velge ellipsen som vises, og deretter velge **Flytt opp**.

    **Target** vises først når brukeren åpner appen.

## <a name="accessibility-guidelines"></a>Retningslinjer for tilgjengelighet

### <a name="color-contrast"></a>Fargekontrast

Når **skjermen** er den fungerende bakgrunnen for tekst, må det være tilstrekkelig med fargekontrast mellom:

- **[Fyll](properties-color-border.md)** og tekst
- **[BackgroundImage](properties-visual.md)** og tekst (hvis aktuelt)

Hvis for eksempel en **skjerm** inneholder en **[etikett](control-text-box.md)**  og etiketten har gjennomsiktig fyll, blir skjermens **[fyll](properties-color-border.md)** den fungerende bakgrunnsfargen for etiketten.

I tillegg til tekst, bør du vurdere å kontrollere fargekontrast med viktige grafiske objekter, for eksempel stjerneikonene i en **[vurdering](control-rating.md)**-kontroll.

### <a name="screen-reader-support"></a>Kundestøtte for skjermlesere

- Det må foreligge et beskrivende navn for hver **skjerm**. Skjermnavnet kan vises og redigeres på samme måte som andre kontroller: i trevisningen i Kontroller-ruten eller i toppteksten i Egenskaper-ruten.

    > [!NOTE]
  > Når en ny **skjerm** er lastet inn, vil skjermlesere lese opp navnet.
