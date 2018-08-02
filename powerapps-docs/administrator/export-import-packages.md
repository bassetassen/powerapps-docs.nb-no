---
title: Å eksportere og importere ressurser | Microsoft Docs
description: Finn ut hvordan du eksporterer og importerer ressurser i PowerApps
author: nimakms
manager: kvivek
ms.service: powerapps
ms.component: pa-admin
ms.topic: conceptual
ms.date: 07/28/2017
ms.author: nimak
ms.openlocfilehash: db5861b9f598045436ad0bf796f04ed1df4b8903
ms.sourcegitcommit: 2e7b621066cdc3e7be329d5213ecfee0b4223641
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 07/30/2018
ms.locfileid: "39349758"
---
# <a name="export-and-import-resources"></a>Å eksportere og importere ressurser
Hvis du har opprettet flere miljøer for å støtte utviklingen av databasen og appene dine, må du flytte endringer til ett miljø til et annet miljø. Du kan bruke **Eksporter ressurser** og **Importer ressurser** for å flytte ressursen mellom miljøer.

## <a name="why-use-multiple-environments"></a>Hvorfor distribuere til flere forskjellige miljøer?
Hvert miljø inneholder ressurser, for eksempel enheter, flyter og apper, som du oppretter eller endrer under utviklingsprosessen. 

Utvikling gjøres vanligvis i det samme miljøet som brukes av organisasjonens sluttbrukere. Dette miljøet kalles standardmiljøet. Det er relativt enkelt å behandle ressursendringer i det samme miljøet. Du validerer endringer for å være sikker på at alle kritiske forretningsprosesser og -programmer er funksjonelle, og deretter genererer du appen.

Noen ganger utføres utvikling og testing i separate miljøer, og endringene er flyttet til standardmiljøet når de er klare for bruk av sluttbrukere. Det finnes flere grunner til hvorfor du bør bruke separate miljøer. Du har for eksempel kanskje brukt et separat miljø når du først evaluerte systemet. Du kan eventuelt ønske å redusere risikoen som er involvert når endringer utføres for standardmiljøet. Separate miljøer gir isolasjon, fordi du foretar endringer i ett miljø som ikke er standardmiljøet. Du kan opprette et ekstra oppsamlingsmiljø, avhengig av risikoomfanget. I dette tilfellet har du et utviklingsmiljø, et oppsamlingsmiljø og et standardmiljø.

## <a name="moving-resource-changes"></a>Å flytte ressursendringer
Du flytter ressurser via separate eksport- og importprosesser, ved bruk av en pakkefil (.zip). Pakkefilen eksporteres, lagres lokalt, sendes til administratoren for målmiljøet, og importeres deretter til målmiljøet. Importprosessen følges ofte av valideringstesting for å garantere at ingen kritiske forretningsprosesser har blitt påvirket i negativ retning.

Funksjonaliteten til både ressursimport og -eksport er tilgjengelig i **Miljøer**-delen av administrasjonssenteret. Både eksport og import skjer innenfor et utvalgt miljø.

### <a name="export-resources"></a>Å eksportere ressurser
Eksportpakken inneholder alle endringer til **enheter og nedtrekksmenyer**. Vi arbeider for å aktivere eksporten av flere ressurstyper som apper, flyter, koblinger, roller og annet. Dette alternativet lar deg flytte innhold fra ett miljø til et annet miljø.

1. Klikk på **Miljøer** i [administrasjonssenteret](https://admin.powerapps.com) i venstre navigasjonsrute.
2. Å velge kildemiljøet.
3. Klikk på **Eksporter ressurser** øverst til høyre.
4. Velg ressursene du vil eksportere først:
   1. Velg fanen som samsvarer med ressurstypen du ønsker å velge, som **Enheter**.
   2. Velg alle ressurser under typen ved å merke av for overskriften, eller velg ressursene individuelt.
   3. Klikk på **Neste**.
5. Inkluder relaterte ressurser hvis det er aktuelt:
   1. Hvis vi oppdager noen relaterte ressurser, viser vi deg en forhåndsvalgt liste.
   2. Ekskluder alle relaterte ressurser ved å merke av for overskriften, eller fjern merket for ressursene enkeltvis.
   3. Klikk på **Neste**.
6. Legg til et **Navn** for den eksporterte pakken.
7. Du kan alternativt egendefinere oppstartshandlinger som skal utføres under import av ressurser:
   1. Klikk på **Importoppsett** for hver ressurs for å se en dialogboks.
   2. Velg oppsetthandlingen du ønsker å utføre som standard når denne pakken importeres
   3. Klikk på **Lagre**.
8. Klikk på **Eksporter**.
9. Når eksporten er fullført, lagrer du pakkefilen lokalt.

Du kan alternativt klikke på **Velg alle ressurser** på siden for ressursvalg for å inkludere alle ressursene til alle støttede typer i den endelige pakken og gå direkte til den siste eksportsiden.

### <a name="import-resources"></a>Å importere ressurser
Det første trinnet er å velge en pakkefil som ble eksportert fra kildemiljøet. Importprosessen validerer, analyserer og forsøker å importere pakken.

1. Klikk på **Miljøer** i [administrasjonssenteret](https://admin.powerapps.com) i navigasjonsruten.
2. Velg målmiljøet.
3. Klikk på **Importer ressurser** øverst til høyre.
4. Klikk på **Last opp**, og bla gjennom etter en pakkefil som er lagret lokalt.
5. Klikk på **Neste** for å gå til den siste importsiden.
6. Løs valideringsfeil og -advarsler under import:
   1. Vær oppmerksom på advarsler eller feil, som angitt av ikonet til venstre for et **ressursnavn**.
   2. Klikk på **Importoppsett**-feltet eller ikonet under **Handling** for mer informasjon.
   3. Velg riktig handling for importoppsett.
   4. Pakken som importeres valideres automatisk på nytt.
7. Fortsett til **Import** hvis du ikke ser noen feil.

Hvis pakken bare er importert delvis, mottar du en feilmelding som beskriver hva som ble importert og hva som ikke ble importert.

## <a name="resource-types"></a>Ressurstyper
Utviklingsprossessen kan innebære endringer til mange ressurstyper. Hvis du for eksempel oppdaterer en app, kan du legge til, fjerne eller oppdatere flere enheter eller tilkoblinger. Endringer til noen, og ikke alle, ressurstypene kan flyttes mellom miljøer. De følgende delene beskriver ressurstypene du kan flytte.

### <a name="entities-picklists"></a>Enheter, nedtrekksmenyer
Du kan eksportere og importere enheter og nedtrekksmenyer som følger:

* **Standardenheter** – bare tilpasninger flyttes mellom miljøer. (Du kan ikke endre bruksklare felt for standardenheter.)
* **Egendefinerte enheter** – egendefinerte enheter flyttes i hele organisasjonen.
* **Egendefinerte nedtrekksmenyer** – egendefinerte nedtrekksmenyer flyttes i hele organisasjonen.

## <a name="data"></a>Data
Du kan ikke flytte databasedata som en del av eksporten og importen av ressurser. Du kan bruke Microsoft Excel til å flytte data. 

