---
title: Legge til data i en enhet i Common Data Service ved hjelp av Power Query | Microsoft Docs
description: Trinnvise instruksjoner for hvordan du bruker Power Query til å legge til data i en ny eller eksisterende enhet i Common Data Service fra en annen datakilde.
author: mllopis
manager: kfile
ms.service: powerapps
ms.devlang: na
ms.topic: conceptual
ms.component: cds
ms.date: 03/21/2018
ms.author: millopis
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="add-data-to-an-entity-in-common-data-service-by-using-power-query"></a>Legge til data i en enhet i Common Data Service ved hjelp av Power Query
I denne prosedyren skal du opprette en enhet i [Common Data Service](data-platform-intro.md) og fylle ut enheten med data fra en OData-feed ved hjelp Power Query. Du kan bruke de samme fremgangsmåtene for å integrere data fra disse online og lokale kildene, blant annet:

* SQL Server
* Salesforce
* IBM DB2
* Tilgang
* Excel
* Web-API-er
* OData-feeder
* Tekstfiler

Du kan også filtrere, transformere og slå sammen data på før du laster dem til en ny eller eksisterende enhet.

Hvis du ikke har en lisens for PowerApps, kan du [registrere deg gratis](../signup-for-powerapps.md).

## <a name="prerequisites"></a>Forhåndskrav
Hvis du vil følge dette emnet, må du bytte til et [miljø](../canvas-apps/working-with-environments.md) der du kan opprette enheter.

## <a name="specify-the-source-data"></a>Angi datakilden

1. Logg på [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc), og klikk eller trykk på Pil ned for **Data** nær venstre kant.

    ![Hjemmesiden for PowerApps](./media/data-platform-cds-newentity-pq/sign-in.png)

1. I listen som vises, klikker eller trykker du på **Dataintegrering**, og klikker eller trykker på **Nytt prosjekt** nær øvre høyre hjørne i vinduet.

1. I listen over datakilder klikker eller trykker du på **OData**.

    ![Velge OAuth-koblingen](./media/data-platform-cds-newentity-pq/choose-odata.png)

1. Under **Tilkoblingsinnstillinger** skriver du inn eller limer inn URL-adressen, og velger deretter **Neste**:<br>
`http://services.odata.org/V4/Northwind/Northwind.svc/`

1. I listen over tabeller merker du av for **Kunder**, og klikker eller trykker deretter på **Neste**.

    ![Velg Kunder-tabellen](./media/data-platform-cds-newentity-pq/select-table.png)

1. (valgfritt) Endre skjemaet etter behov ved å velge kolonner som skal inkluderes, transformere tabellen på én eller flere måter, legge til en indeks eller betinget kolonne eller andre endringer.

1. Klikk eller trykk på **Neste** nederst til høyre.

## <a name="specify-the-target-entity"></a>Angi målenheten
1. Under **Innstillinger for lasting** velger du **Last til ny enhet**.

    ![Angi navnet på den nye enheten](./media/data-platform-cds-newentity-pq/new-entity-name.png)

    Du kan gi den nye enheten et annet navn eller visningsnavn, men behold standardverdiene for å følge denne opplæringen nøyaktig.

1. I listen **Primært feltnavn** klikker eller trykker du på **Kontaktperson**, og klikker eller trykker deretter på **Neste** i nedre høyre hjørne.

    Du kan angi et annet primært feltnavn, tilordne en annen kolonne i kildetabellen til hvert felt i enheten som du oppretter, eller begge deler. Du kan også angi om tekstkolonner i spørringsutdataene skal opprettes som enten tekst med flere linjer eller en enkelt linje med tekst i Common Data Service. For å følge denne opplæringen nøyaktig, beholder du standardkolonnetilordningen.

1. Når **lastestatusen** er **fullført**, velger du **Ferdig** i nedre høyre hjørne.

1. Under **Data** (nær venstre kant), velger du **Enheter** for å vise listen over enheter i databasen.

    **Kunder**-enheten som du opprettet fra en OData-feed, vises som en egendefinert enhet.

    ![Liste over standard og egendefinerte enheter](./media/data-platform-cds-newentity-pq/entity-list.png)

> [!WARNING]
> Hvis du bruker Power Query for å legge til data i en eksisterende enhet, overskrives alle dataene i denne enheten.

Hvis du velger **Last til eksisterende enhet**, kan du angi en enhet som du legger til data fra **Kunder**-tabellen. Du kan for eksempel legge til dataene i **Forretningsforbindelse**-enheten som Common Data Service leveres med. Under **Kildekolonne** kan du videre angi at dataene i **Kontaktnavn**-kolonnen fra **Kunder**-tabellen skal legges til i **Navn**-kolonnen i **Forretningsforbindelser**-enheten.

![Angi navnet på den nye enheten](./media/data-platform-cds-newentity-pq/existing-entity.png)

Vi er glade over denne funksjonaliteten og ser frem til å få tilbakemelding fra deg. [Send oss forslag og tilbakemeldinger](https://powerusers.microsoft.com/t5/PowerApps-Community/ct-p/PowerApps1) om denne funksjonen.

Hvis en [feilmelding om tillatelser](data-platform-cds-newentity-troubleshooting-mashup.md) vises, kontakter du administratoren.
