---
title: Patch-funksjonen | Microsoft Docs
description: Referanseinformasjon, inkludert syntaks og eksempler for Patch-funksjonen i PowerApps
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 10/21/2015
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 3adb036a1619263d2b8cef1f649c2d2f97925ceb
ms.sourcegitcommit: 825daacc9a812637815afc1ce6fad28f0cebd479
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/04/2019
ms.locfileid: "57803140"
---
# <a name="patch-function-in-powerapps"></a>Patch-funksjonen i PowerApps
Endrer eller oppretter én eller flere [poster](../working-with-tables.md#records) i en [datakilde](../working-with-data-sources.md), eller fletter poster utenfor en datakilde.

Bruk **Patch**-funksjonen til å endre poster i komplekse situasjoner, for eksempel når du utfører oppdateringer som ikke krever noen brukermedvirkning eller bruker skjemaer som strekker seg over flere skjermbilder.

I mindre kompliserte situasjoner kan du bruke kontrollen **Rediger skjema** for å oppdatere poster i en datakilde på en enklere måte. Når du legger til en **Rediger skjema**-kontroll, gir du brukerne et skjema som skal fylles ut og lagrer deretter endringene i en datakilde. Hvis du vil ha mer informasjon, kan du se [Forstå dataskjemaer](../working-with-forms.md).

## <a name="overview"></a>Oversikt
Bruk **Patch**-funksjonen til å endre én eller flere poster i en datakilde.  Verdiene for spesifikke [felter](../working-with-tables.md#elements-of-a-table) blir endret uten å påvirke andre egenskaper. Denne formelen endrer for eksempel telefonnummeret for en kunde kalt Contoso:

`Patch( Customers, First( Filter( Customers, Name = "Contoso" ) ), { Phone: “1-212-555-1234” } )`

Bruk **Patch** med **[Defaults](function-defaults.md)**-funksjonen for å opprette poster. Bruk denne virkemåten til å bygge ett [enkelt skjermbilde](../working-with-data-sources.md) for både oppretting og redigering av poster. Denne formelen oppretter for eksempel en post for en kunde kalt Contoso:

`Patch( Customers, Defaults( Customer ), { Name: “Contoso” } )`

Selv om du ikke jobber med en datakilde, kan du bruke **Patch** til å slå sammen to eller flere poster. Denne formelen fletter for eksempel to poster til én, som identifiserer både telefonnummeret og plasseringen for Contoso:

`Patch( { Name: "Contoso", Phone: “1-212-555-1234” }, { Name: "Contoso", Location: “Midtown”  } )`

## <a name="description"></a>Beskrivelse
### <a name="modify-or-create-a-record-in-a-data-source"></a>Å endre eller opprette en post i en datakilde
Hvis du vil bruke denne funksjonen med en datakilde, kan du angi datakilden og deretter angi en grunnleggende post:

* Hvis du vil endre en post, må den grunnleggende posten ha kommet fra en datakilde.  Den grunnleggende posten kan ha blitt levert gjennom **[Items](../controls/properties-core.md)**-egenskapen i et galleri, blitt plassert i en [kontekstvariabel](../working-with-variables.md#use-a-context-variable) eller gått gjennom en annen bane. Men du skal kunne spore den grunnleggende posten tilbake til datakilden.  Dette er viktig, da posten inneholder tilleggsinformasjon for å hjelpe deg med å finne posten på nytt for redigering.  
* Hvis du vil opprette en post, kan du bruke **[Defaults](function-defaults.md)**-funksjonen til å opprette en grunnleggende post med standardverdier.  

Deretter kan du angi én eller flere endringsposter, der hver av dem inneholder nye egenskapsverdier som overstyrer egenskapsverdiene i den grunnleggende posten. Endringsposter behandles i rekkefølgen fra begynnelsen av argumentlisten til slutten, der nyere egenskapsverdier overstyrer tidligere verdier.

Returverdien for **Patch** er posten som du har endret eller opprettet.  Hvis du har opprettet en post, kan returverdien inneholde egenskapene som datakilden genererte automatisk.

Når du oppdaterer en datakilde, kan det oppstå et eller flere problemer. Bruk **[Errors](function-errors.md)**-funksjonen til å identifisere og undersøke problemer, som beskrives i [Working with large data sources](../working-with-data-sources.md) (Å arbeide med store datakilder).

Relaterte funksjoner, inkludert **[Update](function-update-updateif.md)**-funksjonen, kan brukes til å erstatte en hel post, og **[Collect](function-clear-collect-clearcollect.md)**-funksjonen kan brukes til å opprette en post.  Du kan bruke **[UpdateIf](function-update-updateif.md)**-funksjonen til å endre bestemte egenskaper for flere poster basert på en betingelse.

### <a name="modify-or-create-a-set-of-records-in-a-data-source"></a>Å endre eller opprette et sett med poster i en datakilde
**Patch** kan også brukes til å opprette eller endre flere poster med ett enkelt oppkall.

I stedet for å sende én grunnleggende post kan en tabell med grunnleggende poster angis i det andre argumentet.  Endringsposter er også inkludert i en tabell, tilsvarende én-til-én med de grunnleggende postene.  Antallet poster i hver endringstabell må være den samme som antallet poster i den grunnleggende tabellen.

Når du bruker **Patch** på denne måten, er returverdien også en tabell med hver post tilsvarende én-til-én for de grunnleggende postene og endringspostene.

### <a name="merge-records-outside-of-a-data-source"></a>Å flette poster utenfor en datakilde
Angi to eller flere poster som du vil flette. Poster behandles i rekkefølgen fra begynnelsen av argumentlisten til slutten, der nyere egenskapsverdier overstyrer tidligere verdier.

**Patch** returnerer den flettede posten og endrer ikke tilhørende argumenter eller poster i noen datakilder.

## <a name="syntax"></a>Syntaks
#### <a name="modify-or-create-a-record-in-a-data-source"></a>Å endre eller opprette en post i en datakilde
**Patch**( *DataSource*, *BaseRecord*, *ChangeRecord1* [, *ChangeRecord2*, … ])

* *DataSource* – obligatorisk. Datakilden som inneholder posten du vil endre, eller som skal inneholde posten du vil opprette.
* *BaseRecord* – obligatorisk. Posten som skal endres eller opprettes.  Hvis posten ble levert fra en datakilde, blir posten funnet og endret. Hvis resultatet av **[Defaults](function-defaults.md)** brukes, blir det opprettet en post.
* *ChangeRecord(s)* – obligatorisk.  Én eller flere poster som inneholder egenskaper som skal endres i *BaseRecord*.  Endringsposter behandles i rekkefølgen fra begynnelsen av argumentlisten til slutten, der nyere egenskapsverdier overstyrer tidligere verdier.

#### <a name="modify-or-create-a-set-of-records-in-a-data-source"></a>Å endre eller opprette et sett med poster i en datakilde
**Patch**( *DataSource*, *BaseRecordsTable*, *ChangeRecordTable1* [, *ChangeRecordTable2*, … ] )

* *DataSource* – obligatorisk. Datakilden som inneholder postene du vil endre, eller som skal inneholde postene du vil opprette.
* *BaseRecordTable* – obligatorisk. En tabell med poster som skal endres eller opprettes.  Hvis posten ble levert fra en datakilde, blir posten funnet og endret. Hvis resultatet av **[Defaults](function-defaults.md)** brukes, blir det opprettet en post.
* *ChangeRecordTable(s)* – obligatorisk.  Én eller flere tabeller med poster som inneholder egenskaper som skal endres for hver post i *BaseRecordTable*.  Endringsposter behandles i rekkefølgen fra begynnelsen av argumentlisten til slutten, der nyere egenskapsverdier overstyrer tidligere verdier.

#### <a name="merge-records"></a>Å flette poster
**Patch**( *Record1*, *Record2* [, …] )

* *Record(s)* – obligatorisk.  Minst to poster som du vil flette. Poster behandles i rekkefølgen fra begynnelsen av argumentlisten til slutten, der nyere egenskapsverdier overstyrer tidligere verdier.

## <a name="examples"></a>Eksempler
#### <a name="modify-or-create-a-record-in-a-data-source"></a>Å endre eller opprette en post (i en datakilde)
I disse eksemplene skal du endre eller opprette en post i en datakilde med navnet **IceCream** som inneholder dataene i denne [tabellen](../working-with-tables.md) og genererer verdiene automatisk i **ID**-[kolonnen](../working-with-tables.md#columns):

![](media/function-patch/icecream.png)

| Formel | Beskrivelse | Resultat |
| --- | --- | --- |
| **Patch(&nbsp;IceCream,<br>First( Filter( IceCream, Flavor = "Chocolate" ) ), {&nbsp;Quantity:&nbsp;400&nbsp;} )** |Endrer en post i **IceCream**-datakilden:<ul><li> **ID**-kolonnen for posten som skal endres, inneholder verdien **1**. (**Chocolate**-posten har denne ID-en.)</li><li>Verdien i **Quantity**-kolonnen endres til **400**. |{&nbsp;ID:&nbsp;1, Flavor:&nbsp;"Chocolate", Quantity:&nbsp;400 }<br><br>**Chocolate**-posten i datakilden **IceCream** har blitt endret. |
| **Patch( IceCream, Defaults(&nbsp;IceCream ), {&nbsp;Flavor:&nbsp;“Strawberry”&nbsp;}&nbsp;)** |Oppretter en post i **IceCream**-datakilden:<ul><li>**ID**-kolonnen inneholder verdien **3**, som datakilden genererer automatisk.</li><li>**Quantity**-kolonnen inneholder **0**, som er standardverdien for kolonnen i datakilden **IceCream**, som **[Defaults](function-defaults.md)**-funksjonen angir.<li>**Flavor**-kolonnen inneholder verdien for **Strawberry**.</li> |{ ID:&nbsp;3, Flavor:&nbsp;“Strawberry”, Quantity:&nbsp;0&nbsp;}<br><br>**Strawberry**-posten i datakilden **IceCream** har blitt opprettet. |

Når de forrige formlene har blitt vurdert, avsluttes datakilden med disse verdiene:

![](media/function-patch/icecream-after.png)

#### <a name="merge-records-outside-of-a-data-source"></a>Å flette poster (utenfor en datakilde)

| Formel | Beskrivelse | Resultat |
| --- | --- | --- |
| **Patch(&nbsp;{&nbsp;Name:&nbsp;"James",&nbsp;Score:&nbsp;90&nbsp;}, {&nbsp;Name:&nbsp;"Jim",&nbsp;Passed:&nbsp;true&nbsp;} )** |Fletter to poster utenfor en datakilde:<br><ul><li>Verdiene i **Navn**-kolonnen for hver post samsvarer ikke. Resultatet inneholder verdien (**Jim**) i posten som er nærmere slutten av argumentlisten, i stedet for verdien (**James**) i posten som er nærmere begynnelsen.</li><li>Den første posten inneholder en kolonne (**Score**) som ikke finnes i den andre posten. Resultatet inneholder kolonnen med den tilhørende verdien (**90**).</li><li>Den andre posten inneholder en kolonne (**Passed**) som ikke finnes i den første posten. Resultatet inneholder kolonnen med den tilhørende verdien (**true**). |{&nbsp;Name:&nbsp;"Jim", Score:&nbsp;90, Passed:&nbsp;true&nbsp;} |

