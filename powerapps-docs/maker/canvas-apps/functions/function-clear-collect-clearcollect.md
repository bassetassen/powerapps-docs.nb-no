---
title: Funksjonene Collect, Clear og ClearCollect | Microsoft Docs
description: Referanseinformasjon for funksjonene Collect, Clear og ClearCollect i PowerApps, inkludert syntaks og eksempler
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 11/01/2015
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 8a7c52962c23df5f2efcf76c04aeba528e94217c
ms.sourcegitcommit: 464ee88a958dda11c5de5603c608deab6c9cdcab
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/04/2018
ms.locfileid: "48578746"
---
# <a name="collect-clear-and-clearcollect-functions-in-powerapps"></a>Funksjonene Collect, Clear og ClearCollect i PowerApps
Oppretter og tømmer [samlinger](../working-with-data-sources.md#collections) og legger til [poster](../working-with-tables.md#records) i valgt [datakilde](../working-with-data-sources.md).

## <a name="description"></a>Beskrivelse
### <a name="collect"></a>Collect
**Collect**-funksjonen legger til poster i en datakilde. Elementene som skal legges til, kan være:

* En enkeltverdi: Verdien legges inn i **[Verdi](function-value.md)**-feltet i en ny post.  Alle de andre egenskapene forblir [tomme](function-isblank-isempty.md).
* En post: Hver navngitt egenskap legges inn i den tilsvarende egenskapen til en ny post.  Alle de andre egenskapene forblir blanke.
* En [tabell](../working-with-tables.md): Hver post i tabellen legges til som en separat post i datakilden som beskrevet ovenfor. Tabellen legges ikke inn som en nestet tabell i en post. Hvis du vil gjøre dette, må du sette inn tabellen i en post først.

Når funksjonen brukes med en samling, legges ekstra [kolonner](../working-with-tables.md#columns) til etter behov. Kolonnene for andre datakilder er fast for datakilden, og nye kolonner kan ikke legges til.  

Hvis datakilden ikke allerede finnes, oppretter funksjonen en samling.

Samlinger brukes noen ganger til å holde globale variabler eller til å lage en midlertidig kopi av en datakilde. PowerApps er basert på formler som automatisk beregnes på nytt når brukeren samhandler med en app. Samlinger har ikke denne fordelen, og hvis du bruker samlinger, kan det gjøre appen vanskeligere å opprette og forstå. Les om å [jobbe med variabler](../working-with-variables.md) før du bruker samlinger på denne måten.

Du kan også bruke **[Patch](function-patch.md)**-funksjonen til å opprette poster i en datakilde.

**Collect** returnerer den endrede datakilden som en tabell.  **Collect** kan bare brukes i en [formel for virkemåte](../working-with-formulas-in-depth.md).

### <a name="clear"></a>Fjern
**Clear**-funksjonen sletter alle postene i en samling.  Kolonnene i samlingen blir værende.

Legg merke til at **Clear** bare fungerer på samlinger og ikke på andre datakilder.  Du kan bruke **[RemoveIf](function-remove-removeif.md)( *DataSource*, true)** til dette.  Vær forsiktig, ettersom dette vil fjerne alle postene som er lagret for datakilden, og kan påvirke andre brukere.

Du kan bruke **[Remove](function-remove-removeif.md)**-funksjonen til å fjerne poster selektivt.

**Clear** har ingen returverdi.  Funksjonen kan bare brukes i en formel for virkemåte.

### <a name="clearcollect"></a>ClearCollect
**ClearCollect**-funksjonen sletter alle poster fra en samling og legger deretter til et annet sett med poster i samme samling.  **ClearCollect** fungerer som en kombinasjon av **Clear** og deretter **Collect** i én enkelt funksjon.

**ClearCollect** returnerer den endrede samlingen som en tabell.  **ClearCollect** kan bare brukes i en formel for virkemåte.

## <a name="syntax"></a>Syntaks
**Collect**( *DataSource*, *Item*, ...)

* *DataSource* – obligatorisk. Datakilden som du vil legge til data i.  Hvis den ikke allerede finnes, opprettes en ny samling.
* *Item* – obligatorisk.  Én eller flere poster eller tabeller som skal legges til i datakilden.  

**Clear**( *Collection* )

* *Collection* – obligatorisk. Samlingen som du vil tømme.

**ClearCollect**( *Collection*, *Item*, ...)

* *Collection* – obligatorisk. Samlingen som du vil tømme og legge til data i.
* *Item* – obligatorisk.  Én eller flere poster eller tabeller som skal legges til i datakilden.  

## <a name="examples"></a>Eksempler
### <a name="clearing-and-adding-records-to-a-data-source"></a>Fjerne og legge til poster i en datakilde
I disse eksemplene tømmer du en samling som heter **IceCream**, og legger til data.  Datakilden begynner med dette innholdet:

![](media/function-clear-collect-clearcollect/icecream.png)

| Formel | Beskrivelse | Resultat |
| --- | --- | --- |
| **ClearCollect( IceCream, {&nbsp;Flavor:&nbsp;"Strawberry",&nbsp;Quantity:&nbsp;300&nbsp;} )** |Fjerner alle dataene fra samlingen **IceCream** og legger til en post som inneholder et antall jordbæris. |<style> img { max-width: none } </style> ![](media/function-clear-collect-clearcollect/icecream-clearcollect.png)<br><br>Datakilden **IceCream** har også blitt endret. |
| **Collect( IceCream, {&nbsp;Flavor:&nbsp;"Pistachio",&nbsp;Quantity:&nbsp;40&nbsp;}, {&nbsp;Flavor:&nbsp;"Orange",&nbsp;Quantity:&nbsp;200&nbsp;}  )** |Legger til to poster i **IceCream**-samlingen med et antall iskrem med pistasj- og appelsinsmak. |![](media/function-clear-collect-clearcollect/icecream-collect.png)<br><br>Datakilden **IceCream** har også blitt endret. |
| **Clear( IceCream )** |Fjerner alle postene fra **IceCream**-samlingen. |![](media/function-clear-collect-clearcollect/icecream-clear.png)<br><br>Datakilden **IceCream** har også blitt endret. |

### <a name="collect-a-static-list"></a>Samle inn en statisk liste

1. Legg til en knapp, og angi knappens **[OnSelect](../controls/properties-core.md)**-egenskap som denne formelen:<br>**Collect(Products, &quot;Europa&quot;, &quot;Ganymede&quot;, &quot;Callisto&quot;)**
   
    Denne funksjonen oppretter en samling som heter **Products** og inneholder en rad for hvert av tre produktnavn.
    
1. Velg knappen mens du holder nede ALT.

1. (valgfritt) Hvis du vil forhåndsvise samlingen som du opprettet, kan du velge **Samlinger** på **Fil-menyen**.

### <a name="put-a-sharepoint-list-into-a-collection"></a>Legge til en SharePoint-liste i en samling

1. [Opprett en tilkobling til en SharePoint-liste](../connect-to-sharepoint.md). 

1. Legg til en knapp, og angi **[OnSelect](../controls/properties-core.md)**-egenskapen til denne funksjonen, noe som erstatter *ListName* med navnet på SharePoint-listen:<br>
**Collect**(**MySPCollection**, *ListName*)

    Denne funksjonen oppretter en samling som heter **MySPCollection**, og som inneholder de samme dataene som SharePoint-listen.
    
1. Velg knappen mens du holder nede ALT.

1. (valgfritt) Hvis du vil forhåndsvise samlingen som du opprettet, kan du velge **Samlinger** på **Fil-menyen**.

Hvis du vil ha informasjon om hvordan du viser data fra en SharePoint-liste (for eksempel datoer, valg og personer) i et galleri, kan du se [Vis data i et galleri](../connections/connection-sharepoint-online.md#show-data-in-a-gallery). Hvis du vil ha informasjon om hvordan du viser data i et skjema (med rullegardinlister, datovelgere og personvelgere), kan du se [Kontroller for redigeringsskjema og visningsskjema](../controls/control-form-detail.md).
