---
title: 'Galleri-kontrollen: referanse | Microsoft Docs'
description: Informasjon om Galleri-kontrollen, inkludert egenskaper og eksempler
author: fikaradz
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 05/25/2017
ms.author: fikaradz
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 710bc4a11e4de9921e0efa077cb0e18f58f09cb5
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/24/2018
ms.locfileid: "42831508"
---
# <a name="gallery-control-in-powerapps"></a>Galleri-kontrollen i PowerApps
En kontroll som inneholder andre kontroller og viser et datasett.

## <a name="description"></a>Beskrivelse
En **Galleri**-kontroll kan vise flere poster fra en datakilde, og hver post kan inneholde flere typer data. En **Galleri**-kontroll kan vise flere kontakter for hvert element og kontaktinformasjon for hver kontakt, deriblant et navn, en postadresse og et telefonnummer. Hvert felt vises i en separat kontroll i **Galleri**-kontrollen, og du kan konfigurere disse kontrollene i malen. Malen vises som det første elementet i galleriet, i den venstre kanten av en **Galleri**-kontroll i vannrett/liggende retning og øverst i en **Galleri**-kontroll i loddrett/stående retning. Eventuelle endringer du gjør i malen, gjenspeiles i hele **Galleri**-kontrollen.

Forhåndsdefinerte maler er tilgjengelig for å for å vise bilde eller tekst og et galleri for elementer med variabel høyde.

## <a name="key-properties"></a>Nøkkelegenskaper
**[Standard](properties-core.md)**  – elementet eller posten fra datakilden som skal velges i galleriet når appen startes.

**[Elementer](properties-core.md)** – kilden til dataene som vises i en kontroll, for eksempel et galleri, en liste eller et diagram.

**Valgt** – det valgte elementet.

## <a name="additional-properties"></a>Tilleggsegenskaper
**[AccessibleLabel](properties-accessibility.md)** – etikett for skjermlesere. Bør beskrive hva listen over elementer er.

**AllItems** – alle elementene i et galleri, inkludert ekstra kontroll-verdier som er en del av malen i galleriet.

**[BorderColor](properties-color-border.md)** – fargen på kontrollerens kantlinje.

**[BorderStyle](properties-color-border.md)** – om kontrollens kantlinje er satt til **Heltrukket**, **Stiplet**, **Prikket** eller **Ingen**.

**[BorderThickness](properties-color-border.md)** – tykkelsen til kontrollens kantlinje.

**[DisplayMode](properties-core.md)** – om kontrollen tillater brukerinndata (**Rediger**), bare viser data (**Vis**) eller er deaktivert (**Deaktivert**).

**[Fyll](properties-color-border.md)** – bakgrunnsfargen på kontrollen.

**[Høyde](properties-size-location.md)** – avstanden mellom kontrollens øvre og nedre kant.

**Oppsett** – om brukeren ruller gjennom et galleri eller justerer en glidebryteren fra topp til bunn (**loddrett**) eller fra venstre mot høyre (**vannrett**).

**NavigationStep** – hvor langt et galleri ruller hvis **ShowNavigation**-egenskapen er satt til **sann** og brukeren velger en navigasjonspil i en av endene av galleriet.

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
[**Filter**( *DataSource*, *Formula* )](../functions/function-filter-lookup.md)

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
  > Skjermlesere kunngjør når elementer i galleriet endres. **AccessibleLabel** nevnes også. Dette gir kontekst til kunngjøringen, og er enda viktigere når det finnes flere gallerier på samme skjerm.

### <a name="keyboard-support"></a>Tastaturstøtte
* Vurder å angi **ShowScrollbar** til **sann**. Rullefeltet vises ikke på de fleste skjermenhetene før du begynner å rulle.
* Hvis du skal kunne klikke hvor som helst i et gallerielement for å merke det, må det også finnes en måte for tastaturbrukere å merke gallerielementet. Legg for eksempel til en **[knapp](control-button.md)** som har egenskapen **OnSelect** angitt til **Select(Parent)**.

    > [!NOTE]
  > Kontroller utenfor galleriet behandles ikke i tastaturnavigasjonsrekkefølgen i galleriet. **[TabIndex](properties-accessibility.md)** for kontroller i et galleri omfattes. Hvis du vil ha mer informasjon, kan du se [egenskaper for tilgjengelighet](properties-accessibility.md).
