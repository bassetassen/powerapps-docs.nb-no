---
title: GUID-funksjonen | Microsoft Docs
description: Referanseinformasjon for GUID-funksjonen i PowerApps, inkludert syntaks og eksempler
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 06/09/2018
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: a45aa397aa65e11ab01e04367d859e11bf552f66
ms.sourcegitcommit: 3aeb9381fbeb66cf08355d9a3d0f00ce2737e256
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/29/2018
ms.locfileid: "43164535"
---
# <a name="guid-function-in-powerapps"></a>GUID-funksjonen i PowerApps
Konverterer en GUID-streng ([Globally Unique Identifier](https://en.wikipedia.org/wiki/Universally_unique_identifier)) til en GUID-verdi, eller oppretter en ny GUID-verdi.

## <a name="description"></a>Beskrivelse
Bruk **GUID**-funksjonen til å konvertere en streng som inneholder den heksadesimale representasjonen av en GUID i en GUID-verdi, som kan sendes til en database. GUID-verdier brukes som nøkler av databasesystemer som Common Data Service for apper og SQL Server.

Strengen som sendes, kan inneholde små eller store bokstaver, men i disse formatene må den inneholde 32 heksadesimale tegn:

- **"123e4567-e89b-12d3-a456-426655440000"** (bindestreker i standardplasseringer)
- **"123e4567e89b12d3a456426655440000"** (ingen bindestreker)

Hvis du ikke angir et argument, oppretter denne funksjonen en ny GUID.

Hvis du vil konvertere en GUID-verdi til en streng, bruker du den bare i en strengkontekst. GUID-verdien konverteres til en heksadesimal representasjonsstreng med bindestreker og små bokstaver. 

> [!NOTE]
> Det finnes for tiden en kjent feil som gjør at GUID-verdier kan sammenlignes direkte med strenger.  Dette vil snart endre seg og produsere en feil, derfor må du ikke blir for vant med det.  Hvis du vil sammenligne en streng med en GUID-verdi, må du først transformere strengen til en GUID-verdi med GUID-funksjonen, og deretter sammenligne GUID-verdiene.  Dette normaliserer begge verdiene for en ren sammenligning.  Hvis du ikke gjør dette, blir GUID-verdien konvertert til en streng automatisk, og sammenligningen vil avhenge av formateringen til strengen og om det finnes noen alfanumeriske tegn.

> [!NOTE]
> Det er for øyeblikket ingen måte du kan lese eller skrive GUID-verdier til en database på.  Støtte for Common Data Service and SQL Server finnes på veikartet vårt. 

## <a name="volatile-functions"></a>Flyktige funksjoner
**GUID** er en flyktig funksjon når den brukes sammen med et argument. Hver gang en av disse funksjonene evalueres returnerer den en annen verdi.  

En flyktig funksjon returnerer en annen verdi når den brukes i en formel for dataflyt, hvis formelen den viser, ser ut til å være evaluert på nytt. Hvis ingenting annet endres i formelen, vil den ha samme verdi i hele kjøringen av appen.

En etikettkontroll der **Tekst**-egenskapen er angitt til for eksempel **GUID()**, endrer ikke mens appen din er aktiv. Å bare lukke og åpne appen vil resultere i en forskjellig verdi.

Funksjonen vil evalueres på nytt hvis den er en del av en formel der noe annet er endret. Hvis vi angir **Tekst**-egenskapen for en **etikettkontroll** til denne formelen, genereres for eksempel en GUID hver gang brukeren endrer verdien til **tekstinndatakontrollen**:

**TextInput1.Text & " " & GUID()**

Når den brukes i en [virkemåteformel](../working-with-formulas-in-depth.md) blir **GUID** evaluert hver gang formelen evalueres. Hvis du vil ha mer informasjon, ser du eksemplene senere i dette emnet.

## <a name="syntax"></a>Syntaks
**GUID**( [ *GUIDString* ] )


* *GUIDString* – valgfritt.  En tekststreng som inneholder den heksadesimale representasjonen av en GUID. Hvis ingen streng angis, opprettes det en ny GUID.

## <a name="examples"></a>Eksempler

#### <a name="basic-usage"></a>Grunnleggende bruk

Hvis du vil returnere en GUID-verdi basert på den heksadesimale strengrepresentasjonen:

* **GUID( "0f8fad5b-d9cb-469f-a165-70867728950e" )**

Du kan også oppgi GUID-verdi uten bindestreker. Denne formelen returnerer den samme GUID-verdien:

* **GUID( "0f8fad5bd9cb469fa16570867728950e" )**

Brukes i kontekst til å angi **Status**-feltet i en ny databasepost til en godt etablert verdi:

* **Patch( Products, Default( Products ), { Status: GUID( "F9168C5E-CEB2-4faa-B6BF-329BF39FA1E4" ) } )**

Du ønsker sikkert ikke å vise GUID-verdiene til brukerne, men GUID-verdiene kan hjelpe deg med å feilsøke appen. Hvis du vil vise verdien til **Status**-feltet i posten du opprettet i forrige eksempel, angir du **Text**-egenskapen for en **etikettkontroll** til denne formelen:

* **First( Products ).Status**

**Etikettkontrollen** viser **f9168c5e-ceb2-4faa-b6bf-329bf39fa1e4**.

#### <a name="create-a-table-of-guids"></a>Opprett en tabell med GUID-verdier

1. Angi **[OnSelect](../controls/properties-core.md)**-egenskapen til **[Knapp](../controls/control-button.md)**-kontrollen som denne formelen:

    **ClearCollect( NewGUIDs, ForAll( [ 1, 2, 3, 4, 5 ], GUID() ) )**

    Denne formelen oppretter én kolonnetabell som brukes til å oppdatere fem ganger, noe som resulterer i fem GUID-verdier.

1. Legg til en **[Datatabellkontroll](../controls/control-data-table.md)**, angi **Elementer**-egenskapen til **NewGUIDs**, og vis deretter **Verdi**-feltet.

1. Velg knappen ved å klikke eller trykke på den mens du holder nede ALT.

    Datatabellen viser en liste over GUID-verdiene:

    ![En skjerm som viser en tabell med fem forskjellige GUID-verdier](media/function-guid/guid-collection-1.png)

1. Velg knappen igjen for å vise en annen liste med GUID-verdier:

    ![Den samme skjermen som viser en datatabell med et nytt sett med fem forskjellige GUID-verdier](media/function-guid/guid-collection-2.png)

Hvis du vil generere en enkelt GUID-verdi i stedet for en tabell, bruker du denne formelen:

**Set( NewGUID, GUID() )**
