---
title: Utvikling ved hjelp av Common Data Model | Microsoft Docs
description: Gir informasjon om hvordan du kan bruke Common Data Model til å utvikle programmer og løsninger.
author: RobertBruckner
ms.service: powerapps
ms.topic: article
ms.date: 07/24/2018
ms.author: robruc
ms.openlocfilehash: 6e99fbe13d9b6e3acdd0cfdd08662676a321471c
ms.sourcegitcommit: abe4d4728db7f56088f618af5b820af78e7099c9
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 07/28/2018
ms.locfileid: "39332092"
---
# <a name="how-to-use-the-common-data-model"></a>Slik bruker du Common Data Model

Med **Common Data Model (CDM)** kan du plassere dataene i formater som representerer konsepter og aktiviteter som ofte brukes, og som i stor grad blir brukt og forstått, slik at du kan sende en spørring til dataene, bruke dem på nytt og samhandle med andre bedrifter og programmer som også bruker dette formatet. På samme måte som at du vet størrelsen og formen på et AA-batteri, og at de kan brukes i alle fjernkontroller, definerer CDM størrelsen og formen på en *Kontakt* (for eksempel), slik at programutviklere og bedriftspartnere vet hvordan de skal bruke dataene og kan bygge programmene dine (eller samhandle med dem) smidig og trygt. Og ettersom CDM er en definisjon av standard enheter med åpen kildekode, kan fellesskapet av interesserte utviklere enkelt forstå og delta i skjemadefinisjoner.

I dag brukes CDM i Common Data Service (CDS) for apper, som støtter Dynamics og PowerApps, og i funksjonene for dataforberedelse i Power BI til å opprette skjematiserte filer i Azure Data Lake.

![Common Data Model med CDS for apper](media/cdm-with-cds.png)

Du kan bruke CDM og CDS for apper på følgende måter:

-   **Lagre og behandle data i CDM-format på en sikker måte**: Du kan bruke CDS for apper til å lagre og behandle dataene dine på en sikker måte i det standardiserte CDM-formatet. Ved å gjøre dette får du tilgang til og kan bruke disse dataene i Microsoft-programmer og -tjenester, for eksempel Dynamics, Power Apps, Flow eller Power BI, eller dine egne egendefinerte programmer.

-   **Opprette egendefinerte CDM-enheter**: CDM kan utvides, slik at du kan opprette hvilke som helst enhetstyper som ikke allerede finnes i CDM, som er spesifikke for din organisasjon, og fylle ut disse enhetene med eksisterende data ved hjelp av **Power Query**. På denne måten kan du dra nytte av CDM og skreddersy den for bedriften din.

-   **Opprette dine egne repositorier med data**: Du kan bygge repositorier med data som samsvarer med **Common Data Model (CDM)**-skjemaet, og koble til disse datakildene ved hjelp av Microsoft-datakoblinger. På denne måten kan du bygge egendefinerte bransjespesifikke programmer som bruker eller deler CDM-dataene dine, uavhengig av hvor dataene stammer fra eller er lagret.

-   **Raskt utlede og distribuere innsikt ved hjelp av Power BI**: Du kan bruke avanserte tjenester for dataforberedelse i Power BI som benytter CDM-datalagrene dine (for eksempel data du har plassert i CDS for apper) til å opprette rapporter og instrumentbord, og deretter opprette rapportgenererende programmer som automatisk henter inn CDM-dataene i tilpasset innsikt for enkeltpersoner og grupper i organisasjonen.

-   **Produsere tilpassede, men organisasjonsomfattende rapporter i Power BI**: Du kan bruke programmer som automatisk genererer tilpassede rapporter du kan plassere i Power BI-arbeidsområder for brukere i organisasjonen og andre steder.

Etter hvert som Microsoft fortsetter å utvide CDM, vil nye bransjer, som for eksempel helsesektoren, sammen med mange partnere og emneeksperter, kunne dra nytte av CDM og plattformene som støtter den.

## <a name="data-integration-and-power-query-online"></a>Dataintegrering og Power Query Online

Begge plattformene som for øyeblikket støtter CDM, tilbyr også dataintegrering gjennom Power Query Online, som tillater at brukere henter inn data fra en rekke kilder, transformerer dem om nødvendig, og deretter tilordner dem til standard CDM-enheter eller oppretter egendefinerte enheter. Power Query Online bruker den samme visuelle, selvbetjente funksjonaliteten for dataforberedelse som Power Query i Excel og Power BI Desktop, slik at eksisterende brukere kan komme i gang raskt.

![Tilordne data med enheter i CDM](media/cdm-map-entities.png)

## <a name="common-data-service-for-apps"></a>Common Data Service for apper

Med CDS for apper kan du raskt komme i gang med programmer ved å bruke CDM med innebygd forretningslogikk, sikkerhet og integrering. Med plattformen kan du:

-   **Dra nytte av pakkede forretningsprogrammer**: Mange Microsoft Dynamics-løsninger, og mange tredjepartsprogrammer, er basert på (eller benytter i hvert fall) CDS for apper. Når dataene er i CDM, kan du dra nytte av disse pakkede programmene.

-   **Få tilgang til tilpassede løsninger**: Det finnes et økosystem med utvidelser og fullstendige programmer som er opprettet av utviklere som forstår og arbeider med data i CDM-format. Se [innføring i løsninger](https://docs.microsoft.com/powerapps/developer/common-data-service/introduction-solutions) hvis du vil ha mer informasjon.

Uansett hva hensikten din er, plasserer CDM dataene dine i et vanlig format slik at du kan bruke, dele og analysere dem på en enklere måte.

**Ressurser for CDS for apper**

-   [Hva er CDS for apper?](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro)

-   [Legg til data i en enhet i CDS for apper ved hjelp av Power Query](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-cds-newentity-pq)

-   [Innføring i løsninger](https://docs.microsoft.com/powerapps/developer/common-data-service/introduction-solutions)

-   [Å bygge en modelldrevet app](https://docs.microsoft.com/powerapps/maker/model-driven-apps/model-driven-app-overview)

-   [Å bygge en lerretsapp](https://docs.microsoft.com/powerapps/maker/canvas-apps/getting-started)

-   [Opprett en flyt som bruker CDS for apper](https://docs.microsoft.com/flow/common-data-model-intro)

