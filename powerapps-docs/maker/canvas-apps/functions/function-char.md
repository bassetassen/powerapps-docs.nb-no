---
title: Char-funksjonen | Microsoft Docs
description: Referanseinformasjon for Char-funksjonen i PowerApps, inkludert syntaks og eksempler
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 03/01/2019
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 099afb1e89d1551c6c6b969c3ae3688a3cdec777
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/07/2019
ms.locfileid: "71992964"
ms.PowerAppsDecimalTransform: true
---
# <a name="char-function-in-powerapps"></a>Char-funksjonen i PowerApps

Oversetter en tegnkode til en streng.

## <a name="description"></a>Beskrivelse

**Char** -funksjonen oversetter et tall til en streng med tilsvarende ASCII-tegn.

## <a name="syntax"></a>Syntaks

**Char**( *CharacterCode* )

- *CharacterCode* – nødvendig. ASCII-karakterkode å oversette.

## <a name="examples"></a>Eksempler

| Formel | Beskrivelse | Resultat |
| --- | --- | --- |
| **Char (65)** |Returnerer tegnet som samsvarer med ASCII-koden 65. |AV |
| **Char( 105 )** |Returnerer tegnet som samsvarer med ASCII-koden 105. |utdrag |
| **Char( 35 )** |Returnerer tegnet som samsvarer med ASCII-koden 35. |"#" |

### <a name="display-a-character-map"></a>Vis et Tegnkart

1. Legg til en [**Galleri**](../controls/control-gallery.md) -kontroll med et **tomt vannrett** oppsett på en tom skjerm i en tavle-app, og angi deretter disse egenskapene:

    - **Elementer**: `[0;1;2;3;4;5;6;7]`
    - **Bredde**: 800
    - **Høyde**: 500
    - **TemplateSize**: 100
    - **TemplatePadding**: 0

1. Legg til en **Galleri** -kontroll med et **tomt loddrett** oppsett i galleriet, og angi deretter disse egenskapene:

    - **Elementer**: `ForAll( [0;2;3;4;5;6;7;8;9;10;11;12;13;14;15]; Value + ThisItem.Value * 16 )`
    - **Bredde**: 100
    - **Høyde**: 500
    - **TemplateSize**: 30
    - **TemplatePadding**: 0

    Verdien for **Items** -egenskapen multipliserer 16 etter Kol onne nummeret som er angitt i verdi-kolonnen for **Items** -egenskapen fra det første galleriet (0-7 i `ThisItem.Value`). Formelen legger deretter til resultatet i ett av rad numrene fra det andre galleriet (0-15 i post omfanget som [**ForAll**](function-forall.md) -funksjonen gir).

1. I det andre galleriet (loddrett), Legg til en **etikett** -kontroll, og angi disse egenskapene:

    - **Tekst**: `ThisItem.Value`
    - **Bredde**: 50

1. I det andre galleriet (loddrett), Legg til en ny **etikett** -kontroll, og angi disse egenskapene:

    - **Tekst**: `Char( ThisItem.Value )`
    - **Bredde**: 50
    - **X**: 50

Du har opprettet et diagram med de første 128 ASCII-tegnene. Tegn som vises som en liten firkant, kan ikke skrives ut.

![Første 128 ASCII-tegn](media/function-char/chart-lower.png)

Hvis du vil vise de utvidede ASCII-tegnene, kan du angi **elementer** -egenskapen for det andre galleriet til denne formelen, som legger til 128 i hver tegn verdi:

`ForAll( [0;2;3;4;5;6;7;8;9;10;11;12;13;14;15]; Value + ThisItem.Value * 16 + 128)`

![Utvidede ASCII-tegn](media/function-char/chart-higher.png)

Hvis du vil vise tegnene i en annen skrift, kan du angi egenskapen **font** for den andre etiketten til en verdi, for eksempel **Dancing script**.

![Dancing-skript](media/function-char/chart-higher-dancing-script.png)
