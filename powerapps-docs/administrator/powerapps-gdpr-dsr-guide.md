---
title: DSR-veiledning for kundeopprettede data for PowerApps | Microsoft Docs
description: DSR-veiledning for kundeopprettede data for PowerApps
services: powerapps
suite: powerapps
documentationcenter: na
author: jamesol-msft
manager: kfile
editor: ''
tags: ''
ms-topic: article
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 04/17/2018
ms.author: jamesol
ms.openlocfilehash: 823c14d0677ef96c48a26e2488bac1c91bbea225
ms.sourcegitcommit: e3a2819c14ad67cc4ca6640b9064550d0f553d8f
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/20/2018
---
# <a name="responding-to-data-subject-rights-dsr-requests-for-powerapps-customer-data"></a>Svar på DSR-forespørsler om kundedata for PowerApps

## <a name="introduction-to-dsr-requests"></a>Innføring i DSR-forespørsler
Vi har laget denne dokumentasjonen for å hjelpe deg med å forberede deg på å implementere EUs personvernforordning (GDPR). Dokumentasjonen beskriver hva vi gjør for å forberede oss på EUs personvernforordning (GDPR). I tillegg gir den eksempler på hva du som Microsoft-bruker kan gjøre i dag for å sikre at du samsvarer med GDPR-forskriftene når du bruker PowerApps, Microsoft Flow og Common Data Service for Apps.

EUs personvernforordning (GDPR) gir en bruker (kalt «den registrerte» i forordningen) rett til å behandle personopplysningene som en arbeidsgiver eller et annet byrå eller organisasjon («datakontrollør» eller bare «kontrollør») har samlet inn. Personopplysninger er definert svært bredt under GDPR som alle data som er knyttet til en identifisert eller identifiserbar person. GDPR gir brukere bestemte rettigheter til personopplysningene sine. Disse rettighetene omfatter det å få kopier av personopplysninger, be om at de rettes, begrense behandlingen av dem, slette dem eller motta dem i elektronisk format slik at de kan flyttes til en annen kontrollør. En formell forespørsel fra en bruker til en kontrollør om behandling av personopplysningene sine, kalles en DSR-forespørsel.

Veiledningen beskriver hvordan du bruker Microsofts produkter, tjenester og administrative verktøy for å hjelpe kontrollørkundene våre med å finne og behandle personopplysninger i forbindelse med DSR-forespørsler. Dette omfatter spesifikt hvordan du finner, får tilgang til og behandler personopplysninger som befinner seg i Microsoft-skyen. Her er en rask oversikt over prosessene som er beskrevet i denne veiledningen:

1. **Finne** – Bruk søke- og oppdagelsesverktøy til enklere å finne kundedata som kan danne grunnlaget for en DSR-forespørsel. Når potensielt relevante dokumenter er samlet inn, kan du utføre en eller flere av DSR-handlingene som er beskrevet i trinnene nedenfor, for å svare på forespørselen. Eventuelt kan du avgjøre at forespørselen ikke oppfyller organisasjonens retningslinjer for å svare på DSR-forespørsler.

1. **Få tilgang til** – Hent personopplysninger som ligger i Microsoft-skyen, og lag eventuelt en kopi til brukeren.

1. **Korrigere** – Gjør eventuelle endringer eller implementer andre forespurte handlinger i personopplysningene.

1. **Begrense** – Begrense behandlingen av personopplysninger, enten ved å fjerne lisenser for ulike nettbaserte tjenester eller ved å slå av de ønskede tjenestene der det er mulig. Du kan også fjerne data fra Microsoft-skyen og beholde dem lokalt eller på en annen plassering.

5. **Slette** – Fjern personopplysninger som ligger i Microsoft-skyen, permanent.

6. **Eksportere** – Lag en elektronisk kopi (i maskinlesbart format) av personopplysningene til brukeren.

Hver del i denne veiledningen beskriver de tekniske prosedyrene som en datakontrollørorganisasjon kan utføre for å svare på en DSR-forespørsel om personopplysninger i Microsoft-skyen.

## <a name="discover"></a>Discover
Det første trinnet i å svare på en DSR-forespørsel er å finne personopplysningene som forespørselen dreier seg om. Dette første trinnet – å finne og se gjennom de aktuelle personopplysningene – hjelper deg med å finne ut om forespørselen oppfyller organisasjonens krav til å utføre eller avslå en DSR-forespørsel. Etter at du har funnet og sett gjennom de aktuelle personopplysningene, kan det for eksempel hende at du avgjør at forespørselen ikke oppfyller kravene til organisasjonen, ettersom den kan ha negativ innvirkning på andres rettigheter.

### <a name="step-1-find-personal-data-for-the-user-in-powerapps"></a>Trinn 1: Finn personopplysninger for brukeren i PowerApps
Nedenfor finner du et sammendrag av de ulike PowerApps-ressursene som inneholder personopplysninger for en bestemt bruker.

Ressurser som inneholder personopplysninger |    Formål
--- | ---
Miljø |   Et miljø er et område der du kan lagre, administrere og dele organisasjonens forretningsdata, apper og flyter. [Finn ut mer](https://go.microsoft.com/fwlink/?linkid=872239)
Miljøtillatelser | Brukere blir tilordnet miljøroller som skal gis utvikler- og administratorrettigheter i et miljø. [Finn ut mer](https://go.microsoft.com/fwlink/?linkid=872240)
Lerretsapp  | Plattformuavhengige forretningsapper som kan bygges fra et tomt lerret og kobles til over 200 datakilder. [Finn ut mer](https://go.microsoft.com/fwlink/?linkid=872241)
Lerretsapptillatelser  | Lerretsapper kan deles med brukere i en organisasjon. [Finn ut mer](https://go.microsoft.com/fwlink/?linkid=872242)
Tilkobling  | Brukes av koblinger og gir mulighet for tilkobling til API-er, systemer, databaser og så videre. [Finn ut mer](https://go.microsoft.com/fwlink/?linkid=872243)
Tilkoblingstillatelser  | Enkelte typer tilkoblinger kan deles med brukere i en organisasjon. [Finn ut mer](https://go.microsoft.com/fwlink/?linkid=872244)
Egendefinert kobling    | Egendefinerte koblinger som en bruker har opprettet for å gi tilgang til en datakilde som ikke tilbys via en av standardkoblingene for PowerApps. [Finn ut mer](https://go.microsoft.com/fwlink/?linkid=872245)
Tillatelser for egendefinerte koblinger    | Egendefinerte koblinger kan deles med brukere i en organisasjon. [Finn ut mer](https://go.microsoft.com/fwlink/?linkid=872246)
Bruker- og brukerappinnstillinger for PowerApps    | PowerApps lagrer flere brukerinnstillinger som brukes i PowerApps-kjøretiden og -portalen.
PowerApps-varslinger | PowerApps sender flere typer varslinger til brukere, blant annet når en app deles med dem og når en eksport i Common Data Service for Apps er fullført.
Gateway | Gatewayer er lokale datagatewayer som kan installeres av en bruker for rask og sikker overføring av data mellom PowerApps og en datakilde som ikke er i skyen. [Finn ut mer](https://go.microsoft.com/fwlink/?linkid=872247)
Gatewaytillatelser | Gatewayer kan deles med brukere i en organisasjon. [Finn ut mer](https://go.microsoft.com/fwlink/?linkid=872249)
Modelldrevne apper og tillatelser for modelldrevne apper  | Utforming av modelldrevne apper er en komponentfokusert tilnærming til apputvikling. Modelldrevne apper og deres tillatelser for brukertilgang lagres som data i databasen for Common Data Service for Apps.  [Finn ut mer](https://go.microsoft.com/fwlink/?linkid=872248)

I PowerApps kan du finne personopplysninger for en bestemt bruker på følgende måter:

- **Nettstedstilgang**: [PowerApps-området](https://web.powerapps.com), [PowerApps-administrasjonssenteret](https://admin.powerapps.com/) og [Office 365 Service Trust Portal](https://servicetrust.microsoft.com/)
- **PowerShell-tilgang**: PowerApps-cmdleter (for [apputviklere](https://go.microsoft.com/fwlink/?linkid=871448) og [administratorer](https://go.microsoft.com/fwlink/?linkid=871804)) og [cmdleter for lokale gatewayer](https://go.microsoft.com/fwlink/?linkid=872238)

Du finner detaljerte instruksjoner om hvordan du kan bruke disse metodene til å finne personopplysninger for en bestemt bruker for hver av disse ressurstypene, i [Export Customer Data in PowerApps]( https://go.microsoft.com/fwlink/?linkid=871888) (Eksporter kundedata i PowerApps).

Når du har funnet dataene, kan du utføre ønsket handling for å fullføre forespørselen fra brukeren.

### <a name="step-2-find-personal-data-for-the-user-in-microsoft-flow"></a>Trinn 2: Finn personopplysninger for brukeren i Microsoft Flow
PowerApps-lisenser inkluderer alltid Microsoft Flow-funksjoner. I tillegg til å være inkludert i PowerApps-lisensene er Microsoft Flow også tilgjengelig som en frittstående tjeneste.
Se Executing DSRs against Microsoft Flow Customer Data (Håndtering av DSR-forespørsler om kundedata for Microsoft Flow) for informasjon om hvordan du finner personopplysninger som er lagret av Microsoft Flow-tjenesten.

> [!IMPORTANT]
> Det anbefales at administratorer utfører dette trinnet for PowerApps-brukere.

### <a name="step-3-find-personal-data-for-the-user-in-instances-of-common-data-service-cds-for-apps"></a>Trinn 3: Finn personopplysninger for brukeren i instanser av Common Data Service (CDS) for Apps
Enkelte PowerApps-lisenser, deriblant PowerApps Community Plan, gir brukerne i organisasjonen muligheten til å opprette instanser av CDS for Apps samt til å opprette og utvikle apper på CDS for Apps. PowerApps Community Plan er en gratislisens som gir brukere muligheten til å prøve CDS for Apps i et enkeltmiljø. Se siden med [PowerApps-priser](https://powerapps.microsoft.com/pricing/) for informasjon om hvilke funksjoner som er inkludert i de ulike PowerApps-lisensene.

Se Executing DSRs against Common Data Service Customer Data (Håndtering av DSR-forespørsler om kundedata for Common Data Service) for informasjon om hvordan du finner personopplysninger som er lagret av CDS for Apps.

> [!IMPORTANT]
> Det anbefales at administratorer utfører dette trinnet for PowerApps-brukere.

## <a name="rectify"></a>Korriger
Hvis en bruker har bedt deg om å korrigere personopplysningene i organisasjonens data, må du og organisasjonen avgjøre om forespørselen skal utføres. Korrigering av data kan omfatte handlinger som blant annet redigering eller fjerning av personopplysninger fra et dokument eller annet element.

PowerApps har avhengigheter på Azure Active Directory for identitetsfastsettelse. Identiteter inneholder personopplysninger og kan derfor redigeres i Azure Active Directory. Bedriftskunder kan administrere DSR-forespørsler om korrigering, inkludert begrensede redigeringsfunksjoner i samsvar med en gitt Microsoft-tjeneste.  Som databehandler tilbyr ikke Microsoft muligheten til å korrigere systemgenererte logger, ettersom disse gjenspeiler faktiske aktiviteter og regnes som en historisk oversikt over hendelser i Microsofts tjenester. Du finner mer informasjon i GDPR-dokumentasjonen om DSR-forespørsler i Azure, som finnes i [Office 365 Service Trust Portal](https://servicetrust.microsoft.com/ViewPage/GDPRDSR).

## <a name="restrict"></a>Begrens
Brukere kan be om at du begrenser behandlingen av personopplysningene deres.  Vi tilbyr både eksisterende programmeringsgrensesnitt (API-er) og brukergrensesnitt.  Disse gir tenantadministratoren til bedriftskunder muligheten til å behandle DSR-forespørsler gjennom en kombinasjon av dataeksport og datasletting. En kunde kan be om følgende:

- Eksport av en elektronisk kopi av personopplysningene til brukeren, deriblant følgende:

    - kontoer
    - systemgenererte logger
    - tilknyttede logger
- Sletting av kontoen og tilknyttede data som er lagret i Microsoft-systemene.

## <a name="export"></a>Eksporter
«Retten til dataportabilitet» gir en bruker rett til å be om en kopi av personopplysningene sine i et elektronisk format (det vil si et «strukturert, velkjent, maskinlesbart og interoperabelt format») som kan overføres til en annen datakontrollør.

Se [Executing Export Data Subject Rights (DSR) Requests against PowerApps Customer Data](https://go.microsoft.com/fwlink/?linkid=871888) (Håndtering av DSR-forespørsler om sletting av kundedata for PowerApps) for mer informasjon.

## <a name="delete"></a>Slett
«Retten til sletting» ved å fjerne personopplysninger fra en organisasjons kundedata er en viktig beskyttelse i EUs personvernforordning (GDPR). Fjerning av personopplysninger omfatter systemgenererte logger, men ikke informasjon for revisjonslogger.

PowerApps gir brukere mulighet til å utvikle bransjespesifikke apper som er en viktig del av organisasjonens daglige drift. Når en bruker forlater organisasjonen, må du manuelt se gjennom data og ressurser vedkommende har opprettet, og avgjøre om du vil slette det. Andre kundedata blir automatisk slettet når brukerens konto blir slettet fra Azure Active Directory.

Se [Executing Delete Data Subject Rights (DSR) Requests against PowerApps Customer Data](https://go.microsoft.com/fwlink/?linkid=871883) (Håndtering av DSR-forespørsler om sletting av kundedata for PowerApps) for mer informasjon.
