---
title: Definer felt for beregnet verdi i PowerApps | MicrosoftDocs
description: Finn ut hvordan du definerer felt for beregnet verdi
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
ms.openlocfilehash: c76162747ac2bda27c46895290e5943b7f46739f
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/08/2018
ms.locfileid: "39690616"
---
# <a name="define-rollup-fields-that-aggregate-values"></a>Definer felt for beregnet verdi som aggregerer verdier

Med felt for beregnet verdi kan brukere få innsikt i data ved å overvåke viktige forretningsmål. Et felt for beregnet verdi inneholder en aggregert verdi som er beregnet over postene, som er knyttet til en bestemt post. Dette inkluderer vanlige enheter og aktivitetsenheter som e-poster og avtaler.

I mer komplekse scenarioer kan du aggregere data over hierarkiet til postene. Som administrator eller systemtilpasser kan du definere felt for beregnet verdi ved å bruke tilpasningsverktøyene i PowerApps, uten å måtte skrive noen kode.  
  
<a name="BKMK_benefitsandcapabilities"></a> 
 
## <a name="rollup-fields-benefits-and-capabilities"></a>Fordeler og muligheter med felt for beregnet verdi  

Fordelene og mulighetene med felt for beregnet verdi inkluderer:  
  
- Visuell redigering er enkelt. Du kan opprette felt for beregnet verdi ved bruk av redigeringsprogrammet for felt, akkurat på samme måte som når du oppretter et vanlig felt.  
- Bredt utvalg av mengdefunksjoner. Du kan aggregere data ved bruk av følgende funksjoner: `SUM`, `COUNT`, `MIN`, `MAX` og `AVG`.  
- Fullstendig filterstøtte for aggregasjon. Du kan angi ulike filtre for kildeenheten eller tilknyttet enhet mens du angir flere betingelser.  
- Sømløs integrering med brukergrensesnittet. Du kan inkludere feltene for beregnet verdi i skjemaer, visninger, diagrammer og rapporter.  
- Felter for beregnet verdi er løsningskomponenter. Du kan enkelt transportere feltene for beregnet verdi som komponenter mellom miljøer og distribuere dem i løsninger.  
- Felter for beregnet verdi og beregnede felter er komplementær til hverandre. Du kan enkelt bruke et felt for beregnet verdi som en del av et beregnet felt, og omvendt.  
- Du kan konfigurere felter for beregnet verdi for å bruke egendefinerte kontroller.  
  
 Enkelte eksempler på felter for beregnet verdi inkluderer:  
  
- Beregnet totalomsetning fra åpne muligheter hos en kunde  
- Beregnet totalomsetning fra åpne muligheter hos alle kunder i et hierarki  
- Beregnet totalomsetning fra en salgsmulighet inkludert underordnede muligheter  
- Beregnet totalverdi av kvalifiserte kundeemner som ble generert av en kampanje  
- Antall åpne tilfeller med høy prioritet fra alle kontoer i et hierarki  
- Tidligste opprettelsestidspunkt for alle åpne tilfeller med høy prioritet for en konto  
  
Hvert felt for beregnet verdi oppretter to tilbehørsfelter med suffiksmønsteret *&lt;fieldname&gt;*`_date` og *&lt;fieldname&gt;*`_state`. `_date`-feltet inneholder DateTime-data og `_state`-feltet inneholder Heltall-data. `_state`-feltet har følgende verdier:  
  
|Verdi|Tilstand|Beskrivelse|  
|-|-|-|  
|0|NotCalculated|Feltverdien er ennå ikke beregnet.|  
|1|Beregnet|Feltverdien er beregnet per det siste oppdateringstidspunktet i _date-feltet.|  
|2|OverflowError|Feltverdiberegningen resulterte i en overflytsfeil.|  
|3|OtherError|Feltverdiberegningen mislyktes på grunn av en intern feil. Den følgende kjøringen av beregning vil sannsynligvis løse problemet.|  
|4|RetryLimitExceeded|Feltverdiberegningen mislyktes fordi det maksimale antallet nye forsøk på å beregne verdien ble overskredet på grunn av et høyt antall samtidighet og låsekonflikter.|  
|5|HierarchicalRecursionLimitReached|Feltverdiberegningen mislyktes fordi grensen for maksimal hierarkidybde for beregningen ble nådd.|  
|6|LoopDetected|Feltverdiberegningen mislyktes fordi en rekursiv løkke ble oppdaget i hierarkiet for posten.|  
  
<a name="BKMK_calculations"></a>  
 
## <a name="rollup-calculations"></a>Beregnet verdi  

De beregnede verdiene beregnes av planlagte systemjobber som kjører asynkront i bakgrunnen. Du må være en administrator for å vise og behandle jobber for beregnet verdi. 

### <a name="view-rollup-jobs"></a>Vis jobber for beregnet verdi

Slik viser du jobber for beregnet verdi:

1. Mens du viser **Standardløsning for Common Data Services**, redigerer du nettadressen, fjerner alt etter `dynamics.com`, og oppdaterer siden.
2. Velg **System** > **Systemjobber** i **Innstillinger**-området.<br />![Naviger til systemjobber](media/navigate-system-jobs.png)
1. Velg **Gjentakende systemjobber** i visningsvelgeren.
2. Hvis du ønsker å finne en relevant jobb raskt, kan du filtrere Systemjobb-typen: **Masseberegn felt for beregnet verdi** eller **Beregn felt for beregnet verdi**.
 
### <a name="mass-calculate-rollup-field"></a>Masseberegn felt for beregnet verdi

**Masseberegn felt for beregnet verdi** er en gjentakende jobb, som er opprettet per felt for beregnet verdi. Den kjører én gang, etter at du opprettet eller oppdaterte et felt for beregnet verdi. Jobben omberegner den angitte verdien i feltet for beregnet verdi i alle eksisterende poster som inneholder dette feltet. Jobben kjører i 12 timer etter at du opprettet eller oppdaterte et felt (standard). Etter at jobben er fullført, planlegges den automatisk til å kjøre på et senere tidspunkt, omtrent etter ti år. Hvis feltet endres, tilbakestilles jobben til å kjøre på nytt 12 timer etter oppdateringen. Forsinkelsen på 12 timer er nødvendig for å sikre at **Masseberegn felt for beregnet verdi** kjøres på et tidspunkt der miljøet ikke er i drift. Det anbefales at en administrator justerer starttidspunktet for jobben **Masseberegn felt for beregnet verdi** etter at feltet for beregnet verdi er endret, på en sånn måte at den kjøres på et tidspunkt der miljøet ikke er i drift. Midnatt ville for eksempel vært et ideelt tidspunkt for å kjøre jobben. På denne måten kan du sikre en effektiv behandling av feltene for beregnet verdi.  

### <a name="calculate-rollup-field"></a>Beregn felt for beregnet verdi 

**Beregn felt for beregnet verdi** er en gjentakende jobb som gjør trinnvise beregninger av alle felt for beregnet verdi i de eksisterende postene for en bestemt enhet. Det er bare én jobb av typen **Beregn felt for beregnet verdi** per enhet. De trinnvise beregningene betyr at jobbprosessene for **Beregn felt for beregnet verdi** behandler postene som ble opprettet, oppdatert eller slettet etter at siste jobb av typen **Masseberegn felt for beregnet verdi** har fullført kjøringen. Standardinnstillingen for maksimal gjentakelse er én time. Jobben opprettes automatisk når det første feltet for beregnet verdi på en enhet er opprettet, og slettet når det siste feltet for beregnet verdi er slettet.  

## <a name="online-recalculation-option"></a>Alternativet Omberegning på nett
Hvis du holder pekeren over feltet for beregnet verdi i skjemaet, kan du se tidspunktet for siste beregnet verdi, og du kan oppdatere den beregnede verdien ved å velge Oppdater-ikonet ved siden av feltet, som vist nedenfor:  

![Felt for beregnet verdi i kontoskjemaet](media/rollup-field-on-account-form.png)
  

Det finnes noen viktige faktorer du bør huske når du bruker alternativet Omberegning på nett (manuell oppdatering i skjemaet):  
  
- Du må ha skrivetilgang på enheten og skrivetilgangsrettigheter for kildeposten i datakilden der du ønsker en oppdatering. Hvis du for eksempel beregner den anslåtte omsetningen fra de åpne mulighetene i en konto, trenger du ikke skrivetilgang på salgsmulighetsenheten, bare på kontoenheten.  
- Dette alternativet er bare tilgjengelig i tilkoblet modus. Du kan ikke bruke den mens du arbeider frakoblet.  
- Maksimalt antall poster under oppdateringen av beregnet verdi er begrenset til 50 000 poster. Når det gjelder den hierarkiske beregningen, gjelder dette for de relaterte postene i hele hierarkiet. Hvis grensen overskrides, ser du en feilmelding: *beregninger kan ikke utføres på nettet fordi beregningsgrensen på 50 000 relaterte poster er nådd.* Denne grensen gjelder ikke når den beregnede verdien omberegnes automatisk av systemjobber.  
- Maksimal hierarkidybde er begrenset til 10 for posten i datakilden. Hvis grensen overskrides, ser du en feilmelding: *beregninger kan ikke utføres på nettet fordi grensen for hierarkidybde på 10 er nådd.* Denne grensen gjelder ikke når den beregnede verdien omberegnes automatisk av systemjobber.  

## <a name="modify-rollup-job-recurrence"></a>Endre gjentakelse for jobb for beregnet verdi

Som systemadministrator kan du endre mønster for gjentakelsen av jobber for beregnet verdi, utsette, sette på pause eller fortsette den. Du kan imidlertid ikke avbryte eller slette en jobb for beregnet verdi. 

Hvis du vil sette på pause, utsette, gjenoppta eller endre mønsteret for gjentakelsen, må du vise systemjobbene. Hvis du vil ha mer informasjon, kan du se [Vis jobber for beregnet verdi](#view-rollup-jobs) 

Velg **Handlinger** fra navigasjonslinjen, og velg den ønskede handlingen. 

Det finnes tre tilgjengelige valg for jobben **Masseberegn felt for beregnet verdi**: **Gjenoppta**, **Utsett** og **Pause**. 

Det finnes tre tilgjengelige valg for jobben **Beregn felt for beregnet verdi**: **Endre gjentakelse**, **Gjenoppta**, **Utsett** og **Pause**.  
  
<a name="BKMK_businessscenarios"></a>  
 
## <a name="examples"></a>Eksempler 

La oss ta en titt på flere eksempler for feltet for beregnet verdi. Vi samler data for en post fra de relaterte postene med og uten bruk av et hierarki. Vi samler også data for en post fra relaterte aktiviteter og aktiviteter som er indirekte relatert til en post, via ActivityParty-enheten. I hvert eksempel kan vi definerer feltet for beregnet verdi ved hjelp av redigeringsprogrammet for felt. Åpne Løsningsutforsker for å åpne redigeringsprogrammet for felt, og utvid **Komponenter** > **Enheter**. Velg enheten du vil bruke, og velg **Felt**. Velg **Ny**. Oppgi den nødvendige informasjonen for feltet i redigeringsprogrammet, inkludert **Felttype** og **Datatype**. Velg **Beregnet verdi** i **Felttype** når du har valgt datatypen. Datatyper inkluderer desimaler eller hele tall, valuta og dato/klokkeslett. Velg **Rediger**-knappen ved siden av **Felttype**. Dette tar deg til redigeringsprogrammet for definisjonen av felt for beregnet verdi. Definisjonen av felt for beregnet verdi består av tre inndelinger: **Kildeenhet**, **Relatert enhet** og **Aggregasjon**.  
  
-   I **Kildeenhet**-inndelingen angir du enheten som har et definert felt for beregnet verdi, og om du aggregerer over et hierarki. Du kan legge til filtre med flere betingelser for å angi postene i hierarkiet du vil bruke for beregnet verdi.  
  
-   I **Relatert enhet**-inndelingen angir du enheten som du aggregerer. Denne inndelingen er valgfri når du velger å beregne en verdi over hierarkiet på kildeenheten. Du kan legge til filtre med flere betingelser for å angi hvilke relaterte poster som skal brukes i beregningen. Du kan for eksempel inkludere inntektene fra åpne salgsmuligheter med en årlig omsetning som er større enn USD 1000.  
  
-   I **Aggregasjon**-inndelingen kan du angi måleverdien du vil beregne. Du kan velge tilgjengelig aggregasjonsfunksjoner, for eksempel SUM, COUNT, MIN, MAX eller AVG.  
  
### <a name="aggregate-data-for-a-record-from-related-records"></a>Aggreger data for en post fra relaterte poster  

I dette eksemplet brukes ikke et hierarki. Total anslått omsetning beregnes for en konto, fra de relaterte åpne salgsmulighetene.  

![Aggreger anslått omsetning for en konto](media/rollup-field-no-hierarchy.png)
  
### <a name="aggregate-data-for-a-record-from-the-child-records-over-the-hierarchy"></a>Aggreger data for en post fra de underordnede postene, over hierarkiet 
 
I dette eksemplet beregner vi total anslått omsetning for en salgsmulighet inkludert underordnede muligheter, over hierarkiet.  
  
![Aggreger anslått omsetning over salgsmulighetshierarkiet](media/rollup-field-hierarchy-self.png)
  
### <a name="aggregate-data-for-a-record-from-the-related-records-over-the-hierarchy"></a>Aggreger data for en post fra de relaterte postene, over hierarkiet

I dette eksemplet beregner vi total anslått omsetning for åpne muligheter på alle kontoene, over hierarkiet.  
  
![Aggreger anslått omsetning over kontohierarkiet](media/rollup-field-hierarchy.png)  
  
### <a name="aggregate-data-for-a-record-from-all-related-activities"></a>Aggreger data for en post fra alle relaterte aktiviteter
  
I dette eksemplet beregner vi den totale tiden som er brukt og fakturert fra alle aktiviteter, som er knyttet til en konto. Dette kan omfatte tiden som brukes på telefonen, og på avtaler, eller tilpassede aktiviteter.  
  
I tidligere versjoner kan du definere et felt for beregnet verdi for en enkelt aktivitet, for eksempel en telefonsamtale, faks eller avtale. Men du må legge sammen dataene ved hjelp av beregnede felt for å oppnå resultatet fra eksemplet som vises nedenfor. Nå kan du gjøre det alt i ett trinn ved å definere ett felt for beregnet verdi for aktivitetsenheten.  
  
![Beregn verdier for alle aktiviteter på en konto](media/rollup-enhancements-activities.png)  
  
### <a name="aggregate-data-for-a-record-from-all-related-activities-and-activities-indirectly-related-via-the-activity-party-entity"></a>Aggreger data for en post fra relaterte aktiviteter og aktiviteter som er indirekte relatert, via ActivityParty-enheten  

I dette eksemplet teller vi totalt antall e-poster som ble sendt til en konto, der kontoen er oppført på e-postens «Mottaker»- eller «Kopi mottaker»-linjen. Dette gjøres ved å angi **Deltakelsestype** i **FILTRE** for ActivityParty-enheten i definisjonen av feltet for beregnet verdi. Hvis du ikke bruker filtrering, brukes alle tilgjengelige deltakelsestyper for en aktivitet, i beregningen. 
 
Hvis du vil ha mer informasjon om de ActivityParty-enheten og deltakelsestypene som er tilgjengelig for en bestemt aktivitet, kan du se [ActivityParty-enhet](/dynamics365/customer-engagement/developer/activityparty-entity).

  
![Relaterte aktiviteter og aktivitetspart for beregnet verdi](media/rollup-enhancements-indirect-activities.png)  
  
### <a name="aggregate-data-for-a-record-from-related-records-using-the-avg-operator"></a>Aggreger data for en post fra relaterte poster ved bruk av AVG-operatoren

I dette eksemplet beregner vi en gjennomsnittlig anslått omsetning fra alle muligheter, som er knyttet til en konto.  
  
![Gjennomsnittlig anslått omsetning i Dynamics 365](media/rollup-enhancements-average.PNG)  
  
Eksemplet nedenfor viser hvordan du kan beregne en gjennomsnittlig anslått omsetning fra relaterte muligheter over et hierarki over kontoer. Du kan se gjennomsnittlig anslått omsetning på hvert nivå i hierarkiet.  
  
![Gjennomsnittlig anslått omsetning i Dynamics 365](media/cust-rollup-enhancements-avg-over-hierarchy.png)  
  
<a name="BKMK_considerations"></a> 

## <a name="rollup-field-considerations"></a>Viktige faktorer for felt for beregnet verdi 

Du bør være klar over visse betingelser og begrensninger når du arbeider med felt for beregnet verdi:  
  
- Du kan definere maksimalt 100 felt for beregnet verdi for organisasjonen og opptil 10 felt for beregnet verdi per enhet.  
- En arbeidsflyt kan ikke utløses av feltoppdateringene for beregnet verdi.  
- En Vent-betingelse for en arbeidsflyt kan ikke bruke et felt for beregnet verdi.  
- En beregnet verdi over feltet for beregnet verdi støttes ikke.  
- En beregnet verdi kan ikke referere til et beregnet felt som bruker et annet beregnede felt, selv om alle feltene på det andre beregnede feltet befinner seg på den gjeldende enheten.  
- Den beregnede verdien kan bare ta i bruk filtre på kildeenheten eller relaterte enheter, enkle felt eller ikke-komplekse beregnede felt.  
- En beregnet verdi kan bare gjøres over relaterte enheter med 1:N-relasjon. En beregnet verdi kan ikke utføres over N:N-relasjoner.  
- En beregnet verdi kan ikke utføres over 1:N-relasjonen for Aktivitet-enheten eller ActivityParty-enheten.  
- Forretningsregler, arbeidsflyter eller beregnede felt bruker alltid den siste beregnede verdien i feltet for beregnet verdi.  
- Et felt for beregnet verdi er aggregert etter systembruker. Alle brukere er i stand til å se den samme verdien i feltet for beregnet verdi. Du kan kontrollere synligheten til feltet for beregnet verdi med sikkerhet på feltnivå (FLS) ved å begrense hvem som har tilgang til feltet for beregnet verdi. Hvis du vil ha mer informasjon, kan du se  [Sikkerhet på feltnivå for å kontrollere tilgang](/dynamics365/customer-engagement/admin/field-level-security). 

### <a name="precision-rounding"></a>Nøyaktig avrunding
 
Hvis nøyaktigheten til det aggregerte feltet er større enn nøyaktigheten til feltet for beregnet verdi, avrundes nøyaktigheten til det aggregerte feltet nedover til nøyaktigheten til feltet for beregnet verdi, før aggregasjonen utføres. La oss ta for oss et spesifikt eksempel for å illustrere denne atferden. La oss si at feltet for beregne verdi på kontoen, for å beregne den totale anslåtte omsetningen til de relaterte mulighetene, har en nøyaktighet på to desimaltegn. Feltet Ansl. omsetning på salgsmulighetsenheten er det aggregerte feltet med en nøyaktighet på fire desimaltegn. I vårt eksempel har kontoen to relaterte muligheter. Den aggregerte summen av den anslåtte omsetningen beregnes som følger:  
  
1. Ansl. omsetning for den første salgsmuligheten: USD 1000,0041  
1. Ansl. omsetning for den andre salgsmuligheten: USD 2000,0044  
1. Aggregert sum av Ansl. omsetning: USD 1000,00 + USD 2 000,00 = USD 3000,00

Som du kan se så gjennomføres avrundingen til to desimaltegn på det aggregerte feltet før aggregasjonen gjennomføres.  
  
### <a name="different-behavior-from-associated-grids"></a>Ulik atferd fra tilknyttede rutenett
 
Enkelte enhetsskjemaer, som Konto eller Kontakt, inneholder allerede de tilknyttede rutenettene (slik som de er). Et Konto-skjema inkluderer Kontakter, Tilfeller, Salgsmuligheter og andre rutenett. Noen av postene som vises i rutenettene for Konto-skjema er direkte relatert til kontoposten, andre (indirekte) gjennom relasjonene med andre poster. Til sammenligning bruker bare aggregasjonen tilhørende feltet for beregnet verdi direkte relasjoner, som er uttrykkelig definert i definisjonen av feltet for beregnet verdi. Ingen andre relasjoner vurderes. La oss se på et annet eksempel for å illustrere forskjellen i virkemåte.  
  
1. Kontoen A1 har en hovedkontakt, P1. Tilfellet C1 er tilknyttet med kontoen A1 (C1.Customer field  =  A1) og tilfellet C2 er tilknyttet med kontakten P1 (C2.Customer field = P1).  
1. **Cases**-rutenettet på **Account**-skjemaet for A1-posten viser to tilfeller: C1 og C2.  
1. Feltet for beregnet verdi på kontoenheten, som heter Totalt antall tilfeller, brukes for å telle tilfellene som er tilknyttet med kontoen.  
1. I definisjonen av feltet for beregnet verdi for kontoen spesifiserer vi tilfellene som har kunderelasjonen med kontoen. Etter aggregasjonen er Totalt antall tilfeller lik 1 (tilfelle C1). Tilfellet C2 er ikke inkludert i summen da det er direkte relatert til kontakten, og ikke kontoen, og kan ikke uttrykkelig defineres i definisjonen av feltet for beregnet verdi for kontoen. Som et resultat av dette vil ikke totalantallet tilfeller som returneres av operasjonen for beregnet verdi, stemme overens med antallet tilfeller som vises i **Tilfeller**-rutenettet.  
  
### <a name="see-also"></a>Se også  

[Opprette og redigere felter](create-edit-fields.md)<br />
[Definer beregnede felt](define-calculated-fields.md)<br />
[Virkemåte og formatet for Dato- og Tidspunkt-feltet](behavior-format-date-time-field.md)<br />
[Definer og spør hierarkisk relatert data](define-query-hierarchical-data.md)<br />
[Video: Felt for beregnet verdi og beregnede felt](http://www.youtube.com/watch?v=RoahCH1p3T8&list=PLC3591A8FE4ADBE07&index=8)<br />
[Video: Bruk Power BI](http://www.youtube.com/watch?v=PkQe4BFlBS8&list=PLC3591A8FE4ADBE07&index=3)
