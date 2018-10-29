---
title: Attributtmetadata | Microsoft Docs
description: Lær om bruken av attributtmetadata i Common Data Service for apper.
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
ms.date: 03/12/2018
ms.author: jdaly
search.audienceType:
- developer
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: f6fcf3ba1e8e9773df65ac566a9d5c798f4d13a9
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/24/2018
ms.locfileid: "42859165"
---
# <a name="attribute-metadata"></a>Attributtmetadata

Enheter inkluderer en samling av attributter som representerer dataene du kan inkludere i hver post. Utviklere må forstå de ulike typene attributter og hvordan de arbeider med dem. 

Hvis du vil ha mer informasjon, kan du se [Dynamics 365 Customer Engagement – Veiledning for utviklere: Innføring i enhetsattributter](/dynamics365/customer-engagement/developer/introduction-entity-attributes)

## <a name="attribute-names"></a>Attributtnavn

Hver attributt, i likhet med enheter, får definert et unikt navn under opprettelsen. Dette navnet presenteres på flere måter:


|Navn |Beskrivelse  |
|---------|---------|
|`SchemaName`|Som regel en Pascal-versjon av det logiske navnet. det vil si `AccountNumber`|
|`LogicalName`|Bare små bokstaver. det vil si `accountnumber`|

Når du oppretter et egendefinert attributt, vil navnet du velger starte med tilpassingsprefiksverdien til løsningsutgiveren som er tilknyttet med løsningen, der attributtet ble opprettet i.

Du kan ikke endre navnene på et attributt etter at det er opprettet.

Hver attributt har også to egenskaper som kan vise lokaliserte verdier. Disse er verdier som brukes for å henvise til attributtene i en app.

|Navn |Beskrivelse  |
|---------|---------|
|`DisplayName`|Vanligvis det samme som skjemanavnet, men kan inneholde mellomrom. det vil si **kontonummer**|
|`Description`|En kort setning som beskriver attributtet eller veileder brukeren. det vil si *Skriv inn ID-nummer eller kode for kontoen for å søke etter og identifisere kontoen i systemvisninger.*<br />I modelldrevne apper vises denne informasjonen når brukerne holder markøren over feltet for attributtet i et skjema.|


Disse er lokaliserbare verdier som brukes for å henvise til attributtene i en app. Disse verdiene kan endres når som helst. Hvis du vil legge til eller endre lokaliserte verdier, kan du se  [Tilpassingsveiledning for Dynamics 365 Customer Engagement: Oversett egendefinert enhets- og felttekst til andre språk](/dynamics365/customer-engagement/customize/export-customized-entity-field-text-translation).

## <a name="attribute-types"></a>Attributtyper

Egenskapen `AttributeTypeName` beskriver attributtypen. Denne egenskapen inneholder en verdi av typen `AttributeTypeDisplayName` som viser en etikett for hver av de ulike attributtypene som finnes. 

> [!NOTE]
> Ikke forveksle dette med egenskapen `AttributeType`. Verdiene i denne eldre egenskapen er i hovedsak lik `AttributeTypeName`, bortsett fra at den viser `ImageType`-attributt som `Virtual`. Du må referere til egenskapen `AttributeTypeName` i stedet for egenskapen `AttributeType`.

I den følgende tabellen:

- Disse typene er gruppert etter kategori for sammenligning.
- For hver `AttributeTypeDisplayName`-verdi er den avledede klassen til den tilsvarende .NET-samlingen [AttributeMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.attributemetadata) inkludert der det er tilgjengelig. Det er ikke en 1:1-relasjon mellom disse typene og `AttributeTypeDisplayName`-etiketten.
- Disse attributtypene som kan opprettes som egendefinerte attributter, inkluderer den tilsvarende etiketten som vises i brukergrensesnittet.


|Kategori|AttributeTypeDisplayName/<br />typen AttributeMetadata|Kan opprette/<br />Etikett|Beskrivelse  |
|---------|---------|---------|---------|
|Kategorisering|`BooleanType`<br />[BooleanAttributeMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.booleanattributemetadata)|Ja<br />**To alternativer**|Inneholder den utvalgte verdien fra to alternativer som vanligvis indikerer en sann eller usann verdi.<br />Hvis du vil ha mer informasjon, kan du se [Alternativsett](#option-sets)|
|Kategorisering|`EntityNameType`<br />[EntityNameAttributeMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.entitynameattributemetadata)|Nei|Inneholder en alternativverdi som samsvarer med enheten i systemet. Bare til intern bruk.|
|Kategorisering|`MultiSelectPicklistType`<br />[MultiSelectPicklistAttributeMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.multiselectpicklistattributemetadata)|Ja<br />**Flervalg av alternativsett**|Inneholder alternativverdier for flervalgsspørsmål hvor flere alternativer kan velges.<br />Mer informasjon: <br />[Alternativsett](#option-sets)<br />[Dynamics 365 Customer Engagement – Veiledning for utviklere: Nedtrekksmenyattributter for flervalg](/dynamics365/customer-engagement/developer/multi-select-picklist)|
|Kategorisering|`PicklistType`<br />[PicklistAttributeMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.picklistattributemetadata)|Ja<br />**Alternativsett**|Inneholder den valgte alternativverdien hvor et alternativ kan velges.<br />Hvis du vil ha mer informasjon, kan du se [Alternativsett](#option-sets)|
|Kategorisering|`StateType`<br />[StateAttributeMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.stateattributemetadata)|Nei|Inneholder alternativverdien som beskriver statusen til en enhetspost.<br />Hvis du vil ha mer informasjon, kan du se [Alternativsett](#option-sets)|
|Kategorisering|`StatusType`<br />[StatusAttributeMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.statusattributemetadata)|Nei|Inneholder alternativverdien som beskriver årsaken til statusen for en enhetspost.<br />Hvis du vil ha mer informasjon, kan du se [Alternativsett](#option-sets)|
|Samling|`CalendarRulesType`|Nei|Inneholder en samling av `CalendarRules`-enhetspostene.<br />Det er ingen attributter som bruker denne typen. Når du genererer en proxy, vil kodegeneringsverktøyet opprette to simulerte attributter som ikke finnes i metadataene. Disse attributtene representerer en visning av kalenderreglerpostene som er tilknyttet enhetsposten i en én-til-mange-relasjon.|
|Samling|`PartyListType`|Nei|Inneholder en samling av `ActivityParty`-enhetspostene.<br />Hvis du vil ha mer informasjon, kan du se [ActivityParty-enheten](#activityparty-entity)|
|Dato og klokkeslett|`DateTimeType`<br />[DateTimeAttributeMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.datetimeattributemetadata)|Ja<br />**Dato og klokkeslett**|Inneholder en verdi for dato og klokkeslett.<br />Alle attributtene for dato og klokkeslett støtter verdier så tidlig som 1.1.1753 12:00.|
|Bilde|`ImageType`<br />[ImageAttributeMetadata]()|Ja<br />**Bilde**|Inneholder data for å støtte henting av bildedata for en enhetspost.<br />Hvis du vil ha mer informasjo, kan du se [Enhetsbilder](entity-metadata.md#entity-images)|
|Behandlet egenskap|`ManagedPropertyType`<br />[ManagedPropertyAttributeMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.imageattributemetadata)|Nei|Inneholder data som beskriver om løsningskomponenten som er lagret i enhetsposten, kan tilpasses når den er inkludert i en behandlet løsning.<br />Hvis du vil ha mer informasjon, kan du se [Behandlede egenskaper](introduction-solutions.md#managed-properties)|
|Antall|`BigIntType`<br />[BigIntAttributeMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.bigintattributemetadata)|Nei|Inneholder en `BigInt`-verdi. Bare til intern bruk.|
|Antall|`DecimalType`<br />[DecimalAttributeMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.decimalattributemetadata)|Ja<br />**Desimaltall**|Inneholder en `Decimal`-verdi. Egenskapen `Precision` angir nivået av presisjon.|
|Antall|`DoubleType`<br />[DoubleAttributeMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.doubleattributemetadata)|Ja<br />**Flyttall**|Inneholder en `Double`-verdi. Egenskapen `Precision` angir nivået av presisjon.|
|Antall|`IntegerType`<br />[IntegerAttributeMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.integerattributemetadata)|Ja<br />**Heltall**|Inneholder en `Int`-verdi|
|Antall|`MoneyType`<br />[MoneyAttributeMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.moneyattributemetadata)|Ja<br />**Valuta**|Inneholder en `Decimal`-verdi. Egenskapen `PrecisionSource` fastslår hvor nivået av presisjon skal angis.<br />0 : Egenskapen `Precision`<br />1 : Attributtet `Organization.PricingDecimalPrecision`<br />2 : Attributtet `TransactionCurrency.CurrencyPrecision` i enhetsposten|
|Referanse|`CustomerType`<br />[LookupAttributeMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.lookupattributemetadata)|Ja<br />**Kunde**|Inneholder en referanse til enten en konto eller kontaktenhetspost.|
|Referanse|`LookupType`<br />[LookupAttributeMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.lookupattributemetadata)|Ja<br />**Oppslag**|Inneholder en referanse til en enhetspost. De logiske navnene til de gyldige postene lagres vanligvis i egenskapen `Targets` til attributtet.|
|Referanse|`OwnerType`<br />[LookupAttributeMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.lookupattributemetadata)|Nei|Inneholder en referanse til en enhetspost for enten bruker eller team.|
|Streng|`MemoType`<br />[MemoAttributeMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.memoattributemetadata)|Ja<br />**Flere linjer med tekst**|Inneholder en strengverdi som skal vises i en flerlinjet tekstboks.|
|Streng|`StringType`<br />[StringAttributeMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.stringattributemetadata)|Ja<br />**Enkeltlinje med tekst**|Inneholder en strengverdi som skal vises i en tekstboks med én linje.|
|Unik identifikator|`UniqueidentifierType`<br />[UniqueIdentifierAttributeMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.uniqueidentifierattributemetadata)|Nei|Inneholder en unik identifikatorverdi for GUID.|
|Virtuell|`VirtualType`|Nei|Disse attributtene kan ikke brukes i kode og kan generelt ignoreres.|


## <a name="supported-operations-and-form-usage-for-attributes"></a>Støttede operasjoner og skjemabruk for attributter

Hver attributt inkluderer boolske egenskaper som beskriver operasjonene den kan utføre, og hvordan det kan brukes i et skjema.

|Egenskap|Beskrivelse|
|--|--|
|`IsRequiredForForm`|Angir om attributtet må inkluderes som et felt i et skjema.|
|`IsValidForCreate`|Angir om attributtverdien kan angis i en opprettingsoperasjon.|
|`IsValidForForm`|Angir om attributtet kan inkluderes som et felt i et skjema.|
|`IsValidForRead`|Angir om attributtverdien kan hentes.|
|`IsValidForUpdate`|Angir om attributtverdien kan angis i en oppdateringsoperasjon.|

Hvis du prøver å angi en verdi i en opprettings- eller oppdateringsoperasjon for en attributt som ikke er gyldig for den operasjonen, ignoreres verdien.
Hvis du prøver å hente et attributt som ikke er gyldig for lesing, returneres en nullverdi.


## <a name="attribute-requirement-level"></a>Kravnivå for attributt

Egenskapen `RequiredLevel` er en behandlet boolsk egenskap som angir om det kreves en attributtverdi.

Denne egenskapen kan ha følgende verdisett:

|Navn|Verdi|Brukergrensesnittetikett|Beskrivelse|
|--|--|--|--|
|`None`|0|**Valgfritt**|Ingen krav er angitt.|
|`SystemRequired`|1|**Nødvendig for systemet**|Attributtet må ha en verdi.|
|`ApplicationRequired`|2|**Nødvendig for bedriften**|Bedriften krever at attributtet må ha en verdi.|
|`Recommended`|3|**Anbefalt for selskapet**|Det anbefales at attributtet har en verdi.|

Common Data Service for apper fremtvinger bare alternativet `SystemRequired` for attributter som opprettes av systemet. Egendefinerte attributter kan ikke angis til å bruke alternativet `SystemRequired`. 

Modelldrevne apper fremtvinger alternativet `ApplicationRequired`, og bruker en annen presentasjon for alternativet `Recommended`. Opprettere av egendefinerte klienter kan bruke denne informasjonen til å kreve lignende validerings- eller presentasjonsalternativer.

Fordi dette er en behandlet egenskap, kan du, som utgiver av en behandlet løsning, bestemme om forbrukerne av løsningen kan endre disse innstillingene for attributter i løsningen.

Hvis du vil ha mer informasjon, kan du se [Behandlede egenskaper](introduction-solutions.md#managed-properties)


## <a name="rollup-and-calculated-attributes"></a>Felt for beregnet verdi og beregnede attributter

Beregnede attributter og felt for beregnet verdi frigjør brukeren fra å måtte utføre beregninger manuelt, og gjør at de kan fokusere på arbeidet sitt. Systemansvarlige kan definere at et felt skal inneholde verdien til mange vanlige beregninger, uten å måtte samarbeide med en utvikler. Utviklere kan også dra nytte av plattformegenskapene for å utføre disse beregningene, i stedet for gjennom sin egen kode.

Mer informasjon: 
- [Tilpassingsveiledning for Dynamics 365 Customer Engagement: Definer felter for beregnet verdi som aggregerer verdier](/dynamics365/customer-engagement/customize/define-rollup-fields)
- [Tilpassingsveiledning for Dynamics 365 Customer Engagement: Beregnede attributter felt for beregnet verdi](/dynamics365/customer-engagement/customize/define-calculated-fields)
- [Dynamics 365 Customer Engagement – Veiledning for utviklere: Beregnede attributter felt for beregnet verdi](/dynamics365/customer-engagement/developer/calculated-rollup-attributes)

## <a name="attribute-format"></a>Attributtformat

Formatverdiene for attributter kontrollerer hvordan de vises i modelldrevne apper. Utviklere av egendefinerte apper kan bruke denne informasjonen til å opprette lignende opplevelser.

### <a name="integer-formats"></a>Heltallformater

Bruk egenskapen `Format` med heltallsattributter til å vise alternative brukeropplevelser for denne typen.

|Alternativ|Beskrivelse|
|--|--|
|`None`|Viser en tekstboks for å redigere en tallverdi|
|`Duration`|Viser en rullegardinliste som inneholder tidsintervaller. En bruker kan velge en verdi fra listen eller skrive inn et heltall som representerer antallet minutter.|
|`TimeZone`|Viser en rullegardinliste som inneholder en liste over tidsssoner.|
|`Language`|Viser en rullegardinliste som inneholder en liste over språk som har blitt aktivert for organisasjonen. Hvis ingen andre lang har blitt aktivert, blir grunnspråket det eneste alternativet. Verdien som lagres, er LCID-verdien for språket.|

### <a name="string-formats"></a>Strengformater

Bruk egenskapen `FormatName` med strengattributter til å angi verdier fra [klassen StringFormatName](/dotnet/api/microsoft.xrm.sdk.metadata.stringformatname) for å kontrollere hvordan strengattributtet formateres.

|Navn|Beskrivelse|
|--|--|
|`Email`|Skjemafeltet validerer tekstverdien som en e-postadresse, og oppretter en mailto-kobling i feltet.|
|`PhoneNumber`|Skjemafeltet inneholder en kobling for å starte en telefonsamtale ved bruk av Skype.|
|`PhoneticGuide`|Bare til intern bruk.|
|`Text`|Skjemaet viser en tekstboks.|
|`TextArea`|Skjemaet viser et tekstområdefelt.|
|`TickerSymbol`|Skjemaet viser en kobling som åpnes for å vise et tilbud for børstelegrafsymboler.|
|`URL`|Skjemaet viser en kobling for å åpne nettadressen.|
|`VersionNumber`|Bare til intern bruk.|

### <a name="date-and-time-formats"></a>Dato- og klokkeslettformater

Egenskapen `DateTimeBehavior` kontrollerer virkemåten for dato- og klokkeslettattributter.
Det finnes tre alternativer:

|Alternativ|Kort beskrivelse|
|--|--|
|`UserLocal`|Lagrer dato- og klokkeslettverdien som UTC-verdi i systemet.|
|`DateOnly`|Lagrer den faktiske datoverdien med klokkeslettverdien som 12:00 (00:00:00) i systemet.|
|`TimeZoneIndependent`|Lagrer de faktiske dato- og klokkeslettverdiene i systemet, uavhengig av brukerens tidssone.|

Bruk egenskapen `Format` for å kontrollere hvordan verdien skal vises i en modelldrevet app, uavhengig av `DateTimeBehavior`.

|Alternativ|Beskrivelse|
|--|--|
|DateAndTime|Viser fullstendig dato og klokkeslett.|
|DateOnly|Viser bare datoen.|

Hvis du vil ha mer informasjon, kan du se [Dynamics 365 Customer Engagement – Veiledning for utviklere: Virkemåte og format for dato- og klokkeslettattributtet](/dynamics365/customer-engagement/developer/behavior-format-date-time-attribute)

## <a name="auto-number-attributes"></a>Attributter for automatisk nummer

Du kan legge til et attributt for automatisk nummer for enhver enhet. Du kan for øyeblikket legge til attributtet programmatisk. Det finnes ingen brukergrensesnitt for å legge til denne attributtypen.
Hvis du vil ha mer informasjon, kan du se [Dynamics 365 Customer Engagement – Veiledning for utviklere: Opprett attributter for automatisk nummer](/dynamics365/customer-engagement/developer/create-auto-number-attributes)

## <a name="option-sets"></a>Alternativsett

Attributtene som viser et sett med alternativer, kan referere til et sett med alternativer som er definert av attributtet, eller de kan referere til et separat sett med alternativer som kan deles av mer enn ett attributt. Dette er spesielt nyttig når verdier i én attributt også gjelder for andre attributter. Ved å referere til et felles sett med alternativer, kan alternativene vedlikeholdes på ett sted. Disse alternativsettene som kan deles, er *globale* alternativsett. De som er definert i attributtet, er *lokale* alternativsett.

### <a name="retrieve-options-data"></a>Hent alternativdata
Organisasjonstjenesten har forespørselsklasser du kan bruke til å hente alternativene som ble brukt av et attributt.

#### <a name="use-the-organization-service-to-retrieve-options"></a>Bruk organisasjonstjenesten til å hente alternativer

Hver av attributtene med alternativer som er arvet fra [EnumAttributeMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.enumattributemetadata) og inkluderer egenskapen [OptionSet Property](/dotnet/api/microsoft.xrm.sdk.metadata.enumattributemetadata.optionset). Denne egenskapen inneholder [OptionSetMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.optionsetmetadata) som inneholder alternativene i egenskapen [Alternativer](/dotnet/api/microsoft.xrm.sdk.metadata.optionsetmetadata.options). 

Med organisasjonstjenesten kan du bruke følgende meldinger til å hente informasjon om disse alternativsettene:

|Forespørselsklasse|Beskrivelse|
|--|--|
|[RetrieveAllOptionSetsRequest](/dotnet/api/microsoft.xrm.sdk.messages.retrievealloptionsetsrequest) |Henter data om alle *globale* alternativsett.|
|[RetrieveAttributeRequest](/dotnet/api/microsoft.xrm.sdk.messages.retrieveattributerequest) |Henter data om et attributt, inkludert eventuelle *lokale* alternativsett.|
|[RetrieveMetadataChangesRequest](/dotnet/api/microsoft.xrm.sdk.messages.retrievemetadatachangesrequest) |Henter metadata basert på en spørring som kan inneholde *lokale* alternativsett.<br />Hvis du vil ha mer informasjon, kan du se [Hent og oppdag endringer til metadata](/dynamics365/customer-engagement/developer/retrieve-detect-changes-metadata)|
|[RetrieveOptionSetRequest](/dotnet/api/microsoft.xrm.sdk.messages.retrieveoptionsetrequest) |Henter data om et *globalt* alternativsett.|

Mer informasjon: 
- [Eksempel: Dump attributtmetadata for nedtrekksmenyen til en fil](/dynamics365/customer-engagement/developer/org-service/sample-dump-attribute-picklist-metadata-file)
- [Dynamics 365 Customer Engagement – Veiledning for utviklere: Egendefiner globale alternativsett](/dynamics365/customer-engagement/developer/org-service/customize-global-option-sets)

#### <a name="use-the-web-api-to-retrieve-options"></a>Bruk Web API-en til å hente alternativer

Web API-en inneholder en RESTful-stil for å spørre alternativverdier. Du kan hente lokale eller globale alternativer ved å hente attributtene i en enhet. Det følgende eksemplet returnerer [OptionSetMetadata](/dynamics365/customer-engagement/web-api/optionsetmetadata) for alternativene inkludert i [Konto](reference/entities/account.md).[egenskapen AccountCategoryCode property](reference/entities/account.md#BKMK_AccountCategoryCode).

`GET <organization url>/api/data/v9.0/EntityDefinitions(LogicalName='account')/Attributes(LogicalName='accountcategorycode')/Microsoft.Dynamics.CRM.PicklistAttributeMetadata?$select=LogicalName&$expand=OptionSet`

Med Web API-en kan du også bruke [funksjonen RetrieveMetadataChanges](/dynamics365/customer-engagement/web-api/retrievemetadatachanges).

Hvis du vil ha mer informasjon, kan du se: [Dynamics 365 Customer Engagement – Veiledning for utviklere: Spørringsmetadata ved bruk av Web API > Spørring for attributtene EntityMetadata](/dynamics365/customer-engagement/developer/webapi/query-metadata-web-api#querying-entitymetadata-attributes)



## <a name="attribute-mapping"></a>Attributtilordning

Når du oppretter en ny enhetspost i konteksten til en eksisterende enhetspost, kan du automatisk overføre bestemte verdier fra den eksisterende enhetsposten som standardverdier for den nye enhetsposten. Dette strømlinjeformer dataregistrering for personer ved bruk av modelldrevne apper. Programbrukere ser de tilordnede verdiene, og de kan redigere dem før de lagrer enheten.

For utviklere som oppretter egendefinerte klienter, kan den samme virkemåten oppnås ved bruk av `InitializeFrom` melding (Organization service  [klassen InitializeFromRequest](/dotnet/api/microsoft.crm.sdk.messages.initializefromrequest) eller Web API [funksjonen InitializeFrom](/dynamics365/customer-engagement/web-api/initializefrom)) til å hente enhetsdata med det konfigurerte standardverdisettet.

Mer informasjon 
- [Tilpassingsveiledning for Dynamics 365 Customer Engagement: Tilordne enhetsfelter](/dynamics365/customer-engagement/customize/map-entity-fields#BKMK_mappingEntityFields)
- [Utviklerveiledning for Dynamics 365 Customer Engagement: Egendefiner tilordninger for enhet og attributt](/dynamics365/customer-engagement/developer/customize-entity-attribute-mappings)

### <a name="see-also"></a>Se også

[Enheter for Common Data Service for apper](entities.md)
