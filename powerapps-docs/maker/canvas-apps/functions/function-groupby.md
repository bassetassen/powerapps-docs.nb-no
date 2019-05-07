---
title: Funksjonene GroupBy og Ungroup | Microsoft Docs
description: Referanseinformasjon for funksjonene GroupBy og Ungroup i PowerApps, inkludert syntaks og eksempler
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 04/26/2016
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 5752781cf99a538d76e9dd9197aa4f8b8abce53e
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/23/2019
ms.locfileid: "61563547"
ms.PowerAppsDecimalTransform: true
---
# <a name="groupby-and-ungroup-functions-in-powerapps"></a>Funksjonene GroupBy og Ungroup i PowerApps
Grupperer og deler opp [poster](../working-with-tables.md#records) av en [tabell](../working-with-tables.md).

## <a name="description"></a>Beskrivelse
Funksjonen **GroupBy** returnerer en tabell med poster som er gruppert sammen, basert på verdiene i én eller flere [kolonner](../working-with-tables.md#columns). Poster i den samme gruppen er plassert i én enkelt post. En kolonne som inneholder en nestet tabell av de resterende kolonnene, er lagt til.   

Funksjonen **Ungroup** reverserer **GroupBy**-prosessen. Denne funksjonen returnerer en tabell, og bryter opp alle grupperte poster til separate poster.

Du kan gruppere poster ved hjelp av **GroupBy**, endre tabellen som returneres og deretter dele opp grupper med poster i tabellen som er endret ved hjelp av **Ungroup**. Du kan for eksempel fjerne en gruppe av poster ved å følge denne fremgangsmåten:

* Bruk **GroupBy**-funksjonen.
* Bruk **[Filter](function-filter-lookup.md)**-funksjonen til å fjerne hele gruppen av poster.
* Bruk **Ungroup**-funksjonen.  

Du kan også samle resultater basert på en gruppering:

* Bruk **GroupBy**-funksjonen.
* Bruk **[AddColumns](function-table-shaping.md)**-funksjonen med **[Sum](function-aggregates.md)**, **[Average](function-aggregates.md)**  og andre mengdefunksjoner til å legge til en ny kolonne som er et aggregat av gruppetabellene.
* Bruk funksjonen **[DropColumns](function-table-shaping.md)** for å fjerne gruppetabellen.

**Ungroup** prøver å beholde den opprinnelige rekkefølgen til postene som ble matet til **GroupBy**.  Dette er ikke alltid mulig (for eksempel hvis den opprinnelige tabellen inneholder *tomme* poster).

En tabell er en verdi i PowerApps, akkurat som en streng eller et tall. Du kan angi en tabell som et argument for en funksjon, og en funksjon kan returnere en tabell. **GroupBy** og **Ungroup** endrer ikke en tabell, i stedet tar de en tabell som et argument og returnerer en annen tabell. Hvis du vil ha mer informasjon, kan du se [arbeide med tabeller](../working-with-tables.md).

## <a name="syntax"></a>Syntaks
**GroupBy**( *Table*; *ColumnName1* [; *ColumnName2*; ... ]; *GroupColumnName* )

* *Tabell* – obligatorisk. Tabell som skal grupperes.
* *ColumnName(s)* – obligatorisk.  Kolonnenavnene i *Tabell* som du vil gruppere i poster.  Disse kolonnene blir kolonnene i den resulterende tabellen.
* *GroupColumnName* – obligatorisk.  Kolonnenavn for lagring av postdata er ikke i *ColumnName(s)*.
  
    > [!NOTE]
  > Du må spesifisere hvert mellomrom med **«\_x0020\_»** for SharePoint- og Excel-datakilder som inneholder kolonnenavn med mellomrom. Du kan for eksempel angi **«ColumnName»** som **«Column_x0020_Name»**.

**Ungroup**( *Table*; *GroupColumnName* )

* *Tabell* – obligatorisk. Tabell som skal deles opp.
* *GroupColumnName* – obligatorisk. Kolonnen som inneholder postdata-oppsettet med  **GroupBy**-funksjonen.
  
    > [!NOTE]
  > Du må spesifisere hvert mellomrom med **«\_x0020\_»** for SharePoint- og Excel-datakilder som inneholder kolonnenavn med mellomrom. Du kan for eksempel angi **"ColumnName"** som **"Column_x0020_Name"**.

## <a name="examples"></a>Eksempler
### <a name="create-a-collection"></a>Opprett en samling
1. Legg til en knapp, og angi **[Text](../controls/properties-core.md)**-egenskapen, slik at knappen viser **Original**.
2. Angi **[OnSelect](../controls/properties-core.md)**-egenskapen for **Original**-knappen til denne formelen:

```powerapps-comma   
ClearCollect( CityPopulations; 
    { City: "London";    Country: "United Kingdom"; Population: 8615000}; 
    { City: "Berlin";    Country: "Germany";        Population: 3562000}; 
    { City: "Madrid";    Country: "Spain";          Population: 3165000}; 
    { City: "Rome";      Country: "Italy";          Population: 2874000}; 
    { City: "Paris";     Country: "France";         Population: 2273000}; 
    { City: "Hamburg";   Country: "Germany";        Population: 1760000}; 
    { City: "Barcelona"; Country: "Spain";          Population: 1602000}; 
    { City: "Munich";    Country: "Germany";        Population: 1494000}; 
    { City: "Milan";     Country: "Italy";          Population: 1344000}
)
```

3. Velg **Opprinnelig**-knappen mens du holder nede ALT-tasten.
   
    Du opprettet en [samling](../working-with-data-sources.md#collections), kalt **CityPopulations**, som inneholder disse dataene:
   
    ![](media/function-groupby/cities.png)
4. Velg **Samlinger** i **Fil**-menyen, og velg deretter **CityPopulations**-samlingen for å vise denne samlingen.  De fem første postene i samlingen vises:
   
    ![](media/function-groupby/citypopulations-collection.png)

### <a name="group-records"></a>Grupper poster
1. Legg til en annen knapp, og angi **[Text](../controls/properties-core.md)**-egenskapen til **Group**.
2. Sett **[OnSelect](../controls/properties-core.md)**-egenskapen til denne knappen til denne formelen:
   
    **ClearCollect( CitiesByCountry; GroupBy( CityPopulations; "Country"; "Cities" ) )**
3. Velg **Gruppe**-knappen mens du holder nede ALT-tasten.
   
    Du opprettet en samling, kalt **CitiesByCountry**, hvor poster for den forrige samlingen er gruppert etter **Country**-kolonnen.
   
    ![](media/function-groupby/cities-grouped.png)
4. Velg **Samlinger** i **Fil**-menyen for å vise de fem første postene i denne samlingen.
   
    ![](media/function-groupby/citiesbycountry-collection.png)
5. For å vise befolkningen i byer i et land må du velge tabellikonet i **Cities**-kolonnen for det landet (for eksempel Tyskland):
   
    ![](media/function-groupby/population-germany.png)

### <a name="filter-and-ungroup-records"></a>Filtrer og del opp grupperte poster
1. Legg til en annen knapp, og angi **[Text](../controls/properties-core.md)**-egenskapen, slik at knappen viser **Filter**.
2. Sett **[OnSelect](../controls/properties-core.md)**-egenskapen til denne knappen til den følgende formelen:
   
    **ClearCollect( CitiesByCountryFiltered; Filter( CitiesByCountry; "e" in Country ) )**
3. Velg knappen du la til mens du holder nede ALT-tasten.
   
    Du opprettet en tredje samling, kalt **CitiesByCountryFiltered**, som bare inkluderer landene som har en «e» i navnet (det vil si ikke Spania eller Italia).
   
    ![](media/function-groupby/cities-grouped-hase.png)
4. Legg til en knapp til, og angi **[Text](../controls/properties-core.md)**-egenskapen, slik at knappen viser **Ungroup**.
5. Sett **[OnSelect](../controls/properties-core.md)**-egenskapen til denne knappen til den følgende formelen:
   
    **ClearCollect( CityPopulationsUngrouped; Ungroup( CitiesByCountryFiltered; "Cities" ) )**
   
    Som resulterer i:
   
    ![](media/function-groupby/cities-hase.png)

### <a name="aggregate-results"></a>Samlede resultater
Noe annet vi kan gjøre med en gruppert tabell, er å samle resultatene.  I dette eksemplet skal vi summere befolkningen av de store byene i hvert land.

1. Legg til en annen knapp, og endre **[Text](../controls/properties-core.md)**-egenskapen, slik at knappen viser **Sum**.
2. Angi **[OnSelect](../controls/properties-core.md)**-egenskapen for **Sum**-knappen til denne formelen:
   
    **ClearCollect( CityPopulationsSum; AddColumns( CitiesByCountry; "Sum of City Populations"; Sum( Cities; Population ) ) )**
   
    Som resulterer i:
   
    ![](media/function-groupby/cities-sum.png)
   
    **[AddColumns](function-table-shaping.md)** starter med **CitiesByCountry**-samlingen som grunnlag og legger til en ny kolonne kalt **Sum of City Populations**.  Verdier for denne kolonnen er beregnet rad-for-rad basert på formelen **Sum( Cities; Population )**.  Funksjonen **AddColumns** angir verdien for **Cities**-kolonnen (en tabell) for hver rad, og **[Sum](function-aggregates.md)** legger sammen **Befolkning** for hver rad i denne undertabellen.

    Nå som vi har summen som vi ønsker, kan vi bruke **[DropColumns](function-table-shaping.md)** til å fjerne undertabeller.
  
3. Legg til en annen knapp, og endre **[Tekst](../controls/properties-core.md)**-egenskapen, slik at knappen viser **"SumOnly"**.
4. Angi **[OnSelect](../controls/properties-core.md)**-egenskapen for **"SumOnly"**-knappen til denne formelen:

    **ClearCollect( CityPopulationsSumOnly; DropColumns( CityPopulationsSum; "Cities" ) )**
   
    Som resulterer i:
   
    ![](media/function-groupby/cities-sum-drop-cities.png)
   
    Legg merke til at vi ikke trengte å dele opp grupper med denne tabellen.

