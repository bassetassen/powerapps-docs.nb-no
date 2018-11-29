---
title: Opprette en løsning | MicrosoftDocs
description: Lær hvordan du oppretter en løsning
ms.custom: ''
ms.date: 10/30/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - PowerApps
author: Mattp123
ms.assetid: e21a4876-08b4-417a-a644-c577a27c5cf1
caps.latest.revision: 12
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="create-a-solution"></a>Opprette en løsning

Ettersom standardløsningen inneholder alle løsningskomponentene kan det være enklere å finne bare løsningskomponentene som du har tilpasset, hvis du oppretter en egen løsning og gjør alle dine tilpassinger der. Dette gjør det også enkelt å eksportere en sikkerhetskopi av din løsning som en mindre fil. Hvis du velger å gjøre dette, må du alltid huske å legge til noen av løsningskomponentene du redigerer, i denne løsningen. Når du oppretter nye løsningskomponenter, bør du alltid opprette dem i sammenheng med denne løsningen. På denne måten vil tilpassingsprefikset for løsningsutgiveren brukes konsekvent. Når du har opprettet løsningskomponenter i løsningen eller lagt til eksisterende løsningskomponenter i denne løsningen, kan du også redigere dem i standardløsningen hvis du ønsker.  
  
 Hvis du vil ha mer informasjon om løsningskonsepter, kan du se [Arbeide med løsninger](solutions-overview.md).  
  
1.  Logg på [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) og velg **Løsninger** fra den venstre navigasjonsruten. 
  
2.  Velg **Ny løsning**, og fyll deretter ut de nødvendige feltene for løsningen.
  
    |Felt|Beskrivelse|  
    |-----------|-----------------|  
    |**Visningsnavn**|Navnet vises i listen over løsninger. Du kan endre dette senere.|  
    |**Navn**|Det unike navnet på løsningen. Dette genereres ved hjelp av verdien du angir i feltet Visningsnavn. Du kan redigere dette før du lagrer løsningen, men når du har lagret løsningen, kan du ikke endre det.|  
    |**Utgiver**|Du kan velge standardutgiveren eller opprette en ny utgiver. Med mindre du planlegger å distribuere din løsning, bør du bare bruke standardutgiveren for organisasjonen.|  
    |**Versjon**|Angi et nummer for versjonen av løsningen. Dette er bare viktig hvis du eksporterer løsningen. Versjonsnummeret skal inkluderes i filnavnet når du eksporterer løsningen.|  
  
3.  Velg **Lagre**.  
  
 Når du har lagret løsningen, vil du kanskje legge til informasjon i felt som ikke er obligatoriske. Disse trinnene er valgfrie. Bruk **Beskrivelse** -feltet for å beskrive løsningen, og velg en HTML-webressurs som en **konfigurasjonsside** for løsningen. Konfigurasjonssiden brukes vanligvis av uavhengige programvareleverandører som distribuerer løsninger. Når dette er angitt, vises en ny **Konfigurasjon**-node under **Informasjon**-noden for å vise denne webressursen. Utviklere vil bruke denne siden til å inkludere instruksjoner eller kontroller slik at du kan angi konfigurasjonsdataene eller starte løsningen.  
  
<a name="BKMK_AddSolutionComponents"></a>   

## <a name="add-solution-components"></a>Legge til løsningskomponenter  
 Når du har opprettet løsningen, vil ikke den inneholde noen løsningskomponenter. Du kan opprette nye løsningskomponenter eller bruke knappen **Legg til eksisterende** i listemenyen for å legge til en hvilken som helst løsningskomponent fra standardløsningen.  
  
 Når du gjør dette, kan det hende at du ser dialogboksen **Mangler obligatoriske komponenter**.  
   
 ![Dialogboksen Legg til nødvendige komponenter](media/crm-itpro-cust-addrequiredcomponents.PNG "Dialogboksen Legg til nødvendige komponenter")  
  
 Denne dialogboksen varsler deg om at løsningskomponenten har avhengigheter i andre løsningskomponenter. Hvis du velger **Nei, ikke ta med nødvendige komponenter**, kan det hende at løsningen mislykkes hvis du importerer den til en annen organisasjon der ikke alle de nødvendige komponentene finnes. Hvis løsningsimporten lykkes, er virkemåten i den andre løsningen kanskje ikke identisk sammenlignet med den opprinnelige organisasjonen, fordi komponentene er konfigurert annerledes enn dem i kildeløsningen.  
  
 Det er vanligvis sikrere å ta med de nødvendige komponentene hvis du har tenkt å eksportere løsningen til en annen organisasjon. Hvis du ikke legger til disse komponentene når du legger til en enkelt løsningskomponent, kan du komme tilbake senere, velge løsningskomponenten du la til, og velge **Legg til nødvendige komponenter** fra menyen.  
  
 Hvis du ikke har til hensikt å eksportere løsningen, eller hvis du bare har tenkt å eksportere den som en uadministrert løsning, og importere den tilbake til den samme organisasjonen, er det ikke nødvendig å ta med nødvendige komponenter. Hvis du noen gang eksporterer løsningen, vil du se en annen advarsel som angir at noen nødvendige komponenter mangler. Hvis du bare vil importere denne løsningen tilbake til den samme organisasjonen, er det OK å ignorere denne advarselen. Trinnene for å redigere programnavigeringen eller båndet uten å bruke en tredjeparts redigeringsverktøy forventer at du skal eksportere løsningen tilbake til den samme organisasjonen.  

> [!IMPORTANT]
>  Hvis du planlegger å inkludere avtaler i løsningen, anbefaler vi på det på det sterkeste at du ikke bare inkluderer avtaler og bare regelmessige avtaler i separate løsninger. Hvis du installerer og avinstallerer separate løsninger med forskjellige avtaletyper, vil det oppstå en SQL Server-feil, og du må opprette avtalene på nytt. 

## <a name="see-also"></a>Se også
 [Bruke løsninger](use-solution-explorer.md)
