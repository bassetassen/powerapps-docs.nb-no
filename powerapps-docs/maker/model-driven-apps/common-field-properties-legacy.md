---
title: Felles feltegenskaper for modelldrevne apper i PowerApps | MicrosoftDocs
description: Slik fungerer felles feltegenskaper for hovedskjema i Dynamics 365 for Customer Engagement
Keywords: Main form; Common field properties; Dynamics 365
author: Mattp123
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
ms.author: matp
manager: kvivek
ms.date: 06/18/2018
ms.service: crm-online
ms.topic: article
ms.assetid: 2b91ee28-7f09-435e-9fae-5225aa698e22
ms.openlocfilehash: 74e67dd4299d06a54d5ec85765e4e5d03710b432
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/08/2018
ms.locfileid: "39691203"
---
# <a name="model-driven-app-common-field-properties"></a>Felles feltegenskaper for modelldrevne apper

 Feltene i et skjema viser kontrollene som brukes til å vise eller redigere data i en enhetspost. Felt kan formateres til å bruke opptil fire kolonner i en inndeling.  

Du har tilgang til **Felles feltegenskaper** i løsningsutforsker. Utvid enheten du vil ha under **Komponenter**, utvid **Enheter**, velg enheten du vil ha, og velg deretter **Skjemaer.** Åpne skjemaet av typen **Hoved** i listen over skjemaer. Deretter dobbeltklikker du på et av feltene for å vise Felles feltegenskaper.

![felles feltegenskaper](media/common-field-properties.png)
  
Tabellen nedenfor beskriver egenskaper alle felt har. Visse typer felt har spesielle egenskaper. Disse beskrives i [Spesielle feltegenskaper](special-field-properties-legacy.md).  
  
|Fane|Egenskap|Beskrivelse|  
|---------|--------------|-----------------|  
|**Skjerm**|**Etikett**|**Obligatorisk**: Som standard samsvarer etiketten med visningsnavnet for feltet. Du kan overstyre dette navnet for skjemaet ved å angi en annen etikett her.|  
||**Vis etikett på skjemaet**|Du kan velge ikke å vise etiketten i det hele tatt.|  
||**Feltets virkemåte**|Angi feltnivåets virkemåte ved å bruke avmerkingsboksene.|  
||**Låsing**|Dette hindrer at feltet fjernes fra skjemaet ved et uhell. Dette hindrer at konfigurasjon du har brukt på feltet, for eksempel hendelsesbehandling, fjernes hvis feltet fjernes. Hvis du vil fjerne dette feltet, må en tilpasser fjerne denne innstillingen først.|  
||**Synlighet**|Det er valgfritt å vise feltet, og det kan kontrolleres ved å bruke skript. Mer informasjon: [Alternativer for synlighet](visibility-options-legacy.md)|  
||**Tilgjengelighet**|Velg om du vil at fanen skal være tilgjengelig på telefonen.|
|**Formatering**|**Velg antall kolonner kontrollen bruker**|Når inndelingen som inneholder feltene, har mer enn én kolonne, kan du angi at feltet skal bruke opptil det antallet kolonner inndelingen har.|  
|**Detaljer**|**Visningsnavn**, **Navn** og **Beskrivelse**|Disse skrivebeskyttede feltene er for referanse. Klikk på **Rediger**-knappen for enkel tilgang til feltdefinisjonen hvis du vil redigere den.<br /><br /> Hver forekomst av et felt i skjemaet har en navneegenskap, slik at den kan refereres til i skjemaskript, men dette navnet administreres av programmet. Den første forekomsten av feltet er navnet på feltet som ble angitt da det ble opprettet. Mer informasjon: [Opprett og rediger felt](../common-data-service/create-edit-fields.md)<br /><br /> For hver ekstra gang et felt inkluderes i et skjema, tilføyer navnet et tall som begynner med 1 på slutten. Så hvis feltnavnet er 'new_cost', er den første forekomsten 'new_cost', den andre er 'new_cost1', og så videre, for hver forekomst av feltet i skjemaet.<br /><br />**Obs!** Feltet **beskrivelse**-verdi viser verktøytipstekst for feltet når markøren flyttes over feltet.|  
|**Hendelser**|**Skjemabiblioteker**|Angi JavaScript-nettressurser som skal brukes i `OnChange` hendelsesbehandlingen for feltet.<br /><br />|  
||**Hendelsesbehandling**|Konfigurer funksjonene fra skjemabiblioteker som bør kalles for felt `OnChange`-hendelsen. Mer informasjon: [Konfigurer hendelsesbehandlinger](configure-event-handlers-legacy.md)|  
|**Forretningsregler**|**Forretningsregler**|Vis og administrer forretningsregler som refererer til dette feltet. Mer informasjon: [Opprett forretningsregler og -anbefalinger](create-business-rules-recommendations-apply-logic-form.md)|  
|**Kontroller**|**Kontroller**|Legg til kontroller, og angi tilgjengeligheten på nettet, telefon og nettbrett.|  

## <a name="next-steps"></a>Neste trinn

[Bruk hovedskjema og tilknyttede komponenter](use-main-form-and-components.md)
