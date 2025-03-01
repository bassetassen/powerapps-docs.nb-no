---
title: User-funksjonen | Microsoft Docs
description: Referanseinformasjon for User-funksjonen i PowerApps, inkludert syntaks
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 11/07/2016
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 69da2bbdadc40421e9962de73d531b6c19554eeb
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/07/2019
ms.locfileid: "71983488"
---
# <a name="user-function-in-powerapps"></a>User-funksjonen i PowerApps
Returnerer informasjon om gjeldende bruker.

## <a name="description"></a>Beskrivelse
**User**-funksjonen returnerer en [post](../working-with-tables.md#records) med informasjon om gjeldende bruker:

| Egenskap | Beskrivelse |
| --- | --- |
| **User().Email** |E-postadressen til gjeldende bruker. |
| **User().FullName** |Fullt navn på gjeldende bruker, inkludert fornavn og etternavn. |
| **User().Image** |Bilde av gjeldende bruker. Dette vil være en nettadresse for bilde på formen "blob:*identifier*". Angi **[Image](../controls/properties-visual.md)** -egenskapen for **[Bilde](../controls/control-image.md)** -kontrollen som denne verdien, for å vise bildet i appen. |

> [!NOTE]
> Informasjonen som returneres, er for den gjeldende brukeren av PowerApps.  Det vil samsvare med Kontoinformasjonen som vises i PowerApps-spillerne og studio, som du finner utenfor eventuelle forfattede apper.  Dette kan ikke samsvare med den gjeldende brukerens informasjon i Office 365 eller andre tjenester.

## <a name="syntax"></a>Syntaks
**User**()

## <a name="examples"></a>Eksempler
Gjeldende PowerApps-bruker har følgende informasjon:

* Fullt navn: **«Ola Nordmann»**
* E-postadresse: **john.doe@contoso.com**
* Bilde: ![](media/function-user/john-doe-picture.png) 

|       Formel       |                                                                    Beskrivelse                                                                    |                                                 Resultat                                                  |
|---------------------|---------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------|
|     **User()**      |                                             Informasjonen som returneres er for den gjeldende brukeren av PowerApps.                                             |    { FullName:&nbsp;"John Doe", Email:&nbsp;"john.doe@contoso.com", Image:&nbsp;"blob:1234...5678" }    |
|  **User().Email**   |                                                 E-postadressen til gjeldende bruker av PowerApps.                                                  |                                         "john.doe@contoso.com"                                          |
| **User().FullName** |                                                   Fullt navn på gjeldende bruker av PowerApps.                                                    |                                               "John Doe"                                                |
|  **User().Image**   | Nettadressen til bildet til gjeldende bruker av PowerApps.  Angi **Image**-egenskapen for **Bilde**-kontrollen som denne verdien, for å vise bildet i appen. | "blob:1234...5678"<br><br>Med **ImageControl.Image**:<br>![](media/function-user/john-doe-picture.png) |

