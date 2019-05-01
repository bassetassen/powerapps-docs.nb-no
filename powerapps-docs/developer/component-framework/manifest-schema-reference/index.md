---
title: Manifestskjemareferanse for PowerApps-komponenten Framework | Microsoft Docs
description: ''
keywords: ''
ms.author: nabuthuk
manager: ''
ms.date: 06/4/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 045a395b-4475-48dd-8f67-6bc2b33cd89c
ms.openlocfilehash: 88e9d35792d86e279b9af4a19eaff288643412ca
ms.sourcegitcommit: c52c1869510a9a37d9f7b127e06f07583529588b
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/26/2019
ms.locfileid: "64524316"
---
# <a name="manifest-schema-reference"></a>Manifestskjemareferanse

[!INCLUDE[cc-beta-prerelease-disclaimer](../../../includes/cc-beta-prerelease-disclaimer.md)]

Denne delen inneholder referansedokumentasjon for manifestskjema som er generert ved hjelp av PowerApps CLI.

|Element|Beskrivelse|
|----|-----------|
|[Kode](code.md)|[!INCLUDE [code-description](includes/code-description.md)]|
|[Kontroll](control.md)|[!INCLUDE [control-description](includes/control-description.md)]|
|[css](css.md)|[!INCLUDE [css-description](includes/css-description.md)]|
|[datasett](data-set.md)|[!INCLUDE [data-set-description](includes/data-set-description.md)]|
|[html](html.md)|[!INCLUDE [html-description](includes/html-description.md)]|
|[img](img.md)|[!INCLUDE [img-description](includes/img-description.md)]|
|[manifest](manifest.md)|Manifestet er metadatafilen som definerer en komponent. Det er et XML-dokument som beskriver<br/> – Navneområdet til komponenten.<br/> – Typen data det kan konfigureres til, enten et felt eller et datasett.<br/> – Egenskaper som kan konfigureres i programmet når komponenten er lagt til.<br/> – En liste over ressursfiler som komponenten trenger.<br/> – Én av dem må være en JavaScript-nettressurs. Denne JavaScript-en må inkludere en funksjon som vil instansiere et objekt. Dette implementerer et grensesnitt som viser metoder som kreves for at komponenten som skal fungere. Dette kalles biblioteket for komponentimplementering.<br/> – Navnet på en JavaScript-funksjon i biblioteket for komponentimplementering som vil returnere et objekt som gjelder det påkrevde grensesnittet.<br/> Når noen konfigurerer en komponent i programmet, filtrerer dataene i manifestet de tilgjengelige komponentene slik at bare gyldige komponenter for konteksten er tilgjengelige for konfigurasjon. Egenskapene som er definert i manifestet for en komponent gjengis som konfigurasjonsfelt, slik at personen som konfigurerer kontrollen kan angi verdier. Disse egenskapsverdiene blir deretter tilgjengelige for komponentfunksjonen ved kjøretid.|
|[egenskap](property.md)|[!INCLUDE [property-description](includes/property-description.md)]|
|[egenskapssett](property-set.md)|[!INCLUDE [property-set-description](includes/property-set-description.md)]|
|[ressurser](resources.md)|[!INCLUDE [resources-description](includes/resources-description.md)]|
|[resx](resx.md)|[!INCLUDE [resx-description](includes/resx-description.md)]|
|[typegruppe](type-group.md)|[!INCLUDE [type-group-description](includes/type-group-description.md)]|


### <a name="related-topics"></a>Relaterte emner

[Manifestskjemareferanse for PowerApps-komponenten Framework](index.md)<br/>
[API-referanse for PowerApps-komponenten Framework](../reference/index.md)<br/>
[Oversikt over PowerApps-komponenten Framework](../overview.md)