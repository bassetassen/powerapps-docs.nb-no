---
title: 'Strekkodeleser-kontroll: referanse i Microsoft Docs'
description: Informasjon om Strekkodeleser-kontrollen, inkludert egenskaper og eksempler
author: fikaradz
ms.service: powerapps
ms.topic: reference
ms.component: canvas
ms.date: 10/25/2016
ms.author: fikaradz
ms.openlocfilehash: 22b5cf081755f25b3aff33c36137547882fe3812
ms.sourcegitcommit: 7354a0c61578fcc0b9965bf557b9d7c553c73e96
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/05/2018
ms.locfileid: "34803478"
---
# <a name="barcode-scanner-control-experimental-in-powerapps"></a>Strekkodeleser-kontrollen (eksperimentell) i PowerApps
En eksperimentell kontroll som lar brukeren ta bilder ved hjelp av strekkodeleseren på enheten.

## <a name="description"></a>Beskrivelse
Hvis du legger til denne kontrollen, kan brukeren oppdatere en datakilde med ett eller flere bilder fra der som appen kjører.

## <a name="key-properties"></a>Nøkkelegenskaper
**Strekkodeleser** – på en enhet som har mer enn én strekkodeleser, den numeriske ID-en til strekkodeleseren som appen bruker.

## <a name="additional-properties"></a>Tilleggsegenskaper
**[AccessibleLabel](properties-accessibility.md)** – etikett for skjermlesere.

**[BorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje.

**[BorderStyle](properties-color-border.md)** – om kontrollens kantlinje er satt til **Heltrukket**, **Stiplet**, **Prikket** eller **Ingen**.

**[BorderThickness](properties-color-border.md)** – tykkelsen til kontrollens kantlinje.

**Brightness** – hvor mye lys brukeren sannsynligvis oppfatter i et bilde.

**Contrast** – hvor enkelt brukeren kan skille mellom lignende farger i et bilde.

**[DisplayMode](properties-core.md)** – om kontrollen tillater brukerinndata (**Rediger**), bare viser data (**Vis**) eller er deaktivert (**Deaktivert**).

**[Høyde](properties-size-location.md)** – avstanden mellom kontrollens øvre og nedre kant.

**[OnSelect](properties-core.md)** – hvordan appen reagerer når brukeren klikker eller trykker på en kontroll.

**OnStream** – hvordan appen svarer når **Strøm**-egenskapen oppdateres.

**Bilde** – bildet som brukeren tar.

**ShowLiveBarcodeDetection** – om visuelle hjelpemidler vises for å angi statusen til strekkodegjenkjenning. Gule rektangler representerer områder som undersøkes. En grønn linje på tvers av et rektangel angir vellykket strekkodeidentifikasjon.

**Strøm** – automatisk oppdatert bilde basert på **StreamRate**-egenskapen.

**StreamRate** – hvor ofte du vil oppdatere bildet på **Strøm** -egenskapen, i millisekunder.  Denne verdien kan være fra 100 (1/10 av et sekund) til 3 600 000 (1 time).

**Tekst** – verdien av strekkoden som sist ble identifisert av strekkodeleseren.

**[Verktøytips](properties-core.md)** – forklarende tekst som vises når brukeren holder pekeren over en kontroll.

**[Synlig](properties-core.md)** – om kontrollen vises eller skjules.

**[Bredde](properties-size-location.md)** – avstanden mellom kontrollens venstre og høyre kant.

**[X](properties-size-location.md)** – avstanden mellom kontrollens venstre kant og den venstre kanten til kontrollens overordnede beholder (eller skjermen, hvis det ikke finnes noen overordnet beholder).

**[Y](properties-size-location.md)** – avstanden mellom kontrollens øvre kant og den øvre kanten til kontrollens overordnede beholder (eller skjermen, hvis det ikke finnes noen overordnet beholder).

**Zoom** – Hvor mye et bilde fra en strekkodeleser prosentvis forstørres eller visningen av en fil i PDF-visningsprogram.

## <a name="related-functions"></a>Relaterte funksjoner
[**Patch**( *DataSource*, *BaseRecord*, *ChangeRecord* )](../functions/function-patch.md)

## <a name="example"></a>Eksempel
### <a name="add-photos-to-an-image-gallery-control"></a>Å legge til bilder i en Bildegalleri-kontroll
1. Legg til en **Strekkodeleser**-kontroll, gi den navnet **Mybarcode scanner**

    Vet du ikke hvordan du [legger til, gir navn til og konfigurerer en kontroll](../add-configure-controls.md)?
2. Legg til en **Etikett**-kontroll, og angi utmatingen til strekkodens **Tekst**-egenskap.  
3. Skann en strekkode av typen som er angitt under BarcodeType-egenskapen.
4. Etiketten skal vises de skannede strekkodene.


## <a name="accessibility-guidelines"></a>Retningslinjer for tilgjengelighet
### <a name="video-alternatives"></a>Alternativer for video
* Vurder å legg til en **[etikett](control-text-box.md)** der **[Tekst](properties-core.md)**-egenskapen er angitt til strekkodeleserens **Tekst**-egenskap. Hvis du gjør det ovennevnte, blir strekkodeleseren tilgjengelig for alle og ikke bare for de med nedsatt syn, siden strekkodeleseren ikke viser den identifiserte strekkodeverdien.

### <a name="screen-reader-support"></a>Kundestøtte for skjermlesere
* **[AccessibleLabel](properties-accessibility.md)** bør vises.

    > [!NOTE]
> Skjermleserne kunngjør når en ny strekkode har blitt funnet. Verdien vil ikke kunngjøres. Så lenge strekkoden er synlig så vil skjermlesere gi en påminnelse hvert 5. sekund om at den samme strekkoden fremdeles identifiseres.
