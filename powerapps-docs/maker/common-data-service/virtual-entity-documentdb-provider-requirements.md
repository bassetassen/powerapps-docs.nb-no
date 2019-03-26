---
title: 'Forhåndsvisningsfunksjon: Bruke Azure Cosmos DB for SQL-API-dataleverandør med Common Data Service for Apps | MicrosoftDocs'
description: Lær hvordan du konfigurerer Azure Cosmos DB for SQL-API-dataleverandøren for bruk med virtuelle enheter.
keywords: SQL-API
ms.date: 02/15/2019
ms.service: crm-online
ms.custom: null
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
ms.assetid: d0031ffc-8754-4a12-b8c1-e08edc49ff73
author: Mattp123
ms.author: matp
manager: kvivek
ms.reviewer: null
ms.suite: null
ms.tgt_pltfrm: null
caps.latest.revision: null
topic-status: Drafting
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="preview-feature-azure-cosmos-db-sql-api-data-provider-requirements"></a>Forhåndsvisningsfunksjon: Krav for Azure Cosmos DB for SQL-API-dataleverandør

Dette emnet beskriver kravene til Azure Cosmos DB for SQL API-dataleverandøren og hvordan du konfigurerer og anbefalte gode fremgangsmåter når du bruker Azure Cosmos DB for SQL API-dataleverandøren med virtuelle enheter. 

> [!IMPORTANT]
> - [!INCLUDE [cc-preview-features-definition](../../includes/cc-preview-features-definition.md)]
> - [!INCLUDE [cc-preview-features-definition](../../includes/cc-preview-features-expect-changes.md)]
> - [!INCLUDE [cc-preview-features-definition](../../includes/cc-preview-features-no-ms-support.md)]


## <a name="what-is-azure-cosmos-db"></a>Hva er Azure Cosmos DB?

Azure Cosmos DB er Microsofts globalt distribuerte databasetjeneste med flere modeller for forretningskritiske programmer. Det gir omfattende og velkjente SQL-spørringsfunksjoner med konsekvent lave ventetider over skjemaløse JSON-data. Mer informasjon: [Innføring i Azure Cosmos DB: SQL-API](https://docs.microsoft.com/azure/cosmos-db/sql-api-introduction)

## <a name="requirements"></a>Krav

- Azure-abonnement som inkluderer Azure Cosmos DB.
- En Azure Cosmos DB SQL API-samling.
- Azure Cosmos DB-databasetypen må være SQL. 

## <a name="data-type-mapping"></a>Tilordning av datatype

Anta at du har et Azure Cosmos DB-dokument i en samling kalt *Bestillinger* som har følgende JSON-struktur.

![Eksempel-JSON for SQL-API-dokument.](media/documentdbexample.png)

Denne tabellen angir datatypetilordningene for SQL API-dokumentet i *Bestillinger*-samlingen med Common Data Service for Apps.

|SQL API-data|CDS for Apps|
|--|--|
|`id`|Primærnøkkel|
|`name`|En enkelt linje med tekst|
|`quantity`|Heltall|
|`orderid`|En enkelt linje med tekst|
|`ordertype`|Alternativsett|
|`amount`|Desimaltall eller valuta|
|`delivered`|To alternativer|
|`datetimeoffset`|Dato og klokkeslett|

> [!NOTE]
> - Attributter med et understrekingstegn (_) prefikset genereres av SQL API.
> - Attributter som er konfigurert som valgfrie i SQL API-dokumentet og tilordnes i CDS for Apps som **Nødvendig for selskapet**, fører til feil under kjøring.
> - ID-attributtverdier må være GUID-er.
> - Hvis du vil ha mer informasjon om hvordan du bruker datoer i SQL API, kan du se [Arbeide med datoer i Azure Cosmos DB](https://azure.microsoft.com/blog/working-with-dates-in-azure-documentdb-4/).

## <a name="supported-sql-query-filtering"></a>Støttet filtrering av SQL-spørring

Filtrering av SQL-spørringer støtter følgende operatorer. 

- Sammenligningsoperatorer:`<`,`>`,`<=`, `>=`,`!=`
- Logiske operatorer: `and`, `or` 
- Angivelsesoperatorer: `in`, `not in`
- Strengoperatorer: `like`, `contains`, b`egins with`, `ends with`

> [!NOTE]
> Bruk av like-operatoren er oversatt til de tilsvarende `contains`/`begins with`/`ends with` operatorene. SQL API støtter ikke mønsterargumenter som beskrevet i emnet [Like (Transact-SQL)](/sql/t-sql/language-elements/like-transact-sql). The Azure Cosmos DB for SQL API-dataleverandøren kan oversette det enkelte spesialtilfellet `Like('[aA]%')` til `BeginsWith('a')` ELLER `BeginsWith('A')`. Legg merke til at strengsammenligning i SQL API skiller mellom små og store bokstaver.

## <a name="add-a-data-source-using-the-azure-cosmos-db-for-sql-api-data-provider"></a>Legge til en datakilde ved hjelp av Azure Cosmos DB for SQL-API-dataleverandøren

1. Gå til [AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.documentdb_data_provider?tab=Overview), velg **HENT DEN NÅ**, og følg instruksjonene for å legge til programmet i miljøet ved hjelp av v9x eller senere.
2. Etter at løsningen er installert, logger du på miljøet og går til **Innstillinger** > **Administrasjon** > **Datakilder for virtuelle enheter**.
3. Klikk på handlingsverktøylinjen, velg **NY** og i dialogboksen **Velg dataleverandør** velger du **Azure Cosmos DB for SQL-API-dataleverandør** og velger deretter **OK**.
![Velg Azure Cosmos DB for SQL-API-dataleverandøren.](media/createdatasource.png)
1. Angi følgende informasjon, og velg deretter **Lagre og lukk**.

    |Felt|Beskrivelse|
    |--|--|
    |**Navn**|Skriv inn et navn som beskriver datakilden.|
    |**Samlingsnavn**|Navnet på Azure Cosmos DB-*databasen* som inneholder samlingen du vil vise i en virtuell enhet.  |
    |**Autorisasjonsnøkkel**|Primær- eller sekundærnøkkelen for Azure Cosmos DB-kontoen. Du kan finne nøkkelen i Azure-administrasjonsportalen under **Nøkler**-innstillingen under Azure Cosmos DB-kontoen din.|
    |**URI**|URI for ressursgruppen hvor Azure Cosmos DB-samlingen er plassert. URI-en er utformet på lignende måte som `https://contoso/documents.azure.com:443`. Du kan finne URI-en i Azure-administrasjonsportalen under **Nøkler**-innstillingen for Azure Cosmos DB-kontoen din. |
    |**Tidsavbrudd i sekunder**|Skriv inn ventetiden for et svar fra Azure Cosmos DB-tjenesten før dataforespørselen blir tidsavbrutt, i antall sekunder. Du kan for eksempel angi 30 hvis du vil vente maksimalt 30 sekunder før et tidsavbrudd oppstår. Standard tidsavbrudd er 120 sekunder.|

    > [!div class="mx-imgBorder"] 
    > ![Opprett datakilden ved hjelp av SQL-API-dataleverandøren.](media/cosmosdb-datasource.png)

## <a name="best-practices-and-limitations"></a>Gode fremgangsmåter og begrensninger

- Vær oppmerksom på følgende når du bruker Azure Cosmos DB som datakilde:
   - Hver Azure Cosmos DB-datakilde kan bare være knyttet til en enkelt virtuell enhet.
   - Du kan koble flere datakilder til samme samling i Azure Cosmos DB.
- Du kan ikke segmentere dataene i en samling etter enhet.
- Azure Cosmos DB-databaser krever ikke et skjema, men dataene i Azure Cosmos DB må struktureres ved hjelp av et forutsigelig skjema. 
- Selv om Azure Cosmos DB for SQL API-dataleverandøren implementerer spørringsoversetting av projeksjon , filtrering og sorteringsoperatorer, støtter den ikke join-operasjoner.
- Du kan bare filtrere etter én enkelt kolonne med SQL API.

## <a name="see-also"></a>Se også

[Opprette og redigere virtuelle enheter som inneholder data fra en ekstern datakilde](create-edit-virtual-entities.md)
