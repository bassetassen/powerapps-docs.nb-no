---
title: Enhetsmetadata | Microsoft Docs
description: Lær om bruken av enhetsmetadata i Common Data Service for apper.
services: ''
suite: powerapps
documentationcenter: na
author: JimDaly
manager: faisalmo
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/19/2018
ms.author: jdaly
search.audienceType:
- developer
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: 60fafa90df656bb6d135a8cf7e2c2f3b4f8457da
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/24/2018
ms.locfileid: "42840750"
---
# <a name="entity-metadata"></a>Enhetsmetadata

Du kan lagre strukturerte data i hver enhet. For utviklere så tilsvarer enheter klassene du bruker når du arbeider med data i Common Data Service for apper.

## <a name="entity-names"></a>Enhetsnavn
Hver enhet får definert et unikt navn under opprettelsen. Dette navnet presenteres på flere måter:

|Navneegenskap |Beskrivelse|
|---------|---------|
|`SchemaName`|Som regel en Pascal-versjon av det logiske navnet. dvs. Konto|
|`CollectionSchemaName`|En flertallsform av skjemanavnet. dvs. Kontoer|
|`LogicalName`|Alle versjoner av skjemanavnet, med små bokstaver. dvs. konto|
|`LogicalCollectionName`|Alle versjoner av samlingsskjemanavnet, med små bokstaver. dvs. kontoer|
|`EntitySetName`|Brukes for å identifisere samlinger med Web API-en. Det er som standard det samme som det logiske samlingsnavnet.<br />Det er mulig å endre Enhetssett-navnet ved å oppdatere metadataene programmatisk. Men dette bør bare gjøres før en Web API-kode skrives for enheten. Mer informasjon: [Utviklerveiledning for Dynamics 365 Customer Engagement: Web API-typer og -operasjoner > Endre navnet på et enhetssett](/dynamics365/customer-engagement/developer/webapi/web-api-types-operations#change-the-name-of-an-entity-set)|

> [!NOTE]
> Når du oppretter en egendefinert enhet, vil navnet du velger starte med tilpassingsprefiksverdien til løsningsutgiveren som er tilknyttet med løsningen, der enheten ble opprettet i. Du kan endre navnet på enhetssettet etter at enheten er opprettet, men du kan ikke endre navnet på selve enheten. Hvis du ønsker konsekvente navn for metadataelementene i løsningen, bør du opprette dem i en løsning som opprettes tilknyttet en løsningsutgiver – som inneholder tilpassingsprefikset du ønsker å bruke. Mer informasjon: [Opprett en løsningsutgiver og løsning](introduction-solutions.md#create-a-solution-publisher-and-solution)

Hver enhet har også tre egenskaper som kan vise lokaliserte verdier:


|Navn  |Beskrivelse  |
|---------|---------|
|`DisplayName`|Vanligvis det samme som skjemanavnet, men kan inneholde mellomrom. dvs. Konto|
|`DisplayCollectionName`|En flertallsform av visningsnavnet. dvs. Kontoer|
|`Description`|En kort setning som beskriver enheten, dvs. *virksomhet som presenterer en kunde eller potensiell kunde. Firmaet som faktureres i forretningstransaksjoner.*|

Disse er lokaliserbare verdier som brukes for å henvise til enhetene i en app. Disse verdiene kan endres når som helst. Hvis du vil legge til eller endre lokaliserte verdier, kan du se  [Tilpassingsveiledning for Dynamics 365: Oversett egendefinert enhets- og felttekst til andre språk](/dynamics365/customer-engagement/customize/export-customized-entity-field-text-translation).


## <a name="primary-key"></a>Primærnøkkel

`PrimaryIdAttribute`-egenskapsverdien er det logiske navnet til attributtet som er primærnøkkelen for enheten.

Alle enhetene har som standard et enkelt unikt identifikatorattributt for GUID. Dette har som regel navnet *&lt; logisk navn for enhet &gt;*+ `Id`.

## <a name="primary-name"></a>Primært navn

`PrimaryNameAttribute`-egenskapsverdien er det logiske navnet på attributtet som lagrer strengverdien, som identifiserer enhetsposten. Dette er verdien som vises i en kobling som åpner posten i et brukergrensesnitt.

**Eksempel**: Kontaktenheten bruker `fullname`-attributtet som attributt for primært navn.

> [!NOTE]
> Ikke alle enheter har et primært navn. Noen enheter er ikke ment å vises i et brukergrensesnitt.

## <a name="entity-images"></a>Enhetsbilder

`PrimaryImageAttribute`-egenskapsverdien er det logiske navnet på attributtet som lagrer bildedataene for enhetsposten. Hver enhet kan bare ha ett bildeattributt, og det logiske navnet på attributtet er alltid `entityimage`.

**Eksempel**: [Kontaktenhet](reference/entities/contact.md) [EntityImage](reference/entities/contact.md#BKMK_EntityImage)-attributtet kan lagre et bilde av kontakten,.

Enhetsbilder er ikke inkludert i henteoperasjoner med mindre uttrykkelig angitt, med hensyn til ytelsen.

Hver enhet som støtter enhetsbilder, har tre støttende attributter.

|SchemaName|Type|Beskrivelse|
|--|--|--|
|`EntityImage_Timestamp` |`BigIntType`|Verdien representerer når bildet ble oppdatert sist, og brukes for å sikre at siste versjon av bildet lastes ned og bufres på klienten.|
|`EntityImage_URL`|`StringType`|En absolutt nettadresse som viser enhetsbildet i en klient.|
|`EntityImageId`|`UniqueIdentifierType`|Den unike ID-en til bildet.|

Mer informasjon: 
- [Utviklerveiledning for Dynamics 365 Customer Engagement – Bildeattributter](/dynamics365/customer-engagement/developer/image-attributes)
- [Eksempel fra Utviklerveiledning for Dynamics 365 Customer Engagement: Angi og hent enhetsbilder](/dynamics365/customer-engagement/developer/sample-set-retrieve-entity-images)

> [!NOTE]
> Dette er forskjellig fra ikonet som vises for enhet i modelldrevne apper. `IconVectorName`-egenskapen inneholder navnet på SVG-nettressursen som angir dette.

## <a name="types-of-entities"></a>Enhetstyper

Funksjonene og virkemåten til enhetene avhenger av flere enhetsegenskaper. Flesteparten av disse egenskapene er relativt enkle, og de har beskrivende navn. Det er fire som krever litt mer forklaring, og de er: *Eierskap*, *Aktivitetsenheter*, *Activityparty-enhet* og *Underordnede enheter*.

### <a name="entity-ownership"></a>Eierskap for enhet

Enheter kan kategoriseres etter hvordan dataene i dem, eies. Dette er et viktig konsept knyttet til hvordan sikkerhet gjelder for enheter. Denne informasjonen finnes i `OwnershipType`-egenskapen. Den følgende tabellen beskriver de forskjellige eierskapstypene:

|Eierskapstype  |Beskrivelse  |
|---------|---------|
|Bedriften din|Data tilhører forretningsenheten. Tilgang til dataene kan kontrolleres på forretningsenhetsnivå.|
|Ingen|Data som ikke eies av en annen enhet.|
|Organisasjon|Data tilhører organisasjonen. Tilgang til dataene kan kontrolleres på organisasjonsnivå.|
|Bruker eller team|Data tilhører en bruker eller et team. Handlinger som kan utføres på disse postene, kan kontrolleres på et brukernivå.|

Når du oppretter nye enheter, er de eneste eierskapsalternativene: **Organisasjon** eller **Bruker eller team**. Når du foretar et valg for dette alternativet, kan du ikke endre det. Velg **Bruker eller team** for den mest detaljerte kontrollen over hvem som kan vise eller utføre handlinger på postene. Velg **Organisasjon** når dette kontrollnivået ikke er nødvendig. 

### <a name="activity-entities"></a>Aktivitetsenheter

En aktivitet er en oppgave som utføres, eller som skal utføres, av en bruker. En aktivitet er en hvilken som helst handling en kan føre opp i en kalender. 

Aktiviteter er modellert forskjellig fra andre typer enheter som lagrer bedriftsdata. Data om aktiviteter vises ofte sammen i en liste, men hver aktivitetstype krever unike egenskaper. I stedet for å ha en enkelt aktivitetsenhet med hver mulige egenskap, finnes det separate typer aktivitetsenheter. Hver av dem arver egenskapene fra en grunnleggende [aktivitetspekerenhet](reference/entities/activitypointer.md). Disse enhetene har `IsActivity`-egenskapen angitt til sann.


|Enhet |Beskrivelse  |
|---------|---------|
|[Avtale](reference/entities/appointment.md)|Forpliktelse som representerer et tidsintervall med start-/sluttidspunkt og varighet.|
|[Email](reference/entities/email.md)|Aktivitet som leveres ved bruk av e-postprotokoller.|
|[Faks](reference/entities/fax.md)|Aktivitet som sporer samtaleresultat og antall sider for en faks, og eventuelt lagrer en elektronisk kopi av dokumentet.|
|[Letter](reference/entities/letter.md)|Aktivitet som sporer leveringen av et brev. Aktiviteten kan inneholde den elektroniske kopien av et brev.|
|[Telefonsamtale](reference/entities/phonecall.md)|Aktivitet for å spore en telefonsamtale.|
|[RecurringAppointmentMaster](reference/entities/recurringappointmentmaster.md)|Hovedavtalen for en regelmessig avtaleserie.|
|[Sosial aktivitet](reference/entities/socialactivity.md)|Bare til intern bruk.|
|[Oppgave](reference/entities/task.md)|Generisk aktivitet som representerer arbeid som må utføres.|

Når noen oppretter noen av disse aktivitetsenhetspostene, opprettes en tilsvarende `ActivityPointer`-enhetspost med samme den unike `ActivityId`-attributtverdien. Du kan ikke opprette, oppdatere eller slette forekomster av `ActivityPointer`-enheten, men du kan hente dem. Dette er det som gjør at alle aktivitetstyper kan presenteres sammen i en liste.

Du kan opprette egendefinerte aktivitetsenheter som fungerer på samme måte.
<!-- TODO: Add link to topic about creating an activity entity -->

### <a name="activityparty-entity"></a>ActivityParty-enheten

Denne enheten brukes for å legge til struktur i `PartyListType`-attributter for aktivitetsenheter som inneholder referanser til andre enheter. Du bruker denne enheten når du angir innstillinger for aktivitetsenhetsattributter som `Email.to` eller `PhoneCall.from`. Angi [ParticipationTypeMask](reference/entities/activityparty.md#BKMK_ParticipationTypeMask)-attributtet i [ActivityParty-enheten](reference/entities/activityparty.md) for å definere rollen til referansen. Roller inkluderer `Sender`, `ToRecipient`, `Organizer` og mer.

Du kan spørre `ActivityParty`-enheten, men du kan ikke opprette, hente, oppdatere eller slette en aktivitetspart utenfor aktiviteten den er knyttet til.
Mer informasjon: 
- [Utviklerveiledning for Dynamics 365 Customer Engagement – ActivityParty-enheten](/dynamics365/customer-engagement/developer/activityparty-entity)


### <a name="child-entities"></a>Underordnede enheter

Enheter der `IsChildEntity`-egenskapen er sann har aldri noen angitte rettigheter, og eies aldri av bruker eller team. Operasjoner som kan utføres på en underordnet enhet, er bundet til en enhet som de er knyttet til via en mange-til-én-relasjon. Brukere kan bare utføre operasjoner på underordnede enheter hvis de kan utføre de samme operasjonene på den relaterte enheten. Underordnet enheter slettes automatisk når enhetsoppføringen de er avhengige av, slettes.

For eksempel så er `PostComment`, `PostLike` og `PostRole` alle underordnet `Post`-enheten.

## <a name="entity-keys"></a>Enhetsnøkler

Hver alternative nøkkeldefinisjon beskriver én eller flere attributter i kombinasjon, som unikt identifiserer en enhetsforekomst. Alternative nøkler brukes som regel bare for integrering med eksterne systemer. Du kan definere alternative nøkler for en unik identifikasjon av en post. Dette er nyttig hvis du integrerer data med et system som ikke støttes unike identifikatornøkler for GUID. Du kan definere en enkelt feltverdi eller kombinasjon av feltverdier for en unik identifikasjon av en enhet. Hvis du legger til en alternativ nøkkel, fremtvinges det en unikhetsbegrensning på disse attributtene. Du vil ikke være i stand til å opprette eller oppdatere en annen enhetspost med de samme verdiene.

Mer informasjon: 
 - [Tilpassingsveiledning for Dynamics 365 Customer Engagement: Definer alternative nøkler som skal referere Dynamics 365-poster](/dynamics365/customer-engagement/customize/define-alternate-keys-reference-records)
 - [Utviklerveiledning for Dynamics 365 Customer Engagement: Definer alternative nøkler for en enhet og Utviklerveiledning: Synkroniser Dynamics 365-data med eksterne systemer](/dynamics365/customer-engagement/developer/synchronize-dynamics-365-data-with-external-systems)

## <a name="entity-states"></a>Enhetstilstander

De fleste enhetene har to egenskaper for å spore tilstanden til en post. Disse er `StateCode`, som heter **Status** i modelldrevne apper, og `StatusCode`, som heter **Statusårsak** i modelldrevne apper. 

Begge attributtene inneholder et sett med alternativer som viser gyldige verdier. Attributtverdiene `StateCode` og `StatusCode` er koblet, slik at bare enkelte `StatusCode`-alternativer er gyldige for en gitt `StateCode`.

Dette kan variere avhengig av enheten, men det vanlige mønsteret for mange enheter, og standard for mange egendefinerte enheter, er:

|StateCode-alternativer  |StatusCode-alternativer  |
|---------|---------|
|0 : Aktiv|1 : Aktiv|
|1: Inaktiv|2: Inaktiv|

Noen enheter har andre sett med alternativer. 

**Eksempel**: `PhoneCall`-enheten `StateCode` og `StatusCode`-alternativene.


|`StateCode`|`StatusCode`|
|---------|---------|
|0: Åpne|1: Åpne|
|1 : Fullført|2: Utført <br />4: Mottatt|
|2: Avbrutt|3: Avbrutt|

Settet med gyldige delstatskoder for en enhet kan ikke tilpasses, men statuskodene kan tilpasses. Du kan legge til flere `StatusCode`-alternativer for en tilsvarende `StateCode`.

Du kan definere flere vilkår for gyldig overgang mellom statuser, når det kommer til egendefinerte enheter. Mer informasjon: 
- [Utviklerveiledning for Dynamics 365 Customer Engagement: Egendefiner metadata for enhetsattributt](/dynamics365/customer-engagement/developer/customize-entity-attribute-metadata)
- [Utviklerveiledning for Dynamics 365 Customer Engagement: Definer egendefinerte tilstandsmodelloverføringer](/dynamics365/customer-engagement/developer/define-custom-state-model-transitions).

### <a name="see-also"></a>Se også

[Enheter for Common Data Service for apper](entities.md)
