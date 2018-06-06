---
title: 'Knappekontroll: referanse | Microsoft Docs'
description: Informasjon, inkludert egenskaper og eksempler, om knappekontrollen
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
ms.openlocfilehash: 3bab51ee290d779cd01789f55ee7c5908395537a
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/22/2018
ms.locfileid: "30996372"
---
# <a name="button-control-in-powerapps"></a>Knappekontroll i PowerApps
En kontroll som brukeren kan klikke eller trykke på for å samhandle med appen.

## <a name="description"></a>Beskrivelse
Konfigurer **[OnSelect](properties-core.md)**-egenskapen til en **knappekontroll** for å kjøre én eller flere formler når brukeren klikker eller trykker på kontrollen.

## <a name="key-properties"></a>Nøkkelegenskaper
**[OnSelect](properties-core.md)** – Hvordan appen responderer når brukeren klikker eller trykker på en kontroll.

**[Text](properties-core.md)**  – Tekst som vises på en kontroll eller som brukeren skriver inn i en kontroll.

## <a name="additional-properties"></a>Tilleggsegenskaper
**[Align](properties-text.md)**  – Plasseringen av teksten i forhold til den vannrette midten av kontrollen.

**AutoDisableOnSelect** – Deaktiverer kontrollen automatisk mens **OnSelect**-atferden kjøres.

**[BorderColor](properties-color-border.md)** – Fargen på kontrollens kantlinje.

**[BorderStyle](properties-color-border.md)** – Hvorvidt kontrollens kantlinje er satt til **Solid**, **Dashed**, **Dotted** eller **None**.

**[BorderThickness](properties-color-border.md)** – Tykkelsen på kontrollens kantlinje.

**[FocusedBorderThickness](properties-color-border.md)** – Tykkelsen på kantlinjen for en kontroll når den har tastaturfokus.

**[Color](properties-color-border.md)**  – Fargen på teksten i kontrollen.

**[DisplayMode](properties-core.md)** – Hvorvidt kontrollen tillater brukerinndata (**Edit**), bare viser data (**View**) eller er deaktivert (**Disabled**).

**[DisabledBorderColor](properties-color-border.md)**  – Fargen på kontrollens kantlinje hvis kontrollens **[DisplayMode](properties-core.md)**-egenskap er angitt som **Disabled**.

**[DisabledColor](properties-color-border.md)** – Fargen på kontrollens tekst hvis kontrollens **[DisplayMode](properties-core.md)**-egenskap er angitt som **Deaktivert**.

**[DisabledFill](properties-color-border.md)** – Bakgrunnsfargen på en kontroll hvis kontrollens **[DisplayMode](properties-core.md)**-egenskap er angitt som **Disabled**.

**[Fill](properties-color-border.md)** – Bakgrunnsfargen på kontrollen.

**[Font](properties-text.md)**  – Navnet på skriftserien som teksten vises i.

**[FontWeight](properties-text.md)**  – Tykkelsen på teksten i en kontroll: **Bold**, **Semibold**, **Normal** eller **Lighter**.

**[Height](properties-size-location.md)** – Avstanden mellom kontrollens øvre og nedre kant.

**[HoverBorderColor](properties-color-border.md)**  – Fargen på kontrollens kantlinje når brukeren holder musepekeren på denne kontrollen.

**[HoverColor](properties-color-border.md)** – Fargen på teksten i en kontroll når brukeren holder musepekeren over den.

**[HoverFill](properties-color-border.md)**  – Bakgrunnsfargen for en kontroll når brukeren holder musepekeren over den.

**[Italic](properties-text.md)**  – Hvorvidt teksten i en kontroll er kursiv.

**[PaddingBottom](properties-size-location.md)** – Avstanden mellom teksten i en kontroll og den nederste kanten av kontrollen.

**[PaddingLeft](properties-size-location.md)** – Avstanden mellom teksten i en kontroll og den venstre kanten av kontrollen.

**[PaddingRight](properties-size-location.md)** – Avstanden mellom teksten i en kontroll og den høyre kanten av kontrollen.

**[PaddingTop](properties-size-location.md)** – Avstanden mellom teksten i en kontroll og den øverste kanten av kontrollen.

**Pressed** – *sann* mens en kontroll trykkes på, *usann* hvis ikke.

**[PressedBorderColor](properties-color-border.md)**  – Fargen på kontrollens kantlinje når brukeren trykker eller klikker på kontrollen.

**[PressedColor](properties-color-border.md)** – Fargen på teksten i en kontroll når brukeren trykker eller klikker på kontrollen.

**[PressedFill](properties-color-border.md)** – Bakgrunnsfargen i en kontroll når brukeren trykker eller klikker på kontrollen.

**[RadiusBottomLeft](properties-size-location.md)** – I hvilken grad hjørnet nederst til venstre i en kontroll avrundes.

**[RadiusBottomRight](properties-size-location.md)**  – I hvilken grad hjørnet nederst til høyre i en kontroll avrundes.

**[RadiusTopLeft](properties-size-location.md)**  – I hvilken grad hjørnet øverst til venstre i en kontroll avrundes.

**[RadiusTopRight](properties-size-location.md)**  – I hvilken grad hjørnet øverst til høyre i en kontroll avrundes.

**[Size](properties-text.md)** – Skriftstørrelsen på teksten som vises på en kontroll.

**[Strikethrough](properties-text.md)**  – Hvorvidt det vises en linje gjennom teksten som vises på en kontroll.

**[TabIndex](properties-accessibility.md)** – Tilpasser fanerekkefølgen for kontroller ved kjøretid når den er angitt som en annen verdi enn null.

**[Tooltip](properties-core.md)** – Forklarende tekst som vises når brukeren holder pekeren over en kontroll.

**[Underline](properties-text.md)**  – Hvorvidt det vises en linje under teksten som vises på en kontroll.

**[VerticalAlign](properties-text.md)**  – Plasseringen av tekst på en kontroll i forhold til den loddrette midten av kontrollen.

**[Visible](properties-core.md)** – Hvorvidt kontrollen vises eller skjules.

**[Width](properties-size-location.md)** – Avstanden mellom kontrollens venstre og høyre kant.

**[X](properties-size-location.md)** – Avstanden mellom kontrollens venstre kant og den venstre kanten til kontrollens overordnede beholder (eller skjermbilde, hvis det ikke finnes noen overordnet beholder).

**[Y](properties-size-location.md)** – Avstanden mellom kontrollens øvre kant og den øvre kanten til kontrollens overordnede beholder (eller skjermbilde, hvis det ikke finnes noen overordnet beholder).

## <a name="related-functions"></a>Relaterte funksjoner
**[Navigate( *ScreenName*, *ScreenTransitionValue* )](../functions/function-navigate.md)**

## <a name="examples"></a>Eksempler
### <a name="add-a-basic-formula-to-a-button"></a>Slik legger du til en grunnleggende formel i en knapp
1. Legg til en **[Tekstinndata](control-text-input.md)**-kontroll, og gi den navnet **Source**.
   
    Vet du ikke hvordan du [legger til, gir navn til og konfigurerer en kontroll](../add-configure-controls.md)?
2. Legg til en **Knapp**-kontroll, angi kontrollens **[Text](properties-core.md)**-egenskap til "Add" og angi kontrollens **[OnSelect](properties-core.md)**-egenskap til denne formelen:<br>
   **UpdateContext({Total:Total + Value(Source.Text)})**
   
    Vil du ha mer informasjon om **[UpdateContext](../functions/function-updatecontext.md)**-funksjonen eller [andre funksjoner](../formula-reference.md)?
3. Legg til en **[Etikett](control-text-box.md)**-kontroll, angi kontrollens **[Text](properties-core.md)**-egenskap til **Total** og trykk deretter på **F5**.
4. Slett standardteksten fra **Source**, skriv inn et tall og klikk eller trykk deretter på **Add**.
   
    **[Etikett](control-text-box.md)**-kontrollen viser tallet du skrev inn.
5. Slett tallet fra **Source**, skriv inn et annet tall og klikk eller trykk deretter på **Add**.
   
    **[Etikett](control-text-box.md)**-kontrollen viser summen av de to tallene du skrev inn.
6. (valgfritt) Gjenta det forrige trinnet én eller flere ganger.
7. Hvis du vil returnere til standardarbeidsområdet, trykker du på Esc (eller klikker eller trykker på Lukk-ikonet øverst til høyre).

### <a name="configure-a-button-with-multiple-formulas"></a>Slik konfigurerer du en knapp med flere formler
Legg til en formel som sletter **Tekstinndata**-kontrollen mellom oppføringene.

1. Angi **[HintText](control-text-input.md)**-egenskapen for **Source** til "Enter a number".
2. Angi **[OnSelect](properties-core.md)**-egenskapen for **Add** til denne formelen:
   
    **UpdateContext({Total:Total + Value(Source.Text)});<br>UpdateContext({ClearInput: ""})**
   
    > [!NOTE]
> Adskill flere formler med semikolon «**;**».
3. Angi **[standardegenskapen](properties-core.md)** for **Source** til **ClearInput**.
4. Trykk på **F5**, og test deretter appen ved å legge til flere tall.

### <a name="add-another-button-to-reset-the-total"></a>Slik legger du til en ny knapp for å tilbakestille summen
Legg til en ny knapp for å slette summen mellom beregningene.

1. Legg til enda en **Knapp**-kontroll, angi kontrollens **[Tekst](properties-core.md)**-egenskap til "Clear" og angi kontrollens **[OnSelect](properties-core.md)**-egenskap til denne formelen:
   
    **UpdateContext({Total:0})**
2. Trykk på **F5**, legg til flere tall og klikk eller trykk deretter på **Slett** for å tilbakestille summen.

### <a name="change-a-buttons-appearance"></a>Endre utseendet til en knapp
#### <a name="change-a-buttons-shape"></a>Endre formen på en knapp
PowerApps oppretter som standard en trekantet **knappekontroll** med avrundede hjørner. Du kan utføre grunnleggende endringer til formen av en **Knapp**-kontroll ved å angi kontrollens **[Height](properties-size-location.md)**-, **[Width](properties-size-location.md)**- og **[Radius](properties-size-location.md)**-egenskaper.

> [!NOTE]
> [Ikoner og figurer](control-shapes-icons.md) gir et bredt utvalg av utforminger og kan utføre noen av de samme grunnleggende funksjonene som **Knapp**-kontrollene. **[Ikoner og figurer](control-shapes-icons.md)** har imidlertid ikke en **[Text](properties-core.md)**-egenskap.

1. Legg til en **Knapp**-kontroll, angi kontrollens **[Height](properties-size-location.md)**- og **[Width](properties-size-location.md)**-egenskaper til **300** for å lage en stor, firkantet knapp.
2. Endre egenskapene **[RadiusTopLeft](properties-size-location.md)**, **[RadiusTopRight](properties-size-location.md)**, **[RadiusBottomLeft](properties-size-location.md)** og **[RadiusBottomRight](properties-size-location.md)** for å justere graden av krumming i hvert hjørne. Her ser du noen eksempler på ulike former, og hver av dem starter med en firkantet knapp på 300 x 300 piksler:
   
   * Angi alle fire verdiene for **[Radius](properties-size-location.md)** til **150** for å opprette en sirkel.
   * Angi verdiene for egenskapene **[RadiusTopLeft](properties-size-location.md)** og **[RadiusBottomRight](properties-size-location.md)** til **300** for å opprette en løvformet **knapp**.
   * Angi verdiene for egenskapene **[RadiusTopLeft](properties-size-location.md)** og **[RadiusTopRight](properties-size-location.md)** til **300**, og verdiene for egenskapene **[RadiusBottomLeft](properties-size-location.md)** og **[RadiusBottomRight](properties-size-location.md)** til **100** for å opprette en faneformet knapp.

#### <a name="change-a-buttons-color-when-you-hover-over-it"></a>Endre fargen på en knapp når pekeren holdes over den
Som standard tones fyllfargen til en **Knapp**-kontroll ned med 20 % når du holder pekeren over knappen. Du kan justere atferden ved å endre **[HoverFill](properties-color-border.md)**-egenskapen, som bruker **[ColorFade](../functions/function-colors.md)**-funksjonen. Hvis du angir **[ColorFade](../functions/function-colors.md)**-formelen til et positiv prosenttall, blir fargen lysere når du holder pekeren over knappen, mens et negativ prosenttall gjør fargen mørkere.

* Endre prosentdelen for **[ColorFade](../functions/function-colors.md)** i **[HoverFill](properties-color-border.md)**-egenskapen for én av knappene du opprettet, og se hva som skjer.

Du kan også angi fargen til en **Knapp**-kontroll ved å angi **[HoverFill](properties-color-border.md)**-egenskapen til en formel som inneholder **[ColorValue](../functions/function-colors.md)**-funksjonen i stedet for **[ColorFade](../functions/function-colors.md)**-funksjonen, som i **ColorValue("Red")**.

> [!NOTE]
> Fargeverdien kan være en hvilken som helst CSS-fargedefinisjon, enten et navn eller en heksadesimal verdi.

* Erstatt **[ColorFade](../functions/function-colors.md)**-funksjonen med en **[ColorValue](../functions/function-colors.md)**-funksjon i én knappene du opprettet, og se hva som skjer.

