---
title: 'Glidebryter-kontrollen: referanse | Microsoft Docs'
description: Informasjon om glidebryteren, inkludert egenskaper og eksempler
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
ms.openlocfilehash: 198275ef72129b17cbf73a5f4eb47fd342de3b24
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/23/2019
ms.locfileid: "61548758"
---
# <a name="slider-control-in-powerapps"></a>Glidebryter-kontrollen i PowerApps
En kontroll som lar brukeren angi en verdi ved å dra i et håndtak.

## <a name="description"></a>Beskrivelse
Brukeren kan angi en verdi mellom en minimumsverdi og en maksimumsverdi som du angir, ved å dra håndtaket til en glidebryter i retningen venstre-høyre eller opp-ned, avhengig av hva du velger.

## <a name="key-properties"></a>Nøkkelegenskaper
**[Default](properties-core.md)** – Startverdien for en kontroll før den endres av brukeren.

**Max** – den maksimale verdien som brukeren kan angi for en glidebryter eller en vurdering.

**Min** – minimumsverdien som brukeren kan angi for en glidebryter.

**[Value](properties-core.md)** – verdien til en inndatakontroll.

## <a name="additional-properties"></a>Tilleggsegenskaper
**[AccessibleLabel](properties-accessibility.md)** – etikett for skjermlesere.

**[BorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje.

**[BorderStyle](properties-color-border.md)** – om kontrollens kantlinje er satt til **Heltrukket**, **Stiplet**, **Prikket** eller **Ingen**.

**[BorderThickness](properties-color-border.md)** – tykkelsen til kontrollens kantlinje.

**[DisplayMode](properties-core.md)** – om kontrollen tillater brukerinndata (**Rediger**), bare viser data (**Vis**) eller er deaktivert (**Deaktivert**).

**[DisabledBorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje hvis kontrollens **[DisplayMode](properties-core.md)**-egenskap er angitt til **Deaktivert**.

**[FocusedBorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje når kontrollen er fokusert.

**[FocusedBorderThickness](properties-color-border.md)** – fargen på kontrollens kantlinje når kontrollen er fokusert.

**HandleActiveFill** – fargen på håndtaket for en glidebryter mens brukeren endrer verdien.

**HandleFill** – fargen på håndtaket (elementet som endrer posisjon) i en veksleknapp eller glidebryter.

**HandleHoverFill** – fargen på håndtaket i en glidebryter når brukeren holder musepekeren på den.

**HandleSize** – diameteren på håndtaket.

**[Høyde](properties-size-location.md)** – avstanden mellom kontrollens øvre og nedre kant.

**[HoverBorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje når brukeren holder musepekeren på denne kontrollen.

**Layout** – om brukeren ruller gjennom et galleri eller justerer en glidebryter fra topp til bunn (**loddrett**) eller fra venstre mot høyre (**vannrett**).

**[OnChange](properties-core.md)** – hvordan appen reagerer når brukeren endrer verdien på en kontroll (ved å for eksempel justere en glidebryter).

**[OnSelect](properties-core.md)** – hvordan appen reagerer når brukeren klikker eller trykker på en kontroll.

**[PressedBorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje når brukeren trykker eller klikker på kontrollen.

**RailFill** – bakgrunnsfargen for rektangelet i vekslekontrollen når verdien er **usann**, eller fargen på linjen til høyre for håndtaket i en glidebryter.

**RailFill** – bakgrunnsfargen for rektangelet i vekslekontrollen når verdien er **usann** eller fargen på linjen til høyre for håndtaket i en glidebryterkontroll når du peker over en vekslekontroll eller en glidebryter.

**ReadOnly** – om en bruker kan endre verdien til en glidebryter eller vurderingskontroll.

**[Reset](properties-core.md)** – Hvorvidt en kontroll tilbakestilles til standardverdien.

**ShowValue** – Om glidebryterens eller vurderingens verdi vises når en bruker endrer verdien eller holder musepekeren over kontrollen.

**[TabIndex](properties-accessibility.md)** – navigasjonsrekkefølge for tastatur i forhold til andre kontroller.

**[Verktøytips](properties-core.md)** – forklarende tekst som vises når brukeren holder pekeren over en kontroll.

**ValueFill** – bakgrunnsfargen for rektangelet i vekslekontrollen når verdien er **sann** eller fargen på linjen til venstre for håndtaket i en glidebryterkontroll.

**ValueHoverFill** – når du holder musepekeren over en vekslekontroll eller en glidebryter, bakgrunnsfargen for rektangelet i en vekslekontroll når verdien er **sann** eller fargen på linjen til venstre for håndtaket i en glidebryterkontroll.

**[Synlig](properties-core.md)** – om kontrollen vises eller skjules.

**[Bredde](properties-size-location.md)** – avstanden mellom kontrollens venstre og høyre kant.

**[X](properties-size-location.md)** – avstanden mellom kontrollens venstre kant og den venstre kanten til kontrollens overordnede beholder (eller skjermen, hvis det ikke finnes noen overordnet beholder).

**[Y](properties-size-location.md)** – avstanden mellom kontrollens øvre kant og den øvre kanten til kontrollens overordnede beholder (eller skjermen, hvis det ikke finnes noen overordnet beholder).

## <a name="related-functions"></a>Relaterte funksjoner
[**Sum**( *Value1*, *Value2* )](../functions/function-aggregates.md)

## <a name="example"></a>Eksempel
1. Legg til en knapp, og angi **[OnSelect](properties-core.md)**-egenskapen til denne formelen:
   <br>**ClearCollect(CityPopulations, {City:"London", Country:"United Kingdom", Population:8615000}, {City:"Berlin", Country:"Germany", Population:3562000}, {City:"Madrid", Country:"Spain", Population:3165000}, {City:"Rome", Country:"Italy", Population:2874000}, {City:"Paris", Country:"France", Population:2273000}, {City:"Hamburg", Country:"Germany", Population:1760000}, {City:"Barcelona", Country:"Spain", Population:1602000}, {City:"Munich", Country:"Germany", Population:1494000}, {City:"Milan", Country:"Italy", Population:1344000})**
   
    Vet du ikke hvordan du [legger til, gir navn til og konfigurerer en kontroll](../add-configure-controls.md)?
   
    Vil du ha mer informasjon om **[ClearCollect](../functions/function-clear-collect-clearcollect.md)**-funksjonen eller [andre funksjoner](../formula-reference.md)?
2. Trykk på F5, velg knappen, og trykk deretter på ESC.
3. Legg til en glidebryter, flytt den under knappen og gi glidebryteren navnet **MinPopulation**.
4. Angi glidebryterens **Max**-egenskap som **5000000** og **Min**-egenskap som **1000000**.
5. Legg til et tekstgalleri i loddrett/stående retning, flytt det nedenfor glidebryteren, og angi galleriets **[Items](properties-core.md)**-egenskap til denne formelen:<br>
   **Filter(CityPopulations, Population > MinPopulation)**
6. Angi **[Text](properties-core.md)**-egenskapen til den øverste etiketten i det første elementet i galleriet som **ThisItem.City**, og angi **[Text](properties-core.md)**-egenskapen til den nederste etiketten til denne formelen:<br> **Text(ThisItem.Population, "##,###")**
7. Trykk på F5, og juster deretter **MinPopulation** til å bare vise byer som har et innbyggertall som er større enn verdien du angir.
8. Trykk på ESC for å gå tilbake til standardarbeidsområdet.


## <a name="accessibility-guidelines"></a>Retningslinjer for tilgjengelighet
### <a name="color-contrast"></a>Fargekontrast
Det må være tilstrekkelig fargekontrast mellom:
* **ValueFill** og **RailFill**
* **ValueHoverFill** og **RailHoverFill**
* **[FokusertGrenseFarge](properties-color-border.md)** og farge utenfor kontrollen
* **ValueFill** og bakgrunnsfarge
* **RailFill** og bakgrunnsfarge
* **ValueHoverFill** og bakgrunnsfarge
* **RailHoverFill** og bakgrunnsfarge

### <a name="screen-reader-support"></a>Kundestøtte for skjermlesere
* **[AccessibleLabel](properties-accessibility.md)** bør vises.

### <a name="keyboard-support"></a>Tastaturstøtte
* **[TabIndex](properties-accessibility.md)** må være null eller større, slik at tastaturbrukere kan navigere til den.
* Fokusindikatorer må være godt synlige. Bruk **[FocusedBorderColor](properties-color-border.md)** og **[FocusedBorderThickness](properties-color-border.md)** for å oppnå dette.
* Glidebryterens verdi må vises når du samhandler med tastaturet. Dette kan oppnås ved bruk av én av disse metodene:
    * Angi **ShowValue** til **sann**.
    * Legge til en **[etikett](control-text-box.md)** ved siden av glidebryteren. Angi etikettens **[tekst](properties-core.md)** til glidebryterens **[verdi](properties-core.md)**.
