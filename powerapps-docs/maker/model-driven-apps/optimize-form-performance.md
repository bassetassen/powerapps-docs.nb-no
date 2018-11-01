---
title: Optimalisere skjemaytelsen for modelldrevne apper i PowerApps | MicrosoftDocs
description: Finn ut hvordan du kan unngå skjemautforminger som fører til treg innlasting av skjemaer
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
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="optimize-model-driven-app-form-performance"></a>Optimalisere skjemaytelsen for modelldrevne apper

Skjemaer som lastes inn langsomt, kan redusere produktiviteten og gjøre det vanskeligere for brukere å ta i bruk systemet. Følg disse anbefalingene for å få skjemaer til å lastes inn så raskt som mulig. Mange av disse anbefalingene er om hvordan en utvikler kan implementere skjemaskript for organisasjonen. Diskuter disse anbefalingene med utviklere som lager skjemaskript for skjemaene.  
  
<a name="BKMK_FormDesign"></a>   
## <a name="form-design"></a>Skjemautforming  
 Tenk på hvordan brukeren skal bruke skjemaet, og mengden data som må vises i det.  
  
 **Bruk så få felt som mulig**  
 Jo flere felt du har i et skjema, desto mer data må overføres via Internett eller intranettet for å vise hver enkelt oppføring.  
  
<a name="BKMK_FormScripts"></a>   
## <a name="form-scripts"></a>Skjemaskript  
 Når du har tilpassinger der skjemaskript brukes, må du passe på at utvikleren forstår disse strategiene, for å forbedre ytelsen.  
  
 **Unngå å ta med unødvendige JavaScript-biblioteker**  
 Jo flere skript du legger til i skjemaet, desto lengre tid tar det å laste dem ned. Skript hurtigbufres vanligvis i nettleseren etter at de er lastet inn første gang, men ytelsen første gang et skjema vises, kan ofte gjøre et betydelig inntrykk.  
  
 **Unngå å laste alle skriptene i Onload-hendelsen**  
 Hvis du har kode som bare støtter `OnChange`-hendelser for felt eller `OnSave`-hendelsen, må du passe på at du angir skriptbiblioteket med hendelsesbehandlingen for disse hendelsene i stedet for `OnLoad`-hendelsen. Dermed kan lasting av disse bibliotekene utsettes og ytelsen under innlasting av skjemaet økes.  
  
 **Bruke skjulte kategorier til å utsette innlasting av webressurser**  
 Når webressurser eller IFRAMES er tatt med i deler i en skjult kategori, lastes de ikke inn så lenge kategorien er skjult. De lastes inn når kategorien vises. Når kategoritilstanden endres, inntreffer hendelsen `TabStateChange`. Kode som kreves for å støtte webressurser eller IFRAMEs i skjulte kategorier, kan bruke hendelsesbehandling for hendelsen **TabStateChange** og redusere mengden kode som kanskje ellers måtte brukes i `OnLoad`-hendelsen.  
  
 **Angi standardalternativer for synlighet**  
 Unngå å bruke skjemaskript i `OnLoad`-hendelsen som skjuler skjemaelementer. Angi i stedet standardalternativer for synlighet for skjemaelementer som kan være skjult, slik at de ikke vises som standard når skjemaet lastes inn. Bruk deretter skript i `OnLoad`-hendelsen til å vise skjemaelementene du vil vise.  
  
<a name="BKMK_CommandBar"></a>   
## <a name="command-bar-or-ribbon"></a>Kommandolinjen eller båndet  
 Ta hensyn til disse anbefalingene når du redigerer kommandolinjen eller båndet.  
  
 **Bruk så få kontroller som mulig**  
 Vurder hvilke kontroller du må ha på kommandolinjen eller båndet for skjemaet, og skjul de du ikke trenger. Hver kontroll som vises, øker mengden ressurser som må lastes ned til nettleseren.  
  
## <a name="next-steps"></a>Neste trinn  
 [Opprette og utforme skjemaer](create-design-forms.md)    
    
 
