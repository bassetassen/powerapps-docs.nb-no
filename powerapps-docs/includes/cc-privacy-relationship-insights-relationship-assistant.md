---
ms.openlocfilehash: 40dcde544894751da2696defc76819892659cb25
ms.sourcegitcommit: ad203331ee9737e82ef70206ac04eeb72a5f9c7f
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/18/2019
ms.locfileid: "67224794"
---
Begrenset datautveksling, som inkluderer navnet på en avsender og e-postadresse, i tillegg til utdrag fra brødteksten i e-posten, hentes ved å aktivere Relationship Assistant-funksjonen (men er ikke lagret i [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)]), med hensikten å vise relevante innsikter i e-posten. Relationship Assistant-funksjonen kan videre konfigureres til å hente informasjon når det gjelder nyheter, økonomi og flyreiseinformasjon, ved å sende alle forespørsler til eksterne komponenter, som MSN Money og Bing (som ikke regnes som [!INCLUDE[pn_ms_dyn_365](pn-ms-dyn-365.md)] Core Services). En administrator kan aktivere og deaktivere Relationship Assistant-funksjonen ved å gå til **Innstillinger** > **Konfigurasjon av intelligens**, klikke på **Relationship Assistant**-fanen, og deretter merke av riktig.  
  
 De eksterne komponentene som er involvert med Relationship Assistant-funksjonen er beskrevet i følgende deler.  
  
 **[!INCLUDE[pn_bing](pn-bing.md)]**  
  
 Relationship Assistent bruker [!INCLUDE[pn_bing](pn-bing.md)] til å søke etter relevante nyheter som kan vises til en bruker ved hjelp av kontonavnene fra brukerens [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)]-data.  
  
 **[!INCLUDE[pn_ms_MSN_Money](pn-ms-msn-money.md)]**  
  
 Relationship Assistent bruker [!INCLUDE[pn_ms_MSN_Money](pn-ms-msn-money.md)] til å søke etter relevante nyheter som kan vises til en bruker ved hjelp av kontonavnene fra brukerens [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)]-data.