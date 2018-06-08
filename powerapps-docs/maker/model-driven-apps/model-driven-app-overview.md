---
title: Oversikt over hvordan du bygger en modelldrevet app med PowerApps | Microsoft Docs
description: Trinnvise instruksjoner for oppretting og konfigurering av en enhet som brukes med en PowerApps-app.
documentationcenter: na
author: Mattp123
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: conceptual
ms.component: model
ms.date: 03/21/2018
ms.author: matp
ms.openlocfilehash: 76571a53c95661d853b7fb326e3c1087a6f432c4
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/04/2018
ms.locfileid: "32330932"
---
# <a name="overview-of-building-a-model-driven-app"></a>Oversikt over hvordan du bygger en modelldrevet app

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
Definering og gjennomføring av konsekvente forretningsprosesser er en viktig del av utforming av modelldrevne apper. Konsekvente prosesser bidrar til å sikre at brukerne av appen kan fokusere på arbeidet sitt og ikke på å utføre en rekke manuelle trinn. Prosesser kan være enkle eller komplekse, og de endres ofte over tid. Når du vil opprette en prosess, velger du **Avansert** for å åpne [Løsningsutforsker](#advanced-model-driven-app-making). Velg **Prosesser** i venstre navigasjonsrute i Løsningsutforsker, og velg deretter **Ny**. Mer informasjon: [Arbeide med forretningslogikk](#working-with-business-logic)  

### <a name="composing-the-model-driven-app"></a>Komponere den modelldrevne appen
Når du har modellert dataene og definert prosessene, bygger du appen ved å velge og komponere komponentene du trenger ved å bruke Apputforming.

![Apputforming](media/model-driven-app-overview/app-designer.png)

## <a name="model-driven-app-components-and-designers"></a>Komponenter i modelldrevne apper samt utformere
En godt utformet modelldrevet app består av flere komponenter som utformeren velger for å sette sammen den ferdige appens utseende og funksjonalitet. Komponentene og komponentegenskapene som designerne bruker til å lage en app, utgjør metadataene. For hjelpe deg å forstå hvordan hver av disse komponentene er knyttet til apputformingen har vi her delt dem inn i kategoriene *data*, *brukergrensesnitt*, *logikk* og *visualisering*. 

### <a name="data"></a>Data
Disse komponentene bestemmer hvilke data appen baseres på.


|Komponent  |Beskrivelse  |Utforming  |
|---------|---------|---------|
|Enhet     |Et element med egenskaper som spores, som en kontakt eller en konto. Mange standardenheter er tilgjengelige. Du kan egendefinere en enhet som ikke er systemstandard (produksjonsenhet) eller opprette en egendefinert enhet fra grunnen av.     | [!INCLUDE [powerapps](../../includes/powerapps.md)] enhetsutformer        |
|Felt     | En egenskap som er tilknyttet en enhet. Et felt defineres av en datatype, som bestemmer hvilken type data som kan legges inn eller velges. Eksempler omfatter tekst, tall, dato og klokkeslett, valuta eller oppslag (oppretter en relasjon med en annen enhet). Felter brukes med skjemaer, visninger og søk.        | [!INCLUDE [powerapps](../../includes/powerapps.md)] enhetsutformer   |
|Relasjon     | Enhetsrelasjoner definerer hvordan enheter kan knyttes til hverandre. Det finnes relasjoner av typene 1:N (én til mange), N:1 (mange til én) og N:N (mange til mange). For eksempel: Hvis du legger til et oppslagsfelt til en enhet, opprettes en ny 1:N-relasjon mellom de to enhetene og du kan legge dette oppslagsfeltet i et skjema.   | [!INCLUDE [powerapps](../../includes/powerapps.md)] enhetsutformer        |
|Alternativsettfelt     | Dette er et spesialtypefelt, som gir brukeren et sett med forhåndsdefinerte alternativer. Hvert alternativ har en nummerverdi og en etikett. Når dette feltet legges til på et skjema, viser det en kontroll som brukeren bruker til å velge et alternativ med.  Det finnes to typer alternativsett: alternativsett, der brukeren kan velge ett alternativ, og alternativsett for flervalg, som tillater valg av mer enn ett alternativ.  | [!INCLUDE [powerapps](../../includes/powerapps.md)] alternativsettutformer     |

### <a name="ui"></a>Brukergrensesnitt
Disse komponentene bestemmer hvordan brukere samhandler med appen. 

|Komponent  |Beskrivelse  |Utforming  |
|---------|---------|---------|
|App     | Bestemmer de grunnleggende elementene i appen, som komponenter, egenskaper, klienttype og appens URL-adresse.      | Apputforming   |
|Kart over webområde     | Angi navigasjonen for appen.        | Utformer for kart over webområde        |
|Skjema     | Et sett med felter for innlegging av data for en gitt enhet, som samsvarer med elementene som organisasjonen sporer for enheten. For eksempel, et sett med felter for innlegging av data, der brukeren legger inn relevant informasjon for å spore en kundes tidligere bestillinger, sammen med bestemte forespurte datoer for nye bestillinger.        | Skjemautforming        |
|Vis     | Vis definerer hvordan en liste med oppføringer for en bestemt enhet vises i applikasjonen. En visning definerer kolonnene som skal vises, bredden på hver kolonne, sorteringsegenskaper og standardfiltre.   |  Visningsutforming       |

![Apputforming og skjemautforming](media/model-driven-app-overview/app-and-form-designers.png)

### <a name="logic"></a>Logikk
Bestemmer hvilke forretningsprosesser, regler og automatisering appen skal ha. [!INCLUDE [powerapps](../../includes/powerapps.md)]-skapere bruker en utformer som er spesifikk for den type prosess eller regel. 


|Logikktype  |Beskrivelse  |Utforming  |
|---------|---------|---------|
|Forretningsprosessflyt     | En online prosess som veileder brukeren gjennom en standard forretningsprosess. Du kan for eksempel bruke en forretningsprosess hvis du vil at alle skal håndtere kundeserviceforespørsler på samme måte, eller til å kreve at personalet må innhente godkjenning for en faktura før en bestilling legges inn.        | Utformer for forretningsprosessflyt        |
|Arbeidsflyt     |  Arbeidsflyter automatiserer forretningsprosesser uten et brukergrensesnitt. Utformere bruker arbeidsflyter til å starte automatisering som ikke krever handling fra brukeren.       | Arbeidsflytutforming        |
|Handlinger    |  Handlinger er en type prosess som kan brukes til manuell aktivering av handlinger, inkludert tilpassede handlinger, direkte fra en arbeidsflyt.       |  Prosessutforming       |
|Forretningsregel     | Brukes til å ta i bruk regler eller anbefalt logikk på et skjema, som f.eks. å angi krav til felter, skjule felter eller validere data. Apputforming bruker et enkelt brukergrensesnitt til å implementere og opprettholde regler som endres raskt og brukes ofte.         |  Utforming av forretningsregel       |
|Flyt     | Flyt er en skybasert tjeneste som kan brukes til å opprette automatiserte arbeidsflyter mellom apper og tjenester for å få varslinger, synkronisere filer, samle inn data og mer.        | Microsoft Flow        |

![Utforming av arbeidsflyt, handling og forretningsprosessflyt](media/model-driven-app-overview/designer-mash.png)

### <a name="visualizations"></a>Visualiseringer
Bestemmer hvilke typer datavisualiseringer og rapporteringer appen skal ha tilgjengelig.


|Komponent  |Beskrivelse  |Utforming  |
|---------|---------|---------|
|Diagram     | En enkel grafikkvisualisering som kan vises i en visning, på et skjema eller legges til på et instrumentbord.        | Diagramutforming        |
|Instrumentbord     | Fungerer som en palett for én eller flere grafikkvisualiseringer som gir en oversikt over forretningsdata handlinger kan utføres på.        | Utforming av instrumentbord        |
|Innebygd Power BI     | Legg innebygde Power BI-fliser og -instrumentbord til i appen. Power BI er en skybasert tjeneste som gir innsikt i forretningsanalyser.        |  Kombinasjon av diagramutforming, utforming av instrumentbord og Power BI       |

![Eksempel på instrumentbord](media/model-driven-app-overview/dashboard-designer.png)

### <a name="advanced-model-driven-app-making"></a>Lage avanserte, modelldrevne apper
Løsningsutforsker er et omfattende verktøy til bruk i bygging av avanserte, modelldrevne apper. I Løsningsutforsker kan du navigere gjennom et hierarki som inneholder alle appkomponentene ved å bruke navigasjonsruten på venstre side av verktøyet.

![Løsningsutforsker](media/model-driven-app-overview/solutionexplorer-entitiescollapsed.png)

Åpne Løsningsutforsker ved å velge **Modelldrevet** i den venstre ruten i [!INCLUDE [powerapps](../../includes/powerapps.md)].

  ![Velg Modelldrevet](media/model-driven-app-overview/app-type-picker-mod.png)

Velg deretter fanen **Avansert**. 

## <a name="model-driven-app-development-resources"></a>Utviklingsressurser for modelldrevne apper
Du finner mer informasjon om utvikling av modelldrevne apper under disse emnene.
### <a name="modeling-your-data"></a>Modellere dataene
- [Utforme egendefinerte forretningsapper ved bruk av Apputforming](https://docs.microsoft.com/dynamics365/customer-engagement/customize/design-custom-business-apps-using-app-designer)
- [Opprette og utforme skjemaer](https://docs.microsoft.com/dynamics365/customer-engagement/customize/create-design-forms)
- [Opprette eller redigere visninger](https://docs.microsoft.com/dynamics365/customer-engagement/customize/create-edit-views)  

### <a name="modeling-and-composing-your-app"></a>Modellere og komponere appen
- [Opprette eller redigere enheter](https://docs.microsoft.com/dynamics365/customer-engagement/customize/create-edit-entities)
- [Opprette og redigere relasjoner](https://docs.microsoft.com/dynamics365/customer-engagement/customize/create-edit-entity-relationships) 
- [Opprette og redigere felter](https://docs.microsoft.com/dynamics365/customer-engagement/customize/create-edit-fields)
- [Opprette og redigere globale alternativsett](https://docs.microsoft.com/dynamics365/customer-engagement/customize/create-edit-global-option-sets)

### <a name="working-with-business-logic"></a>Arbeide med forretningslogikk
- [Oversikt over forretningsprosessflyter](https://docs.microsoft.com/dynamics365/customer-engagement/customize/business-process-flows-overview)
- [Bruke arbeidsflytprosesser til å automatisere prosesser](https://docs.microsoft.com/dynamics365/customer-engagement/customize/workflow-processes)
- [Oversikt over handlinger](https://docs.microsoft.com/dynamics365/customer-engagement/customize/actions)
- [Opprette forretningsregler og -anbefalinger for å ta i bruk logikk](https://docs.microsoft.com/dynamics365/customer-engagement/customize/create-business-rules-recommendations-apply-logic-form)

### <a name="using-visualizations-in-your-app"></a>Bruke visualiseringer i appen
- [Opprette eller redigere et systemdiagram](https://docs.microsoft.com/dynamics365/customer-engagement/customize/create-edit-system-chart)
- [Opprette eller redigere instrumentbord](https://docs.microsoft.com/dynamics365/customer-engagement/customize/create-edit-dashboards)


### <a name="distributing-your-app"></a>Distribuere appen
[Opprette en løsning](https://docs.microsoft.com/dynamics365/customer-engagement/customize/create-solution)

## <a name="next-steps"></a>Neste trinn
[Hurtigstart: Opprette en egendefinert enhet](../common-data-service/data-platform-create-entity.md)

[Opplæring: Opprette en egendefinert enhet som har PowerApps-komponenter](../common-data-service/create-custom-entity.md)

