---
title: 'HTML-tekstkontroll: referanse | Microsoft Docs'
description: Informasjon om HTML-tekstkontrollen, inkludert egenskaper og eksempler
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
ms.openlocfilehash: 965c779a752d0bfd864a06d5fa886b0187839123
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/24/2018
ms.locfileid: "42836897"
---
# <a name="html-text-control-in-powerapps"></a>HTML-tekstkontrollen i PowerApps
En boks som viser tekst og konverterer HTML-koder til formatering.

## <a name="description"></a>Beskrivelse
En **HTML-tekst**-kontroll viser ikke bare ren tekst og tall, men konverterer også HTML-koder, for eksempel harde mellomrom.

## <a name="key-properties"></a>Nøkkelegenskaper
**[Farge](properties-color-border.md)** – fargen på teksten i kontrollen.

**[Skrift](properties-text.md)** – navnet på skriftserien som teksten vises i.

**HTMLText** – teksten som vises i en kontroll for HTML-tekst, og som kan inneholde HTML-koder.

## <a name="additional-properties"></a>Tilleggsegenskaper
**[BorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje.

**[BorderStyle](properties-color-border.md)** – om kontrollens kantlinje er satt til **Heltrukket**, **Stiplet**, **Prikket** eller **Ingen**.

**[BorderThickness](properties-color-border.md)** – tykkelsen til kontrollens kantlinje.

**[DisplayMode](properties-core.md)** – om kontrollen tillater brukerinndata (**Rediger**), bare viser data (**Vis**) eller er deaktivert (**Deaktivert**).

**[DisabledBorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje hvis kontrollens **[DisplayMode](properties-core.md)**-egenskap er angitt som **Deaktivert**.

**[DisabledFill](properties-color-border.md)** – bakgrunnsfargen på en kontroll hvis **[DisplayMode](properties-core.md)**-egenskapen er angitt som **Deaktivert**.

**[Fyll](properties-color-border.md)** – bakgrunnsfargen på kontrollen.

**[Høyde](properties-size-location.md)** – avstanden mellom kontrollens øvre og nedre kant.

**[HoverBorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje når brukeren holder musepekeren på denne kontrollen.

**[OnSelect](properties-core.md)** – hvordan appen responderer når brukeren klikker eller trykker på en kontroll.

**[PaddingBottom](properties-size-location.md)** – avstanden mellom teksten i en kontroll og den nederste kanten av kontrollen.

**[PaddingLeft](properties-size-location.md)** – avstanden mellom teksten i en kontroll og den venstre kanten av kontrollen.

**[PaddingRight](properties-size-location.md)** – avstanden mellom teksten i en kontroll og den høyre kanten av kontrollen.

**[PaddingTop](properties-size-location.md)** – avstanden mellom teksten i en kontroll og den øverste kanten av kontrollen.

**[Størrelse](properties-text.md)** – skriftstørrelsen på teksten som vises på en kontroll.

**[Verktøytips](properties-core.md)** – forklarende tekst som vises når brukeren holder pekeren over en kontroll.

**[Synlig](properties-core.md)** – om kontrollen vises eller skjules.

**[Bredde](properties-size-location.md)** – avstanden mellom kontrollens venstre og høyre kant.

**[X](properties-size-location.md)** – avstanden mellom kontrollens venstre kant og den venstre kanten til kontrollens overordnede beholder (eller skjermen, hvis det ikke finnes noen overordnet beholder).

**[Y](properties-size-location.md)** – avstanden mellom kontrollens øvre kant og den øvre kanten til kontrollens overordnede beholder (eller skjermen, hvis det ikke finnes noen overordnet beholder).

## <a name="related-functions"></a>Relaterte funksjoner
[**Find**( *FindString*, *WithinString* )](../functions/function-find.md)

## <a name="example"></a>Eksempel
1. Legg til en **[Etikett](control-text-box.md)**-kontroll, kalt **Kilde**, og angi **[Tekst](properties-core.md)**-egenskapen til denne strengen:

\<p > Vi har gjort en uvanlig \&nbsp; \&quot; dyp \&quot; globalisering og lokalisering. \<p>

Vet du ikke hvordan du [legger til, gir navn til og konfigurerer en kontroll](../add-configure-controls.md)?

1. Legg til en **HTML-tekst**-kontroll, og angi dens **HTMLText**-egenskap til denne verdien:<br>
   **Source.Text**
   
     **HTML-tekst**-kontrollen viser den samme teksten som **[Etikett](control-text-box.md)**-kontrollen, men konverterer kodene til de aktuelle tegnene.


## <a name="accessibility-guidelines"></a>Retningslinjer for tilgjengelighet
**HTML-tekst** er ikke ment å være interaktiv. Den bør bare brukes for tekstvisning.

### <a name="color-contrast"></a>Fargekontrast
Det må være tilstrekkelig fargekontrast mellom:
* **[Farge](properties-color-border.md)** og **[Fyll](properties-color-border.md)**
* Tekst med egendefinerte farger og bakgrunner

### <a name="screen-reader-support"></a>Kundestøtte for skjermlesere
* **HtmlText** må være til stede.

### <a name="keyboard-support"></a>Tastaturstøtte
* **HtmlText** kan ikke inneholde interaktive elementer som `<button>`, `<a>` eller `<input>`. **[TabIndex](properties-accessibility.md)**-systemet i PowerApps tar ikke hensyn til elementene i **HtmlText**.
