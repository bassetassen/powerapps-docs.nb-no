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
ms.openlocfilehash: 9956332c35b4df2773b2634cb7f66d2ea96469e4
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/23/2019
ms.locfileid: "61551058"
---
# <a name="encodeurl-and-plaintext-functions-in-powerapps"></a>Funksjonene EncodeURL og PlainText i PowerApps
Strenger for koder og dekoder.

## <a name="description"></a>Beskrivelse
Den **EncodeUrl** funksjonen koder en nettadressestreng, erstatter bestemte ikke-alfanumeriske tegn med % og et heksadesimalt tall.  

Den **ren tekst** funksjonen fjerner HTML- og XML-koder, konverterer bestemte koder som disse til riktige symboler:

* **&amp;nbsp;**
* **&amp;quot;**

Returverdien fra disse funksjonene er den kodede eller dekodede strengen. Denne funksjonen fjernes ikke alle HTML- og XML-koder. 

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
