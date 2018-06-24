---
title: 'Etikettkontroll: referanse | Microsoft Docs'
description: Informasjon om etikettkontrollen, inkludert egenskaper og eksempler
documentationcenter: na
author: fikaradz
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: reference
ms.component: canvas
ms.date: 10/25/2016
ms.author: fikaradz
ms.openlocfilehash: caa8cf8678a509e4d66442f790b8d89905d48b92
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/04/2018
ms.locfileid: "31838606"
---
# <a name="label-control-in-powerapps"></a>Etikettkontrollen i PowerApps
En boks som viser data som tekst, tall, datoer eller valuta.

## <a name="description"></a>Beskrivelse
En etikett viser data som du angir som en litteral tekststreng. Det vises nøyaktig slik du skriver det, eller som en formel som returnerer en streng med tekst. Etiketter vises ofte utenfor en annen kontroll (for eksempel et banner som identifiserer en skjerm), som en etikett som identifiserer en annen kontroll (for eksempel en vurdering eller lydkontroll), eller i et galleri for å vise en bestemt type informasjon om et element.

## <a name="key-properties"></a>Nøkkelegenskaper
**[AutoHeight](properties-core.md)** – angis som sann for å tillate at etiketten øker høyden automatisk for å vise hele den konfigurerte teksten. Angis som usann for å avkorte teksten til den tilordnede høyden.

**[Farge](properties-color-border.md)**  – fargen på teksten i kontrollen.

**[Skrift](properties-text.md)**  – navnet på skriftserien som teksten vises i.

**[Tekst](properties-core.md)**  – tekst som vises på en kontroll, eller som brukeren skriver inn i en kontroll.

**[DelayOutput](properties-core.md)** – angis som sann for å forsinke en handling ved tekstinndata.

## <a name="additional-properties"></a>Tilleggsegenskaper
**[Juster](properties-text.md)**  – plasseringen av teksten i forhold til den vannrette midten av kontrollen.

**AutoHeight** – om en etikett automatisk øker **[Høyde](properties-size-location.md)**-egenskapen hvis  **[Tekst](properties-core.md)**-egenskapen inneholder flere tegn enn kontrollen kan vise om gangen.

**[BorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje.

**[BorderStyle](properties-color-border.md)** – om kontrollens kantlinje er satt til **Heltrukket**, **Stiplet**, **Prikket** eller **Ingen**.

**[BorderThickness](properties-color-border.md)** – tykkelsen til kontrollens kantlinje.

**[DisplayMode](properties-core.md)** – om kontrollen tillater brukerinndata (**Rediger**), bare viser data (**Vis**) eller er deaktivert (**Deaktivert**).

**[DisabledBorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje hvis kontrollens **[DisplayMode](properties-core.md)**-egenskap er angitt til **Deaktivert**.

**[DisabledColor](properties-color-border.md)** – fargen på kontrollens tekst hvis kontrollens **[DisplayMode](properties-core.md)**-egenskap er angitt som **Deaktivert**.

**[DisabledFill](properties-color-border.md)** – bakgrunnsfargen på en kontroll hvis **[DisplayMode](properties-core.md)**-egenskapen er angitt som **Deaktivert**.

**[Fyll](properties-color-border.md)** – bakgrunnsfargen på kontrollen.

**[FocusedBorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje når kontrollen er fokusert.

**[FocusedBorderThickness](properties-color-border.md)** – tykkelsen på kontrollens kantlinje når kontrollen er fokusert.

**[FontWeight](properties-text.md)** – tykkelsen på teksten i en kontroll: **Fet**, **Halvfet**, **Normal** eller **Lysere**.

**[Høyde](properties-size-location.md)** – avstanden mellom kontrollens øvre og nedre kant.

**[HoverBorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje når brukeren holder musepekeren på denne kontrollen.

**[HoverColor](properties-color-border.md)** – Fargen på teksten i en kontroll når brukeren holder musepekeren over den.

**[HoverFill](properties-color-border.md)** – bakgrunnsfargen for en kontroll når brukeren holder musepekeren over den.

**[Kursiv](properties-text.md)** – om teksten i en kontroll er i kursiv.

**[LineHeight](properties-text.md)** – avstanden mellom linjer med tekst, elementer i en liste eller lignende.

**[OnSelect](properties-core.md)** – hvordan appen reagerer når brukeren klikker eller trykker på en kontroll.

**Overflyt** – om et rullefelt vises i en etikett hvis **Bryt**-egenskapen er satt til **sann** og verdien av kontrollens **[Tekst](properties-core.md)**-egenskap inneholder flere tegn enn kontrollen kan vise om gangen.

**[PaddingBottom](properties-size-location.md)** – avstanden mellom teksten i en kontroll og den nederste kanten av kontrollen.

**[PaddingLeft](properties-size-location.md)** – avstanden mellom teksten i en kontroll og den venstre kanten av kontrollen.

**[PaddingRight](properties-size-location.md)** – avstanden mellom teksten i en kontroll og den høyre kanten av kontrollen.

**[PaddingTop](properties-size-location.md)** – avstanden mellom teksten i en kontroll og den øverste kanten av kontrollen.

**[PressedBorderColor](properties-color-border.md)**  – fargen på kontrollens kantlinje når brukeren trykker eller klikker på kontrollen.

**[PressedColor](properties-color-border.md)** – fargen på teksten i en kontroll når brukeren trykker eller klikker på kontrollen.

**[PressedFill](properties-color-border.md)** – bakgrunnsfargen i en kontroll når brukeren trykker eller klikker på kontrollen.

**[Størrelse](properties-text.md)** – skriftstørrelsen på teksten som vises på en kontroll.

**[Strikethrough](properties-text.md)** – om det vises en linje gjennom teksten som vises på en kontroll.

**[TabIndex](properties-accessibility.md)** – navigasjonsrekkefølge for tastatur i forhold til andre kontroller.

**[Verktøytips](properties-core.md)** – forklarende tekst som vises når brukeren holder pekeren over en kontroll.

**[Underline](properties-text.md)**  – Hvorvidt det vises en linje under teksten som vises på en kontroll.

**[VerticalAlign](properties-text.md)** – plasseringen av tekst i en kontroll i forhold til det vertikale midtpunktet i kontrollen.

**[Visible](properties-core.md)** – om kontrollen vises eller skjules.

**[Width](properties-size-location.md)** – avstanden mellom venstrekanten og høyrekanten på en kontroll.

**Bryt** – om teksten som er for lang til å få plass i en etikett brytes til neste linje.

**[X](properties-size-location.md)** – avstanden mellom kontrollens venstre kant og den venstre kanten til kontrollens overordnede beholder (eller skjermen, hvis det ikke finnes noen overordnet beholder).

**[Y](properties-size-location.md)** – avstanden mellom kontrollens øvre kant og den øvre kanten til kontrollens overordnede beholder (eller skjermen, hvis det ikke finnes noen overordnet beholder).

## <a name="related-functions"></a>Relaterte funksjoner
[**Tekst**( *Tall*, «*FormatCodes*» )](../functions/function-text.md)

## <a name="examples"></a>Eksempler
### <a name="show-a-literal-string"></a>Vise en litteral streng
* Legg til en etikett, og sett **[Tekst](properties-core.md)**-egenskapen til **«God dag, verden»** (inkludert de doble anførselstegnene).
  
    Lurer du på hvordan du [legger til og konfigurerer en kontroll](../add-configure-controls.md)?

### <a name="show-the-result-of-a-formula"></a>Vise resultatet av en formel
* Legg til en etikett, og angi **[Tekst](properties-core.md)**-egenskapen som en formel, som denne:<br>
  **Today()**
  
    > [!NOTE]
> Når du angir en formel, bruker du ikke anførselstegn med mindre ett av argumentene i formelen er en litteral streng. I så fall må du omslutte argumentet i doble anførselstegn og ikke hele formelen.
  
    Vil du ha mer informasjon om **[Today](../functions/function-now-today-istoday.md)**-funksjonen eller [andre funksjoner](../formula-reference.md)?

### <a name="show-data-in-a-gallery"></a>Vise data i et galleri
I denne prosedyren oppretter du en samling kalt **CityPopulations**, som inneholder data om innbyggertallet for forskjellige byer i Europa. Deretter viser du dataene i et galleri som inneholder tre etiketter, og du angir hvilken type data som skal vises i hver etikett.

1. Legg til en knapp, og angi knappens **[OnSelect](properties-core.md)**-egenskap til denne formelen:<br>
   **ClearCollect(CityPopulations, {City:"London", Country:"United Kingdom", Population:8615000}, {City:"Berlin", Country:"Germany", Population:3562000}, {City:"Madrid", Country:"Spain", Population:3165000}, {City:"Rome", Country:"Italy", Population:2874000}, {City:"Paris", Country:"France", Population:2273000}, {City:"Hamburg", Country:"Germany", Population:1760000}, {City:"Barcelona", Country:"Spain", Population:1602000}, {City:"Munich", Country:"Germany", Population:1494000}, {City:"Milan", Country:"Italy", Population:1344000})**
2. Trykk på F5, velg knappen, og trykk deretter på ESC.
3. Legg til et tekstgalleri, og sett **[Elementer](properties-core.md)**-egenskapen til **CityPopulations**.
   
    Når galleriet er valgt, viser den høyre ruten alternativene for galleriet.
4. Angi den øverste listen i **Gallery1**-ruten til **Populasjon**, angi den midterste listen til **By**, og angi den nederste listen som **Land**.


## <a name="accessibility-guidelines"></a>Retningslinjer for tilgjengelighet
Til tross for navnet er det ikke nødvendig å bruke en **etikett**-kontroll som en etikett for en annen kontroll. Den kan brukes til å vise alle slags tekstsekvenser.

En **etikett** kan brukes som en knapp eller kobling ved å angi **[OnSelect](properties-core.md)**-virkemåte. Når den brukes på denne måten, foreligger det lignende tilgjengelighetshensyn som ved knapper.

### <a name="color-contrast"></a>Fargekontrast
Det må være tilstrekkelig fargekontrast mellom:
* **[Farge](properties-color-border.md)** og **[Fyll](properties-color-border.md)**
* Andre [standardkrav for fargekontrast](../accessible-apps-color.md) gjelder (hvis den brukes som en knapp eller kobling)

### <a name="screen-reader-support"></a>Kundestøtte for skjermlesere
* **[Tekst](properties-core.md)** må foreligge.

    > [!NOTE]
> Skjermlesere behandler **etiketter** som knapper når **[TabIndex](properties-accessibility.md)** er null eller større.

### <a name="low-vision-support"></a>Støtte for nedsatt syn
* **Etikett** skal se ut som en kobling, hvis den brukes som en kobling.
    * Angi **[understreking](properties-text.md)** til **sann**
    * **[HoverColor](properties-color-border.md)** må være forskjellig fra **[Farge](properties-color-border.md)**

### <a name="keyboard-support"></a>Tastaturstøtte
* **[TabIndex](properties-accessibility.md)** må være lik null eller større hvis teksten brukes som en knapp eller kobling. Dette gjør at tastaturbrukere får muligheten til å navigere til den.
* Fokusindikatorer må være klart synlige hvis teksten brukes som en knapp eller kobling. Bruk **[FocusedBorderColor](properties-color-border.md)** og **[FocusedBorderThickness](properties-color-border.md)** for å oppnå dette.
