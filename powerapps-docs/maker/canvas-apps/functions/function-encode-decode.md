---
title: Funksjonene EncodeURL og PlainText | Microsoft Docs
description: Referanseinformasjon for funksjonene EncodeURL og PlainText i PowerApps, inkludert syntaks og eksempler
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 11/07/2015
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: c21cae9e39e3a9a1461ac3fafe576f40b70c0818
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/07/2019
ms.locfileid: "71985026"
---
# <a name="encodeurl-and-plaintext-functions-in-powerapps"></a>Funksjonene EncodeURL og PlainText i PowerApps
Strenger for koder og dekoder.

## <a name="description"></a>Beskrivelse
**EncodeUrl** -funksjonen koder en URL-streng, og erstatter enkelte ikke-alfanumeriske tegn med% og et heksadesimalt tall.  

**Ren tekst** -funksjonen fjerner HTML-og XML-koder, noe som gjør det mulig å konvertere bestemte koder som disse til et passende symbol:

* **&amp;nbsp;**
* **&amp;quot;**

Returverdien fra disse funksjonene er den kodede eller dekodede strengen. Denne funksjonen fjerner ikke alle HTML-og XML-koder. 

## <a name="syntax"></a>Syntaks
**EncodeUrl**( *String* )

* *String* – obligatorisk.  Nettadresse som skal kodes.

**PlainText**( *String* )

* *String* – obligatorisk. Streng som skal fjernes fra HTML- og XML-kode.

## <a name="examples"></a>Eksempler
Hvis du viser en RSS-feed i et tekstgalleri, og deretter angir **[Tekst](../controls/properties-core.md)** -egenskapen for en etikett i det galleriet som **ThisItem.description**, kan etiketten vises som rå HTML- eller XML-kode, som i dette eksempelet:

```html
    <p>We have done an unusually&nbsp;&quot;deep&quot; globalization and localization.<p>
```

Hvis du angir **[Tekst](../controls/properties-core.md)** -egenskapen til etiketten som **PlainText(ThisItem.description)** , vises teksten som i dette eksempelet:

```
    We have done an unusually "deep" globalization and localization.
```