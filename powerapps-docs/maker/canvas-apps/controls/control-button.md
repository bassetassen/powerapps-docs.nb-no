---
title: 'Knapp-kontroll: referanse | Microsoft Docs'
description: Informasjon, inkludert egenskaper og eksempler, om Knapp-kontrollen
author: fikaradz
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.date: 10/25/2016
ms.author: fikaradz
ms.reviewer: anneta
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: d4cde32e52240e04a3499444d2c1325d0105a945
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/24/2018
ms.locfileid: "42855431"
---
# <a name="button-control-in-powerapps"></a>Knappkontroll i PowerApps
En kontroll som brukeren kan klikke eller trykke på for å samhandle med appen.

## <a name="description"></a>Beskrivelse
Konfigurer **[OnSelect](properties-core.md)**-egenskapen til en **Knapp**-kontroll for å kjøre én eller flere formler når brukeren klikker eller trykker på kontrollen.

## <a name="key-properties"></a>Nøkkelegenskaper
**[OnSelect](properties-core.md)** – hvordan appen responderer når brukeren klikker eller trykker på en kontroll.

**[Text](properties-core.md)**  – Tekst som vises på en kontroll eller som brukeren skriver inn i en kontroll.

## <a name="additional-properties"></a>Tilleggsegenskaper
**[Align](properties-text.md)**  – Plasseringen av teksten i forhold til den vannrette midten av kontrollen.

**AutoDisableOnSelect** – Deaktiverer kontrollen automatisk mens **OnSelect**-atferden kjøres.

**[BorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje.

**[BorderStyle](properties-color-border.md)** – om kontrollens kantlinje er satt til **Heltrukket**, **Stiplet**, **Prikket** eller **Ingen**.

**[BorderThickness](properties-color-border.md)** – tykkelsen til kontrollens kantlinje.

**[Farge](properties-color-border.md)** – fargen på teksten i kontrollen.

**[DisplayMode](properties-core.md)** – om kontrollen tillater brukerinndata (**Rediger**), bare viser data (**Vis**) eller er deaktivert (**Deaktivert**).

**[DisabledBorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje hvis kontrollens **[DisplayMode](properties-core.md)**-egenskap er angitt til **Deaktivert**.

**[DisabledColor](properties-color-border.md)** – fargen på kontrollens tekst hvis kontrollens **[DisplayMode](properties-core.md)**-egenskap er angitt som **Deaktivert**.

**[DisabledFill](properties-color-border.md)** – bakgrunnsfargen på en kontroll hvis **[DisplayMode](properties-core.md)**-egenskapen er angitt som **Deaktivert**.

**[FocusedBorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje når kontrollen er fokusert.

**[FocusedBorderThickness](properties-color-border.md)** – fargen på kontrollens kantlinje når kontrollen er fokusert.

**[Fyll](properties-color-border.md)** – bakgrunnsfargen på kontrollen.

**[Skrift](properties-text.md)** – navnet på skriftserien som teksten vises i.

**[FontWeight](properties-text.md)** – tykkelsen på teksten i en kontroll: **Fet**, **Halvfet**, **Normal** eller **Lysere**.

**[Høyde](properties-size-location.md)** – avstanden mellom kontrollens øvre og nedre kant.

**[HoverBorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje når brukeren holder musepekeren på denne kontrollen.

**[HoverColor](properties-color-border.md)** – Fargen på teksten i en kontroll når brukeren holder musepekeren over den.

**[HoverFill](properties-color-border.md)** – bakgrunnsfargen for en kontroll når brukeren holder musepekeren over den.

**[Italic](properties-text.md)**  – Hvorvidt teksten i en kontroll er kursiv.

**[PaddingBottom](properties-size-location.md)** – Avstanden mellom teksten i en kontroll og den nederste kanten av kontrollen.

**[PaddingLeft](properties-size-location.md)** – avstanden mellom teksten i en kontroll og den venstre kanten av kontrollen.

**[PaddingRight](properties-size-location.md)** – avstanden mellom teksten i en kontroll og den høyre kanten av kontrollen.

**[PaddingTop](properties-size-location.md)** – Avstanden mellom teksten i en kontroll og den øverste kanten av kontrollen.

**Pressed** – *sann* mens en kontroll trykkes på, *usann* hvis ikke.

**[PressedBorderColor](properties-color-border.md)**  – Fargen på kontrollens kantlinje når brukeren trykker eller klikker på kontrollen.

**[PressedColor](properties-color-border.md)** – fargen på teksten i en kontroll når brukeren trykker eller klikker på kontrollen.

**[PressedFill](properties-color-border.md)** – bakgrunnsfargen i en kontroll når brukeren trykker eller klikker på kontrollen.

**[RadiusBottomLeft](properties-size-location.md)** – i hvilken grad hjørnet nederst til venstre i en kontroll avrundes.

**[RadiusBottomRight](properties-size-location.md)**  – i hvilken grad hjørnet nederst til høyre i en kontroll avrundes.

**[RadiusTopLeft](properties-size-location.md)** – i hvilken grad hjørnet øverst til venstre i en kontroll avrundes.

**[RadiusTopRight](properties-size-location.md)**  – I hvilken grad hjørnet øverst til høyre i en kontroll avrundes.

**[Size](properties-text.md)** – skriftstørrelsen på teksten som vises på en kontroll.

**[Strikethrough](properties-text.md)** – om det vises en linje gjennom teksten som vises på en kontroll.

**[TabIndex](properties-accessibility.md)** – navigasjonsrekkefølge for tastatur i forhold til andre kontroller.

**[Verktøytips](properties-core.md)** – forklarende tekst som vises når brukeren holder pekeren over en kontroll.

**[Underline](properties-text.md)**  – Hvorvidt det vises en linje under teksten som vises på en kontroll.

**[VerticalAlign](properties-text.md)** – plasseringen av tekst i en kontroll i forhold til det vertikale midtpunktet i kontrollen.

**[Visible](properties-core.md)** – om kontrollen vises eller skjules.

**[Bredde](properties-size-location.md)** – avstanden mellom kontrollens venstre og høyre kant.

**[X](properties-size-location.md)** – avstanden mellom kontrollens venstre kant og den venstre kanten til kontrollens overordnede beholder (eller skjermen, hvis det ikke finnes noen overordnet beholder).

**[Y](properties-size-location.md)** – avstanden mellom kontrollens øvre kant og den øvre kanten til kontrollens overordnede beholder (eller skjermen, hvis det ikke finnes noen overordnet beholder).

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

1. Angi **[HintText](control-text-input.md)**-egenskapen for **Kilde** til «Sett inn et tall».
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
PowerApps oppretter som standard en trekantet **Knapp**-kontroll med avrundede hjørner. Du kan utføre grunnleggende endringer til formen av en **Knapp**-kontroll ved å angi kontrollens **[Height](properties-size-location.md)**-, **[Width](properties-size-location.md)**- og **[Radius](properties-size-location.md)**-egenskaper.

> [!NOTE]
> [Ikoner og figurer](control-shapes-icons.md) gir et bredt utvalg av utforminger og kan utføre noen av de samme grunnleggende funksjonene som **Knapp**-kontrollene. **[Ikoner og figurer](control-shapes-icons.md)** har imidlertid ikke en **[Text](properties-core.md)**-egenskap.

1. Legg til en **Knapp**-kontroll, angi kontrollens **[Height](properties-size-location.md)**- og **[Width](properties-size-location.md)**-egenskaper til **300** for å lage en stor, firkantet knapp.
2. Endre egenskapene **[RadiusTopLeft](properties-size-location.md)**, **[RadiusTopRight](properties-size-location.md)**, **[RadiusBottomLeft](properties-size-location.md)** og **[RadiusBottomRight](properties-size-location.md)** for å justere graden av krumming i hvert hjørne. Her ser du noen eksempler på ulike figurer, hver av dem starter med en firkantet knapp å 300 x 300 piksler:
   
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


## <a name="accessibility-guidelines"></a>Retningslinjer for tilgjengelighet
### <a name="color-contrast"></a>Fargekontrast
* [Standardkrav for fargekontrast](../accessible-apps-color.md) gjelder.

### <a name="screen-reader-support"></a>Kundestøtte for skjermlesere
* **[Tekst](properties-core.md)** må foreligge.

### <a name="keyboard-support"></a>Tastaturstøtte
* **[TabIndex](properties-accessibility.md)** må være null eller større, slik at tastaturbrukere kan navigere til den.
* Fokusindikatorer må være godt synlige. Bruk **[FocusedBorderColor](properties-color-border.md)** og **[FocusedBorderThickness](properties-color-border.md)** for å oppnå dette.
 
