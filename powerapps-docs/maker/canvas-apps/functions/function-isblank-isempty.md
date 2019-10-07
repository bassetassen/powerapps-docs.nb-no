---
title: Funksjonene Blank, Coalesce, IsBlank og IsEmpty | Microsoft Docs
description: Referanseinformasjon for funksjonene Blank, Coalesce, IsBlank og IsEmpty i PowerApps, inkludert syntaks og eksempler
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.component: canvas
ms.date: 08/27/2019
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: d932d43bd9474f3cd7ca63ef0ef0a51a9e74ca91
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/07/2019
ms.locfileid: "71984750"
---
# <a name="blank-coalesce-isblank-and-isempty-functions-in-powerapps"></a>Funksjonene Blank, Coalesce, IsBlank og IsEmpty i PowerApps
Tester om en verdi er tom eller en [tabell](../working-with-tables.md) inneholder ingen [poster](../working-with-tables.md#records), og gir en måte å opprette *tom*-verdier på.

## <a name="overview"></a>Oversikt
*Tom* er en plassholder for «ingen verdi» eller «ukjent verdi».  En **[kombinasjons boks](../controls/control-combo-box.md)** kontrollens **valgte** egenskap er *tom* hvis brukeren ikke har valgt et valg. Mange data kilder kan lagre og returnere NULL verdier, som er representert i PowerApps som *tomme*.

Enhver egenskap eller beregnet verdi i PowerApps kan være *tom*.  En boolsk verdi har for eksempel vanligvis én av to verdier: **sann** eller **usann**.  Men i tillegg til disse to, kan den også være *tom* , noe som angir at tilstanden ikke er kjent.  Dette ligner på Microsoft Excel, der en regne ark celle starter som Tom uten innhold, men som kan inneholde verdiene **sann** eller **Usann** (blant annet). Innholdet i cellen kan når som helst tømmes på nytt, slik at den returneres til en *tom* tilstand.

En *tom streng* refererer til en streng som ikke inneholder noen tegn.  [ **Len** -funksjonen](function-len.md) returnerer null for en slik streng, og den kan skrives i formler som to doble anførsels tegn med ingenting mellom `""`.  Noen kontroller og data kilder bruker en tom streng for å angi betingelsen «no Value».  For å forenkle oppretting av apper kan du teste **IsBlank** **og samle** funksjoner for både *tomme* verdier eller tomme strenger.    

I konteksten til **IsEmpty** -funksjonen, er *tom* spesifikk for tabeller som ikke inneholder noen poster. Tabellstrukturen kan være intakt, komplett med [kolonnenavn](../working-with-tables.md#columns), men det er ingen data i tabellen. En tabell kan starte som tom, ta med poster, og ikke lenger være tom, og deretter få postene fjernet og igjen være tom.

> [!NOTE]
> Vi er i en overgangs periode.  Helt til nå er *tom* også brukt til å rapportere feil, noe som gjør det umulig å skille en gyldig «ingen verdi» fra en feil.  På dette tidspunktet er det bare støtte for lokale samlinger når du lagrer *tomme* verdier.  Du kan lagre *tomme* verdier i andre data kilder hvis du slår på eksperimentell-funksjonen feil administrasjon på Fil-menyen, App-innstillinger, avanserte innstillinger, eksperimentelle funksjoner.  Vi jobber aktivt med å fullføre denne funksjonen og fullføre den riktige separasjonen av *tomme* verdier fra feil.

## <a name="description"></a>Beskrivelse
**Blank**-funksjonen returnerer en *tom* verdi. Bruk denne til å lagre en NULL-verdi i en datakilde som støtter disse verdiene. Dette fjerner enhver verdi fra feltet.

**IsBlank** -funksjonen tester for en *tom* verdi eller en tom streng.  Testen inneholder tomme strenger som forenkler oppretting av apper fordi noen data kilder og kontroller bruker en tom streng når det ikke finnes noen verdi.  Hvis du vil teste spesifikt for en *tom* verdi, bruker du `if( Value = Blank(), ...` i stedet for **IsBlank**.

**Oppsamlings** funksjonen evaluerer argumentene i rekkefølge og returnerer den første verdien som ikke er *tom* eller en tom streng.  Bruk denne funksjonen til å erstatte en *tom* verdi eller en tom streng med en annen*verdi, men la ikke være tom* og ikke-tomme streng verdier uendret.  Hvis alle argumentene er *tomme* eller tomme strenger, returnerer funksjonen *tom* **, noe som gjør at** en god måte kan konvertere tomme strenger til *tomme* verdier.  Alle argumentene til **Coalesce** må være av samme type. Du kan for eksempel ikke blande tall med tekststrenger.  

`Coalesce( value1, value2 )` er den mer konsise ekvivalenten til `If( Not IsBlank( value1 ), value1, Not IsBlank( value2 ), value2 )` og krever ikke at **verdi1** og **verdi2** evalueres to ganger.  [ **IF** -funksjonen](function-if.md) returnerer *tom* hvis det ikke finnes noen «ellers» formel som er tilfelle her.

**IsEmpty**-funksjonen tester om tabellen inneholder noen poster. Det tilsvarer å bruke **[CountRows](function-table-counts.md)** -funksjonen og se etter null. Du kan se etter datakildefeil ved å kombinere **IsEmpty**-funksjonen med **[Errors](function-errors.md)** -funksjonen.

Returverdien for både **IsBlank** og **IsEmpty** er en boolsk **sann** eller **usann**.

## <a name="syntax"></a>Syntaks
**Blank**()

**Coalesce**( *Value1* [, *Value2*, ... ] )

* *Value(s)* – obligatorisk. Verdier å teste.  Hver verdi evalueres i rekkefølge til en verdi som ikke er *tom* , og ikke en tom streng, blir funnet.  Verdier etter dette punktet evalueres ikke.  

**IsBlank**( *Verdi* )

* *Value* – obligatorisk. Verdi som skal testes for en *tom* verdi eller en tom streng.

**IsEmpty**( *Tabell* )

* *Tabell* – obligatorisk. Tabell som skal testes for poster.

## <a name="examples"></a>Eksempler
### <a name="blank"></a>Blank
> [!NOTE]
> På dette tidspunktet fungerer det følgende eksemplet bare for lokale samlinger.  Du kan lagre *tomme* verdier i andre data kilder hvis du slår på eksperimentell-funksjonen feil administrasjon på Fil-menyen, App-innstillinger, avanserte innstillinger, eksperimentelle funksjoner.  Vi jobber aktivt med å fullføre denne funksjonen og fullføre separasjonen av *tomme* verdier fra feil.

1. Opprett en app fra grunnen av, og legg til en **Knapp**.
2. Sett knappens **[OnSelect](../controls/properties-core.md)** -egenskap til denne formelen:

    ```powerapps-dot
    ClearCollect( Cities, { Name: "Seattle", Weather: "Rainy" } )
    ```
3. Forhåndsvis appen, klikk eller trykk på knappen som du har lagt til, og lukk deretter Forhåndsvisning.  
4. Klikk eller trykk på **Samlinger** på **Fil**-menyen.

     Samlingen **Byer** vises, som viser én post med «Seattle» og «Regn»:

    ![Samlingen som viser Seattle med regnvær](./media/function-isblank-isempty/seattle-rainy.png)
5. Klikk eller trykk på Tilbake-pilen for å gå tilbake til standardarbeidsområdet.
6. Legg til en **Etikett**-kontroll, og angi **Tekst**-egenskapen til denne formelen:

    ```powerapps-dot
    IsBlank( First( Cities ).Weather )
    ```

    Etiketten viser **usann** fordi **Vær**-feltet inneholder en verdi («Regn»).
7. Legg til en annen knapp, og angi knappens **OnSelect**-egenskap til denne formelen:

    ```powerapps-dot
    Patch( Cities, First( Cities ), { Weather: Blank() } )
    ```
8. Forhåndsvis appen, klikk eller trykk på knappen som du har lagt til, og lukk deretter Forhåndsvisning.  

    **Vær**-feltet i den første posten i **Byer** erstattes med et *tom*-felt, og fjerner dermed «Regn», som stod der tidligere.

    ![Samling som viser Seattle med blankt værfelt](./media/function-isblank-isempty/seattle-blank.png)

    Etiketten viser **usann** fordi **Vær**-feltet ikke lenger inneholder en verdi.

### <a name="coalesce"></a>Oppsamling

| Formel | Beskrivelse | Resultat |
| --- | --- | --- |
| **Oppsamling (&nbsp;Blank (), &nbsp;1 @ no__t-3)** |Tester returverdien fra **Blank**-funksjonen, som alltid returnerer en *tom* verdi. Fordi det første argumentet er *tomt*, fortsetter evalueringen med neste argument til en verdi som ikke er*tom* , og som ikke er tom, blir funnet. |**1** |
| **Samling ("", 2)** |Tester det første argumentet, som er en tom streng. Fordi det første argumentet er en tom streng, fortsetter evalueringen med neste argument til en verdi som ikke er*tom* , og som ikke er tom streng, blir funnet. |**2** |
| **Oppsamling (blank (), "", blank (), "", 3, 4)** |**Oppsamlingen** starter i begynnelsen av argument listen og evaluerer hvert argument i sving til en verdi som ikke*er tom,* og som ikke er tom.  I dette tilfellet returnerer de fire første argumentene alle *tomme* eller en tom streng, så evalueringen fortsetter til det femte argumentet. Det femte argumentet er ikke*tomt* og ikke-tom streng, så evaluering stopper her. Verdien til det femte argumentet returneres, og det sjette argumentet evalueres ikke. |**3** |
| **Oppsamling («»)** | Tester det første argumentet, som er en tom streng. Fordi det første argumentet er en tom streng, og det ikke finnes flere argumenter, returnerer funksjonen *tom*.   |*tom* |

### <a name="isblank"></a>IsBlank
1. Opprett en app fra grunnen av, legg til en kontroll for innskriving av tekst og gi den navnet **FirstName**.
2. Legg til en etikett, og angi **[Tekst](../controls/properties-core.md)** -egenskapen til denne formelen:

    ```powerapps-dot
    If( IsBlank( FirstName.Text ), "First Name is a required field." )
    ```

    Som standard er **[Tekst](../controls/properties-core.md)** -egenskapen til en tekstinndatakontroll satt til **«Tekstinndata»** . Fordi egenskapen inneholder en verdi, er den ikke tom, og etiketten viser ikke noen melding.
3. Fjern alle tegnene fra tekstinndatakontrollen, inkludert mellomrom.

    Fordi **[tekst](../controls/properties-core.md)** -egenskapen ikke lenger inneholder noen tegn, er det en tom streng, og **IsBlank (for navn. text)** vil være **sann**. Den obligatoriske feltmeldingen vises.

Hvis du vil ha informasjon om hvordan du utfører validering ved hjelp av andre verktøy, kan du se **[Validate](function-validate.md)** -funksjonen og [Å arbeide med datakilder](../working-with-data-sources.md).  

Andre eksempler:

| Formel | Beskrivelse | Resultat |
| --- | --- | --- |
| **IsBlank (&nbsp;Blank () &nbsp;)** |Tester returverdien fra **Blank**-funksjonen, som alltid returnerer en *tom* verdi. |**sann** |
| **IsBlank( "" )** |En streng som ikke inneholder noen tegn. |**sann** |
| **IsBlank( "Hello" )** |En streng som inneholder ett eller flere tegn. |**usann** |
| **IsBlank( *AnyCollection* )** |Fordi [samlingen](../working-with-data-sources.md#collections) finnes, er den ikke tom, selv om den ikke inneholder noen poster. Hvis du vil se etter en tom samling, kan du bruke **IsEmpty** i stedet. |**usann** |
| **IsBlank( Mid( "Hello", 17, 2 ) )** |Det første tegnet for **[Mid](function-left-mid-right.md)** er utenfor slutten av strengen.  Resultatet er en tom streng. |**sann** |
| **IsBlank( If( false, false ) )** |En **[If](function-if.md)** -funksjon uten *ElseResult*.  Fordi betingelsen alltid er **usann**, returnerer denne **[If](function-if.md)** -funksjonen alltid *tom*. |**sann** |

### <a name="isempty"></a>IsEmpty
1. Opprett en app fra grunnen av, og legg til en **Knapp**.
2. Sett knappens **[OnSelect](../controls/properties-core.md)** -egenskap til denne formelen:

    **Collect (IceCream, {Flavor: "Strawberry", antall: 300}, {Flavor: «Sjokolade», antall: 100})**
3. Forhåndsvis appen, klikk eller trykk på knappen som du har lagt til, og lukk deretter Forhåndsvisning.  

    En samling med navnet **IceCream** opprettes og inneholder disse dataene:

    ![](media/function-isblank-isempty/icecream-strawberry-chocolate.png)

    Denne samlingen har to poster, og er ikke tom. **IsEmpty( IceCream )** returnerer **usann**, og **CountRows( IceCream )** returnerer **2**.
4. Legg til en annen knapp, og angi knappens **[OnSelect](../controls/properties-core.md)** -egenskap til denne formelen:

    **Clear( IceCream )**
5. Forhåndsvis appen, klikk eller trykk på den andre knappen, og lukk deretter Forhåndsvisning.  

    Samlingen er nå tom:

    ![](media/function-isblank-isempty/icecream-clear.png)

    **[Clear](function-clear-collect-clearcollect.md)** -funksjonen fjerner alle postene fra en samling, noe som resulterer i en tom samling. **IsEmpty( IceCream )** returnerer **sann**, og **CountRows( IceCream )** returnerer **0**.

Du kan også bruke **IsEmpty** til å teste om en beregnet tabell er tom, som disse eksemplene viser:

| Formel | Beskrivelse | Resultat |
| --- | --- | --- |
| **IsEmpty( [&nbsp;1,&nbsp;2,&nbsp;3 ] )** |Tabellen med én kolonne inneholder tre poster, og er derfor ikke tom. |**usann** |
| **IsEmpty( [&nbsp;] )** |Tabellen med én kolonne inneholder ingen poster, og er tom. |**sann** |
| **IsEmpty( Filter( [&nbsp;1,&nbsp;2,&nbsp;3&nbsp;], Value > 5 ) )** |Tabellen med én kolonne inneholder ingen verdier som er større enn 5.  Resultatet fra filteret inneholder ingen poster, og er tom. |**sann** |

