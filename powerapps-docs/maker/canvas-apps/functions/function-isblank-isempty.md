---
title: Funksjonene Blank, Coalesce, IsBlank og IsEmpty | Microsoft Docs
description: Referanseinformasjon for funksjonene Blank, Coalesce, IsBlank og IsEmpty i PowerApps, inkludert syntaks og eksempler
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.component: canvas
ms.date: 07/24/2017
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: e31d3689c7b61c408be90c31f1e212e4fdd9a91c
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/24/2018
ms.locfileid: "42848987"
---
# <a name="blank-coalesce-isblank-and-isempty-functions-in-powerapps"></a>Funksjonene Blank, Coalesce, IsBlank og IsEmpty i PowerApps
Tester om en verdi er tom eller en [tabell](../working-with-tables.md) inneholder ingen [poster](../working-with-tables.md#records), og gir en måte å opprette *tom*-verdier på.

## <a name="overview"></a>Oversikt
*Tom* er en plassholder for «ingen verdi» eller «ukjent verdi». En **[tekstinndata](../controls/control-text-input.md)**-kontroll er *tom* hvis brukeren ikke har skrevet inn noen tegn i den. Den samme kontrollen er ikke lenger *tom* så snart brukeren skriver inn et tegn i den.  Noen datakilder kan lagre og returnere NULL-verdier, som representeres i PowerApps som *tom*.

> [!NOTE]
> For øyeblikket støttes lagring av *tom*-verdier bare for lokale samlinger. Vi vet at mange datakilder støtter *tom*-verdier (NULL), og vi jobber med å fjerne denne begrensningen.

Alle egenskaper eller beregnede verdier kan være *tom*.  En boolsk verdi har for eksempel vanligvis én av to verdier: **sann** eller **usann**.  Men i tillegg til disse to kan den også være *tom*.  Dette ligner på Microsoft Excel, der en regnearkcelle tar utgangspunkt i å være tom men kan inneholde blant annet verdiene **sann** eller **usann**. Du kan fjerne innholdet i cellen når som helst, og cellen vil da gå tilbake til en *tom* tilstand.

*Tom* er spesifikk for tabeller som ikke inneholder noen poster. Tabellstrukturen kan være intakt, komplett med [kolonnenavn](../working-with-tables.md#columns), men det er ingen data i tabellen. En tabell kan starte som tom, ta med poster, og ikke lenger være tom, og deretter få postene fjernet og igjen være tom.

## <a name="description"></a>Beskrivelse
**Blank**-funksjonen returnerer en *tom* verdi. Bruk denne til å lagre en NULL-verdi i en datakilde som støtter disse verdiene. Dette fjerner enhver verdi fra feltet.

**IsBlank**-funksjonen tester for en *tom*-verdi. *Tom*-verdier finnes i situasjoner som for eksempel:

* Verdien som returneres fra **Blank**-funksjonen.
* En kontrollegenskap har ingen formel som er angitt for den.
* Ingen verdi er skrevet inn i en kontroll for innskriving av tekst, eller ingen valg er gjort i en listeboks. Du kan bruke **IsBlank** til å gi tilbakemelding om at et felt er obligatorisk.
* En streng som ikke inneholder noen tegn, har en **[Len](function-len.md)** på 0.
* Det oppstod en feil i en funksjon. Ofte var ett av argumentene til funksjonen ugyldig. Mange funksjoner returnerer *tom* hvis verdien for et argument er *tom*.
* Tilkoblede [datakilder](../working-with-data-sources.md), for eksempel SQL Server, kan bruke «nullverdier». Disse verdiene vises som *tom* i PowerApps.
* *Annet*-delen av en **[If](function-if.md)**-funksjon var ikke angitt, og alle betingelsene var **usann**.
* Du brukte **[Update](function-update-updateif.md)**-funksjonen, men spesifiserte ikke en verdi for alle kolonnene. Derfor ble ingen verdier plassert i kolonnene som du ikke anga.

**Coalesce**-funksjonen evaluerer argumentene i rekkefølge og returnerer den første verdien som ikke er *tom*.  Bruk denne funksjonen til å erstatte en *tom* verdi med en annen verdi, men la ikke-*tom*-verdier forbli uendret.  Hvis alle argumentene er *tom*, returnerer funksjonen *tom*.  Alle argumentene til **Coalesce** må være av samme type. Du kan for eksempel ikke blande tall med tekststrenger.  **Coalesce( value1, value2 )** er den mer konsise utgaven som tilsvarer **If( Not( IsBlank( value1 ) ), value1, value2 )** og ikke krever **value1** for å bli evaluert to ganger.  

**IsEmpty**-funksjonen tester om tabellen inneholder noen poster. Det tilsvarer å bruke **[CountRows](function-table-counts.md)**-funksjonen og se etter null. Du kan se etter datakildefeil ved å kombinere **IsEmpty**-funksjonen med **[Errors](function-errors.md)**-funksjonen.

Returverdien for både **IsBlank** og **IsEmpty** er en boolsk **sann** eller **usann**.

## <a name="syntax"></a>Syntaks
**Blank**()

**Coalesce**( *Value1* [, *Value2*, ... ] )

* *Value(s)* – obligatorisk. Verdier å teste.  Hver verdi blir evaluert i rekkefølge frem til en ikke-*tom* verdi blir funnet.  Verdier etter den første ikke-*tomme*-verdien blir ikke evaluert.  

**IsBlank**( *Verdi* )

* *Verdi* – obligatorisk. Verdien som skal testes.

**IsEmpty**( *Tabell* )

* *Tabell* – obligatorisk. Tabell som skal testes for poster.

## <a name="examples"></a>Eksempler
### <a name="blank"></a>Tom
> [!NOTE]
> På dette tidspunktet fungerer det følgende eksemplet bare for lokale samlinger.  Vi vet at mange datakilder støtter *tom*-verdier (NULL), og vi jobber med å fjerne denne begrensningen.

1. Opprett en app fra grunnen av, og legg til en **Knapp**.
2. Sett knappens **[OnSelect](../controls/properties-core.md)**-egenskap til denne formelen:

    **ClearCollect( Cities, { Name: "Seattle", Weather: "Rainy" } )**
3. Forhåndsvis appen, klikk eller trykk på knappen som du har lagt til, og lukk deretter Forhåndsvisning.  
4. Klikk eller trykk på **Samlinger** på **Fil**-menyen.

     Samlingen **Byer** vises, som viser én post med «Seattle» og «Regn»:

    ![Samlingen som viser Seattle med regnvær](./media/function-isblank-isempty/seattle-rainy.png)
5. Klikk eller trykk på Tilbake-pilen for å gå tilbake til standardarbeidsområdet.
6. Legg til en **Etikett**-kontroll, og angi **Tekst**-egenskapen til denne formelen:

    **IsBlank( First( Cities ).Weather )**

    Etiketten viser **usann** fordi **Vær**-feltet inneholder en verdi («Regn»).
7. Legg til en annen knapp, og angi knappens **OnSelect**-egenskap til denne formelen:

    **Patch( Cities, First( Cities ), { Weather: Blank() } )**
8. Forhåndsvis appen, klikk eller trykk på knappen som du har lagt til, og lukk deretter Forhåndsvisning.  

    **Vær**-feltet i den første posten i **Byer** erstattes med et *tom*-felt, og fjerner dermed «Regn», som stod der tidligere.

    ![Samling som viser Seattle med blankt værfelt](./media/function-isblank-isempty/seattle-blank.png)

    Etiketten viser **usann** fordi **Vær**-feltet ikke lenger inneholder en verdi.

### <a name="coalesce"></a>Oppsamling

| Formel | Beskrivelse | Resultat |
| --- | --- | --- |
| **Coalesce( Blank(), 1 )** |Tester returverdien fra **tom**-funksjonen, som alltid returnerer en *tom* verdi. Fordi det første argumentet er *tom*, fortsetter evalueringen med det neste argumentet til en ikke-*tom* verdi blir funnet. |**1** |
| **Coalesce( Blank(), Blank(), Blank(), Blank(), 2, 3 )** |**Oppsamling** starter i begynnelsen av argumentlisten og evaluerer hvert argument i tur og orden til en ikke-*tom* verdi blir funnet.  I dette tilfellet returnerer de første fire argumentene alle *tom*, slik at evalueringen fortsetter til det femte argumentet. Det femte argumentet er ikke-*tomt*, slik at evalueringen stopper her. Verdien til det femte argumentet returneres, og det sjette argumentet evalueres ikke. |**2** |

### <a name="isblank"></a>IsBlank
1. Opprett en app fra grunnen av, legg til en kontroll for innskriving av tekst og gi den navnet **FirstName**.
2. Legg til en etikett, og angi **[Tekst](../controls/properties-core.md)**-egenskapen til denne formelen:

    **If( IsBlank( FirstName.Text ), "First Name is a required field." )**

    Som standard er **[Tekst](../controls/properties-core.md)**-egenskapen til en tekstinndatakontroll satt til **«Tekstinndata»**. Fordi egenskapen inneholder en verdi, er den ikke tom, og etiketten viser ikke noen melding.
3. Fjern alle tegnene fra tekstinndatakontrollen, inkludert mellomrom.

    Fordi **[Tekst](../controls/properties-core.md)**-egenskapen ikke lenger inneholder tegn, er den *tom*, og **IsBlank( FirstName.Text )** vil være **sann**. Den obligatoriske feltmeldingen vises.

Hvis du vil ha informasjon om hvordan du utfører validering ved hjelp av andre verktøy, kan du se **[Validate](function-validate.md)**-funksjonen og [Å arbeide med datakilder](../working-with-data-sources.md).  

Andre eksempler:

| Formel | Beskrivelse | Resultat |
| --- | --- | --- |
| **IsBlank( Blank() )** |Tester returverdien fra **tom**-funksjonen, som alltid returnerer en *tom* verdi. |**sann** |
| **IsBlank( "" )** |En streng som ikke inneholder noen tegn. |**sann** |
| **IsBlank( "Hello" )** |En streng som inneholder ett eller flere tegn. |**usann** |
| **IsBlank( *AnyCollection* )** |Fordi [samlingen](../working-with-data-sources.md#collections) finnes, er den ikke tom, selv om den ikke inneholder noen poster. Hvis du vil se etter en tom samling, kan du bruke **IsEmpty** i stedet. |**usann** |
| **IsBlank( Mid( "Hello", 17, 2 ) )** |Det første tegnet for **[Mid](function-left-mid-right.md)** er utenfor slutten av strengen.  Resultatet er en tom streng. |**sann** |
| **IsBlank( If( false, false ) )** |En **[If](function-if.md)**-funksjon uten *ElseResult*.  Fordi betingelsen alltid er **usann**, returnerer denne **[If](function-if.md)**-funksjonen alltid *tom*. |**sann** |

### <a name="isempty"></a>IsEmpty
1. Opprett en app fra grunnen av, og legg til en **Knapp**.
2. Sett knappens **[OnSelect](../controls/properties-core.md)**-egenskap til denne formelen:

    **Collect( IceCream, { Flavor: "Strawberry", Quantity: 300 }, { Flavor: "Chocolate", Quantity: 100 } )**
3. Forhåndsvis appen, klikk eller trykk på knappen som du har lagt til, og lukk deretter Forhåndsvisning.  

    En samling med navnet **IceCream** opprettes og inneholder disse dataene:

    ![](media/function-isblank-isempty/icecream-strawberry-chocolate.png)

    Denne samlingen har to poster, og er ikke tom. **IsEmpty( IceCream )** returnerer **usann**, og **CountRows( IceCream )** returnerer **2**.
4. Legg til en annen knapp, og angi knappens **[OnSelect](../controls/properties-core.md)**-egenskap til denne formelen:

    **Clear( IceCream )**
5. Forhåndsvis appen, klikk eller trykk på den andre knappen, og lukk deretter Forhåndsvisning.  

    Samlingen er nå tom:

    ![](media/function-isblank-isempty/icecream-clear.png)

    **[Clear](function-clear-collect-clearcollect.md)**-funksjonen fjerner alle postene fra en samling, noe som resulterer i en tom samling. **IsEmpty( IceCream )** returnerer **sann**, og **CountRows( IceCream )** returnerer **0**.

Du kan også bruke **IsEmpty** til å teste om en beregnet tabell er tom, som disse eksemplene viser:

| Formel | Beskrivelse | Resultat |
| --- | --- | --- |
| **IsEmpty( [&nbsp;1,&nbsp;2,&nbsp;3 ] )** |Tabellen med én kolonne inneholder tre poster, og er derfor ikke tom. |**usann** |
| **IsEmpty( [&nbsp;] )** |Tabellen med én kolonne inneholder ingen poster, og er tom. |**sann** |
| **IsEmpty( Filter( [&nbsp;1,&nbsp;2,&nbsp;3&nbsp;], Value > 5 ) )** |Tabellen med én kolonne inneholder ingen verdier som er større enn 5.  Resultatet fra filteret inneholder ingen poster, og er tom. |**sann** |

