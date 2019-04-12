---
title: Definere og spørre etter hierarkiske data med Common Data Service | MicrosoftDocs
description: Finn ut hvordan du definerer og spør etter hierarkisk relaterte data
ms.custom: ''
ms.date: 06/02/2018
ms.reviewer: ''
ms.service: powerapps
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
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="define-and-query-hierarchically-related-data"></a>Definere og spørre etter hierarkisk relaterte data

Du kan få verdifull innsikt i bedriftsdata ved å definere og spørre etter hierarkisk relaterte data. Den hierarkiske modelleringen og visualiseringsfunksjonene gir deg mange fordeler:  
  
- Vise og utforske kompleks hierarkisk informasjon.  
- Vise KPI-er (Key Performance Indicators) i den kontekstavhengige visningen av et hierarki.  
- Visuelt analysere viktig informasjon på Internett og nettbrett.  
  
Enkelte standardenheter har allerede hierarkier definert. Andre enheter, inkludert egendefinerte enheter, kan aktiveres for et hierarki, og du kan lage visualiseringer for dem. 

## <a name="define-hierarchical-data"></a>Definere hierarkiske data

I Common Data Service støttes hierarkiske datastrukturer av *selvrefererende relasjoner* av typen én-til-mange (1:N) for de relaterte oppføringene. 

> [!NOTE]
> *Selvrefererende* betyr at enheten er relatert til seg selv. Forretningsforbindelsesenheten har for eksempel et oppslagsfelt for å knytte det til en annen oppføring for forretningsforbindelseenheten.

Når en selvrefererende én-til-mange-relasjon (1:N) finnes, kan alternativet **Hierarkisk** i relasjonsdefinisjonen settes til **Ja**.

![Hierarkisk-innstillingen i relasjonsdefinisjonen](media/self-referential-relationship-car-solution-explorer.png)

Hvis du vil spørre dataene som et hierarki, må du sette én av enhetens selvrefererende relasjoner av typen én-til-mange (1:N) til hierarkisk. Dette kan bare gjøres i løsningsutforskeren.

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]

Slik slår du på hierarkiet:  
  
1. Når du [viser 1:N-relasjoner](create-edit-1n-relationships-solution-explorer.md#view-entity-relationships), velger du den selvrefererende relasjonen du vil redigere.
2. I **Relasjonsdefinisjon** setter du **Hierarkisk** til **Ja**.  
  
> [!NOTE]
> - Noen av de medfølgende (1:N)-relasjonene kan ikke tilpasses. Dette vil hindre deg i å angi disse relasjonene som hierarkiske.  
> - Du kan angi en hierarkisk relasjon for de selvreferensielle relasjonene for systemet. Dette inkluderer de selvrefererende relasjonene (1:N) av systemtype, for eksempel "contact_master_contact"-forholdet.  

> [!IMPORTANT]
> Du kan ha flere selvrefererende relasjoner, men bare én relasjon per enhet kan defineres som den hierarkiske relasjonen. Hvis du prøver å endre innstillingen etter at den er definert, får du en advarsel:
>
> - **Når du deaktiverer:** Hvis du deaktiverer hierarkiinnstillingen for denne relasjonen, ugyldiggjøres alle definisjoner av beregnet verdi, prosesser og visninger som bruker dette hierarkiet. Vil du fortsette? 
> - **Når du aktiverer:** Hvis du aktiverer hierarkiinnstillingen for denne relasjonen, ugyldiggjøres alle definisjoner av beregnet verdi som bruker det eksisterende hierarkiet. Vil du fortsette?
>
> Hvis du er sikker på at det finnes ingen andre avhengigheter på eksisterende hierarki, bør du se gjennom all dokumentasjon om distribusjonen eller kontakte andre tilpassere for å forstå hvordan den eksisterende hierarkiske relasjonen brukes, før du fortsetter.

<a name="BKMK_Querydata"></a> 
  
## <a name="query-hierarchical-data"></a>Spørre hierarkiske data  

Uten et definert hierarki, for å hente hierarkiske data må det spørres etter de relaterte oppføringene. Med et definert hierarki kan du spørre etter de relaterte dataene som et hierarki, i ett trinn. Du kan spørre etter enhetsoppføringene ved hjelp av logikken **Under** og **Ikke under**. De hierarkiske operatorene **Under** og **Ikke under** vises i Avansert søk og redigeringsprogrammet for arbeidsflyt. Hvis du vil ha mer informasjon om hvordan du bruker disse operatorene, kan du se [Konfigurere arbeidsflyttrinn](/flow/configure-workflow-steps#setting-conditions-for-workflow-actions). Hvis du vil ha mer informasjon om avansert søk, kan du se [Opprette, redigere eller lagre et søk i Avansert søk](https://docs.microsoft.com/dynamics365/customer-engagement/basics/save-advanced-find-search).  

> [!NOTE]
> Utviklere kan også bruke disse operatorene i kode. Mer informasjon: [Dokumentasjon for utviklere: Spørre etter hierarkiske data](/dynamics365/customer-engagement/developer/org-service/query-hierarchical-data)
  
Eksemplene nedenfor viser scenarier for hierarkispørring:  
  
### <a name="query-account-hierarchy"></a>Spørre forretningsforbindelseshierarki  
  
![Spørring om forretningsforbindelser i forretningsforbindelseshierarkiet](media/query-accounts.png)  
  
### <a name="query-account-hierarchy-including-related-activities"></a>Spørre forretningsforbindelseshierarki, inkludert relaterte aktiviteter  
  
![Spørre forretningsforbindelsens tilknyttede aktiviteter](media/query-account-related-activities.png)  
  
###  <a name="query-account-hierarchy-including-related-opportunities"></a>Spørre forretningsforbindelseshierarki, inkludert relaterte salgsmuligheter  
  
![Spørre kontoens tilknyttede salgsmuligheter](media/query-account-related-opportunities.png)  
  
## <a name="see-also"></a>Se også 
[Opprette og redigere 1:N-enhetsrelasjoner (én-til-mange) eller N:1-enhetsrelasjoner (mange-til-én)](create-edit-1n-relationships.md)<br />
[Opprette og redigere 1:N- (én-til-mange) eller N:1-enhetsrelasjoner (mange-til-én) med løsningsutforskeren](create-edit-1n-relationships-solution-explorer.md)<br />
[Visualisere hierarkiske data med modelldrevne apper](visualize-hierarchical-data.md)<br />
[Video: Hierarkisk sikkerhetsmodellering](http://www.youtube.com/watch?v=kx5So32DrCo&index=10&list=PLC3591A8FE4ADBE07)<br />
[Video: Hierarkivisualisering](http://www.youtube.com/watch?v=_dGBE6icLNw&index=9&list=PLC3591A8FE4ADBE07)
