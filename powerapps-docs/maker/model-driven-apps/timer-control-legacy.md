---
title: Modelldrevet tidtakerkontroll for apper i PowerApps | MicrosoftDocs
description: Slik kan du bruke tidtakerkontrollen
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
ms.openlocfilehash: 7df13482e7773abc3e6762f80bd9f6b99c7ba9e6
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/08/2018
ms.locfileid: "39691160"
---
# <a name="model-driven-app-timer-control-overview"></a>Oversikt over modelldrevet tidtakerkontroll for apper

 Bruk en tidtakerkontroll med skjemaer der poster trenger å oppnå en bestemt tidsbasert milepæl. En tidtakerkontroll viser hvor mye tid som er tilgjengelig for å fullføre en handling i oppløsningen til en aktiv post, eller hvor mye tid som er gått siden tidspunktet for når handlingen skulle vært utført. Tidtakerkontroller må som et minimum konfigureres til å vise om handlingen er fullført eller ikke. De kan i tillegg konfigureres til å vise advarsler når betingelsene nærmer seg å ikke fullføres i tide.  
  
 Tidtakerkontroller kan legges til i et skjema for en hvilken som helst enhet, men de brukes oftest til saksenheter, spesielt når de kobles til felt som sporer avtaler for tjenestenivå. Du kan legge til flere tidtakerkontroller i brødteksten til et skjema. Du kan ikke legge dem til toppteksten eller bunnteksten.  
  
 **Datakilde**-egenskaper for tidtakerkontrollen bruker felt for enheten.  
  
-   **Felt for feiltidspunkt** bruker et felt for dato og klokkeslett for å angi tidspunkt.  
  
-   De tre feltene for betingelser bruker ett av feltene **Alternativsett**, **To alternativer**, **Status** eller **Statusårsak** for enheten.  

Hvis du vil opprette en tidtakerkontroll, velger du **Sett inn**-fanen i skjemautforming. Deretter velger du **Tidtaker** på verktøylinjen. 

  ![Sett inn tidtakerkontrollen](media/insert-timer-control.png)

Skriv inn eller velg egenskapene du vil bruke, på egenskaper-siden, og velg **OK**. 

  
<a name="BKMK_TimerControlProperties"></a>   

## <a name="timer-control-properties"></a>Egenskaper for tidtakerkontroll  
 Tabellen nedenfor beskriver egenskapene til en tidtakerkontroll.  
  
|Gruppe|Navn|Beskrivelse|  
|-----------|----------|-----------------|  
|Navn|Navn|**Obligatorisk**. Et unikt navn for kontrollen.|  
||Etikett|**Obligatorisk**. Etiketten som skal vises for tidtakerkontrollen.|  
|Datakilde|Felt for feiltidspunkt|**Obligatorisk**. Velg ett av feltene for dato og klokkeslett for enheten, som skal representere når en milepæl bør være fullført.|  
||Gyldig betingelse|**Obligatorisk**. Velg et felt for enheten for å evaluere gyldigheten til milepælen. Velg deretter hvilket alternativ som indikerer gyldigheten.|  
||Advarselsbetingelse|Velg et felt for enheten for å evaluere om gyldigheten til milepælen er i fare, slik at en advarsel bør vises. Deretter velger du hvilket alternativ som indikerer at en advarsel bør vises.|  
||Annuller betingelse|Velg et felt for enheten for å evaluere om prestasjonen til milepælen bør annulleres. Deretter velger du hvilket alternativ som indikerer at milepælen er annullert.|  

## <a name="next-steps"></a>Neste trinn

[Oversikt over brukergrensesnittet for skjemaredigeringsprogrammet ](form-editor-user-interface-legacy.md)