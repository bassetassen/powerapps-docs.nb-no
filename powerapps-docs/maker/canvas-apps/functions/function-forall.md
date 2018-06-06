---
title: Funksjonen ForAll | Microsoft Docs
description: Referanseinformasjon, inkludert syntaks og eksempler for funksjonen ForEach i PowerApps
services: ''
suite: powerapps
documentationcenter: na
author: gregli-msft
manager: anneta
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 04/26/2016
ms.author: gregli
ms.openlocfilehash: e2e0a0d638f8f0ff5f9924604a43fa38a556f8fe
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/22/2018
ms.locfileid: "30996507"
---
# <a name="forall-function-in-powerapps"></a>Funksjonen ForAll i PowerApps
Beregner verdier og utfører handlinger for alle [poster](../working-with-tables.md#records) i en [tabell](../working-with-tables.md).

## <a name="description"></a>Beskrivelse
Funksjonen **ForAll** evaluerer en formel for alle poster i en tabell.  Formelen kan beregne en verdi og/eller utføre handlinger, som endring av data eller arbeid med en tilkobling.

[!INCLUDE [record-scope](../../../includes/record-scope.md)]

### <a name="return-value"></a>Returverdi
Resultatet fra hver formelevaluering returneres i en tabell, i samme rekkefølge som inndatatabellen.

Hvis resultatet av formelen er en enkeltverdi, vil den ferdige tabellen være en enkeltkolonnetabell.  Hvis resultatet av formelen er en post, vil den ferdige tabellen inneholde poster med samme kolonner som resultatposten.  

Hvis formelresultatet er en *tom* verdi, vil det ikke finnes noen poster i resultattabellen for inndataposten.  I slike tilfeller, vil det være færre poster i resultattabellen enn i kildetabellen.

### <a name="taking-action"></a>Utføre handling
Formelen kan inkludere funksjoner som utfører handling, blant annet endring av poster i en datakilde med funksjonene **[Patch](function-patch.md)** og **[Collect](function-clear-collect-clearcollect.md)**.  Formelen kan også kalle opp metoder ved tilkoblinger.  Flere handlinger kan utføres per post ved bruk av [**;**-operatøren](operators.md). Du kan ikke endre tabellen som funksjonen **ForAll** brukes på.

Når du skriver en formel, må du huske på at poster kan behandles i en hvilken som helst rekkefølge og, når det er mulig, parallelt.  Den første posten i tabellen kan behandles etter den siste posten.  Pass på at du ikke bestiller avhengigheter.  Av denne grunn kan du ikke bruke funksjonene **[UpdateContext](function-updatecontext.md)**, **[Clear](function-clear-collect-clearcollect.md)** og **[ClearCollect](function-clear-collect-clearcollect.md)** i funksjonen **ForAll**, da disse enkelt kan brukes til å inneholde variabler som ville vært mottakelige for denne effekten.  Du kan bruke **[Collect](function-clear-collect-clearcollect.md)**, men rekkefølgen på postene som legges til er ikke definert.

Flere funksjoner som endrer datakilder, inkludert **Collect**, **Remove** og **Update**, returnerer den endrede datakilden som returverdi.  Disse returverdiene kan være store og bruke betydelig med ressurser hvis de returneres for hver post i **ForAll**-tabellen.  Det kan også hende at disse returverdiene ikke er som du forventer, siden **ForAll** kan operere parallelt og kan separere funksjonens bivirkninger slik at de ikke oppnår resultat.  Heldigvis er det slik at hvis returverdien fra **ForAll** ikke brukes, noe som ofte er tilfelle ved funksjoner for dataendring, vil det ikke bli opprettet en returverdi, og det vil ikke være grunn til å bekymre seg over ressurser eller bestilling.  Hvis du imidlertid bruker resultatet fra en **ForAll**, og en av funksjonene returnerer en datakilde, bør du tenke nøye over hvordan du strukturerer resultatet og teste det på mindre datasett først.  

### <a name="alternatives"></a>Alternativer
Mange funksjoner i PowerApps kan behandle mer enn en verdi om gangen ved bruk av en enkeltkolonnetabell.  For eksempel kan funksjonen **Len** behandle en tabell med tekstverdier og returnere en tabell med lengder på samme måte som **ForAll**.  Dette kan fjerne behovet for å bruke **ForAll** i mange tilfeller, og er mer effektivt og enklere å lese.

**ForAll** kan heller ikke delegeres, men det kan andre funksjoner som for eksempel **Filter**.  

### <a name="delegation"></a>Delegering
[!INCLUDE [delegation-no-one](../../../includes/delegation-no-one.md)]

## <a name="syntax"></a>Syntaks
**ForAll**( *Tabell*, *Formel* )

* *Table* – obligatorisk. Tabellen som skal kjøres.
* *Formula* – obligatorisk.  Formelen som skal evalueres for alle postene i *Table*.

## <a name="examples"></a>Eksempler
### <a name="calculations"></a>Beregninger
Følgende eksempler bruker **Squares** som [datakilde](../working-with-data-sources.md):

![](media/function-forall/squares.png)

For å opprette denne datakilden som en samling angir du **Knapp**-kontrollens **OnSelect**-egenskap til denne formelen, åpner Forhåndsvisningsmodus og klikker eller trykker deretter på knappen:

* **ClearCollect( Squares, [ "1", "4", "9" ] )**

| Formel | Beskrivelse | Resultat |
| --- | --- | --- |
| **ForAll(&nbsp;Squares, Sqrt(&nbsp;Value&nbsp;)&nbsp;)**<br><br>**Sqrt(&nbsp;Squares&nbsp;)** |Beregner kvadratroten av **Value**-kolonnen for alle postene i inndatatabellen.  Funksjonen **Sqrt** kan også brukes med en enkeltkolonnetabell, noe som gjør det mulig å utføre dette eksempelet uten å bruke **ForAll**. |<style> img { max-width: none } </style> ![](media/function-forall/sqrt.png) |
| **ForAll(&nbsp;Squares, Power(&nbsp;Value,&nbsp;3&nbsp;)&nbsp;)** |Opphøyer **Value**-kolonnen til tredje potens for alle postene i inndatatabellen.  Funksjonen **Power** støtter ikke enkeltkolonnetabeller. Derfor må **ForAll** brukes i dette tilfellet. |<style> img { max-width: none } </style> ![](media/function-forall/power3.png) |

### <a name="using-a-connection"></a>Bruke en tilkobling
Følgende eksempler bruker **Expressions** som [datakilde](../working-with-data-sources.md):

![](media/function-forall/translate.png)

For å opprette denne datakilden som en samling angir du **Knapp**-kontrollens **OnSelect**-egenskap til denne formelen, åpner Forhåndsvisningsmodus og klikker eller trykker deretter på knappen:

* **ClearCollect( Expressions, [ "Hello", "Good morning", "Thank you", "Goodbye" ] )**

Dette eksempelet bruker også en [Microsoft Translator](../connections/connection-microsoft-translator.md)-tilkobling.  Hvis du vil legge til denne tilkoblingen i appen din, kan du se emnet om hvordan kan [behandle tilkoblinger](../add-manage-connections.md).

| Formel | Beskrivelse | Resultat |
| --- | --- | --- |
| **ForAll( Expressions, MicrosoftTranslator.Translate( Value, "es" ) )** |Oversett innholdet i **Value**-kolonnen til spansk (forkortet «es») for alle postene i Expressions-tabellen. |<style> img { max-width: none } </style> ![](media/function-forall/translate-es.png) |
| **ForAll( Expressions, MicrosoftTranslator.Translate( Value, "fr" ) )** |Oversett innholdet i **Value**-kolonnen til fransk (forkortet «fr») for alle postene i Expressions-tabellen. |<style> img { max-width: none } </style> ![](media/function-forall/translate-fr.png) |

### <a name="copying-a-table"></a>Kopiere en tabell
Noen ganger trenger du å filtrere, bearbeide, sortere og manipulere data.  PowerApps tilbyr en rekke funksjoner for å gjøre dette, blant annet **Filter**, **AddColumns** og **Sort**.  PowerApps behandler hver tabell som en verdi, slik at den kan flyte gjennom formler og være enkel i bruk.      

Noen ganger vil du også lage en kopi av resultatet for senere bruk.  Eller du vil flytte informasjon fra en datakilde til en annen.  PowerApps tilbyr funksjonen **Collect** for å kopiere data.

Før du kopierer, bør du likevel tenke nøye over om det virkelig er nødvendig.  Mange situasjoner kan løses ved å filtrere og forme den underliggende datakilden etter behov med en formel. Noen av ulempene ved å lage en kopi er som følger:

* To kopier av den samme informasjonen betyr at én av dem kan bli usynkronisert.  
* En kopi kan bruke opp mye av datamaskinens minne, nettverksbåndbredde og/eller tid.  
* For de fleste datakilder kan ikke kopiering delegeres, noe som begrenser hvor mye data som kan flyttes.      

Følgende eksempler bruker **Products** som [datakilde](../working-with-data-sources.md):

![](media/function-forall/prod.png)

For å opprette denne datakilden som en samling angir du **Knapp**-kontrollens **OnSelect**-egenskap til denne formelen, åpner Forhåndsvisningsmodus og klikker eller trykker deretter på knappen:

* **ClearCollect( Products, Table( { Product: "Widget", 'Quantity Requested': 6, 'Quantity Available': 3 }, { Product: "Gadget", 'Quantity Requested': 10, 'Quantity Available': 20 }, { Product: "Gizmo", 'Quantity Requested': 4, 'Quantity Available': 11 }, { Product: "Apparatus", 'Quantity Requested': 7, 'Quantity Available': 6 } ) )**

Målet vårt er å arbeide med en avledet tabell som kun inkluderer elementer der det har blitt forspurt flere enn det antallet som er tilgjengelig, og som vi trenger å bestille:

![](media/function-forall/prod-order.png)  

Vi kan utføre denne oppgaven på forskjellige måter, der alle gir det samme resultatet, med ulike fordeler og ulemper.

#### <a name="table-shaping-on-demand"></a>Tabellbearbeiding ved behov
Ikke lag den kopien!  Vi kan bruke følgende formel hvor som helst etter behov:

* **ShowColumns( AddColumns( Filter( Products, 'Quantity Requested' > 'Quantity Available' ), "Quantity To Order", 'Quantity Requested' - 'Quantity Available' ), "Product", "Quantity To Order" )**

[Omfanget av en post](../working-with-tables.md#record-scope) opprettes med funksjonene **Filter** og **AddColumns** for å utføre henholdsvis operasjonene sammenligning og subtraksjon, med feltene  **'Quantity Requested'** og **'Quantity Available'** for hver post.

I dette eksempelet kan funksjonen **Filter** delegeres.  Dette er viktig ettersom den kan finne alle produkter som oppfyller kriteriet, selv om dette kun er noen få poster i en tabell med millioner av poster.  På dette tidspunktet kan ikke **ShowColumns** og **AddColumns** delegeres, noe som betyr at det faktiske antallet produkter som må bestilles, vil være begrenset.  Hvis du vet at størrelsen på dette resultatet alltid vil være relativt liten, vil denne tilnærmingen fungere helt greit.

Siden vi ikke lagde en kopi, vil det ikke finnes noen ekstra kopi av informasjonen som må administreres eller som kan utdateres.  

#### <a name="forall-on-demand"></a>ForAll ved behov
En annen fremgangsmåte er å bruke funksjonen **ForAll** til å erstatte funksjonene for tabellbearbeiding :

* **ForAll( Products, If( 'Quantity Requested' > 'Quantity Available', { Product: Product, 'Quantity To Order': 'Quantity Requested' - 'Quantity Available' } ) )**

Denne formelen kan være lettere å lese og skrive for noen personer.

Ingen deler av **ForAll** kan delegeres.  Kun den første delen av **Products**-tabellen vil evalueres, noe som kan bli et problem hvis tabellen er veldig stor.  Siden **Filter** kunne delegeres i forrige eksempel, kan den fungere bedre med store datasett.

#### <a name="collect-the-result"></a>Samle inn resultatet
I noen tilfeller kan en kopi av data være nødvendig.  Det kan hende at du må flytte informasjon fra én datakilde til en annen.  I dette eksempelet legges ordrer inn gjennom en **NewOrder**-tabell i et leverandørsystem.  For å oppnå brukersamhandling med høy hastighet kan det hende at du vil bufre en lokal kopi av tabellen for å unngå serverventetid.

Vi bruker den samme tabellbearbeidingen som i de to forrige eksemplene, men vi registrerer resultatet i en samling:

* **ClearCollect( NewOrder, ShowColumns( AddColumns( Filter( Products, 'Quantity Requested' > 'Quantity Available' ), "Quantity To Order", 'Quantity Requested' - 'Quantity Available' ), "Product", "Quantity To Order" ) )**
* **ClearCollect( NewOrder, ForAll( Products, If( 'Quantity Requested' > 'Quantity Available', { Product: Product, 'Quantity To Order': 'Quantity Requested' - 'Quantity Available' } ) ) )**

**ClearCollect** og **Collect** kan ikke delegeres.  Dette betyr at det er en begrensning på hvor mye data som kan flyttes på denne måten.

#### <a name="collect-within-forall"></a>Samle inn innenfor ForAll
Til slutt kan vi utføre **Collect**funksjonen direkte i **ForAll**:

* **Clear( ProductsToOrder ); ForAll( Products, If( 'Quantity Requested' > 'Quantity Available', Collect( NewOrder, { Product: Product, 'Quantity To Order': 'Quantity Requested' - 'Quantity Available' } ) ) )**

Funksjonen **ForAll** kan fortsatt ikke delegeres på dette tidspunktet.  Hvis **Products**-tabellen er stor, vil **ForAll** kun se på det første settet med poster, og det kan hende at vi går glipp av noen produkter som må bestilles.  Denne tilnærmingen er likevel grei for tabeller som vi vet at vil forbli små.

Vær oppmerksom på at vi ikke registrer resultatet fra **ForAll**.  Oppkall av **Collect**-funksjonen utført fra innsiden av funksjonen vil returnere **NewOrder**-datakilden for alle postene, noe som kan føre til store menger data hvis vi skulle registrert det.  

