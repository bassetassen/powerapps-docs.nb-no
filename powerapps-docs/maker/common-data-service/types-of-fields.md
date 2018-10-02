---
title: Feltdatatyper i Common Data Service for Apps | MicrosoftDocs
description: Forstå de ulike feltdatatypene som er tilgjengelige for appen din
keywords: ''
ms.date: 06/27/2018
ms.service: crm-online
ms.custom: null
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
author: Mattp123
ms.assetid: 734b4ffa-5543-4f88-8517-299589f433f7
ms.author: matp
manager: kvivek
ms.reviewer: null
ms.suite: null
ms.tgt_pltfrm: null
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="types-of-fields"></a>Felttyper

Navnene som brukes for typer, avhenger av designeren som brukes. [PowerApps-portalen](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) bruker en konvensjon som inneholder måten dataene formateres på. Løsningsutforskertypen bruker et navn som er rettet inn etter databasedatatypen med en formatmodifikator. Tabellen nedenfor inneholder den tilsvarende `AttributeTypeDisplayName`-API-typen.

|Type portaldata |Type løsningsutforsker| API-type|
|--|--|--|
|**Stort heltall**|**Tidsangivelse**|`BigIntType`|
|**Valuta**|**Valuta**|`MoneyType`|
|**Kunde**|**Kunde**|`CustomerType`|
|**Dato og klokkeslett**|**Dato og klokkeslett**<br />*Dato og klokkesett*-format|`DateTimeType`|
|**Bare dato**|**Dato og klokkeslett**<br />*Bare dato*-format|`DateTimeType`|
|**Desimaltall**|**Desimaltall**|`DecimalType`|
|**Varighet**|**Heltall**<br />*Varighet*-format|`IntegerType`|
|**E-postadresse**|**En enkelt linje med tekst**<br />*E-post*-format|`StringType`|
|**Flyttall**|**Flyttall**|`DoubleType`|
|**Bilde**|**Bilde**|`ImageType`|
|**Språk**|**Heltall**<br />*Språk*-format|`IntegerType`|
|**Oppslag**|**Oppslag**|`LookupType`|
|**Alternativsett med flere valg**|**Alternativsett med flere valg**|`MultiSelectPicklistType`|
|**Tekst med flere linjer**|**Flere linjer med tekst**|`MemoType`|
|**Alternativsett**|**Alternativsett**|`PicklistType`|
|**Eier**|**Eier**|`OwnerType`|
|**Telefon**|**En enkelt linje med tekst**<br />*Telefon*-format|`StringType`|
|**Statusårsak**|**Statusårsak**|`StatusType`|
|**Status**|**Status**|`StateType`|
|**Tekstområde**|**En enkelt linje med tekst**<br />*Tekstområde*-format|`StringType`|
|**Tekst**|**En enkelt linje med tekst**<br />*Tekst*-format|`StringType`|
|**Ticker-kode**|**En enkelt linje med tekst**<br />Ticker-kode-format|`StringType`|
|**Tidssone**|**Heltall**<br />*Tidssone*-format|`IntegerType`|
|**To alternativer**|**To alternativer**|`BooleanType`|
|**Unik identifikator**|**Unik ID** eller **Primærnøkkel**|`UniqueidentifierType`|
|**URL-adresse**|**En enkelt linje med tekst**<br />*URL*-format|`StringType`|
|**Heltall**|**Heltall**<br />*Ingen*-format|`IntegerType`|

For flere beskrivelser for hver type du kan legge til eller redigere, se emnet for tilsvarende designer:
 - [Opprette og redigere felt for Common Data Service for Apps ved hjelp av PowerApps-portalen: Feltdatatyper](create-edit-field-portal.md#field-data-types)
 - [Opprette og redigere felt for Common Data Service for Apps ved hjelp av løsningsutforskeren i PowerApps: Feltdatatyper](create-edit-field-solution-explorer.md#field-data-types)

Du finner mer informasjon om hvordan feltdatatyper er definert i API-et, ved å se [Attributtmetadata](/powerapps/developer/common-data-service/entity-attribute-metadata)

## <a name="field-types-used-by-the-system"></a>Felttyper som brukes av systemet

Det finnes noen felt som brukes av systemet som du ikke kan legge til ved hjelp av utformingen.

|Type|Beskrivelse|
|--|--|
|**Stort heltall** eller **Tidsangivelse**|Brukes av systemet for å fange opp et versjonsnummer eller administrere oppdateringer til en enhet.|
|**Kunde**|Et oppslagsfelt som du kan bruke til å angi en kunde, som kan være en forretningsforbindelse eller kontakt.<br />**Obs!** Dette attributtet kan legges til ved hjelp av løsningutforskeren.|
|**Eier**|Et systemoppslagsfelt som refererer til brukeren eller teamet som er tilordnet en bruker- eller teameid enhetsoppføring.|
|**Statusårsak**|Et systemfelt som har alternativer som gir mer detaljert informasjon om Status-feltet. Hvert alternativ er knyttet til ett av de tilgjengelige statusalternativene. Du kan legge til og redigere alternativene. <br /><br /> Du kan også ta med egendefinerte tilstandsoverganger for å kontrollere hvilke statusalternativer som er tilgjengelige for bestemte enheter. Mer informasjon: [Definere overganger for statusårsaker for egendefinerte enheter](define-status-reason-transitions.md)|
|**Status**|Et systemfelt som har alternativer som vanligvis tilsvarer statusen Aktiv og Inaktiv. Noen systemattributter har flere alternativer, men alle egendefinerte attributter har bare statusalternativene **Aktiv** og **Inaktiv**.  |
|**Unik identifikator**|Et systemfelt lagrer en GUID-verdi (globalt unik identifikator) for hver oppføring.|

  
## <a name="multiselect-option-set"></a>Alternativsett med flere valg

Du kan tilpasse skjemaer, (hovedskjemaer, hurtigoppretting og hurtigvisning) og e-postmaler ved å legge til flervalgsfelt. Når du legger til et felt for alternativsett med flere valg, kan du angi flere verdier som brukerne kan velge. Når brukere fyller ut skjemaet, kan de velge en av, flere av eller alle verdiene som vises i en rullegardinliste.

Hvis for eksempel en organisasjon opererer i flere områder eller land, kan du inkludere flere plasseringer og land i et felt av typen "driftsområder". En bruker kan deretter velge ett eller flere steder fra listen over tilgjengelige verdier.

Velg flere alternativsett er bare tilgjengelig i skrivebeskyttet rutenett, redigerbart rutenett og skjemaer. Alternativsett med flere valg støttes ikke i: 
- Arbeidsflyter, handlinger, dialogbokser, beregnede verdier, diagrammer, og beregnede felt.
- Rapporter, SLA og rutingsregel.

Flervalgsfelt støttes i følgende skjematyper:

|Skjematype|Tilgjengelighet|
|--|--|
|**Turbo-skjema**|Ja|
|**Oppdateringsskjema**|Skrivebeskyttet (feltet blir tilgjengelig, men kan ikke redigeres)|
|**Gammelt skjema**|No|
|**Skjema for masseredigering**|No|

Du kan bruke globale alternativsett som er definert i organisasjonen for å konfigurere verdiene for alternativsett med flere valg.


<a name="BKMK_UsingTheRightTypeOfNumber"></a>
  
## <a name="using-the-right-type-of-number"></a>Bruke riktig type tall

Når du velger riktig type tallfelt som skal brukes, skal det være ganske enkelt å bruke typen **Heltall** eller **Valuta**. Valget mellom å bruke **Flyttall** eller **Desimaltall** krever mer omtanke.  
  
Desimaltall lagres i databasen nøyaktig som angitt. Flyttall lagrer en svært riktig tilnærmet verdi. Hvorfor velge en svært riktig tilnærmet verdi når du kan bruke den nøyaktige verdien? Svaret er at du får ulik systemytelse.  
  
Bruk desimaler når du skal gi rapporter som krever svært nøyaktige beregninger, eller hvis du vanligvis bruker spørringer som søker etter verdier som er lik eller ikke lik en annen verdi.  
  
Bruk flyttall når du lagrer data som representerer brøker eller verdier som du vil vanligvis spørresammenligne med en annen verdi ved å bruke en operator for større eller mindre enn. I de fleste tilfeller er det ikke merkbar forskjell mellom desimaltall og flyttall. Hvis du trenger mest mulig nøyaktige beregninger, bør flyttall fungere for deg.  
  
<a name="BKMK_UsingCurrencyFields"></a>
 
## <a name="using-currency-fields"></a>Bruke valutafelt

Valutafelt lar en organisasjon konfigurere flere valutaer som kan brukes for oppføringer i organisasjonen. Når organisasjoner har flere valutaer, vil de vanligvis utføre beregninger for å angi verdier ved hjelp av standardvalutaen. Når du legger til et valutafelt i en enhet som ikke har andre valutafelt, legges det til to ekstra felt:  
  
- Et oppslagsfelt kalt **Valuta** som du kan sette til alle aktive valutaer som er konfigurert for organisasjonen. Du kan konfigurere flere aktive valutaer for organisasjonen under **Innstillinger** > **Forretningsbehandling** > **Valutaer**. Der kan du angi valutaen og valutakursen med standardvalutaen som er angitt for organisasjonen. Hvis du har flere aktive valutaer, kan du legge til valutafeltet i skjemaet og la brukere angi hvilken valuta som skal brukes for pengeverdier for denne oppføringen. Dette vil endre valutasymbolet som er vist for valutafelt i skjemaet.  
  
  Enkeltpersoner kan også endre sine personlige alternativer for å velge en standardvaluta for oppføringene som de oppretter.
  
- Et desimaltallfelt kalt **Valutakurs** som inneholder valutakursen for en valgt valutaen som er tilknyttet enheten i forhold til standardvalutaen. Hvis dette feltet er lagt til i skjemaet, kan brukere se verdien, men de kan ikke redigere den. Valutakursen lagres med valutaen.  
  
For hver valutafelt du legger til, legges det til et annet valutafelt med suffikset `_Base` i navnet. Dette feltet lagrer beregning av verdien i valutafeltet du la til, og standardvalutaen. Hvis dette feltet er lagt til i skjemaet, kan det ikke redigeres.  
  
Når du konfigurerer et valutafelt, kan du velge presisjonsverdien. Det er tre alternativer, som vist i tabellen nedenfor.  
  
|Alternativ|Beskrivelse|  
|------------|-----------------|  
|Priser med desimalpresisjon|Dette er presisjon for én enkelt organisasjon som skal brukes for priser som finnes under **Innstillinger** > **Administrasjon** > **Systeminnstillinger** > kategorien **Generelt**.|  
|Valutanøyaktighet|Dette alternativet gjelder presisjonen som er definert for valutaen i oppføringen.|  
|Bestemte presisjonsverdier|Disse innstillingene tillater definering av en spesifikk angitt presisjon ved hjelp av verdiene mellom 0 og 4.|  
  
<a name="BKMK_DifferentTypesOfLookups"></a> 
  
## <a name="different-types-of-lookups"></a>Ulike typer oppslag  

Når du oppretter et nytt oppslagsfelt, oppretter du en ny mange-til-en/enhetsrelasjon (N: 1) mellom enheten du arbeider med og **Måloppføringstype** som er angitt for oppslaget. Det finnes flere konfigurasjonsalternativer for denne relasjonen som er beskrevet i [Opprette og redigere relasjoner mellom enheter](create-edit-entity-relationships.md). Alle egendefinerte oppslag tillater imidlertid bare referanse til én enkelt oppføring for én enkelt måloppføringstype.  
  
Du bør imidlertid være oppmerksom på at ikke alle oppslag fungerer på denne måten. Det finnes flere ulike typer systemoppslag, som vist her.  
  
|Oppslagstype|Beskrivelse|  
|-----------------|-----------------|  
|**Enkel**|Tillater én enkelt referanse til en bestemt enhet. Alle egendefinerte oppslag er av denne typen.|  
|**Kunde**|Tillater én enkelt referanse til en forretningsforbindelses- eller kontaktoppføring.|  
|**Eier**|Tillater én enkelt referanse til en team- eller brukerkoppføring. Alle team- eller brukereide enheter har en av disse.|  
|**PartyList**|Tillater flere referanser til flere enheter. Disse oppslagene finner du for **Til**- og **Kopi**-feltene for E-post-enheten. De brukes også i telefon- og avtaleenhetene.|  
|**Angående**|Tillater én enkelt referanse til flere enheter. Disse oppslagene finnes i feltet som brukes i aktiviteter.|  

<a name="BKMK_ImageFields"></a>

## <a name="image-fields"></a>Bildefelt  

Bruk bildefelt til å vise ett enkelt bilde per oppføring i programmet. Hver enhet kan bare ha ett bildefelt. Du kan legge til et bildefelt i egendefinerte enheter, men ikke i standardenheter. Enkelte standardenheter har bildefelt definert.
  
Selv om en enhet har et bildefelt, kreves det et tilleggstrinn for å vise bildet i en modelldrevet app. I enhetsdefinisjonen er feltverdiene for **Hovedbilde** **[Ingen]** eller **Enhetsbilde**. Velg **Enhetsbilde** for å vise bildet i programmet.  
  
Når bildevisning er aktivert for en enhet, vises det et plassholderbilde i alle oppføringer som ikke har et bilde. Eksempel:

![Plassholderbilde](../common-data-service/media/lead-entity-form.PNG)
  
Brukere kan velge standardbildet for å laste opp et bilde fra datamaskinen. Bilder må være mindre enn 5 120 kB og må være i ett av følgende formater:  
  
- JPG
- JPEG
- GIF
- TIF
- TIFF
- BMP
- PNG
  
Når bildet er lastet opp, blir det konvertert til JPG-format, og alle nedlastede bilder vil også bruke dette formatet. Hvis et animert GIF-bilde lastes opp, lagres bare det første bildet.  
  
Når et bilde lastes opp, vil det endres til maksimumsstørrelsen 144 x 144 piksler. Brukere bør skalere eller beskjære bildene før de laster dem opp, slik at de vises slik de skal i denne størrelsen. Alle bilder beskjæres til å være firkantet. Hvis begge sider av et bilde er mindre enn 144 piksler, blir bildet beskåret til å være en firkant med målene på den korteste siden.  

Mer informasjon for utviklere som arbeider med bildedata:
- [Enhetsmetadata > Enhetsbilder](/powerapps/developer/common-data-service/entity-metadata#entity-images)
- [Utviklerveiledning for Dynamics 365 Customer Engagement: Bildeattributter](/dynamics365/customer-engagement/developer/image-attributes)
