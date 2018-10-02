---
title: Konfigurere Notatkontroll for modelldrevne apper å få tilgang til informasjon om innlegg i PowerApps | MicrosoftDocs
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
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="set-up-the-model-driven-app-notes-control-to-access-information-about-posts"></a>Konfigurere Notatkontroll for modelldrevne apper å få tilgang til informasjon om innlegg

 Når du bruker [oppdaterte skjemaer](main-form-presentations.md#updated-forms) i PowerApps-skjemaer for bestemte systemenheter, gir notatkontrollen mulighet til å få tilgang til informasjon om **innlegg**, **aktiviteter** og **notater**. Når du har aktivert notater og aktiviteter for egendefinerte enheter, vil du bare se **Notater** og **Aktiviteter**. Hvis du vil ta med **Innlegg**, må du aktivere dem for den egendefinerte enheten.  
  
## <a name="enable-posts-for-a-custom-entity"></a>Aktivere innlegg for en egendefinert enhet  
  
1.  Gå til **[Innstillinger](advanced-navigation.md#settings)** > **Konfigurasjon av aktivitetsfeeder**. 
  
2.  Åpne oppføringen for den egendefinerte enheten.  
  
3.  Kontroller at det er merket av for **Aktiver vegger for denne typen oppføringsskjema**, og lagre oppføringen.  
  
4.  Velg **Aktiver** på kommandolinjen.  
  
5.  Hvis du vil aktivere vegger, må du publisere enheten.  
  
 Som standard for systemenheter er notatkontrollen plassert i en inndeling for sosial rute midt i en kategori med tre kolonner, øverst i skjemaet. Den kan vises i et skjema bare én gang. Du kan flytte eller fjerne notatkontrollen. Hvis du vil legge den til igjen, bruker du **Notater**-knappen i **Kontroll**-gruppen i kategorien **Sett inn**.  
  
 Tabellen nedenfor beskriver egenskapene for notatkontrollen.  
  
|Kategori|Egenskap|Beskrivelse|  
|---------|--------------|-----------------|  
|**Vis**|**Etikett**|**Nødvendige**: Selv om etiketten ikke vises som standard, kreves det en etikett.|  
||**Vis etikett i skjemaet**|Du kan velge å vise etiketten.|  
||**Lås feltet i skjemaet**|Dette hindrer at notatene fjernes utilsiktet fra skjemaet.|  
||**Standardkategori**|Velg hvilken kategori som skal vises som standard. Alternativene er:<br /><br /> - **Aktiviteter**<br />- **Innlegg**<br />- **Notater**|  
|**Formatering**|**Velg antall kolonner som kontrollen bruker**|Når inndelingen som inneholder notatkontrollen inneholder flere enn én kolonne, kan du angi at feltet skal bruke opptil antallet kolonner som inndelingen har.|  
||**Antall rader**|Styr høyden på notatkontrollen ved å velge antall rader som kontrollen bruker.|  
||**Utvid automatisk for å bruke tilgjengelig plass**|I stedet for å angi høyden med antall rader, kan du tillate at høyden på notatkontrollen kan utvides til tilgjengelig plass.|  
  
## <a name="next-steps"></a>Neste trinn
[Åpne skjemaredigeringsprogrammet](open-form-editor.md)
