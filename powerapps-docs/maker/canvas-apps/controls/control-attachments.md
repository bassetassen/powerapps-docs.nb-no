---
title: 'Vedlegg-kontroll: referanse | Microsoft Docs'
description: Informasjon om Vedlegg-kontrollen, inkludert egenskaper og eksempler
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
ms.date: 09/29/2017
ms.author: fikaradz
ms.openlocfilehash: 5bb7e4f27ed7ee0a30fb028d4d8dfd20a5fc250b
ms.sourcegitcommit: 078ba325480147e6e4da61e319ed53219f1c5cfc
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/06/2018
ms.locfileid: "30998332"
---
# <a name="attachments-control-in-powerapps"></a>Vedlegg-kontrollen i PowerApps
Dette er en kontroll som lar brukerne laste ned filer på enhetene sine så vel som laste opp og slette filer fra en SharePoint-liste.

## <a name="limitations"></a>Begrensninger
Vedlegg-kontrollen har følgende midlertidige begrensninger:
1. Nedlasting av vedlegg støttes ikke i Internet Explorer.

1. Opplasting av vedlegg fungerer bare med datakilder for SharePoint-lister.  Støtte for andre datakilder introduseres trinnvis, og starter med CDS.

1. Opplasting og sletting av funksjonalitet fungerer bare i et skjema.  Vedlegg-kontrollen ser deaktivert ut når den er i redigeringsmodus og ikke i et skjema.   Vær oppmerksom på at hvis du vil lagre filtilføyelsene og slettingene i serverdelen, må sluttbrukeren lagre skjemaet.

1. Du kan bare laste opp filer med opptil 10 MB.  

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
**AccessibleLabel** – etiketten som leses av skjermleseren.

**AddAttachmentText** – etiketteksten for koblingen som ble brukt til å legge til et nytt vedlegg.

**[BorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje.

**[BorderStyle](properties-color-border.md)** – om kontrollens kantlinje er **Heltrukket**, **Stiplet**, **Prikket** eller **Ingen**.

**[BorderThickness](properties-color-border.md)**  – tykkelsen på kontrollens kantlinje.

**[DisplayMode](properties-core.md)** – om kontrollen tillater tillegging og sletting av filer (**Rediger**), bare viser data (**Vis**) eller er deaktivert (**Deaktivert**).

**[Høyde](properties-size-location.md)** – avstanden mellom kontrollens øvre og nedre kant.

**MaxAttachmentsText** – teksten som erstatter Legg til fil-koblingen når kontrollen inneholder maksimalt antall tillatte filer.

**NoAttachmentsText** – informasjonstekst som vises til brukeren når det ikke er noen filer vedlagt.

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

Lurer du på hvordan du [legger til og konfigurerer en kontroll](../add-configure-controls.md)?
