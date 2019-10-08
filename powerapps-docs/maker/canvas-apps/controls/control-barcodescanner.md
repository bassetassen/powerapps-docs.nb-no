---
title: 'Nett strek kode – skanner kontroll: referanse | Microsoft Docs'
description: Informasjon, deriblant egenskaper og eksempler, om strek kode-skanner kontrollen
author: fikaradz
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.date: 10/25/2016
ms.author: fikaradz
ms.reviewer: tapanm
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: d1162c0c9954e67196eb4d3e42b2c91bdc3bf804
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/07/2019
ms.locfileid: "71986988"
ms.PowerAppsDecimalTransform: true
---
# <a name="web-barcode-scanner-control-experimental-in-powerapps"></a>Nett strek kode – skanner kontroll (eksperimentell) i PowerApps

Den gamle kontrollen for strek kode-skanning, som er foreldet, men som kanskje er nyttig for skanne koder i en nett leser.

## <a name="description"></a>Beskrivelse

Kontrollen viser kamera feeden i appen, slik at brukere kan skanne strek koder på alle enheter. Kontrollen er foreldet på grunn av dårlig ytelse, og kontrollen for mobile **[Barcode-skanneren](control-new-barcode-scanner.md)** erstatter denne kontrollen.

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

[**Patch**( *DataSource*; *BaseRecord*; *ChangeRecord* )](../functions/function-patch.md)

## <a name="example"></a>Eksempel

### <a name="add-photos-to-an-image-gallery-control"></a>Å legge til bilder i en Bildegalleri-kontroll

1. Legg til en **Strekkodeleser**-kontroll, gi den navnet **Mybarcode scanner**

    Vet du ikke hvordan du [legger til, gir navn til og konfigurerer en kontroll](../add-configure-controls.md)?

1. Legg til en **etikett** -kontroll, og angi utdataene til **tekst** egenskapen for strek kode skanneren.

1. Skann en strek kode av typen som er angitt under **BarcodeType** -egenskapen.

    Etiketten viser den skannede strek koden.

## <a name="accessibility-guidelines"></a>Retningslinjer for tilgjengelighet

### <a name="video-alternatives"></a>Alternativer for video

* Vurder å legg til en **[etikett](control-text-box.md)** der **[Tekst](properties-core.md)** -egenskapen er angitt til strekkodeleserens **Tekst**-egenskap. Hvis du gjør det ovennevnte, blir strekkodeleseren tilgjengelig for alle og ikke bare for de med nedsatt syn, siden strekkodeleseren ikke viser den identifiserte strekkodeverdien.

### <a name="screen-reader-support"></a>Kundestøtte for skjermlesere

* **[AccessibleLabel](properties-accessibility.md)** bør vises.

    > [!NOTE]
  > Skjerm lesere vil annonsere når en ny strek kode er funnet. Verdien vil ikke bli kunngjort. Så lenge strek koden er i visning, vil skjerm lesere minne brukeren hvert femte sekund som den samme strek koden fremdeles identifiseres.
