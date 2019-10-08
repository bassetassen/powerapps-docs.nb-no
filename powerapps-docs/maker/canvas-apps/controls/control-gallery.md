---
title: 'Galleri-kontrollen: referanse | Microsoft Docs'
description: Informasjon om Galleri-kontrollen, inkludert egenskaper og eksempler
author: fikaradz
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 05/25/2017
ms.author: fikaradz
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 964f57c427b8e9e2e2f7a50e3d6e149ddea8e8b0
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/07/2019
ms.locfileid: "71986678"
ms.PowerAppsDecimalTransform: true
---
# <a name="gallery-control-in-canvas-apps"></a>Galleri-kontrollen i lerret apper

En kontroll som inneholder andre kontroller og viser et datasett.

## <a name="description"></a>Beskrivelse

En **Galleri**-kontroll kan vise flere poster fra en datakilde, og hver post kan inneholde flere typer data. En **Galleri**-kontroll kan vise flere kontakter for hvert element og kontaktinformasjon for hver kontakt, deriblant et navn, en postadresse og et telefonnummer. Hvert felt vises i en separat kontroll i **Galleri**-kontrollen, og du kan konfigurere disse kontrollene i malen. Malen vises som det første elementet i galleriet, i den venstre kanten av en **Galleri**-kontroll i vannrett/liggende retning og øverst i en **Galleri**-kontroll i loddrett/stående retning. Eventuelle endringer du gjør i malen, gjenspeiles i hele **Galleri**-kontrollen.

Forhånds definerte maler for å vise bilder og tekst i et galleri er tilgjengelig, i tillegg til et galleri for elementer med variabel høyde.

## <a name="limitations"></a>Begrensninger

Hvis en bruker ruller gjennom den **fleksible høyden** på Galleri-kontrollen før alle elementene lastes inn, kan elementet som for øyeblikket er i visning, skyve seg ned og ut av visningen når data innlastingen er fullført. Du unngår dette problemet ved å bruke en standard **Galleri** kontroll i stedet for varianten av den **fleksible høyden** .

## <a name="key-properties"></a>Nøkkelegenskaper

**[Standard](properties-core.md)**  – elementet eller posten fra datakilden som skal velges i galleriet når appen startes.

**[Elementer](properties-core.md)** – kilden til dataene som vises i en kontroll, for eksempel et galleri, en liste eller et diagram.

**Valgt** – det valgte elementet.

## <a name="additional-properties"></a>Tilleggsegenskaper

**[AccessibleLabel](properties-accessibility.md)** – etiketten til galleriet (ikke elementene i den inneholder) for skjerm lesere. Bør beskrive hva listen over elementer er.

**AllItems** – alle elementene i et galleri, inkludert ekstra kontroll-verdier som er en del av malen i galleriet.

**[BorderColor](properties-color-border.md)** – fargen på kontrollerens kantlinje.

**[BorderStyle](properties-color-border.md)** – om kontrollens kantlinje er satt til **Heltrukket**, **Stiplet**, **Prikket** eller **Ingen**.

**[BorderThickness](properties-color-border.md)** – tykkelsen til kontrollens kantlinje.

**[DisplayMode](properties-core.md)** – om kontrollen tillater brukerinndata (**Rediger**), bare viser data (**Vis**) eller er deaktivert (**Deaktivert**).

**[Fyll](properties-color-border.md)** – bakgrunnsfargen på kontrollen.

**[Høyde](properties-size-location.md)** – avstanden mellom kontrollens øvre og nedre kant.

**ItemAccessibleLabel** – etikett for hvert Galleri element for skjerm lesere. Bør beskrive hva hvert element er.

**NavigationStep** – hvor langt et galleri ruller hvis **ShowNavigation**-egenskapen er satt til **sann** og brukeren velger en navigasjonspil i en av endene av galleriet.

**Velges** – om Galleri elementer kan velges. Når satt til **sann**, identifiserer skjerm lesere galleriet som en valgbar liste, og du velger et element ved å klikke eller trykke på det. Når det er satt til **False**, identifiserer skjerm lesere galleriet som en vanlig liste, og når du klikker eller trykker på et element, merkes det ikke.

**ShowNavigation** – om det vises en pil i hver ende av et galleri slik at en bruker kan bla gjennom elementene i galleriet ved å klikke eller trykke på en pil.

**ShowScrollbar** – om et rullefelt vises når brukeren beveger seg over et galleri.

**Fest** – om når en bruker ruller gjennom et galleri, den automatisk festes slik at det neste elementet vises i sin helhet.

**TemplateFill** – bakgrunnsfargen til et galleri.

**TemplatePadding** – avstanden mellom elementene i et galleri.

**TemplateSize** – høyden på malen for et galleri i vertikal/loddrett retning eller bredden til malen til et galleri i horisontal/vannrett retning.

**Transition** – den visuelle effekten (**Pop**, **Push** eller **None**) når brukeren holder pekeren over et element i et galleri.

**[Synlig](properties-core.md)** – om kontrollen vises eller skjules.

**[Bredde](properties-size-location.md)** – avstanden mellom kontrollens venstre og høyre kant.

**WrapCount** – antall elementer som vises per rad eller kolonne basert på horisontalt eller vertikalt oppsett.

**[X](properties-size-location.md)** – avstanden mellom kontrollens venstre kant og den venstre kanten til kontrollens overordnede beholder (eller skjermen, hvis det ikke finnes noen overordnet beholder).

**[Y](properties-size-location.md)** – avstanden mellom kontrollens øvre kant og den øvre kanten til kontrollens overordnede beholder (eller skjermen, hvis det ikke finnes noen overordnet beholder).

## <a name="related-functions"></a>Relaterte funksjoner

[**Filter**( *DataSource*; *Formula* )](../functions/function-filter-lookup.md)

## <a name="examples"></a>Eksempler

### <a name="show-and-filter-data"></a>Å vise og filtrere data

* [Å vise tekst](control-text-box.md#show-data-in-a-gallery)
* [Å vise bilder](control-image.md#show-a-set-of-images-from-a-data-source)
* [Å filtrere data ved å velge et listealternativ](control-drop-down.md#example)
* [Å filtrere data ved å justere en glidebryter](control-slider.md#example)

### <a name="get-data-from-the-user"></a>Å hente data fra brukeren

* [Å hente tekst](control-text-input.md#collect-data)
* [Å hente bilder](control-add-picture.md#add-images-to-an-image-gallery-control)
* [Å hente fotografier](control-camera.md#example)
* [Å hente lyder](control-microphone.md#example)
* [Å hente tegninger](control-pen-input.md#create-a-set-of-images)

## <a name="accessibility-guidelines"></a>Retningslinjer for tilgjengelighet

### <a name="color-contrast"></a>Fargekontrast

Hvis du skal kunne klikke hvor som helst i et gallerielement for å merke det, må det være tilstrekkelig fargekontrast mellom:

* **[BorderColor](properties-color-border.md)** og fargen utenfor galleriet (hvis det foreligger en kantlinje)
* **[Fyll](properties-color-border.md)** og fargen utenfor galleriet (hvis det ikke foreligger en kantlinje)

### <a name="screen-reader-support"></a>Kundestøtte for skjermlesere

* **[AccessibleLabel](properties-accessibility.md)** bør vises.

    > [!NOTE]
    > Skjerm lesere vil annonsere når elementer i galleriet endres. **AccessibleLabel** nevnes også. Dette gir kontekst til kunngjøringen, og er enda viktigere når det finnes flere gallerier på samme skjerm.

* Bruk **ItemAccessibleLabel** til å sammenfatte innholdet i Galleri elementene når et galleri element inneholder flere kontroller.

* Angi verdien for **valgbar** til **sann** hvis du vil at brukere skal velge et galleri element. Ellers setter du denne verdien til **Usann**.

* Når et galleri element inneholder flere kontroller, kan du bruke **ItemAccessibleLabel** til å gi et sammendrag av innholdet i Galleri elementet.

* Du kan **velge** å angi riktig, avhengig av om brukerne er ment å velge et galleri element.

### <a name="keyboard-support"></a>Tastaturstøtte

* Vurder å angi **ShowScrollbar** til **sann**. Rullefeltet vises ikke på de fleste skjermenhetene før du begynner å rulle.
* Hvis du skal kunne klikke hvor som helst i et gallerielement for å merke det, må det også finnes en måte for tastaturbrukere å merke gallerielementet. Legg for eksempel til en **[knapp](control-button.md)** som har egenskapen **OnSelect** angitt til **Select(Parent)** .

    > [!NOTE]
  > Kontroller utenfor galleriet behandles ikke i tastaturnavigasjonsrekkefølgen i galleriet. **[TabIndex](properties-accessibility.md)** for kontroller i et galleri omfattes. Hvis du vil ha mer informasjon, kan du se [egenskaper for tilgjengelighet](properties-accessibility.md).
