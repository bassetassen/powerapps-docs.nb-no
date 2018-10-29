---
title: Konfigurer en enhet for tilbakemelding med PowerApps | MicrosoftDocs
description: Lær hvordan du aktiverer tilbakemelding for en enhet
ms.custom: ''
ms.date: 05/18/2018
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
ms.assetid: 5b25cf09-d43b-4165-9eaa-7549f4855e7c
caps.latest.revision: 13
ms.author: matp
manager: kvivek
ms.openlocfilehash: efb1cf167353d5928564b42aeb7a49f43cf272d6
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/08/2018
ms.locfileid: "39692883"
---
# <a name="configure-an-entity-for-feedbackratings"></a>Konfigurer en enhet for tilbakemelding/vurderinger

La kunder skrive tilbakemeldinger for alle enhetsposter, eller vurdere enhetsposter innenfor et definert vurderingsområde, ved å aktivere enheter for tilbakemelding.  

Denne funksjonen brukes vanligvis med et system som henter data fra kunder via en portal eller en undersøkelse. Data om tjenesten eller kundetilfredshet med produktet, kan brukes med enheter som representerer den typen data.

Tilbakemelding kan også brukes av ansatte til å gi tilbakemelding om et samarbeid.

> [!NOTE]
> Du nå ha en sikkerhetsrolle som systemansvarlig eller systemtilpasser, eller tilsvarende tillatelser, for å utføre disse trinnene.
  
## <a name="enable-feedback"></a>Aktiver tilbakemelding  
  
Rediger enheten for å aktivere **Tilbakemelding**. Mer informasjon: [Rediger en enhet](edit-entities.md)
  
## <a name="add-a-subgrid-for-feedback-on-the-entity-form"></a>Legg til et delrutenett for tilbakemelding på enhetsskjemaet  

Brukere må, som standard, gå til listen over tilknyttede oppføringer i posten du vil legge til tilbakemelding for. Hvis du vil gjøre det enklere for brukerne å legge til tilbakemelding, kan du legge til et delrutenett for tilbakemelding i enhetsskjemaet for enheten du aktiverer tilbakemelding for.  

<!-- This is the closest I could find to a topic about adding an subgrid to a form. --> Mer informasjon:  [Oversikt over egenskaper for delrutenett](../model-driven-apps/sub-grid-properties-legacy.md)

## <a name="add-a-rollup-field--to-the-entity-form-to-show-the-ratings"></a>Legg til et felt for beregnet verdi i enhetsskjemaet for å vise vurderingene  

Avhengig av hvordan du vil beregne vurderingene for enheten, kan du opprette et felt for beregnet verdi som beregner vurderingen, og deretter legge den til enhetsskjemaet du aktiverer for tilbakemelding. Mer informasjon: [Definer felt for beregnet verdi som samler verdier](define-rollup-fields.md)
  
### <a name="see-also"></a>Se også  
 [Send inn tilbakemelding eller vurderinger for Dynamics 365-poster](/dynamics365/customer-engagement/basics/submit-feedback-ratings)
