---
title: Hva er Common Data Service for apper? | Microsoft Docs
description: Innføring i Common Data Service for apper, enheter og serverside-logikk.
author: clwesene
manager: kfile
ms.service: powerapps
ms.topic: overview
ms.component: cds
ms.date: 05/01/2018
ms.author: matp
ms.openlocfilehash: 586750edf476a9145e2822522cc0b4b5ad729539
ms.sourcegitcommit: 7296649d03ebc33dc5ddb9e7c551869dc781f154
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/09/2018
ms.locfileid: "35250827"
---
# <a name="what-is-common-data-service-for-apps"></a>Hva er Common Data Service for apper?
Common Data Service (CDS) for apper lar deg lagre og behandle data som brukes av forretningsprogrammer på en sikker måte. Data i CDS for apper lagres i et sett med enheter. En *enhet* er et sett med poster som brukes til å lagre data. Det ligner en tabell i en database. CDS for apper inkluderer et grunnleggende sett med standardenheter som dekker vanlige scenarioer, men du kan også opprette egendefinerte enheter som er spesifikke for din organisasjon, og fylle dem med data ved hjelp av Power Query. Apputviklere kan deretter bruke PowerApps til å bygge rike programmer ved hjelp av disse dataene.

![Skjermbilde som viser en oversikt over forretningsprogramplattformen. ](./media/data-platform-cds-intro/platform.png "Plattformoversikt")

Hvis du vil ha informasjon om kjøp av et abonnement for å bruke CDS for apper, kan du se [Prisinformasjon](../../administrator/pricing-billing-skus.md).

## <a name="why-use-common-data-service-for-apps"></a>Hvorfor bruke Common Data Service for apper?
Med enheter i Common Data Service (både standard og egendefinert) får man et sikkert og skybasert lagringsalternativ for dataene. Med enheter kan du opprette en forretningsfokusert definisjon av organisasjonens data for bruk i appene. Hvis du ikke er sikker på om enheter er det beste alternativet, kan du ta en titt på disse fordelene:

* **Enkelt å administrere** &ndash; både metadataene og dataene lagres i skyen. Du trenger ikke å bekymre deg for måten de lagres på.
* **Enkelt å sikre** &ndash; data lagres på en sikker måte slik at brukere kun kan se dem hvis du gir dem tilgang. Rollebasert sikkerhet lar deg styre tilgang til enheter for forskjellige brukere i organisasjonen.
* **Få tilgang til dataene for Dynamics 365** &ndash; Dataene fra appene for Dynamics 365 er også lagret i Common Data Service for apper, slik at du raskt kan bygge apper som drar nytte av dataene for Dynamics 365, og utvide appene med bruk av PowerApps.
* **Rike metadata** &ndash; datatyper og relasjoner utnyttes direkte i PowerApps.
* **Logikk og validering** &ndash; definer beregnede felt, forretningsregler, arbeidsflyter og flyter for forretningsprosesser for å sikre datakvalitet og generere forretningsprosesser.
* **Produktivitetsverktøy** &ndash; enheter er tilgjengelige i tilleggene for Microsoft Excel for å øke produktiviteten og sikre at dataene er tilgjengelige.

## <a name="dynamics-365-and-the-common-data-service-for-apps"></a>Dynamics 365 og Common Data Service for apper

Apper for Dynamics 365, for eksempel Dynamics 365 for Sales, Service eller Talent, bruker også Common Data Service for apper til å lagre og sikre data som brukes av appene. Dette gjør det mulig å bygge apper med PowerApps og Common Data Service for apper direkte mot kjernen for forretningsdataene som allerede brukes i Dynamics 365, uten behov for integrering.

* **Bygg apper mot Dynamics 365** &ndash; Bygg apper raskt mot forretningsdataene i PowerApps eller ved hjelp av Pro Developer SDK.
* **Administrer gjenbrukbar forretningslogikk og regler** &ndash; Forretningsregler og logikk som allerede er definert i enhetene for Dynamics 365, brukes i PowerApps til å sikre datakonsekvens uavhengig av hvordan brukerne har tilgang til dataene, eller gjennom hvilket program.
* **Gjenbrukbare ferdigheter på tvers av Dynamics 365 og PowerApps** &ndash; Brukere med tidligere ferdigheter i PowerApps eller Dynamics 365, kan nå benytte disse ferdighetene på tvers av den nye plattformen for Common Data Service for apper. Oppretting av enheter, skjemaer, diagrammer og så videre, er nå vanlig på tvers av appene.

    > [!NOTE]
    > Dynamics 365 for Finance and Operations krever for øyeblikket konfigurasjonen av dataintegratoren for å gjøre forretningsdataene fra Finance and Operations tilgjengelig i Common Data Service for apper.

## <a name="integrating-data-into-the-common-data-service"></a>Slik integrerer du data i Common Data Service

Det innebærer vanligvis data fra mer enn én kilde når du bygger en app. Selv om dette noen ganger kan gjøres på appnivå, finnes det også tilfeller der integrering av disse dataene i et felles lager, gjør det mulig med en enklere bygging av apper og et enkelt sett med logikk for å vedlikeholde og arbeide med dataene. Common Data Service for apper gjør det mulig å integrere data fra flere kilder i et enkelt lager som deretter kan brukes i PowerApps, Flow og Power BI, sammen med data som allerede er tilgjengelige fra appene i Dynamics 365.

* **Planlagt integrering med andre systemer** &ndash; Data som beholdes i en annen app kan synkroniseres regelmessig med Common Data Service for apper, slik at du kan dra nytte av andre appdata i PowerApps.
* **Transformer og importer data ved hjelp av PowerQuery** &ndash; Transformering av data ved importering til Common Data Service kan gjøres via PowerQuery fra mange nettbaserte datakilder, et vanlige verktøy som brukes på tvers av Excel og Power BI.
* **Engangsimport av data** &ndash; Enkel import og eksport av filer i Excel og CSV kan brukes for et engangstilfelle eller for sjelden import av data i Common Data Service for apper.


## <a name="interacting-with-entities"></a>Å arbeide med enheter
Når du utvikler en app, kan du bruke standardenheter, egendefinerte enheter eller begge deler. Common Data Service-tjenesten for apper tilbyr standardenheter som standard. Disse er utformet (i henhold til anbefalte fremgangsmåter) med tanke på å skulle fange opp de vanligste konseptene og scenariene for en organisasjon.

![Skjermbilde som viser en liste over enheter. ](./media/data-platform-cds-intro/entitylist.png "Enhetsliste")

Hvis du vil ha en fullstendig liste over enheter, kan du se [Enhetsreferanse](https://docs.microsoft.com/powerapps/developer/common-data-service/reference/about-entity-reference).

Du kan utvide funksjonaliteten til standardenheter ved å opprette én eller flere egendefinerte enheter for å lagre informasjon som er unik for organisasjonen. Hvis du vil ha mer informasjon, kan du se [Hvordan opprette en egendefinert enhet](create-custom-entity.md).

## <a name="logic-and-validation"></a>Logikk og validering
Enheter i Common Data Service for apper kan dra nytte av omfattende serverside-logikk og validering for å sikre datakvalitet og redusere gjentakende kode i hver app som oppretter og bruker data i en enhet.

* **Forretningsregler** kan validere data på tvers av flere felt og enheter og aktivere advarsler og feilmeldinger, uavhengig av appen som brukes til å opprette dataene. Hvis du vil ha mer informasjon, kan du se [Oppretting av en forretningsregel](./data-platform-create-business-rule.md).
* **Flyter for forretningsprosesser** hjelper brukere å sikre at data angis konsekvent og følger de samme trinnene hver gang. Flyter for forretningsprosesser støttes for øyeblikket bare for modelldrevne apper. Hvis du vil ha mer informasjon, kan du se [Oversikt over flyter for forretningsprosesser](/dynamics365/customer-engagement/customize/business-process-flows-overview).
* **Arbeidsflyter** lar deg automatisere forretningsprosesser uten brukermedvirkning. Hvis du vil ha mer informasjon, kan du se [Oversikt over arbeidsflyter](/dynamics365/customer-engagement/customize/workflow-processes).
* **Forretningslogikk med kode** støtter mer avanserte scenarier for utviklere for å utvide programmet direkte via kode. Hvis du vil ha mer informasjon, kan du se [Å bruke forretningslogikk med kode](../../developer/common-data-service/apply-business-logic-with-code.md).

## <a name="developer-capabilities"></a>Utviklerfunksjoner
I tillegg til funksjonene som er tilgjengelige via [PowerApps](https://web.powerapps.com)-portalen, inneholder CDS for apper også funksjoner for utviklere for en programmatisk tilgang til metadata og data for å opprette enheter og forretningslogikk samt samhandle med dataene. Hvis du vil ha mer informasjon, kan du se [Oversikt for utviklere over Common Data Service for apper](../../developer/common-data-service/overview.md)

## <a name="next-steps"></a>Neste trinn
Slik kommer du i gang med å bruke CDS for apper ved å:
* [generere en app ved hjelp av en Common Data Service-database](../canvas-apps/data-platform-create-app-scratch.md).
* [opprette en egendefinert enhet ](create-custom-entity.md) og deretter [opprette en app som bruker denne enheten](../canvas-apps/data-platform-create-app.md).
* [bruke Power Query](./data-platform-cds-newentity-pq.md) til å koble til en nettbasert eller lokal datakilde, og importere den direkte til Common Data Service for apper.

## <a name="privacy-notice"></a>Erklæring om personvern
Med den vanlige datamodellen i Microsoft PowerApps samler vi inn og lagrer egendefinerte enhets- og feltnavn i diagnostiseringssystemene. Vi bruker denne kunnskapen til å forbedre den vanlige datamodellen for kundene våre. Enhets- og feltnavnene som app-oppretterne lager, hjelper oss med å forstå Scenarioer som er typiske i Microsoft PowerApps-fellesskapet, og få rede på hull i tjenestens standarddekning for enheter, som eksempelvis skjemaer knyttet til organisasjoner. Dataene i databasetabeller som er knyttet til disse enhetene, blir ikke åpnet eller brukt av Microsoft eller replisert utenfor området hvor databasen er klargjort. Merk deg imidlertid at den egendefinerte enheten og feltnavnene kan repliseres på tvers av områder og blir slettet i henhold til retningslinjene våre for dataoppbevaring. Microsoft tar vare på personvernet ditt, som ytterligere beskrevet i [Klareringssenteret](https://www.microsoft.com/trustcenter/Privacy/default.aspx).
