---
title: Endre egendefinerte enhetsikoner for modelldrevet app i PowerApps | MicrosoftDocs
definition: Learn how to change the icon for a custom entity
ms.custom: ''
ms.date: 05/17/2018
ms.reviewer: ''
ms.service: powerapps
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
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="change-model-driven-app-custom-entity-icons"></a>Endre egendefinerte enhetsikoner for modelldrevet app 

Når du oppretter en egendefinert enhet, tilordnes den automatisk et standardikon. Alle egendefinerte enheter bruker det samme ikonet som standard. Bruk egendefinerte ikoner for å skille utseendet på de egendefinerte enhetene. Du kan ikke endre ikonene som er tilordnet systemenheter.  
  
 Du kan laste opp tre typer enhetsikoner for hver egendefinerte enhet. 

|Ikontype  |Beskrivelse  |
|---------|---------|
|**Enhetlig grensesnitt-ikon**|Må være et ikon for skalerbar vektorgrafikk (.svg) |
|**Ikon i webprogram**|Et SVG-, GIF-, PNG- eller JPG-formatbilde på 16 x 16 piksler.|
|**Ikon for enhetsskjemaer**.|Et SVG-, GIF-, PNG- eller JPG-formatbilde på 32 x 32 piksler.|

> [!NOTE]
> Alle bildefiler kan ikke være større enn 10 kB.
>
> Når du bruker et SVG-bilde (scalable vector graphic – skalerbar vektorgrafikk) som **Ikon i webprogram** eller **Ikon for enhetsskjema**, må det ha angitt standardstørrelse. Siden SVG er et XML-dokument, kan du redigere [svg](https://developer.mozilla.org/docs/Web/SVG/Element/svg)-elementet [bredde](https://developer.mozilla.org/docs/Web/SVG/Attribute/width)- og [høyde](https://developer.mozilla.org/docs/Web/SVG/Attribute/height)-verdiene i et tekstredigeringsprogram for å definere standardstørrelsen på bildet.

Hver ikontype lagres som en webressurs. Du kan opprette webressursene først og deretter angi ikonene for å bruke dem, eller du kan opprette den nye webressursen i **Oppslagsoppføring**-dialogboksen ved å velge **Ny** under angivelse av verdien. Mer informasjon: [Opprette eller redigere webressurser for å utvide en app](create-edit-web-resources.md)

## <a name="set-the-icons-for-a-custom-entity"></a>Angi ikonene for en egendefinert enhet.

Du må bruke løsningsutforsker for å angi enhetsikoner.

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]

### <a name="set-entity-icons"></a>Angi enhetsikoner

1. Velg **Oppdater ikoner** på kommandolinjen.  
  
2. I dialogboksen **Velg nye ikoner**, i kategorien **Webklient** under **Ikon i webprogram** eller **Ikon for enhetsskjema**, til høyre for **Nytt ikon**, velger du **Bla gjennom**-knappen ![Oppslag-knappen](media/lookup-button-4.gif).
3. Velg eller opprett den aktuelle webressursen, og velg deretter **OK**. 
4. I **Enhetlig grensesnitt**-kategorien gjør du det samme for **Nytt ikon**-feltet.
5. Velg **OK** for å lukke dialogboksen **Velg nye ikoner**.
6. På kommandolinjen, på **Fil**-menyen velger du **Lagre**.  
7. Når endringene er fullført, publiserer du dem. Velg **Publiser** på kommandolinjen når enheten er valgt i løsningsutforskeren.
  
## <a name="community-tools"></a>Fellesskapsverktøy

**[Iconator](https://www.xrmtoolbox.com/plugins/MscrmTools.Iconator/)** er et verktøy som XrmToolbox-fellesskapet utviklet for Dynamics 365 Customer Engagement. Se [Utviklerverktøy for Common Data Service](https://docs.microsoft.com/dynamics365/customer-engagement/developer/developer-tools)-emnet for verktøy utviklet av fellesskapet.

> [!NOTE]
> Fellesskapsverktøy er ikke fra Microsoft og det er ikke kundestøtte for disse. Hvis du har spørsmål om verktøyet, kontakter du utgiveren. Mer informasjon: [XrmToolBox](https://www.xrmtoolbox.com).

## <a name="next-steps"></a>Neste trinn  
[Opprette en enhet](../common-data-service/create-edit-entities.md)<br />
[Redigere en enhet](../common-data-service/edit-entities.md)
