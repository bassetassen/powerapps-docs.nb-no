---
title: 'Web-strekkodeleser kontrollen: referanse | Microsoft Docs'
description: Informasjon, inkludert egenskaper og eksempler, om strekkodeleser kontrollen
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
ms.openlocfilehash: 787fa34bdfcabf6103fefd82f66e976b680544e2
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/23/2019
ms.locfileid: "61544595"
---
# <a name="web-barcode-scanner-control-experimental-in-powerapps"></a>Web strekkodeleser kontrollen (eksperimentell) i PowerApps

Den eldre strekkodeskanning kontrollen, som er foreldet, men det kan være nyttig for å skanne-koder i en nettleser.

## <a name="description"></a>Beskrivelse

Kontrollen viser kameraet feed i appen slik at brukere kan skanne strekkoder på alle enheter. Kontrollen er foreldet på grunn av dårlig ytelse, og mobile **[strekkodeleser](control-new-barcode-scanner.md)** kontrollen erstatter denne kontrollen.

## <a name="key-properties"></a>Nøkkelegenskaper

**Strekkodeleser** – på en enhet som har mer enn én strekkodeleser, den numeriske ID-en til strekkodeleseren som appen bruker.

## <a name="additional-properties"></a>Tilleggsegenskaper

**[AccessibleLabel](properties-accessibility.md)** – etikett for skjermlesere.

**[BorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje.

**[BorderStyle](properties-color-border.md)** – om kontrollens kantlinje er satt til **Heltrukket**, **Stiplet**, **Prikket** eller **Ingen**.

**[BorderThickness](properties-color-border.md)** – tykkelsen til kontrollens kantlinje.

**[DisplayMode](properties-core.md)** – Hvorvidt kontrollen tillater brukerinndata (**Edit**), bare viser data (**View**) eller er deaktivert (**Disabled**).

**[Høyde](properties-size-location.md)** – avstanden mellom kontrollens øvre og nedre kant.

**ShowLiveBarcodeDetection** – om visuelle hjelpemidler vises for å angi statusen til strekkodegjenkjenning. Gule rektangler representerer områder som undersøkes. En grønn linje på tvers av et rektangel angir vellykket strekkodeidentifikasjon.

**Strøm** – automatisk oppdatert bilde basert på **StreamRate**-egenskapen.

**StreamRate** – hvor ofte du vil oppdatere bildet på **Strøm** -egenskapen, i millisekunder.  Denne verdien kan være fra 100 (1/10 av et sekund) til 3 600 000 (1 time).

**Tekst** – verdien av strekkoden som sist ble identifisert av strekkodeleseren.

**[Verktøytips](properties-core.md)** – forklarende tekst som vises når brukeren holder pekeren over en kontroll.

**[Synlig](properties-core.md)** – om kontrollen vises eller skjules.

**[Bredde](properties-size-location.md)** – avstanden mellom kontrollens venstre og høyre kant.

**[X](properties-size-location.md)** – avstanden mellom kontrollens venstre kant og den venstre kanten til kontrollens overordnede beholder (eller skjermen, hvis det ikke finnes noen overordnet beholder).

**[Y](properties-size-location.md)** – avstanden mellom kontrollens øvre kant og den øvre kanten til kontrollens overordnede beholder (eller skjermen, hvis det ikke finnes noen overordnet beholder).

## <a name="related-functions"></a>Relaterte funksjoner

[**Patch**( *DataSource*, *BaseRecord*, *ChangeRecord* )](../functions/function-patch.md)

## <a name="example"></a>Eksempel

### <a name="add-photos-to-an-image-gallery-control"></a>Å legge til bilder i en Bildegalleri-kontroll

1. Legg til en **Strekkodeleser**-kontroll, gi den navnet **Mybarcode scanner**

    Vet du ikke hvordan du [legger til, gir navn til og konfigurerer en kontroll](../add-configure-controls.md)?

1. Legg til en **etikett** kontroll, og angi utmatingen til strekkodeleserens **tekst** egenskapen.

1. Skanne en strekkode av typen er angitt **BarcodeType** egenskapen.

    Etiketten viser de skannede strekkodene.

## <a name="accessibility-guidelines"></a>Retningslinjer for tilgjengelighet

### <a name="video-alternatives"></a>Alternativer for video

* Vurder å legg til en **[etikett](control-text-box.md)** der **[Tekst](properties-core.md)**-egenskapen er angitt til strekkodeleserens **Tekst**-egenskap. Hvis du gjør det ovennevnte, blir strekkodeleseren tilgjengelig for alle og ikke bare for de med nedsatt syn, siden strekkodeleseren ikke viser den identifiserte strekkodeverdien.

### <a name="screen-reader-support"></a>Kundestøtte for skjermlesere

* **[AccessibleLabel](properties-accessibility.md)** bør vises.

    > [!NOTE]
  > Skjermlesere leser opp når en ny strekkode har blitt funnet. Verdien vil ikke kunngjøres. Så lenge strekkoden er synlig, minne skjermlesere brukeren hver fem sekunder som den samme strekkoden fremdeles identifiseres.
