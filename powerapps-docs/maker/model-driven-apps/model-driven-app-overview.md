---
title: Oversikt over bygging av en modelldrevet app med PowerApps | MicrosoftDocs
description: Trinnvise instruksjoner for å opprette og konfigurere en enhet for bruk med en PowerApps-app.
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
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="what-are-model-driven-apps-in-powerapps"></a>Hva er modelldrevne apper i PowerApps?

Modelldrevet apputforming er en komponentfokusert metode for apputvikling. Design av modelldrevne apper krever ikke kode, og appene du lager, kan være enkle eller meget komplekse.  I motsetning til apputvikling med lerret der designeren har full kontroll over appoppsettet, er mye av oppsettet allerede bestemt for deg med modelldrevne apper tilordnes stort sett av komponentene som du legger til i appen. 

![Eksempel på modelldrevet app](media/model-driven-app-overview/model-app-sample.png)

Design av modelldrevne apper gir følgende fordeler:
- Avanserte designmiljøer med fokus på komponenter uten kode 
- Opprette komplekse responsive apper med et likt brukergrensesnitt på tvers av en rekke enheter, fra skrivebord til mobil
- Utforme funksjonalitet som ligner på det som er tilgjengelig i Dynamics 365 customer engagement-plattformen 
- Appen kan distribueres som en løsning
 
## <a name="the-approach-to-model-driven-app-making"></a>Metoden for utvikling av modelldrevne apper
På et grunnleggende nivå består utvikling av modelldrevne apper av tre viktige fokusområder.

- Modellering av forretningsdata 
- Definering av forretningsprosesser 
- Konstruksjon av appen

### <a name="modeling-business-data"></a>Modellering av forretningsdata
For å modellere forretningsdata avgjør du hvilke data som appen din trenger, og hvordan disse dataene er relatert til andre data. Modelldreven utforming bruker en metadatadrevet arkitektur slik at designere kan tilpasse programmet uten å skrive kode. Metadata betyr "data om data", og den definerer strukturen på dataene som er lagret i systemet. [Opplæring: Opprette en egendefinert enhet som har komponenter i PowerApps](../common-data-service/create-custom-entity.md)

### <a name="defining-business-processes"></a>Definering av forretningsprosesser
Definere og fremtvinge konsekvente forretningsprosesser er et viktig aspekt under utvikling av modelldrevne apper. Ensartede prosesser er med på å sikre at appbrukerne kan fokusere på arbeidet sitt og slippe å huske hvordan et sett med manuelle trinn utføres. Prosesser kan være enkle eller komplekse og endres ofte over tid. Hvis du vil opprette en prosess, fra PowerApps.com modelldrevet område, velg ![Innstillinger](media/powerapps-gear.png) > **Avanserte tilpassinger** > **Åpne løsningsutforskeren**. I navigasjonsruten til venstre i løsningsutforskeren, velg **Prosesser**, og velg deretter **Ny**. Mer informasjon: [BOversikt over forretningsprosessflyter](/flow/business-process-flows-overview) og [Bruke forretningslogikk med Common Data Service for Apps](../common-data-service/cds-processes.md). 

### <a name="composing-the-model-driven-app"></a>Skrive den modelldrevne appen
Når du har modellert dataene og definert prosesser, kan du bygge appen ved å velge og konfigurere komponentene du trenger, ved hjelp av apputformingen.

![Apputforming](media/model-driven-app-overview/app-designer.png)

## <a name="next-steps"></a>Neste trinn

[Lage din første modelldrevne app](build-first-model-driven-app.md)

[Forstå modelldrevede appkomponenter](model-driven-app-components.md)

