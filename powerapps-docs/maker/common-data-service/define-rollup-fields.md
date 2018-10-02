---
title: Definere felt for beregnet verdi i PowerApps | MicrosoftDocs
description: Lær hvordan du definerer felt for beregnet verdi
ms.custom: ''
ms.date: 05/23/2018
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
ms.assetid: ff0504a1-01bd-4f9b-b884-7f84911d86c3
caps.latest.revision: 58
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="define-rollup-fields-that-aggregate-values"></a>Definere felt for beregnet verdi som samler verdier

Felt for beregnet verdi gir brukerne bedre innsikt i dataene ved å overvåke viktige forretningsdata. Et felt for beregnet verdi inneholder en mengdeverdi som beregnes på tvers av oppføringene som er knyttet til en bestemt oppføring. Dette omfatter vanlige enheter og aktivitetsentiteter, for eksempel e-postmeldinger og avtaler.

I mer kompliserte scenarier, kan du samle data over hierarkiet av oppføringer. Som systemansvarlig eller tilpasser kan du definere felt for beregnet verdi ved hjelp av verktøyene for tilpassing i PowerApps, uten at det er nødvendig å skrive kode.  
  
<a name="BKMK_benefitsandcapabilities"></a> 
 
## <a name="rollup-fields-benefits-and-capabilities"></a>Felt for beregnet verdi, fordeler og funksjoner  

Fordelene og funksjonene i felt for beregnet verdi omfatter følgende:  
  
- Det er enkelt å redigere visuelt. Du kan opprette felt for beregnet verdi ved hjelp av feltredigeringsprogrammet, slik som når du oppretter et vanlig felt.  
- Stort utvalg av mengdefunksjoner. Du kan samle data ved hjelp av følgende funksjoner: `SUM`, `COUNT`, `MIN`, `MAX` og `AVG`.  
- Full filterstøtte for samling. Du kan angi ulike filtre for kildeenheten eller den relaterte enheten mens du angir flere betingelser.  
- Sømløs integrasjon med brukergrensesnittet. Du kan ta med felt for beregnet verdi i skjemaer, visninger, diagrammer og rapporter.  
- Felt for beregnet verdi er løsningskomponenter. Du kan enkelt transportere feltene for beregnet verdi som komponenter mellom miljøer og distribuere dem i løsninger.  
- Felt for beregnet verdi og de beregnede feltene utfyller hverandre. Du kan bruke et felt for beregnet verdi som en del av det beregnede feltet, og omvendt.  
- Du kan konfigurere felt for beregnet verdi for å bruke egendefinerte kontroller.  
  
 Eksempler på felt for beregnet verdi er:  
  
- Samlet beregnet omsetning av åpne salgsmuligheter på en konto  
- Samlet beregnet omsetning av åpne salgsmuligheter på alle kontoene i et hierarki  
- Samlet beregnet omsetning av en salgsmulighet, inkludert underordnede salgsmuligheter  
- Samlet beregnet verdi for kvalifiserte kundeemner som genereres av en kampanje  
- Antall åpne saker med høy prioritet på alle kontoene i et hierarki  
- Tidligste opprettelsestidspunkt for alle åpne saker med høy prioritet for en konto  
  
Hvert felt for beregnet verdi oppretter to tilbehørsfelt med suffiksmønsteret *&lt;feltnavn&gt;*`_date` og *&lt;feltnavn&gt;*`_state`. Feltet `_date` inneholder DateTime-data, og feltet `_state` inneholder Integer-data. `_state`-feltet har følgende verdier:  
  
|Verdi|Tilstand|Beskrivelse|  
|-|-|-|  
|0|NotCalculated|Feltverdien er ikke beregnet ennå.|  
|1|Calculated|Feltverdien er beregnet per siste oppdateringstidspunkt i _date-feltet.|  
|2|OverflowError|Beregningen av feltverdien førte til overflytsfeil.|  
|3|OtherError|Beregningen av feltverdien mislyktes på grunn av en intern feil. Neste kjøring av beregningsjobben kan sannsynligvis rette den.|  
|4|RetryLimitExceeded|Beregningen av feltverdien mislyktes fordi maksimalt antall nye forsøk på å beregne verdien ble overskredet på grunn av høyt antall samtidighets- og låsekonflikter.|  
|5|HierarchicalRecursionLimitReached|Beregningen av feltverdien mislyktes fordi grensen for maksimal hierarkidybde for beregningen ble nådd.|  
|6|LoopDetected|Beregningen av feltverdien mislyktes fordi en rekursiv løkke ble oppdaget i hierarkiet for oppføringen.|  
  
<a name="BKMK_calculations"></a>  
 
## <a name="rollup-calculations"></a>Verdiberegninger  

De beregnede verdiene beregnes av planlagte systemjobber som kjøres asynkront i bakgrunnen. Du må være administrator for å kunne vise og behandle jobbene for beregnet verdi. 

### <a name="view-rollup-jobs"></a>Vise jobber for beregnet verdi

Slik viser du jobber for beregnet verdi:

1. Når du viser **standardløsningen Common Data Services**, redigerer du URL-adressen og fjerner alt etter `dynamics.com`. Oppdater deretter siden.
2. I **Innstillinger**-området velger du **System** > **Systemjobber**.<br />![Navigere til systemjobber](media/navigate-system-jobs.png)
1. I visningsvelgeren velger du **Regelmessige systemjobber**.
2. Du kan raskt finne en relevant jobb ved å filtrere etter systemjobbtypen: **Masseberegn felt for beregnet verdi** eller **Beregn felt for beregnet verdi**.
 
### <a name="mass-calculate-rollup-field"></a>Masseberegn felt for beregnet verdi

**Masseberegn felt for beregnet verdi** er en regelmessig jobb som opprettes per felt for beregnet verdi. Den kjøres én gang etter at du har opprettet eller oppdatert et felt for beregnet verdi. Jobben beregner det angitte feltet for beregnet verdi på nytt i alle eksisterende oppføringer som inneholder dette feltet. Jobben kjøres som standard 12 timer etter at du har opprettet eller oppdatert et felt. Når jobben er fullført, blir den automatisk planlagt slik at den kjører på nytt langt inn i fremtiden, om ca. 10 år. Hvis feltet endres, tilbakestilles jobben slik at den kjører på nytt 12 timer etter oppdateringen. Forsinkelsen på 12 timer er nødvendig for å sikre at **Masseberegn felt for beregnet verdi** kjører utenom arbeidstiden i miljøet. Det anbefales at en administrator justerer starttidspunktet for en **Masseberegn felt for beregnet verdi**-jobb etter at feltet for beregnet verdi er opprettet eller endret, slik at den kjører utenom arbeidstiden. Midnatt kan for eksempel være et bra tidspunkt å kjøre jobben på, for å sikre effektiv behandling av felt for beregnet verdi.  

### <a name="calculate-rollup-field"></a>Beregn felt for beregnet verdi 

**Beregn felt for beregnet verdi** er en regelmessig jobb med trinnvise beregninger for alle felt for beregnet verdi i de eksisterende oppføringene for en bestemt enhet. Det er bare én forekomst av jobben **Beregn felt for beregnet verdi** per enhet. De trinnvise beregningene betyr at jobben **Beregn felt for beregnet verdi** behandler oppføringene som ble opprettet, oppdatert eller slettet etter at den siste jobben **Masseberegn felt for beregnet verdi** ble ferdig. Standardinnstillingen for maksimal regelmessighet er én time. Jobben opprettes automatisk når første felt for beregnet verdi for en enhet opprettes, og slettes når siste felt for beregnet verdi slettes.  

## <a name="online-recalculation-option"></a>Alternativ for tilkoblet, ny beregning
Hvis du holder markøren over feltet for beregnet verdi i skjemaet, kan du se tidspunktet for siste beregnet verdi, og du kan oppdatere den beregnede verdien ved å velge oppdateringsikonet ved siden av feltet, som vist nedenfor:  

![Felt for beregnet verdi i forretningsforbindelseskjema](media/rollup-field-on-account-form.png)
  

Du må ta hensyn til følgende når du bruker alternativet for tilkoblet, ny beregning (manuell oppdatering i skjemaet):  
  
- Du må ha skriverettigheter til enheten og skriverettigheter til kildeoppføringen der du ber om oppdateringen. Hvis du for eksempel skal beregne omsetningen fra de åpne salgsmulighetene på en konto, trenger du ikke å ha skriverettigheter til salgsmuligheten, bare til forretningsforbindelsesenheten.  
- Dette alternativet er bare tilgjengelig i tilkoblet modus. Du kan ikke bruke det mens du arbeider frakoblet.  
- Maksimalt antall oppføringer under oppdatering av beregnet verdi er begrenset til 50 000 oppføringer. Når det gjelder hierarkisk beregnet verdi gjelder dette for de relaterte oppføringene i hele hierarkiet. Hvis grensen overskrides, vises følgende feilmelding: *Nettbaserte beregninger kan ikke utføres fordi beregningsgrensen på 50 000 relaterte oppføringer er nådd.* Denne grensen gjelder ikke når beregnet verdi beregnes automatisk av systemjobber.  
- Maksimal hierarkidybde er begrenset til 10 for kildeoppføringen. Hvis grensen overskrides, vises en feilmelding om at *nettbaserte beregninger ikke kan utføres fordi grensen på 10 for hierarkidybde for kildeoppføring er nådd.* Denne grensen gjelder ikke når beregnet verdi beregnes automatisk av systemjobber.  

## <a name="modify-rollup-job-recurrence"></a>Endre regelmessighet for jobben for beregnet verdi

Som systemansvarlig kan du endre regelmessighetsmønstret for jobben for beregnet verdi eller utsette, midlertidig stanse eller fortsette jobben for beregnet verdi. Du kan imidlertid ikke avbryte eller slette en jobb for beregnet verdi. 

Hvis du vil midlertidig stanse, utsette, fortsette eller endre regelmessighetsmønstret, må du vise systemjobbene. Mer informasjon: [Vise jobber for beregnet verdi](#view-rollup-jobs) 

Velg **Handlinger** i navigasjonsfeltet, og velg ønsket handling. 

Følgende er tilgjengelige valg for jobben **Masseberegn felt for beregnet verdi**: **Fortsett**, **Utsett** og **Stans midlertidig**. 

Følgende er tilgjengelige valg for jobben **Beregn felt for beregnet verdi**: **Endre regelmessighet**, **Fortsett**, **Utsett** og **Stans midlertidig**.  
  
<a name="BKMK_businessscenarios"></a>  
 
## <a name="examples"></a>Eksempler 

La oss ta en titt på flere eksempler med felt for beregnet verdi. Vi samler data for en oppføring fra de relaterte oppføringene, med og uten bruk av et hierarki. Vi samler også data for en oppføring fra relaterte aktiviteter og aktiviteter indirekte relatert til en oppføring, via Aktivitetspart-enheten. I hvert eksempel definerer vi feltet for beregnet verdi ved hjelp av feltredigeringsprogrammet. Åpne løsningsutforskeren for å åpne redigeringsprogrammet for felt, og utvid **Komponenter** > **Enheter**. Velg ønsket enhet, og velg **Felt**. Velg **Ny**. Oppgi nødvendig informasjon for feltet i redigeringsprogrammet, inkludert **Felttype** og **Datatype**. Velg **Beregnet verdi** i **Felttype** etter at du har valgt datatypen. Datatypene omfatter desimaltall eller heltall, valuta og dato/klokkeslett. Velg **Rediger**-knappen ved siden av **Felttype**. Dermed går du til redigeringsprogrammet for definisjon av felt for beregnet verdi. Definisjonen av felt for beregnet verdi består av tre deler: **Kildeenhet**, **Relatert enhet** og **Samling**.  
  
-   I **Kildeenhet**-delen kan du angi enheten som feltet for beregnet verdi er definert for, og om du vil samle data på tvers av et hierarki. Du kan legge til filtre med flere betingelser for å angi hvilke oppføringer i hierarkiet du vil bruke for beregnet verdi.  
  
-   I **Relatert enhet**-delen angir du enheten du samler data på tvers av. Denne delen er valgfri når du velger å beregne verdi på tvers av hierarkiet for kildeenheten. Du kan legge til filtre med flere betingelser for å angi hvilke relaterte oppføringer du vil bruke i beregningen. Du kan for eksempel ta med omsetning fra åpne salgsmuligheter der den årlige omsetningen er større enn NOK 10 000.  
  
-   I **Samling**-delen kan du angi metrikkverdien du vil beregne. Du kan velge tilgjengelige mengdefunksjoner, for eksempel SUM, ANTALL, MIN, MAKS eller GJSN.  
  
### <a name="aggregate-data-for-a-record-from-related-records"></a>Samle data for en oppføring fra relaterte oppføringer  

I dette eksemplet brukes ikke et hierarki. Samlet beregnet omsetning beregnes for en konto fra de relaterte åpne salgsmulighetene.  

![Samle beregnet omsetning for en forretningsforbindelse](media/rollup-field-no-hierarchy.png)
  
### <a name="aggregate-data-for-a-record-from-the-child-records-over-the-hierarchy"></a>Samle data for en oppføring fra de underordnede oppføringene på tvers av hierarkiet 
 
I dette eksemplet skal vi beregne samlet beregnet omsetning for en salgsmulighet med underordnede salgsmuligheter på tvers av hierarkiet.  
  
![Mengde beregnet omsetning, salgsmulighetshierarki](media/rollup-field-hierarchy-self.png)
  
### <a name="aggregate-data-for-a-record-from-the-related-records-over-the-hierarchy"></a>Samle data for en oppføring fra de relaterte oppføringene på tvers av hierarkiet

I dette eksemplet skal vi beregne samlet beregnet omsetning for åpne salgsmuligheter på alle kontoene på tvers av hierarkiet.  
  
![Mengde beregnet omsetning over forretningsforbindelseshierarki](media/rollup-field-hierarchy.png)  
  
### <a name="aggregate-data-for-a-record-from-all-related-activities"></a>Samle data for en oppføring fra alle relaterte aktiviteter
  
I dette eksemplet beregner vi den totale tiden som er brukt og fakturert fra alle aktiviteter som er relatert til en forretningsforbindelse. Dette kan omfatte tid brukt i telefonsamtaler, på avtaler, eller på egendefinerte aktiviteter.  
  
I tidligere versjoner kunne du definere et felt for beregnet verdi for én enkelt aktivitet, for eksempel en telefonsamtale, faks eller avtale. For å oppnå resultatet for eksemplet som vises nedenfor, måtte du imidlertid legge sammen dataene ved hjelp av beregnede felt. Nå kan du gjøre det i ett trinn ved å definere ett felt for beregnet verdi for Aktivitet-enheten.  
  
![Beregnet verdi av alle aktiviteter for en konto](media/rollup-enhancements-activities.png)  
  
### <a name="aggregate-data-for-a-record-from-all-related-activities-and-activities-indirectly-related-via-the-activity-party-entity"></a>Samle også data for en oppføring fra alle relaterte aktiviteter og aktiviteter indirekte relatert til en oppføring, via Aktivitetspart-enheten.  

I dette eksemplet telle vi antall e-postmeldinger som sendes til en forretningsforbindelse der forretningsforbindelsen er oppført i e-postens Til- eller Kopi-linjer. Dette gjøres ved å angi **Deltakelsestype** i **FILTRE** for Aktivitetspart-enheten i definisjonen for feltet for beregnet verdi. Hvis du ikke bruker filtrering, brukes alle tilgjengelige deltakelsetyper for en aktivitet i beregningen. 
 
Hvis du vil ha mer informasjon om Aktivitetspart-enheten og deltakelsestypene som er tilgjengelige for en bestemt aktivitet, kan du se [ActivityParty-enhet](/dynamics365/customer-engagement/developer/activityparty-entity).

  
![Beregnet verdi av relaterte aktiviteter og aktivitetspart](media/rollup-enhancements-indirect-activities.png)  
  
### <a name="aggregate-data-for-a-record-from-related-records-using-the-avg-operator"></a>Samle data for en oppføring fra de relaterte oppføringene ved hjelp av AVG-operatoren

I dette eksemplet beregner vi et gjennomsnitt beregnet omsetning fra alle salgsmulighetene som er knyttet til en forretningsforbindelse.  
  
![Gjennomsnittlig beregnet omsetning i Dynamics 365](media/rollup-enhancements-average.PNG)  
  
Eksemplet nedenfor viser hvordan du beregner en gjennomsnittlig beregnet omsetning fra tilknyttede salgsmuligheter over et hierarki av forretningsforbindelser. Gjennomsnittlig beregnet omsetning kan ses på hvert nivå i hierarkiet.  
  
![Gjennomsnittlig beregnet omsetning i Dynamics 365](media/cust-rollup-enhancements-avg-over-hierarchy.png)  
  
<a name="BKMK_considerations"></a> 

## <a name="rollup-field-considerations"></a>Hensyn ved bruk av felt for beregnet verdi 

Du må være oppmerksom på bestemte betingelser og begrensninger når du arbeider med felt for beregnet verdi:  
  
- Du kan definere opptil 100 felt for beregnet verdi for organisasjonen og opptil 10 felt for beregnet verdi per enhet.  
- En arbeidsflyt kan ikke utløses av oppdateringer av felt for beregnet verdi.  
- En ventebetingelse for arbeidsflyt kan ikke bruke et felt for beregnet verdi.  
- En beregnet verdi over feltet for beregnet verdi støttes ikke.  
- En beregnet verdi kan ikke referere til et beregnet felt som bruker et annet beregnet felt, selv om alle feltene i det andre beregnede feltet er på gjeldende enhet.  
- Den beregnede verdien kan bare bruke filtre på kildeenheten eller relaterte enheter, enkle felt eller ikke-komplekse beregnede felt.  
- En verdiberegning kan bare utføres på tvers av relaterte enheter med 1:N-relasjoner. En verdiberegning kan ikke utføres på tvers av N:N-relasjoner.  
- En verdiberegning kan ikke utføres på tvers av 1:N-relasjoner for Aktivitet-enheten eller Aktivitetspart-enheten.  
- Forretningsregler, arbeidsflyter eller beregnede felt bruker alltid den siste beregnede verdien for feltet for beregnet verdi.  
- Et felt for beregnet verdi samles under systembrukerkonteksten. Alle brukere kan se den samme verdien i feltet for beregnet verdi. Du kan styre synligheten til feltet for beregnet verdi med feltnivåsikkerhet ved å begrense hvem som kan få tilgang til feltet for beregnet verdi. Mer informasjon: [Feltnivåsikkerhet for å kontrollere tilgang](/dynamics365/customer-engagement/admin/field-level-security) 

### <a name="precision-rounding"></a>Presisjonsavrunding
 
Hvis presisjonen for det aggregerte feltet er større enn presisjonen for feltet for beregnet verdi, avrundes aggregert feltpresisjonen nedover til presisjonen for feltet for beregnet verdi før aggregasjonen blir utført. For å illustrere dette skal vi se på et konkret eksempel. La oss si at feltet for beregnet verdi på kontoenheten, for beregning av total omsetningen for tilknyttede salgsmuligheter, har en nøyaktighet ned til to desimaler. Feltet for beregnet omsetning på enheten for salgsmulighet er det aggregerte feltet med presisjonen på fire desimaler. I vårt eksempel har kontoen to relaterte salgsmuligheter. Den aggregerte summen av beregnet omsetning blir beregnet som følger:  
  
1. Ber. omsetning for første salgsmuligheten: $1000.0041  
1. Ber. omsetning for andre salgsmulighet: $2000.0044  
1. Aggregert sum for beregnet Omsetning: $1000.00 + $2000.00 = $3000.00

Som du kan se, utføres presisjonsavrunding til to desimaler på de aggregerte feltene før aggregasjonen blir utført.  
  
### <a name="different-behavior-from-associated-grids"></a>Annen funksjonalitet fra tilknyttede rutenett
 
Visse enhetsskjemaer, for eksempel forretningsforbindelse eller kontaktperson, out-of-the-box, inneholder de tilknyttede rutenettene. Et skjema for forretningsforbindelse inneholder for eksempel kontakter, saker, salgsmuligheter og andre rutenett. Noen av oppføringene som vises i skjemaet for forretningsforbindelse, er direkte relatert til forretningsforbindelsesoppføringen; andre er indirekte relatert gjennom relasjoner med andre poster. I sammenligning bruker aggregasjonen for felt for beregnet verdi bare direkte relasjoner som er definert eksplisitt i definisjonen for felt for beregnet verdi. Det tas ikke hensyn til noen andre relasjoner. For å illustrere forskjellen i virkemåte skal vi se på eksemplet nedenfor.  
  
1. Forretningsforbindelse A1 har en primær kontaktperson, P1. Sak C1 er tilknyttet forretningsforbindelsen A1 (C1.Kundefelt = A1) og sak C2 er tilknyttet kontakten P1 (C2.Kundefelt = P1).  
1. Rutenettet for **saker** på **Forretningsforbindelse**-skjemaet for A1-posten viser to saker, C1 og C2.  
1. Felt for beregnet verdi på enheten for forretningsforbindelse, kalt Totalt antall av saker, brukes til å telle sakene som er tilknyttet kontoen.  
1. I definisjonen for felt for beregnet verdi for forretningsforbindelse angir vi saker som har kunderelasjonen med forretningsforbindelsen. Etter aggregering er totalt antall saker lik 1 (sak C1). Sak C2 er ikke inkludert i totalsummen fordi den er direkte relatert til kontakten, ikke til forretningsforbindelsen, og kan ikke være eksplisitt definert i feltet for beregnet verdi for forretningsforbindelse. Derfor samsvarer ikke totalt antall saker som er returnert av operasjonen for beregnet verdi, med antall saker som er vist i rutenettet for **saker**.  
  
### <a name="see-also"></a>Se også  

[Opprette og rediger felt](create-edit-fields.md)<br />
[Definere beregnede felt](define-calculated-fields.md)<br />
[Virkemåte og format for Dato og klokkeslett-feltet](behavior-format-date-time-field.md)<br />
[Definere og spørre etter hierarkisk relaterte data](define-query-hierarchical-data.md)<br />
[Video: Beregnet verdi og beregnede felt](http://www.youtube.com/watch?v=RoahCH1p3T8&list=PLC3591A8FE4ADBE07&index=8)<br />
[Video: Bruke Power BI](http://www.youtube.com/watch?v=PkQe4BFlBS8&list=PLC3591A8FE4ADBE07&index=3)
