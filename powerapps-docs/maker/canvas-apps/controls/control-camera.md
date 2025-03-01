---
title: 'Kamera-kontroll: referanse | Microsoft Docs'
description: Informasjon om Kamera-kontrollen, inkludert egenskaper og eksempler
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
ms.openlocfilehash: 88b6b9faf8c4d7c14a09bfc89791a050e3c07ca2
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/07/2019
ms.locfileid: "71986861"
ms.PowerAppsDecimalTransform: true
---
# <a name="camera-control-in-powerapps"></a>Kamera-kontrollen i PowerApps
En kontroll som lar brukeren ta bilder ved hjelp av kameraet på enheten.

## <a name="description"></a>Beskrivelse
Hvis du legger til denne kontrollen, kan brukeren oppdatere en datakilde med ett eller flere bilder fra der som appen kjører.

## <a name="key-properties"></a>Nøkkelegenskaper
**Kamera** – ID-nummeret til kameraet som appen bruker for enheter med mer enn ett kamera.

## <a name="additional-properties"></a>Tilleggsegenskaper
**[AccessibleLabel](properties-accessibility.md)** – etikett for skjermlesere. Skal beskrive formålet med å legge til et bilde.

**[BorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje.

**[BorderStyle](properties-color-border.md)** – om kontrollens kantlinje er satt til **Heltrukket**, **Stiplet**, **Prikket** eller **Ingen**.

**[BorderThickness](properties-color-border.md)** – tykkelsen til kontrollens kantlinje.

**Brightness** – hvor mye lys brukeren sannsynligvis oppfatter i et bilde.

**Contrast** – hvor enkelt brukeren kan skille mellom lignende farger i et bilde.

**[DisplayMode](properties-core.md)** – om kontrollen tillater brukerinndata (**Rediger**), bare viser data (**Vis**) eller er deaktivert (**Deaktivert**).

**[FocusedBorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje når kontrollen er fokusert.

**[FocusedBorderThickness](properties-color-border.md)** – fargen på kontrollens kantlinje når kontrollen er fokusert.

**[Høyde](properties-size-location.md)** – avstanden mellom kontrollens øvre og nedre kant.

**[OnSelect](properties-core.md)** – hvordan appen reagerer når brukeren klikker eller trykker på en kontroll.

**OnStream** – hvordan appen svarer når **Strøm**-egenskapen oppdateres.

**Bilde** – bildet som brukeren tar.

**Strøm** – automatisk oppdatert bilde basert på **StreamRate**-egenskapen.

**StreamRate** – hvor ofte du vil oppdatere bildet på **Strøm** -egenskapen, i millisekunder.  Denne verdien kan være fra 100 (1/10 av et sekund) til 3 600 000 (1 time).

**[TabIndex](properties-accessibility.md)** – navigasjonsrekkefølge for tastatur i forhold til andre kontroller.

**[Verktøytips](properties-core.md)** – forklarende tekst som vises når brukeren holder pekeren over en kontroll.

**[Synlig](properties-core.md)** – om kontrollen vises eller skjules.

**[Bredde](properties-size-location.md)** – avstanden mellom kontrollens venstre og høyre kant.

**[X](properties-size-location.md)** – avstanden mellom kontrollens venstre kant og den venstre kanten til kontrollens overordnede beholder (eller skjermen, hvis det ikke finnes noen overordnet beholder).

**[Y](properties-size-location.md)** – avstanden mellom kontrollens øvre kant og den øvre kanten til kontrollens overordnede beholder (eller skjermen, hvis det ikke finnes noen overordnet beholder).

## <a name="related-functions"></a>Relaterte funksjoner
[**Patch**( *DataSource*; *BaseRecord*; *ChangeRecord* )](../functions/function-patch.md)

## <a name="example"></a>Eksempel
### <a name="add-photos-to-an-image-gallery-control"></a>Å legge til bilder i en Bildegalleri-kontroll
1. Legg til en **kamera**-kontroll, gi den navnet **MyCamera**, og angi **[OnSelect](properties-core.md)** -egenskapen som denne formelen:<br>
   **Collect(MyPix; MyCamera.Photo)**

    Vet du ikke hvordan du [legger til, gir navn til og konfigurerer en kontroll](../add-configure-controls.md)?

    Vil du ha mer informasjon om **[Collect](../functions/function-clear-collect-clearcollect.md)** -funksjonen eller [andre funksjoner](../formula-reference.md)?
2. Trykk på F5, og ta et bilde ved å klikke eller trykke på **MyCamera**.
3. Legg til en **[bildegalleri](control-gallery.md)** -kontroll, og juster størrelsen på **[bilde](control-image.md)** -kontrollen, malen og selve **bildegalleri**-kontrollen, slik at de passer på skjermen.
4. Angi **[Elementer](properties-core.md)** -egenskapen til **Bildegalleri**-kontrollen som:<br>**MyPix**.
5. Angi **[Elementer](properties-visual.md)** -egenskapen til **Bilde**-kontrollen som dette uttrykket:<br>
   **ThisItem.Url**

    Bildet som du tok, vises i **Bildegalleri**-kontrollen.
6. Ta så mange bilder som du ønsker, og gå tilbake til standardarbeidsområdet ved å trykke på ESC.
7. (valgfritt) Angi **OnSelect**-egenskapen for **Bilde**-kontrollen i **Bildegalleri**-kontrollen til **Remove(MyPix; ThisItem)** , trykk på F5, og klikk eller trykk så på et bilde for å fjerne det.

Bruk **[SaveData](../functions/function-savedata-loaddata.md)** -funksjonen til å lagre bildene lokalt, eller **[Patch](../functions/function-patch.md)** -funksjonen for å oppdatere en datakilde.


## <a name="accessibility-guidelines"></a>Retningslinjer for tilgjengelighet
I tillegg til å vise kamera-feeden, fungerer hele kamerakontrollen også som en knapp som tar et bilde. I så måte foreligger det lignende tilgjengelighetshensyn som man har med knapper.

### <a name="video-alternatives"></a>Alternativer for video
* Vurder å legge til en alternativ form for inndata for brukere med nedsatt syn. For eksempel **[Legg til bilde](control-add-picture.md)** , for å la brukere laste opp et bilde fra enheten.

### <a name="color-contrast"></a>Fargekontrast
Det må være tilstrekkelig fargekontrast mellom:
* **[FocusedBorderColor](properties-color-border.md)** og den ytre fargen

### <a name="screen-reader-support"></a>Kundestøtte for skjermlesere
* **[AccessibleLabel](properties-accessibility.md)** bør vises.

### <a name="keyboard-support"></a>Tastaturstøtte
* **[TabIndex](properties-accessibility.md)** må være null eller større, slik at tastaturbrukere kan navigere til den.
* Fokusindikatorer må være godt synlige. Bruk **[FocusedBorderColor](properties-color-border.md)** og **[FocusedBorderThickness](properties-color-border.md)** for å oppnå dette.
