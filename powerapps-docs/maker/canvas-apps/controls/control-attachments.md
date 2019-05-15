---
title: 'Vedlegg-kontroll: referanse | Microsoft Docs'
description: Informasjon om Vedlegg-kontrollen, inkludert egenskaper og eksempler
author: fikaradz
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.date: 04/23/2018
ms.author: fikaradz
ms.reviewer: anneta
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 9d24094bfbc596c232e7455ef3d8b8dcdfc5be5c
ms.sourcegitcommit: 9b2648a9066fe5d3b27b3d893daacba9b18eb75e
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 05/14/2019
ms.locfileid: "65609373"
---
# <a name="attachments-control-in-powerapps"></a>Vedlegg-kontrollen i PowerApps
En kontroll som gjør at brukere kan laste ned filer på enhetene sine, samt laste opp og slette filer fra en SharePoint-liste eller en Common Data Service-enhet.

## <a name="limitations"></a>Begrensninger
Vedleggskontrollen har disse begrensningene:
1. Vedlegg støttes med SharePoint-lister og Common Data Service-enheter.

1. Last opp og sletting av funksjonalitet fungerer bare i et skjema. Vedlegg-kontrollen vises deaktivert når i redigeringsmodus og ikke i et skjema. Hvis du vil lagre filtilføyelsene og slettingene, må appen brukeren lagre skjemaet. På grunn av denne begrensningen, vedlegg-kontrollen er ikke tilgjengelig fra den **Sett inn** fane vises men i skjemaet når skjemaet vedlegg-feltet er aktivert i en SharePoint- eller Common Data Service-skjemaet.

1. Du kan laste opp filer bare hvis de er 10 MB eller mindre.  

## <a name="description"></a>Beskrivelse
En **vedlegg** kontrollen kan du åpne, legge til og slette filer fra en SharePoint-liste eller en Common Data Service-enhet.

## <a name="key-properties"></a>Nøkkelegenskaper
**[Elementer](properties-core.md)** – kilden som beskriver filene som kan lastes ned.

**MaxAttachments** – maksimalt antall filer kontrollen godkjenner.

**MaxAttachmentSize** – maksimalt tillatte filstørrelse i MB for hvert nye vedlegg.  Grensen er for øyeblikket 10 MB.

**OnAttach** – hvordan appen reagerer når brukeren legger til et nytt filvedlegg.

**OnRemove** – hvordan appen reagerer når brukeren sletter et eksisterende filvedlegg.

**[OnSelect](properties-core.md)** – hvordan appen reagerer når brukeren klikker på et vedlegg.

## <a name="additional-properties"></a>Tilleggsegenskaper
**[AccessibleLabel](properties-accessibility.md)** – etikett for skjermlesere. Skal beskrive formålet med vedleggene.

**AddAttachmentText** – etiketteksten for koblingen som ble brukt til å legge til et nytt vedlegg.

**[BorderColor](properties-color-border.md)** – Fargen på kontrollens kantlinje.

**[BorderStyle](properties-color-border.md)** – om kontrollens kantlinje er satt til **Heltrukket**, **Stiplet**, **Prikket** eller **Ingen**.

**[BorderThickness](properties-color-border.md)** – Tykkelsen på kontrollens kantlinje.

**[DisplayMode](properties-core.md)** – om kontrollen tillater tillegging og sletting av filer (**Rediger**), bare viser data (**Vis**) eller er deaktivert (**Deaktivert**).

**[FocusedBorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje når kontrollen er fokusert.

**[FocusedBorderThickness](properties-color-border.md)** – fargen på kontrollens kantlinje når kontrollen er fokusert.

**[Høyde](properties-size-location.md)** – avstanden mellom kontrollens øvre og nedre kant.

**MaxAttachmentsText** – teksten som erstatter Legg til fil-koblingen når kontrollen inneholder maksimalt antall tillatte filer.

**NoAttachmentsText** – informasjonstekst som vises til brukeren når det ikke er noen filer vedlagt.

**[TabIndex](properties-accessibility.md)** – navigasjonsrekkefølge for tastatur i forhold til andre kontroller.

**[Synlig](properties-core.md)** – om kontrollen er synlig eller skjult.

**[Bredde](properties-size-location.md)** – avstanden mellom kontrollens venstre og høyre kant.

**[X](properties-size-location.md)** – avstanden mellom kontrollens venstre kant og den venstre kanten til kontrollens overordnede beholder (eller skjermen, hvis det ikke finnes noen overordnet beholder).

**[Y](properties-size-location.md)** – avstanden mellom kontrollens øvre kant og den øvre kanten til kontrollens overordnede beholder (eller skjermen, hvis det ikke finnes noen overordnet beholder).


## <a name="example"></a>Eksempel
1. Opprett en app fra dataene ved bruk av en SharePoint-liste som datakilde. Alternativt kan du legge til et skjema i appen og angi en SharePoint-liste som datakilden.

2. Velg **Skjema**-kontrollen i trevisningen til venstre.

3. Klikk på **Data** på Egenskaper-fanen i Alternativer-panelet til høyre.

4. Aktiver **Vedlegg**-feltet under **Felter**.

    Vedlegg-feltet som er knyttet til SharePoint-listen vises i skjemaet.

[Finn ut hvordan du legger til og konfigurerer en kontroll].(../add-configure-controls.md)


## <a name="accessibility-guidelines"></a>Retningslinjer for tilgjengelighet
### <a name="color-contrast"></a>Fargekontrast
Det må være tilstrekkelig fargekontrast mellom:
* **ItemColor** og **ItemFill**
* **ItemHoverColor** og **ItemHoverFill**
* **ItemPressedColor** og **ItemPressedFill**
* **AddedItemColor** og **AddedItemFill**
* **RemovedItemColor** og **RemovedItemFill**
* **ItemErrorColor** og **ItemErrorFill**
* **AddAttachmentColor** og **Fyll**
* **MaxAttachmentsColor** og **Fyll**
* **NoAttachmentsColor** og **Fyll**

Dette er i tillegg til [kravene for standard fargekontrast](../accessible-apps-color.md).

### <a name="screen-reader-support"></a>Kundestøtte for skjermlesere
Følgende egenskaper må være til stede:
* **[AccessibleLabel](properties-accessibility.md)**
* **AddAttachmentsText**
* **MaxAttachmentsText**
* **NoAttachmentsText**

### <a name="keyboard-support"></a>Tastaturstøtte
* **[TabIndex](properties-accessibility.md)** må være null eller større, slik at tastaturbrukere kan navigere til den.
* Fokusindikatorer må være godt synlige. Bruk **[FocusedBorderColor](properties-color-border.md)** og **[FocusedBorderThickness](properties-color-border.md)** for å oppnå dette.
