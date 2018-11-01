---
title: Tidtakerkontroll i modelldrevne apper i PowerApps | MicrosoftDocs
description: Forstå hvordan du kan bruke tidtakerkontrollen
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
ms.assetid: b2b64771-083b-42f9-a3d5-2218f9d8a713
caps.latest.revision: 63
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="model-driven-app-timer-control-overview"></a>Oversikt over tidtakerkontroll i modelldrevne apper

 Bruk en tidtakerkontroll med skjemaer der oppføringer må oppfylle en bestemt tidsbasert milepæl. En tidtakerkontroll viser brukere hvor mye tid som er tilgjengelig til å fullføre en handling i løsningen av en aktiv oppføring, eller hvor mye tid har gått siden fristen for fullføring av handlingen. Tidtakerkontroller må som et minimum konfigureres til å vise fullført eller mislykket fullføring av handlingen. De kan i tillegg konfigureres til å vise advarsler når betingelsene nærmer seg feil.  
  
 En tidtakerkontroll kan legges til i et skjema for en hvilken som helst enhet, men de brukes oftest for saksenheten, spesielt når de er koblet til felt som sporer servicenivåavtaler. Du kan legge til flere tidtakerkontroller i brødteksten i et skjema. Du kan ikke legge dem til i toppteksten eller bunnteksten.  
  
 Tidtakerkontrollenegenskapen **Datakilde** bruke felt for enheten.  
  
-   **Felt for feiltidspunkt** bruker et dato-/klokkeslettfelt til å angi klokkeslettet.  
  
-   De tre betingelsesfeltene bruker ett av feltene **Alternativsett**, **To alternativer**, **Status** eller **Statusårsaken** for enheten.  

Du kan opprette en tidtakerkontroll i skjemautforming ved å velge kategorin **Sett inn** og deretter velge **Tidtaker** på verktøylinjen. 

  > [!div class="mx-imgBorder"] 
  > ![Sette inn tidtakerkontroll](media/insert-timer-control.png)

På egenskapssiden for tidtakerkntrollen angir eller velger du egenskapene du ønsker, og velg deretter **OK**. 

  
<a name="BKMK_TimerControlProperties"></a>   

## <a name="timer-control-properties"></a>Egenskaper for tidtakerkontroll  
 Tabellen nedenfor beskriver egenskapene for tidtakerkontrollen.  
  
|Gruppe|Navn|Beskrivelse|  
|-----------|----------|-----------------|  
|Navn|Navn|**Required**. Et unikt navn for kontrollen.|  
||Etikett|**Required**. Etiketten som vises for tidtakerkontrollen.|  
|Datakilde|Felt for feiltidspunkt|**Required**. Velg ett av feltene for dato og klokkeslett for enheten som skal representeres når en milepæl skal være fullført.|  
||Gyldig betingelse|**Required**. Velg et felt for enheten for å evaluere hvor vellykket milepælen er, og velg deretter alternativet som angir at fullført.|  
||Advarselsbetingelse|Velg et felt for enheten til å evaluere om en vellykket milepælen er i fare, slik at en advarsel skal vises, og velg deretter alternativet som angir at en advarsel skal vises.|  
||Annuller betingelse|Velg et felt for enheten til å vurdere om oppnåelse av milepælen skal avbrytes, og velg deretter hvilket alternativ som angir at milepælen er avbrutt.|  

## <a name="next-steps"></a>Neste trinn

[Oversikt over brukergrensesnittet i skjemaredigeringsprogrammet](form-editor-user-interface-legacy.md)
