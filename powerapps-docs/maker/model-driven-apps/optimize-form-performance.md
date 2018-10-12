---
title: Optimer ytelsen til modelldrevet appskjema i PowerApps | MicrosoftDocs
description: Finn ut hvordan du unngår skjemadesign som forårsaker at et skjema lastes inn sakte
ms.custom: ''
ms.date: 06/27/2018
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
ms.assetid: 59cfa5e6-638a-437f-a462-fddfd26fb07d
caps.latest.revision: 8
ms.author: matp
manager: kvivek
ms.openlocfilehash: c9dd764fe565b59e68411dabf453207c4e01a320
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/08/2018
ms.locfileid: "39690675"
---
# <a name="optimize-model-driven-app-form-performance"></a>Optimer ytelsen til modelldrevet appskjema

Skjemaer som lastes inn sakte kan redusere produktivitet og brukerimplementering. Følg disse anbefalingene for å maksimere hvor raskt skjemaene lastes inn. Mange av disse anbefalingene handler om hvordan en utvikler kan implementere skjemaskript for organisasjonen. Husk å diskuter disse anbefalingene med utviklerne som oppretter skjemaskript for skjemaene.  
  
<a name="BKMK_FormDesign"></a>   
## <a name="form-design"></a>Skjemautforming  
 Tenk over samhandlingen brukeren har med skjemaet og mengden data som må vises i det.  
  
 **Ikke bruk for mange felt**  
 Jo flere felt du bruker i et skjema, jo mer data må overføres fra Internett eller Intranett for å vise hver post.  
  
<a name="BKMK_FormScripts"></a>   
## <a name="form-scripts"></a>Skjemaskript  
 Når du har tilpasninger som bruker skjemaskript, må du sørge for at utvikleren forstår disse strategiene for å forbedre ytelsen.  
  
 **Unngå å inkluder unødvendige JavaScript-webressursbiblioteker**  
 Jo flere skript du legger til i skjemaet, jo lengre tid vil det ta for å laste dem ned. Skript er vanligvis hurtigbufret i nettleseren etter at de ble lastet inn første gang, men ytelsen første gangen et skjema ble vist skaper ofte et betydelig inntrykk.  
  
 **Unngå å laste inn alle skriptene i Onload-hendelsen**  
 Hvis du har kode som bare støtter `OnChange`-hendelser for felt eller `OnSave`-hendelser, må du angi skriptbiblioteket med hendelsesbehandlingen for disse hendelsene i stedet for `OnLoad`-hendelsen. På denne måten kan innlastingen av disse bibliotekene utsettes, noe som øker ytelsen når skjemaet lastes.  
  
 **Bruk skjulte faner for å utsette lasting av webressurser**  
 Når webressurser eller IFRAMES er inkludert i inndelinger i en skjult fane, lastes de ikke hvis fanen er skjult. De lastes når fanen vises. Når fanetilstanden endres, forekommer `TabStateChange`-hendelsen. Kode som er nødvendig for å støtte webressurser eller IFRAME i skjulte faner, kan bruke hendelsesbehandling for **TabStateChange**-hendelsen og redusere kode som ellers ville ha forekommet i `OnLoad`-hendelsen.  
  
 **Angi standard synlighetsalternativer**  
 Unngå bruken av skjemaskript i `OnLoad`-hendelsen som skjuler skjemaelementer. Angi i stedet standard synlighetsalternativer for skjemaelementer som kan være skjult, slik at de ikke er synlig som standard når skjemaet lastes. Deretter kan du bruke skript i `OnLoad`-hendelsen for å vise de skjemaelementene du ønsker.  
  
<a name="BKMK_CommandBar"></a>   
## <a name="command-bar-or-ribbon"></a>Kommandolinje eller båndet  
 Vær oppmerksom på disse anbefalingene når du redigerer kommandolinjen eller båndet.  
  
 **Ikke bruk for mange kontroller**  
 Evaluer hvilke kontroller som er nødvendig og skjul de du ikke trenger, på kommandolinjen eller båndet for skjemaet. Hver kontroll som vises øker ressursene som må lastes ned til nettleseren.  
  
## <a name="next-steps"></a>Neste trinn  
 [Opprette og utforme skjemaer](create-design-forms.md)    
    
 
