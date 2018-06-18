---
title: Hva er Common Data Service for apper? | Microsoft Docs
description: Innføring i Common Data Service for apper, enheter og serverside-logikk.
author: Mattp123
manager: kfile
ms.service: powerapps
ms.topic: overview
ms.component: cds
ms.date: 05/01/2018
ms.author: matp
ms.openlocfilehash: b26f788a782e42125d6397d38b2d946f8188e475
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/04/2018
ms.locfileid: "34552833"
---
# <a name="what-is-common-data-service-for-apps"></a>Hva er Common Data Service for apper?
Common Data Service (CDS) for apper lar deg lagre og behandle data som brukes av forretningsprogrammer på en sikker måte. Data i CDS for apper lagres i et sett med enheter. En *enhet* er et sett med poster som brukes til å lagre data. Det ligner en tabell i en database. CDS for apper inkluderer et grunnleggende sett med standardenheter som dekker vanlige scenarioer, men du kan også opprette egendefinerte enheter som er spesifikke for din organisasjon, og fylle dem med data ved hjelp av Power Query. Apputviklere kan deretter bruke PowerApps til å bygge rike programmer ved hjelp av disse dataene.

Hvis du vil ha informasjon om kjøp av et abonnement for å bruke CDS for apper, kan du se [Prisinformasjon](../../administrator/pricing-billing-skus.md).

## <a name="why-use-common-data-service-for-apps"></a>Hvorfor bruke Common Data Service for apper?
Med enheter i Common Data Service (både standard og egendefinert) får man et sikkert og skybasert lagringsalternativ for dataene. Med enheter kan du opprette en forretningsfokusert definisjon av organisasjonens data for bruk i appene. Hvis du ikke er sikker på om enheter er det beste alternativet, kan du ta en titt på disse fordelene:

* **Enkelt å administrere** &ndash; både metadataene og dataene lagres i skyen. Du trenger ikke å bekymre deg for måten de lagres på.
* **Enkelt å dele** &ndash; du kan enkelt dele data med kolleger&mdash;fordi PowerApps administrerer tillatelsene.
* **Enkelt å sikre** &ndash; data lagres på en sikker måte slik at brukere kun kan se dem hvis du gir dem tilgang. Rollebasert sikkerhet lar deg styre tilgang til enheter for forskjellige brukere i organisasjonen.
* **Rike metadata** &ndash; datatyper og relasjoner utnyttes direkte i PowerApps. For eksempel vil det å angi en nettadresse for felttyper, vise dataene som en hyperkobling i appen.
* **Logikk og validering** &ndash; definer beregnede felt, forretningsregler, arbeidsflyter og flyter for forretningsprosesser for å sikre datakvalitet og generere forretningsprosesser.
* **Produktivitetsverktøy** &ndash; enheter er tilgjengelige i tilleggene for Microsoft Excel for å øke produktiviteten og sikre at dataene er tilgjengelige.

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
