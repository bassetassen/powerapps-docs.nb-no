---
title: Deaktivere eller aktivere en konto eller kontakt i en modell drevet app | MicrosoftDocs
ms.custom: ''
author: mduelae
manager: kvivek
ms.service: powerapps
ms.component: pa-user
ms.topic: conceptual
ms.date: 11/16/2018
ms.author: mduelae
ms.reviewer: ''
ms.assetid: ''
search.audienceType:
- enduser
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: aa397d26d3a93812a72c6de1d1e7b996577c6bba
ms.sourcegitcommit: 483c777a1537ccab6a2a2da6a5d1fe4470dd0e7e
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/19/2019
ms.locfileid: "63318443"
---
---
# <a name="deactivate-or-activate-an-account-or-contact"></a>Deaktivere eller aktivere en konto eller kontakt

I en modell drevet app kan du deaktivere en konto eller en kontakt i stedet for å slette den. Dette sikrer integriteten til revisjons sporet som er knyttet til denne posten.  
  
En deaktivert konto eller kontakt blir inaktiv, noe som betyr at den ikke kan redigeres eller brukes til å opprette nye relasjoner med andre poster. Alle relasjoner som er opprettet med den deaktiverte varen, er imidlertid fremdeles tilgjengelige.  
  
Hvis du senere må aktivere en deaktivert konto på nytt, er det enkelt å gjøre det.   
  
## <a name="deactivate-an-account-or-contact"></a>Deaktiver en konto eller kontakt 
  
1.  Gå til **forretnings forbindelser** eller **kontakter**fra menyen til venstre.  
  
2.  Velg den aktive kontoen eller kontakten du vil deaktivere, på kommando linjen Velg **Deaktiver**, og bekreft deretter deaktivering.

    > [!div class="mx-imgBorder"]
    > ![Deaktiver en konto i powerapps](media/DeactiveAccounts.png "Deaktiver en konto i powerapps")


## <a name="activate-an-account-or-contact"></a>Aktiver en konto eller kontakt  
  
1.  Gå til **forretnings forbindelser** eller **kontakter**fra menyen til venstre. 
  
2.  Gå til listen over **system visninger** .

3.  Velg **inaktive kontoer** eller **inaktive kontakter**.  
  
4.  Velg de inaktive kontoene eller kontaktene du vil aktivere.

5.  Velg **Aktiver**, og bekreft deretter aktiveringen.  

    > [!div class="mx-imgBorder"]
    > ![Aktiver en konto i powerapps](media/ActiveAccounts.png "Aktiver en konto i powerapps")  



