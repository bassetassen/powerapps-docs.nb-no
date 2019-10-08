---
title: EndsWith- og StartsWith-funksjonen | Microsoft Docs
description: Referanseinformasjon for funksjonene EndsWith og StartsWith i PowerApps, inkludert syntaks og eksempler
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 07/24/2017
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 510e52e5f1711362116809d0870daafb32c9f266
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/07/2019
ms.locfileid: "71992167"
ms.PowerAppsDecimalTransform: true
---
# <a name="endswith-and-startswith-functions-in-powerapps"></a>EndsWith- og StartsWith-funksjonen i PowerApps
Tester om én tekststreng begynner eller slutter med en annen tekststreng.

## <a name="description"></a>Beskrivelse
**EndsWith**-funksjonen tester om én tekststreng slutter med en annen tekststreng.

**StartsWith**-funksjonen tester om én tekststreng begynner med en annen tekststreng.    

Testene med begge funksjonene skiller ikke mellom små eller store bokstaver.  Returverdien til begge er en boolsk **sann**- eller **usann**-verdi.  

Bruk **EndsWith** og **StartsWith** med **[Filter](function-filter-lookup.md)** -funksjonen for å søke i dataene i appen din. Du kan også bruke **[in](operators.md#in-and-exactin-operators)** -operatoren eller **[Search](function-filter-lookup.md)** -funksjonen for å søke hvor som helst i tekststrenger, ikke bare i begynnelsen eller slutten.  Funksjonene du velger avhenger av behovet til appen og hvilke funksjoner som kan [delegeres](../delegation-overview.md) for din bestemte datakilde.  Hvis én av disse funksjonene ikke kan delegeres, vises det en delegeringsadvarsel under redigeringen for å advare deg om denne begrensningen.

## <a name="syntax"></a>Syntaks
**EndsWith**( *Text*; *EndText* )

* *Text* – obligatorisk.  Teksten som skal testes.
* *EndText* – obligatorisk.  Teksten det skal søkes etter på slutten av *Text*.  Hvis *EndText* er en tom streng, returnerer **EndsWith***sann*.

**StartsWith**( *Text*; *StartText* )

* *Text* – obligatorisk.  Teksten som skal testes.
* *StartText* – obligatorisk.  Teksten det skal søkes etter i begynnelsen av *Text*.  Hvis *StartText* er en tom streng, returnerer **StartsWith***sann*.

## <a name="examples"></a>Eksempler

| Formel | Beskrivelse | Resultat |
| --- | --- | --- |
| **EndsWith( "Hello World"; "world" )** |Tester om **"Hello World"** slutter på **"world"** .  Testen skiller ikke mellom små og store bokstaver. |**sann** |
| **EndsWith( "Good bye"; "good" )** |Tester om **"Good bye"** slutter på **"good"** .  *EndText*-argumentet ( **"good"** ) vises i teksten, men ikke på slutten. |**usann** |
| **EndsWith( "Always say hello"; "hello" )** |Tester om **"Always say hello"** slutter med **"hello"** . |**sann** |
| **EndsWith ("Bye Bye", "")** |Tester om **"Bye bye"** slutter på en tom tekststeng (**Len** returnerer 0).  Det er enkelt å bruke **EndsWith** i **Filter**-uttrykk, og er angitt for å returnere **sann** i dette tilfellet. |**sann** |

| Formel | Beskrivelse | Resultat |
| --- | --- | --- |
| **StartsWith( "Hello World"; "hello" )** |Tester om **"Hello World"** begynner med **"hello"** .  Testen skiller ikke mellom små og store bokstaver. |**sann** |
| **StartsWith( "Good bye"; "hello" )** |Tester om **"Good bye"** begynner med **"hello"** . |**usann** |
| **StartsWith( "Always say hello"; "hello" )** |Tester om **"Always say hello"** begynner med **"hello"** .  Selv om **"hello"** vises i teksten, vises det ikke i begynnelsen. |**usann** |
| **StartsWith( "Bye bye"; "" )** |Tester om **"Bye bye"** begynner med en tom tekststeng (**Len** returnerer 0).  Det er enkelt å bruke **StartsWith** i **Filter**-uttrykk, og er angitt for å returnere **sann** i dette tilfellet. |**sann** |

### <a name="search-user-experience"></a>Brukeropplevelse for søk
I mange apper kan du skrive ett eller flere tegn i en søkeboks for å filtrere en liste over poster i et stort datasett. Mens du skriver, viser listen bare de postene som samsvarer med søkevilkårene.

Eksemplene i resten av dette temaet viser resultatene av å søke i en **Kunde**-liste som inneholder disse dataene:

![](media/function-startswith/customers.png)

Hvis du vil opprette denne datakilden som en samling, oppretter du en **[Knapp](../controls/control-button.md)** , og angir egenskapen **OnSelect** til denne formelen:

**ClearCollect (kunder; tabell ({Name: «Fred Garcia»; firma: «Gas tro nor delikat Esser»}; {Name: «Bjørn Miller»; firma: «Contoso»}; {Name: «Glenda Johnson»; firma: «Contoso»}; {Name: «Mike Andresen»; firma: «Adventure Works»}; {Name: «Bjarne Jensen»; firma: «Adventure Works»}))**

Som du ser av dette eksemplet, kan du vise en liste over poster i en [**Galleri-kontroll**](../controls/control-gallery.md) nederst på skjermen. Nær toppen av skjermen kan du legge til en [**Tekstinndata**](../controls/control-text-input.md)-kontroll, som heter **SearchInput**, slik at brukerne kan angi hvilke poster de har interesse av.

![](media/function-startswith/customers-ux-unfiltered.png)

Mens de skriver tegn i **SearchInput**, filtreres resultatene i galleriet automatisk. I dette tilfellet er galleriet konfigurert til å vise poster der navnet på kunden (ikke navnet på firmaet) begynner med tegnsekvensen i **SearchInput**. Hvis brukeren skriver inn **bj** i søkeboksen, viser galleriet disse resultatene:

![](media/function-startswith/customers-ux-startswith-co.png)

Hvis du vil filtrere basert på **Navn**-kolonnen, angir du egenskapen **Elementer** for Galleri-kontrollen til én av disse formlene:

| Formel | Beskrivelse | Resultat |
| --- | --- | --- |
| **Filter( Customers; StartsWith( Name; SearchInput.Text ) )** |Filtrerer **Kunder**-datakilden for poster der søkestrengen vises i begynnelsen av **Navn**-kolonnen. Testen skiller ikke mellom små og store bokstaver. Hvis brukeren skriver **bj** i søkeboksen, viser galleriet **Bjarne Høgdal** og **Bjørn Rosendal**. Galleriet viser ikke **Finn Andresen**, fordi kolonnen **Name** for den posten begynner ikke med den søkestrengen. |<style> img { max-width: none } </style> ![](media/function-startswith/customers-name-co-startswith.png) |
| **Filter( Customers; SearchInput.Text in Name )** |Filtrerer **Kunder**-datakilden for poster der søkestrengen vises hvor som helst i **Navn**-kolonnen. Testen skiller ikke mellom små og store bokstaver. Hvis brukeren skriver **bj** i søkeboksen, viser galleriet **Bjarne Høgdal,** **Bjørn Rosendal** og **Bjarte Andresen**, fordi søkestrengen finnes et sted **Navn**-kolonnen i alle postene. |<style> img { max-width: none } </style> ![](media/function-startswith/customers-name-co-contains.png) |
| **Search( Customers; SearchInput.Text; "Name" )** |Funksjonen **Search** ligner på operatoren **in**, og den søker etter et treff hvor som helst i **Navn**-kolonnen for hver post. Vær oppmerksom på at du må omslutte kolonnenavnet i doble anførselstegn. |<style> img { max-width: none } </style> ![](media/function-startswith/customers-name-co-contains.png) |

Du kan utvide søket til å inkludere kolonnen **Bedrift** så vel som kolonnen **Navn**:

| Formel | Beskrivelse | Resultat |
| --- | --- | --- |
| **Filter( Customers; StartsWith( Name; SearchInput.Text ) &#124;;&#124;; StartsWith( Company; SearchInput.Text ) )** |Filtrerer datakilden **Customers** for posten der enten kolonnen **Name** eller **Company** begynner med søkestrengen (for eksempel **bj**).  Operatoren [ **&#124;&#124;** ](operators.md) er *sann* hvis begge funksjonene **StartsWith** er *sann*. |<style> img { max-width: none } </style> ![](media/function-startswith/customers-all-co-startswith.png) |
| **Filter( Customers; SearchInput.Text in Name &#124;;&#124;; SearchInput.Text in Company )** |Filtrerer **Kunder**-datakilden for posten der enten **Navn**-kolonnen eller **Bedrift**-kolonnen inneholder søkestrengen (for eksempel **bj**). |<style> img { max-width: none } </style> ![](media/function-startswith/customers-all-co-contains.png) |
| **Search( Customers; SearchInput.Text; "Name"; "Company" )** |Funksjonen **Search** ligner på operatoren **in**, og den søker i datakilden **Kunder** etter posten der enten **Navn**-kolonnen eller **Bedrift**-kolonnen inneholder søkestrengen (for eksempel **bj**). Funksjonen **Search** er enklere å lese og skrive enn **Filter** hvis du ønsker å angi flere kolonner og operatorer som **in**. Vær oppmerksom på at du må omslutte kolonnenavnet i doble anførselstegn. |<style> img { max-width: none } </style> ![](media/function-startswith/customers-all-co-contains.png) |

