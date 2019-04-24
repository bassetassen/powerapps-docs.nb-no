---
title: DataSourceInfo-funksjonen | Microsoft Docs
description: Referanseinformasjon for DataSourceInfo-funksjonen i PowerApps, inklusive syntaks og eksempler
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 11/11/2015
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: d856ccd086a919e206175c25eee19f435325fb8c
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/23/2019
ms.locfileid: "61551310"
---
# <a name="datasourceinfo-function-in-powerapps"></a>DataSourceInfo-funksjonen i PowerApps
Returnerer informasjon om en [datakilde](../working-with-data-sources.md).

## <a name="overview"></a>Oversikt
Datakilder kan gi mye informasjon for å optimalisere brukeropplevelsen.

Du kan bruke informasjon på [kolonne](../working-with-tables.md#columns)-nivået til å validere inndata fra brukerne og gi umiddelbare tilbakemelding til brukeren før du bruker **[Patch](function-patch.md)**-funksjonen. **[Validate](function-validate.md)**-funksjonen bruker den samme informasjonen.

Du kan bruke informasjon på datakilde-nivå, for eksempel for å deaktivere eller skjule **Rediger**- og **Ny**-knapper for brukere som ikke har tillatelse til å redigere og opprette [poster](../working-with-tables.md#records).

Det varierer hvor mye informasjon datakildene leverer, og det kan forekomme at de ikke leverer noe.  [Samlinger](../working-with-data-sources.md#collections) gir ingen informasjon. Hvis informasjonen ikke er angitt, brukes standard, eller *tom* returneres.

## <a name="description"></a>Beskrivelse
### <a name="column-information"></a>Kolonneinformasjon
Du kan bruke **DataSourceInfo** til å få informasjon om en bestemt kolonne for en datakilde:  

| Informasjonsargument | Resultattype | Beskrivelse |
| --- | --- | --- |
| **DataSourceInfo.DisplayName** |Streng |Visningsnavn for kolonnen. Hvis ingen visningsnavn er definert, returneres navnet på kolonnen. |
| **DataSourceInfo.MaxLength** |Tall |Maksimalt antall tegn som kan registreres. Gjelder bare kolonner som inneholder strenger. Hvis et maksimum ikke er angitt, returneres *tom*. |
| **DataSourceInfo.MaxValue** |Tall |Maksimal numerisk verdi som en kolonne kan inneholde. Gjelder bare kolonner som inneholder tall. Hvis et maksimum ikke er angitt, returneres *tom*. |
| **DataSourceInfo.MinValue** |Tall |Maksimal numerisk verdi som en kolonne kan inneholde. Gjelder bare kolonner som inneholder tall. Hvis et maksimum ikke er angitt, returneres *tom*. |
| **DataSourceInfo.Required** |Boolsk |Er en verdi påkrevd for denne kolonnen? Hvis det ikke er angitt av datakilden, returneres **usann**. |

Det tredje argumentet er navnet på en kolonne som en streng.  Kolonnen **Telefon** i samlingen **Personer** ville for eksempel ha blitt sendt som **"Telefon"**, inklusive doble anførselstegn.

### <a name="data-source-information"></a>Datakilde-informasjon
Du kan bruke **DataSourceInfo** til å få informasjon om en bestemt kolonne for en datakilde:  

| Informasjonsargument | Resultattype | Beskrivelse |
| --- | --- | --- |
| **DataSourceInfo.AllowedValues** |Boolsk |Hvilke typer tillatelser kan brukere gis for denne datakilden? Hvis det ikke er angitt av datakilden, returneres *tom*. |
| **DataSourceInfo.CreatePermission** |Boolsk |Har den gjeldende brukeren tillatelse til å opprette poster i denne datakilden? Hvis det ikke er angitt av datakilden, returneres **sann**. |
| **DataSourceInfo.DeletePermission** |Boolsk |Har den gjeldende brukeren tillatelse til å slette poster i denne datakilden? Hvis det ikke er angitt av datakilden, returneres **sann**. |
| **DataSourceInfo.EditPermission** |Boolsk |Har den gjeldende brukeren tillatelse til å endre poster i denne datakilden? Hvis det ikke er angitt av datakilden, returneres **sann**. |
| **DataSourceInfo.ReadPermission** |Boolsk |Har den gjeldende brukeren tillatelse til å lese poster i denne datakilden? Hvis det ikke er angitt av datakilden, returneres **sann**. |

## <a name="syntax"></a>Syntaks
**DataSourceInfo**( *DataSource*, *Information*, *ColumnName* )

* *DataSource* – obligatorisk. Datakilden som skal oppdateres.
* *Information* – obligatorisk. Typen informasjon som du vil hente.
* *ColumnName* – valgfritt. For informasjon på kolonnenivå – kolonnenavnet som en streng. Kolonnen **Telefon** ville for eksempel ha blitt sendt som **"Telefon"**, inklusive doble anførselstegn. *ColumnName*-argumentet kan ikke brukes for informasjon på datakilde-nivå.
  
    > [!NOTE]
  > For SharePoint og Excel-datakilder som inneholder kolonnenavn med mellomrom, må du spesifisere hvert mellomrom med **"\_x0020\_"**. Du kan for eksempel angi **"ColumnName"** som **"Column_x0020_Name"**.

## <a name="examples"></a>Eksempler
Eksemplene i denne delen bruker denne datakilden, kalt **IceCream**:

![](media/function-datasourceinfo/icecream.png)

Datakilden har også gitt deg denne informasjonen:

* Visningsnavnet for **Quantity** er "Quantity on Hand".
* Den maksimale lengden på **Flavor** er 30 tegn.
* **Flavor**-kolonnen må inneholde en verdi. **Quantity**-kolonnen er ikke påkrevd.
* Minimum for **Quantity** er 0.
* Maksimum for **Quantity** er 100.
* Den gjeldende brukeren kan lese og redigere postene i datakilden **IceCream**, men kan ikke opprette eller slette poster.

| Formel | Beskrivelse | Resultat |
| --- | --- | --- |
| **DataSourceInfo(&nbsp;IceCream, DataSourceInfo.DisplayName,&nbsp;"Quantity"&nbsp;)** |Returnerer visningsnavnet for **Quantity**-kolonnen i datakilden **IceCream**. |"Quantity on Hand" |
| **DataSourceInfo(&nbsp;IceCream, DataSourceInfo.MaxLength,&nbsp;"Flavor"&nbsp;)** |Returnerer den maksimale lengden på strengen for **Flavor**-kolonnen i datakilden **IceCream**. |30 |
| **DataSourceInfo(&nbsp;IceCream, DataSourceInfo.Required,&nbsp;"Flavor"&nbsp;)** |Er **Smak**-kolonnen i datakilden **IceCream** påkrevd? |**sann** |
| **DataSourceInfo(&nbsp;IceCream, DataSourceInfo.Required,&nbsp;"Quantity"&nbsp;)** |Er **Antall**-kolonnen i datakilden **IceCream** påkrevd? |**usann** |
| **DataSourceInfo(&nbsp;IceCream, DataSourceInfo.Required,&nbsp;"Quantity"&nbsp;)** |Returnerer den numeriske maksimalverdien for **Quantity**-kolonnen i datakilden **IceCream**. |100 |
| **DataSourceInfo(&nbsp;IceCream, DataSourceInfo.MinValue,&nbsp;"Quantity"&nbsp;)** |Returnerer den numeriske minimumsverdien for **Quantity**-kolonnen i datakilden **IceCream**. |0 |
| **DataSourceInfo(&nbsp;IceCream, DataSourceInfo.ReadPermission)** |Kan den gjeldende brukeren lese poster i datakilden **IceCream**? |**sann** |
| **DataSourceInfo(&nbsp;IceCream, DataSourceInfo.EditPermission)** |Kan den gjeldende brukeren endre poster i datakilden **IceCream**? |**sann** |
| **DataSourceInfo(&nbsp;IceCream, DataSourceInfo.CreatePermission)** |Kan den gjeldende brukeren opprette poster i datakilden **IceCream**? |**usann** |
| **DataSourceInfo(&nbsp;IceCream, DataSourceInfo.DeletePermission)** |Kan den gjeldende brukeren slette poster i datakilden **IceCream**? |**usann** |

