---
title: 'Kombinasjonsbokskontroll: referanse | Microsoft Docs'
description: Informasjon, inkludert egenskaper og eksempler, om kombinasjonsbokskontrollen
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
ms.date: 09/13/2017
ms.author: fikaradz
ms.openlocfilehash: 4d298e24ea967cbf5cb47638d4296f6efbd758c7
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/22/2018
ms.locfileid: "30995932"
---
# <a name="combo-box-control-in-powerapps"></a>Kombinasjonsbokskontroll i PowerApps
En kontroll som gjør det mulig for brukere å foreta valg ut ifra angitte valgmuligheter.  Støtter søk og flervalg.

## <a name="description"></a>Beskrivelse
En **Kombinasjonsbokskontroll** gjør det mulig for deg å søke etter elementer du vil velge.  Dette søket utføres på serversiden i SearchField-egenskapen, slik at ytelsen ikke påvirkes av store datakilder.  

Enkelt- og flervalgsmodus konfigureres via SelectMultiple-egenskapen.

Når du søker etter elementer som du skal velge, kan du for hvert element velge å vise en enkelt dataverdi, to verdier, eller et bilde og to verdier (Person) ved å endre innstillingene for oppsett i Data-ruten.

## <a name="people-picker"></a>Personvelger
For å bruke **Kombinasjonsboks** som personvelger, velger du **Person**-malen i innstillingene for oppsett i Data-ruten, og konfigurerer de relaterte dataegenskapene slik at de vises for personen under.

## <a name="key-properties"></a>Nøkkelegenskaper
**[Elementer](properties-core.md)** – datakilden det kan foretas valg ut ifra.

**DefaultItems** – de opprinnelig valgte elementene før brukeren tar i bruk kontrollen.

**SelectedItems** – listen over valgte elementer som resultat av brukermedvirkning.

**SelectMultiple** – om brukeren kan velge et enkelt eller flere elementer.

**IsSearchable** – hvorvidt brukeren kan søke etter elementer før vedkommende foretar et valg.

## <a name="additional-properties"></a>Tilleggsegenskaper
**[BorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje.

**[BorderStyle](properties-color-border.md)** – om kontrollens kantlinje er **Heltrukket**, **Stiplet**, **Prikket** eller **Ingen**.

**[BorderThickness](properties-color-border.md)**  – tykkelsen på kontrollens kantlinje.

**[Standard](properties-core.md)** – det opprinnelige valget før det endres av en bruker i enkeltvalgmodus.

**DisplayFields** – liste over felt som vises for hvert element som returneres av søket.  Enklest å konfigurere via Data-ruten i Alternativer for Egenskaper-fanen.

**[DisplayMode](properties-core.md)** – om kontrollen tillater brukerinndata (**Rediger**), viser kun data (**Vis**) eller er deaktivert (**Deaktivert**).

**[Høyde](properties-size-location.md)** – avstanden mellom kontrollens øvre og nedre kant.

**InputTextPlaceholder** – veiledningstekst som vises for sluttbrukere når ingen elementer er valgt.

**OnChange** – hvordan appen responderer når brukeren endrer et utvalg.

**OnNavigate** – hvordan appen responderer når brukeren klikker på et element.

**[OnSelect](properties-core.md)** – hvordan appen responderer når brukeren klikker eller trykker på en kontroll.

**[Synlig](properties-core.md)** – om kontrollen vises eller skjules.

**[Bredde](properties-size-location.md)** – avstanden mellom kontrollens venstre og høyre kant.

**[X](properties-size-location.md)** – avstanden mellom kontrollens venstre kant og den venstre kanten til kontrollens overordnede beholder (eller skjermen, hvis det ikke finnes noen overordnet beholder).

**[Y](properties-size-location.md)** – avstanden mellom kontrollens øvre kant og den øvre kanten til kontrollens overordnede beholder (eller skjermen, hvis det ikke finnes noen overordnet beholder).

## <a name="example"></a>Eksempel
1. Legg til en **Kombinasjonsboks**-kontroll fra Sett inn-fanen på Kontroller-menyen.  
2. Klikk på Alternativer for egenskaper-fanen, klikk på Data.  
3. Velg datakilden, oppsett og tilknyttede egenskaper nedenfor.
4. Angi egenskapen **SelectMultiple** på Avansert-fanen.

    En funksjonell **kombinasjonsboks** vises i appen din.

    Lurer du på hvordan du [legger til og konfigurerer en kontroll](../add-configure-controls.md)?.
