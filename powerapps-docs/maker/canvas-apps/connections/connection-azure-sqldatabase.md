---
title: Oversikt over SQL Server-tilkoblingen | Microsoft Docs
description: Trinnvise instruksjoner for hvordan du kobler til Azure SQL eller en lokal SQL Server-database
author: lancedMicrosoft
ms.service: powerapps
ms.topic: reference
ms.component: canvas
ms.date: 07/12/2016
ms.author: lanced
ms.openlocfilehash: e11521219fcd368801a6e943f45dbc713309ec36
ms.sourcegitcommit: 7354a0c61578fcc0b9965bf557b9d7c553c73e96
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/05/2018
ms.locfileid: "34803424"
---
# <a name="connect-to-sql-server-from-powerapps"></a>Koble til SQL Server fra PowerApps
![SQL Server-ikon](./media/connection-azure-sqldatabase/sqlicon.png)

Koble til SQL Server, i Azure eller en lokal database, slik at du kan vise informasjon fra den i PowerApps.

## <a name="prerequisites"></a>Forutsetninger

* [Registrer deg](../../signup-for-powerapps.md) for PowerApps, og deretter [logger du deg på](http://web.powerapps.com) ved å angi samme legitimasjon som du brukte til å registrere deg.
* Samle inn følgende informasjon for en database som inneholder minst én tabell med en primærnøkkel:
  
  * navnet på databasen
  * navnet på serveren som er vert for databasen
  * et gyldig brukernavn og passord for å koble til databasen
  * godkjenningstypen som kreves for å koble til databasen
    
    Hvis du ikke har denne informasjonen, kan du spørre administratoren for databasen som du vil bruke.
* Hvis du skal bruke lokal database, må du finne en [datagateway](../gateway-management.md) som har blitt delt med deg (eller opprette en).
  
    > [!NOTE]
> Gatewayer og lokale tilkoblinger kan bare opprettes og brukes i brukerens [standardmiljø](../working-with-environments.md).

## <a name="generate-an-app-automatically"></a>Generer en app automatisk
1. Klikk eller trykk på **Ny** på **Fil**-menyen (nær venstre kant) i PowerApps Studio.
   
    ![Ny-alternativet på Fil-menyen](./media/connection-azure-sqldatabase/file-new.png)
2. Klikk eller trykk på høyrepilen på slutten av raden for koblinger under **Start med dine data**.
3. Hvis du allerede har en tilkobling til databasen som du vil bruke, klikk eller trykk på den, og gå rett til trinn 7 i denne prosedyren.
4. Klikk eller trykk på **Ny tilkobling**, og klikk eller trykk på **SQL Server**.
   
    ![Legge til en SQL Server-tilkobling](./media/connection-azure-sqldatabase/add-sql-connection.png)
5. Gjør ett av disse trinnene:
   
   * Angi **Koble til direkte (skytjenester)**, og skriv deretter eller lim inn servernavnet, databasenavnet, brukernavnet og passordet for databasen du vil bruke.
     
       ![Koble til en database i Azure](./media/connection-azure-sqldatabase/connect-azure.png)
   * Angi **Koble til med lokal datagateway**, skriv inn eller lim inn servernavnet, databasenavnet, brukernavnet og passordet for databasen som du vil bruke, og angi godkjenningstypen og gatewayen.
     
       ![Koble til en lokal database](./media/connection-azure-sqldatabase/connect-onprem.png)
     
       > [!NOTE]
> Hvis du ikke har en gateway, må du [installere en](../gateway-reference.md) og deretter klikke eller trykke på **Oppdater gatewaylisten**.
6. Klikk eller trykk på **Koble til**.
7. Klikk eller trykk på et alternativ under **Velg et datasett**, klikk eller trykk på et alternativ under **Velg en tabell** og klikk eller trykk deretter på **Koble til**.
   
    PowerApps oppretter en app som viser data på tre skjermbilder. Heuristikk foreslår hva slags data som skal vises, men du må kanskje tilpasse brukergrensesnittet etter dine behov.
8. Tilpass appen ved hjelp av teknikker som ligner på de som beskrives i [Lag en app fra Excel](../get-started-create-from-data.md), fra og med trinnet for endring av oppsettet i appen.

## <a name="build-an-app-from-scratch"></a>Bygge en app fra grunnen av
1. Logg deg på [powerapps.com](https://web.powerapps.com) med den samme kontoen du brukte til å registrere deg for PowerApps.
2. Klikk eller trykk på **Tilkoblinger** i venstre navigasjonsfelt:  
   
    ![Administrere tilkoblinger](./media/connection-azure-sqldatabase/manage-connections.png)
3. Klikk eller trykk på **Ny tilkobling** i øvre høyre hjørne, og klikk eller trykk deretter på **SQL Server**.
4. Gjør ett av disse trinnene:
   
   * Angi **Koble til direkte (skytjenester)**, og skriv deretter eller lim inn servernavnet, databasenavnet, brukernavnet og passordet for databasen du vil bruke.
     
       ![Koble til en database i Azure](./media/connection-azure-sqldatabase/connect-azure-portal.png)
   * Angi **Koble til med lokal datagateway**, skriv eller lim inn servernavnet, databasenavnet, brukernavnet og passordet for databasen som du vil bruke, og angi godkjenningstypen og gatewayen.
     
       ![Koble til en database i Azure](./media/connection-azure-sqldatabase/connect-onprem-portal.png)
     
       > [!NOTE]
> Hvis du ikke har en gateway, må du [installere en](../gateway-reference.md) og deretter klikke eller trykke på klokkeretning-ikonet for å oppdatere listen.
5. Klikk eller trykk på **Opprett** for å opprette tilkoblingen.
6. Opprett en app ved hjelp av teknikker som ligner på dem som beskrives i [Opprette en app fra grunnen av](../get-started-create-from-blank.md).

## <a name="update-an-existing-app"></a>Oppdatere en eksisterende app
1. Åpne appen som du vil oppdatere i PowerApps Studio.
2. Klikk eller trykk på **Datakilder** på **Vis**-fanen på båndet.
3. Klikk eller trykk på **Legg til en datakilde** i ruten til høyre.
   
    ![Legge til en datakilde](./media/connection-azure-sqldatabase/add-data-source.png)
4. Klikk eller trykk på **Ny tilkobling**, klikk eller trykk på **SQL Server** og klikk eller trykk deretter på **Koble til**.
5. Gjør ett av disse trinnene:
   
   * Angi **Koble til direkte (skytjenester)**, og skriv deretter eller lim inn servernavnet, databasenavnet, brukernavnet og passordet for databasen du vil bruke.
     
       ![Koble til en database i Azure](./media/connection-azure-sqldatabase/connect-azure-fromblank.png)
   * Angi **Koble til med lokal datagateway**, skriv eller lim inn servernavnet, databasenavnet, brukernavnet og passordet for databasen som du vil bruke, og angi godkjenningstypen og gatewayen.
     
       ![Koble til en database i Azure](./media/connection-azure-sqldatabase/connect-onprem-fromblank.png)
     
       > [!NOTE]
> Hvis du ikke har en gateway, må du [installere en](../gateway-reference.md) og deretter klikke eller trykke på sirkel-ikonet for å oppdatere listen.
6. Klikk eller trykk på **Koble til**.
7. Klikk eller trykk på et alternativ under **Velg et datasett**.
8. Velg én eller flere avmerkingsbokser under **Velg en tabell**, og klikk eller trykk på **Koble til**.

## <a name="next-steps"></a>Neste trinn
* Finn ut hvordan du kan [vise data fra en datakilde](../add-gallery.md).
* Finn ut hvordan du kan [vise detaljer og opprette eller oppdatere poster](../add-form.md).
* Se andre typer [datakilder](../connections-list.md) som du kan koble til.  
* [Forstå tabeller og poster](../working-with-tables.md) med datakilder i tabellform.

<!--NotAvailableYet
## View the available functions ##
This connection includes the following functions:

| Function Name |  Description |
| --- | --- |
|[GetItems](connection-azure-sqldatabase.md#getitems) | Retrieves rows from a SQL table |
|[PostItem](connection-azure-sqldatabase.md#postitem) | Inserts a new row into a SQL table |
|[GetItem](connection-azure-sqldatabase.md#getitem) | Retrieves a single row from a SQL table |
|[DeleteItem](connection-azure-sqldatabase.md#deleteitem) | Deletes a row from a SQL table |
|[PatchItem](connection-azure-sqldatabase.md#patchitem) | Updates an existing row in a SQL table |
|[GetTables](connection-azure-sqldatabase.md#gettables) | Retrieves tables from a SQL database |

### GetItems
Get rows: Retrieves rows from a SQL table

#### Input properties

| Name| Data Type|Required|Description|
| ---|---|---|---|
|table|string|yes|Name of SQL table|
|$skip|integer|no|Number of entries to skip (default = 0)|
|$top|integer|no|Maximum number of entries to retrieve (default = 256)|
|$filter|string|no|An ODATA filter query to restrict the number of entries|
|$orderby|string|no|An ODATA orderBy query for specifying the order of entries|

### PostItem
Insert row: Inserts a new row into a SQL table

#### Input properties

| Name| Data Type|Required|Description|
| ---|---|---|---|
|table|string|yes|Name of SQL table|
|item| |yes|Row to insert into the specified table in SQL|

#### Output properties

| Property Name | Data Type | Required | Description |
|---|---|---|---|
|value|array|No | |


### GetItem
Get row: Retrieves a single row from a SQL table

#### Input properties

| Name| Data Type|Required|Description|
| ---|---|---|---|
|table|string|yes|Name of SQL table|
|id|string|yes|Unique identifier of the row to retrieve|

#### Output properties

| Property Name | Data Type | Required | Description |
|---|---|---|---|
|ItemInternalId|string|No | |


### DeleteItem
Delete row: Deletes a row from a SQL table

#### Input properties

| Name| Data Type|Required|Description|
| ---|---|---|---|
|table|string|yes|Name of SQL table|
|id|string|yes|Unique identifier of the row to delete|

#### Output properties
None.

### PatchItem
Update row: Updates an existing row in a SQL table

#### Input properties

| Name| Data Type|Required|Description|
| ---|---|---|---|
|table|string|yes|Name of SQL table|
|id|string|yes|Unique identifier of the row to update|
|item| |yes|Row with updated values|

#### Output properties

| Property Name | Data Type | Required | Description |
|---|---|---|---|
|ItemInternalId|string|No | &nbsp; |


### GetTables
Get tables: Retrieves tables from a SQL database

#### Input properties
None.

#### Output properties

| Property Name | Data Type | Required | Description |
|---|---|---|---|
|value|array|No | Can output the Name and DisplayName properties |

### ExecuteProcedure
Execute stored procedure: Executes a stored procedure in SQL

#### Input properties

| Name| Data Type|Required|Description|
| ---|---|---|---|
|procedure|string|yes|Procedure name|
|parameters| |yes|Input parameters|

#### Output properties
Result of the stored procedure execution.

| Property Name | Data Type | Required | Description |
|---|---|---|---|
|OutputParameters|object|No | Output parameter values |
|ReturnCode|integer|No | Return code of a procedure |
|ResultSets|object|No | Result sets|

-->
