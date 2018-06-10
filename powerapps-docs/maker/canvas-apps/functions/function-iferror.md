---
title: IfError-funksjonen | Microsoft Docs
description: Referanseinformasjon for IfError-funksjonen i PowerApps, inkludert syntaks og eksempler
documentationcenter: na
author: gregli-msft
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: reference
ms.component: canvas
ms.date: 03/21/2018
ms.author: gregli
ms.openlocfilehash: 2bd8ba7dc9b764399165c75361215cee2edb4e7b
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/04/2018
ms.locfileid: "31831450"
---
# <a name="iferror-function-in-powerapps"></a>IfError-funksjonen i PowerApps
Oppdager feil, og oppgir en alternativ verdi eller utfører en handling.

## <a name="description"></a>Beskrivelse
> [!NOTE]
> Denne funksjonen er en del av en eksperimentell funksjon, og kan endres underveis.  Virkemåten som beskrives her er bare tilgjengelig når funksjonen *Feiladministrasjon på formelnivå* er slått på.  Dette er en innstilling som gjelder for hele appen, og standardinnstillingen er angitt til av.  Hvis du vil slå denne funksjonen på, navigerer du til *Fil*-fanen, *Appinnstillinger* i menyen til venstre, og deretter *Eksperimentelle funksjoner*.  Vi setter stor pris på dine tilbakemeldinger – fortell oss hva du synes i [forumet for PowerApps-fellesskapet](https://powerusers.microsoft.com/t5/Expressions-and-Formulas/bd-p/How-To).

**IfError**-funksjonen tester hvert argument i rekkefølge etter en feilverdi, og stanser når den finner den første ikke-feilverdien.  Argumentene etter at ikke-feilverdien blir funnet ignoreres og evalueres ikke.

Bruk **IfError** for å erstatte feilverdier med en gyldig verdi.  Hvis det for eksempel er mulig at brukerinndata kan føre til en deling på null, erstatter du den med null eller en annen gyldig verdi som passer for appen, slik at nedstrømsberegninger kan fortsette.

Bruk **IfError** i [formler for virkemåte](../working-with-formulas-in-depth.md) for å utføre handlinger, kontrollere resultatene for feil, og utfører (ved behov) ytterligere handlinger eller viser en feilmelding til brukeren med [**ShowError**](function-showerror.md).

Hvis alle argumentene til **IfError** resulterer i en feil, returneres verdien av det siste argumentet (som er en feilverdi). 

## <a name="syntax"></a>Syntaks
**IfError**( *Value*, *Fallback1* [, *Fallback2*, ... ] )

* *Value* – obligatorisk. Formlene som skal testes for en feilverdi. 
* *Fallback* – obligatorisk. Formlene som skal evalueres og verdiene som skal returneres hvis det forrige argumentet returnerte en feil.  *Fallback*-argumenter evalueres helt til en ikke-feilverdi blir funnet.

## <a name="examples"></a>Eksempler

| Formel | Beskrivelse | Resultat |
| --- | --- | --- |
| **IfError( 1, 2 )** |Det første argumentet er ikke en feil.  Det returneres, og etterfølgende argumenter evalueres ikke.   | 1 |
| **IfError( 1/0, 2 )** | Det første argumentet returnerer en feilverdi (på grunn av deling med null).  Det andre argumentet evalueres, og en ikke-feilverdi blir ikke funnet eller returnert. | 2 | 
| **IfError( 1/0, ShowError( "Division by Zero" ) )** | Det første argumentet returnerer en feilverdi (på grunn av deling med null).  Det andre argumentet evalueres og vises en melding til brukeren.  Returverdien til **IfError** er returverdien til **ShowError**, påtvunget til den samme typen som det første argumentet til **IfError** (et tall). | 1 |
| **IfError( 1/0, 1/0, 2, 1/0, 3 )** | Det første argumentet returnerer en feilverdi (på grunn av deling med null).  Det andre argumentet evalueres, noe som også resulterer i en feilverdi (en annen deling på null).  Det tredje argumentet evalueres, og en feilverdi blir ikke funnet eller returnert.  Det fjerde og femte argumentet ignoreres.  | 2 |

### <a name="step-by-step"></a>Trinn for trinn

1. Legg til en **[Tekstinndata](../controls/control-text-input.md)**-kontroll, og gi den navnet **TextInput1** hvis den ikke har det navn som standard.

2. Legg til en **[Etikett](../controls/control-text-box.md)**-kontroll, og gi den navnet **Label1** hvis den ikke har det navn som standard.

3. Angi formelen for **Tekst**-egenskapen til **Label1** til:

    **IfError( Value( TextInput1.Text ), -1 )**

4. Skriv inn **1234** i **TextInput1**.  

    Label1 viser verdien **1234**, da dette er en gyldig inndata til Value-funksjonen.

5. Skriv inn **ToInfinity** i **TextInput1**.

    Label1 viser verdien **-1**, da dette ikke er en gyldig inndata til Value-funksjonen.  Hvis ikke IfError brukes for Value-funksjonen, ville ikke etiketten vise noen verdi. Det er fordi at verdien ville behandles som *tom*. 

