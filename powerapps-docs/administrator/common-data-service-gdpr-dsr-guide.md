---
title: Svar på DSR-forespørsler om kundedata for CDS for Apps | Microsoft Docs
description: Gjennomgang av hvordan du svarer på DSR-forespørsler om kundedata for CDS for Apps
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
ms.date: 04/23/2018
ms.author: paulliew
ms.openlocfilehash: 88a3d0c31a9608a901d99a8a901a209f14c13fc0
ms.sourcegitcommit: 8bd4c700969d0fd42950581e03fd5ccbb5273584
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/26/2018
---
# <a name="responding-to-data-subject-rights-dsr-requests-for-common-data-service-for-apps-customer-data"></a>Svar på DSR-forespørsler om kundedata i Common Data Service for Apps

## <a name="introduction-to-dsr-requests"></a>Innføring i DSR-forespørsler
EUs personvernforordning (GDPR) gir en bruker (kalt «*den registrerte*» i forordningen) rett til å behandle personopplysningene som en arbeidsgiver eller et annet byrå eller organisasjon («*datakontrollør*» eller bare «*kontrollør*») har samlet inn. Personopplysninger er definert svært bredt under GDPR som alle data som er knyttet til en identifisert eller identifiserbar person. GDPR gir dataemner rett til å gjøre følgende, slik det gjelder deres personopplysninger:

* Få kopier
* Be om rettelser
* Begrense behandling
* Slette den
* Motta den i elektronisk format, slik at den kan flyttes til en annen kontrollør

En formell forespørsel fra en bruker til en kontrollør om behandling av personopplysningene hans eller hennes, kalles en DSR-forespørsel.

Denne artikkelen beskriver hvordan Microsoft forbereder seg på GDPR og gir eksempler på hva du kan gjøre for å sikre at du samsvarer med GDPR-forskriftene når du bruker PowerApps, Microsoft Flow og Common Data Service (CDS) for Apps. Du finner ut hvordan du bruker Microsofts produkter, tjenester og administrative verktøy for å hjelpe kontrollørkundene med å finne, få tilgang til og behandle personopplysninger i Microsoft-skyen i forbindelse med DSR-forespørsler.

Følgende handlinger er dekket i denne artikkelen:

* **Finne** – Bruk søke- og oppdagelsesverktøy til enklere å finne kundedata som kan danne grunnlaget for en DSR-forespørsel. Når potensielt relevante dokumenter er samlet inn, kan du utføre en eller flere av følgende DSR-handlinger, for å svare på forespørselen. Eventuelt kan du avgjøre at forespørselen ikke oppfyller organisasjonens retningslinjer for å svare på DSR-forespørsler.

* **Få tilgang til** – Hent personopplysninger som ligger i Microsoft-skyen, og lag eventuelt en kopi av dataene til brukeren.

* **Korrigere** – Gjør eventuelle endringer eller implementer andre forespurte handlinger i personopplysningene.

* **Begrense** – Begrense behandlingen av personopplysninger, enten ved å fjerne lisenser for ulike nettbaserte tjenester eller ved å slå av de ønskede tjenestene der det er mulig. Du kan også fjerne data fra Microsoft-skyen og beholde dem lokalt eller på en annen plassering.

* **Slette** – Fjern personopplysninger som ligger i Microsoft-skyen, permanent.

* **Eksportere** – Lag en elektronisk kopi (i maskinlesbart format) av personopplysningene til brukeren.

## <a name="cds-for-apps-customer-data"></a>CDS for kundedata for apper

> [!IMPORTANT]
> Gjelder for både CDS for Apps og den forrige versjonen av Common Data Service

CDS for Apps og den forrige versjonen av Common Data Service (CDS) har separate prosesser for samhandling med personopplysninger.

Du kan identifisere hvilken type CDS-miljø du har, ved å logge på [PowerApps](https://web.powerapps.com) og følge disse trinnene:

1. I rullegardinlisten **Miljø** velger du miljø.
2. I navigasjonsruten klikker eller trykker du **Data**, og klikker eller trykker **enheter**.

    Miljøet ditt er CDS for Apps hvis du ser følgende enheter oppført:

    ![Liste over PowerApps-enheter](./media/common-data-service-gdpr-dsr-guide/powerapps-entities-list.png)

    Miljøet ditt er den forrige versjonen av CDS hvis du ser følgende enheter oppført:

    ![Liste over eldre PowerApps-enheter](./media/common-data-service-gdpr-dsr-guide/powerapps-legacy-entities-list.png)

Når du finner ut hvilken type CDS-miljø du har, kan du følge trinnene i avsnittene nedenfor for å identifisere personlige data.

> [!NOTE]
> Du kan ha noen miljøer i CDS for Apps og andre i forrige versjon av CDS, så du må gjenta prosessene som er beskrevet nedenfor, for hvert miljø i organisasjonen.

## <a name="user-personal-data-in-cds-for-apps"></a>Bruk personlige data i CDS for apper

### <a name="prerequisites"></a>Forutsetninger
Du må opprette brukere i administrasjonssenteret for Office 365 og tilordne dem en riktig brukerlisens og sikkerhetsrolle før de kan få tilgang til og bruke CDS for Apps.

Standard personopplysninger for brukere (for eksempel brukernavn, bruker-ID, telefon, e-post og adresse) oppbevares og vedlikeholdes i administrasjonssenteret for Office 365. Systemadministratorer kan bare oppdaterer disse personopplysningene i administrasjonssenteret for Office 365, og dataene synkroniseres da automatisk til CDS for Apps-systembrukerenheten i alle miljøer. Systemadministratorer kan også opprette egendefinerte attributter for å registrere ytterligere personopplysninger for brukere i brukerenheten for CDS for Apps-systemet, og deretter manuelt vedlikeholde og administrere disse attributtene.

For å unngå avbrudd på forretningsbruksområder som kan være viktige for organisasjonens drift fjernes ikke oppføringen til brukeren automatisk fra brukerenheten i CDS for Apps-systemet når den brukeren slettes fra administrasjonssenteret for Office 365. Brukerens status er satt til Deaktivert i CDS for Apps, men en systemadministrator i CDS for Apps må finne og fjerne brukerens personopplysninger fra CDS for Apps i programmet.

Det er bare globale administratorer i Office 365 og CDS som kan utføre handlingene under Finn, Korriger, Eksporter og Slett nedenfor.

### <a name="discover"></a>Discover
Systemansvarlige kan opprette flere CDS for Apps-instanser. Disse instansene kan brukes til utprøving, utvikling eller produksjon. Hver av disse instansene har en kopi av systembrukerenheten med eventuelle egendefinerte attributter som kan ha blitt lagt til av systemansvarlig, samt personopplysninger for brukere synkronisert fra administrasjonssenteret for Office 365.

Systemansvarlige kan finne en liste over alle CDS for Apps-instanser ved å gå til administrasjonssenteret for Dynamics 365 fra administrasjonssenteret for PowerApps.

Fra [administrasjonssenteret for PowerApps](https://admin.powerapps.com/) gjør du følgende:

1. I navigasjonsruten klikker eller trykker du på **Miljøer**, og velger deretter et miljø fra listen.

3.  Klikk eller trykk på **administrasjonssenteret for Dynamics 365**.

    ![Miljødetaljer i PowerApps](./media/common-data-service-gdpr-dsr-guide/powerapps-environment-details.png)

    En liste over alle instanser vises.

    ![Instansvelger i PowerApps](./media/common-data-service-gdpr-dsr-guide/powerapps-instance-picker.png)

Du kan finne personlige data fra CDS for Apps-brukere i følgende ressurser:

|Ressurs | Formål | Nettstedstilgang | Programmatisk tilgang
| --- | --- | --- | ---
| Enhetsoppføring | Det er kjent som brukerenhetssystemet, og lagrer en brukers personlige data. | [Administrasjonssenteret for PowerApps](https://admin.powerapps.com) | Gjennom [Web-API](https://docs.microsoft.com/en-us/dynamics365/customer-engagement/developer/webapi/update-delete-entities-using-web-api#basic-update)
| Revisjonshistorikk | Gir kunder tillatelse til å identifisere ressurser som brukere opprettet, hatt fikk tilgang til, endret eller slettet på et enhetsnivå. | [Administrasjonssenteret for PowerApps](https://admin.powerapps.com) | Gjennom [Web-API](https://docs.microsoft.com/en-us/dynamics365/customer-engagement/developer/webapi/update-delete-entities-using-web-api#basic-update)

#### <a name="user"></a>Bruker
Brukers personlige data er lagret i Azure Active Directory-og synkroniseres automatisk med alle CDS for Apps-miljøer. Systemansvarlige kan ikke oppdatere disse personopplysningene data direkte i CDS for Apps mens brukeren er aktiv&mdash;de må oppdatere opplysningene direkte i administrasjonssenteret for Office 365. Systemansvarlige kan legge til personlige data (for eksempel egendefinerte attributter) direkte til CDS for Apps, men de må behandle disse dataene manuelt.

Hvis du vil finne en bruker og hans eller hennes personlige data, kan du gå til [PowerApps-administrasjonssenteret](https://admin.powerapps.com/) og gjøre følgende:

1. I navigasjonsruten klikker eller trykker du på **Miljøer**, og velger deretter et miljø fra listen.

2. Klikk eller trykk **administrasjonssenteret for Dynamics 365 Administration Center**, velg et miljø fra listen, og klikk eller trykk deretter på **Åpne**.

3. Gå til **Settings (Innstillinger)** > **Security (Sikkerhet)** > **Users (Brukere)**.

4. Angi navnet på brukeren i **Søk**-boksen, og deretter klikker eller trykker du på **Søk**.

5. Hvis du vil vise brukerens personlige data, dobbeltklikker eller dobbelttrykker du på brukerens navn.

    ![Brukerskjema i PowerApps](./media/common-data-service-gdpr-dsr-guide/powerapps-user-form.png)

#### <a name="audit-history"></a>Revisjonshistorikk
Når [revisjonssporing er aktivert](https://docs.microsoft.com/dynamics365/customer-engagement/admin/audit-data-user-activity) for en entitet i CDS for Apps, blir personopplysninger for brukere logget i revisjonshistorikken sammen med handlingene som brukeren utfører.

### <a name="rectify"></a>Korriger
Hvis en bruker ber deg om å korrigere personopplysningene i organisasjonens data, må du og organisasjonen avgjøre om forespørselen skal utføres. Korrigering av data kan omfatte redigering eller fjerning av personopplysninger fra et dokument eller annet element.

Du kan bruke Azure Active Directory til å administrere identitetene (personopplysninger) for brukerne dine i CDS for Apps. Bedriftskunder kan administrere DSR-forespørsler om korrigering, ved å bruke begrensede redigeringsfunksjoner i en gitt Microsoft-tjeneste. Som databehandler tilbyr ikke Microsoft muligheten til å korrigere systemgenererte logger, ettersom disse gjenspeiler faktiske aktiviteter og regnes som en historisk oversikt over hendelser i Microsofts tjenester. Se [GDPR: Data Subject Requests (DSRs)](https://servicetrust.microsoft.com/ViewPage/GDPRDSR) (GDPR: DRS-forespørsler) for mer informasjon.

Når en brukeroppføring er slettet fra Azure Active Directory, kan systemansvarlige deretter fjerne eventuelle gjenværende personopplysninger relatert til brukeren (for eksempel egendefinerte attributter) fra alle instanser.  

### <a name="export"></a>Eksporter

#### <a name="system-user"></a>Systembruker
Du kan eksportere en brukers personlige data lagret i systemet for brukeridentitet til Excel fra brukerlisten i administrasjonssenteret.

Fra [administrasjonssenteret for PowerApps](https://admin.powerapps.com/) gjør du følgende:

1. I navigasjonsruten klikker eller trykker du på **Miljøer**, og velger deretter et miljø fra listen.

2. Klikk eller trykk **administrasjonssenteret for Dynamics 365 Administration Center**, velg et miljø fra listen, og klikk eller trykk deretter på **Åpne**.

3. Gå til **Innstillinger** > **Sikkerhet**, og velg deretter **Visning av aktiverte brukere**.

4. Klikk **Eksporter til Excel**.

#### <a name="audit-history"></a>Revisjonshistorikk
Du kan ta skjermbilder av revisjonslogg fra administrasjonssenteret.

Fra [administrasjonssenteret for PowerApps](https://admin.powerapps.com/) gjør du følgende:

1. I navigasjonsruten klikker eller trykker du på **Miljøer**, og velger deretter et miljø fra listen.

2. Klikk eller trykk **administrasjonssenteret for Dynamics 365 Administration Center**, velg et miljø fra listen, og klikk eller trykk deretter på **Åpne**.

3. Gå til **Innstillinger** > **Revisjon**, og velg deretter **Revisjonshistorikkvisning**.

    ![Revisjonshistorikkmeny i PowerApps](./media/common-data-service-gdpr-dsr-guide/powerapps-audit-history-menu.png)

4. Finn brukeroppføring for sporing av endringer, og trykk deretter Alt + PrtScn for å ta skjermbildet.

    ![Revisjonshistorikkdetaljer i PowerApps](./media/common-data-service-gdpr-dsr-guide/powerapps-audit-history-details.png)

5. Lagre skjermbildet til en fil, som du deretter kan sende til DSR-anmoderen.

### <a name="delete"></a>Slett

#### <a name="user"></a>Bruker
For å unngå avbrudd på forretningsbruksområder som kan være viktige for organisasjonens drift fjernes ikke oppføringen til brukeren automatisk fra brukerenheten i CDS for Apps-systemet når den brukeren slettes fra administrasjonssenteret for Office 365. Brukerens status er satt til Deaktivert i CDS for Apps, men en systemadministrator i CDS for Apps må finne og fjerne brukerens personopplysninger fra CDS for Apps i programmet.

#### <a name="remove-a-users-personal-data-from-the-users-summary-page"></a>Fjern en brukers personlige data fra brukerens sammendragsside
Når oppføringen for en bruker er slettet fra Azure Active Directory, vises følgende melding på brukerens sammendragsside.

*This user’s information is no longer managed by Office 365. (Informasjonen for denne brukeren administreres ikke lenger av Office 365.) You can update this record to respond to DSR requests by removing or replacing all personal data associated with this user. (Du kan oppdatere denne oppføringen for å håndtere DSR-forespørsler ved å fjerne eller erstatte alle personopplysninger tilknyttet denne brukeren.)*

Fra [administrasjonssenteret for PowerApps](https://admin.powerapps.com/) gjør du følgende:

1. I navigasjonsruten klikker eller trykker du på **Miljøer**, og velger deretter et miljø fra listen.

2. Klikk eller trykk **administrasjonssenteret for Dynamics 365 Administration Center**, velg et miljø fra listen, og klikk eller trykk deretter på **Åpne**.

3. Gå til **Innstillinger** > **Sikkerhet** > **Brukere**, og velg deretter **Visning av deaktiverte brukere**.

4. Angi navnet på brukeren i **Søk**-boksen, og deretter klikker eller trykker du på **Søk**.

9. Dobbeltklikk på brukernavnet i søkeresultatlisten.

10. På brukerens sammendragssider fjerner du alle personlige data, og klikker eller trykker på **Lagre**.

#### <a name="remove-a-users-personal-data-by-using-excel"></a>Fjern en brukers personlige data ved hjelp av Excel
Fra [administrasjonssenteret for PowerApps](https://admin.powerapps.com/) gjør du følgende:

1. I navigasjonsruten klikker eller trykker du på **Miljøer**, og velger deretter et miljø fra listen.

2. Klikk eller trykk **administrasjonssenteret for Dynamics 365 Administration Center**, velg et miljø fra listen, og klikk eller trykk deretter på **Åpne**.

3. Gå til **Innstillinger** > **Sikkerhet** > **Brukere**, og velg deretter **Visning av deaktiverte brukere**.

4. Opprett og Last ned en Excel-malfil fra brukerens personlige data. Hvis du vil ha trinnvise instruksjoner, se [Opprett en ny Excel-mal](https://docs.microsoft.com/en-us/dynamics365/customer-engagement/admin/analyze-your-data-with-excel-templates#create-a-new-excel-template).

8. Åpne den nedlastede filen for Excel-malen, fjern brukerens personlige data og lagre deretter filen.

9. Gå tilbake til visningssiden **Disabled Users (Deaktiverte brukere)**, og klikk eller trykk på **Import Data (Importer data)**.

10. Velg Excel-malfil i **Last opp datafil**-dialogboksen og gjør alle nødvendige endringer i **Kartfelt**-vinduet.

12. Klikk eller trykk **Neste**, og klikk eller trykk **Send**.

#### <a name="remove-audit-history-from-the-audit-summary-view-page"></a>Fjern revisjonshistorikk fra siden Audit Summary View (Sammendragsvisning for sporing av endringer)
Fra [administrasjonssenteret for PowerApps](https://admin.powerapps.com/) gjør du følgende:

1. I navigasjonsruten klikker eller trykker du på **Miljøer**, og velger deretter et miljø fra listen.

2. Klikk eller trykk **administrasjonssenteret for Dynamics 365 Administration Center**, velg et miljø fra listen, og klikk eller trykk deretter på **Åpne**.

3. Gå til **Innstillinger** > **Revisjon**, og velg deretter **Revisjonshistorikkvisning**.

4. Finn brukerens endringslogg, klikk eller trykk på avmerkingsboksen ved siden av radene, og klikk eller trykk på **Slett endringshistorikk**.

## <a name="personal-data-stored-in-databases-of-cds-for-apps"></a>Personlige data som er lagret i databasene for CDS for Apps

### <a name="prerequisites"></a>Forutsetninger
Det kan hende du lagrer personopplysninger fra enkeltpersoner (for eksempel dine egne kunder) i CDS for Apps-enhetene dine.  

CDS-systemansvarlige er ansvarlig for å opprettholde en oversikt over hvor personlige data lagres i ulike enheter for hver person slik at han eller hun kan finne disse dataene som svar på eventuelle DSR-forespørsler.  

Personopplysninger kan deretter eksporteres, korrigeres eller slettes i en enhet ved hjelp av funksjonene i produktet.  

### <a name="discover"></a>Discover
Når CDS-administrator mottar en DSR-forespørsel fra en enkeltperson, må de identifisere hvilke miljøer/CDS-instanser som inneholder personopplysninger for den personen. Personlige data lagres vanligvis i viktige enheter (for eksempel konto, kontakt, kundeemne, salgsmulighet osv.), men det er ditt ansvar å utarbeide retningslinjer og prosedyrer for å opprettholde en oversikt over der du lagrer personlige data for hver person slik at du er forberedt på å svare på forespørsler om DSR.

Ved hjelp av en innholdsliste kan CDS-systemansvarlige konfigurere søkeenhetene og feltene og deretter få tilgang til CDS for apps-miljø for å oppdage personlige data. Hvis du vil ha mer informasjon, se [Konfigurer relevanssøk](https://go.microsoft.com/fwlink/?linkid=872506).

Fra [administrasjonssenteret for PowerApps](https://admin.powerapps.com/) gjør du følgende:

1. I navigasjonsruten klikker eller trykker du på **Miljøer**, og velger deretter et miljø fra listen.

2. Klikk eller trykk på **administrasjonssenteret for Dynamics 365**, velg et miljø fra listen, klikk eller trykk på søk-knappen, og deretter klikker eller trykker du på **Relevanssøk**.

    ![Meny for relevanssøk i PowerApps](./media/common-data-service-gdpr-dsr-guide/powerapps-relevance-search-menu.png)

3. Angi personopplysningene for brukeren i søkeboksen. og deretter klikker eller trykker du på **Søk**.

    ![Resultater av relevanssøk i PowerApps](./media/common-data-service-gdpr-dsr-guide/powerapps-relevance-search-results.png)

### <a name="rectify"></a>Korriger
Systemansvarlige for CDS kan oppdatere enkeltpersoners personopplysninger ved hjelp av listen over resultater fra relevanssøket. Personlige data for en enkeltperson kan imidlertid også være lagret i andre egendefinerte enheter. Systemansvarlige for CDS har ansvaret for å opprettholde en oversikt over disse egendefinerte enhetene og gjøre dn aktuelle oppdateringene i personopplysningene.

Gjør følgende fra resultatene av relevanssøket:

1. Klikk eller trykk på et element som inneholder personens personlige data.

2. Oppdater den enkeltes personlige data der det er nødvendig, og klikk eller trykk på **Lagre**.

    ![PowerApps-kontodetaljer](./media/common-data-service-gdpr-dsr-guide/powerapps-account-details.png)

### <a name="export"></a>Eksporter
Du kan ta et skjermbilde av dataene og dele den med DSR-anmoderen.

Fra [administrasjonssenteret for PowerApps](https://admin.powerapps.com/) gjør du følgende:

1. I navigasjonsruten klikker eller trykker du på **Miljøer**, og velger deretter et miljø fra listen.

2. Klikk eller trykk på **administrasjonssenteret for Dynamics 365**, velg et miljø fra listen, klikk eller trykk på søk-knappen, og deretter klikker eller trykker du på **Relevanssøk**.

    ![Meny for relevanssøk i PowerApps](./media/common-data-service-gdpr-dsr-guide/powerapps-relevance-search-menu.png)

3. Angi personopplysningene for brukeren i søkeboksen. og deretter klikker eller trykker du på **Søk**.

    ![Resultater av relevanssøk i PowerApps](./media/common-data-service-gdpr-dsr-guide/powerapps-relevance-search-results.png)

4. Dobbeltklikk elementet i listen over søkeresultater.

5. Trykk på Alt-PrtScn for å ta skjermbildet.

6. Lagre skjermbildet til en fil, som du deretter kan sende til DSR-anmoderen.

### <a name="delete"></a>Slett
CDS-systemadministratorer kan slette en brukers personopplysninger fra oppføringer der dataene er lagret.  CDS-administratoren kan velge å enten slette oppføringen der personopplysningene er lagret, eller fjerne innholdet i personopplysningene fra oppføringen.  

> [!NOTE]
> CDS-administratorer kan tilpasse et miljø for å hindre at en oppføring blir slettet fra en enhet. Hvis miljøet er konfigurert på denne måten, må du fjerne innholdet i personopplysningene fra oppføringen i stedet for å slette selve oppføringen.

Gjør følgende fra resultatene av relevanssøket:

1. Klikk eller trykk på et element som inneholder personens personlige data.

2. På båndet klikker eller trykker du på **Slett**. (Merk at **Slett** er deaktivert hvis oppføringen ikke kan slettes).

    ![Kontosletting i PowerApps](./media/common-data-service-gdpr-dsr-guide/powerapps-account-delete.png)

## <a name="personal-data-stored-in-databases-of-the-previous-version-of-cds"></a>Personopplysninger lagret i databaser for den forrige versjonen av CDS

### <a name="prerequisites"></a>Forutsetninger
Det kan hende du lagrer personopplysninger fra enkeltpersoner (for eksempel dine egne kunder) i CDS-enhetene dine.  

CDS-systemansvarlige er ansvarlig for å opprettholde en oversikt over hvor personlige data lagres i ulike enheter for hver person slik at han eller hun kan finne disse dataene som svar på eventuelle DSR-forespørsler.  

Personopplysninger kan deretter eksporteres, korrigeres eller slettes i en enhet ved hjelp av funksjonene i produktet.  

### <a name="discover"></a>Discover
Når CDS-administratorer mottar en DSR-forespørsel fra en enkeltperson, må de identifisere hvilke miljøer/CDS-instanser som inneholder personopplysninger for den personen. Personlige data lagres vanligvis i viktige enheter (for eksempel konto, kontakt, kundeemne, salgsmulighet osv.), men det er ditt ansvar å utarbeide retningslinjer og prosedyrer for å opprettholde en oversikt over der du lagrer personlige data for hver person slik at du er forberedt på å svare på forespørsler om DSR.

Du kan finne personlige data fra brukere av den forrige versjonen av CDS i følgende ressurser:

|Ressurs | Formål | Nettstedstilgang |  Programmatisk tilgang
| --- | --- | --- | ---
|Enhetsoppføringer | Registrerer forretningstransaksjoner i de respektive forretningsenhetene. | [PowerApps](https://web.powerapps.com) |      Nei

#### <a name="entity-records"></a>Enhetsoppføringer
Enkeltpersonens personopplysninger kan lagres i en hvilken som helst forretningsenhet.

Denne versjonen av CDS inneholder sitt eget databaseskjema og infrastruktur. Den har sine egne enheter, og du administrerer disse enhetene i [PowerApps](http://web.powerapps.com/).

Gjør følgende for å se listen over enhetene dine:

1. I rullegardinlisten **Miljø** velger du miljø.

2. I navigasjonsruten klikker eller trykker du **Data**, og klikker eller trykker **enheter**.

    ![Eldre PowerApps-enheter](./media/common-data-service-gdpr-dsr-guide/powerapps-legacy-entities.png)

3. Fra listen over enheter klikker eller trykker du på en enhet (for eksempel kontoenheten), som vist nedenfor.

    ![Detaljliste over eldre PowerApps-enheter](./media/common-data-service-gdpr-dsr-guide/powerapps-legacy-entities-details-list.png)

4. Klikk eller trykk på **Data**-kategorien. En liste over oppføringer for enheten vises.

    ![Eldre kontodata for PowerApps](./media/common-data-service-gdpr-dsr-guide/powerapps-legacy-account-data.png)

5. Klikk eller trykk på **Eksporter data**.

6. Når eksporten er fullført, klikker eller trykker du på **Åpne i Excel**, og klikk eller trykk på **Aktiver redigering**.

7. Klikk eller trykk på søk-knappen, skriv inn enkeltpersonens personlige data i søkeboksen, og klikk eller trykk på **Søk**.

8. Bruk lagerlisten, gjenta trinnene ovenfor for hver av forretningsenhetene for å finne alle de individuelle personopplysningene.

### <a name="rectify"></a>Korriger
Hvis en bruker ber deg om å korrigere personopplysningene i organisasjonens data, må du og organisasjonen avgjøre om forespørselen skal utføres. Korrigering av data kan omfatte redigering eller fjerning av personopplysninger fra et dokument eller annet element.

Du kan bruke Azure Active Directory for å administrere identiteter (personlige data) i den forrige versjonen av CDS. Bedriftskunder kan administrere DSR-forespørsler om korrigering, ved å bruke begrensede redigeringsfunksjoner i en gitt Microsoft-tjeneste. Som databehandler tilbyr ikke Microsoft muligheten til å korrigere systemgenererte logger, ettersom disse gjenspeiler faktiske aktiviteter og regnes som en historisk oversikt over hendelser i Microsofts tjenester. Se [GDPR: Data Subject Requests (DSRs)](https://servicetrust.microsoft.com/ViewPage/GDPRDSR) (GDPR: DRS-forespørsler) for mer informasjon.

Du kan korrigere personopplysninger som ligger i CDS-miljøet ved å eksportere enhetsdataene til et Excel-regneark, oppdatere dem og deretter importere oppdateringene tilbake til databasen.

CDS-systemadministratorne har ansvaret for å identifisere alle enheter som inneholder personopplysninger for en enkeltperson, og for å gjenta følgende trinn for hver av enhetene.

Fra [PowerApps](http://web.powerapps.com/) gjør du følgende:

1. I navigasjonsruten klikker eller trykker du **Data**, og klikker eller trykker **enheter**.

    ![Eldre PowerApps-enheter](./media/common-data-service-gdpr-dsr-guide/powerapps-legacy-entities.png)

2. Fra listen over enheter klikker eller trykker du på en enhet (for eksempel kontoenheten), som vist nedenfor.

    ![Detaljliste over eldre PowerApps-enheter](./media/common-data-service-gdpr-dsr-guide/powerapps-legacy-entities-details-list.png)

3. Klikk eller trykk på **Data**-kategorien. En liste over oppføringer for enheten vises.

    ![Eldre kontodata for PowerApps](./media/common-data-service-gdpr-dsr-guide/powerapps-legacy-account-data.png)

4. Klikk eller trykk på **Eksporter data**.

5. Når eksporten er fullført, klikker eller trykker du på **Åpne i Excel**, og klikk eller trykk på **Aktiver redigering**.

6. På menylinjen klikker eller trykker du på **Fil**, klikk eller trykk på **Lagre som**, og velg deretter en plassering der du vil lagre filen.

7. Utfør de nødvendige oppdateringene i personopplysningene og lagre regnearket.

10. I PowerApps går du tilbake til **Data**-kategorien av enheten, og klikker eller trykker på **Importer data**.

11. Klikk på **Søk**, og deretter velger og åpner du Excel-regnearket som du nettopp har oppdatert.

12. Klikk på **Importer**.

### <a name="export"></a>Eksporter
Du kan eksportere personopplysninger fra hver enhet til et Excel-regneark og vise det.

Fra [PowerApps](http://web.powerapps.com/) gjør du følgende:

1. I navigasjonsruten klikker eller trykker du **Data**, og klikker eller trykker **enheter**.

    ![Eldre PowerApps-enheter](./media/common-data-service-gdpr-dsr-guide/powerapps-legacy-entities.png)

2. Fra listen over enheter klikker eller trykker du på enheten som du vil eksportere og vise (for eksempel kontoenheten), som vist nedenfor.

    ![Detaljliste over eldre PowerApps-enheter](./media/common-data-service-gdpr-dsr-guide/powerapps-legacy-entities-details-list.png)

3. Klikk eller trykk på **Data**-kategorien. En liste over oppføringer for enheten vises.

    ![Eldre kontodata for PowerApps](./media/common-data-service-gdpr-dsr-guide/powerapps-legacy-account-data.png)

4. Klikk eller trykk på **Eksporter data**.

    Eksportoperasjonen kjøres i bakgrunnen, og du blir varslet når den er fullført.

5. Du viser de eksporterte dataene ved å klikke eller trykke på **Open in Excel (Åpne i Excel)**.

### <a name="delete"></a>Slett
Du kan slette personopplysninger som er lagret i enheter, ved å bruke funksjonen for eksport/import av data.

CDS-systemadministratorne har ansvaret for å identifisere alle enheter som inneholder personopplysninger for en enkeltperson, og for å gjenta følgende trinn for hver av enhetene.

Fra [PowerApps](http://web.powerapps.com/) gjør du følgende:

1. I navigasjonsruten klikker eller trykker du **Data**, og klikker eller trykker **enheter**.

    ![Eldre PowerApps-enheter](./media/common-data-service-gdpr-dsr-guide/powerapps-legacy-entities.png)

2. Fra listen over enheter klikker eller trykker du på enheten som du ønsker å fjerne personlige data fra (for eksempel kontoenheten), som vist nedenfor.

    ![Detaljliste over eldre PowerApps-enheter](./media/common-data-service-gdpr-dsr-guide/powerapps-legacy-entities-details-list.png)

3. Klikk eller trykk på **Data**-kategorien. En liste over oppføringer for enheten vises.

    ![Eldre kontodata for PowerApps](./media/common-data-service-gdpr-dsr-guide/powerapps-legacy-account-data.png)

4. Klikk eller trykk på **Eksporter data**.

5. Når eksporten er fullført, klikker eller trykker du på **Åpne i Excel**, og klikk eller trykk på **Aktiver redigering**.

6. På menylinjen klikker eller trykker du på **Fil**, klikk eller trykk på **Lagre som**, og velg deretter en plassering der du vil lagre filen.

7. Slett rader som inneholder personlige data som du vil fjerne fra enheten og lagre regnearket.

10. I PowerApps går du tilbake til **Data**-kategorien av enheten, og klikker eller trykker på **Importer data**.

11. Klikk på **Søk**, og deretter velger og åpner du Excel-regnearket som du nettopp har oppdatert.

12. Klikk på **Importer**.