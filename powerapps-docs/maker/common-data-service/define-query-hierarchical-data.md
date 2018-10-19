---
title: Definer og spør hierarkisk data med Common Data Service for apper | MicrosoftDocs
description: Finn ut hvordan du definerer og spør hierarkisk relaterte data
ms.custom: ''
ms.date: 06/02/2018
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
ms.assetid: 0cf62817-5ff5-40bb-ad17-e1f6b0921720
caps.latest.revision: 42
ms.author: matp
manager: kvivek
ms.openlocfilehash: 4dad7da635156350d104d68108ac4acfbb991862
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/08/2018
ms.locfileid: "39690723"
---
# <a name="define-and-query-hierarchically-related-data"></a>Definer og spør hierarkisk relaterte data

Du kan få verdifull forretningsinnsikt ved å definere og spørre hierarkisk relaterte data. De hierarkiske modellerings- og visualiseringsfunksjonene gir deg en rekke fordeler:  
  
- Vis og utforsk kompleks hierarkisk informasjon.  
- Vis sentrale ytelsesindikatorer (KPI-er) i den kontekstuelle visningen av et hierarki.  
- Visuell analyse av viktig informasjon på nettet og på nettbrett.  
  
Enkelte standardenheter har allerede definerte hierarkier. Andre enheter, blant annet egendefinerte enheter, kan være aktivert for et hierarki, og du kan opprette visualiseringer for dem. 

## <a name="define-hierarchical-data"></a>Definer hierarkiske data

Med Common Data Service for apper, støttes hierarkiske datastrukturer én-til-mange (1:N)-relasjoner med *selvreferanse* for de relaterte postene. 

> [!NOTE]
> *Selvreferanse* betyr at enheten er relatert til seg selv. Kontoenheten har for eksempel et oppslagsfelt som knytter den til en annen kontoenhetspost.

Når det eksisterer en én-til-mange (1:N)-relasjon med selvreferanse, kan det **hierarkiske** alternativet angis som **Ja** i relasjonsdefinisjonen.

![Hierarkisk innstilling i relasjonsdefinisjonen](media/self-referential-relationship-car-solution-explorer.png)

Du må angi enhetens én-til-mange (1:N)-relasjoner med selvreferanse som hierarkisk for å spørre dataene som et hierarki. Dette kan bare gjøres ved hjelp av løsningsutforskeren.

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]

Slik slår du på hierarkiet:  
  
1. Velg hvilken relasjon med selvreferanse du vil redigere mens du [viser 1:N-relasjoner](create-edit-1n-relationships-solution-explorer.md#view-entity-relationships).
2. Angi **Hierarkisk** som **Ja** i **Relasjonsdefinisjon**.  
  
> [!NOTE]
> - Enkelte av de ferdiglagede (1:N)-relasjonene kan ikke tilpasses. Dette vil hindre deg i å angi disse relasjonene som hierarkiske.  
> - Du kan angi en hierarkisk relasjon for systemrelasjoner med selvreferanse. Dette omfatter 1:N-relasjoner med selvreferanse av typen system, for eksempel "contact_master_contact"-relasjonen.  

> [!IMPORTANT]
> Du kan ha flere relasjoner med selvreferanse, men bare én relasjon per enhet kan defineres som en hierarkisk relasjon. Hvis du prøver å endre innstillingen når den er i bruk, får du en advarsel:
>
> - **Ved deaktivering:** Hvis du slår av hierarkiinnstillingen for denne relasjonen, fungerer ingen definisjoner for beregnet verdi eller prosesser og visninger som bruker dette hierarkiet. Vil du fortsette? 
> - **Ved aktivering:**  Hvis du aktiverer hierarkiinnstillingen for denne relasjonen, blir alle definisjoner for beregnet verdi som bruker det eksisterende hierarkiet, ugyldige. Vil du fortsette?
>
> Med mindre du er sikker på at det ikke finnes andre avhengigheter i det eksisterende hierarkiet, bør du se gjennom eventuell dokumentasjon om distribusjonen eller rådføre deg med andre tilpassere for å få forstå hvordan den eksisterende hierarkiske relasjonen brukes før du fortsetter.

<a name="BKMK_Querydata"></a> 
  
## <a name="query-hierarchical-data"></a>Spørring av hierarkiske data  

Hvis du ikke har et definert hierarki, må du gjentakende spørre etter relaterte poster for å hente hierarkiske data. Hvis du har et definert hierarki, kan du spørre etter de relaterte dataene som et hierarki i ett trinn. Du kan spørre etter poster ved å bruke logikken **Under** og **Ikke under**. De hierarkiske operatorene **Under** og **Ikke under** vises i det avanserte søket og redigeringsprogrammet for arbeidsflyt. Hvis du vil ha mer informasjon om hvordan du bruker disse operatorene, kan du se [Konfigurer trinn for arbeidsflyt](/flow/configure-workflow-steps#setting-conditions-for-workflow-actions). Hvis du vil ha mer informasjon om Avansert søk, kan du se [Opprett, rediger eller lagre et avansert søk](https://docs.microsoft.com/dynamics365/customer-engagement/basics/save-advanced-find-search)  

> [!NOTE]
> Utviklere har også muligheten til å bruke disse operatorene i kode. Mer informasjon [Utviklerdokumentasjon: Spørring av hierarkiske data](/dynamics365/customer-engagement/developer/org-service/query-hierarchical-data)
  
Eksemplene nedenfor viser scenarioer for spørring av hierarkier:  
  
### <a name="query-account-hierarchy"></a>Hierarki for spørringskonto  
  
![Spørringskontoer i kontohierarkiet](media/query-accounts.png)  
  
### <a name="query-account-hierarchy-including-related-activities"></a>Hierarki for spørringskonto, inkludert relaterte aktiviteter  
  
![Aktiviteter relatert til spørringskonto](media/query-account-related-activities.png)  
  
###  <a name="query-account-hierarchy-including-related-opportunities"></a>Hierarki for spørringskonto, inkludert relaterte muligheter  
  
![Muligheter relatert til spørringskonto](media/query-account-related-opportunities.png)  
  
## <a name="see-also"></a>Se også 
[Opprett og rediger 1:N (én-til-mange) eller N:1 (mange-til-én)-enhetsrelasjoner](create-edit-1n-relationships.md)<br />
[Opprett og rediger 1:N (én-til-mange) eller N:1 (mange-til-én)-enhetsrelasjoner ved hjelp av løsningsutforsker](create-edit-1n-relationships-solution-explorer.md)<br />
[Visualiser hierarkiske data med modelldrevne apper](visualize-hierarchical-data.md)<br />
[Video: Hierarkisk sikkerhetsmodellering](http://www.youtube.com/watch?v=kx5So32DrCo&index=10&list=PLC3591A8FE4ADBE07)<br />
[Video: Hierarkivisualisering](http://www.youtube.com/watch?v=_dGBE6icLNw&index=9&list=PLC3591A8FE4ADBE07)
