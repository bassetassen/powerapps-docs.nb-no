---
title: Konfigurere tilkoblingsroller | MicrosoftDocs
ms.custom: ''
ms.date: 05/27/2018
ms.reviewer: ''
ms.service: powerapps
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - PowerApps
ms.author: matp
manager: brycho
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="configure-connection-roles"></a>Konfigurer tilkoblingsroller

Du kan definere **tilkoblinger** med Common Data Service mellom enhetsoppføringer uten å opprette en enhetsrelasjon. I modelldrevne apper kan brukere opprette en navngitt kobling mellom oppføringer for å opprette en mindre formell relasjon som ikke justerer oppretting av en faktisk enhetsrelasjon. Her er noen eksempler: *venn*, *søsken*, *ektefelle*, *deltaker* og *interessent*. Noen tilkoblinger kan også være resiproke, for eksempel *barn* og *forelder*, *mann* og *kone* eller *lege* og *pasient*.

Når brukere har angitt en tilkobling mellom to oppføringer, kan de også legge til en beskrivelse og ytterligere informasjon, for eksempel start- og sluttdatoer for relasjonen. Mer informasjon: [Opprette koblinger for å definere og vise relasjoner mellom oppføringer](/dynamics365/customer-engagement/basics/create-connections-view-relationships-between-records).

Alle som har skrivetilgang til **Tilkoblingsrolle**-enheten, kan finne ut hvilken tilkobling som er tilgjengelig for personers bruk.

## <a name="view-connection-roles"></a>Vise tilkoblingsroller

Det finnes en rekke standard tilkoblingsroller som allerede er konfigurert i Common Data Service. For å vise dem må du gå til Innstillinger-området. 

### <a name="navigate-to-the-settings-area"></a>Navigere til innstillingsområdet

1. Når du viser en modelldrevet app, redigerer du URL-adressen for å fjerne alt etter `dynamics.com` og oppdaterer siden.
1. Gå til **Innstillinger** > **Virksomhet** > **Forretningsbehandling** og velg deretter **Tilkoblingsroller**.

![Tilkoblingsroller i innstillingene for forretningsbehandling](media/navigate-settings-connection-roles.png)

Du kan se alle tilkoblingsroller som er tilgjengelige for dette miljøet, i denne visningen, og du kan redigere dem her.

> [!NOTE]
> Hvis du vil distribuere tilkoblingsroller med en løsning, må du kontrollere at de er inkludert i løsningen du vil distribuere. Mer informasjon: [Legge til tilkoblingsroller i en løsning](#add-connection-roles-to-a-solution)

## <a name="view-connection-roles-in-the-solution-explorer"></a>Vis tilkoblingsroller i løsningsutforskeren.

Fordi tilkoblingsroller er *løsningsavhengige*, som betyr at de kan tas med i en løsning, kan du også legge til tilkoblingsroller i en løsning som du distribuerer.

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]

De fleste tilkoblingsrollene du kan se i **Innstillinger**-området, er definert i den *interne* **standardløsningen** (må ikke forveksles med **standardløsningen for Common Data Services**). Den interne **standardløsningen** inneholder alle tilpassingene i systemet. Hvis du vil vise **standardløsningen**, velger du **Alle løsninger – interne**-visningen.

## <a name="add-connection-roles-to-a-solution"></a>Legge til tilkoblingsroller i en løsning

Vanligvis anbefales det ikke å redigere komponenter i den interne **standardløsningen**. I **standardløsningen for Common Data Services** eller en annen løsning du har opprettet for å arbeide i, kan du bruke **Legg til eksisterende**-kommandoen for å hente en av standardtilkoblingsrollene til løsningen din.

![Legge til eksisterende tilkoblingsrolle](media/add-existing-connection-role.png)

Når du legger til tilkoblingsrollen i løsningen, kan du redigere den når den er synlig.

## <a name="create-or-edit-connection-roles"></a>Opprett eller rediger tilkoblingsroller.

> [!IMPORTANT]
> Hvis du planlegger å distribuere en løsning som inneholder nye tilkoblingsroller eller endringer av eksisterende tilkoblingsroller, må du legge dem til i løsningen du vil distribuere. Når du redigerer eller legger til nye tilkoblingsroller ved hjelp av **Innstillinger**-området, legges disse tilkoblingsrollene til den interne **standardløsningen** og inkluderer dem ikke i løsningen du vil distribuere, med mindre du først legger dem til i løsningen din. Mer informasjon: [Legge til tilkoblingsroller i en løsning](#add-connection-roles-to-a-solution)

I **Tilkoblingsroller**-listen velger du én av tilkoblingsrollene for å redigere den.
Det er tre trinn for å definere en tilkoblingsrolle som er tydelige i skjemaet.

![Opprette tilkoblingsrolle-skjema](media/create-connection-role-form.png)

### <a name="describe-the-connection-role"></a>Beskriv tilkoblingsrollen

Angi følgende felt:

|Felt|Beskrivelse|
|--|--|
|**Navn**|(Obligatorisk) Tekst som beskriver tilkoblingen.|
|**Kategori for tilkoblingsrolle**|En gruppe som beskriver kategorien for tilkoblingen. Mer informasjon: [Kategori for tilkoblingsrolle-verdier](#connection-role-category-values)|
|**Beskrivelse**|Angi en definisjon for rollen.|

#### <a name="connection-role-category-values"></a>Kategori for tilkoblingsrolle-verdier

Standardverdiene for **Kategori for tilkoblingsrolle** er:
- Forretning
- Serie
- Sosialt
- Sales
- Andre
- Interessent
- Salgsteam
- Service

Du kan legge til nye kategorier eller endre eksisterende ved å redigere det globale alternativsettet for **kategori**. Mer informasjon: [Opprette og redigere globale alternativsett for Common Data Service (valglister)](create-edit-global-option-sets.md)

### <a name="select-record-types"></a>Velg oppføringstyper

Velg hvilke oppføringstyper som skal være tilgjengelige for tilkobling.

> [!NOTE]
> Selv om **Alle** er valgt som standard, må du vurdere hvilke typer som er aktuelle for tilkoblingsrollen du legger til.

### <a name="matching-connection-roles"></a>Tilkoblingsroller som samsvarer

I dette valgfrie trinnet kan du definere roller som skal brukes resiprokt. Det er ikke nødvendig, men tilkoblinger er mer meningsfulle hvis disse er definert.

Brukere kan for eksempel angi at Glen er *venn* av Mary, men betyr dette at Mary er *venn* av Glen? Vi håper det. Men hvis Glen er *far* til Mary, betyr ikke det at Mary er *far* til Glen. Angivelse av riktig resiprositet krever dette ekstra trinnet.

Når brukere angir en tilkoblingsrolle som ikke har en samsvarende tilkoblingsrolle, vises rollen bare når tilkoblingen vises fra oppføringen som tilkoblingen ble brukt på. Når vist fra den tilkoblede oppføringen, er rollen tom hvis ikke det er angitt en samsvarende rolle.

For rolledefinisjoner som *venn*, *ektefelle*, *kollega* eller *søsken* er det best å tilordne samsvarende rollen til seg selv. Hvis en enkelt samsvarende tilkoblingsrolle er konfigurert, brukes den enkelte samsvarende tilkoblingsrollen i begge retninger.

> [!IMPORTANT]
> Du må lagre en ny tilkoblingsrolle uten denne samsvarende tilkoblingsrollen før du kan sette den samsvarende tilkoblingsrollen til seg selv.

Du vil oppdage at noen tilkoblingsroller allerede er konfigurert med samsvarende tilkoblingsroller. *Tidligere ansatt* samsvares med *Tidligere arbeidsgiver* og omvendt. Denne typen en-til-en samsvarende tilkoblingsrolle er mest vanlig.

Du kan konfigurere flere samsvarende tilkoblingsroller for å beskrive komplekse relasjoner. Hvis du oppretter en tilkoblingsrolle som *far*, kan du konfigurere to roller til som *datter* og *sønn* og bruke begge som samsvarende tilkoblingsroller til *far*. Både *datter*- og *sønn*-tilkoblingsrollen må så samsvares med *far*. Selvsagt må du deretter definere en tilsvarende rolle for *mor*, som på samme måte samsvares med *datter* og *sønn*.

> [!TIP]
> Før du oppretter et komplekst sett med tilkoblingsroller, bør du vurdere om det er nok med et enklere rollesett. I stedet for å opprette et komplekst sett med tilkoblingsroller som *far*, *mor*, *sønn* og *datter* kan du for eksempel vurdere om det vil fungere å bare bruke *forelder* og *barn*.

Hvis mer enn én samsvarende tilkoblingsrolle er konfigurert, representerer disse tilkoblingsrollene de eneste gyldige resiproke rollene. Den første blir brukt automatisk som standardverdi. Hvis standardverdien ikke er riktig, må brukerne manuelt redigere tilkoblingen og velge mellom gyldige alternativer definert i konfigurasjonen.

### <a name="see-also"></a>Se også
<!-- This is in the basics guide. It needs to be migrated -->
[Opprette koblinger for å definere og vise relasjoner mellom poster](/dynamics365/customer-engagement/basics/create-connections-view-relationships-between-records)<br />
[Opprette og redigere globale alternativsett for Common Data Service (plukklister)](create-edit-global-option-sets.md)<br />
[Opprette og redigere relasjoner mellom enheter](create-edit-entity-relationships.md)


