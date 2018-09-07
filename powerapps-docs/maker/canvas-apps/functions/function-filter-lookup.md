---
title: Funksjonene Filter, Search og LookUp | Microsoft Docs
description: Referanseinformasjon for funksjonene Filter og LookUp i PowerApps, inkludert syntaks og eksempler
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 02/05/2017
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: c37aa315981c51a446254473686c44501e72a96f
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/24/2018
ms.locfileid: "42831480"
---
# <a name="filter-search-and-lookup-functions-in-powerapps"></a>Funksjonene Filter, Search og LookUp i PowerApps
Finner én eller flere [poster](../working-with-tables.md#records) i en [tabell](../working-with-tables.md).

## <a name="description"></a>Beskrivelse
**Filter**-funksjonen finner poster i en tabell som tilfredsstiller en formel.  Bruk**Filter** til å finne et sett med poster som samsvarer med ett eller flere vilkår, og forkast de som ikke gjør det.

Funksjonen **LookUp** finner den første posten i en tabell som tilfredsstiller formelen.  Bruk **LookUp** til å finne enkeltposter som samsvarer med ett eller flere vilkår.

Formelen evalueres for hver post i tabellen, dette gjelder begge.  Poster som resulterer i *sann*-uttrykk, er inkludert i resultatet.  Bortsett fra de normale [operatorene](operators.md) for formelen kan du nå bruke operatorene **[in](operators.md#in-and-exactin-operators)** og **[exactin](operators.md#in-and-exactin-operators)** for delstrengtreff.

[!INCLUDE [record-scope](../../../includes/record-scope.md)]

Funksjonen **Search** finner poster i en tabell som inneholder en streng i én av kolonnene. Strengen kan befinne seg hvor som helst i kolonnen: hvis du for eksempel søker etter «tor» eller «mod», finner funksjonen et treff i en kolonne som inneholder «Tormod». Søkene skiller ikke mellom små og store bokstaver. I motsetning til **Filter** og **LookUp** så bruker funksjonen **Search** én enkelt streng for samsvar i stedet for en formel.

**Filter** og **Search** returnerer en tabell som inneholder de samme kolonnene som den opprinnelige tabellen, og postene som samsvarer med vilkårene. **LookUp** returnerer bare den første posten som blir funnet, etter å ha tatt i bruk en formel for å redusere posten til en enkeltverdi. Hvis ingen poster returneres, returnerer **Filter** og **Search** en [tom](function-isblank-isempty.md) tabell, og **LookUp** returnerer en *tom* post.  

[Tabeller](../working-with-tables.md) er en verdi i PowerApps, akkurat som en streng eller et tall. De kan sendes til og returneres fra funksjoner.  **Filter**, **Search** og **LookUp** endrer ikke en tabell. De tar i stedet en tabell som et argument og returnerer en tabell, en post, eller en enkeltverdi fra den. Se [Arbeide med tabeller](../working-with-tables.md) for mer informasjon.

[!INCLUDE [delegation](../../../includes/delegation.md)]

## <a name="syntax"></a>Syntaks
**Filter**( *Table*, *Formula1* [, *Formula2*, ... ] )

* *Table* – obligatorisk. Tabell det skal søkes i.
* *Formula* – obligatorisk. Formelen der hver post i tabellen evalueres. Funksjonen returnerer alle postene som resulterer i **sann**-uttrykk. Du kan referere til kolonner i tabellen. Hvis du oppgir mer enn én formel, kombineres resultatene av alle formlene med funksjonen **[And](function-logicals.md)**.

**Search**( *Table*, *SearchString*, *Column1* [, *Column2*, ... ] )

* *Table* – obligatorisk. Tabell det skal søkes i.
* *SearchString* – obligatorisk. Strengen som du vil finne. Hvis strengen er *tom*, returneres alle postene.
* *Column(s)* – obligatorisk. Navene på kolonnene som du søker etter, i *Table*. Kolonnene du søker i, må inneholde tekst. Kolonnenavnene må være strenger og omsluttet av doble anførselstegn. Kolonnenavnene må imidlertid være statiske og kan ikke beregnes med en formel. Hvis *SearchString* finnes blant dataene i noen av disse kolonnene som delvise treff, returneres den fullstendige posten.

> [!NOTE]
> Du må spesifisere hvert mellomrom med **"\_x0020\_"** for SharePoint- og Excel-datakilder som inneholder kolonnenavn med mellomrom. Du kan for eksempel angi **"ColumnName"** som **"Column_x0020_Name"**.

**LookUp**( *Table*, *Formula* [, *ReductionFormula* ] )

* *Table* – obligatorisk. Tabell det skal søkes i. Syntaksen vises som *kilde* i brukergrensesnittet, ovenfor funksjonsboksen.
* *Formula* – obligatorisk.
  Formelen der hver post i tabellen evalueres. Funksjonen returnerer den første posten som resulterer i et **sann**-uttrykk. Du kan referere til kolonner i tabellen. Syntaksen vises som *vilkår* i brukergrensesnittet, ovenfor funksjonsboksen.
* *ReductionFormula* – valgfritt. Denne formelen evalueres over posten som ble funnet, og reduserer deretter posten til en enkeltverdi. Du kan referere til kolonner i tabellen. Hvis du ikke bruker denne parameteren, returnerer funksjonen den fullstendige posten fra tabellen. Syntaksen vises som *resultat* i brukergrensesnittet, ovenfor funksjonsboksen.

## <a name="examples"></a>Eksempler
Følgende eksempler bruker **IceCream** som [datakilde](../working-with-data-sources.md):

![](media/function-filter-lookup/icecream.png)

| Formel | Beskrivelse | Resultat |
| --- | --- | --- |
| **Filter( IceCream, OnOrder > 0 )** |Returnerer poster der **OnOrder** er større enn null. |<style> img { max-width: none; } </style> ![](media/function-filter-lookup/icecream-onorder.png) |
| **Filter( IceCream, Quantity + OnOrder > 225 )** |Returnerer poster der summen av kolonnene **Quantity** og **OnOrder** er større enn 225. |![](media/function-filter-lookup/icecream-overstock.png) |
| **Filter( IceCream, "chocolate" in Lower( Flavor ) )** |Returnerer poster der ordet «chocolate» vises i **Flavor**-navnet, uavhengig av store og små bokstaver. |![](media/function-filter-lookup/icecream-chocolate.png) |
| **Filter( IceCream, Quantity < 10  && OnOrder < 20 )** |Returnerer poster der **Quantity** er mindre enn 10 og **OnOrder** er mindre enn 20.  Ingen poster samsvarer med disse vilkårene, derfor returneres det en tom tabell. |![](media/function-filter-lookup/icecream-empty.png) |
| **Search( IceCream, "choc", "Flavor" )** |Returnerer poster der strengen «choc» vises i **Flavor**-navnet, uavhengig av store og små bokstaver. |![](media/function-filter-lookup/icecream-chocolate.png) |
| **Search( IceCream, "", "Flavor" )** |Siden søkeordet er tomt, returneres alle postene. |![](media/function-filter-lookup/icecream.png) |
| **LookUp( IceCream, Flavor = "Chocolate", Quantity )** |Søker etter en post der **Flavor** er lik «Chocolate», men det finnes ingen.  **Quantity** blir returnert fra den første posten som blir funnet. |100 |
| **LookUp( IceCream, Quantity > 150, Quantity + OnOrder )** |Søker etter en post der **Quantity** er større enn 100, og det finnes flere.  Den første posten som blir funnet, der «Vanilla» er angitt for **Flavor**, returnerer summen av kolonnene **Quantity** og **OnOrder**. |250 |
| **LookUp( IceCream, Flavor = "Pistachio", OnOrder )** |Søker etter en post der **Flavor** er lik «Pistachio», men det finnes ingen.  Siden ingen ble funnet, returnerer **Lookup** et *tom* resultat. |*tom* |
| **LookUp( IceCream, Flavor = "Vanilla" )** |Søker etter en post der **Flavor** er lik «Vanilla», men det finnes ingen.  Siden det ikke ble angitt en reduksjonsformel, returneres hele formelen. |{ Flavor: "Vanilla", Quantity: 200, OnOrder: 75 } |

### <a name="search-user-experience"></a>Brukeropplevelse for søk
I mange apper kan du skrive ett eller flere tegn i en søkeboks for å filtrere en liste over poster i et stort datasett. Mens du skriver, viser listen bare de postene som samsvarer med søkevilkårene.

Eksemplene i resten av dette temaet viser resultatene av å søke i en listen, som heter **Customers**, som inneholder disse dataene:

![](media/function-filter-lookup/customers.png)

Hvis du vil opprette denne datakilden som en samling, oppretter du en **[Knapp](../controls/control-button.md)**-kontroll og angir egenskapen **OnSelect** til denne formelen:

**ClearCollect( Customers, Table( { Name: "Fred Garcia", Company: "Northwind Traders" }, { Name: "Cole Miller", Company: "Contoso" }, { Name: "Glenda Johnson", Company: "Contoso" }, { Name: "Mike Collins", Company: "Adventure Works" }, { Name: "Colleen Jones", Company: "Adventure Works" } ) )**

Som du ser av dette eksemplet, kan du vise en liste over poster i en [**Galleri-kontroll**](../controls/control-gallery.md) nederst på skjermen. Nær toppen av skjermen kan du legge til en [**Tekstinndata**](../controls/control-text-input.md)-kontroll, som heter **SearchInput**, slik at brukerne kan angi hvilke poster de har interesse av.

![](media/function-filter-lookup/customers-ux-unfiltered.png)

Mens de skriver tegn i **SearchInput**, filtreres resultatene i galleriet automatisk. I dette tilfellet er galleriet konfigurert til å vise poster der navnet på kunden (ikke navnet på firmaet) begynner med tegnsekvensen i **SearchInput**. Hvis brukeren skriver **bj** i søkeboksen, viser galleriet disse resultatene:

![](media/function-filter-lookup/customers-ux-startswith-co.png)

Hvis du vil filtrere basert på kolonnen **Name**, angir du egenskapen **Items** for Galleri-kontrollen til én av disse formlene:

| Formel | Beskrivelse | Resultat |
| --- | --- | --- |
| **Filter( Customers, StartsWith( Name, SearchInput.Text ) )** |Filtrerer **Kunder**-datakilden for poster der søkestrengen vises i begynnelsen av **Navn**-kolonnen. Testen skiller ikke mellom små og store bokstaver. Hvis brukeren skriver **bj** i søkeboksen, viser galleriet **Bjarne Høgdal** og **Bjørn Rosendal**. Galleriet viser ikke **Finn Andresen**, fordi kolonnen **Name** for den posten begynner ikke med den søkestrengen. |<style> img { max-width: none } </style> ![](media/function-filter-lookup/customers-name-co-startswith.png) |
| **Filter( Customers, SearchInput.Text in Name )** |Filtrerer **Kunder**-datakilden for poster der søkestrengen vises hvor som helst i **Navn**-kolonnen. Testen skiller ikke mellom små og store bokstaver. Hvis brukeren skriver **bj** i søkeboksen, viser galleriet **Bjarne Høgdal,** **Bjørn Rosendal** og **Bjarte Andresen**, fordi søkestrengen finnes et sted **Navn**-kolonnen i alle postene. |<style> img { max-width: none } </style> ![](media/function-filter-lookup/customers-name-co-contains.png) |
| **Search( Customers, SearchInput.Text, "Name" )** |Funksjonen **Search** ligner på operatoren **in**, og den søker etter et treff hvor som helst i **Navn**-kolonnen for hver post. Vær oppmerksom på at du må omslutte kolonnenavnet i doble anførselstegn. |<style> img { max-width: none } </style> ![](media/function-filter-lookup/customers-name-co-contains.png) |

Du kan utvide søket til å inkludere kolonnen **Bedrift** så vel som kolonnen **Navn**:

| Formel | Beskrivelse | Resultat |
| --- | --- | --- |
| **Filter( Customers, StartsWith( Name, SearchInput.Text ) &#124;&#124; StartsWith( Company, SearchInput.Text ) )** |Filtrerer datakilden **Customers** for posten der enten kolonnen **Name** eller **Company** begynner med søkestrengen (for eksempel **bj**).  Operatoren [**&#124;&#124;** ](operators.md) er *sann* hvis begge funksjonene **StartsWith** er *sann*. |<style> img { max-width: none } </style> ![](media/function-filter-lookup/customers-all-co-startswith.png) |
| **Filter( Customers, SearchInput.Text in Name &#124;&#124; SearchInput.Text in Company )** |Filtrerer **Kunder**-datakilden for posten der enten **Navn**-kolonnen eller **Bedrift**-kolonnen inneholder søkestrengen (for eksempel **bj**). |<style> img { max-width: none } </style> ![](media/function-filter-lookup/customers-all-co-contains.png) |
| **Search( Customers, SearchInput.Text, "Name", "Company" )** |Funksjonen **Search** ligner på operatoren **in**, og den søker i datakilden **Kunder** etter posten der enten **Navn**-kolonnen eller **Bedrift**-kolonnen inneholder søkestrengen (for eksempel **bj**). Funksjonen **Search** er enklere å lese og skrive enn **Filter** hvis du ønsker å angi flere kolonner og operatorer som **in**. Vær oppmerksom på at du må omslutte kolonnenavnet i doble anførselstegn. |<style> img { max-width: none } </style> ![](media/function-filter-lookup/customers-all-co-contains.png) |

