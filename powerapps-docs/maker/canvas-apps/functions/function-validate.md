---
title: Funksjonen Validate | Microsoft Docs
description: Referanseinformasjon for funksjonen Validate i PowerApps, inkludert syntaks og eksempler
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
ms.openlocfilehash: bec00071d1b354872bf3b140e5c879fe8857ffec
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/24/2018
ms.locfileid: "42865674"
---
# <a name="validate-function-in-powerapps"></a>Funksjonen Validate i PowerApps
Funksjonen **Validate** kontrollerer hvorvidt verdien av en [enkeltkolonne](../working-with-tables.md#columns) eller en fullstendig [post](../working-with-tables.md#records) er gyldig for en [datakilde](../working-with-data-sources.md).  

## <a name="description"></a>Beskrivelse
Før en bruker sender inn en dataendring, kan du gi umiddelbar tilbakemelding på gyldigheten av denne sendingen, noe som resulterer i en bedre brukeropplevelse.

Datakilder kan gi informasjon om hva som regnes som gyldige verdier i en post. Denne informasjonen kan inneholde mange begrensninger, som for eksempel:

* hvorvidt en kolonne krever en verdi
* hvor lang en tekststreng kan være
* hvor høye og lave tallene kan være
* hvor tidlig og sent en dato kan være

Funksjonen **Validate** bruker denne informasjonen til å finne ut om en verdi er gyldig, og til å returnere en korrekt feilmelding hvis det ikke er tilfelle. Du kan bruke funksjonen **[DataSourceInfo](function-datasourceinfo.md)** til å vise den samme informasjonen som **Validate** bruker.

Det varierer hvor mye valideringsinformasjon datakildene gir, og det kan forekomme at de ikke gir noe slik informasjon. **Validate** kan kun kontrollere verdier basert på denne informasjonen. Selv om **Validate** ikke finner et problem, kan bruk av dataendringene fortsatt mislykkes. Du kan bruke funksjonen **[Errors](function-errors.md)** til å hente informasjon om feilen.

Hvis **Validate** finner et problem, vil funksjonen returnere en feilmelding som du kan vise til brukeren av appen. Hvis alle verdiene er gyldige, vil **Validate** returnere [tom](function-isblank-isempty.md). Når du arbeider med en [samling](../working-with-data-sources.md#collections) som ikke har noen valideringsinformasjon, vil verdiene alltid være gyldige.

## <a name="syntax"></a>Syntaks
**Validate**( *DataSource*, *Column*, *Value* )

* *DataSource* – obligatorisk. Datakilden det skal valideres med.
* *Column* – obligatorisk. Kolonnen som skal valideres.
* *Value* – obligatorisk. Verdien for den valgte kolonnen som skal valideres.

**Validate**( *DataSource*, *OriginalRecord*, *Updates* )

* *DataSource* – obligatorisk. Datakilden det skal valideres med.
* *OriginalRecord* – obligatorisk.  Posten som inneholder oppdateringer som skal valideres.
* *Updates* – obligatorisk.  Endringene som skal brukes på den opprinnelige posten.

## <a name="examples"></a>Eksempler
I disse eksemplene må verdiene i **Prosent**-kolonnen i datakilden for **Resultater** være mellom 0 og 100. Hvis dataen består valideringen, returnerer funksjonen *tom*. Hvis ikke, returnerer funksjonen en feilmelding.

### <a name="validate-with-a-single-column"></a>Å validere med en enkeltkolonne

| Formel | Beskrivelse | Resultat |
| --- | --- | --- |
| **Validate( Scores, Percentage, 10 )** |Kontrollerer om **10** er en gyldig verdi for **Prosent**-kolonnen i datakilden for **Resultater**. |*tom* |
| **Validate( Scores, Percentage, 120 )** |Kontrollerer om **120** er en gyldig verdi for **Prosent**-kolonnen i datakilden for **Resultater**. |«Verdiene må være mellom 0 og 100.» |

### <a name="validate-with-a-complete-record"></a>Å validere med en fullstendig post

| Formel | Beskrivelse | Resultat |
| --- | --- | --- |
| **Validate( Scores, EditRecord, Gallery.Updates )** |Kontrollerer om **10** er en gyldig verdi for **Prosent**-kolonnen i datakilden for **Resultater**. |*tom* |
| **Validate( Scores, EditRecord, Gallery.Updates )** |Kontrollerer om **120** er en gyldig verdi for **Prosent**-kolonnen i datakilden for **Resultater**. |«Verdiene må være mellom 0 og 100.» |

