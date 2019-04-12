---
title: Konfigurere en enhet for tilbakemelding med PowerApps | MicrosoftDocs
description: Finn ut hvordan du aktiverer tilbakemelding for en enhet
ms.custom: ''
ms.date: 05/18/2018
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
ms.assetid: 5b25cf09-d43b-4165-9eaa-7549f4855e7c
caps.latest.revision: 13
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="configure-an-entity-for-feedbackratings"></a>Konfigurere en enhet for tilbakemelding/vurderinger

La kunder eller ansatte skrive tilbakemelding for alle enhetsoppføringer eller vurdere enhetsoppføringene innenfor et definert rangeringsområde ved å aktivere enheter for tilbakemelding.  

Denne funksjonen brukes vanligvis med et system som henter data fra kunder via en portal eller undersøkelse. Data om tjeneste- eller produkttilfredshet kan brukes med enheter som representerer denne typen data.

Tilbakemelding kan også brukes av ansatte for å gi tilbakemelding på samarbeid.

> [!NOTE]
> Du må ha sikkerhetsrollen som systemansvarlig eller systemtilpasser eller tilsvarende tillatelser for å utføre disse trinnene.
  
## <a name="enable-feedback"></a>Aktivere tilbakemelding  
  
Rediger enheten for å aktivere **Tilbakemelding**. Mer informasjon: [Redigere en enhet](edit-entities.md)
  
## <a name="add-a-subgrid-for-feedback-on-the-entity-form"></a>Legge til delrutenett for tilbakemelding på enhetsskjemaet  

Som standard må brukere gå til listen over tilknyttede oppføringer for oppføringen du vil legge til tilbakemelding for. Hvis du vil gjøre det enklere for brukerne å legge til tilbakemelding, kan du legge til et tilbakemeldingsdelrutenett i skjemaet for enheten du aktiverer tilbakemelding for.  

<!-- This is the closest I could find to a topic about adding an subgrid to a form. -->
Mer informasjon:  [Oversikt over egenskaper for delrutenett](../model-driven-apps/sub-grid-properties-legacy.md)

## <a name="add-a-rollup-field--to-the-entity-form-to-show-the-ratings"></a>Legge til et felt for beregnet verdi i enhetsskjemaet for å vise vurderingene  

Avhengig av hvordan du vil beregne vurderingen for enheten, kan du lage et felt for beregnet verdi som beregner vurderingen, og deretter legge det til i skjemaet for enheten som aktiveres for tilbakemelding. Mer informasjon: [Definere felt for beregnet verdi som samler verdier](define-rollup-fields.md)
  
### <a name="see-also"></a>Se også  
 [Sende tilbakemelding eller vurderinger for Dynamics 365-oppføringer](/dynamics365/customer-engagement/basics/submit-feedback-ratings)
