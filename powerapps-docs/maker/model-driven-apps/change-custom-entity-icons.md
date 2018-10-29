---
title: Endre egendefinerte enhetsikoner for modelldrevne apper i PowerApps | MicrosoftDocs
definition: Learn how to change the icon for a custom entity
ms.custom: ''
ms.date: 05/17/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
author: Mattp123
ms.assetid: 477f9792-8207-49ef-8968-45274b5355a8
caps.latest.revision: 19
ms.author: matp
manager: kvivek
tags:
- Links to topic not migrated
ms.openlocfilehash: c625ac14905e49879eb6dc93eff706a7dab18433
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/08/2018
ms.locfileid: "39696586"
---
# <a name="change-model-driven-app-custom-entity-icons"></a>Endre egendefinerte enhetsikoner for modelldrevne apper 

Når du oppretter en egendefinert enhet, tilordnes den automatisk et standardikon. Alle egendefinerte enheter bruker det samme ikonet som standard. Bruk egendefinerte ikoner for å skille hvordan de egendefinerte enhetene ser ut. Du kan ikke endre ikonene som er tilordnet systemenheter.  
  
 Du kan laste opp tre typer enhetsikoner for hver egendefinerte enhet. 

|Ikontype  |Beskrivelse  |
|---------|---------|
|**Ikon for enhetlig grensesnitt**|Må være et skalerbart vektorgrafikkikon (.svg) |
|**Ikon i nettprogram**|Et bilde i SVG-, GIF-, PNG- eller JPG-format, 16x16 piksler i størrelse|
|**Ikon for enhetsskjemaer**|Et bilde i SVG-, GIF-, PNG- eller JPG-format, 32x32 piksler i størrelse|

> [!NOTE]
> Ingen av bildefilene kan være større enn 10 KB.
>
> Når du bruker et skalerbart vektorgrafikkbilde (.svg) som **Ikon i nettprogram** eller **Ikon for enhetsskjemaer**, må det være i standardstørrelse. Da SVG er et XML-dokument, kan du redigere [bredde](https://developer.mozilla.org/docs/Web/SVG/Attribute/width)- og [høyde](https://developer.mozilla.org/docs/Web/SVG/Attribute/height)-verdiene for [SVG](https://developer.mozilla.org/docs/Web/SVG/Element/svg)-elementet med et tekstredigeringsprogram for å definere standardstørrelsen for bildet.

Hver ikontype lagres som en nettressurs. Du kan opprette nettressursene først og deretter angi at ikonene bruker dem, eller du kan opprette den nye nettressursen i dialogboksen **Oppslagspost** ved å merke av for **Ny** mens du angir verdien. Mer informasjon: [Opprett eller rediger nettressurser for å utvide en app](create-edit-web-resources.md)

## <a name="set-the-icons-for-a-custom-entity"></a>Angi ikonene for en egendefinert enhet

Du må bruke løsningsutforsker for å angi enhetsikoner.

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]

### <a name="set-entity-icons"></a>Angi enhetsikoner

1. Velg **Oppdateringsikoner** på kommandolinjen.  
  
2. Velg **Bla gjennom**-knappen ![Oppslag-knappen](media/lookup-button-4.gif) i dialogboksen **Velg nye ikoner** på **Nettklient**-fanen under **Ikon i nettprogram** eller **Ikon for enhetsskjemaer**, til høyre for **Nytt ikon**.
3. Velg eller opprett den riktige nettressursen, og velg deretter **OK**. 
4. Gjør det samme for **Nytt ikon**-feltet på **Enhetlig grensesnitt**-fanen.
5. Velg **OK** for å lukke dialogboksen **Velg nye ikoner**.
6. Velg **Lagre** på kommandolinjen, i **Fil**-menyen.  
7. Når endringene er ferdige, publiserer du dem. Velg **Publiser** i kommandolinjen mens enheten er utvalgt i løsningsutforskeren.
  
## <a name="community-tools"></a>Fellesskapsverktøy

**[Iconator](https://www.xrmtoolbox.com/plugins/MscrmTools.Iconator/)** er et verktøy som XrmToolbox-fellesskapet utviklet for Dynamics 365 Customer Engagement. Les emnet [Utviklerverktøyene for Common Data Service for apper](https://docs.microsoft.com/dynamics365/customer-engagement/developer/developer-tools) for utviklerverktøyene for fellesskapet.

> [!NOTE]
> Fellesskapsverktøyene er ikke et produkt fra Microsoft, og de støttes ikke. Hvis du har spørsmål om verktøyet, kan du kontakte utgiveren. Mer informasjon: [XrmToolBox](https://www.xrmtoolbox.com).

## <a name="next-steps"></a>Neste trinn  
[Opprett en enhet](../common-data-service/create-edit-entities.md)<br />
[Rediger en enhet](../common-data-service/edit-entities.md)
