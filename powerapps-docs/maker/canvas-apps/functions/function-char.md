---
title: Char-funksjonen | Microsoft Docs
description: Referanseinformasjon for Char-funksjonen i PowerApps, inkludert syntaks og eksempler
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 03/01/2019
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: b7d29d883a14e34dd89d766a6aeffb17275bde6b
ms.sourcegitcommit: 825daacc9a812637815afc1ce6fad28f0cebd479
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/04/2019
ms.locfileid: "57803462"
---
# <a name="char-function-in-powerapps"></a>Char-funksjonen i PowerApps

Oversetter en tegnkode til en streng.

## <a name="description"></a>Beskrivelse

Den **Char** funksjonen oversetter et tall til en streng med det tilsvarende ASCII-tegnet.

## <a name="syntax"></a>Syntaks

**Char**( *CharacterCode* )

- *CharacterCode* – nødvendig. ASCII-karakterkode å oversette.

## <a name="examples"></a>Eksempler

| Formel | Beskrivelse | Resultat |
| --- | --- | --- |
| **Char (65)** |Returnerer tegnet som samsvarer med ASCII-koden 65. |"A" |
| **Char( 105 )** |Returnerer tegnet som samsvarer med ASCII-koden 105. |"i" |
| **Char( 35 )** |Returnerer tegnet som samsvarer med ASCII-koden 35. |"#" |

### <a name="display-a-character-map"></a>Vise et Tegnkart

1. På en tom skjerm i en nettbrett-app, kan du legge til en [ **galleriet** ](../controls/control-gallery.md) kontroll med en **tom vannrett** oppsett, og deretter angi følgende egenskaper:

    - **Elementer**: `[0,1,2,3,4,5,6,7]`
    - **Bredde**: 800
    - **Høyde**: 500
    - **TemplateSize**: 100
    - **TemplatePadding**: 0

1. I galleriet, kan du legge til en **galleriet** kontroll med en **tom loddrett** oppsett, og deretter angi følgende egenskaper:

    - **Elementer**: `ForAll( [0,2,3,4,5,6,7,8,9,10,11,12,13,14,15], Value + ThisItem.Value * 16 )`
    - **Bredde**: 100
    - **Høyde**: 500
    - **TemplateSize**: 30
    - **TemplatePadding**: 0

    Verdien for den **elementer** egenskapen multipliserer 16 ved kolonnenummeret levert av kolonnen verdi den **elementer** egenskapen fra første galleriet (0-7 i ThisItem.Value). Formelen deretter legger til resultatet i en av rad tallene fra det andre galleriet (0-15 i oppføringen omfang som den [ **ForAll** ](function-forall.md) funksjonen gir).

1. I det andre (loddrette) galleriet, kan du legge til en **etikett** kontroll, og angi følgende egenskaper:

    - **Tekst**: `ThisItem.Value`
    - **Bredde**: 50

1. I det andre (loddrette) galleriet, Legg til en annen **etikett** kontroll, og angi følgende egenskaper:

    - **Tekst**: `Char( ThisItem.Value )`
    - **Bredde**: 50
    - **X**: 50

Du har opprettet et diagram av de første 128 ASCII-tegnene. Tegnene som vises som en liten firkant ikke kan skrives ut.

![Først 128 ASCII-tegn](media/function-char/chart-lower.png)

Hvis du vil vise de utvidede ASCII-tegnene, kan du angi den **elementer** -egenskapen for det andre galleriet til denne formelen, som legger til 128 til hver tegnverdien:

`ForAll( [0,2,3,4,5,6,7,8,9,10,11,12,13,14,15], Value + ThisItem.Value * 16 + 128)`

![Utvidede ASCII-tegn](media/function-char/chart-higher.png)

Hvis du vil vise tegnene i en annen skrift, kan du angi den **skrift** -egenskapen for den andre etiketten til en verdi som **"Dansende Script"**.

![Dansende skript](media/function-char/chart-higher-dancing-script.png)