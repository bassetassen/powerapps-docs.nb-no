---
title: Definere alternative nøkler for å referere til oppføringer med Common Data Service | MicrosoftDocs
description: Lær hvordan du definerer alternative nøkler som kan brukes til å referere til oppføringer i Common Data Service
ms.custom: ''
ms.date: 06/06/2018
ms.reviewer: ''
ms.service: powerapps
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
author: Mattp123
ms.assetid: 29e53691-0b18-4fde-a1d0-7490aa227898
caps.latest.revision: 10
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="define-alternate-keys-to-reference-records"></a>Definere alternative nøkler for å referere til oppføringer

Med *alternative nøkler* kan du sikre en effektiv og nøyaktig måte å integrere data med eksterne systemer. Dette er viktig når et eksternt system ikke lagrer de globalt unike identifikatorene (GUID) som unikt identifiserer oppføringer i Common Data Service. 

Et system for integrering av dataene bruker alternative nøkler til å unikt identifisere oppføringer ved hjelp av én eller flere enhetsfeltverdier som representerer en unik kombinasjon . Hver alternative nøkkel har et unikt navn. 

For eksempel for å identifisere en oppføring for forretningsforbindelse med en alternativ nøkkel kan du bruke nummeret for forretningsforbindelsen eller forretningsforbindelsesfeltet sammen med andre felt som har verdier som ikke skal endres.

> [!NOTE]
> Selv om du kan definere alternative nøkler med PowerApps, kan de bare brukes programmatisk i kode. Hvis du vil lære mer om bruk av alternative nøkler programmatisk, kan du se:   
> - [Dokumentasjon for utviklere: Bruke en alternativ nøkkel til å opprette en oppføring](/dynamics365/customer-engagement/developer/use-alternate-key-create-record) 
> - [Dokumentasjon for utviklere: Hente en oppføring med web-API ved hjelp av en alternativ nøkkel](/dynamics365/customer-engagement/developer/webapi/retrieve-entity-using-web-api#retrieve-using-an-alternate-key)

Noen av fordelene med funksjonen for alternative nøkler er:  
  
- Raskere oppslag i oppføringene.  
- Mer robust massedataoperasjoner.  
- Forenklet programmering med data som er importert fra eksterne systemer uten oppførings-ID-er.  
  

## <a name="creating-an-alternate-key"></a>Opprette en alternativ nøkkel

Det finnes to utforminger som du kan bruke til å opprette alternative nøkler:

|Designer| Beskrivelse|
|--|--|
|[PowerApps-portalen](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)|Inneholder en enkel strømlinjeformet opplevelse, men enkelte alternativer er ikke tilgjengelige.<br />Mer informasjon: [Definere alternative nøkler ved hjelp av PowerApps-portalen](define-alternate-keys-portal.md)|
|Løsningsutforsker|Ikke så enkel, men den er mer fleksibel når kravene er mindre vanlige.<br />Mer informasjon: [Definere alternative nøkler ved hjelp av løsningsutforskeren](define-alternate-keys-solution-explorer.md) |

> [!NOTE]
> Du kan også opprette en alternativ nøkkel i miljøet ved hjelp av følgende:
> - Importer en løsning som inneholder definisjonen av den alternative nøkkelen.
> - En utvikler kan også skrive kode for å opprette dem. Mer informasjon: [Dokumentasjon for utviklere: Definere alternative nøkler for en enhet](/dynamics365/customer-engagement/developer/define-alternate-keys-entity)

Informasjonen i dette emnet hjelper deg med å velge hvilken utforming du kan bruke. 

Du bør bruke [PowerApps-portalen](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) til å opprette alternative nøkler, med mindre du må ta hensyn til noen av følgende krav:

- Opprette en alternativ nøkkel i en annen løsning enn standardløsningen Common Data Service
- Du vil enkelt spore den opprettede systemjobben som sporer fremdriften under oppretting av de tilhørende indeksene


## <a name="limits-in-creating-alternate-keys"></a>Begrensninger ved oppretting av alternative nøkler

Det finnes begrensninger ved oppretting av alternative nøkler.

### <a name="fields-that-can-be-used-for-alternate-keys"></a>Felt som kan brukes for alternative nøkler

Bare disse felttypene kan brukes til å opprette alternative nøkler:
 - Desimal
 - Heltall
 - En enkelt linje med tekst (streng)

### <a name="number-of-keys"></a>Antall nøkler

Du kan definere opptil fem forskjellige nøkler for en entitet.
 
### <a name="valid-key-size"></a>Gyldig nøkkelstørrelse

Når en nøkkel opprettes, validerer systemet at nøkkelen kan støttes av plattformen, inkludert at den totale størrelsen på nøkkelen ikke bryter SQL-baserte indeksbegrensninger, som 900 byte per nøkkel og 16 kolonner per nøkkel. Hvis nøkkelstørrelsen ikke oppfyller betingelsene, vises en feilmelding.

### <a name="unicode-characters-in-key-value"></a>Unicode-tegn i nøkkelverdi

Hvis dataene i et felt som brukes i en alternativ nøkkel, inneholder ett av følgende tegn `<`,`>`,`*`,`%`,`&`,`:`,`/`,`\\`, vil patch- eller upsert-handlinger ikke fungere. 

Hvis du bare trenger unikhet, fungerer denne metoden, men hvis du trenger å bruke disse nøklene som en del av dataintegrering, er det best å opprette nøklene i felt som ikke har data med disse tegnene.

## <a name="track-the-status-of-the-creation-of-the-alternate-key"></a>Spore statusen for oppretting av en alternativ nøkkel

Når en alternativ nøkkel er opprettet, starter den en systemjobb for å opprette indekser i databasetabellene for å overholde unike begrensninger på felt som brukes av den alternative nøkkelen. Den alternative nøkkelen trer ikke i kraft før disse indeksene er opprettet. Oppretting av disse indeksene kan ta litt tid avhengig av hvor mye data det er i systemet. 

Statusen til systemjobben bestemmer tilstanden for den alternative nøkkelen. Den alternative nøkkelen kan ha følgende tilstander:
- **Venter**
- **Pågår**
- **Aktiv**
- **Mislykket**

Når systemjobben er fullført, er statusen for den alternative nøkkelen **Aktiv**, og den er tilgjengelig for bruk.

Hvis en systemjobb mislykkes, kan du finne systemjobben for å vise eventuelle feil. Systemjobben har et navn som følger dette mønsteret: `Create index for {0} for entity {1}` der `0` er **visningsnavnet** for den alternative nøkkelen, og `1` er navnet på enheten.


> [!NOTE]
> Hvis du vil overvåke statusen til systemjobben, bør du bruke løsningsutforsker til å opprette indeksen. Den inneholder en kobling til systemjobben. slik at du kan overvåke den. Mer informasjon: [(Valgfritt) Vise systemjobbsporing under oppretting av indekser](define-alternate-keys-solution-explorer.md#optional-view-the-system-job-tracking-creation-of-indexes)
  
  
### <a name="see-also"></a>Se også  

[Definere alternative nøkler ved hjelp av PowerApps-portalen](define-alternate-keys-portal.md)<br />
[Definere alternative nøkler ved hjelp av løsningsutforskeren](define-alternate-keys-solution-explorer.md)<br />
[Dokumentasjon for utviklere: Definere alternative nøkler for en enhet](/dynamics365/customer-engagement/developer/define-alternate-keys-entity)<br />
[Dokumentasjon for utviklere: Bruke en alternativ nøkkel til å opprette en oppføring](/dynamics365/customer-engagement/developer/use-alternate-key-create-record)
