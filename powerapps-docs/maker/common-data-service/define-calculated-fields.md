---
title: Definere beregnede felt i PowerApps | MicrosoftDocs
description: Lær hvordan du definerer beregnede felt
ms.custom: ''
ms.date: 05/25/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
author: Mattp123
ms.assetid: 6d58a297-2ddf-4236-be3a-47249b49d5fa
caps.latest.revision: 67
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="define-calculated-fields-to-automate-manual-calculations"></a>Definere beregnede felt for å automatisere manuelle beregninger

Bruk beregnede felt for å automatisere manuelle beregninger som brukes i forretningsprosessene. 

En selger vil for eksempel vite hva vektet omsetning er for en salgsmulighet, som er basert på den beregnede omsetningen fra en salgsmulighet multiplisert med sannsynligheten. Eller de vil legge på en rabatt automatisk hvis en ordre er større enn 500 kroner. Et beregnet felt kan inneholde verdier fra vanlige matematiske eller betingede operasjoner, for eksempel større enn og hvis-ellers. Du kan gjøre alt dette ved hjelp av PowerApps uten å måtte skrive kode.  
  
## <a name="capabilities"></a>Funksjoner
  
- Beregnede felt bruker feltene fra gjeldende enhet eller relaterte overordnede enheter.  
- Uttrykksstøtte er tilgjengelig i den gjeldende enheten og relaterte overordnede enhetsfelt i **Betingelse**-delene og **Handling**-delene. De innebygde funksjonene inkluderer:  
 **ADDHOURS**, **ADDDAYS**, **ADDWEEKS**, **ADDMONTHS**, **ADDYEARS**, **SUBTRACTHOURS**, **SUBTRACTDAYS**, **SUBTRACTWEEKS**, **SUBTRACTMONTHS**, **SUBTRACTYEARS**, **DIFFINDAYS**, **DIFFINHOURS**, **DIFFINMINUTES**, **DIFFINMONTHS**, **DIFFINWEEKS**, **DIFFINYEARS**, **CONCAT**, **TRIMLEFT** og **TRIMRIGHT**.  
- En omfattende støtte gir forgrening og flere betingelser. De logiske operasjonene omfatter operatorene **OG** og **ELLER**.  
- De visuelle redigeringsfunksjonene inkluderer et moderne brukergrensesnitt og IntelliSense i **HANDLING**-delen. 
- En sømløs integrasjon av de beregnede feltene med skjemaer, visninger, diagrammer og rapporter er tilgjengelig i sanntid.  
- Du kan konfigurere beregnede felt for å bruke egendefinerte kontroller.  
  
  
## <a name="scenarios"></a>Scenarier
  
- **Vektet omsetning**: Beregnet omsetning multiplisert med sannsynlighet  
- **Nettoverdi**: Aktiva fratrukket gjeld for en gitt konto  
- **Arbeidskostnad**: Grunnsats opptil 40 timer, pluss overtid  
- **Kontaktnummer**: Telefonnummer for en salgsmulighet basert på forretningsforbindelse eller kontakt  
- **Poengsum for kundeemne**: Enkelt felt som gir informasjon om kvaliteten på et gitt kundeemne  
- **Oppfølging innen**: Oppfølging av en aktivitet angitt med et bestemt antall dager som er basert på prioritet  
  
> [!IMPORTANT]
>  Du må ha skriverettighet til [Sikkerhetsprofil for felt](/powerapps/developer/common-data-service/reference/entities/fieldsecurityprofile)-enheten hvis du vil opprette et beregnet felt. Hvis det beregnede feltet bruker de sikre feltene i en beregning, bør du vurdere å sikre det beregnede feltet i tillegg, for å hindre at brukere får tilgang til data som de ikke har tilstrekkelige rettigheter til. Redigeringsprogrammet for beregnet felt gir deg en advarsel hvis du oppretter et beregnet felt som bruker sikre felt i en beregning, og foreslår at du sikrer det beregnede feltet. Mer informasjon: [Feltnivåsikkerhet for å kontrollere tilgang](/dynamics365/customer-engagement/admin/field-level-security)  

## <a name="create-a-calculated-field"></a>Opprett et beregnet felt

Bruk feltredigeringsprogrammet til å angi et beregnet felt. I dette eksemplet skal vi bruke [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc), men trinnene er de samme som for løsningsutforskeren. Mer informasjon: [Opprette og redigere felt](create-edit-fields.md)
  
1. Åpne [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc).
1. Utvid **Data** > **Enheter**.  
1. Velg ønsket enhet, og velg **Felt**. Velg **Legg til felt**.  
1. Oppgi nødvendig informasjon for feltet, inkludert **Visningsnavn**, **Navn** og **Datatype**. 
1. Hvis datatypen er en av typene som støtter beregnede felt, kan du gjøre feltet til et beregnet felt ved å velge **Legg til** > **Beregning**.

    ![Gjøre felt til et beregnet felt](media/make-field-calculated-maker.png)

    Dette er felttypene som støtter beregninger:
    - Tekst
    - Alternativsett  
    - To alternativer  
    - Heltall  
    - Desimaltall  
    - Valuta  
    - Dato/klokkeslett

1. Valg av **Beregning** krever at du lagrer endringene i enheten. Klikk **Lagre** i dialogboksen **Ventende endringer** for å fortsette.
1. Dette åpner redigeringsprogrammet for beregnet felt, der det nye beregnede feltet er opprettet, men ingen formel er angitt. Definisjonen av beregnet felt består av to deler: **BETINGELSE** og **HANDLING**.  
  ![Skjema for nytt beregnet felt](media/empty-field-calculation.png)
- I **Betingelse**-delen kan du angi enhet, felt, operator, type og verdi. I rullegardinlisten for **Enhet** kan du velge en gjeldende enhet eller en relatert enhet. I rullegardinlisten **Felt** kan du velge mellom alle tilgjengelige felt for enheten. Avhengig av operatoren du velger, må du kanskje angi type og verdi. Du kan angi flere betingelser ved hjelp av operatorene `AND` eller `OR`.  
- I **Handling**-delen kan du angi formelen for det beregnede feltet.  
  
> [!NOTE]
>  Du kan bruke data fra oppføringer for oppslag i handlingen. Du må først velge oppslagsfeltet, og skriv deretter inn et punktum. Etter dette, kan du velge ett av de tilgjengelige feltene i den relaterte entiteten. Når det gjelder *`<LookupFieldName>.<RelatedFieldName>`*, kan du velge: `ParentAccountId.AccountNumber`.  
>   
>  Legg merke til at feltnivåsikkerhet ignoreres på den relaterte entiteten, slik at hvis det er følsomme data i feltet bør du også sikre det beregnede feltet.  


<a name="BusinessScenarios"></a> 
  
## <a name="examples"></a>Eksempler  

La oss se nærmere på eksempler på beregnet felt. 
  
### <a name="weighted-revenue-of-opportunity"></a>Vektet omsetning for salgsmulighet

I dette eksemplet bruker vi feltene for salgsmulighetsenheten til å beregne vektet omsetning basert på sannsynligheten for salgsmuligheten. I feltredigeringsprogrammet for en salgsmulighet oppretter vi et felt kalt for **Vektet omsetning** og setter felttypen til **Beregnet** og datatypen til **Valuta**.

I **Betingelse**-delen i redigeringsprogrammet for definisjon av beregnet felt angir vi at salgsmuligheten skal ha statusen åpen. I **HANDLING** beregner formelen vektet omsetning basert på den anslåtte omsetningen til salgsmuligheten, multiplisert med sannsynligheten for salgsmuligheten.  Følgende skjermbilder gir en trinnvis beskrivelse av hvordan du definerer det beregnede feltet **Vektet omsetning**.  
  
#### <a name="set-the-condition-on-the-opportunities"></a>Angi betingelsen for salgsmulighetene:
  
![Angi vektet omsetning i Dynamics 365](media/calc-field-open-opportunity.png)  
  
#### <a name="provide-the-formula-for-the-weighted-revenue"></a>Angi formelen for vektet omsetning: 
  
![Angi anslått verdi av vektet omsetning i Dynamics 365](media/calc-field-open-opportunities-3.png)  
  
#### <a name="altogether"></a>Samlet:
  
![Vektet omsetning for å beregne omsetning i Dynamics 365](media/calculated-field-open-opportunity.png)  
  
### <a name="follow-up-date-of-opportunity"></a>Oppfølgingsdato for salgsmulighet 
 
I dette eksemplet bruker vi feltene for det opprinnelige kundeemnet for en salgsmulighet til å beregne riktig dato for oppfølging av salgsmuligheten. 

I feltredigeringsprogrammet for en salgsmulighet oppretter vi et felt kalt for **Oppfølgingsdato** og setter typen til **Beregnet** og datatypen til **Dato og klokkeslett**.  

I **Betingelse**-delen i redigeringsprogrammet for definisjon av beregnet felt angir vi to betingelser: kjøpstidsramme og anslått verdi for salgsmuligheten. 

I **HANDLING**-delen finner du to formler:
 - For oppfølging av den umiddelbare salgsmuligheten i løpet av en uke
 - For oppfølging i løpet av en måned hvis salgsmuligheten ikke sannsynligvis skjer med en gang. 

Følgende skjermbilder gir en trinnvis beskrivelse av hvordan du definerer det beregnede feltet **Oppfølgingsdato**.  
  
#### <a name="set-the-two-conditions-on-the-originating-lead"></a>Angi to betingelser for det opprinnelige emnet:
  
![Oppfølgingsdato for en salgsmulighet i Dynamics 365](media/calc-field-follow-update-2.PNG)  
  
![Oppfølgingsdato for en salgsmulighet i Dynamics 365](media/calc-field-follow-update-3.PNG)  
  
#### <a name="provide-the-formula-to-follow-up-in-one-week"></a>Inneholder formelen for oppfølging i løpet av en uke:
  
![Oppfølgingsdato for en salgsmulighet i Dynamics 365](media/calc-field-follow-update-4.PNG)  
  
#### <a name="provide-the-formula-to-follow-up-in-one-month"></a>Inneholder formelen for oppfølging i løpet av en måned:
  
![Angi oppfølgingsdato i Dynamics 365](media/calc-field-follow-update-5.PNG)  
  
#### <a name="altogether"></a>Samlet:
  
 ![Angi oppfølgingsdato Hvis-Så og Ellers i Dynamics 365](media/calc-field-follow-update-6.PNG)  
  
### <a name="days-from-a-record-creation"></a>Dager siden en oppføring ble opprettet 
 
I dette eksemplet bruker vi **DIFFINDAYS**-funksjonen til å beregne forskjellen i dager, fra tidspunktet en oppføring ble opprettet til gjeldende dato. 

Opprette et nytt heltallsfelt kalt **Beregnet forskjell dager**.
  
#### <a name="provide-the-formula-for-computing-the-difference-in-days"></a>Angi formelen for utregning av forskjellen i dager
  
![Beregnet felt, DIFFINDAYS-funksjonen](media/custom-calc-field-diff-days.png)  
  
#### <a name="altogether"></a>Samlet:
  
![Forskjellen i dager siden posten ble opprettet](media/calc-field-diff-days-complete.png)  
  
<a name="Syntax"></a> 
  
## <a name="functions-syntax"></a>Funksjonssyntaks  

Tabellen nedenfor inneholder informasjon om syntaksen for funksjonene i **HANDLING**-delen av det beregnede feltet.  
  
> [!TIP]
>  Funksjonsnavnene er angitt med store bokstaver.  
  
|Funksjonssyntaks|Beskrivelse|Returtype|  
|---------------------|-----------------|-----------------|  
|**ADDDAYS** (hele tall, dato og klokkeslett)|Returnerer ny dato og nytt klokkeslett som er lik den angitte datoen og klokkeslettet, i tillegg til det angitte antallet dager.|Dato og klokkeslett|  
|**ADDHOURS** (hele tall, dato og klokkeslett)|Returnerer ny dato og nytt klokkeslett som er lik den angitte datoen og klokkeslettet, i tillegg til det angitte antallet timer.|Dato og klokkeslett|  
|**ADDMONTHS** (hele tall, dato og klokkeslett)|Returnerer ny dato og nytt klokkeslett som er lik den angitte datoen og klokkeslettet, i tillegg til det angitte antallet måneder.|Dato og klokkeslett|  
|**ADDWEEKS** (hele tall, dato og klokkeslett)|Returnerer ny dato og nytt klokkeslett som er lik den angitte datoen og klokkeslettet, i tillegg til det angitte antallet uker.|Dato og klokkeslett|  
|**ADDYEARS** (hele tall, dato og klokkeslett)|Returnerer ny dato og nytt klokkeslett som er lik den angitte datoen og klokkeslettet, i tillegg til det angitte antallet år.|Dato og klokkeslett|  
|**SUBTRACTDAYS** (hele tall, dato og klokkeslett)|Returnerer ny dato og nytt klokkeslett som er lik den angitte datoen og klokkeslettet, minus det angitte antallet dager.|Dato og klokkeslett|  
|**SUBTRACTHOURS** (hele tall, dato og klokkeslett)|Returnerer ny dato og nytt klokkeslett som er lik den angitte datoen og klokkeslettet, minus det angitte antallet timer.|Dato og klokkeslett|  
|**SUBTRACTMONTHS** (hele tall, dato og klokkeslett)|Returnerer ny dato og nytt klokkeslett som er lik den angitte datoen og klokkeslettet, minus det angitte antallet måneder.|Dato og klokkeslett|  
|**SUBTRACTWEEKS** (hele tall, dato og klokkeslett)|Returnerer ny dato og nytt klokkeslett som er lik den angitte datoen og klokkeslettet, minus det angitte antallet uker.|Dato og klokkeslett|  
|**SUBTRACTYEARS** (hele tall, dato og klokkeslett)|Returnerer ny dato og nytt klokkeslett som er lik den angitte datoen og klokkeslettet, minus det angitte antallet år.|Dato og klokkeslett|  
|**DIFFINDAYS** (dato og klokkeslett, dato og klokkeslett)|Returnerer differansen i dager mellom to **Dato og klokkeslett**-felt. Hvis både datoer og klokkeslett faller på samme dag, er forskjellen null.|Heltall|  
|**DIFFINHOURS** (dato og klokkeslett, dato og klokkeslett)|Returnerer differansen i timer mellom to **Dato og klokkeslett**-felt.|Heltall|  
|**DIFFINMINUTES** (dato og klokkeslett, dato og klokkeslett)|Returnerer differansen i minnutter mellom to **Dato og klokkeslett**-felt.|Heltall|  
|**DIFFINMONTHS** (dato og klokkeslett, dato og klokkeslett)|Returnerer differansen i måneder mellom to **Dato og klokkeslett**-felt. Hvis både datoer og klokkeslett faller på samme måned, er forskjellen null.|Heltall|  
|**DIFFINWEEKS** (dato og klokkeslett, dato og klokkeslett)|Returnerer differansen i uker mellom to **Dato og klokkeslett**-felt. Hvis både datoer og klokkeslett faller på samme uke, er forskjellen null.|Heltall|  
|**DIFFINYEARS** (dato og klokkeslett, dato og klokkeslett)|Returnerer differansen i år mellom to **Dato og klokkeslett**-felt. Hvis både datoer og klokkeslett faller på samme år, er forskjellen null.|Heltall|  
|**CONCAT** (enkelt linje med tekst, enkelt linje med tekst, ... enkelt linje med tekst)|Returnerer en streng som er resultatet av å slå sammen to eller flere strenger.|Streng|  
|**TRIMLEFT** (enkel linje med tekst, heltall)|Returnerer en streng som inneholder en kopi av en angitt streng uten de første N-tegnene.|Streng|  
|**TRIMRIGHT** (enkel linje med tekst, heltall)|Returnerer en streng som inneholder en kopi av en angitt streng uten de siste N-tegnene.|Streng|  
  
> [!NOTE]
>  Alle DIFF-funksjoner krever at det første **Dato og klokkeslett**-feltet og andre **Dato og klokkeslett**-feltet har samme virkemåte: **Brukerlokal**, **Bare dato** eller **Tidssoneuavhengig**. Hvis virkemåten til det andre feltet ikke samsvarer med det første feltet, vises feilmeldingen som angir at det andre feltet ikke kan brukes i den gjeldende funksjonen. Mer informasjon: [Virkemåte og format for dato og klokkeslett-feltet](behavior-format-date-time-field.md).  
  
> [!NOTE]
>  Du kan ikke angi en dato, for eksempel 01.01.2015, som datoverdien i et beregnet felt. Verdier for dato/klokkeslett kan bare angis eller sammenlignes med andre dato/klokkeslett-felt.  
  
I **CONCAT**-funksjonen kan du bruke litterale strenger som enkeltlinjer med tekst, felt for forretningsenheter som inneholder en enkelt linje med tekst, eller en kombinasjon av begge. For eksempel: **CONCAT** (fornavn, etternavn, "er en leder."). Hvis en litteral streng inneholder anførselstegn, setter du skråstrek (\\) (escape-tegnet) foran hvert anførselstegn, som dette: `This string contains the \"quotation marks.\"` Dette sikrer at anførselstegn inne i strengen ikke er behandlet som spesialtegn som deler opp strengene.  
  
Eksemplene nedenfor viser hvordan du bruker **TRIMLEFT**- og **TRIMRIGHT**-funksjonene. De inneholder de opprinnelige strengene og de resulterende strengene som ble returnert av **TRIMLEFT**- og **TRIMRIGHT**-funksjonene:  
  
**TRIMLEFT** ("RXX10-3456789", 3), returnerer strengen `10-3456789`    
**TRIMRIGHT** ("20-3456789RXX", 3), returnerer strengen `20-3456789` 
  
<a name="Considerations"></a> 
  
## <a name="considerations"></a>Vurderinger 
 
Du må være oppmerksom på bestemte betingelser og begrensninger når du arbeider med beregnede felt:  
  
- Lagrede spørringer, diagrammer og visualiseringer kan ha maksimalt ti unike beregnede felt.  
- Verdier for beregnede felt vises ikke i frakoblet modus for Outlook-klienten i flisvisningene eller på hovedskjemaer for enhet.  
- Maksimalt antall kjedede, beregnede felt er fem.  
- Et beregnet felt kan ikke referere til seg selv eller ha sykliske kjeder.  
- Hvis du endrer en av betingelsesoperatorene i en setning med flere betingelser, oppdateres alle betingelsesoperatorene i denne betingelsen. Hvis du for eksempel i setningen `IF (x > 50) OR (y ==10) OR (z < 5)` endrer operatoren `OR` til operatoren `AND`, vil alle `OR`-operatorene i setningen bli til `AND`-operatorer.  
- Du får tilgang til overordnede felt via oppslagsfeltet til den overordnede enheten, for eksempel *`<LookupFieldName>.<FieldName>`*. Det er ikke mulig med oppslagsfelt med flere enheter, for eksempel kunde som kan være forretningsforbindelse og kontakt. Noen enheter har imidlertid enkelte oppslagsfelt for en bestemt enhet, for eksempel `ParentAccountid.`*`<FieldName>`* eller `ParentContactid.`*`<FieldName>`*.  
- Sortering deaktiveres for:  
  - Et beregnet felt som inneholder et felt fra en overordnet oppføring.  
  - Et beregnet felt som inneholder et logisk felt (for eksempel adressefeltet)
  - Et beregnet felt som inneholder et annet beregnet felt.  
- Beregnede felt kan bare omfatte to enheter.  
  - Et beregnet felt kan inneholde et felt fra en annen enhet (omfatter to enheter – gjeldende enhet og overordnet oppføring).  
  - Et beregnet felt kan ikke inneholde et beregnet felt fra en annen enhet som også inneholder et annet felt fra en annen enhet (omfatter tre enheter):   
    (Gjeldende enhet) Beregnet felt &larr; (Overordnet oppføring) Beregnet felt 1 &larr; (Overordnet oppføring) Beregnet felt 2.  
- Du kan ikke utløse arbeidsflyter eller plugin-moduler på beregnede felt.  
- Du kan ikke endre et eksisterende enkelt felt til et beregnet felt. Hvis det gjeldende programmet bruker JavaScript eller plugin-moduler for å beregne et felt, vil du ikke kunne bruke funksjonen for beregnede felt uten å måtte opprette et nytt felt.  
- Duplikatregistreringsregler utløses ikke for beregnede felt.  
- En beregnet verdi kan ikke referere til et beregnet felt som bruker et annet beregnet felt, selv om alle feltene i det andre beregnede feltet er på gjeldende enhet.  
  
### <a name="see-also"></a>Se også
 
[Opprette og rediger felt](create-edit-fields.md)<br />
[Definere felt for beregnet verdi som samler verdier](define-rollup-fields.md)<br />
[Video: Beregnet verdi og beregnede felt](http://go.microsoft.com/fwlink/p/?LinkId=517727)
