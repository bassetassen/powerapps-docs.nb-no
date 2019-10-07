---
title: GUID-funksjonen | Microsoft Docs
description: Referanseinformasjon for GUID-funksjonen i PowerApps, inkludert syntaks og eksempler
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 11/14/2018
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: ea2668ca295d807bbc19f71c9aa9f477c3b96041
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/07/2019
ms.locfileid: "71992671"
---
# <a name="guid-function-in-powerapps"></a>GUID-funksjonen i PowerApps
Konverterer en GUID-streng ([Globally Unique Identifier](https://en.wikipedia.org/wiki/Universally_unique_identifier)) til en GUID-verdi, eller oppretter en ny GUID-verdi.

## <a name="description"></a>Beskrivelse
Bruk **GUID**-funksjonen til å konvertere en streng som inneholder den heksadesimale representasjonen av en GUID i en GUID-verdi, som kan sendes til en database. GUID-verdier brukes som nøkler av database systemer, for eksempel Common Data Service og SQL Server.

Strengen som sendes, kan inneholde små eller store bokstaver, men i disse formatene må den inneholde 32 heksadesimale tegn:

- **"123e4567-e89b-12d3-a456-426655440000"** (bindestreker i standardplasseringer)
- **"123e4567e89b12d3a456426655440000"** (ingen bindestreker)

Hvis du ikke angir et argument, oppretter denne funksjonen en ny GUID.

Hvis du vil konvertere en GUID-verdi til en streng, bruker du den bare i en strengkontekst. GUID-verdien konverteres til en heksadesimal representasjonsstreng med bindestreker og små bokstaver. 

Når du genererer en ny GUID, bruker denne funksjonen pseudo-tilfeldige tall til å opprette en versjon 4 [IETF RFC 4122](https://www.ietf.org/rfc/rfc4122.txt) GUID. Når du konverterer en streng til en GUID, støtter denne funksjonen enhver GUID-versjon ved å godta en streng på 32 heksadesimale sifre.

## <a name="volatile-functions"></a>Flyktige funksjoner
**GUID** er en flyktig funksjon når den brukes sammen med et argument. Hver gang en av disse funksjonene evalueres returnerer den en annen verdi.  

En flyktig funksjon returnerer en annen verdi når den brukes i en formel for dataflyt, hvis formelen den viser, ser ut til å være evaluert på nytt. Hvis ingenting annet endres i formelen, vil den ha samme verdi i hele kjøringen av appen.

En etikettkontroll der **Tekst**-egenskapen er angitt til for eksempel **GUID()** , endrer ikke mens appen din er aktiv. Å bare lukke og åpne appen vil resultere i en forskjellig verdi.

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

* **Patch (produkter, standard (produkter), {status: GUID ("F9168C5E-CEB2-4faa-B6BF-329BF39FA1E4")})**

Du ønsker sikkert ikke å vise GUID-verdiene til brukerne, men GUID-verdiene kan hjelpe deg med å feilsøke appen. Hvis du vil vise verdien til **Status**-feltet i posten du opprettet i forrige eksempel, angir du **Text**-egenskapen for en **etikettkontroll** til denne formelen:

* **First( Products ).Status**

**Etikettkontrollen** viser **f9168c5e-ceb2-4faa-b6bf-329bf39fa1e4**.

#### <a name="create-a-table-of-guids"></a>Opprett en tabell med GUID-verdier

1. Angi **[OnSelect](../controls/properties-core.md)** -egenskapen til **[Knapp](../controls/control-button.md)** -kontrollen som denne formelen:

    **ClearCollect( NewGUIDs, ForAll( [ 1, 2, 3, 4, 5 ], GUID() ) )**

    Denne formelen oppretter én kolonnetabell som brukes til å oppdatere fem ganger, noe som resulterer i fem GUID-verdier.

1. Legg til en **[Datatabellkontroll](../controls/control-data-table.md)** , angi **Elementer**-egenskapen til **NewGUIDs**, og vis deretter **Verdi**-feltet.

1. Velg knappen ved å klikke eller trykke på den mens du holder nede ALT.

    Datatabellen viser en liste over GUID-verdiene:

    ![En skjerm som viser en tabell med fem forskjellige GUID-verdier](media/function-guid/guid-collection-1.png)

1. Velg knappen igjen for å vise en annen liste med GUID-verdier:

    ![Den samme skjermen som viser en datatabell med et nytt sett med fem forskjellige GUID-verdier](media/function-guid/guid-collection-2.png)

Hvis du vil generere en enkelt GUID-verdi i stedet for en tabell, bruker du denne formelen:

**Set( NewGUID, GUID() )**
