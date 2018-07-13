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
ms.openlocfilehash: d8e195ad3e4f59b9f07e23e17a685d9d1f55bef4
ms.sourcegitcommit: dfa0e1a7981814e15e6ca4720e2a5f930e859db1
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 07/13/2018
ms.locfileid: "39022037"
---
# <a name="attachments-control-in-powerapps"></a>Vedlegg-kontrollen i PowerApps
Dette er en kontroll som lar brukerne laste ned filer på enhetene sine så vel som laste opp og slette filer fra en SharePoint-liste.

## <a name="limitations"></a>Begrensninger
Vedlegg-kontrollen har følgende midlertidige begrensninger:
1. Nedlasting av vedlegg støttes bare i SharePoint-listeskjemaer i Internet Explorer.

1. Opplasting av vedlegg fungerer bare med datakilder for SharePoint-lister.  Støtte for andre datakilder introduseres trinnvis, og starter med CDS.

1. Opplasting og sletting av funksjonalitet fungerer bare i et skjema.  Vedlegg-kontrollen ser deaktivert ut når den er i redigeringsmodus og ikke i et skjema.   Vær oppmerksom på at hvis du vil lagre filtilføyelsene og slettingene i serverdelen, må sluttbrukeren lagre skjemaet.

1. Du kan bare laste opp filer med opptil 10 MB.  

1. iOS-enheter kan for øyeblikket bare laste opp filer fra dokumenter og skylagringskontoer. Hvis du vil legge ved bilder/videoer, kan du bruke nettleseren på iOS-enheten til å kjøre appen.

## <a name="description"></a>Beskrivelse
Med en **Vedlegg**-kontroll kan du åpne filer som er lagret på en datakilde så vel som slette filer fra en SharePoint-liste.

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
1. Opprett en app fra dataene ved bruk av en SharePoint-liste som datakilde.  Du kan alternativt legge til et skjema i appen og angi en SharePoint-liste som datakilden.

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
