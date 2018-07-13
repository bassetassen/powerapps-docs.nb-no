---
title: Slik svarer du på DSR-forespørsler om systemgenererte logger i PowerApps, Microsoft Flow og Common Data Service for apper | Microsoft Docs
description: Gjennomgang av hvordan du svarer på DSR-forespørsler om systemgenererte logger i PowerApps, Microsoft Flow og Common Data Service for apper
author: jamesol-msft
manager: kfile
ms.service: powerapps
ms.component: pa-admin
ms.topic: conceptual
ms.date: 05/23/2018
ms.author: jamesol
ms.openlocfilehash: 18bba11ce747b1e04be6013bf41419c34232865a
ms.sourcegitcommit: 79b8842fb0f766a0476dae9a537a342c8d81d3b3
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 07/07/2018
ms.locfileid: "37897252"
---
# <a name="responding-to-dsr-requests-for-system-generated-logs-in-powerapps-microsoft-flow-and-common-data-service-for-apps"></a>Svar på DSR-forespørsler om systemgenererte logger i PowerApps, Microsoft Flow og Common Data Service for Apps
Microsoft gir deg muligheten til å få tilgang til, eksportere og slette systemgenererte logger som kan anses som personlige under den brede definisjonen av *personopplysninger* i EUs personvernforordning (GDPR). Her er noen eksempler på systemgenererte logger som kan anses som personlige under GDPR:
* produkt- og tjenestebruksdata, for eksempel brukeraktivitetslogger
* søkeforespørsler og spørringsdata fra brukere
* data generert av produkter og tjenester som et produkt av systemets funksjonalitet og samhandling med brukere eller andre systemer

Vær oppmerksom på at det ikke er støtte for muligheten til å begrense eller rette opp data i systemgenererte logger. Data i systemgenererte logger utgjør faktiske handlinger utført i Microsoft-skyen, og diagnosedata, inkludert endringer i slike data, går ut over den historiske oversikten over handlinger og gir økt sikkerhetsrisiko og fare for svindel.

## <a name="prerequisites"></a>Forutsetninger
Denne artikkelen fokuserer på hvordan man svarer på DSR-forespørsler for systemgenererte logger i administrerte og ikke-administrerte tenanter. For å avgjøre hvorvidt du hører til en administrert eller ikke-administrert tenant kan du se inndelingen **Å fastslå tenanttype** nedenfor.

## <a name="accessing-and-exporting-system-generated-logs-for-managed-tenants"></a>Slik får du tilgang til og eksporterer systemgenererte logger for administrerte leiere
Administratorer har tilgang til systemgenererte logger som er knyttet til en brukers bruk av tjenester og programmer for PowerApps, Microsoft Flow og Common Data Service (CDS) for Apps.

Gjør følgende for å få tilgang til og eksporterer systemgenererte logger:

1. Gå til [Microsoft Service Trust Portal](https://servicetrust.microsoft.com/) og logg deg på med legitimasjonen til en global administrator for Office 365.

2. Gå til rullegardinlisten **Privacy** (Personvern) øverst på siden, og velg **Data Subject Request** (DSR-forespørsel).

3. På siden **Data Subject Request** (DSR-forespørsel) går du til **System Generated Logs** (Systemgenererte logger) og velger **Data Log Export** (Eksport av datalogg). Dataloggeksporten vises med en liste over forespørsler fra organisasjonen din om eksport av data.

4. Hvis du vil opprette en ny forespørsel for en bruker, klikker du på **Create Export Data Request** (Opprett forespørsel om dataeksport).

    Når du oppretter en ny forespørsel, blir forespørselen oppført på siden **Data Log Export** (Eksport av datalogg), der du kan spore statusen for den. Når en forespørsel er fullført, kan du klikke en kobling for å få tilgang til de systemgenererte loggene, som blir eksportert til Azure-lagringsstedet for organisasjonen innen 30 dager etter oppretting av forespørselen. Dataene blir lagret i vanlige, maskinlesbare filformater, for eksempel XML, CSV eller JSON. Hvis du ikke har en Azure-konto og et Azure-lagringssted, må du opprette en Azure-konto og/eller et Azure-lagringssted for organisasjonen, slik at verkøyet for dataloggeksport kan eksportere de systemgenererte loggene. Du finner mer informasjon i [Introduction to Azure Storage](https://docs.microsoft.com/azure/storage/common/storage-introduction) (Innføring i Azure Storage).

Tabellen nedenfor gir en oppsummering av hvordan man får tilgang til og eksporterer systemgenererte logger for administrerte tenanter:

| Spørsmål | Svar |
| --- | --- |
| Hvor lang tid bruker verktøyet Microsoft-verktøyet Dataloggeksport på å fullføre en forespørsel? |    Dette avhenger av flere faktorer. I de fleste tilfeller tar det en dag eller to, men det kan ta opptil 30 dager.
| Hvilket format kommer utdataene i? | Utdataene kommer som strukturerte, maskinlesbare filer, for eksempel XML, CSV eller JSON.
| Hvem har tilgang til verktøyet Dataloggeksport og kan sende forespørsler om tilgang til systemgenererte logger? | Globale administratorer for Office 365 har tilgang til loggbehandlingsverktøyet for GDPR.
| Hvilke data returnerer Dataloggeksport-verktøyet? | Dataloggeksport-verktøyet returnerer systemgenererte logger som Microsoft lagrer. De eksporterte dataene kommer fra ulike Microsoft-tjenester, deriblant Office 365, Azure, Dynamics, PowerApps, Microsoft Flow og CDS for Apps.
| Hvordan blir dataene returnert til brukeren? |   Data eksporteres til organisasjonens Azure-lagringssted. Det er opp til administratorene i organisasjonen å bestemme hvordan disse dataene skal vises/returneres til brukerne.
| Hvordan ser data i systemgenererte logger ut? |  Her er et eksempel på en oppføring i en systemgenerert logg i JSON-format: <br> [{ <br>"DateTime": "2017-04- 28T12:09:29-07:00",  <br> "AppName": "SharePoint", <br> "Action": "OpenFile", "IP": "154.192.13.131", <br> "DevicePlatform": "Windows 1.0.1607" <br>}]

> [!NOTE]
>  Av sikkerhetsmessige og revisjonsformål, er det enkelte funksjoner som ikke lar deg eksportere eller slette systemgenererte logger for å beholde integriteten til personlige opplysninger.
>
>

## <a name="deleting-system-generated-logs-for-managed-tenants"></a>Slik sletter du systemgenererte logger for administrerte tenanter
Hvis du vil slette systemgenererte logger som er hentet via en tilgangsforespørsel, må du fjerne brukeren fra tjenesten og slette vedkommendes Azure Active Directory-konto. Du finner instruksjoner om permanent sletting av en bruker i delen **Deleting a user** (Sletting av en bruker) i *GDPR-dokumentasjonen om DSR-forespørsler i Azure*, som du finner i [Office 365 Service Trust Portal](https://servicetrust.microsoft.com/ViewPage/GDPRDSR). Det er viktig å være oppmerksom på at permanent sletting av en brukerkonto ikke kan gjøres om når slettingen er startet.

Permanent sletting av en brukerkonto fjerner brukerens data fra systemgenererte logger for tjenestene PowerApps, Microsoft Flow og CDS for Apps innen 30 dager.


## <a name="accessing-and-exporting-system-generated-logs-for-unmanaged-tenants"></a>Slik får du tilgang til og eksporterer systemgenererte logger for ikke-administrerte tenanter

Brukere har tilgang til systemgenererte logger som er knyttet til deres bruk av tjenester og programmer for PowerApps, Microsoft Flow og Common Data Service (CDS) for apper.

Gjør følgende for å få tilgang til og eksporterer systemgenererte logger:
1. Gå til [Personvernportal for arbeid og skole](https://go.microsoft.com/fwlink/?linkid=873123).
1. På **Mine dataforespørsler**-siden kan en bruker be om en dataeksport ved å klikke på **Ny eksportforespørsel**-knappen.
1. Når du klikker på denne knappen, vil du bli bedt om å bekrefte forespørselen. Klikk på **Ja** for å fortsette.
1. Nye eksportforespørsler kan ta opptil én måned til å fullføre. I dette tidsrommet vil du se statusen **Kjører**.
1. Når prosessen er fullført, vil kolonnen **Fullført dato** være utfylt, og du tilbys en kobling til de **systemgenererte** loggene dine.
1. Klikk på denne koblingen for å laste ned dataene dine. Du kan bruke et tekstredigeringsprogram til å vise disse dataene.
1. Legg også merke til at **utløpsdatoen** for dette innholdet er fylt ut i Utløpsdato-kolonnen. Utløpsdatoen angir hvor lang tid du har på deg til å hente de systemgenererte loggene.

Tabellen nedenfor gir en oppsummering av hvordan man får tilgang til og eksporterer systemgenererte logger for ikke-administrerte tenanter:

| Spørsmål | Svar |
| --- | --- |
| Hvor lang tid bruker verktøyet Microsoft-verktøyet Dataloggeksport på å fullføre en forespørsel? |    Dette avhenger av flere faktorer. I de fleste tilfeller tar det en dag eller to, men det kan ta opptil 30 dager.
| Hvilket format kommer utdataene i? | Utdataene kommer som strukturerte, maskinlesbare filer, for eksempel XML, CSV eller JSON.
| Hvem har tilgang til verktøyet Dataloggeksport og kan sende forespørsler om tilgang til systemgenererte logger? | Brukere som er medlem av en ikke-administrert tenant har tilgang til å sende forespørsler.
| Hvilke data returnerer Dataeksport-verktøyet? | Dataeksport-verktøyet returnerer systemgenererte logger som Microsoft lagrer. De eksporterte dataene kommer fra ulike Microsoft-tjenester, deriblant Office 365, Azure, Dynamics, PowerApps, Microsoft Flow og CDS for Apps.
| Hvordan blir dataene returnert til brukeren? |   Data eksporteres til et Microsoft-webområde der en kobling på en sikker måte tilbys for brukeren som utførte DSR-forespørselen.
| Hvordan ser data i systemgenererte logger ut? |  Her er et eksempel på en oppføring i en systemgenerert logg i JSON-format: <br> [{ <br>"DateTime": "2017-04- 28T12:09:29-07:00",  <br> "AppName": "SharePoint", <br> "Action": "OpenFile", "IP": "154.192.13.131", <br> "DevicePlatform": "Windows 1.0.1607" <br>}]

> [!NOTE]
>  Av sikkerhetsmessige og revisjonsformål, er det enkelte funksjoner som ikke lar deg eksportere eller slette systemgenererte logger for å beholde integriteten til personlige opplysninger.
>
>

## <a name="deleting-system-generated-logs-for-unmanaged-tenants"></a>Slik sletter du systemgenererte logger for ikke-administrerte tenanter
Hvis du vil slette systemgenererte logger hentet via en forespørsel om tilgang, må du lukke kontoen din. Dette vil føre til at de systemgenererte loggene slettes og dataene fjernes i tjenestene for PowerApps, Microsoft Flow og CDS for apper innen 30 dager.

Slik sletter du systemgenererte logger:
1. Gå til [Personvernportal for arbeid og skole](https://go.microsoft.com/fwlink/?linkid=873123).
1. En bruker kan be om å få slettet sine data på **Mine dataforespørsler**-siden, ved å klikke på **Lukk konto**-knappen.
1. Når du klikker på denne knappen, vil du bli bedt om å bekrefte forespørselen. Klikk på **Ja** for å fortsette.
1. Når kontoen er avsluttet, har du ikke tilgang til PowerApps, Microsoft Flow og CDS.

## <a name="determining-tenant-type"></a>Å fastslå tenanttype
Hvis du vil finne ut om du er bruker av en administrert eller ikke-administrert tenant, kan du utføre følgende handlinger:
1. Åpne følgende nettadresse i en nettleser, og pass på å erstatte e-postadressen din i nettadressen:[ https://login.windows.net/common/userrealm/foobar@contoso.com?api-version=2.1](https://login.windows.net/common/userrealm/foobar@contoso.com?api-version=2.1).

2. Hvis du er medlem av en **ikke-administrert tenant**, får du se en `"IsViral": true` i svaret.
   ```
      {
      ...
      "Login": "foobar@unmanagedcontoso.com",
      "DomainName": "unmanagedcontoso.com",
      "IsViral": **true**,
      ...
      }
   ```

3. Ellers hører du til en administrert tenant.
