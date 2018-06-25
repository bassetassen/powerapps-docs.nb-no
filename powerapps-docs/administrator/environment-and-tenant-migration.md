---
title: Å overføre apper mellom miljøer og tenanter | Microsoft Docs
description: Gjennomgang av hvordan du overfører PowerApps-apper mellom miljøer og tenanter
author: jamesol-msft
manager: kfile
ms-topic: conceptual
ms.service: powerapps
ms.component: pa-admin
ms.topic: conceptual
ms.author: jamesol
ms.openlocfilehash: 3a064bdb3f75bf45047e3ae0ff465fde1d2b66fa
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/04/2018
ms.locfileid: "34167841"
---
# <a name="environment-and-tenant-app-migration-through-packaging"></a>Å overføre apper mellom miljøer og tenanter gjennom pakking
Finn ut hvordan du overfører ressurser fra ett miljø til et annet med pakking. Disse miljøene kan være på samme tenant eller på forskjellige tenanter.

## <a name="the-scenario"></a>Scenarioet
Et vanlig scenario der du ønsker å overføre ressurser, er en situasjon der du har test- og utviklingsmiljøer, i tillegg til et produksjonsmiljø. Utviklere og testere har bred tilgang til appene i miljøene sine. Men når tiden er inne for å overføre en ny app til produksjon, har det miljøet streng kontroll over tillatelsene for å oppdatere og endre den.

Et annet scenario er der hver kunde har sine egne miljøer og data. Når det legges til en ny kunde, opprettes det et nytt miljø for dem, og du ville ha overført apper over til miljøene.

## <a name="which-resources-can-i-migrate-through-packaging"></a>Hvilke ressurser kan jeg overføre gjennom pakking?
Når du eksporterer en app, eksporteres også den avhengige ressursen for appen i pakken.  Bare et delsett av alle mulige ressurstyper støttes innledningsvis, som du kan se av tabellen nedenfor.

| Ressurstype | Støttes | Importalternativer |
| --- | --- | --- |
| App |Ja |Det finnes to alternativer for å importere en app i et miljø: <ol><li><b>Opprett ny</b> – appen opprettes som en ny app i miljøet hvor pakken importeres.</li> <li><b>Oppdatering</b> – appen eller flyten finnes allerede i miljøet og blir oppdatert når du importerer denne pakken.</li></ol> |
| Flyt |Ja |Det finnes to alternativer for å importere en flyt i et miljø: <ol><li><b>Opprett ny</b> – flyten opprettes som en ny flyt i miljøet hvor pakken importeres.</li> <li><b>Oppdatering</b> – flyten eller flyten finnes allerede i miljøet og blir oppdatert når du importerer denne pakken.</li></ol> <b>Obs! </b>Alle ressurser som flyten er avhengig av inkluderes også i app-pakken som eksporteres, og den må konfigureres med pakken som importeres. |
| Egendefinerte koblinger |Nei |Hvis en app er avhengig av en egendefinert kobling, <b>støtter vi for</b> øyeblikket ikke eksportering av koblingen som en del av pakken. <p></p> Hvis du har en app som er avhengig av en egendefinert tilkobling, er det eneste alternativet å opprette koblingen på nytt og oppdatere den i målmiljøet, og velge koblingen når du importerer pakken. |
| Tilkoblinger |Nei |Hvis en app avhenger av en tilkobling (for eksempel en SQL-tilkobling med legitimasjon), støtter vi for øyeblikket ikke eksportering av tilkoblingen eller legitimasjonen som en del av pakken. <p></p> Hvis du har en app som er avhengig av en delt tilkobling (som SQL), er det eneste alternativet å opprette koblingen på nytt med gjeldende legitimasjon i målmiljøet, og velge tilkoblingen når du importerer pakken. |
| CDS-tilpassinger |Nei |Eksport av CDS-tilpassinger støttes ikke lenger som en del av pakking. Dette støttes nå gjennom å eksportere og importere standardløsningen for miljøet som beskrives i artikkelen nedenfor. |
| Gatewayer |Nei |Gatewayer støttes bare i standardmiljøer (og {tenantnavn} (fra forhåndsvisning) ), derfor støttes ikke eksportering/overføring. |

## <a name="how-do-i-get-access-to-packaging-for-my-app"></a>Hvordan får jeg tilgang til pakking for appen?
Muligheten for å eksportere en app er tilgjengelig for alle brukere med Kan redigere-tillatelser i appen.

Muligheten for å importere appen er tilgjengelig for alle brukere med tillatelsen Miljøoppretter i målmiljøet.

En bruker må ha en PowerApps-abonnement 2 eller prøveversjon av PowerApps-abonnement 2 for å eksportere eller importere apper.

> [!NOTE]
> Når pakking er i forhåndsvisning, kan en bruker med en gyldig PowerApps-lisens ta i bruk pakking for appene og miljøene.

## <a name="exporting-an-app"></a>Å eksportere en app
1. Klikk eller trykk på **Apper** i http://web.powerapps.com, velg ellipsen for appen du ønsker å overføre, og velg deretter **Eksport (forhåndsvisning)**.

    ![Å velge eksport](./media/environment-and-tenant-migration/select-export.png)
2. Når siden for eksportpakke åpnes, angir du navn og beskrivelse for pakken.

    ![Å se gjennom pakkedetaljene](./media/environment-and-tenant-migration/package-details.png)
3. I delen Å se gjennom pakkedetaljene kan du legge til kommentarer eller merknader, eller endre innstillingen for hvordan hver individuelle ressurs kan importeres i målmiljøet i løpet av importering av pakken.

    ![Å konfigurere pakkens innhold](./media/environment-and-tenant-migration/export-package-content.png)

4. Når du er ferdig, velger du **Eksport**, og pakkefilen begynner å laste ned i løpet av et par sekunder.

## <a name="importing-an-app"></a>Å importere en app
1. Klikk eller trykk på **Apps** i http://web.powerapps.com, og velg deretter **Importer pakke (forhåndsvisning)**.

    ![Å velge import](./media/environment-and-tenant-migration/select-import.png)
2. Velg **Last opp**, og velg app-pakkefilen du ønsker å importere.

    ![Å velge pakkefilen](./media/environment-and-tenant-migration/select-file.png)
3. Når pakken har blitt lastet opp, må du se gjennom pakkens innhold, og du må oppgi ytterligere informasjon om elementer som er merket med et rødt ikon. Dette gjør du ved velge skiftenøkkelikonet for hvert element og oppgi nødvendig informasjon.

    ![Å se gjennom pakkens innhold](./media/environment-and-tenant-migration/import-package-content.png)
4. Når du har oppgitt all den nødvendige informasjonen, velger du **Import**.

    ![Å oppdatere pakkens innhold](./media/environment-and-tenant-migration/import-package-content-dirty.png)
5. Når importen er fullført, blir du automatisk omdirigert til en side (lik den nedenfor) som gir en oversikt om importoperasjonen var vellykket.

    ![Å se gjennom importresultater](./media/environment-and-tenant-migration/import-results.png)

> [!NOTE]
>  Hvis du importerer en app og velger å **Oppdatere** en eksisterende app, lagres de nye endringene som et utkast i programmene.  Du må [publisere](http://powerapps.microsoft.com/tutorials/save-publish-app/#publish-an-app) disse endringene for at de skal være tilgjengelig for de andre brukerne av programmene.
>
>

## <a name="exporting-cds-customizations-and-model-driven-apps"></a>Å eksportere CDS-tilpassinger og modelldrevne apper
Eksport av enhet eller tilpassinger av alternativsett eller eventuelle modelldrevne apper som du har bygget inn https://web.powerapps.com, støttes ved å eksportere standardmiljøløsningen som følger:
> [!NOTE]
>  Hvis du vil finne ut mer om løsninger i PowerApps, kan du se [Innføring i løsninger](../developer/common-data-service/introduction-solutions.md).
>
>

1. Velg utformingsmodusen **Modelldrevet (forhåndsvisning)** i miljøet, i http://web.powerapps.com.

    ![Å velge modelldrevet utformingsmodus](./media/environment-and-tenant-migration/select-model-driven.png)

2. Velg **Avansert** i navigasjonsfeltet til venstre for å starte løsningsutforsker for miljøets standardløsning

    ![Å velge avansert](./media/environment-and-tenant-migration/select-advanced.png)

3. Velg **Eksporter løsning**, og fullfør de nødvendige trinnene.  En løsningspakkefil lastes ned innen et par sekunder.

    ![Å velge eksport](./media/environment-and-tenant-migration/select-export-solution.png)

## <a name="importing-cds-customization-and-model-driven-apps"></a>Å importere CDS-tilpassinger og modelldrevne apper
Hvis du vil importere en CDS-løsningspakke, må du dessverre foreta en manuell endring i opplevelsen, noe som vi jobber aktivt for å løse:

1. Velg utformingsmodusen **Modelldrevet (forhåndsvisning)** i miljøet, i http://web.powerapps.com.

    ![Å velge modelldrevet utformingsmodus](./media/environment-and-tenant-migration/select-model-driven.png)

2. Velg **Avansert** i navigasjonsfeltet til venstre for å starte løsningsutforsker for miljøets standardløsning.

    ![Å velge avansert](./media/environment-and-tenant-migration/select-advanced.png)

3. Kopier nettadressen fra nettleseren, gjør følgende endringer, og gå deretter til den nye nettadressen i nettleseren:

    * Gjeldende nettadressestruktur: https://{orguniquename}.crm.dynamics.com/tools/solution/edit.aspx?id={solutionname}

        ![Å redigere nettadresse](./media/environment-and-tenant-migration/edit-url.png)

    * Ny nettadressestruktur: https://{orguniquename}.crm.dynamics.com/tools/solution/SolutionImportWizard.aspx

        ![Å velge pakken](./media/environment-and-tenant-migration/select-package.png)

4. Velg CDS-løsningspakkefilen du vil importere, og fullfør veiviseren.

5. Hvis importen er vellykket, ser du følgende bekreftelsesdialogboks. Hvis du ønsker at endringene til løsningen skal være tilgjengelig for andre i miljøet, velger du **Publiser alle tilpassinger**

    ![Vellykket importering](./media/environment-and-tenant-migration/successful-import.png)
