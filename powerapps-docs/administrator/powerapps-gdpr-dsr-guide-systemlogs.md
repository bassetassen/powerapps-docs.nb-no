---
title: Svar på DSR-forespørsler om systemgenererte logger i PowerApps, Microsoft Flow og Common Data Service | Microsoft Docs
description: Svar på DSR-forespørsler om systemgenererte logger i PowerApps, Microsoft Flow og Common Data Service
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
ms.date: 04/18/2018
ms.author: jamesol
ms.openlocfilehash: 1b85ac81969407fe4e84c41fd93debeccddb0f05
ms.sourcegitcommit: e3a2819c14ad67cc4ca6640b9064550d0f553d8f
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/20/2018
---
# <a name="responding-to-dsr-requests-for-system-generated-logs-in-powerapps-microsoft-flow-and-common-data-service-for-apps"></a>Svar på DSR-forespørsler om systemgenererte logger i PowerApps, Microsoft Flow og Common Data Service for Apps
Microsoft gir deg muligheten til å få tilgang til, eksportere og slette systemgenererte logger som kan anses som personlige under den brede definisjonen av *personopplysninger* i EUs personvernforordning (GDPR). Her er noen eksempler på systemgenererte logger som kan anses som personlige under GDPR:
* produkt- og tjenestebruksdata, for eksempel brukeraktivitetslogger
* søkeforespørsler og spørringsdata fra brukere
* data generert av produkter og tjenester som et produkt av systemets funksjonalitet og samhandling med brukere eller andre systemer

Vær oppmerksom på at det ikke er støtte for muligheten til å begrense eller rette opp data i systemgenererte logger. Data i systemgenererte logger utgjør faktiske handlinger utført i Microsoft-skyen, og diagnosedata, inkludert endringer i slike data, går ut over den historiske oversikten over handlinger og gir økt sikkerhetsrisiko og fare for svindel.

## <a name="accessing-and-exporting-system-generated-logs"></a>Tilgang til og eksport av systemgenererte logger
Administratorer har tilgang til systemgenererte logger som er knyttet til en brukers bruk av tjenester og programmer for PowerApps, Microsoft Flow og CDS for Apps. Slik får du tilgang til og eksporterer systemgenererte logger:

1. Gå til [Microsoft Service Trust Portal](https://servicetrust.microsoft.com/) og logg deg på med legitimasjonen til en global administrator for Office 365.

2. Gå til rullegardinlisten **Privacy** (Personvern) øverst på siden, og velg **Data Subject Request** (DSR-forespørsel).

3. På siden **Data Subject Request** (DSR-forespørsel) går du til **System Generated Logs** (Systemgenererte logger) og velger **Data Log Export** (Eksport av datalogg). Dataloggeksporten vises med en liste over forespørsler fra organisasjonen din om eksport av data.

4. Hvis du vil opprette en ny forespørsel for en bruker, klikker du på **Create Export Data Request** (Opprett forespørsel om dataeksport).

    Når du oppretter en ny forespørsel, blir forespørselen oppført på siden **Data Log Export** (Eksport av datalogg), der du kan spore statusen for den. Når en forespørsel er fullført, kan du klikke en kobling for å få tilgang til de systemgenererte loggene, som blir eksportert til Azure-lagringsstedet for organisasjonen innen 30 dager etter oppretting av forespørselen. Dataene blir lagret i vanlige, maskinlesbare filformater, for eksempel XML, CSV eller JSON. Hvis du ikke har en Azure-konto og et Azure-lagringssted, må du opprette en Azure-konto og/eller et Azure-lagringssted for organisasjonen, slik at verkøyet for dataloggeksport kan eksportere de systemgenererte loggene. Du finner mer informasjon i [Introduction to Azure Storage](https://docs.microsoft.com/azure/storage/common/storage-introduction) (Innføring i Azure Storage).

Tabellen nedenfor gir en oppsummering av tilgang til og eksport av systemgenererte logger:

| Spørsmål | Svar |
| --- | --- |
| Hvor lang tid bruker verktøyet Microsoft-verktøyet Dataloggeksport på å fullføre en forespørsel? |    Dette avhenger av flere faktorer. I de fleste tilfeller tar det en dag eller to, men det kan ta opptil 30 dager.
| Hvilket format kommer utdataene i? | Utdataene kommer som strukturerte, maskinlesbare filer, for eksempel XML, CSV eller JSON.
| Hvem har tilgang til verktøyet Dataloggeksport og kan sende forespørsler om tilgang til systemgenererte logger? | Globale administratorer for Office 365 har tilgang til loggbehandlingsverktøyet for GDPR.
| Hvilke data returnerer Dataloggeksport-verktøyet? | Dataloggeksport-verktøyet returnerer systemgenererte logger som Microsoft lagrer. De eksporterte dataene kommer fra ulike Microsoft-tjenester, deriblant Office 365, Azure, Dynamics, PowerApps, Microsoft Flow og CDS for Apps.
| Hvordan blir dataene returnert til brukeren? |   Data eksporteres til organisasjonens Azure-lagringssted. Det er opp til administratorene i organisasjonen å bestemme hvordan disse dataene skal vises/returneres til brukerne.
| Hvordan ser data i systemgenererte logger ut? |  Her er et eksempel på en oppføring i en systemgenerert logg i JSON-format: <br> [{ <br>"DateTime": "2017-04- 28T12:09:29-07:00",  <br> "AppName": "SharePoint", <br> "Action": "OpenFile", "IP": "154.192.13.131", <br> "DevicePlatform": "Windows 1.0.1607" <br>}]

> [!NOTE]
>  Noen funksjoner tillater ikke eksport eller sletting av systemgenererte logger med personopplysninger, slik at integriteten til denne informasjonen kan beholdes av sikkerhets- og revisjonshensyn.
>
>

## <a name="deleting-system-generated-logs"></a>Sletting av systemgenererte logger
Hvis du vil slette systemgenererte logger som er hentet via en tilgangsforespørsel, må du fjerne brukeren fra tjenesten og slette vedkommendes Azure Active Directory-konto. Du finner instruksjoner om permanent sletting av en bruker i delen **Deleting a user** (Sletting av en bruker) i *GDPR-dokumentasjonen om DSR-forespørsler i Azure*, som du finner i [Office 365 Service Trust Portal](https://servicetrust.microsoft.com/ViewPage/GDPRDSR). Det er viktig å være oppmerksom på at permanent sletting av en brukerkonto ikke kan gjøres om når slettingen er startet.

Permanent sletting av en brukerkonto fjerner brukerens data fra systemgenererte logger for tjenestene PowerApps, Microsoft Flow og CDS for Apps innen 30 dager.
