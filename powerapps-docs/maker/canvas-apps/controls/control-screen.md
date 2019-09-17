---
title: 'Skjermkontroll: referanse | Microsoft Docs'
description: Informasjon, inkludert egenskaper og eksempler, om en skjermkontroll
author: emcoope-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 09/14/2019
ms.author: emcoope
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: dceb9eee8eb5a0ed11a4b44fb2df6d63ba5e9cae
ms.sourcegitcommit: 5899d37e38ed7111d5a9d9f3561449782702a5e9
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 09/17/2019
ms.locfileid: "71038246"
ms.PowerAppsDecimalTransform: true
---
# <a name="screen-control-in-powerapps"></a>Skjermkontroll i PowerApps

Et brukergrensesnitt-element som inneholder én eller flere andre kontroller i en app.

## <a name="description"></a>Beskrivelse

De fleste apper har flere **skjerm**-kontroller som inneholder **[etikett](control-text-box.md)** -kontroller, **[knapper](control-button.md)** og andre kontroller som viser data og støtter navigering. Hvis du vil ha informasjon om hvordan du legger til en skjerm, Omorganiser skjermer og konfigurerer navigasjon, kan du gå gjennom [legge til en skjerm](../add-screen-context-variables.md).

## <a name="key-properties"></a>Nøkkelegenskaper

**[BackgroundImage](properties-visual.md)** – navnet på en bildefil som vises i bakgrunnen på en skjerm.

**[Fyll](properties-color-border.md)** – bakgrunnsfargen på kontrollen.

## <a name="additional-properties"></a>Tilleggsegenskaper

**Høyde** -skjerm høyden. Hvis appen svarer ([**Tilpass til siden**](../set-aspect-ratio-portrait-landscape.md#change-screen-size-and-orientation) er **slått av**) og enheten som appen kjører på, er kortere enn denne egenskapen, kan skjermen rulle loddrett.

**[ImagePosition](properties-visual.md)** – plasseringen (**Fyll**, **Tilpass**, **Strekk**, **Fylle side ved side** eller **Midtstill**) til et bilde på en skjerm eller en kontroll hvis det ikke har samme størrelse som bildet.

**Navn** -navnet på skjermen.

**OnHidden** – virkemåten til en app når brukeren navigerer bort fra en skjerm.

**OnVisible** – virkemåten til en app når brukeren navigerer til en skjerm.  Bruk denne egenskapen til å konfigurere variabler og forhånds lastings data som brukes av skjermen.  Bruk egenskapen [**app. OnStart**](../functions/object-app.md#onstart-property) for konfigurasjon én gang når appen startes.

**Orientering** – retningen på skjermen. Hvis **bredden** er større enn **høyden**, blir retningen **oppsett. vannrett**, ellers blir det **oppsett. loddrett**.

**Størrelse** – et positivt hel tall som klassifiserer størrelsen på skjermen. Klassifiseringen bestemmes ved å sammenligne skjermens **bredde** -egenskap med verdiene i [**app. SizeBreakpoints**](../functions/signals.md) -egenskapen. **ScreenSize** -typen består av fire verdier (**liten**, **Middels**, **stor**og **ExtraLarge**) som Sams varer med hel tallene 1 til 4.

**Bredde** -bredden på skjermen. Hvis appen reagerer ([**skaleres til å passe**](../set-aspect-ratio-portrait-landscape.md#change-screen-size-and-orientation) **opp) og**enheten som appen kjører på, er smalere enn denne egenskapen, kan skjermen rulle vannrett.

## <a name="related-functions"></a>Relaterte funksjoner

[**Distinct**( *DataSource*; *ColumnName* )](../functions/function-distinct.md)

## <a name="example"></a>Eksempel

1. Legg til en **[Radio](control-radio.md)** -kontroll, gi den navnet **ScreenFills**, og angi **[Elementer](properties-core.md)** -egenskapen dens til denne verdien:

    `["Red"; "Green"]`

    Vet du ikke hvordan du [legger til, gir navn til og konfigurerer en kontroll](../add-configure-controls.md)?

1. Gi standard-**skjerm**-kontrollen navnet **Kilde**, legg til en annen **skjerm**-kontroll, og gi den navnet **Mål**.

1. Legg til en **[figur](control-shapes-icons.md)** -kontroll (for eksempel en pil) i **kilde**, og angi **[OnSelect](properties-core.md)** -egenskapen til denne formelen:

    `Navigate(Target; ScreenTransition.Fade)`

    Vil du ha mer informasjon om **[Navigate](../functions/function-navigate.md)** -funksjonen eller [andre funksjoner](../formula-reference.md)?

1. Legg til en **[figur](control-shapes-icons.md)** -kontroll (som for eksempel en pil) i **Mål**, og angi **[OnSelect](properties-core.md)** -egenskapen til denne formelen:

    `Navigate(Source; ScreenTransition.Fade)`

1. Angi **[Fyll](properties-color-border.md)** -egenskapen for **Mål** til denne formelen:

    `If("Red" in ScreenFills.Selected.Value; RGBA(255; 0; 0; 1); RGBA(54; 176; 75; 1))`

1. Velg **kilde** -skjermen, og velg deretter et alternativ i **[radio](control-radio.md)** -kontrollen mens du holder nede Alt-tasten, og velg deretter **[figur](control-shapes-icons.md)** -kontrollen.

    **Mål** vises i fargen du valgte.

1. Velg **[figur](control-shapes-icons.md)** -kontrollen i **mål**for å gå tilbake til **kilde**.

1. valg fritt Velg det andre alternativet i **[radio](control-radio.md)** -kontrollen, og velg deretter **[Shape](control-shapes-icons.md)** -kontrollen for å bekrefte at **målet** vises i den andre fargen.

1. valg fritt Endre rekkefølgen på skjermene ved å holde pekeren over **målet** i det venstre navigasjons feltet, velge ellipsen som vises, og deretter velge **Flytt opp**.

    **Mål** vises først når brukeren åpner appen.

## <a name="accessibility-guidelines"></a>Retningslinjer for tilgjengelighet

### <a name="color-contrast"></a>Fargekontrast

Når **skjermen** er den fungerende bakgrunnen for tekst, må det være tilstrekkelig med fargekontrast mellom:

- **[Fyll](properties-color-border.md)** og tekst
- **[BackgroundImage](properties-visual.md)** og tekst (hvis aktuelt)

Hvis for eksempel en **skjerm** inneholder en **[etikett](control-text-box.md)**  og etiketten har gjennomsiktig fyll, blir skjermens **[fyll](properties-color-border.md)** den fungerende bakgrunnsfargen for etiketten.

I tillegg til tekst, bør du vurdere å kontrollere fargekontrast med viktige grafiske objekter, for eksempel stjerneikonene i en **[vurdering](control-rating.md)** -kontroll.

### <a name="screen-reader-support"></a>Kundestøtte for skjermlesere

- Det må foreligge et beskrivende navn for hver **skjerm**. Skjermnavnet kan vises og redigeres på samme måte som andre kontroller: i trevisningen i Kontroller-ruten eller i toppteksten i Egenskaper-ruten.

    > [!NOTE]
  > Når en ny **skjerm** er lastet inn, vil skjermlesere lese opp navnet.
