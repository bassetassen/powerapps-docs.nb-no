---
title: Importer oversatte enheter og felttekst med PowerApps | MicrosoftDocs
description: Lær hvordan du importer oversatte enheter og felttekst
ms.custom: ''
ms.date: 06/19/2018
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
ms.assetid: 3d77d149-819b-45e6-8e70-1fbe54d5c153
caps.latest.revision: 19
ms.author: matp
manager: kvivek
ms.openlocfilehash: e2417f7ad75e327fdfc54d4cd4fdd3f62395326b
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/08/2018
ms.locfileid: "39697737"
---
# <a name="import-translated-entity-and-field-text-back-into-an-app"></a>Importer oversatt enhets- og felttekst til en app

Hvis du har tilpasset enhets- eller felttekst, for eksempel feltetiketter eller listeverdier for rullegardiner, kan du gi brukerne i organisasjonen din som ikke jobber med originalspråkversjonen for miljøet, denne egendefinerte teksten på sitt eget språk. Dette gjør du ved å eksportere tekststrengene for alle tilpasninger, slik at de kan oversettes til språkene du bruker i organisasjonen din.  
  
 Etter oversettelsen må du importere de oversatte strengene til miljøet ditt, før brukere kan dra nytte av endringene.  
  
> [!IMPORTANT]
> - Filen du importerer, må være en komprimert fil som inneholder CrmTranslations.xml og [Content_Types].xml-filen i roten.  
> - Du kan ikke importere oversatt tekst som er mer enn 500 tegn. Hvis noen av elementene i oversettelsesfilen er lengre enn 500 tegn, mislykkes importen. Hvis importen mislykkes, kan du se gjennom linjen i filen som forårsaket feilen, redusere antall tegn, og prøv å importere på nytt. Vær også oppmerksom på at når du har importert oversatt tekst, må du publisere tilpassinger på nytt.  
  
1. Åpne [løsningsutforsker](../model-driven-apps/advanced-navigation.md#solution-explorer).  
  
2. Velg **Importer oversettelser** på verktøylinjen for handlinger i løsningsutforsker.  
3.  I dialogboksen **Importer oversatt tekst** angir du filen som inneholder den oversatte teksten, og velger deretter **Importer**.  
  
4.  Når importen er fullført, velger du **Lukk**.  
  
> [!NOTE]
>  Publisering av tilpassinger kan påvirke normale systemoperasjoner. Vi anbefaler at du planlegger publisering når det er minst mulig forstyrrende for brukerne.  

## <a name="community-tools"></a>Fellesskapsverktøy

[Easy Translator](https://www.xrmtoolbox.com/plugins/MsCrmTools.Translator/) er et verktøy som XrmToolBox-fellesskapet utviklet for Dynamics 365 Customer Engagement. Bruk Easy Translator til å eksportere og importere oversettelser med kontekstinformasjon. 

> [!NOTE]
> Fellesskapsverktøyet støttes ikke av Microsoft. Hvis du har spørsmål om verktøyet, kan du kontakte utgiveren. Mer informasjon: [XrmToolBox](https://www.xrmtoolbox.com).

## <a name="next-steps"></a>Neste trinn  
 [Eksporter tilpasset enhets- og felttekst for oversettelse](export-customized-entity-field-text-translation.md)
