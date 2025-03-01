---
title: Funksjonene AddColumns, DropColumns, RenameColumns og ShowColumns | Microsoft Docs
description: Referanseinformasjon, inkludert syntaks og eksempler, for funksjonene AddColumns, DropColumns, RenameColumns og ShowColumns i PowerApps
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 04/04/2019
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 6f2dfae897a19c66e493cbdecd897df87b8194c2
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/07/2019
ms.locfileid: "71992221"
ms.PowerAppsDecimalTransform: true
---
# <a name="addcolumns-dropcolumns-renamecolumns-and-showcolumns-functions-in-powerapps"></a>Funksjonene AddColumns, DropColumns, RenameColumns og ShowColumns i PowerApps
Former en [tabell](../working-with-tables.md) ved å legge til, slippe, gi nytt navn til og velge dens [kolonner](../working-with-tables.md#columns).

## <a name="overview"></a>Oversikt
Disse funksjonene former en tabell ved å justere kolonnene:

* Reduser en tabell som inneholder flere kolonner ned til en enkeltkolonne for bruk med enkeltkolonne-funksjoner, for eksempel **[Lower](function-lower-upper-proper.md)** eller **[Abs](function-numericals.md)** .  
* Legg til en beregnet kolonne i en tabell (for eksempel en **Total Price**-kolonne som viser resultatet av å multiplisere **Quantity** med **Unit Price**).
* Endre navnet til en kolonne til noe mer meningsfylt. Dette vises til brukere eller brukes i formler.

En tabell er en verdi i PowerApps, akkurat som en streng eller et tall.  Du kan angi en tabell som et argument i en formel, og funksjoner kan returnere en tabell som et resultat.

> [!NOTE]
> Funksjonene som dette emnet beskriver, endrer ikke den opprinnelige tabellen. I stedet tar de tabellen som et argument og returnerer en ny tabell med en transformering aktivert. Hvis du vil ha mer informasjon, kan du se [arbeide med tabeller](../working-with-tables.md).  

Du kan ikke endre kolonnene i en [datakilden](../working-with-data-sources.md) ved hjelp av disse funksjonene. Du må endre dataene i kilden. Du kan legge til kolonner i en [samling](../working-with-data-sources.md#collections) med **[Collect](function-clear-collect-clearcollect.md)** -funksjonen. Se [arbeide med datakilder](../working-with-data-sources.md) for mer informasjon.  

## <a name="description"></a>Beskrivelse
Funksjonen **AddColumns** legger til en kolonne i en tabell, og en formel definerer verdiene i kolonnen. Eksisterende kolonner forblir uendret.

Formelen evalueres for hver post i tabellen.
[!INCLUDE [record-scope](../../../includes/record-scope.md)]

Funksjonen **DropColumns** utelukker kolonner fra en tabell.  Alle andre kolonner forblir uendret. **DropColumns** utelukker kolonner, og **ShowColumns** inkluderer kolonner.

Bruk funksjonen **RenameColumns** til å gi nytt navn til én eller flere kolonner i en tabell ved å gi minst ett argumentpar som angir navnet på en kolonne i tabellen (det gamle navnet som du vil erstatte) og navnet på en kolonne som ikke finnes i tabellen (det nye navnet som du vil bruke). Det gamle navnet må allerede finnes i tabellen, og det nye navnet må ikke finnes. Hvert kolonnenavn kan vises bare én gang i argumentlisten som enten et gammelt eller et nytt kolonnenavn. Hvis du vil gi et eksisterende kolonnenavn som nytt navn til en kolonne, må du først fjerne den eksisterende kolonnen med **DropColumns** eller få den eksisterende kolonnen ut av veien med nytt navn ved å neste én **RenameColumns**-funksjon i en annen.

Funksjonen **ShowColumns** inkluderer kolonner i en tabell og utelukker alle andre kolonner. Du kan bruke **ShowColumns** til å opprette en enkeltkolonnetabell fra en flerkolonnetabell.  **ShowColumns** inneholder kolonner, og **DropColumns** utelukker kolonner.  

Resultatet er en ny tabell med transformasjonen som brukes for alle disse funksjonene. Den opprinnelige tabellen er ikke endret. Du kan ikke endre en eksisterende tabell med en formel. SharePoint, Common Data Service, SQL Server og andre data kilder inneholder verktøy for å endre Kol onnene i lister, enheter og tabeller, som ofte kalles XML-skjemaet. Funksjonene i dette emnet transformerer bare en inn data tabell, uten å endre originalen, til en utdatatabellen for videre bruk.

Argumentene til disse funksjonene støtter delegering. Eksempel: en **filter** funksjon som brukes som et argument for å hente relaterte poster, søker gjennom alle oppføringer, selv om **[dbo]. [ AllListings]-** data kilden inneholder en million rader:

```powerapps-comma
AddColumns( RealEstateAgents; 
    "Listings";  
    Filter(  '[dbo].[AllListings]'; ListingAgentName = AgentName ) 
)
```

Utdataene til disse funksjonene er imidlertid underlagt [grensen for antall poster som ikke er delegering](../delegation-overview.md#non-delegable-limits).  I dette eksemplet returneres bare 500 poster, selv om data kilden for **RealEstateAgents** har 501 eller flere poster.

Hvis du bruker **AddColumns** på denne måten, må **filteret** foreta separate kall til data kilden for hver av disse første postene i **RealEstateAgents**, noe som for år saker mye nettverks chatter. Hvis **[dbo]. [ AllListings]** er liten nok og endres ikke ofte, kan du kalle **Collect** -funksjonen i [**OnStart**](signals.md#app) for å bufre data kilden i appen når den starter. Som et alternativ kan du omstrukturere appen slik at du bare drar i de relaterte postene når brukeren ber om dem.  

## <a name="syntax"></a>Syntaks
**AddColumns**( *Table*; *ColumnName1*; *Formula1* [; *ColumnName2*; *Formula2*; ... ] )

* *Table* – obligatorisk.  Tabellen som funksjonen skal arbeide med.
* *ColumnName(s)* – obligatorisk. Navn på kolonnen(e) som skal legges til.  Du må angi en streng (for eksempel **"Name"** inkludert anførselstegn) for dette argumentet.
* *Formula(s)* – obligatorisk.  Formlene som skal evalueres for hver post. Resultatet er lagt til som verdien for den tilsvarende nye kolonnen. Du kan referere til andre kolonner i tabellen i denne formelen.

**DropColumns**( *Table*; *ColumnName1* [; *ColumnName2*; ... ] )

* *Table* – obligatorisk.  Tabellen som funksjonen skal arbeide med.
* *ColumnName(s)* – obligatorisk. Navn på kolonnen(e) som skal utelates. Du må angi en streng (for eksempel **"Name"** inkludert anførselstegn) for dette argumentet.

**RenameColumns**( *tabell*; *OldColumnName1*; *NewColumnName1* [; *OldColumnName2*; *NewColumnName2*;...])

* *Tabell* – obligatorisk.  Tabellen som funksjonen skal arbeide med.
* *OldColumnName* – obligatorisk. Navnet på en kolonne som skal få nytt navn, fra den opprinnelige tabellen. Dette elementet vises først i argumentparet (eller først i hvert argumentpar hvis formelen inneholder mer enn ett par). Dette navnet må være en streng (for eksempel **"Name"** inkludert doble anførselstegn).
* *NewColumnName* – obligatorisk. Erstatningsnavn. Dette elementet vises sist i argumentparet (eller sist i hvert argumentpar hvis formelen inneholder mer enn ett par). Du må angi en streng (for eksempel **"Customer Name"** inkludert doble anførselstegn) for dette argumentet.

**ShowColumns**( *Table*; *ColumnName1* [; *ColumnName2*; ... ] )

* *Table* – obligatorisk.  Tabellen som funksjonen skal arbeide med.
* *ColumnName(s)* – obligatorisk. Navn på kolonnen(e) som skal inkluderes. Du må angi en streng (for eksempel **"Name"** inkludert anførselstegn) for dette argumentet.

## <a name="examples"></a>Eksempler
Eksemplene i denne delen bruker **IceCreamSales**-datakilden, som inneholder dataene i denne tabellen:

![](media/function-table-shaping/icecream.png)

Ingen av disse eksemplene endrer **IceCreamSales**-datakilden. Hver funksjon transformerer verdien for datakilden som en tabell, og returnerer verdien som et resultat.

| Formel | Beskrivelse | Resultat |
| --- | --- | --- |
| **AddColumns( IceCreamSales; "Revenue"; UnitPrice * QuantitySold )** |Legger til en **Revenue**-kolonne i resultatet.  For hver post evalueres **UnitPrice * QuantitySold**, og resultatet plasseres i den nye kolonnen. |<style> img { max-width: none; } </style> ![](media/function-table-shaping/icecream-add-revenue.png) |
| **DropColumns( IceCreamSales; "UnitPrice" )** |Utelater **UnitPrice**-kolonnen fra resultatet. Bruk denne funksjonen til å utelate kolonner, og bruk **ShowColumns** til å inkludere dem. |![](media/function-table-shaping/icecream-drop-price.png) |
| **ShowColumns( IceCreamSales; "Flavor" )** |Inkluderer bare **Flavor**-kolonnen i resultatet. Bruk denne funksjonen til å inkludere kolonner, og bruk **DropColumns** til å utelate dem. |![](media/function-table-shaping/icecream-select-flavor.png) |
| **RenameColumns( IceCreamSales; "UnitPrice"; "Price")** |Gir nytt navn til kolonnen **enhets pris** i resultatet. |![](media/function-table-shaping/icecream-rename-price.png) |
| **RenameColumns( IceCreamSales; "UnitPrice"; "Price"; "QuantitySold"; "Number")** |Gir nytt navn til kolonnene **UnitPrice** og **QuantitySold** i resultatet. |![](media/function-table-shaping/icecream-rename-price-quant.png) |
| **DropColumns(<br>RenameColumns(<br>AddColumns( IceCreamSales; "Revenue";<br>UnitPrice * QuantitySold );<br>"UnitPrice"; "Price" );<br>"Quantity" )** |Utfører transformeringene av den følgende tabellen i rekkefølge fra innsiden av formelen: <ol><li>Legger til en **Revenue**-kolonne basert på per post-beregningen av **UnitPrice * Quantity**.<li>Endrer navnet **UnitPrice** til **Price**.<li>Utelater **Quantity**-kolonnen.</ol>  Vær oppmerksom på at rekkefølgen er viktig. For eksempel kan vi ikke beregne med **UnitPrice** når den har fått nytt navn. |![](media/function-table-shaping/icecream-all-transforms.png) |

### <a name="step-by-step"></a>Trinn for trinn

La oss prøve noen av eksemplene fra tidligere i dette emnet.  

1. Opprett en samling ved å legge til en **[knapp](../controls/control-button.md)** -kontroll og angi **OnSelect** -egenskapen til denne formelen:

    ```powerapps-comma
    ClearCollect( IceCreamSales; 
        Table(
            { Flavor: "Strawberry"; UnitPrice: 1,99; QuantitySold: 20 }; 
            { Flavor: "Chocolate"; UnitPrice: 2,99; QuantitySold: 45 };
            { Flavor: "Vanilla"; UnitPrice: 1,50; QuantitySold: 35 }
        )
    )
    ```

1. Kjør formelen ved å velge knappen mens du holder nede Alt-tasten.

1. Legg til en ny **knapp** -kontroll, angi **OnSelect** -egenskapen til denne formelen, og kjør den:

    ```powerapps-comma
    ClearCollect( FirstExample; 
        AddColumns( IceCreamSales; "Revenue"; UnitPrice * QuantitySold )
    ) 
    ```
1. Velg **samlinger**på **fil** -menyen, og velg deretter **IceCreamSales** for å vise denne samlingen.
 
    Når denne grafikken vises, ble ikke den andre formelen endret. **AddColumns** -funksjonen brukte **IceCreamSales** som et skrivebeskyttet argument. funksjonen endret ikke tabellen som argumentet refererer til.
    
    ![Samlings visning viser tre poster i salgs avdelingen for is-salg som ikke inkluderer en inntekt-kolonne](media/function-table-shaping/ice-cream-sales-collection.png)

1. Velg **FirstExample**.

    Som denne grafikken viser, returnerer den andre formelen en ny tabell med kolonnen som ble lagt til. **ClearCollect** -funksjonen registrerte den nye tabellen i **FirstExample** -samlingen, noe som ble lagt til i den opprinnelige tabellen etter hvert som den ble overført gjennom funksjonen uten å endre kilden:

    ![Samlings visning viser tre poster i den første eksempel samlingen som inkluderer en ny inntekt-kolonne](media/function-table-shaping/first-example-collection.png)
