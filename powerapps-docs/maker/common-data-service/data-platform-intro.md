---
title: Hva er Common Data Service for Apps? | Microsoft Docs
description: 'Innføring i Common Data Service (CDS) for Apps, enheter og logikk på serversiden.'
author: clwesene
manager: kfile
ms.service: powerapps
ms.topic: overview
ms.component: cds
ms.date: 05/01/2018
ms.author: matp
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="what-is-common-data-service-for-apps"></a>Hva er Common Data Service for Apps?
Common Data Service (CDS) for Apps lar deg sikkert lagre og behandle dataene som brukes av forretningsprogrammer. Dataene i CDS for Apps er lagret i et sett av enheter. En *enhet* er et sett med oppføringer som er brukt til å lagre data, tilsvarende hvordan en tabell lagrer data i en database. CDS for Apps omfatter et basissett med standardenheter som dekker vanlige scenarioer, men du kan også opprette egendefinerte enheter som er spesifikke for organisasjonen og fylle ut dem med data ved hjelp av Power Query. Apputviklere kan deretter bruke PowerApps til å lage omfattende programmer ved hjelp av dataene.

![Skjermbilde med oversikt over forretningsprogramplattformen.](./media/data-platform-cds-intro/platform.png "Plattformoversikt")

For informasjon om kjøp av et abonnement for å bruke CDS for Apps, se [Prisinformasjon](../../administrator/pricing-billing-skus.md).

## <a name="why-use-common-data-service-for-apps"></a>Hvorfor bruke Common Data Service for Apps?
Standardenheter og tilpassede enheter i CDS for Apps utgjør et sikkert og skybasert lagringsalternativ for dataene. Enheter lar deg opprette en bedriftsfokusert definisjon av organisasjonens data for bruk i mobilapper. Hvis du ikke er sikker på om enheter er det beste alternativet, kan du vurdere følgende fordeler:

* **Enkel å administrere** &ndash; Begge metadata og data lagres i skyen. Du trenger ikke å bekymre deg om detaljene om hvordan de er lagret.
* **Enkel å sikre** &ndash; Dataene er lagret på en sikker måte, slik at brukere bare kan se dem hvis du gir dem tilgang. Rollebasert sikkerhet gjør det mulig å kontrollere tilgang til enheter for ulike brukere i organisasjonen.
* **Tilgang til Dynamics 365-dataene** &ndash; Data fra Dynamics 365-programmer er også lagret i Common Data Service for Apps, slik at du raskt kan bygge programmer som bruker Dynamics 365-dataene, og utvide appene ved hjelp av PowerApps.
* **Avanserte metadata** &ndash; Datatyper og relasjoner utnyttes direkte fra PowerApps.
* **Logikk og validering** &ndash; Definer beregnede felt, forretningsregler, arbeidsflyter og forretningsprosessflyter for å sørge for datakvalitet og drive forretningsprosesser.
* **Produktivitetsverktøy** &ndash; Enheter som er tilgjengelige i tillegg for Microsoft Excel, for å øke produktiviteten og sikre datatilgjengelighet.

## <a name="dynamics-365-and-the-common-data-service-for-apps"></a>Dynamics 365 og Common Data Service for Apps

Dynamics 365-programmer, for eksempel Dynamics 365 for Sales, Service eller Talent, bruker også Common Data Service for Apps til å lagre og sikre data som brukes av programmene. Dette gjør det mulig for deg å bygge programmer ved hjelp av PowerApps og Common Data Service for Apps direkte mot kjerneforretningsdataene som allerede brukes i Dynamics 365, uten behov for integrering.

* **Bygg apper mot Dynamics 365-dataene** &ndash; Bygg apper raskt mot forretningsdataene i PowerApps eller med Pro Developer SDK.
* **Administrer gjenbrukbar forretningslogikk og -regler** &ndash; Forretningsregler og -logikk som allerede er definert i Dynamics 365-enhetene dine, brukes i PowerApps for å sørge for datakonsistens, uavhengig av hvordan brukerne får tilgang til dataene, eller uansett app.
* **Gjenbrukbare ferdigheter på tvers av Dynamics 365 og PowerApps** &ndash; Brukere med ferdigheter tidligere i PowerApps eller Dynamics 365 kan nå bruke disse ferdigheter på tvers av den nye plattformen Common Data Service for Apps. Opprette enheter, skjemaer, diagrammer osv er nå felles på tvers av programmer.

    > [!NOTE]
    > Dynamics 365 for Finance and Operations krever for øyeblikket konfigurasjon av Data Integrator for å gjøre forretningsdataene fra Finance and Operations tilgjengelige i Common Data Service for Apps.

## <a name="integrating-data-into-the-common-data-service"></a>Integrere data i Common Data Service

Bygging av en app inkluderer vanligvis data fra flere kilder, mens dette noen ganger kan utføres på programnivå, og det er også tilfeller der integrering av disse dataene samlet til et felles lager tillater en enklere appbyggeopplevelse, og ett enkelt sett med logikk for å vedlikeholde og bruke dataene. Common Data Service for Apps gjør det mulig å integrere data fra flere kilder til ett enkelt lager, som deretter kan brukes i PowerApps, flyten og Power BI sammen med dataene som allerede er tilgjengelige fra Dynamics 365-programmene.

* **Planlagt integrering med andre systemer** &ndash; Data som skal beholdes i et annet program, kan regelmessig synkroniseres med Common Data Service for Apps for at du skal bruke data fra andre programmer i PowerApps.
* **Transformere og importere data ved hjelp av PowerQuery** &ndash; Transformering av data når du importerer til Common Data Service kan utføres via PowerQuery fra mange online datakilder, et vanlig verktøy som brukes på tvers av Excel og Power BI.
* **Éngangsimport av data** &ndash; Enkel import og eksport til Excel- og CSV-filer kan brukes for éngangs eller sjelden import av data til Common Data Service for Apps.

Hvis du vil ha mer informasjon om hvordan du integrerer data i Common Data Service, se [Legge til data i en enhet i Common Data Service for Apps ved hjelp av Power Query](data-platform-cds-newentity-pq.md).

## <a name="interacting-with-entities"></a>Samhandle med enheter
Når du utvikler en app, kan du bruke standardenheter, egendefinerte enheter eller begge deler. CDS for Apps inneholder standardenheter som standard. Disse er utviklet, i henhold til gode fremgangsmåter, for å fange opp de mest vanlige konseptene og scenarioene i en organisasjon.

![Skjermbilde viser en liste over enheter.](./media/data-platform-cds-intro/entitylist.png "Enhetsliste")

For en fullstendig liste over enheter, kan du se [enhetsreferansen](https://docs.microsoft.com/powerapps/developer/common-data-service/reference/about-entity-reference).

Du kan utvide funksjonaliteten til standardenheter ved å opprette en eller flere egendefinerte enheter for å lagre informasjon som er unik for organisasjonen. Hvis du vil ha mer informasjon, kan du se [Slik oppretter du en egendefinert enhet](create-custom-entity.md).

## <a name="logic-and-validation"></a>Logikk og validering
Enheter i CDS for Apps kan dra nytte av rik logikk på serversiden og validering for å sikre datakvalitet og redusere repeterende kode i hver app som oppretter og bruker data i en enhet.

* **Forretningsregler** Valider data på tvers av flere felt og enheter og gi advarsels- og feilmeldinger, uavhengig av appen som brukes til å opprette dataene. Hvis du vil ha mer informasjon, kan du se [Opprette en forretningsregel](./data-platform-create-business-rule.md).
* **Forretningsprosessflyter** Rettled brukere for å sikre at de skriver inn data konsekvent og følger de samme trinnene hver gang. Forretningsprosessflyter støttes for øyeblikket bare for modelldrevne apper. For mer informasjon, se [Oversikt over forretningsprosessflyter](/dynamics365/customer-engagement/customize/business-process-flows-overview).
* **Arbeidsflyter** lar deg automatisere forretningsprosesser uten brukerhandling. Hvis du vil ha mer informasjon, kan du se [Oversikt over arbeidsflyter](/dynamics365/customer-engagement/customize/workflow-processes).
* **Forretningslogikk med kode** støtter avanserte utviklerscenarier for å utvide programmet direkte via kode. Hvis du vil ha mer informasjon, kan du se [Bruke forretningslogikk med kode](../../developer/common-data-service/apply-business-logic-with-code.md).

## <a name="developer-capabilities"></a>Funksjoner for utviklere
I tillegg til funksjonene som er tilgjengelige via [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)-portalen, inneholder CDS for Apps også funksjoner som utviklere kan bruke til programmatisk tilgang til metadata og data, for å opprette enheter og forretningslogikk, i tillegg til å samhandle med data. Hvis du vil ha mer informasjon, kan du se [Oversikt over Common Data Service for apputviklere](../../developer/common-data-service/overview.md)

## <a name="next-steps"></a>Neste trinn
Slik kommer du i gang med CDS for Apps:
* [Opprett en app ved å bruke en Common Data Service-database](../canvas-apps/data-platform-create-app-scratch.md).
* [Opprett en egendefinert enhet](create-custom-entity.md) og [opprett deretter en app som bruker enheten](../canvas-apps/data-platform-create-app.md).
* [Bruk Power Query](./data-platform-cds-newentity-pq.md) til å koble til en elektronisk eller lokal datakilde og importere dataene direkte i CDS for Apps.

## <a name="privacy-notice"></a>Personvernerklæring
Med Common Data Model for Microsoft PowerApps samler og lagrer Microsoft egendefinert enhets- og feltnavn i diagnosesystemene våre. Vi bruker denne kunnskapen til å forbedre Common Data Model for kundene våre. Enhets- og feltnavnene som appoppretterne lager, hjelper oss å forstå scenarioer som er vanlige i Microsoft PowerApps-fellesskapet, og fastslår mangler i tjenestens standardenhetsdekning, for eksempel skjemaer som er relatert til organisasjoner. Dataene i databasetabellene som er knyttet til disse enhetene, brukes ikke eller er ikke tilgjengelige for Microsoft eller replikeres utenfor området der databasen klargjøres. Vær imidlertid oppmerksom på at de egendefinerte enhets- og feltnavnene kan replikeres på tvers av områder, og slettes i henhold til våre oppbevaringspolicyer for data. Microsoft går inn for å verne om dine personlige opplysninger som beskrevet ytterligere i vårt [Klareringssenter](https://www.microsoft.com/trustcenter/Privacy/default.aspx).
