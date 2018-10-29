---
title: Konfigurer notatkontroll for modelldrevet app for å få tilgang til informasjon om innlegg i PowerApps | MicrosoftDocs
ms.custom: ''
ms.date: 05/06/2018
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
ms.assetid: f10cdf1c-3540-439c-a171-27a10e72da45
caps.latest.revision: 63
ms.author: matp
manager: kvivek
ms.openlocfilehash: 014f0c2516813b7cbcaa8e44a188455b07056c71
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/08/2018
ms.locfileid: "39697281"
---
# <a name="set-up-the-model-driven-app-notes-control-to-access-information-about-posts"></a>Konfigurer notatkontroll for modelldrevet app for å få tilgang til informasjon om innlegg

 I PowerApps-skjemaer for enkelte systemenheter som bruker [Oppdaterte skjemaer](main-form-presentations.md#updated-forms), kan du bruke notatkontrollen til å få tilgang til informasjon om **Innlegg**, **Aktiviteter** og **Notater**. For egendefinerte skjemaer der notater og aktiviteter er aktivert, ser du bare **Notater** og **Aktiviteter**. Hvis du vil inkludere **Innlegg**, må du aktivere dette for den egendefinerte enheten.  
  
## <a name="enable-posts-for-a-custom-entity"></a>Angi innlegg for en egendefinert enhet  
  
1.  Gå til **[Innstillinger](advanced-navigation.md#settings)** > **Konfigurasjon av aktivitetsfeeder**. 
  
2.  Åpne posten for den egendefinerte enheten.  
  
3.  Sørg for at **Aktiver vegger for denne typen postskjema** er valgt, og lagre posten.  
  
4.  Velg **Aktiver** på kommandolinjen.  
  
5.  Hvis du trenger å aktivere vegger, må du publisere enheten.  
  
 For systemenheter er notatkontrollen plassert i et sosialt ruteområde i midten av en fane med tre kolonner øverst i skjemaet. Det kan vises i et skjema bare én gang. Du kan flytte eller endre navnet på notatkontrollen. Hvis du vil flytte den tilbake, bruker du **Notater**-knappen i **Kontroll**-gruppen på **Sett inn**-fanen.  
  
 Tabellen nedenfor beskriver egenskapene til notatkontrollen.  
  
|Fane|Egenskap|Beskrivelse|  
|---------|--------------|-----------------|  
|**Skjerm**|**Etikett**|**Obligatorisk**: Selv om etiketten ikke vises som standard, er en etikett obligatorisk.|  
||**Vis etikett på skjemaet**|Du kan velge å vise etiketten.|  
||**Lås feltet på skjemaet**|Dette hindrer at notatene fjernes fra skjemaet ved et uhell.|  
||**Standard-fanen**|Velg hvilken fane som skal vises som standard. Alternativene er:<br /><br /> - **Aktiviteter**<br />- **Innlegg**<br />- **Merknader**|  
|**Formatering**|**Velg antall kolonner kontrollen bruker**|Når inndelingen som inneholder notatkontrollen, har mer enn én kolonne, kan du angi at feltet skal bruke opptil det antallet kolonner inndelingen har.|  
||**Antall rader**|Kontroller høyden på notatkontrollen ved å velge hvor mange rader kontrollen skal fylle.|  
||**Utvid for å bruke tilgjengelig plass automatisk**|I stedet for å angi høyden med et antall rader, kan du la høyden på notatkontrollen utvide slik at den fyller den tilgjengelige plassen.|  
  
## <a name="next-steps"></a>Neste trinn
[Åpne redigeringsprogrammet for skjema](open-form-editor.md)
