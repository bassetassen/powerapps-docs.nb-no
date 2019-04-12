---
title: Endre navigasjon i et skjema en modelldrevet app i PowerApps | MicrosoftDocs
description: Finn ut hvordan du endrer navigasjonen i et skjema
ms.custom: ''
ms.date: 06/06/2018
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
ms.assetid: 4c379202-9f0e-4003-a49c-efff53e7f79f
caps.latest.revision: 63
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="change-navigation-within-a-model-driven-app-form"></a>Endre navigasjon i et skjema en modelldrevet app

 Navigasjon i et skjema lar appbrukere vise lister over relaterte oppføringer. Alle enhetsrelasjoner har egenskaper som avgjør om de skal vises. Mer informasjon: [Navigasjonsruteelement for primærenhet](../common-data-service/create-edit-1n-relationships-solution-explorer.md#navigation-pane-item-for-primary-entity)  
  
 Enhetsrelasjoner som er konfigurert til vises, kan overstyres i skjemaredigeringsprogrammet. Du kan også inkludere navigasjonskoblinger for å vise webressurser eller andre nettsteder via skjemanavigasjon.  
  
 Hvis du vil ha trinnvise instruksjoner, kan du se [Opprette og redigere enhetsrelasjoner for Common Data Service](../common-data-service/create-edit-entity-relationships.md)  
  
 Hvis du vil aktivere navigasjon, må du først velge **Navigasjon** i **Velg**-gruppen i kategorien **Hjem** i skjemautforming.  
 
> [!div class="mx-imgBorder"] 
> ![Navigasjonskommando](media/navigation-command.png)
 
 I den høyre ruten i **relasjonsutforskeren** kan du filtrere etter 1:N- (én-til-mange) eller N:N-relasjoner (mange-til-mange), eller vise alle tilgjengelige relasjoner. Avmerkingsboksen **Vis bare ubrukte relasjoner for** deaktiveres og velges. Du kan bare legge til hver relasjon én gang.  
 
 > [!div class="mx-imgBorder"] 
 > ![Relasjonsutforsker](media/relationship-explorer.png)

 Hvis du vil legge til relasjoner fra **relasjonsutforskeren**, dobbeltklikker du relasjonen, og den vil bli lagt til under den merkede relasjonen i navigasjonsområdet. Dobbeltklikk på en relasjon i navigasjonsområdet, og dermed kan du endre etiketten i kategorien **Vis**. I kategorien **Navn** vises det informasjon om relasjonen. Bruk **Rediger** for å åpne definisjonen av enheten.  
  
 Det er fem grupper i navigasjonsområdet. Du kan dra dem for å flytte dem og dobbeltklikke dem for å endre etiketten, men du kan ikke fjerne dem. Disse gruppene vises bare når det er noe i dem. Hvis du ikke vil at en gruppe skal vises, legger du ikke til noe i den.  
  
 Bruk **Navigasjonskobling**-knappen i **Kontroll**-gruppen i kategorien **Sett inn** for å legge til en kobling til en webressurs eller ekstern URL-adresse.  
 
 ![Navigasjonskobling](media/navigation-link.png)
 
<a name="BKMK_NavigationLinkProperties"></a>   
### <a name="navigation-link-properties"></a>Egenskaper for navigasjonskobling  
 Navigasjonskoblinger har følgende egenskaper:  
  
|Egenskap|Beskrivelse|  
|--------------|-----------------|  
|Navn|**Nødvendig**: Tekst som skal vises som en etikett.|  
|Ikon|Bruk en webressurs som er 32 x 32 piksler. Det anbefales å bruke et PNG-bilde med gjennomsiktig bakgrunn.|  
|Webressurs|Angi en webressurs som skal vises i hovedruten i skjemaet.|  
|Ekstern URL-adresse|Angi URL-adressen for en side som skal vises i hovedruten i skjemaet.|  

<a name="BKMK_PrivacyNotices"></a>   

## <a name="privacy-notices"></a>Personvernerklæringer  
 [!INCLUDE[cc_privacy_crm_website_preview_control](../../includes/cc-privacy-crm-website-preview-control.md)]    
  
 [!INCLUDE[cc_privacy_multimedia_control](../../includes/cc-privacy-multimedia-control.md)]  

## <a name="next-steps"></a>Neste trinn

[Oversikt over brukergrensesnittet i skjemaredigeringsprogrammet](form-editor-user-interface-legacy.md)
