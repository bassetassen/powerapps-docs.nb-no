---
title: Forstå modelldrevne app-komponenter i PowerApps | MicrosoftDocs
description: Forstå de forskjellige komponentene i en modelldrevet app, som data, UI, logikk og visualisering.
Keywords: fields, attributes, model-driven app
author: Mattp123
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
ms.author: matp
manager: kvivek
ms.date: 06/27/2018
ms.service: crm-online
ms.topic: article
ms.openlocfilehash: 249f0d35ce9eb466303ef16658aa01198632875e
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/08/2018
ms.locfileid: "39690928"
---
# <a name="understand-model-driven-app-components"></a>Forstå modelldrevne app-komponenter
En godt utformet modelldrevet app består av flere komponenter som du velger ved bruk av utformeren for å bygge utseende og funksjonalitet for den ferdige appen. Komponentene og komponentegenskapene som designerne bruker til å lage en app, utgjør metadataene. 

For hjelpe deg å forstå hvordan hver av disse komponentene er knyttet til apputformingen har vi her delt dem inn i kategoriene *data*, *brukergrensesnitt*, *logikk* og *visualisering*. 

## <a name="data"></a>Data
Disse komponentene bestemmer hvilke data appen baseres på.


|Komponent  |Beskrivelse  |Utforming  |
|---------|---------|---------|
|Enhet     |Et element med egenskaper som spores, som en kontakt eller en konto. Mange standardenheter er tilgjengelige. Du kan egendefinere en enhet som ikke er systemstandard (produksjonsenhet) eller opprette en egendefinert enhet fra grunnen av.     | [!INCLUDE [powerapps](../../includes/powerapps.md)] enhetsutformer        |
|Felt     | En egenskap som er tilknyttet en enhet. Et felt defineres av en datatype, som bestemmer hvilken type data som kan legges inn eller velges. Eksempler omfatter tekst, tall, dato og klokkeslett, valuta eller oppslag (oppretter en relasjon med en annen enhet). Felter brukes med skjemaer, visninger og søk.        | [!INCLUDE [powerapps](../../includes/powerapps.md)] enhetsutformer   |
|Relasjon     | Enhetsrelasjoner definerer hvordan enheter kan knyttes til hverandre. Det finnes relasjoner av typene 1:N (én til mange), N:1 (mange til én) og N:N (mange til mange). For eksempel: Hvis du legger til et oppslagsfelt til en enhet, opprettes en ny 1:N-relasjon mellom de to enhetene og du kan legge dette oppslagsfeltet i et skjema.   | [!INCLUDE [powerapps](../../includes/powerapps.md)] enhetsutformer        |
|Alternativsettfelt     | Dette er et spesialtypefelt, som gir brukeren et sett med forhåndsdefinerte alternativer. Hvert alternativ har en nummerverdi og en etikett. Når dette feltet legges til på et skjema, viser det en kontroll som brukeren bruker til å velge et alternativ med.  Det finnes to typer alternativsett: alternativsett, der brukeren kan velge ett alternativ, og alternativsett for flervalg, som tillater valg av mer enn ett alternativ.  | [!INCLUDE [powerapps](../../includes/powerapps.md)] alternativsettutformer     |

Mer informasjon: [Definer data for en modelldrevet app](define-data-model-driven-app.md) 

## <a name="ui"></a>Brukergrensesnitt
Disse komponentene bestemmer hvordan brukere samhandler med appen. 

|Komponent  |Beskrivelse  |Utforming  |
|---------|---------|---------|
|App     | Bestemmer de grunnleggende elementene i appen, som komponenter, egenskaper, klienttype og appens URL-adresse.      | Apputforming   |
|Kart over webområde     | Angi navigasjonen for appen.        | Utformer for kart over webområde        |
|Skjema     | Et sett med felter for innlegging av data for en gitt enhet, som samsvarer med elementene som organisasjonen sporer for enheten. For eksempel, et sett med felter for innlegging av data, der brukeren legger inn relevant informasjon for å spore en kundes tidligere bestillinger, sammen med bestemte forespurte datoer for nye bestillinger.        | Skjemautforming        |
|Vis     | Vis definerer hvordan en liste med oppføringer for en bestemt enhet vises i applikasjonen. En visning definerer kolonnene som skal vises, bredden på hver kolonne, sorteringsegenskaper og standardfiltre.   |  Visningsutforming       |

![Apputforming og skjemautforming](media/model-driven-app-overview/app-and-form-designers.png)

## <a name="logic"></a>Logikk
Bestemmer hvilke forretningsprosesser, regler og automatisering appen skal ha. [!INCLUDE [powerapps](../../includes/powerapps.md)]-skapere bruker en utformer som er spesifikk for den type prosess eller regel. 


|Logikktype  |Beskrivelse  |Utforming  |
|---------|---------|---------|
|Forretningsprosessflyt     | En online prosess som veileder brukeren gjennom en standard forretningsprosess. Du kan for eksempel bruke en forretningsprosess hvis du vil at alle skal håndtere kundeserviceforespørsler på samme måte, eller til å kreve at personalet må innhente godkjenning for en faktura før en bestilling legges inn.        | Utformer for forretningsprosessflyt        |
|Arbeidsflyt     |  Arbeidsflyter automatiserer forretningsprosesser uten et brukergrensesnitt. Utformere bruker arbeidsflyter til å starte automatisering som ikke krever handling fra brukeren.       | Arbeidsflytutforming        |
|Handlinger    |  Handlinger er en type prosess som kan brukes til manuell aktivering av handlinger, inkludert tilpassede handlinger, direkte fra en arbeidsflyt.       |  Prosessutforming       |
|Forretningsregel     | Brukes til å ta i bruk regler eller anbefalt logikk på et skjema, som f.eks. å angi krav til felter, skjule felter eller validere data. Apputforming bruker et enkelt brukergrensesnitt til å implementere og opprettholde regler som endres raskt og brukes ofte.         |  Utforming av forretningsregel       |
|Flyt     | Flyt er en skybasert tjeneste som kan brukes til å opprette automatiserte arbeidsflyter mellom apper og tjenester for å få varslinger, synkronisere filer, samle inn data og mer.        | Microsoft Flow        |

![Utforming av arbeidsflyt, handling og forretningsprosessflyt](media/model-driven-app-overview/designer-mash.png)

Mer informasjon: [Bruk forretningslogikk i den modelldrevne appen](guide-staff-through-common-tasks-processes.md)

## <a name="visualizations"></a>Visualiseringer
Bestemmer hvilke typer datavisualiseringer og rapporteringer appen skal ha tilgjengelig.


|Komponent  |Beskrivelse  |Utforming  |
|---------|---------|---------|
|Diagram     | En enkel grafikkvisualisering som kan vises i en visning, på et skjema eller legges til på et instrumentbord.        | Diagramutforming        |
|Instrumentbord     | Fungerer som en palett for én eller flere grafikkvisualiseringer som gir en oversikt over forretningsdata handlinger kan utføres på.        | Utforming av instrumentbord        |
|Innebygd Power BI     | Legg innebygde Power BI-fliser og -instrumentbord til i appen. Power BI er en skybasert tjeneste som gir innsikt i forretningsanalyser.        |  Kombinasjon av diagramutforming, utforming av instrumentbord og Power BI       |

![Eksempel på instrumentbord](media/model-driven-app-overview/dashboard-designer.png)

## <a name="advanced-model-driven-app-making"></a>Lage avanserte, modelldrevne apper
Løsningsutforsker er et omfattende verktøy til bruk i bygging av avanserte, modelldrevne apper. I Løsningsutforsker kan du navigere gjennom et hierarki som inneholder alle appkomponentene ved å bruke navigasjonsruten på venstre side av verktøyet.

![Løsningsutforsker](media/model-driven-app-overview/solutionexplorer-entitiescollapsed.png)

Åpne Løsningsutforsker ved å velge **Modelldrevet** i den venstre ruten i [!INCLUDE [powerapps](../../includes/powerapps.md)].

  ![Velg Modelldrevet](media/model-driven-app-overview/app-type-picker-mod.png)

Velg deretter fanen **Avansert**.

Mer informasjon: [Avansert apputvikling og tilpassing](advanced-navigation.md)

## <a name="related-topics"></a>Relaterte emner

[Valider og publiser den modelldrevne appen](validate-app.md)

[Del den modelldrevne appen](share-model-driven-app.md)