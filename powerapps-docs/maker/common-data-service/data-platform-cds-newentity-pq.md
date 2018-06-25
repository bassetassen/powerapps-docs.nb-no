---
title: Å legge til data i en enhet i Common Data Service for apper ved bruk av Power Query | Microsoft Docs
description: Trinnvise instruksjoner for å bruke Power Query til å legge til data i en ny eller eksisterende enhet i Common Data Service for apper fra en annen datakilde.
author: AFTOwen
manager: kfile
ms.service: powerapps
ms.devlang: na
ms.topic: conceptual
ms.component: cds
ms.date: 03/21/2018
ms.author: anneta
ms.openlocfilehash: 60d1843e48a1dc1d310d877bcba67460da557993
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/04/2018
ms.locfileid: "34168301"
---
# <a name="add-data-to-an-entity-in-common-data-service-for-apps-by-using-power-query"></a>Å legge til data i en enhet i Common Data Service for apper ved bruk av Power Query
I denne prosedyren oppretter du en enhet i [Common Data Service for apper](data-platform-intro.md), og fyller denne enheten med data fra en OData-feed ved bruk av Power Query. Du kan bruke de samme teknikkene til å integrere data fra disse nettkildene og lokale kildene, blant annet:

* SQL Server
* Salesforce
* IBM DB2
* Access
* Excel
* Web API-er
* OData-feeder
* Tekstfiler

Du kan også filtrere, transformere og kombinere data før du laster det inn i en ny eller eksisterende enhet.

Hvis du ikke har en PowerApps-lisens, kan du [registrere deg gratis](../signup-for-powerapps.md).

## <a name="prerequisites"></a>Forutsetninger
For å følge dette emnet, må du bytte til et [miljø](../canvas-apps/working-with-environments.md) der du kan opprette enheter.

## <a name="specify-the-source-data"></a>Å angi kildedataene

1. Logg inn i [PowerApps](https://web.powerapps.com), og klikk eller trykk deretter på Ned-pilen for **Data** nær den venstre kanten.

    ![Hjemmesiden for PowerApps](./media/data-platform-cds-newentity-pq/sign-in.png)

1. Klikk eller trykk på **Data Integration** i listen som vises, og klikk eller trykk deretter på **Nytt prosjekt** nær den øverste kanten til høyre.

1. Klikk eller trykk på **OData** i listen over datakilder.

    ![Å velge en OAuth-kobling](./media/data-platform-cds-newentity-pq/choose-odata.png)

1. Skriv eller lim inn denne nettadressen, og velg deretter **Neste** under **Tilkoblingsinnstillinger**:<br>
`http://services.odata.org/V4/Northwind/Northwind.svc/`

1. Merk av for **Kunder** i listen over tabeller, og klikk og trykk deretter på **Next**.

    ![Å velge Kunder-tabellen](./media/data-platform-cds-newentity-pq/select-table.png)

1. (valgfritt) Endre skjemaet etter behov ved å velge hvilke kolonner du ønsker å inkludere, transformere tabellen på flere måter, legg til en indeks eller betinget kolonne, eller foreta andre endringer.

1. Klikk eller trykk på **Neste** nederst til høyre.

## <a name="specify-the-target-entity"></a>Å angi målenheten
1. Velg **Les inn til ny enhet** under **Innlesingsinnstillinger**.

    ![Å angi navnet på den nye enheten](./media/data-platform-cds-newentity-pq/new-entity-name.png)

    Du kan gi den nye enheten et forskjellig navn eller visningsnavn, men la standardverdiene forbli uendret for å følge med i denne opplæringen.

1. Klikk eller trykk på **ContactName** i listen over **Primært navn-felt**, og deretter klikker eller trykker du på **Neste** nede til høyre.

    Du kan angi et forskjellig primært navn-felt, tilordne en forskjellig kolonne i kildetabellen til hvert felt i enheten du oppretter, eller både og. Hvis du ønsker å følge denne opplæringen nøyaktig, gjør du ingenting med standard kolonnetilordning.

1. Når **Laststatus** er **fullført**, velger du **Ferdig** nede til høyre.

1. Velg **Enheter** under **Data** (nær den venstre kanten) for å vise en liste over enheter i databasen din.

    **Kunder**-enheten som du opprettet fra en OData-feed, vises som en kundeenhet.

    ![Liste over standardenheter og egendefinerte enheter](./media/data-platform-cds-newentity-pq/entity-list.png)

> [!WARNING]
> Hvis du bruker Power Query for å legge til data i en eksisterende enhet, overskrives alle dataene i den enheten.

Hvis du velger **Les inn til eksisterende enhet**, kan du angi en enhet der du legger til data fra **Kunder**-tabellen. Du kan for eksempel legge til dataene i **Konto**-enheten som kommer med Common Data Service. Under **Kildekolonne** kan du ytterligere angi at dataene i **ContactName**-kolonnen fra **Kunder**-tabellen skal legges til i **Navn**-kolonnen i **Kontoer**-enheten.

![Å angi navnet på den nye enheten](./media/data-platform-cds-newentity-pq/existing-entity.png)

Vi er begeistret for denne funksjonaliteten, og vi ser frem til å høre tilbakemeldingen din. [Send oss forslag og tilbakemeldinger](https://powerusers.microsoft.com/t5/PowerApps-Community/ct-p/PowerApps1) om denne funksjonen!

Hvis det vises en [feilmelding om tillatelser](data-platform-cds-newentity-troubleshooting-mashup.md), snakker du med administratoren din.