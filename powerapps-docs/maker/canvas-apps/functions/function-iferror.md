---
title: IfError-funksjonen | Microsoft Docs
description: Referanseinformasjon for IfError-funksjonen i PowerApps, inkludert syntaks og eksempler
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 03/21/2018
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 992ff4ccfae533908acac96efaa117a726198334
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/07/2019
ms.locfileid: "71984729"
ms.PowerAppsDecimalTransform: true
---
# <a name="iferror-function-in-powerapps"></a>IfError-funksjonen i PowerApps

Oppdager feil, og oppgir en alternativ verdi eller utfører en handling.

## <a name="description"></a>Beskrivelse

> [!NOTE]
> Denne funksjonen er en del av en eksperimentell funksjon, og kan endres underveis. Virke måten som dette emnet beskriver, er bare tilgjengelig når funksjonen *feil behandling på formel nivå* er aktivert. Denne program nivå innstillingen er deaktivert som standard. Hvis du vil aktivere denne funksjonen, åpner du *fil* -fanen, velger *App-innstillinger* på menyen til venstre, og deretter velger du *eksperimentelle funksjoner*. Vi setter stor pris på dine tilbakemeldinger – fortell oss hva du synes i [forumet for PowerApps-fellesskapet](https://powerusers.microsoft.com/t5/Expressions-and-Formulas/bd-p/How-To).

**IfError** -funksjonen tester én eller flere verdier til den finner et feil resultat. Hvis funksjonen finner en feil, returnerer funksjonen en tilsvarende verdi. Ellers returnerer funksjonen en standard verdi. I begge tilfeller kan det hende at funksjonen returnerer en streng som skal vises, en formel for å evaluere, eller en annen form for resultat. **IfError** -funksjonen ligner på **Hvis** -funksjonen: **IfError** tester for feil, selv **om** tester for **sann**.

Bruk **IfError** til å erstatte feil verdier med gyldige verdier. Bruk for eksempel denne funksjonen hvis bruker inn data kan resultere i en divisjon med null. Bygg en formel for å erstatte resultatet med 0 eller en annen verdi som passer for appen din, slik at data under beregningen kan fortsette. Formelen kan være så enkelt som dette eksemplet:

```powerapps-comma
IfError( 1/x; 0 )
```

Hvis verdien for **x** ikke er null, returnerer formelen **1/x**. Ellers gir **1/x** en feil, og formelen returnerer i stedet 0.

Bruk formler for **IfError** i [virke måte](../working-with-formulas-in-depth.md) for å utføre en handling og se etter en feil før du utfører flere handlinger, som i dette mønsteret:

```powerapps-comma
IfError(
    Patch( DS1; ... ); Notify( "problem in the first action" );
    Patch( DS2; ... ); Notify( "problem in the second action" )
)
```

Hvis det oppstår et problem med den første oppdateringen, vil det første **varselet** kjøres uten videre behandling, og den andre oppdateringen kan ikke kjøres. Hvis den første oppdateringen lykkes, kjøres den andre oppdateringen, og hvis det oppstår et problem, kjøres den andre **varslingen** .

Hvis formelen ikke finner noen feil, og du har angitt det valg frie *DefaultResult* -argumentet, returnerer formelen verdien som du angav for dette argumentet. Hvis formelen ikke finner noen feil, og du ikke har angitt argumentet, returnerer formelen det siste *verdi* argumentet som ble evaluert.

## <a name="syntax"></a>Syntaks

**IfError**( *verdi1*; *Fallback1* [; *verdi2*; *Fallback2*;... [; *DefaultResult* ]] )

* *Verdi (er)* – obligatorisk. Formlene som skal testes for en feilverdi.
* *Fallback* – obligatorisk. Formlene som evalueres og verdiene som skal returneres hvis samsvarende *verdi* argumenter returnerte en feil.
* *DefaultResult* – valgfritt.  Formlene som skal evalueres Hvis formelen ikke finner noen feil.

## <a name="examples"></a>Eksempler

| Formel | Beskrivelse | Resultat |
| --- | --- | --- |
| **IfError( 1; 2 )** |Det første argumentet er ikke en feil. Funksjonen har ingen andre feil som skal kontrolleres, og ingen standard retur verdi. Funksjonen returnerer det siste *verdi* argumentet som ble evaluert.   | 1 |
| **IfError( 1/0; 2 )** | Det første argumentet returnerer en feil verdi (på grunn av en deling med null). Funksjonen evaluerer det andre argumentet og returnerer det som resultatet. | 2 |
| **IfError( 1/0; Notify( «Det oppstod et internt problem»; NotificationType.Error ) )** | Det første argumentet returnerer en feil verdi (på grunn av en deling med null). Funksjonen evaluerer det andre argumentet og viser en melding til brukeren. Returverdien til **IfError** er returverdien til **Notify**, påtvunget til den samme typen som det første argumentet til **IfError** (et tall). | 1 |
| **IfError (1, 2, 3, 4, 5)** | Det første argumentet er ikke en feil. funksjonen evaluerer ikke den tilsvarende Reserve verdien for argumentet. Det tredje argumentet er ikke en feil, så funksjonen evaluerer ikke den tilsvarende Reserve verdien for argumentet. Det femte argumentet har ingen tilsvarende Reserve, og er standard resultatet. Funksjonen returnerer resultatet fordi formelen ikke inneholder feil. | 5 |

### <a name="step-by-step"></a>Trinn for trinn

1. Legg til en **[Tekstinndata](../controls/control-text-input.md)** -kontroll, og gi den navnet **TextInput1** hvis den ikke har det navn som standard.

2. Legg til en **[Etikett](../controls/control-text-box.md)** -kontroll, og gi den navnet **Label1** hvis den ikke har det navn som standard.

3. Angi formelen for **Tekst**-egenskapen til **Label1** til:

    **IfError( Value( TextInput1.Text ); -1 )**

4. Skriv inn **1234** i **TextInput1**.  

    Label1 viser verdien **1234**, da dette er en gyldig inndata til Value-funksjonen.

5. Skriv inn **ToInfinity** i **TextInput1**.

    Label1 viser verdien **-1**, da dette ikke er en gyldig inndata til Value-funksjonen.  Hvis ikke IfError brukes for Value-funksjonen, ville ikke etiketten vise noen verdi. Det er fordi at verdien ville behandles som *tom*. 

