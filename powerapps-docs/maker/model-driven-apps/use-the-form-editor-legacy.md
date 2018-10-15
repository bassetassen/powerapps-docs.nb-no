---
title: Endre navigasjon i et modelldrevet appskjema i PowerApps | MicrosoftDocs
description: Finn ut hvordan du endrer navigasjonen i et skjema
ms.custom: ''
ms.date: 06/06/2018
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
ms.assetid: 4c379202-9f0e-4003-a49c-efff53e7f79f
caps.latest.revision: 63
ms.author: matp
manager: kvivek
ms.openlocfilehash: 5a8156875f669854a4ba4649e50a23e340f3ceff
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/08/2018
ms.locfileid: "39690056"
---
# <a name="change-navigation-within-a-model-driven-app-form"></a>Endre navigasjon i et modelldrevet appskjema

 Navigasjon i et skjema gjør at appbrukere kan vise lister med relaterte poster. Hver enhetsrelasjon har egenskaper som kontrollerer om den skal vises. Mer informasjon: [Navigasjonsruteelement for primær enhet](../common-data-service/create-edit-1n-relationships-solution-explorer.md#navigation-pane-item-for-primary-entity)  
  
 Alle enhetsrelasjoner som er konfigurert til å vises, kan overstyres i redigeringsprogrammet for skjema. Du kan også inkludere navigasjonskoblinger for å vise nettressurser eller andre nettsteder via skjemanavigasjon.  
  
 Hvis du vil ha trinnvise instruksjoner, kan du se [Opprett og rediger enhetsrelasjoner for Common Data Service for apper](../common-data-service/create-edit-entity-relationships.md)  
  
 Hvis du vil aktivere redigeringsnavigasjon, må du først velge **Navigasjon** fra **Velg**-gruppen på **Hjem**-fanen i skjemautforming.  
 
 ![Navigasjonskommando](media/navigation-command.png)
 
 Du kan filtrere etter 1:N (en-til-mange)- eller N:N (mange-til-mange)-relasjoner, i den høyre ruten fra **Relasjonsutforsker**, eller vise alle tilgjengelige relasjoner. **Avmerkingsboksen Vis bare ubrukte relasjoner** er deaktivert og valgt. Så du kan bare legge til hver relasjon én gang.  
  
 ![Relasjonsutforsker](media/relationship-explorer.png)

 Hvis du vil legge til en relasjon fra **Relasjonsutforsker**, dobbeltklikker du på relasjonen, så legges den til under relasjonen som for øyeblikket er valgt i navigasjonsområdet. Dobbeltklikk på en relasjon i navigasjonsområdet, så kan du endre etiketten på **Visning**-fanen. Du ser informasjon om relasjonen på **Navn**-fanen. Bruk **Rediger**-knappen for å åpne definisjonen av enheten.  
  
 Det finnes fem grupper i navigasjonsområdet. Du kan dra dem for å flytte dem, og dobbeltklikke på dem for å endre etiketten, men du kan ikke fjerne dem. Disse gruppene vises bare når det er noe i dem. Hvis du vil at en gruppe ikke skal vises, lar du være å legge noe i den.  
  
 Bruk **Navigasjonskobling**-knappen i **Kontroll**-gruppen på **Sett inn**-fanen for å legge til en kobling i en nettressurs eller ekstern nettadresse.  
 
 ![Navigasjonskobling](media/navigation-link.png)
 
<a name="BKMK_NavigationLinkProperties"></a>   
### <a name="navigation-link-properties"></a>Egenskaper for navigasjonskobling  
 Navigasjonskoblinger har følgende egenskaper:  
  
|Egenskap|Beskrivelse|  
|--------------|-----------------|  
|Navn|**Nødvendig**: teksten som skal vises som en etikett.|  
|Ikon|Bruk en nettressurs på 32 x 32 piksler. Bruk av PNG-bilde med en gjennomsiktig bakgrunn anbefales.|  
|Nettressurs|Angi en nettressurs som skal vises i hovedruten i skjemaet.|  
|Ekstern nettadresse|Angi at nettadressen til en side skal vises i hovedruten i skjemaet.|  

<a name="BKMK_PrivacyNotices"></a>   

## <a name="privacy-notices"></a>Erklæring om personvern  
 [!INCLUDE[cc_privacy_crm_website_preview_control](../../includes/cc-privacy-crm-website-preview-control.md)]    
  
 [!INCLUDE[cc_privacy_multimedia_control](../../includes/cc-privacy-multimedia-control.md)]  

## <a name="next-steps"></a>Neste trinn

[Oversikt brukergrensesnittet for redigeringsprogrammet for skjema](form-editor-user-interface-legacy.md)