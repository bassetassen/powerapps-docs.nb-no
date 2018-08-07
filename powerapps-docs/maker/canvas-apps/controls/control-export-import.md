---
title: Kontrollene Eksporter og Import | Microsoft Docs
description: Informasjon om kontrollene Eksporter og Import, inkludert egenskaper og eksempler
author: fikaradz
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 10/25/2016
ms.author: fikaradz
ms.openlocfilehash: 9eb0cf33c4bac3553592971409f7c52f199b368b
ms.sourcegitcommit: 0f6d7bb9e524202c065b9a7ef92a7f54bdc4bc7c
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/07/2018
ms.locfileid: "39017299"
---
# <a name="export-control-and-import-control-in-powerapps"></a>Kontrollene Eksporter og Import i PowerApps
Kontroller for å eksportere data til en lokal fil og deretter importere dataene til en annen app i PowerApps.

## <a name="description"></a>Beskrivelse
Hvis du vil opprette mer enn én app som bruker de samme dataene, men ikke dele disse dataene utenfor disse appene, kan du eksportere den og importere dem ved hjelp av en **Eksporter**-kontroll og en **Import**-kontroll. Når du eksporterer data, oppretter du en komprimert fil som du kan kopiere til en annen maskin, men du kan ikke lese den i et annet program enn PowerApps.

## <a name="warning"></a>Advarsel
Aktivering av denne funksjonaliteten i appen din kan føre til sikkerhetsproblemer og datalekkasje.  Det anbefales å opplyse brukerne om å bare importere kjente og pålitelige filer og eksportere bare data som ikke er konfidensiell eller sensitiv.

## <a name="key-properties"></a>Nøkkelegenskaper
**Data** – navnet på en samling som du vil eksportere til en lokal fil.

* **Data**-egenskapen er tilgjengelig for en **Eksporter**-kontroll, men ikke for en **Import**-kontroll.

**[OnSelect](properties-core.md)** – hvordan appen reagerer når brukeren klikker eller trykker på en kontroll.

## <a name="additional-properties"></a>Tilleggsegenskaper
**[Align](properties-text.md)** – plasseringen av teksten i forhold til den vannrette midten av kontrollen.

**[BorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje.

**[BorderStyle](properties-color-border.md)** – om kontrollens kantlinje er satt til **Heltrukket**, **Stiplet**, **Prikket** eller **Ingen**.

**[BorderThickness](properties-color-border.md)** – tykkelsen til kontrollens kantlinje.

**[Farge](properties-color-border.md)** – fargen på teksten i kontrollen.

**[DisplayMode](properties-core.md)** – om kontrollen tillater brukerinndata (**Rediger**), bare viser data (**Vis**) eller er deaktivert (**Deaktivert**).

**[DisabledBorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje hvis kontrollens **[DisplayMode](properties-core.md)**-egenskap er angitt til **Deaktivert**.

**[DisabledColor](properties-color-border.md)** – fargen på kontrollens tekst hvis kontrollens **[DisplayMode](properties-core.md)**-egenskap er angitt som **Deaktivert**.

**[DisabledFill](properties-color-border.md)** – bakgrunnsfargen på en kontroll hvis **[DisplayMode](properties-core.md)**-egenskapen er angitt som **Deaktivert**.

**[Fyll](properties-color-border.md)** – bakgrunnsfargen på kontrollen.

**[FocusedBorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje når kontrollen er fokusert.

**[FocusedBorderThickness](properties-color-border.md)** – fargen på kontrollens kantlinje når kontrollen er fokusert.

**[Skrift](properties-text.md)** – navnet på skriftserien som teksten vises i.

**[FontWeight](properties-text.md)** – tykkelsen på teksten i en kontroll: **Fet**, **Halvfet**, **Normal** eller **Lysere**.

**[Høyde](properties-size-location.md)** – avstanden mellom kontrollens øvre og nedre kant.

**[HoverBorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje når brukeren holder musepekeren på denne kontrollen.

**[HoverColor](properties-color-border.md)** – Fargen på teksten i en kontroll når brukeren holder musepekeren over den.

**[HoverFill](properties-color-border.md)** – bakgrunnsfargen for en kontroll når brukeren holder musepekeren over den.

**[Italic](properties-text.md)** – om teksten i en kontroll er kursiv.

**[Padding](properties-size-location.md)**  – avstanden mellom teksten på en import eller eksport-knapp og kantene av denne knappen.

**[PressedBorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje når brukeren trykker eller klikker på kontrollen.

**[PressedColor](properties-color-border.md)** – fargen på teksten i en kontroll når brukeren trykker eller klikker på kontrollen.

**[PressedFill](properties-color-border.md)** – bakgrunnsfargen i en kontroll når brukeren trykker eller klikker på kontrollen.

**[RadiusBottomLeft](properties-size-location.md)** – i hvilken grad hjørnet nederst til venstre i en kontroll avrundes.

**[RadiusBottomRight](properties-size-location.md)**  – i hvilken grad hjørnet nederst til høyre i en kontroll avrundes.

**[RadiusTopLeft](properties-size-location.md)** – i hvilken grad hjørnet øverst til venstre i en kontroll avrundes.

**[RadiusTopRight](properties-size-location.md)**  – I hvilken grad hjørnet øverst til høyre i en kontroll avrundes.

**[Size](properties-text.md)** – skriftstørrelsen på teksten som vises på en kontroll.

**[Strikethrough](properties-text.md)** – om det vises en linje gjennom teksten som vises på en kontroll.

**[TabIndex](properties-accessibility.md)** – navigasjonsrekkefølge for tastatur i forhold til andre kontroller.

**[Text](properties-core.md)**  – Tekst som vises på en kontroll eller som brukeren skriver inn i en kontroll.

**[Underline](properties-text.md)** – om det vises en linje under teksten som vises på en kontroll.

**[VerticalAlign](properties-text.md)** – plasseringen av tekst i en kontroll i forhold til det vertikale midtpunktet i kontrollen.

**[Visible](properties-core.md)** – om kontrollen vises eller skjules.

**[Bredde](properties-size-location.md)** – avstanden mellom kontrollens venstre og høyre kant.

**[X](properties-size-location.md)** – avstanden mellom kontrollens venstre kant og den venstre kanten til kontrollens overordnede beholder (eller skjermen, hvis det ikke finnes noen overordnet beholder).

**[Y](properties-size-location.md)** – avstanden mellom kontrollens øvre kant og den øvre kanten til kontrollens overordnede beholder (eller skjermen, hvis det ikke finnes noen overordnet beholder).

## <a name="example"></a>Eksempel
1. Legg til en **[Knapp](control-button.md)**, og angi **[OnSelect](properties-core.md)**-egenskapen til denne formelen:
   <br>**ClearCollect(Products, {Name:"Europa", Price:"10.99"}, {Name:"Ganymede", Price:"12.49"}, {Name:"Callisto", Price:"11.79"})**
   
    Vet du ikke hvordan du [legger til, gir navn til og konfigurerer en kontroll](../add-configure-controls.md)?
   
    Vil du ha mer informasjon om **[ClearCollect](../functions/function-clear-collect-clearcollect.md)**-funksjonen eller [andre funksjoner](../formula-reference.md)?
2. Trykk på F5, klikk eller trykk på **[Knapp](control-button.md)**-kontrollen, og trykk deretter på Esc for å gå tilbake til arbeidsområdet.
3. Legg til en **Eksporter**-kontroll, og angi **Data**-egenskapen som **Products**.
4. Trykk på F5, klikk eller trykk på **Eksporter**-kontrollen, og angi deretter navnet på filen du vil eksportere dataene til.
5. Klikk eller trykk på **Lagre**, og trykk på Esc for å gå tilbake til standardarbeidsområdet.
6. Legge til en **Import**-kontroll i en ny eller eksisterende app, gi den navnet **MyData**, og angi **[OnSelect](properties-core.md)**-egenskapen som denne formelen:<br>
   **Collect(ImportedProducts, MyData.Data)**
7. Trykk på F5, klikk eller trykk på **MyData**, klikk eller trykk på filen du eksporterte, og klikk eller trykk deretter på **Åpne**.
8. Trykk på Esc, klikk eller trykk på **Samlinger** på **Fil**-menyen, og bekreft at den gjeldende appen har dataene som du eksporterte.


## <a name="accessibility-guidelines"></a>Retningslinjer for tilgjengelighet
De samme retningslinjene for **[Knapp](control-button.md)** gjelder fordi **Eksporter** og **Importer** er bare spesialknapper.
