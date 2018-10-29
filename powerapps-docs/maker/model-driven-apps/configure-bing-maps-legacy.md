---
title: Konfigurer Bing-kart i en modelldrevet app med PowerApps | MicrosoftDocs
ms.custom: ''
ms.date: 06/18/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
ms.assetid: f9729664-561c-4758-86ce-7216d68075d9
caps.latest.revision: 63
ms.author: matp
author: Mattp123
manager: kvivek
ms.openlocfilehash: 44977925bfa92647ddbc29b7a82028f55b146921
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/08/2018
ms.locfileid: "39693752"
---
# <a name="configure-bing-maps-in-a-model-driven-app"></a>Slik konfigurerer du Bing-kart i en modelldrevet app

 Bing-kart kan vises i et skjema for enhetene konto, kontakt, kundeemne, tilbud, ordre, faktura, konkurrent og systembruker. Du kan fjerne Bing-kartområdet i redigeringsprogrammet for skjema, eller legge det til igjen ved å bruke **Bing-kart**-knappen på **Sett inn**-fanen i redigeringsprogrammet for skjema.  
  
 Systeminnstillingen **Vis Bing-kart i skjemaer** må være aktivert for å kunne aktivere Bing-kart.  
  
|Fane|Egenskap|Beskrivelse|  
|---------|--------------|-----------------|  
|**Generelt**|**Etikett**|**Obligatorisk**: en etikett som skal vises for Bing-kart.|  
||**Vis etikett på skjemaet**|Angir om etiketten skal vises.|  
||**Velg en adresse som skal brukes sammen med Bing-kartkontrollen**|Velg hvilken adresse som skal brukes til å gi data til kartet.|  
||**Synlig som standard**|Det er valgfritt å vise Bing-kart, og det kan kontrolleres ved å bruke skript. Mer informasjon: [Alternativer for synlighet](visibility-options-legacy.md)|  
|**Formatering**|**Velg antall kolonner kontrollen bruker**|Når inndelingen som inneholder Bing-kart, har mer enn én kolonne, kan du angi at feltet skal bruke opptil det antallet kolonner inndelingen har.|  
||**Velg antall rader kontrollen bruker**|Du kan styre høyden på Bing-kart ved å angi et antall rader.|  
||**Utvid for å bruke tilgjengelig plass automatisk**|Du kan tillate at høyden på Bing-kart utvides til tilgjengelig plass.|  

## <a name="next-steps"></a>Neste trinn

[Bruk hovedskjema og tilknyttede komponenter](use-main-form-and-components.md)