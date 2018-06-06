---
title: 'Glidebryter-kontrollen: referanse | Microsoft Docs'
description: Informasjon om glidebryteren, inkludert egenskaper og eksempler
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
ms.openlocfilehash: dc10ac44c1c14f182c39176a6b0216f3ede3816d
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/22/2018
ms.locfileid: "30997067"
---
# <a name="slider-control-in-powerapps"></a>Glidebryter-kontrollen i PowerApps
En kontroll som lar brukeren angi en verdi ved å dra i et håndtak.

## <a name="description"></a>Beskrivelse
Brukeren kan angi en verdi mellom en minimumsverdi og en maksimumsverdi som du angir, ved å dra håndtaket til en glidebryter i retningen venstre-høyre eller opp-ned, avhengig av hva du velger.

## <a name="key-properties"></a>Nøkkelegenskaper
**[Default](properties-core.md)** – startverdien for en kontroll før den er endret av brukeren.

**Max** – den maksimale verdien som brukeren kan angi for en glidebryter eller en vurdering.

**Min** – minimalverdien som brukeren kan angi for en glidebryter.

**[Value](properties-core.md)** – verdien til en inndatakontroll.

## <a name="additional-properties"></a>Tilleggsegenskaper
**[BorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje.

**[BorderStyle](properties-color-border.md)** – om kontrollens kantlinje er **Heltrukket**, **Stiplet**, **Prikket** eller **Ingen**.

**[BorderThickness](properties-color-border.md)** – tykkelsen til kontrollens kantlinje.

**[FocusedBorderThickness](properties-color-border.md)**  – tykkelsen på kontrollens kantlinje når den har tastaturfokus.

**[DisplayMode](properties-core.md)** – om kontrollen tillater brukerinndata (**Edit**), bare viser data (**View**) eller er deaktivert (**Disabled**).

**[DisabledBorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje hvis kontrollens **[DisplayMode](properties-core.md)**-egenskap er angitt som **Disabled**.

**HandleActiveFill** – fargen på håndtaket for en glidebryter mens brukeren endrer verdien.

**HandleFill** – fargen på håndtaket (elementet som endrer posisjon) i en veksleknapp eller glidebryter.

**HandleHoverFill** – fargen på håndtaket i en glidebryter når brukeren holder musepekeren på den.

**[Height](properties-size-location.md)** – avstanden mellom kontrollens øvre og nedre kant.

**[HoverBorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje når brukeren holder musepekeren på denne kontrollen.

**Layout** – om brukeren ruller gjennom et galleri eller justerer en glidebryter fra topp til bunn (**loddrett**) eller fra venstre mot høyre (**vannrett**).

**[OnChange](properties-core.md)** – hvordan appen reagerer når brukeren endrer verdien på en kontroll (ved å for eksempel justere en glidebryter).

**[OnSelect](properties-core.md)** – hvordan appen reagerer når brukeren klikker eller trykker på en kontroll.

**[PressedBorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje når brukeren trykker eller klikker på kontrollen.

**RailFill** – bakgrunnsfargen for rektangelet i vekslekontrollen når verdien er **usann**, eller fargen på linjen til høyre for håndtaket i en glidebryter.

**RailFill** – bakgrunnsfargen for rektangelet i vekslekontrollen når verdien er **usann** eller fargen på linjen til høyre for håndtaket i en glidebryterkontroll når du peker over en vekslekontroll eller en glidebryter.

**ReadOnly** – om en bruker kan endre verdien til en glidebryter eller vurderingskontroll.

**[Reset](properties-core.md)** – om en kontroll tilbakestilles til standardverdien.

**ShowValue** – om verdien til glidebryteren eller vurderingen vises når en bruker endrer verdien eller holder musepekeren over kontrollen.

**[TabIndex](properties-accessibility.md)** – tilpasser kategorirekkefølgen ved kjøretid når den ikke er angitt som null.

**[Tooltip](properties-core.md)** – forklarende tekst som vises når brukeren holder pekeren over en kontroll.

**ValueFill** – bakgrunnsfargen for rektangelet i vekslekontrollen når verdien er **sann** eller fargen på linjen til venstre for håndtaket i en glidebryterkontroll.

**ValueHoverFill** – når du holder musepekeren over en vekslekontroll eller en glidebryter, bakgrunnsfargen for rektangelet i en vekslekontroll når verdien er **sann** eller fargen på linjen til venstre for håndtaket i en glidebryterkontroll.

**[Visible](properties-core.md)** – om kontrollen vises eller skjules.

**[Width](properties-size-location.md)** – avstanden mellom venstrekanten og høyrekanten til en kontroll.

**[X](properties-size-location.md)** – avstanden mellom kontrollens venstre kant og den venstre kanten til kontrollens overordnede beholder (eller skjermen, hvis det ikke finnes noen overordnet beholder).

**[Y](properties-size-location.md)** – avstanden mellom kontrollens øvre kant og den øvre kanten til kontrollens overordnede beholder (eller skjermen, hvis det ikke finnes noen overordnet beholder).

## <a name="related-functions"></a>Relaterte funksjoner
[**Sum**( *Value1*, *Value2* )](../functions/function-aggregates.md)

## <a name="example"></a>Eksempel
1. Legg til en knapp, og angi knappens **[OnSelect](properties-core.md)**-egenskap til denne formelen:
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
8. Trykk på Esc for å gå tilbake til standardarbeidsområdet.

