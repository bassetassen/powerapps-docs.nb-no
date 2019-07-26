---
ms.openlocfilehash: f1c11fd086a91db6dc0d0629549166bbba547dee
ms.sourcegitcommit: ad203331ee9737e82ef70206ac04eeb72a5f9c7f
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/18/2019
ms.locfileid: "67226496"
---
## <a name="mapping-functions-for-dynamics-365-customer-engagement-plan"></a>Kartfunksjoner for Dynamics 365 Customer Engagement Plan 
 Automatisering av felttjeneste og prosjekttjeneste har nøkkelfunksjoner som avhenger av plassering. For eksempel plasseringen til tjenestekontoer (som definerer hvor tjenester eller oppgaver finner sted), eller start-/sluttplasseringen til ressurser (personer som utfører tjenester eller oppgaver).  For at systemet skal vise disse på et kart, eller beregne avstander mellom punkter, er det nødvendig å bruke en karttjeneste ( i dette tilfellet Bing-kart).  
  
 Dette er arbeidsflyten til og fra Bing-karttjenesten:  
  
|Fra Dynamics 365|Bing-kart returnerer|Obs!|  
|-----------------------|-----------------------|----------|  
|Adresse (konto eller ressurs)|Breddegrad og lengdegrad for adressen (plassering)|Dette omtales som «geokoding» av en adresse.|  
|Sett med plasseringer (breddegrad/lengdegrad)|Avstanden mellom plasseringer|Dette kan brukes til å finne optimale ruter for ressurser, eller til å beregne reisetid.|  
|Sett med plasseringer (breddegrad/lengdegrad)|Kartvisning med plassering som nåler på kartet|Dette brukes til å vise kontoer og ressurser i en kartvisning.|  
  
> [!NOTE]
>  Bortsett fra dataene som er omtalt ovenfor, sendes ingen data til Bing-karttjenesten.
