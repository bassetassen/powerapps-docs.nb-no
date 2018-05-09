---
title: DSR-veiledning for kundeopprettede data
description: DSR-veiledning for kundeopprettede data for PowerApps
services: powerapps
suite: powerapps
documentationcenter: na
author: jamesol-msft
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 04/17/2018
ms.author: paulliew
ms.openlocfilehash: cff822e24f1384833caa0baa945a7d3d07a8ee9b
ms.sourcegitcommit: e3a2819c14ad67cc4ca6640b9064550d0f553d8f
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/20/2018
---
# <a name="responding-to-data-subject-rights-dsr-requests-for-customer-data-in-common-data-service-for-apps"></a>Svar på DSR-forespørsler om kundedata i Common Data Service for Apps

## <a name="introduction-to-dsr-requests"></a>Innføring i DSR-forespørsler
Vi har laget denne dokumentasjonen for å hjelpe deg med å forberede deg på å implementere EUs personvernforordning (GDPR). Dokumentasjonen beskriver hva vi gjør for å forberede oss på EUs personvernforordning (GDPR). I tillegg gir den eksempler på hva du som Microsoft-bruker kan gjøre i dag for å sikre at du samsvarer med GDPR-forskriftene når du bruker PowerApps, Microsoft Flow og Common Data Service (CDS) for Apps.

GDPR gir en bruker (kalt «den registrerte» i forordningen) rett til å behandle personopplysningene som en arbeidsgiver eller et annet byrå eller organisasjon («datakontrollør» eller bare «kontrollør») har samlet inn. Personopplysninger er definert svært bredt under GDPR som alle data som er knyttet til en identifisert eller identifiserbar person. GDPR gir brukere bestemte rettigheter til personopplysningene sine. Disse rettighetene omfatter det å få kopier av personopplysninger, be om at de rettes, begrense behandlingen av dem, slette dem eller motta dem i elektronisk format slik at de kan flyttes til en annen kontrollør. En formell forespørsel fra en bruker til en kontrollør om behandling av personopplysningene sine, kalles en DSR-forespørsel.

Veiledningen beskriver hvordan du bruker Microsofts produkter, tjenester og administrative verktøy for å hjelpe kontrollørkundene våre med å finne og behandle personopplysninger i forbindelse med DSR-forespørsler. Dette omfatter spesifikt hvordan du finner, får tilgang til og behandler personopplysninger som befinner seg i Microsoft-skyen. Her er en rask oversikt over prosessene som er beskrevet i denne veiledningen:

1. **Finne** – Bruk søke- og oppdagelsesverktøy til enklere å finne kundedata som kan danne grunnlaget for en DSR-forespørsel. Når potensielt relevante dokumenter er samlet inn, kan du utføre en eller flere av DSR-handlingene som er beskrevet i trinnene nedenfor, for å svare på forespørselen. Eventuelt kan du avgjøre at forespørselen ikke oppfyller organisasjonens retningslinjer for å svare på DSR-forespørsler.

2. **Få tilgang til** – Hent personopplysninger som ligger i Microsoft-skyen, og lag eventuelt en kopi til brukeren.

3. **Korrigere** – Gjør eventuelle endringer eller implementer andre forespurte handlinger i personopplysningene.

4. **Begrense** – Begrense behandlingen av personopplysninger, enten ved å fjerne lisenser for ulike nettbaserte tjenester eller ved å slå av de ønskede tjenestene der det er mulig. Du kan også fjerne data fra Microsoft-skyen og beholde dem lokalt eller på en annen plassering.

5. **Slette** – Fjern personopplysninger som ligger i Microsoft-skyen, permanent.

6. **Eksportere** – Lag en elektronisk kopi (i maskinlesbart format) av personopplysningene til brukeren.

Hver del i denne veiledningen beskriver de tekniske prosedyrene som en datakontrollørorganisasjon kan utføre for å svare på en DSR-forespørsel om personopplysninger i Microsoft-skyen.

## <a name="common-data-service-customer-data"></a>Common Data Service-kundedata

> [!IMPORTANT]
> Gjelder for både Common Data Service for Apps og Common Data Service (forrige versjon)

Det finnes to typer Common Data Services (CDS): CDS for Apps og den forrige versjonen av CDS. Hver har sin egen prosess for personopplysninger.

Du kan identifisere hvilken type CDS-miljø du har, ved å følge disse trinnene fra [PowerApps-området](https://web.powerapps.com):

1.  Velg **miljøet** fra rullegardinlisten Environment (Miljø).
2.  Gå til **Data** (Data)  >  **Entities** (Enheter).

    Miljøet ditt er CDS for Apps hvis disse enhetene vises:

    ![Liste over PowerApps-enheter](./media/common-data-service-gdpr-dsr-guide/powerapps-entities-list.png)

    Miljøet ditt er forrige versjon av CDS hvis disse enhetene vises:

    ![Liste over eldre PowerApps-enheter](./media/common-data-service-gdpr-dsr-guide/powerapps-legacy-entities-list.png)

Når du har fastsatt hvilken type CDS-miljø du har, kan du følge de tilsvarende delene i dette dokumentet for å identifisere personopplysninger.

> [!NOTE]
> Du kan ha noen miljøer i CDS for Apps og andre i CDS (forrige versjon), så du må gjenta prosessene som er beskrevet nedenfor, for hvert miljø i organisasjonen.

## <a name="user-personal-data-in-common-data-service-for-apps"></a>Personopplysninger for brukere i Common Data Service for Apps

### <a name="prerequisites"></a>Forutsetninger
For å få tilgang til CDS må det være opprettet en bruker fra administrasjonssenteret for Office 365, og brukeren må ha fått tilordnet en relevant brukerlisens for Common Data Service.  Det kreves også en sikkerhetsrolle før brukeren kan begynne å bruke Common Data Service.

Personopplysninger for brukere oppbevares i administrasjonssenteret for Office 365 og i brukerenheten for CDS-systemet.  Et bestemt sett med standardpersonopplysninger for brukere oppbevares og vedlikeholdes i administrasjonssenteret for Office 365 (for eksempel brukernavn, bruker-ID, telefonnummer, e-post og adresse). Dette settet med personopplysninger for brukeren synkroniseres til brukerenheten for CDS-systemet i alle miljøer.  Systemansvarlig kan bare oppdatere dette settet med personopplysninger i administrasjonssenteret for Office 365, og disse attributtene synkroniseres deretter automatisk til CDS for Apps. Systemansvarlig kan også opprette egendefinerte attributter for å registrere ytterligere personopplysninger for brukere i brukerenheten for CDS-systemet.  Disse egendefinerte attributtene vedlikeholdes og behandles manuelt i CDS av systemansvarlig.

Når en bruker slettes fra administrasjonssenteret for Office 365, fjernes ikke oppføringen for brukeren automatisk fra brukerenheten i CDS-systemet, for å unngå avbrudd i forretningsprogrammer som kan være viktige for organisasjonens drift.  CDS-systemansvarlig må finne og fjerne personopplysninger for brukere fra CDS ved hjelp av programmet.

Det er bare brukere som har rollen global administrator i Office 365 og sikkerhetsrollen systemansvarlig i CDS som kan utføre handlingene under Finn, Korriger, Eksporter og Slett nedenfor.

### <a name="discover"></a>Discover

Systemansvarlige kan opprette flere CDS-instanser.  Disse instansene kan brukes til utprøving, utvikling eller produksjon.   Hver av disse instansene har en kopi av systembrukerenheten med eventuelle egendefinerte attributter som kan ha blitt lagt til av systemansvarlig, samt personopplysninger for brukere synkronisert fra administrasjonssenteret for Office 365.

Systemansvarlig kan finne en liste over alle CDS-instanser ved å gå til administrasjonssenteret for Dynamics 365 fra administrasjonssenteret for PowerApps.

Fra [administrasjonssenteret for PowerApps](https://admin.powerapps.com/):

1.  Gå til fanen Environments (Miljøer).
2.  Velg et miljø i listen over miljøer.
3.  Klikk på koblingen for administrasjonssenteret for Dynamics 365.

    ![Miljødetaljer i PowerApps](./media/common-data-service-gdpr-dsr-guide/powerapps-environment-details.png)

    Det vises en liste over alle instanser.

    ![Instansvelger i PowerApps](./media/common-data-service-gdpr-dsr-guide/powerapps-instance-picker.png)

Personopplysninger fra brukere av CDS finnes på følgende steder:

|Ressurser som inneholder personopplysninger | Formål | Nettstedstilgang | Programmatisk tilgang
| --- | --- | --- | ---
| Enhetsoppføring | Systembrukerenhet | [Administrasjonssenteret for PowerApps](https://admin.powerapps.com) | [Via nett-API](https://docs.microsoft.com/en-us/dynamics365/customer-engagement/developer/webapi/update-delete-entities-using-web-api#basic-update)
| Revisjonshistorikk | Brukes til å gi kunder tillatelse til å identifisere ressurser som brukere har opprettet, hatt tilgang til, endret eller slettet på et enhetsnivå. | [Administrasjonssenteret for PowerApps](https://admin.powerapps.com) | [Via nett-API](https://docs.microsoft.com/en-us/dynamics365/customer-engagement/developer/webapi/update-delete-entities-using-web-api#basic-update)

#### <a name="user"></a>Bruker
Personopplysninger for brukere som vedlikeholdes og administreres i administrasjonssenteret for Office 365, lagres i Azure Active Directory.  Disse personopplysningene administreres i administrasjonssenteret for Office 365 og synkroniseres automatisk til alle CDS-miljøer.  Systemansvarlig kan ikke oppdatere disse personopplysningene data direkte i CDS mens brukeren er aktiv. De må oppdateres direkte i administrasjonssenteret for Office 365.  Ytterligere personopplysninger (for eksempel egendefinerte attributter) kan legges til direkte i CDS og må vedlikeholdes og administreres manuelt av systemansvarlig.

En systemansvarlig for CDS kan finne en gitt brukeren og de tilknyttede personopplysningene ved å følge disse trinnene:

Fra [administrasjonssenteret for PowerApps](https://admin.powerapps.com/):

1.  Gå til fanen Environments (Miljøer).
2.  Velg et miljø i listen over miljøer.
3.  Klikk på koblingen for administrasjonssenteret for Dynamics 365.
4.  Klikk på navnet på miljøet.
5.  Klikk på **Open** (Åpne).
6.  Gå til **Settings** (Innstillinger)  >  **Security** (Sikkerhet).
7.  Klikk på **Users** (Brukere).
8.  Skriv inn brukeren i inndataboksen **Search** (Søk).
9.  Klikk på **Search** (Søk).
10. Dobbeltklikk på brukeren.

    ![Brukerskjema i PowerApps](./media/common-data-service-gdpr-dsr-guide/powerapps-user-form.png)

#### <a name="audit-history"></a>Revisjonshistorikk
Når [revisjonssporing er aktivert](https://docs.microsoft.com/dynamics365/customer-engagement/admin/audit-data-user-activity) for en entitet i Common Data Service, blir personopplysninger for brukere logget i revisjonshistorikken sammen med hendelsene som brukeren utførte.

### <a name="rectify"></a>Korriger

Hvis en bruker har bedt deg om å korrigere personopplysningene i organisasjonens data, må du og organisasjonen avgjøre om forespørselen skal utføres.  Korrigering av data kan omfatte handlinger som blant annet redigering eller fjerning av personopplysninger fra et dokument eller annet element.

Du kan bruke Azure Active Directory til å administrere identiteter (personopplysninger) for sluttbrukerne dine i Common Data Service for Apps. Bedriftskunder har muligheten til å administrere DSR-forespørsler om korrigering, inkludert begrensede redigeringsfunksjoner i samsvar med en gitt Microsoft-tjeneste.  Som databehandler tilbyr ikke Microsoft muligheten til å korrigere systemgenererte logger, ettersom disse gjenspeiler faktiske aktiviteter og regnes som en historisk oversikt over hendelser i Microsofts tjenester. Se [GDPR: Data Subject Requests (DSRs)](https://servicetrust.microsoft.com/ViewPage/GDPRDSR) (GDPR: DRS-forespørsler) for mer informasjon.

Når brukeroppføringen er slettet fra Azure Active Directory, kan systemansvarlige fjerne eventuelle gjenværende personopplysninger for brukeren (for eksempel egendefinerte attributter de har lagt til) fra alle instanser.  

### <a name="export"></a>Eksporter

#### <a name="system-user"></a>Systembruker
Personopplysninger for brukere som er lagret i systembrukerenheten, kan eksporteres til Excel fra brukerlisten i portalen.

Fra [administrasjonssenteret for PowerApps](https://admin.powerapps.com/):

1.  Gå til fanen Environments (Miljøer).
2.  Velg et miljø i listen over miljøer.
3.  Klikk på koblingen for administrasjonssenteret for Dynamics 365.
4.  Klikk på navnet på miljøet.
5.  Klikk på Open (Åpne). Gå til Settings (Innstillinger) > Security (Sikkerhet).
6.  Velg visningen Enabled Users (Aktiverte brukere).
7.  Klikk på Export to Excel (Eksporter til Excel).

#### <a name="audit-history"></a>Revisjonshistorikk
Du kan ta skjermbilder av revisjonshistorikken og kopiere dem fra programmet ved å følge trinnene som er beskrevet nedenfor.
Fra [administrasjonssenteret for PowerApps](https://admin.powerapps.com/):
1.  Gå til fanen Environments (Miljøer).
2.  Velg et miljø i listen over miljøer.
3.  Klikk på koblingen for administrasjonssenteret for Dynamics 365.
4.  Klikk på navnet på miljøet.
5.  Klikk på Open (Åpne).
6.  Gå til Settings (Innstillinger) > Auditing (Revisjon).

    ![Revisjonshistorikkmeny i PowerApps](./media/common-data-service-gdpr-dsr-guide/powerapps-audit-history-menu.png)

7.  Klikk på Audit Summary View (Sammendragsvisning for sporing av endringer).
8.  Finn revisjonsoppføringen for brukeren.

    ![Revisjonshistorikkdetaljer i PowerApps](./media/common-data-service-gdpr-dsr-guide/powerapps-audit-history-details.png)

9.  Trykk på Alt-PrtScn for å ta skjermbildet.
10. Lagre skjermbildet i en fil.
11. Nå kan du sende filen til den som gjorde DSR-forespørselen.

### <a name="delete"></a>Slett

#### <a name="user"></a>Bruker
Når en bruker slettes fra administrasjonssenteret for Office 365, settes statusen for brukeren til Disabled (Deaktivert) i CDS. Personopplysningene for brukeren slettes imidlertid ikke automatisk, for å unngå avbrudd i forretningsprogrammer som kan være viktige for organisasjonens drift.
For at personopplysningene for den deaktiverte brukeren skal bli slettet i CDS, må systemansvarlig fjerne dem manuelt.

#### <a name="remove-user-personal-data-via-user-form"></a>Fjern personopplysninger for brukere via brukerskjema
Når oppføringen for brukeren er slettet fra Azure Active Directory, vises følgende melding i brukerskjemaet.
This user’s information is no longer managed by Office 365. (Informasjonen for denne brukeren administreres ikke lenger av Office 365.) You can update this record to respond to DSR requests by removing or replacing all personal data associated with this user. (Du kan oppdatere denne oppføringen for å håndtere DSR-forespørsler ved å fjerne eller erstatte alle personopplysninger tilknyttet denne brukeren.)

Fra [administrasjonssenteret for PowerApps](https://admin.powerapps.com/):
1.  Gå til fanen Environments (Miljøer).
2.  Velg et miljø i listen over miljøer.
3.  Klikk på koblingen for administrasjonssenteret for Dynamics 365.
4.  Klikk på navnet på miljøet.
5.  Klikk på **Open** (Åpne).
6.  Klikk på **Settings** (Innstillinger)  >  **Security** (Sikkerhet)  >  **Users** (Brukere).
7.  Velg visningen **Disabled Users** (Deaktiverte brukere).
8.  Skriv inn brukernavnet i **Search for records** (Søk etter oppføringer), og klikk på **Search** (Søk).
9.  Dobbeltklikk på brukernavnet i søkeresultatene.
10. Fjern alle personopplysninger, og klikk på **Save** (Lagre).

#### <a name="remove-user-personal-data-via-excel-importexport"></a>Fjern personopplysninger for brukere via import og eksport i Excel
1.  Klikk på **Settings** (Innstillinger)  >  **Security** (Sikkerhet)  >  **Users** (Brukere).
2.  Velg visningen **Disabled Users** (Deaktiverte brukere).
3.  Opprett en Excel-mal med alle kolonnene for personopplysninger for brukere som du vil oppdatere.
4.  Klikk på **Download file** (Last ned fil)
5.  Åpne den nedlastede filen i Excel, gjør oppdateringene, og lagre filen.
6.  Gå tilbake til visningen Disabled Users (Deaktiverte brukere), og klikk på Import Data (Importer data).
7.  Velg den oppdaterte Excel-filen i dialogboksen Upload data file (Last opp datafil).
8.  Gjør de nødvendige endringene i vinduet Map Fields (Tilordne felt).
9.  Klikk på Next (Neste) og Submit (Send inn).

Se [mer Excel-informasjon](https://docs.microsoft.com/en-us/dynamics365/customer-engagement/admin/analyze-your-data-with-excel-templates) om bruk av Excel-maler.


#### <a name="remove-audit-history-via-the-audit-summary-view-form"></a>Fjern revisjonshistorikk via skjemaet Audit Summary View (Sammendragsvisning for sporing av endringer)

Fra [administrasjonssenteret for PowerApps](https://admin.powerapps.com/):
1.  Gå til fanen Environments (Miljøer).
2.  Velg et miljø i listen over miljøer.
3.  Klikk på koblingen for administrasjonssenteret for Dynamics 365.
4.  Klikk på navnet på miljøet.
5.  Klikk på Open (Åpne).
6.  Klikk på Settings (Innstillinger) > Auditing (Sporing av endringer).
7.  Velg Audit Summary View (Sammendragsvisning for sporing av endringer).
8.  Finn brukerens endringshistorikk.
9.  Klikk på avmerkingsboksen for radene.
10. Klikk på ikonet Slett endringshistorikk.

## <a name="personal-data-stored-in-common-data-service-for-apps-databases"></a>Personopplysninger lagret i databaser for Common Data Service for Apps

### <a name="prerequisites"></a>Forutsetninger
Det kan hende du lagrer personopplysninger fra enkeltpersoner (for eksempel dine egne kunder) i innholdet i CDS-enhetene dine.  

Når en person sender en DSR-forespørsel til organisasjonen, må systemansvarlig for CDS finne alle enhetene som personen kan refereres i, i programmet.  CDS-administratoren har ansvaret for å vedlikeholde en oversikt over hvor personopplysninger blir lagret i ulike enheter du bruker, slik at du kan svare på DSR-forespørsler fra enkeltpersoner.

Personopplysninger i innholdet kan deretter eksporteres, korrigeres eller slettes i en enhet ved hjelp av funksjonene i produktet.  

### <a name="discover"></a>Discover
Når en CDS-administrator mottar en DSR-forespørsel fra en enkeltperson, må administratoren identifisere hvilke miljøer/CDS-instanser som inneholder personopplysninger for den personen.  Du bør utarbeide retningslinjer og prosedyrer for vedlikehold av en oversikt over miljøer, instanser og enheter der du har valgt å lagre personopplysninger data fra personer. Dette gjør det enklere å identifisere personopplysninger som er lagret i innholdet.

Ved å bruke oversikten over miljøer, instanser, enheter og felt der personopplysninger er lagret, kan du konfigurere CDS-søkemotoren til å finne personopplysningene.  En CDS-administrator kan konfigurere søkeenhetene og -feltene. Se [Konfigurere relevanssøk](https://go.microsoft.com/fwlink/?linkid=872506) for mer informasjon.
CDS-administratoren kan deretter gå til CDS-miljøet og utføre et søk.

1.  Klikk på **Search** (Søk).
2.  Velg **Relevance Search** (Relevanssøk)

    ![Meny for relevanssøk i PowerApps](./media/common-data-service-gdpr-dsr-guide/powerapps-relevance-search-menu.png)

3.  Angi personopplysningene for brukeren i søkeboksen.
4.  Klikk på Search (Søk).

    ![Resultater av relevanssøk i PowerApps](./media/common-data-service-gdpr-dsr-guide/powerapps-relevance-search-results.png)

Personopplysninger i innholdet lagres vanligvis i nøkkelenhetene, for eksempel konto, kontakt, kundeemne eller salgsmulighet, men det er ditt ansvar å opprettholde en oversikt over hvor du lagrer personopplysninger for enkeltpersoner.

### <a name="rectify"></a>Korriger
Systemansvarlig for CDS kan oppdatere enkeltpersoners personopplysninger ved hjelp av listen over resultater fra relevanssøket.  Du kan imidlertid også ha lagret personopplysningene for denne personen i andre egendefinerte enheter.  Systemansvarlig for CDS har ansvaret for å opprettholde en oversikt over disse egendefinerte enhetene og gjøre den aktuelle oppdateringen i personopplysningene.

Gjør følgende fra resultatene av relevanssøket:

1.  Klikk på et element der det ble funnet personopplysninger.
2.  Oppdater personopplysningene der det er aktuelt.
3.  Klikk på Save (Lagre).

    ![PowerApps-kontodetaljer](./media/common-data-service-gdpr-dsr-guide/powerapps-account-details.png)

### <a name="export"></a>Eksporter
Du kan ta et skjermbilde av dataene og dele dem med den som kom med DSR-forespørselen, ved å følge trinnene som er beskrevet nedenfor.

Fra [administrasjonssenteret for PowerApps](https://admin.powerapps.com/):
1.  Gå til fanen Environments (Miljøer).
2.  Velg et miljø i listen over miljøer.
3.  Klikk på koblingen for administrasjonssenteret for Dynamics 365.
4.  Klikk på navnet på miljøet.
5.  Klikk på **Search** (Søk).
6.  Velg Relevance Search (Relevanssøk).
7.  Angi personopplysningene for brukeren i søkeboksen.
8.  Klikk på Search (Søk).
9.  Finn elementet, og dobbeltklikk på det.
10. Trykk på <alt> <PrtScn> for å ta skjermbildet.
11. Lagre skjermbildet i en fil.
12. Nå kan du sende filen til den som gjorde DSR-forespørselen.

### <a name="delete"></a>Slett

CDS-administratoren kan slette en brukers personopplysninger fra oppføringer der dataene er lagret.  CDS-administratoren kan velge å enten (1) slette oppføringen der personopplysningene er lagret, eller (2) fjerne innholdet i personopplysningene fra oppføringen.  

> [!NOTE]
> CDS-administratorer kan tilpasse miljøet for å hindre at en oppføring blir slettet fra en enhet. Hvis miljøet er konfigurert på denne måten, må du fjerne innholdet i personopplysningene fra oppføringen i stedet for å slette selve oppføringen.

Gjør følgende fra resultatene av relevanssøket:
1.  Klikk på et element der det ble funnet personopplysninger.
2.  Klikk på ikonet Delete (Slett) på båndet (vær oppmerksom på at dette ikonet er deaktivert hvis oppføringen ikke kan slettes).

    ![Kontosletting i PowerApps](./media/common-data-service-gdpr-dsr-guide/powerapps-account-delete.png)

## <a name="personal-data-stored-in-common-data-service-previous-version-databases"></a>Personopplysninger lagret i databaser for Common Data Service (forrige versjon)

### <a name="prerequisites"></a>Forutsetninger

Det kan hende du lagrer personopplysninger fra enkeltpersoner (for eksempel dine egne kunder eller brukere) i innholdet i CDS-enhetene dine.  

Når en person sender en DSR-forespørsel til organisasjonen, må systemansvarlig for CDS finne alle enhetene som personen kan refereres i, i programmet.  CDS-administratoren har ansvaret for å vedlikeholde en oversikt over hvor personopplysninger blir lagret i ulike enheter du bruker, slik at du kan svare på DSR-forespørsler fra enkeltpersoner.

Personopplysninger i innholdet kan deretter eksporteres, korrigeres eller slettes i en enhet ved hjelp av funksjonene i produktet.  

### <a name="discover"></a>Discover
Når en CDS-administrator mottar en DSR-forespørsel fra en enkeltperson, må administratoren identifisere hvilke miljøer/CDS-instanser som inneholder personopplysninger for den personen.  Du bør utarbeide retningslinjer og prosedyrer for vedlikehold av en oversikt over miljøer, instanser og enheter der du har valgt å lagre personopplysninger data fra personer. Dette gjør det enklere å identifisere personopplysninger som er lagret i innholdet.

Personopplysninger fra enkeltpersoner finnes på følgende steder:

|Ressurser som inneholder personopplysninger | Formål | Nettstedstilgang |    Programmatisk tilgang
| --- | --- | --- | ---
|Enhetsoppføringer | Brukes til å registrere forretningstransaksjoner i de respektive forretningsenhetene. | Utviklerportalen for PowerApps |    Nei

#### <a name="entity-records"></a>Enhetsoppføringer
Personopplysninger for enkeltpersoner kan lagres i en hvilken som helst forretningsenhet.
Denne versjonen av Common Data Service inneholder sitt eget databaseskjema og infrastruktur.  Den har sine egne enheter, og administrasjonen av disse enhetene håndteres via [PowerApps-området](http://web.powerapps.com/).

Slik ser du en liste over enhetene dine:

1.  Velg miljøet.

    ![Eldre PowerApps-enheter](./media/common-data-service-gdpr-dsr-guide/powerapps-legacy-entities.png)

2.  Gå til **Data** (Data)  >  fanen **Entities** (Enheter).
3.  Velg enheten, for eksempel kontoenheten.

    ![Detaljliste over eldre PowerApps-enheter](./media/common-data-service-gdpr-dsr-guide/powerapps-legacy-entities-details-list.png)

4.  Klikk på enheten.
5.  Klikk på **Data**-fanen. Det vises en liste over oppføringer for enheten.

    ![Eldre kontodata for PowerApps](./media/common-data-service-gdpr-dsr-guide/powerapps-legacy-account-data.png)

6.  Klikk på ikonet **Export data** (Eksporter data).
7.  Åpne Excel-regnearket når eksporten er fullført.
8.  Klikk på boksen Aktiver redigering.
9.  Klikk på søkeikonet.
10. Skriv inn personopplysningene du vil søke etter.
Personopplysninger i innholdet lagres vanligvis i nøkkelenhetene, for eksempel konto, kontakt, kundeemne, salgsmulighet eller arbeider, men det er ditt ansvar å opprettholde en oversikt over hvor du lagrer personopplysninger for enkeltpersoner.
11. Bruk listen over enheter der det er lagret personopplysninger, og **gjenta trinnene ovenfor for hver av forretningsenhetene for å finne de individuelle personopplysningene**.

### <a name="rectify"></a>Korriger
Hvis en bruker har bedt deg om å korrigere personopplysningene i organisasjonens data, må du og organisasjonen avgjøre om forespørselen skal utføres.  Korrigering av data kan omfatte handlinger som blant annet redigering eller fjerning av personopplysninger fra et dokument eller annet element.

Du kan bruke Azure Active Directory til å administrere identiteter (personopplysninger) for sluttbrukerne dine i Common Data Service for Apps. Bedriftskunder har muligheten til å administrere DSR-forespørsler om korrigering, inkludert begrensede redigeringsfunksjoner i samsvar med en gitt Microsoft-tjeneste.  Som databehandler tilbyr ikke Microsoft muligheten til å korrigere systemgenererte logger, ettersom disse gjenspeiler faktiske aktiviteter og regnes som en historisk oversikt over hendelser i Microsofts tjenester.  

Se [GDPR: Data Subject Requests (DSRs)](https://servicetrust.microsoft.com/ViewPage/GDPRDSR) (GDPR: DRS-forespørsler) for mer informasjon.

Du kan korrigere personopplysninger som ligger i CDS-miljøet ved å eksportere enhetsdataene til et Excel-regneark, oppdatere dem og deretter importere oppdateringene tilbake til databasen.
CDS-administratoren har ansvaret for å identifisere alle enheter der de individuelle personopplysningene er lagret, og for å gjenta trinnene nedenfor for hver av disse enhetene.

Gjør følgende fra [PowerApps-området](http://web.powerapps.com/):

1.  Klikk på **Data** (Data)  >  **Entities** (Enheter).
2.  Klikk på enheten, for eksempel Konto.
3.  Klikk på alternativet **Data**.
4.  Klikk på ikonet **Export data** (Eksporter data).
5.  Klikk på ikonet **Open in Excel** (Åpne i Excel) når eksporten er fullført.
6.  Aktiver redigering i Excel-regnearket, og oppdater personopplysningene.
7.  Lagre det oppdaterte regnearket (velg **Lagre som**, slik at du vet hvor filen ligger).

    ![Eldre kontodata for PowerApps](./media/common-data-service-gdpr-dsr-guide/powerapps-legacy-account-data.png)

8.  Utfør de nødvendige oppdateringene i personopplysningene.
9.  Lagre oppdateringene.
10. Gå til Data (Data) > Entities (Enheter) > skjemaet Account (Konto), og klikk på Import data (Importer data).
11. Klikk på Search (Søk).
12. Velg filen som inneholder oppdateringene.
13. Klikk på Open (Åpne).
14. Klikk på Import (Importer).

### <a name="export"></a>Eksporter

Du kan vise og eksportere personopplysninger fra hver enhet til et Excel-regneark.

Gjør følgende fra [PowerApps-området](http://web.powerapps.com/):

1.  Gå til **Data** (Data)  >  **Entities** (Enheter).
2.  Velg enheten du vil vise og eksportere opplysninger for.
3.  Klikk på alternativet **Data**.
4.  Klikk på ikonet **Export data** (Eksporter data). Denne eksportoperasjonen kjøres i bakgrunnen, og du blir varslet når den er fullført.
5. Du viser de eksporterte dataene ved å klikke på Open in Excel (Åpne i Excel).

### <a name="delete"></a>Slett
Du kan slette personopplysninger som er lagret i enheter, ved å bruke funksjonen for eksport/import av data.

CDS-administratoren har ansvaret for å identifisere alle enhetene som inneholder personopplysningene, og for å gjenta følgende trinn for hver av enhetene.

Gjør følgende fra [PowerApps-området](http://web.powerapps.com/):

1.  Klikk på **Data** (Data)  >  **Entities** (Enheter).
2.  Rull ned til enhetslisten og finn enheten der du vil fjerne personopplysninger.
3.  Klikk på enheten.
4.  Klikk på alternativet **Data**.
5.  Klikk på ikonet **Export data** (Eksporter data).
6.  Klikk på ikonet **Open in Excel** (Åpne i Excel) når eksporten er fullført.
7.  **Aktiver redigering** i Excel-regnearket.
8.  **Lagre** det oppdaterte regnearket (velg Lagre som, slik at du vet hvor filen ligger).
9.  Slett radene som inneholder personopplysningoppføringene du vil fjerne.
10. Lagre oppdateringene.
11. Gå til skjemaet **Entities** (Enheter) og klikk på **Import data** (Importer data).
12. Klikk på **Search** (Søk).
13. Velg filen som inneholder oppdateringene.
14. Klikk på **Open** (Åpne).
15. Klikk på Import (Importer).
