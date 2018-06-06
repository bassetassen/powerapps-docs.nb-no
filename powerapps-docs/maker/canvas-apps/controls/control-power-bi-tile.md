---
title: 'Kontrollen Power BI-flis: referanse | Microsoft Docs'
description: Informasjon, inkludert egenskaper og eksempler, om kontrollen for Power BI-flis
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
ms.date: 07/07/2016
ms.author: fikaradz
ms.openlocfilehash: 1f351877e3c05b83b4bd9cfa104a7eb22cef5028
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/22/2018
ms.locfileid: "30997017"
---
# <a name="power-bi-tile-control-in-powerapps"></a>Kontrollen for Power BI-flis i PowerApps
En kontroll som viser en [Power BI ](https://powerbi.microsoft.com)-flis i en app.

## <a name="description"></a>Beskrivelse
Dra nytte av den eksisterende dataanalysen og rapporteringen din ved å vise **[Power BI-fliser](https://docs.microsoft.com/power-bi/service-dashboard-tiles)** i appene dine.  Velg flisen du ønsker å vise, ved å angi egenskapene **Workspace**, **Dashboard** og **Tile** i **Data**-fanen i panelet for alternativer.

## <a name="sharing-and-security"></a>Deling og sikkerhet
Når PowerApp deles, blir den tilgjengelig for alle brukere som har tilgangsrettigheter til appen.  Men for å kunne gjøre Power BI-innhold synlig for brukerne, må instrumentbordet der flisen kommer fra, være [delt](https://docs.microsoft.com/power-bi/service-how-to-collaborate-distribute-dashboards-reports) med brukeren på Power BI.  Dette sikrer at Power BI-delingstillatelser er fulgt når Power BI-innhold er tilgjengelig i en app.

## <a name="key-properties"></a>Nøkkelegenskaper
**Workspace** – Power BI-arbeidsområdet flisen kommer fra.

**Dashboard** – Power BI-instrumentbordet flisen kommer fra.

**Tile** – navnet på Power BI-flisen du vil vise.

## <a name="additional-properties"></a>Tilleggsegenskaper
**[BorderColor](properties-color-border.md)** – fargen på kontrollens kantlinje.

**[BorderStyle](properties-color-border.md)** – om kontrollens kantlinje er **Heltrukket**, **Stiplet**, **Prikket** eller **Ingen**.

**[BorderThickness](properties-color-border.md)** – tykkelsen til kontrollens kantlinje.

**[DisplayMode](properties-core.md)** – om kontrollen tillater brukerinndata (**Edit**), bare viser data (**View**) eller er deaktivert (**Disabled**).

**[Height](properties-size-location.md)** – avstanden mellom kontrollens øvre og nedre kant.

**[OnSelect](properties-core.md)** – hvordan appen reagerer når brukeren klikker eller trykker på en kontroll. Standard virkemåte fører brukeren til Power BI-rapporten som er forbundet med flisen.

**[Visible](properties-core.md)** – om kontrollen vises eller skjules.

**[Width](properties-size-location.md)** – avstanden mellom venstrekanten og høyrekanten til en kontroll.

**[X](properties-size-location.md)** – avstanden mellom kontrollens venstre kant og den venstre kanten til kontrollens overordnede beholder (eller skjermen, hvis det ikke finnes noen overordnet beholder).

**[Y](properties-size-location.md)** – avstanden mellom kontrollens øvre kant og den øvre kanten til kontrollens overordnede beholder (eller skjermen, hvis det ikke finnes noen overordnet beholder).

## <a name="example"></a>Eksempel
1. Legg til en kontroll for en **Power BI-flis** fra **Sett inn**-fanen på **Kontroller**-menyen.  
2. I **Data**-fanen på panelet Alternativer velger du Mitt arbeidsområde for **Arbeidsområde**-innstillingen.  Velg et instrumentbord fra listen over instrumentbord og en flis fra listen over fliser.
   
    Kontrollen gjengir Power BI-flisen.
   
    Vet du ikke hvordan du [legger til og konfigurerer en kontroll](../add-configure-controls.md)?
   
   Har du ikke Power BI? [Registrer deg](https://docs.microsoft.com/power-bi/service-self-service-signup-for-power-bi).

