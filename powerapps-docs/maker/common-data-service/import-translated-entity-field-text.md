---
title: Importere oversatt enhets- og felttekst med PowerApps | MicrosoftDocs
description: Finn ut hvordan du importerer oversatt enhets- og felttekst
ms.custom: ''
ms.date: 06/19/2018
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
ms.assetid: 3d77d149-819b-45e6-8e70-1fbe54d5c153
caps.latest.revision: 19
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="import-translated-entity-and-field-text-back-into-an-app"></a>Importere oversatt enhets- og felttekst tilbake til en app

Hvis du har tilpasset enhets- eller felttekst, for eksempel feltetiketter eller rullegardinlisteverdier, kan du gi brukere i organisasjonen som ikke arbeider med originalspråkversjonen for miljøet ditt, denne tilpassede teksten på deres eget språk. Hvis du vil gjøre det, eksporterer du tekststrengene for alle tilpassinger, slik at de kan oversettes til de språkene som brukes i organisasjonen.  
  
 Etter oversettelsen må du importere de oversatte tekststrengene til miljøet ditt før brukere kan dra nytte av endringene.  
  
> [!IMPORTANT]
> - Filen du importerer, må være en komprimert fil som inneholder CrmTranslations.xml og [Content_Types]-XML-filen i roten.  
> - Du kan ikke importere oversatt tekst med flere enn 500 tegn. Hvis noen av elementene i oversettingsfilen har mer enn 500 tegn, mislykkes importen. Hvis importen mislykkes, ser du gjennom linjen i filen som forårsaket feilen, reduserer antall tegn og prøver å importere på nytt. Merk også at du må publisere tilpassinger på nytt etter at du har importert oversatt tekst.  
  
1. Åpne [løsningsutforskeren](../model-driven-apps/advanced-navigation.md#solution-explorer).  
  
2. I løsningsutforskeren på handlingsverktøylinjen velger du **Importer oversettelser**.  
3.  I dialogboksen **Importer oversatt tekst** angir du filen som inneholder den oversatte teksten, og deretter velger du **Importer**.  
  
4.  Når importen er fullført, velger du **Lukk**.  
  
> [!NOTE]
>  Publisering av tilpassinger kan forstyrre den ordinære driften av systemet.. Vi anbefaler at du planlegger publisering på tidspunkt der det i minst mulig grad forstyrrer brukerne.  

## <a name="community-tools"></a>Fellesskapsverktøy

[Easy Translator](https://www.xrmtoolbox.com/plugins/MsCrmTools.Translator/) er et verktøy som XrmToolBox-fellesskapet utviklet for Dynamics 365 Customer Engagement. Bruk Easy Translator til å eksportere og importere oversettelser med kontekstavhengig informasjon. 

> [!NOTE]
> Fellesskapsverktøyene støttes ikke av Microsoft. Hvis du har spørsmål om verktøyet, kontakter du utgiveren. Mer informasjon: [XrmToolBox](https://www.xrmtoolbox.com).

## <a name="next-steps"></a>Neste trinn  
 [Eksportere egendefinert enhets- og felttekst for oversetting](export-customized-entity-field-text-translation.md)
