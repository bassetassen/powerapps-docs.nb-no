---
title: Funksjonene EncodeURL og PlainText | Microsoft Docs
description: Referanseinformasjon for funksjonene EncodeURL og PlainText i PowerApps, inkludert syntaks og eksempler
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 11/07/2015
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 30d3378f46e587e45314c30be1fce3c36b2bb120
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/24/2018
ms.locfileid: "42833001"
---
# <a name="encodeurl-and-plaintext-functions-in-powerapps"></a>Funksjonene EncodeURL og PlainText i PowerApps
Strenger for koder og dekoder.

## <a name="description"></a>Beskrivelse
**EncodeURL**-funksjonen koder en nettadressestreng, og erstatter ikke-alfanumeriske tegn med % og et heksadesimalt tall.  

**PlainText**-funksjonen fjerner HTML- og XML-koder, og konverterer koder som disse til riktige symboler:

* **&amp;nbsp;**
* **&amp;quot;**

Returverdien fra disse funksjonene er den kodede eller dekodede strengen.   

## <a name="syntax"></a>Syntaks
**EncodeUrl**( *String* )

* *String* – obligatorisk.  Nettadresse som skal kodes.

**PlainText**( *String* )

* *String* – obligatorisk. Streng som skal fjernes fra HTML- og XML-kode.

## <a name="examples"></a>Eksempler
Hvis du viser en RSS-feed i et tekstgalleri, og deretter angir **[Tekst](../controls/properties-core.md)**-egenskapen for en etikett i det galleriet som **ThisItem.description**, kan etiketten vises som rå HTML- eller XML-kode, som i dette eksempelet:

    <p>We have done an unusually&nbsp;&quot;deep&quot; globalization and localization.<p>

Hvis du angir **[Tekst](../controls/properties-core.md)**-egenskapen til etiketten som **PlainText(ThisItem.description)**, vises teksten som i dette eksempelet:

    We have done an unusually "deep" globalization and localization.
