---
title: Common Data Service for apper | Microsoft Docs
description: Innføring i Common Data Service for apper, enheter og serverside-logikk.
services: powerapps
documentationcenter: na
author: clwesene
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 3/21/2018
ms.author: clwesene
ms.openlocfilehash: 939be0cc43e03836d97049addcff27a8e4b063a0
ms.sourcegitcommit: a9d33322228c398d29964429602dc3fe19fa67d2
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/28/2018
ms.locfileid: "30998087"
---
# <a name="common-data-service-for-apps"></a>Common Data Service for apper

Common Data Service lar deg på en sikker måte lagre og behandle data som brukes i apper du har utviklet eller apper fra Microsoft og andre app-leverandører. Data i Common Data Service er lagret i et sett med standard og egendefinerte enheter. En enhet er et sett med felt som brukes til å lagre data til en tabell i en database. Når dataene er lagret, kan du bruke Microsoft PowerApps til å bygge rikholdige programmer ved hjelp av dataene:

* Oppretting av eksisterende standardenheter eller egendefinerte enheter for å støtte scenarioet og programmet.
* Å opprette PowerApps og Flows direkte mot Common Data Service.
* Legg til egendefinerte felt og relasjoner i standardenheter der tilleggsinformasjon er nødvendig.
* Opprett beregnede og fremhevede felt til enheter for å gi konsekvente beregninger på tvers av apper og analyse.
* Definer forretningsregler for å sikre datakvalitet i enheter, uansett hvilken app som har tilgang til eller redigerer dataene.
* Opprett arbeidsflyter og utnytt integrering med Microsoft Flow til å generere flere handlinger og forretningsprosesser mot dataene.
* Innlem standard og egendefinerte enheter i en app som du utvikler like enkelt som du ville gjort med data i andre kilder.
* Koble til dataene fra Microsoft Excel ved hjelp av produktivitetstillegg i Common Data Service.
* Importer og synkroniser dataene på en enkel måte med Power Query.
* Sikre dataene i organisasjonen ved hjelp av rollebasert sikkerhet for standard og egendefinerte enheter.
* Tilby global støtte for dataene og programmene ved å benytte oversettelse av enhets- og feltnavnene til brukernes språk.

Hver enhet inneholder et sett med poster som brukere kan opprette, lese, oppdatere og slette, avhengig av tillatelsene. Du kan opprette relasjoner mellom enheter slik at du kan slå opp informasjon i én enhet som er basert på en post i en annen enhet. Du kan for eksempel opprette en egendefinert enhet for å spore hendelser en kunde har vært delaktig i. Ved å legge kunden til den egendefinerte enheten som et oppslagsfelt, oppretter du en relasjon mellom de to enhetene som kan benyttes i appen og ved rapportering.

Hvis du vil ha informasjon om kjøp av et abonnement for å bruke Common Data Service, kan du se [Prisinformasjon](../../administrator/pricing-billing-skus.md).

## <a name="why-use-the-common-data-service-for-apps"></a>Hvorfor bruke Common Data Service for apper?
Med enheter i Common Data Service (både standard og egendefinert) får man et sikkert og skybasert lagringsalternativ for dataene. Med enheter kan du opprette en forretningsfokusert definisjon av dataene for bruk i appene. Hvis du ikke er sikker på om enheter er det beste alternativet, kan du ta en titt på disse fordelene:

* **Enkelt å administrere** – både metadataene og dataene lagres i skyen. Du trenger ikke å bekymre deg for måten de lagres på.
* **Enkelt å dele** – du kan enkelt dele data med kolleger fordi PowerApps administrerer tillatelsene.
* **Enkelt å sikre** – data lagres på en sikker måte slik at brukere kun kan se dem hvis du gir dem tilgang. Rollebasert sikkerhet lar deg styre tilgang til enheter for forskjellige brukere i organisasjonen.
* **Rike metadata** – datatyper og relasjoner utnyttes direkte i PowerApps. For eksempel vil det å angi en nettadresse for felttyper vise dataene som en hyperkobling i appen.
* **Logikk og validering** – definer beregnede felt, forretningsregler, arbeidsflyter og flyter for forretningsprosesser for å sikre datakvalitet og generere forretningsprosesser.
* **Produktivitetsverktøy** – enheter er tilgjengelige i tilleggene for Microsoft Excel for å øke produktiviteten og sikre at dataene er tilgjengelige.

Når du utvikler en app, kan du bruke standardenheter, egendefinerte enheter eller begge deler. Hvis en standardenhet kan tjene et bestemt formål i appen, bør du bruke den i stedet for å utvikle en egendefinert enhet som virker på samme måte. Hvis en standardenhet vil tjene formålet med noen få endringer, kan du legge til felt for å tilpasse etter dine behov.

* Common Data Service-tjenesten tilbyr standardenheter som standard. Disse er utformet (i henhold til anbefalte fremgangsmåter) med tanke på å skulle fange opp de vanligste konseptene for en organisasjon, for eksempel kontakter, kontoer og produkter. Hvis du vil ha en fullstendig liste over enheter, kan du se [Standardenheter](data-platform-intro.md#standard-entities).
* Du kan utvide funksjonaliteten til standardenheter ved å opprette én eller flere egendefinerte enheter for å lagre informasjon som er unik for organisasjonen. Hvis du vil ha mer informasjon, kan du se [Hvordan opprette en egendefinert enhet](create-custom-entity.md).

> [!NOTE]
> Hvis det er mulig, bør du bruke standardenheter (med egendefinerte felt som er lagt til, om nødvendig). Dette sikrer at du kan dra nytte av nye funksjoner eller apper som benytter disse enhetene i fremtiden.

## <a name="interacting-with-entities"></a>Å arbeide med enheter

Når man bruker en standardenhet eller oppretter en egendefinert enhet, er det flere elementer tilgjengelig i hvert felt og ulike handlinger som kan utføres. Hvilke funksjoner du trenger å bruke avhenger av hvor enkle eller avanserte forretningsscenarioene er. Hvis du vil se enheter som er tilgjengelige i ditt miljø, kan du logge deg på [PowerApps](https://web.powerapps.com) og klikke på Data og deretter på Enheter fra menyen til venstre.

![Enhetsdetaljer](./media/data-platform-cds-intro/entitylist.png "Enhetsdetaljer")

* Hvert **felt** lar deg definere informasjon som samles samt datatypen eller formatet du ønsker å vise den som. Feltene ligner på kolonnene i databaser eller i Excel.
* Vekslende **nøkler** gir rom for effektive og nøyaktige søk og samhandling med poster i enheten når du ikke bruker den unike identifikatoren som er standard. Dette er viktig når du bruker en forretningsnøkkel eller integrerer med et eksternt system.
* Hver enhet kan ha flere **relasjoner** til andre enheter for å støtte oppslag og spørringer på tvers av enheter. Relasjoner kan opprettes for å støtte mange-til-én-, én-til-mange- og mange-til-mange-relasjoner.
* **Visninger** gjør slik at hver enhet kan presenteres på flere måter, inkludert hvilke felt som vises, filtrering og sortering av dataene. Disse presentasjonene lagres som visninger, og kan brukes i andre apper. Eksempelvis vil du kanskje bare se aktive kontoer i appen din, og da bruker du en visning som filtrert på forhånd for å vise bare aktive kontoer for å unngå at filteret gjentas for alle apper som er i bruk.
* **Forretningsregler** kan brukes til å validere data som opprettes og oppdateres i enheter for å sikre datakvalitet. Hver forretningsregel kan validere data på tvers av flere felt og enheter, og aktivere advarsler og feilmeldinger uavhengig av appen som brukes til å opprette dataene.
* **Data** lagret i Common Data Service er tilgjengelig via PowerApps-portalen, PowerApps, Microsoft Excel og Web-API-er for utviklere.

### <a name="system-fields"></a>Systemfelt
Alle enheter, enten det er standard eller egendefinerte, er opprettet med et sett med skrivebeskyttede felt som du ikke kan endre, slette eller angi en verdi for. Dette er de viktigste systemfeltene:

## <a name="logic-and-validation"></a>Logikk og validering

Enheter i Common Data Service kan dra nytte av omfattende serverside-logikk og validering for å sikre datakvalitet og redusere gjentakende kode i hver app for å opprette og bruke dataene i enheten.

* **Forretningsregler** kan validere data på tvers av flere felt og enheter, og aktivere advarsler og feilmeldinger uavhengig av appen som brukes til å opprette dataene. Hvis du vil ha mer informasjon, kan du se [Oppretting av en forretningsregel](./data-platform-create-business-rule.md).
* **Flyter for forretningsprosesser** hjelper brukere å sikre at data angis konsekvent og følger de samme trinnene hver gang. Flyter for forretningsprosesser støttes for øyeblikket bare for modelldrevne apper. Hvis du vil ha mer informasjon, kan du se [Oversikt over flyter for forretningsprosesser](/dynamics365/customer-engagement/customize/business-process-flows-overview).
* **Arbeidsflyter** lar deg automatisere forretningsprosesser uten brukermedvirkning. Hvis du vil ha mer informasjon, kan du se [Oversikt over arbeidsflyter](/dynamics365/customer-engagement/customize/workflow-processes).
* **Forretningslogikk med kode** støtter mer avanserte scenarier for utviklere for å utvide programmet direkte via kode. Hvis du vil ha mer informasjon, kan du se [Å bruke forretningslogikk med kode](../../developer/common-data-service/apply-business-logic-with-code.md).

## <a name="getting-data-into-the-common-data-service"></a>Å hente data til Common Data Service

Det finnes flere måter å komme i gang med å få data inn i Common Data Service på:

* Å opprette en PowerApp eller Flow for å begynne å opprette data.
* Bruk Power Query til å koble til en nettbasert eller lokal datakilde og importere den direkte til Common Data Service. Med Power Query kan du også opprette enhetene under import basert på skjemaet for kilden, såvel som å utføre transformasjoner til dataene under import. Hvis du vil ha mer informasjon, kan du se [Å legge til data i en enhet i Common Data Service ved hjelp av Power Query](./data-platform-cds-newentity-pq.md).

## <a name="developer-capabilities"></a>Utviklerfunksjoner

I tillegg til funksjonene som er tilgjengelige via [PowerApps](https://web.powerapps.com)-portalen, inneholder Common Data Service også funksjoner for utviklere for en programmatisk tilgang til metadata og data for å opprette enheter og forretningslogikk samt samhandle med dataene. Hvis du vil ha mer informasjon, kan du se [Oversikt for utviklere over Common Data Service for apper](../../developer/common-data-service/overview.md)

## <a name="get-started"></a>Kom i gang
Prøv det ut ved å opprette en app ved bruk av en standardenhet eller [opprett en egendefinert enhet](create-custom-entity.md), og deretter [oppretter du en app som bruker denne enheten](../canvas-apps/data-platform-create-app.md).

## <a name="privacy-notice"></a>Erklæring om personvern
Med den vanlige datamodellen i Microsoft PowerApps samler vi inn og lagrer egendefinerte enhets- og feltnavn i diagnostiseringssystemene.  Vi bruker denne kunnskapen til å forbedre den vanlige datamodellen for kundene våre. Enhets- og feltnavnene som skapere oppretter, hjelper oss med å forstå scenarioene som er typiske i Microsoft PowerApps-fellesskapet og få rede på hull i tjenestens standarddekning for enheter, som eksempelvis skjemaer knyttet til organisasjoner. Dataene i databasetabeller som er knyttet til disse enhetene, blir ikke åpnet eller brukt av Microsoft eller replisert utenfor området hvor databasen er klargjort. Merk deg imidlertid at den egendefinerte enheten og feltnavnene kan repliseres på tvers av områder og blir slettet i henhold til retningslinjene våre for dataoppbevaring. Microsoft tar vare på personvernet ditt, som ytterligere beskrevet i [Klareringssenteret](https://www.microsoft.com/trustcenter/Privacy/default.aspx).

