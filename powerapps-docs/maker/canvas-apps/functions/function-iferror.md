---
title: IfError-funksjonen | Microsoft Docs
description: Referanseinformasjon for IfError-funksjonen i PowerApps, inkludert syntaks og eksempler
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 03/21/2018
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 63a837eff2944569f5f66223690b11ddcfd399f6
ms.sourcegitcommit: aa9f78c304fe46922aecfe3b3fadb6bda72dfb23
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 05/24/2019
ms.locfileid: "66215914"
ms.PowerAppsDecimalTransform: true
---
# <a name="iferror-function-in-powerapps"></a>IfError-funksjonen i PowerApps

Oppdager feil, og oppgir en alternativ verdi eller utfører en handling.

## <a name="description"></a>Beskrivelse

> [!NOTE]
> Denne funksjonen er en del av en eksperimentell funksjon, og kan endres underveis. Virkemåten som beskrives i dette emnet er bare tilgjengelig når den *Feiladministrasjon på formelnivå* funksjonen er aktivert. Denne appen nivå-innstillingen er deaktivert som standard. Hvis du vil aktivere denne funksjonen, kan du åpne den *filen* fanen og velge *appinnstillinger* i den venstre menyen, og velg deretter *eksperimentelle funksjoner*. Vi setter stor pris på dine tilbakemeldinger – fortell oss hva du synes i [forumet for PowerApps-fellesskapet](https://powerusers.microsoft.com/t5/Expressions-and-Formulas/bd-p/How-To).

Den **IfError** funksjonen tester én eller flere verdier til det finner en feil. Hvis funksjonen finner en feil, returnerer funksjonen en tilsvarende verdi. Hvis ikke, returnerer funksjonen en standardverdi. I begge tilfeller dermed funksjonen returnerer en streng for å vise en formel for å evaluere, eller en annen form for resultat. Den **IfError** funksjonen ligner på den **Hvis** funksjonen: **IfError** tester for feil, mens **Hvis** tester **SANN**.

Bruk **IfError** erstatte feilverdier med gyldige verdier. For eksempel bruke denne funksjonen hvis brukerinndata kan resultere i en deling med null. Bygge en formel for å erstatte resultatet med en 0 eller en annen verdi som passer for appen din slik at nedstrømsberegninger kan fortsette. Formelen kan være så enkelt som i dette eksemplet:

```powerapps-comma
IfError( 1/x; 0 )
```

Hvis verdien for **x** ikke er null, returnerer formelen **1 / x**. Ellers **1 / x** fører det til en feil, og formelen returnerer 0 i stedet.

Bruk **IfError** i [formler for virkemåte](../working-with-formulas-in-depth.md) til å utføre en handling og kontroller for en feil før du kan utføre flere handlinger, som i dette mønsteret:

```powerapps-comma
IfError(
    Patch( DS1; ... ); Notify( "problem in the first action" );
    Patch( DS2; ... ); Notify( "problem in the second action" )
)
```

Hvis den første oppdateringen støter på et problem, først **Notify** kjører, at videre behandling oppstår, og ikke kjører som det andre oppdateringen. Hvis den første oppdateringen lykkes, andre oppdateringen kjører og, hvis det oppstår et problem, andre **Notify** kjører.

Hvis formelen ikke finner noen feil, og du har angitt den valgfrie *DefaultResult* argument, formelen returnerer verdien som du har angitt for argumentet. Hvis formelen ikke finner noen feil, og du ikke har angitt som argument, formelen returnerer siste *verdien* argumentet evalueres.

## <a name="syntax"></a>Syntaks

**IfError**( *Value1*; *Fallback1* [; *Value2*; *Fallback2*;... [; *DefaultResult* ]])

* *Verdi(er)* – obligatorisk. Formlene som skal testes for en feilverdi.
* *Fallback* – obligatorisk. Formlene som skal evalueres og verdier som skal returneres hvis samsvarende *verdien* argumentet returnerte en feil.
* *DefaultResult* – valgfritt.  Formler til å evaluere Hvis formelen ikke finner noen feil.

## <a name="examples"></a>Eksempler

| Formel | Beskrivelse | Resultat |
| --- | --- | --- |
| **IfError( 1; 2 )** |Det første argumentet er ikke en feil. Funksjonen har ingen andre feil for å kontrollere og ingen standard returverdi. Funksjonen returnerer sist *verdien* argumentet evalueres.   | 1 |
| **IfError( 1/0; 2 )** | Det første argumentet returnerer en feilverdi (på grunn av deling med null). Funksjonen evaluerer det andre argumentet, og returnerer det som et resultat. | 2 |
| **IfError( 1/0; Notify( «Det oppstod et internt problem»; NotificationType.Error ) )** | Det første argumentet returnerer en feilverdi (på grunn av deling med null). Funksjonen evaluerer det andre argumentet, og viser en melding til brukeren. Returverdien til **IfError** er returverdien til **Notify**, påtvunget til den samme typen som det første argumentet til **IfError** (et tall). | 1 |
| **IfError (1, 2, 3, 4, 5)** | Det første argumentet er ikke en feil, slik at funksjonen ikke evalueres at argumentet tilhørende fallback. Det tredje argumentet er ikke en feil, slik at funksjonen ikke evalueres at argumentet tilhørende fallback. Det femte argumentet har ingen tilsvarende fallback og er standard resultatet. Funksjonen returnerer som oppstår fordi den inneholder ingen feil. | 5 |

### <a name="step-by-step"></a>Trinn for trinn

1. Legg til en **[Tekstinndata](../controls/control-text-input.md)**-kontroll, og gi den navnet **TextInput1** hvis den ikke har det navn som standard.

2. Legg til en **[Etikett](../controls/control-text-box.md)**-kontroll, og gi den navnet **Label1** hvis den ikke har det navn som standard.

3. Angi formelen for **Tekst**-egenskapen til **Label1** til:

    **IfError( Value( TextInput1.Text ); -1 )**

4. Skriv inn **1234** i **TextInput1**.  

    Label1 viser verdien **1234**, da dette er en gyldig inndata til Value-funksjonen.

5. Skriv inn **ToInfinity** i **TextInput1**.

    Label1 viser verdien **-1**, da dette ikke er en gyldig inndata til Value-funksjonen.  Hvis ikke IfError brukes for Value-funksjonen, ville ikke etiketten vise noen verdi. Det er fordi at verdien ville behandles som *tom*. 

