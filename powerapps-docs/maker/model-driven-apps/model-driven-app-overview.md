---
title: Oversikt over hvordan du bygger en modelldrevet app med PowerApps | Microsoft Docs
description: Trinnvise instruksjoner for oppretting og konfigurering av en enhet som brukes med en PowerApps-app.
documentationcenter: na
author: Mattp123
manager: kvivek
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: conceptual
ms.component: model
ms.date: 08/09/2018
ms.author: matp
ms.openlocfilehash: f6434e6a9248586c05fa0b56b8934d910af3087a
ms.sourcegitcommit: 2a61989be5880fede31510c5dab1593a6f42a741
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/09/2018
ms.locfileid: "39723850"
---
# <a name="what-are-model-driven-apps-in-powerapps"></a>Hva er modelldrevne apper i PowerApps?

Utforming av modelldrevne apper er en komponentfokusert tilnærming til apputvikling. Utforming av modelldrevne apper krever ikke kode, og du kan lage både enkle eller svært komplekse apper.  I motsetning til ved utforming av lerretsapper, der utformeren har fullstendig kontroll over appens layout, er mye av layouten fastsatt når du utformer modelldrevne apper, og den bestemmes i stor grad av komponentene du legger til i appen. 

![Eksempel på en modelldrevet app](media/model-driven-app-overview/model-app-sample.png)

Utforming av modelldrevne apper har følgende fordeler:
- utformingsmiljøer med fokus på stort utvalg av komponenter og ingen kode 
- du kan lage komplekse, responsive apper med liknende brukergrensesnitt på tvers av mange enheter, fra stasjonær PC til mobile enheter
- du kan utforme egenskaper som er lignende de som er tilgjengelige i Dynamics 365-plattformen for kundeengasjement 
- appen kan distribueres som en løsning
 
## <a name="the-approach-to-model-driven-app-making"></a>Tilnærming for laging av modelldrevne apper
Ved laging av modelldrevne apper finnes det i hovedsak tre viktige fokusområder.

- Modellering av forretningsdata 
- Definering av forretningsprosesser 
- Komponering av appen

### <a name="modeling-business-data"></a>Modellering av forretningsdata
Modellering av forretningsdata innebærer å bestemme hva slags data appen trenger og hvordan disse dataene knyttes til andre data. Modelldrevet utforming bruker en metadatadrevet arkitektur, slik at designeren kan tilpasse applikasjonen uten å skrive kode. Metadata betyr «data om data» og definerer strukturen på dataene som er lagret i systemet. [Opplæring: Opprette en egendefinert enhet som har PowerApps-komponenter](../common-data-service/create-custom-entity.md)

### <a name="defining-business-processes"></a>Definering av forretningsprosesser
Definering og gjennomføring av konsekvente forretningsprosesser er en viktig del av utforming av modelldrevne apper. Konsekvente prosesser bidrar til å sikre at brukerne av appen kan fokusere på arbeidet sitt og ikke på å utføre en rekke manuelle trinn. Prosesser kan være enkle eller komplekse, og de endres ofte over tid. Hvis du vil opprette en prosess fra området Modelldrevne apper på PowerApps.com, velger du ![Innstillinger](media/powerapps-gear.png) > **Avanserte tilpassinger** > **Åpne løsningsutforsker**. Velg **Prosesser** i venstre navigasjonsrute i Løsningsutforsker, og velg deretter **Ny**. Mer informasjon: [Oversikt over forretningsprosessflyter](/flow/business-process-flows-overview) og [Ta i bruk forretningslogikk med Common Data Service for apper](../common-data-service/cds-processes.md). 

### <a name="composing-the-model-driven-app"></a>Komponere den modelldrevne appen
Når du har modellert dataene og definert prosessene, bygger du appen ved å velge og komponere komponentene du trenger ved å bruke Apputforming.

![Apputforming](media/model-driven-app-overview/app-designer.png)

## <a name="next-steps"></a>Neste trinn

[Bygg din første modelldrevne app](build-first-model-driven-app.md)

[Modelldrevne appkomponenter](model-driven-app-components.md)

