---
title: Funksjonene If og Switch| Microsoft Docs
description: Referanseinformasjon for funksjonene If og Switch i PowerApps, inkludert syntaks og eksempler
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 04/24/2017
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 40ac3089d3563d220ddac29197b0902f4de88a25
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/24/2018
ms.locfileid: "42836331"
---
# <a name="if-and-switch-functions-in-powerapps"></a>Funksjonene If og Switch i PowerApps
Bestemmer om eventuelle betingelser i et sett er sant (**If**) eller om resultatet av en formel samsvarer med en verdi i et sett (**Switch**) og returnerer deretter et resultat eller utfører en handling.

## <a name="description"></a>Beskrivelse
Funksjonen **If** tester én eller flere betingelser inntil et **sann**-resultat blir funnet. Hvis et slikt resultat blir funnet, returneres en tilsvarende verdi. Hvis ingen slike resultater blir funnet, returneres en standardverdi. I begge tilfeller kan den returnerte verdien være en streng for å vise, en formel for å evaluere eller en annen form for resultat.

**Switch**-funksjonen evaluerer en formel og bestemmer om resultatet samsvarer med en verdi i en rekkefølge som du angir. Hvis et treff finnes, returneres en tilsvarende verdi. Hvis det ikke finnes noen treff, returneres en standardverdi. I begge tilfeller kan den returnerte verdien være en streng for å vise, en formel for å evaluere eller en annen form for resultat.

**If** og **Switch** er svært like, men du bør bruke funksjonen som passer situasjonen din best:

* Bruk **If** til å evaluere en enkel betingelse. Den vanligste syntaksen for denne funksjonen er **If**( *Condition*, *ThenResult*, *DefaultResult* ), som gir det vanlige «hvis ...  deretter ... andre ...» mønsteret som brukes i andre programmeringsverktøy.
* Bruk **If** til å evaluere flere ikke-relaterte betingelser. Du kan angi flere betingelser i PowerApps (i motsetning til Microsoft Excel) uten å måtte neste **If**-formler.
* Bruk **Switch** til å evaluere en enkel betingelse mot flere mulige treff. Du kan også bruke **If** i dette tilfellet, men du må gjenta formelen for hvert mulige treff.

Du kan bruke begge disse funksjonene i [formler for virkemåte](../working-with-formulas-in-depth.md) til å forgrene mellom to eller flere handlinger. Bare én gren utløser en handling. Betingelser og treff evalueres i rekkefølge, og de stopper hvis en betingelse er **sann** eller finner et treff.

*Tom* returneres hvis ingen betingelser er **sann**, ingen treff finnes og du ikke angir et standardresultat.

## <a name="syntax"></a>Syntaks
**If**( *Condition*, *ThenResult* [, *DefaultResult* ] )<br>**If**( *Condition1*, *ThenResult1* [, *Condition2*, *ThenResult2*, ... [ , *DefaultResult* ] ] )

* *Condition(s)* – obligatorisk. Formelen(e) til å teste for **sann**. Slike formler inneholder vanligvis sammenlignende [operatorer](operators.md) (for eksempel **<**, **>** og **=**) og tester funksjoner som **[IsBlank](function-isblank-isempty.md)** og **[IsEmpty](function-isblank-isempty.md)**.
* *ThenResult(s)* – obligatorisk. Den tilsvarende verdien skal returneres for en betingelse som evalueres til **sann**.
* *DefaultResult* – valgfritt. Verdien som skal returneres hvis ingen betingelser evalueres til **sann**.  Hvis du ikke angir dette argumentet, returneres *tom*.

**Switch**( *Formula*, *Match1*, *Result1* [, *Match2*, *Result2*, ... [, *DefaultResult* ] ] )

* *Formel* – obligatorisk. Formelen som skal evalueres for treff.  Denne formelen er evaluert bare én gang.
* *Match(s)* – obligatorisk. Verdier som skal sammenlignes med resultatet fra *formelen*.  Hvis et nøyaktig treff blir funnet, returneres det tilhørende *resultatet*.
* *Result(s)* – obligatorisk. Den tilsvarende verdien skal returneres når det er funnet et nøyaktig treff.
* *DefaultResult* – valgfritt. Hvis det ikke blir funnet et nøyaktig treff, returneres verdien. Hvis du ikke angir dette argumentet, returneres *tom*.

## <a name="examples"></a>Eksempler
### <a name="values-in-formulas"></a>Verdier i formler
I eksemplene nedenfor har en **glidebryter**-kontroll (kalt **Slider1**) en verdi på **25**.

| Formel | Beskrivelse | Resultat |
| --- | --- | --- |
| **If( Slider1.Value&nbsp;=&nbsp;25, "Result1" )** |Betingelsen er **sann**, og det tilsvarende resultatet returneres. |«Result1» |
| **If( Slider1.Value&nbsp;=&nbsp;25, "Result1", "Result2" )** |Betingelsen er **sann**, og det tilsvarende resultatet returneres. |«Result1» |
| **If( Slider1.Value&nbsp;>&nbsp;1000, "Result1" )** |Betingelsen er **usann**, og ingen *DefaultResult* ble angitt. |*tom* |
| **If( Slider1.Value&nbsp;>&nbsp;1000, "Result1", "Result2" )** |Betingelsen er **usann**, et *DefaultResult* ble angitt, og det returneres. |«Result2» |
| **If( Slider1.Value&nbsp;=&nbsp;25, "Result1", Slider1.Value&nbsp;>&nbsp;0, "Result2" )** |Den første betingelsen er **sann**, og det tilsvarende resultatet returneres. Den andre betingelsen er også **sann**, men den evalueres ikke fordi den vises i argumentlisten senere enn en betingelse som evalueres til **sann**. |«Result1» |
| **If( IsBlank(&nbsp;Slider1.Value&nbsp;), "Result1", IsNumeric(&nbsp;Slider1.Value&nbsp;), "Result2" )** |Den første betingelsen er **usann** fordi glidebryteren ikke er *tom*. Den andre betingelsen er **sann** fordi verdien til glidebryteren er et tall, og det tilsvarende resultatet returneres. |«Result2» |
| **If( Slider1.Value&nbsp;>&nbsp;1000, "Result1", Slider1.Value&nbsp;>&nbsp;50, "Result2", "Result3")** |Både første og andre betingelse er **usann**, *DefaultResult* ble angitt, og den returneres. |«Result3» |
| **Switch( Slider1.Value, 25, "Result1" )** |Verdien til glidebryteren samsvarer med den første verdien som skal kontrolleres, og det tilsvarende resultatet returneres. |«Result1» |
| **Switch( Slider1.Value, 20, "Result1", 25, "Result2", 30, "Result3" )** |Verdien til glidebryteren samsvarer med den andre verdien som skal kontrolleres, og det tilsvarende resultatet returneres. |«Result2» |
| **Switch( Slider1.Value, 20, "Result1", 10, "Result2", 0, "Result3", "DefaultResult" )** |Verdien til glidebryteren samsvarer ikke med en verdi som skal kontrolleres.  *DefaultResult* ble angitt, slik at det returneres. |«DefaultResult» |

### <a name="branching-in-behavior-formulas"></a>Forgrening i formler for virkemåte
I disse eksemplene har en **[Tekstinndata](../controls/control-text-input.md)**-kontroll kalt **FirstName** verdien «John» skrevet inn i den.

| Formel | Beskrivelse | Resultat |
| --- | --- | --- |
| **If( ! IsBlank ( FirstName.Text ), Navigate(&nbsp;Screen1, ScreenTransition.None) )** |Betingelsen er **sann**, slik at **[Navigate](function-navigate.md)**-funksjonen kjører. Du kan bruke **[IsBlank](function-isblank-isempty.md)**-funksjonen til å teste om et obligatorisk skjemafelt er fylt ut.  Hvis **FirstName** var [tom](function-isblank-isempty.md), vil ikke denne formelen ha noen innvirkning. |**sann**<br><br>Visningen er endret til **Screen1**. |
| **If( IsBlank( FirstName.Text ), Navigate(&nbsp;Screen1, ScreenTransition.None ), Back() )** |Uten **!** operator, betingelsen er **usann**, slik at **[Navigate](function-navigate.md)**-funksjonen ikke kjøres. **[Back](function-navigate.md)**-funksjonen ble angitt som *DefaultResult*, slik at den kjører. |**sann**<br><br>Visningen går tilbake til skjermbildet som tidligere ble vist. |
| **Switch( FirstName.Text, "Carlos", Navigate(&nbsp;Screen1, ScreenTransition.None ), "Kirstin", Navigate( Screen2, ScreenTransition.None ), "John", Navigate( Screen3, ScreenTransition.None ) )** |Verdien for **FirstName.Text** sammenlignes mot «Carlos», «Kirstin» og «John» i den rekkefølgen. Appen finner et treff med «John», og går til **Screen3**. |**sann**<br><br>Visningen er endret til **Screen3**. |

### <a name="step-by-step"></a>Trinn for trinn
1. Legg til en **[Tekstinndata](../controls/control-text-input.md)**-kontroll, og gi den navnet **Text1** hvis den ikke har det navnet som standard.
2. Skriv **30** i **Text1**.
3. Legg til en **Etikett**-kontroll, og angi **[Tekst](../controls/properties-core.md)**-egenskapen til denne formelen:<br>
   **If( Value(Text1.Text) < 20, "Bestill mye mer!", Value(Text1.Text) < 40, "Bestill mer!", Text1.Text )**
   
    **Etikett**-kontrollen viser **Bestill mer!** fordi verdien av **Text1** er mer enn 20, men mindre enn 40.
4. Skriv **15** i **Text1**.
   
    **Etikett**-kontrollen viser **Bestill mye mer!** fordi verdien av **Text1** er mindre enn 20.
5. Skriv **50** i **Text1**.
   
    **Etikett**-kontrollen viser verdien som du skrev inn fordi den er mer enn 40.

