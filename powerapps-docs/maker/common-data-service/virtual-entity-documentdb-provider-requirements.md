---
title: 'Evalueringsfunksjonalitet: Bruk Azure Cosmos DB SQL API-dataleverandør med Common Data Service for apper | MicrosoftDocs'
description: Lær hvordan du konfigurerer Azure Cosmos DB for SQL API-dataleverandøren for bruk med virtuelle enheter.
keywords: SQL API
ms.date: 06/27/2018
ms.service: crm-online
ms.custom: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
ms.assetid: d0031ffc-8754-4a12-b8c1-e08edc49ff73
author: Mattp123
ms.author: matp
manager: kvivek
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
caps.latest.revision: ''
topic-status: Drafting
ms.openlocfilehash: fa45376dff85205a0dfbf28334c678293528d00e
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/08/2018
ms.locfileid: "39696538"
---
# <a name="preview-feature-azure-cosmos-db-sql-api-data-provider-requirements"></a>Evalueringsfunksjonalitet: Krav for Azure Cosmos DB for SQL API-dataleverandør

Dette emnet beskriver kravene for Azure Cosmos DB for SQL API-dataleverandøren så vel som hvordan du konfigurerer og anbefaler anbefalte fremgangsmåtene når du bruker Azure Cosmos DB SQL API-dataleverandøren med virtuelle enheter. 

> [!IMPORTANT]
> - [!INCLUDE [cc-preview-features-definition](../../includes/cc-preview-features-definition.md)]
> - [!INCLUDE [cc-preview-features-definition](../../includes/cc-preview-features-expect-changes.md)]
> - [!INCLUDE [cc-preview-features-definition](../../includes/cc-preview-features-no-ms-support.md)]


## <a name="what-is-azure-cosmos-db"></a>Hva er Azure Cosmos DB?

Azure Cosmos DB er Microsofts globalt distribuerte multimodell-databasetjeneste for forretningskritiske programmer. Det inneholder rike og velkjente SQL-spørringsmuligheter med konsekvent lav ventetid over skjemaløst JSON-data. Mer informasjon: [Innføring i Azure Storage](https://docs.microsoft.com/azure/cosmos-db/sql-api-introduction).

## <a name="requirements"></a>Krav

- Azure-abonnement som inkluderer Azure Cosmos DB.
- En Azure Cosmos DB for SQL API-samling.
- Azure Cosmos DB-datatypen må være SQL. 

## <a name="data-type-mapping"></a>Tilordning av datatype

La oss si at du har et Azure Cosmos DB-dokument som heter *Ordrer* med følgende JSON-struktur.

![Eksempel på JSON for SQL API-dokument.](media/documentdbexample.png)

Denne tabellen angir datatypetilordningene for SQL API-dokumentet i *Ordre*-samlingen med Common Data Service for apper.

|SQL API-data|CDS for apper|
|--|--|
|`id`|Primærnøkkel|
|`name`|Enkeltlinje med tekst|
|`quantity`|Heltall|
|`orderid`|Enkeltlinje med tekst|
|`ordertype`|Alternativsett|
|`amount`|Desimaltall eller valuta|
|`delivered`|To alternativer|
|`datetimeoffset`|Dato og klokkeslett|

> [!NOTE]
> - Attributter med et understrekingstegn (_) genereres av SQL API-en.
> - Attributter som konfigureres som valgfrie i SQL API-dokumentet og tilordnes i CDS for apper som **Nødvendig for selskapet**, forårsaker en kjøretidsfeil.
> - id-attributtverdier må være GUID-er.
> - Hvis du vil ha mer informasjon om hvordan du bruker datoer i SQL API, kan du se [Arbeid med datoer i Azure Cosmos DB](https://azure.microsoft.com/blog/working-with-dates-in-azure-documentdb-4/).

## <a name="supported-sql-query-filtering"></a>Støtter SQL-spørringsfiltrering

SQL-spørringsfiltrering støtter følgende operatorer. 

- Sammenligningsoperatorer:`<`,`>`,`<=`, `>=`,`!=`
- Logiske operatorer: `and`, `or` 
- Angivelsesoperatorer: `in`, `not in`
- Stringoperatorer: `like`, `contains`, b`egins with`, `ends with`

> [!NOTE]
> Bruk av like-operatorer oversettes til tilsvarende `contains`/`begins with`/`ends with`-operatorer. SQL API-en støtter ikke mønsterargumenter som beskrevet i emnet [Like (Transact-SQL)](/sql/t-sql/language-elements/like-transact-sql). Azure Cosmos DB for SQL API-dataleverandøren kan oversette det enkle spesialtilfellet `Like('[aA]%')` til `BeginsWith('a')` ELLER `BeginsWith('A')`. Vær oppmerksom på at strengsammenligningen i SQL API-en skiller mellom små og store bokstaver.

## <a name="add-a-data-source-using-the-azure-cosmos-db-for-sql-api-data-provider"></a>Legg til en datakilde ved bruk av Azure Cosmos DB for SQL API-dataleverandøren

1. Gå til [AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.documentdb_data_provider?tab=Overview), velg **HENT DET NÅ**, og følg instruksjonene for å legge til programmet i miljøet ved bruk av v9x eller nyere.
2. Etter at løsningen er installert, logger du deg på miljøet, og deretter går du til **Innstillinger** > **Administrasjon** > **Virtuelle enhetsdatakilder**.
3. Velg **NY** på Handlinger-verktøylinjen, merk av for **Azure Cosmos DB for SQL API-dataleverandør** i dialogboksen **Velg dataleverandør**, og velg deretter **OK**.
![Velg Azure Cosmos DB for SQL API-dataleverandør.](media/createdatasource.png)
1. Angi følgende informasjon, og velg deretter **LAGRE OG LUKK**.

    |Felt|Beskrivelse|
    |--|--|
    |**Navn**|Skriv inn et navn som beskriver datakilden.|
    |**Navn på samling**|ID-en til Azure Cosmos DB-databasesamlingen inneholder dataene du ønsker å hente frem i en virtuell enhet.  |
    |**Autorisasjonsnøkkel**|Primær-og sekundærnøkkelen for Azure Cosmos DB-kontoen. Du finner nøkkelen fra Azure-administrasjonsportalen under **Nøkkel**-innstillingen, i Azure Cosmos DB-kontoen.|
    |**URI**|URI-en til ressursgruppen der Azure Cosmos DB-samlingen befinner seg. URI-en utformes slik `https://contoso/documents.azure.com:443`. Du finner URI-en fra Azure-administrasjonsportalen under **Nøkkel**-innstillingen, i Azure Cosmos DB-kontoen. |
    |**Tidsavbrudd i sekunder**|Skriv inn antall sekunder du skal vente på svar fra Azure Cosmos DB-tjenesten før dataforespørselen får tidsavbrudd. Du kan for eksempel skrive inn 30 for å vente maksimum 30 sekunder før det skjer et tidsavbrudd. Standard tidsavbrudd er 120 sekunder.|

    ![Opprett datakilden ved hjelp av SQL API-dataleverandøren.](media/cosmosdb-datasource.png)

## <a name="best-practices-and-limitations"></a>Anbefalte fremgangsmåter og begrensninger

- Legg merke til følgende når du bruker Azure Cosmos DB som en datakilde:
   - Hver Azure Cosmos DB-datakilde kan bare være knyttet til en enkelt virtuell enhet.
   - Du kan koble til flere datakilder i den samme samlingen i Azure Cosmos DB.
- Du kan ikke segmentere dataene i en samling etter enhet.
- Azure Cosmos DB-databaser krever ikke et skjema, men dataene i Azure Cosmos DB må imidlertid struktureres ved bruk av et forutsigbart skjema. 
- Selv om Azure Cosmos DB for SQL API-dataleverandøren implementerer spørringsoversettelse av projeksjons-, filtrerings- og sorteringsoperatorer, støtter det ikke JOIN-operasjoner.
- Du kan bare filtrere etter en enkelt kolonne ved bruk av SQL API-en.

## <a name="see-also"></a>Se også

[Opprett og rediger virtuelle enheter som inneholder data fra en ekstern datakilde](create-edit-virtual-entities.md)
