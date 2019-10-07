---
title: 'Kombinasjonsbokskontroll: referanse | Microsoft Docs'
description: Informasjon, inkludert egenskaper og eksempler, om kombinasjonsbokskontrollen
author: fikaradz
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 09/13/2017
ms.author: fikaradz
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: dbbff1f85ccc104a1a0f88c6b9670c45c0528592
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/07/2019
ms.locfileid: "71993488"
---
# <a name="combo-box-control-in-powerapps"></a>Kombinasjonsbokskontroll i PowerApps
En kontroll som gjør det mulig for brukere å foreta valg ut ifra angitte valgmuligheter.  Støtter søk og flervalg.

## <a name="description"></a>Beskrivelse
En **Kombinasjonsbokskontroll** gjør det mulig for deg å søke etter elementer du vil velge.  Dette søket utføres på serversiden i SearchField-egenskapen, slik at ytelsen ikke påvirkes av store datakilder.  

Enkelt- og flervalgsmodus konfigureres via SelectMultiple-egenskapen.

Når du søker etter elementer som du skal velge, kan du for hvert element velge å vise en enkelt dataverdi, to verdier, eller et bilde og to verdier (Person) ved å endre innstillingene for oppsett i Data-ruten.

## <a name="people-picker"></a>Personvelger
For å bruke **Kombinasjonsboks** som personvelger, velger du **Person**-malen i innstillingene for oppsett i Data-ruten, og konfigurerer de relaterte dataegenskapene slik at de vises for personen under.

## <a name="key-properties"></a>Nøkkelegenskaper
**[Elementer](properties-core.md)** – datakilden det kan foretas valg ut ifra.

**DefaultSelectedItems** – de første valgte elementene før brukeren samhandler med kontrollen.

**SelectedItems** – listen over valgte elementer som resultat av brukermedvirkning.

**SelectMultiple** – om brukeren kan velge et enkelt eller flere elementer.

**IsSearchable** – hvorvidt brukeren kan søke etter elementer før vedkommende foretar et valg.

**SearchFields** – datafeltene i datakilden søker når brukeren skriver inn tekst.  Hvis du vil søke etter flere felt, kan du angi ComboBox1.SearchFields = ["MyFirstColumn", "MySecondColumn"]

## <a name="additional-properties"></a>Tilleggsegenskaper
**[AccessibleLabel](properties-accessibility.md)** – etikett for skjermlesere.

**[BorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje.

**[BorderStyle](properties-color-border.md)** – om kontrollens kantlinje er satt til **Heltrukket**, **Stiplet**, **Prikket** eller **Ingen**.

**[BorderThickness](properties-color-border.md)** – tykkelsen til kontrollens kantlinje.

**DisplayFields** – liste over felt som vises for hvert element som returneres av søket.  Enklest å konfigurere via Data-ruten i Alternativer for Egenskaper-fanen.

**[DisplayMode](properties-core.md)** – om kontrollen tillater brukerinndata (**Rediger**), bare viser data (**Vis**) eller er deaktivert (**Deaktivert**).

**[FocusedBorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje når kontrollen er fokusert.

**[FocusedBorderThickness](properties-color-border.md)** – fargen på kontrollens kantlinje når kontrollen er fokusert.

**[Høyde](properties-size-location.md)** – avstanden mellom kontrollens øvre og nedre kant.

**InputTextPlaceholder** – veiledningstekst som vises for sluttbrukere når ingen elementer er valgt.

**OnChange** – hvordan appen responderer når brukeren endrer et utvalg.

**OnNavigate** – hvordan appen responderer når brukeren klikker på et element.

**[OnSelect](properties-core.md)** – hvordan appen responderer når brukeren klikker eller trykker på en kontroll.

**[TabIndex](properties-accessibility.md)** – navigasjonsrekkefølge for tastatur i forhold til andre kontroller.

**[Synlig](properties-core.md)** – om kontrollen vises eller skjules.

**[Bredde](properties-size-location.md)** – avstanden mellom kontrollens venstre og høyre kant.

**[X](properties-size-location.md)** – avstanden mellom kontrollens venstre kant og den venstre kanten til kontrollens overordnede beholder (eller skjermen, hvis det ikke finnes noen overordnet beholder).

**[Y](properties-size-location.md)** – avstanden mellom kontrollens øvre kant og den øvre kanten til kontrollens overordnede beholder (eller skjermen, hvis det ikke finnes noen overordnet beholder).

## <a name="example"></a>Eksempel
1. På **Sett inn** -fanen åpner du **Kontroller** -menyen, og deretter velger du **kombinasjons boks**.  

1. Åpne **Velg en data kilde** -listen (ved siden av **elementer**) i **Egenskaper** -fanen i ruten til høyre, og Legg til eller velg en data kilde.

1. Velg **Rediger** (ved siden av **felt**) på den samme fanen.

1. Åpne den **primære tekst** listen i **data** -ruten, og velg deretter kolonnen som du vil vise i **kombinasjons boks** kontrollen.

1. Velg pil ned for å åpne **kombinasjons boks** -kontrollen mens du holder nede Alt-tasten.

    Kontrollen viser dataene fra kolonnen som du angav i data kilden du angav.
    
1. valg fritt Hvis du vil vise den første posten som standard, kan du angi **DefaultSelectedItems** -egenskapen til dette uttrykket ved *å erstatte data kilden med* navnet på data kilden:

    `First(DataSource)`

## <a name="accessibility-guidelines"></a>Retningslinjer for tilgjengelighet
### <a name="color-contrast"></a>Fargekontrast
Det må være tilstrekkelig fargekontrast mellom:
* **ChevronFill** og **ChevronBackground**
* **ChevronHoverFill** og **ChevronHoverBackground**
* **SelectionColor** og **SelectionFill**
* **SelectionFill** og **[Fyll](properties-color-border.md)**
* **SelectionTagColor** og **SelectionTagFill**

Dette er i tillegg til [kravene for standard fargekontrast](../accessible-apps-color.md).

### <a name="screen-reader-support"></a>Kundestøtte for skjermlesere
* **[AccessibleLabel](properties-accessibility.md)** bør vises.

    > [!NOTE]
  > På berøringsskjermer kan skjermleserbrukere navigere innholdet i kombinasjonsboksen sekvensielt. Kombinasjonsboksen fungerer som en knapp som viser eller skjuler innholdet når valgt.

### <a name="keyboard-support"></a>Tastaturstøtte
* **[TabIndex](properties-accessibility.md)** må være null eller større, slik at tastaturbrukere kan navigere til den.
* Fokusindikatorer må være godt synlige. Bruk **[FocusedBorderColor](properties-color-border.md)** og **[FocusedBorderThickness](properties-color-border.md)** for å oppnå dette.

    > [!NOTE]
  > TAB-tasten navigerer til eller bort fra kombinasjonsboksen. Piltastene navigerer innholdet i kombinasjonsboksen. ESC-tasten lukker rullegardinlisten når den åpnes.
