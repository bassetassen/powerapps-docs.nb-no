---
title: 'Kamera-kontroll: referanse | Microsoft Docs'
description: Informasjon om Kamera-kontrollen, inkludert egenskaper og eksempler
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
ms.openlocfilehash: a3a724ad42082962ec8aea4e616f1d75aa7299ec
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/22/2018
ms.locfileid: "30995987"
---
# <a name="camera-control-in-powerapps"></a>Kamera-kontrollen i PowerApps
En kontroll som lar brukeren ta bilder ved hjelp av kameraet på enheten.

## <a name="description"></a>Beskrivelse
Hvis du legger til denne kontrollen, kan brukeren oppdatere en datakilde med ett eller flere bilder fra der som appen kjører.

## <a name="key-properties"></a>Nøkkelegenskaper
**Kamera** – ID-nummeret til kameraet som appen bruker for enheter med mer enn ett kamera.

## <a name="additional-properties"></a>Tilleggsegenskaper
**[BorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje.

**[BorderStyle](properties-color-border.md)** – om kontrollens kantlinje er **Heltrukket**, **Stiplet**, **Prikket** eller **Ingen**.

**[BorderThickness](properties-color-border.md)** – tykkelsen til kontrollens kantlinje.

**Brightness** – hvor mye lys brukeren sannsynligvis oppfatter i et bilde.

**Contrast** – hvor enkelt brukeren kan skille mellom lignende farger i et bilde.

**[DisplayMode](properties-core.md)** – om kontrollen tillater brukerinndata (**Rediger**), bare viser data (**Vis**) eller er deaktivert (**Deaktivert**).

**[Høyde](properties-size-location.md)** – avstanden mellom kontrollens øvre og nedre kant.

**[OnSelect](properties-core.md)** – hvordan appen reagerer når brukeren klikker eller trykker på en kontroll.

**OnStream** – hvordan appen svarer når **Strøm**-egenskapen oppdateres.

**Bilde** – bildet som brukeren tar.

**Strøm** – automatisk oppdatert bilde basert på **StreamRate**-egenskapen.

**StreamRate** – hvor ofte du vil oppdatere bildet på **Strøm** -egenskapen, i millisekunder.  Denne verdien kan være fra 100 (1/10 av et sekund) til 3 600 000 (1 time).

**[Verktøytips](properties-core.md)** – forklarende tekst som vises når brukeren holder pekeren over en kontroll.

**[Synlig](properties-core.md)** – om kontrollen vises eller skjules.

**[Bredde](properties-size-location.md)** – avstanden mellom kontrollens venstre og høyre kant.

**[X](properties-size-location.md)** – avstanden mellom kontrollens venstre kant og den venstre kanten til kontrollens overordnede beholder (eller skjermen, hvis det ikke finnes noen overordnet beholder).

**[Y](properties-size-location.md)** – avstanden mellom kontrollens øvre kant og den øvre kanten til kontrollens overordnede beholder (eller skjermen, hvis det ikke finnes noen overordnet beholder).

**Zoom** – hvor mye et bilde fra et kamera prosentvis forstørres eller hvor mye som vises i et PDF-visningsprogram.

## <a name="related-functions"></a>Relaterte funksjoner
[**Patch**( *DataSource*, *BaseRecord*, *ChangeRecord* )](../functions/function-patch.md)

## <a name="example"></a>Eksempel
### <a name="add-photos-to-an-image-gallery-control"></a>Å legge til bilder i en bildegalleri-kontroll
1. Legg til en **kamera**-kontroll, gi den navnet **MyCamera**, og angi **[OnSelect](properties-core.md)**-egenskapen som denne formelen:<br>
   **Collect(MyPix, MyCamera.Photo)**
   
    Vet du ikke hvordan du [legger til, gir navn til og konfigurerer en kontroll](../add-configure-controls.md)?
   
    Vil du ha mer informasjon om **[Collect](../functions/function-clear-collect-clearcollect.md)**-funksjonen eller [andre funksjoner](../formula-reference.md)?
2. Trykk på F5, og ta et bilde ved å klikke eller trykke på **MyCamera**.
3. Legge til en **[bildegalleri](control-gallery.md)**-kontroll, og juster størrelsen på **[Bilde](control-image.md)**-kontrollen, malen og selve **Bildegalleri**-kontrollen, slik at de passer på skjermen.
4. Angi **[Elementer](properties-core.md)**-egenskapen til **Bildegalleri**-kontrollen som dette uttrykket:<br>**MyPix.Url**.
5. Angi **[Elementer](properties-visual.md)**-egenskapen til **Bilde**-kontrollen som dette uttrykket:<br>
   **ThisItem.Url**
   
    Bildet som du tok, vises i **Bildegalleri**-kontrollen.
6. Ta så mange bilder som du ønsker, og gå tilbake til standardarbeidsområdet ved å trykke på ESC.
7. (valgfritt) Angi **OnSelect**-egenskapen for **Bilde**-kontrollen i **Bildegalleri**-kontrollen til **Remove(MyPix, ThisItem)**, trykk på F5, og klikk eller trykk så på et bilde for å fjerne det.

Bruk **[SaveData](../functions/function-savedata-loaddata.md)**-funksjonen til å lagre bildene lokalt, eller **[Patch](../functions/function-patch.md)**-funksjonen for å oppdatere en datakilde.

