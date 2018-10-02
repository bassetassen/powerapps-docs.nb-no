---
title: Egenskaper for hurtigvisningskontroll for hovedskjemaer for modelldrevne apper i PowerApps | MicrosoftDocs
description: Forstå egenskapene for hurtigvisningskontroll for hovedskjemaer
Keywords: Quick view control properties; Dynamics 365; Main forms
author: Mattp123
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
ms.author: matp
manager: kvivek
ms.date: 06/06/2018
ms.service: crm-online
ms.topic: article
ms.assetid: 68f68d5b-6c71-4b95-bb46-d48c59d9008e
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="model-driven-app-quick-view-control-properties"></a>Egenskaper for hurtigvisningskontroll for modelldrevne apper

En hurtigvisningskontroll i et skjema i en modelldrevet app viser data fra en oppføring som er valgt i et oppslag i skjemaet. Dataene som vises i kontrollen, defineres ved hjelp av et hurtigvisningsskjema. Dataene som vises, kan ikke redigeres, men når hovedfeltet inkluderes i hurtigvisningsskjemaet, blir dette en kobling for å åpne den relaterte oppføringen. Mer informasjon: [Opprette og redigere hurtigvisningsskjemaer](create-edit-quick-view-forms.md)  

> [!div class="mx-imgBorder"] 
> ![Hurtigvisningsskjema for kontakt i skjemaet for forretningsforbindelse](media/quick-view-form-contact.png "Hurtigvisningsskjema for kontakt i skjemaet for forretningsforbindelse")  

Du kan få tilgang til **Egenskaper for hurtigvisningskontroll** fra PowerApps-nettstedet. 
1.  På [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)-området velger du **Modelldrevet** (nederst til venstre i navigasjonsruten).  

     ![Modelldrevet utformingsmodus](media/model-driven-switch.png)

2.  Utvid **Data**, velg **Enheter**, velg enheten du vil bruke, og velg deretter **Skjemaer**-kategorien. 

3. I listen over skjemaer åpner du skjemaet av typen **Hoved**. I kategorien **Sett inn** velger du **Hurtigvisningsskjema** for å vise egenskapene for hurtigvisningkontroll.

    ![hurtigvisningskontroll](media/quick-view-control.png)
  
|Egenskap|Beskrivelse|  
|--------------|-----------------|  
|**Navn**|**Nødvendig**: Det unike navnet for hurtigvisningsskjemaet som skal brukes ved referanse til det i skript.|  
|**Etikett**|**Nødvendig**: En etikett som skal vises i hurtigvisningsskjemaet.|  
|**Vis etikett i skjemaet**|Viser etiketten i skjemaet.|  
|**Oppslagsfelt**|Velg ett av oppslagsfeltene som er inkludert i skjemaet.|  
|**Relatert enhet**|Denne verdien avhenger av **oppslagsfeltet** du velger. Vanligvis er dette hovedenheten for 1:N-enhetsrelasjonen for oppslaget.<br /><br /> Hvis enheten har oppslaget **Potensiell kunde** som kan godta en forretningsforbindelse eller en kontakt i feltet **Hurtigvisningsskjema**, kan du velge et hurtigvisningsskjema for forretningsforbindelses og kontakt ved å endre denne verdien og deretter velge et annet hurtigvisningsskjema.|  
|**Hurtigvisningsskjema**|Hvis **Relatert enhet** har hurtigvisningsskjemaer, kan du velge dem her. Hvis ikke kan du velge **Ny** for å opprette et.<br /><br /> Velg **Rediger** for å endre det valgte hurtigvisningsskjemaet.|  
|**Tilleggsegenskaper**|Du kan angi standard gjengivelsesstil ved å merke av i avmerkingsboksen.|

## <a name="next-steps"></a>Neste trinn

[Bruk hovedskjemaet og komponentene i skjemaet](use-main-form-and-components.md)
 
