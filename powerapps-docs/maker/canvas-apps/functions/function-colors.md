---
title: Color-opplisting og ColorFade-, ColorValue- og RGBA-funksjoner | Microsoft Docs
description: Referanseinformasjon for Color-opplisting og funksjonene ColorFade, ColorValue og RGBA i PowerApps, inkludert syntaks og eksempler
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 06/04/2019
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 4af851160ea8a2add22add9f79dcc181a734e715
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/07/2019
ms.locfileid: "71994846"
---
# <a name="color-enumeration-and-colorfade-colorvalue-and-rgba-functions-in-powerapps"></a>Color-opplisting og funksjonene ColorFade, ColorValue og RGBA i PowerApps

Bruk innebygde farge verdier, Definer egen definerte farger, og bruk alfa kanalen.

## <a name="description"></a>Beskrivelse

Ved å bruke **farge** nummereringen får du enkel tilgang til fargene som er definert av HTML-GJENNOMGRIPENDE STILARK (CSS). For eksempel returnerer **Color. Red** rent rødt. Du finner en liste over disse fargene på slutten av dette emnet.

**ColorValue** -funksjonen returnerer en farge basert på en farge streng i et CSS. Strengen kan ta et hvilket som helst av disse skjemaene:

- **CSS-farge navn:** **«RoxyBrown»** og **«OliveDrab»** er eksempler. Disse navnene inneholder ikke mellomrom. Listen over støttede farger vises senere i dette emnet.
- **6-sifret heksadesimal verdi:** Eksempel **: #ffd700** er det samme som **«Gold»** . Strengen er i formatet "#*rrggbb*" der *RR* er den røde delen i to heksadesimale sifre, *GG* er den grønne og *bb* er den blå.
- **8-sifret heksadesimal verdi:** **"#Ff7f5080"** er for eksempel det samme som **«korall rødt»** med en 50% alfa kanal. Strengen er i formatet "#*rrggbbaa*" der *RR*, *GG*og *bb* er identiske til skjemaet på 6 sifre. Alfa kanalen representeres av *AA*: **00** representerer fullstendig gjennomsiktig, og **FF** representerer fullstendig ugjennomsiktig.

**RGBA** -funksjonen returnerer en farge basert på røde, grønne og blå komponenter. Funksjonen inkluderer også en alfa kanal for å blande farger i kontroller som er lagvis foran hverandre. En alfa kanal varierer fra 0 eller 0% (som er fullstendig gjennomsiktig og usynlig) til 1 eller 100% (som er helt ugjennomsiktig og blokkerer alle lagene bak en kontroll).

**ColorFade**-funksjonen returnerer en lysere eller mørkere versjon av en farge. Uttoningen varierer fra-1 (som gjør at fargen blir mørkere til svart) til 0 (som ikke påvirker fargen) til 1 (som gjør en farge lysere til hvit).

## <a name="alpha-channel"></a>Alfa kanal

I en lerret-app kan du lag kontroller foran hverandre, og angi gjennomsiktigheten for en kontroll til eventuelle kontroller som er bak den. Som et resultat vil fargene blandes gjennom lagene. Dette diagrammet viser for eksempel hvordan de tre primær fargene blandes med en alfa innstilling på 50%:

> [!div class="mx-imgBorder"]
> @no__t – 0Three primær farger med en alfa innstilling på 50% ](media/function-colors/alpha-primary.png)

Du kan også blande bilder i fil formater som støtter alfa kanaler. Du kan for eksempel ikke blande JPEG-filer, men du kunne blande PNG-filer. Den neste grafikken viser de samme røde, grønne og blå fargene fra det forrige eksemplet, men den røde fargen vises som en uregelmessig (i stedet for en sirkel) i en PNG-fil med en 50% alfa kanal:

> [!div class="mx-imgBorder"]
> @no__t – 0Red uregelmessig med en alfa innstilling på 50% foran blå og grønne sirkler @ no__t-1

Hvis du angir en **farge** opplistings verdi eller bygger en **ColorValue** -formel med et farge navn eller en heksadesimal verdi på 6 sifre, er alfa innstillingen 100%, som er helt ugjennomsiktig.

## <a name="syntax"></a>Syntaks

**Color**.*ColorName*

- *ColorName* – obligatorisk.  Et fargenavn for gjennomgripende stilark (CSS). Listen over mulige opplistings verdier vises på slutten av dette emnet.

**ColorValue**( *CSSColor* )

- *CSSColor* – obligatorisk.  En fargedefinisjon for gjennomgripende stilark (CSS). Du kan angi et navn, for eksempel **OliveDrab**, eller en heksadesimal verdi, for eksempel **#6b8e23** eller **#7fffd420**. Heksadesimale verdier kan ta formen av enten #*rrggbb* eller #*rrggbbaa*.

**RGBA**( *Red*, *Green*, *Blue*, *Alpha* )

- *Red*, *Green*, *Blue* – obligatorisk.  Farge komponent verdier, som er fra 0 (ingen metning) til 255 (full metning).
- *Alpha* – obligatorisk.  Alfa komponent, som strekker seg fra 0 (helt gjennomsiktig) til 1 (fullstendig ugjennomsiktig). Du kan også bruke en prosentandel, fra 0 til 100 %.

**ColorFade**( *Color*, *FadeAmount* )

- *Color* – obligatorisk.  En fargeverdi, for eksempel **Color.Red**, eller utdataene fra **ColorValue** eller **RGBA**.
- *FadeAmount* – obligatorisk.  Et tall mellom -1 og 1. -1 gjør en farge fullstendig mørkere, 0 påvirker ikke fargen, og 1 gjør en farge hvit lysere. Du kan også bruke en prosent del fra-100% til 100%.

## <a name="built-in-colors"></a>Innebygde farger

| Color-opplisting | ColorValue | RGBA | Fargekart |
| --- | --- | --- | --- |
| **Color.AliceBlue** |**ColorValue ("#f0f8ff" &nbsp;)**<br>**ColorValue ("aliceblue" &nbsp;)** |**RGBA (&nbsp;240, &nbsp;248, &nbsp;255, &nbsp;1 @ NO__T-5)** |![aliceblue](./media/function-colors/color-aliceblue.png) |
| **Color.AntiqueWhite** |**ColorValue ("#faebd7" &nbsp;)**<br>**ColorValue ("AntiqueWhite" &nbsp;)** |**RGBA (&nbsp;250, &nbsp;235, &nbsp;215, &nbsp;1 @ NO__T-5)** |![antiquewhite](./media/function-colors/color-antiquewhite.png) |
| **Color.Aqua** |**ColorValue ("#00ffff" &nbsp;)**<br>**ColorValue («AKVAMARIN» &nbsp;)** |**RGBA (&nbsp;0, &nbsp;255, &nbsp;255, &nbsp;1 @ NO__T-5)** |![aqua](./media/function-colors/color-aqua.png) |
| **Color.Aquamarine** |**ColorValue ("#7fffd4" &nbsp;)**<br>**ColorValue ("akvamarin" &nbsp;)** |**RGBA (&nbsp;127, &nbsp;255, &nbsp;212, &nbsp;1 @ NO__T-5)** |![aquamarine](./media/function-colors/color-aquamarine.png) |
| **Color.Azure** |**ColorValue ("#f0ffff" &nbsp;)**<br>**ColorValue («Azure» &nbsp;)** |**RGBA (&nbsp;240, &nbsp;255, &nbsp;255, &nbsp;1 @ NO__T-5)** |![azure](./media/function-colors/color-azure.png) |
| **Color.Beige** |**ColorValue ("#f5f5dc" &nbsp;)**<br>**ColorValue ("beige" &nbsp;)** |**RGBA (&nbsp;245, &nbsp;245, &nbsp;220, &nbsp;1 @ NO__T-5)** |![beige](./media/function-colors/color-beige.png) |
| **Color.Bisque** |**ColorValue ("#ffe4c4" &nbsp;)**<br>**ColorValue ("BISQUE" &nbsp;)** |**RGBA (&nbsp;255, &nbsp;228, &nbsp;196, &nbsp;1 @ NO__T-5)** |![bisque](./media/function-colors/color-bisque.png) |
| **Color.Black** |**ColorValue ("#000000" &nbsp;)**<br>**ColorValue («svart» &nbsp;)** |**RGBA (&nbsp;0, &nbsp;0, &nbsp;0, &nbsp;1 @ NO__T-5)** |![black](./media/function-colors/color-black.png) |
| **Color.BlanchedAlmond** |**ColorValue ("#ffebcd" &nbsp;)**<br>**ColorValue ("blanchedalmond" &nbsp;)** |**RGBA (&nbsp;255, &nbsp;235, &nbsp;205, &nbsp;1 @ NO__T-5)** |![blanchedalmond](./media/function-colors/color-blanchedalmond.png) |
| **Color.Blue** |**ColorValue ("#0000ff" &nbsp;)**<br>**ColorValue («blå» &nbsp;)** |**RGBA (&nbsp;0, &nbsp;0, &nbsp;255, &nbsp;1 @ NO__T-5)** |![blue](./media/function-colors/color-blue.png) |
| **Color.BlueViolet** |**ColorValue ("#8a2be2" &nbsp;)**<br>**ColorValue ("BLUEVIOLET" &nbsp;)** |**RGBA (&nbsp;138, &nbsp;43, &nbsp;226, &nbsp;1 @ NO__T-5)** |![blueviolet](./media/function-colors/color-blueviolet.png) |
| **Color.Brown** |**ColorValue ("#a52a2a" &nbsp;)**<br>**ColorValue («brun» &nbsp;)** |**RGBA (&nbsp;165, &nbsp;42, &nbsp;42, &nbsp;1 @ NO__T-5)** |![brown](./media/function-colors/color-brown.png) |
| **Color.Burlywood** |**ColorValue ("#deb887" &nbsp;)**<br>**ColorValue ("burlywood" &nbsp;)** |**RGBA (&nbsp;222, &nbsp;184, &nbsp;135, &nbsp;1 @ NO__T-5)** |![burlywood](./media/function-colors/color-burlywood.png) |
| **Color.CadetBlue** |**ColorValue ("#5f9ea0" &nbsp;)**<br>**ColorValue ("CadetBlue" &nbsp;)** |**RGBA (&nbsp;95, &nbsp;158, &nbsp;160, &nbsp;1 @ NO__T-5)** |![cadetblue](./media/function-colors/color-cadetblue.png) |
| **Color.Chartreuse** |**ColorValue ("#7fff00" &nbsp;)**<br>**ColorValue ("CHARTREUSE" &nbsp;)** |**RGBA (&nbsp;127, &nbsp;255, &nbsp;0, &nbsp;1 @ NO__T-5)** |![chartreuse](./media/function-colors/color-chartreuse.png) |
| **Color.Chocolate** |**ColorValue ("#d2691e" &nbsp;)**<br>**ColorValue («sjokolade» &nbsp;)** |**RGBA (&nbsp;210, &nbsp;105, &nbsp;30, &nbsp;1 @ NO__T-5)** |![chocolate](./media/function-colors/color-chocolate.png) |
| **Color.Coral** |**ColorValue ("#ff7f50" &nbsp;)**<br>**ColorValue ("korall rødt" &nbsp;)** |**RGBA (&nbsp;255, &nbsp;127, &nbsp;80, &nbsp;1 @ NO__T-5)** |![coral](./media/function-colors/color-coral.png) |
| **Color.CornflowerBlue** |**ColorValue ("#6495ed" &nbsp;)**<br>**ColorValue ("CornflowerBlue" &nbsp;)** |**RGBA (&nbsp;100, &nbsp;149, &nbsp;237, &nbsp;1 @ NO__T-5)** |![cornflowerblue](./media/function-colors/color-cornflowerblue.png) |
| **Color.Cornsilk** |**ColorValue ("#fff8dc" &nbsp;)**<br>**ColorValue ("lys KORNGUL" &nbsp;)** |**RGBA (&nbsp;255, &nbsp;248, &nbsp;220, &nbsp;1 @ NO__T-5)** |![cornsilk](./media/function-colors/color-cornsilk.png) |
| **Color.Crimson** |**ColorValue ("#dc143c" &nbsp;)**<br>**ColorValue («Crimson» &nbsp;)** |**RGBA (&nbsp;220, &nbsp;20, &nbsp;60, &nbsp;1 @ NO__T-5)** |![crimson](./media/function-colors/color-crimson.png) |
| **Color.Cyan** |**ColorValue ("#00ffff" &nbsp;)**<br>**ColorValue («cyan» &nbsp;)** |**RGBA (&nbsp;0, &nbsp;255, &nbsp;255, &nbsp;1 @ NO__T-5)** |![cyan](./media/function-colors/color-cyan.png) |
| **Color.DarkBlue** |**ColorValue ("#00008b" &nbsp;)**<br>**ColorValue ("DarkBlue" &nbsp;)** |**RGBA (&nbsp;0, &nbsp;0, &nbsp;139, &nbsp;1 @ NO__T-5)** |![darkblue](./media/function-colors/color-darkblue.png) |
| **Color.DarkCyan** |**ColorValue ("#008b8b" &nbsp;)**<br>**ColorValue ("DARKCYAN" &nbsp;)** |**RGBA (&nbsp;0, &nbsp;139, &nbsp;139, &nbsp;1 @ NO__T-5)** |![darkcyan](./media/function-colors/color-darkcyan.png) |
| **Color.DarkGoldenRod** |**ColorValue ("#b8860b" &nbsp;)**<br>**ColorValue ("DarkGoldenRod" &nbsp;)** |**RGBA (&nbsp;184, &nbsp;134, &nbsp;11, &nbsp;1 @ NO__T-5)** |![darkgoldenrod](./media/function-colors/color-darkgoldenrod.png) |
| **Color.DarkGray** |**ColorValue ("#a9a9a9" &nbsp;)**<br>**ColorValue ("darkgray" &nbsp;)** |**RGBA (&nbsp;169, &nbsp;169, &nbsp;169, &nbsp;1 @ NO__T-5)** |![darkgray](./media/function-colors/color-darkgray.png) |
| **Color.DarkGreen** |**ColorValue ("#006400" &nbsp;)**<br>**ColorValue ("DarkGreen" &nbsp;)** |**RGBA (&nbsp;0, &nbsp;100, &nbsp;0, &nbsp;1 @ NO__T-5)** |![darkgreen](./media/function-colors/color-darkgreen.png) |
| **Color.DarkGrey** |**ColorValue ("#a9a9a9" &nbsp;)**<br>**ColorValue ("DARKGREY" &nbsp;)** |**RGBA (&nbsp;169, &nbsp;169, &nbsp;169, &nbsp;1 @ NO__T-5)** |![darkgrey](./media/function-colors/color-darkgrey.png) |
| **Color.DarkKhaki** |**ColorValue ("#bdb76b" &nbsp;)**<br>**ColorValue ("DarkKhaki" &nbsp;)** |**RGBA (&nbsp;189, &nbsp;183, &nbsp;107, &nbsp;1 @ NO__T-5)** |![darkkhaki](./media/function-colors/color-darkkhaki.png) |
| **Color.DarkMagenta** |**ColorValue ("#8b008b" &nbsp;)**<br>**ColorValue ("darkmagenta" &nbsp;)** |**RGBA (&nbsp;139, &nbsp;0, &nbsp;139, &nbsp;1 @ NO__T-5)** |![darkmagenta](./media/function-colors/color-darkmagenta.png) |
| **Color.DarkOliveGreen** |**ColorValue ("#556b2f" &nbsp;)**<br>**ColorValue ("DarkOliveGreen" &nbsp;)** |**RGBA (&nbsp;85, &nbsp;107, &nbsp;47, &nbsp;1 @ NO__T-5)** |![darkolivegreen](./media/function-colors/color-darkolivegreen.png) |
| **Color.DarkOrange** |**ColorValue ("#ff8c00" &nbsp;)**<br>**ColorValue ("DARKORANGE" &nbsp;)** |**RGBA (&nbsp;255, &nbsp;140, &nbsp;0, &nbsp;1 @ NO__T-5)** |![darkorange](./media/function-colors/color-darkorange.png) |
| **Color.DarkOrchid** |**ColorValue ("#9932cc" &nbsp;)**<br>**ColorValue ("DarkOrchid" &nbsp;)** |**RGBA (&nbsp;153, &nbsp;50, &nbsp;204, &nbsp;1 @ NO__T-5)** |![darkorchid](./media/function-colors/color-darkorchid.png) |
| **Color.DarkRed** |**ColorValue ("#8b0000" &nbsp;)**<br>**ColorValue ("darkred" &nbsp;)** |**RGBA (&nbsp;139, &nbsp;0, &nbsp;0, &nbsp;1 @ NO__T-5)** |![darkred](./media/function-colors/color-darkred.png) |
| **Color.DarkSalmon** |**ColorValue ("#e9967a" &nbsp;)**<br>**ColorValue ("DarkSalmon" &nbsp;)** |**RGBA (&nbsp;233, &nbsp;150, &nbsp;122, &nbsp;1 @ NO__T-5)** |![darksalmon](./media/function-colors/color-darksalmon.png) |
| **Color.DarkSeaGreen** |**ColorValue ("#8fbc8f" &nbsp;)**<br>**ColorValue ("DARKSEAGREEN" &nbsp;)** |**RGBA (&nbsp;143, &nbsp;188, &nbsp;143, &nbsp;1 @ NO__T-5)** |![darkseagreen](./media/function-colors/color-darkseagreen.png) |
| **Color.DarkSlateBlue** |**ColorValue ("#483d8b" &nbsp;)**<br>**ColorValue ("DarkSlateBlue" &nbsp;)** |**RGBA (&nbsp;72, &nbsp;61, &nbsp;139, &nbsp;1 @ NO__T-5)** |![darkslateblue](./media/function-colors/color-darkslateblue.png) |
| **Color.DarkSlateGray** |**ColorValue ("#2f4f4f" &nbsp;)**<br>**ColorValue ("darkslategray" &nbsp;)** |**RGBA (&nbsp;47, &nbsp;79, &nbsp;79, &nbsp;1 @ NO__T-5)** |![darkslategray](./media/function-colors/color-darkslategray.png) |
| **Color.DarkSlateGrey** |**ColorValue ("#2f4f4f" &nbsp;)**<br>**ColorValue ("DarkSlateGrey" &nbsp;)** |**RGBA (&nbsp;47, &nbsp;79, &nbsp;79, &nbsp;1 @ NO__T-5)** |![darkslategrey](./media/function-colors/color-darkslategrey.png) |
| **Color.DarkTurquoise** |**ColorValue ("#00ced1" &nbsp;)**<br>**ColorValue ("DARKTURQUOISE" &nbsp;)** |**RGBA (&nbsp;0, &nbsp;206, &nbsp;209, &nbsp;1 @ NO__T-5)** |![darkturquoise](./media/function-colors/color-darkturquoise.png) |
| **Color.DarkViolet** |**ColorValue ("#9400d3" &nbsp;)**<br>**ColorValue ("DarkViolet" &nbsp;)** |**RGBA (&nbsp;148, &nbsp;0, &nbsp;211, &nbsp;1 @ NO__T-5)** |![darkviolet](./media/function-colors/color-darkviolet.png) |
| **Color.DeepPink** |**ColorValue ("#ff1493" &nbsp;)**<br>**ColorValue ("deeppink" &nbsp;)** |**RGBA (&nbsp;255, &nbsp;20, &nbsp;147, &nbsp;1 @ NO__T-5)** |![deeppink](./media/function-colors/color-deeppink.png) |
| **Color.DeepSkyBlue** |**ColorValue ("#00bfff" &nbsp;)**<br>**ColorValue ("DeepSkyBlue" &nbsp;)** |**RGBA (&nbsp;0, &nbsp;191, &nbsp;255, &nbsp;1 @ NO__T-5)** |![deepskyblue](./media/function-colors/color-deepskyblue.png) |
| **Color.DimGray** |**ColorValue ("#696969" &nbsp;)**<br>**ColorValue ("DIMGRAY" &nbsp;)** |**RGBA (&nbsp;105, &nbsp;105, &nbsp;105, &nbsp;1 @ NO__T-5)** |![dimgray](./media/function-colors/color-dimgray.png) |
| **Color.DimGrey** |**ColorValue ("#696969" &nbsp;)**<br>**ColorValue ("DimGrey" &nbsp;)** |**RGBA (&nbsp;105, &nbsp;105, &nbsp;105, &nbsp;1 @ NO__T-5)** |![dimgrey](./media/function-colors/color-dimgrey.png) |
| **Color.DodgerBlue** |**ColorValue ("#1e90ff" &nbsp;)**<br>**ColorValue ("dodgerblue" &nbsp;)** |**RGBA (&nbsp;30, &nbsp;144, &nbsp;255, &nbsp;1 @ NO__T-5)** |![dodgerblue](./media/function-colors/color-dodgerblue.png) |
| **Color.FireBrick** |**ColorValue ("#b22222" &nbsp;)**<br>**ColorValue ("FireBrick" &nbsp;)** |**RGBA (&nbsp;178, &nbsp;34, &nbsp;34, &nbsp;1 @ NO__T-5)** |![firebrick](./media/function-colors/color-firebrick.png) |
| **Color.FloralWhite** |**ColorValue ("#fffaf0" &nbsp;)**<br>**ColorValue ("FLORALWHITE" &nbsp;)** |**RGBA (&nbsp;255, &nbsp;250, &nbsp;240, &nbsp;1 @ NO__T-5)** |![floralwhite](./media/function-colors/color-floralwhite.png) |
| **Color.ForestGreen** |**ColorValue ("#228b22" &nbsp;)**<br>**ColorValue ("ForestGreen" &nbsp;)** |**RGBA (&nbsp;34, &nbsp;139, &nbsp;34, &nbsp;1 @ NO__T-5)** |![forestgreen](./media/function-colors/color-forestgreen.png) |
| **Color.Fuchsia** |**ColorValue ("#ff00ff" &nbsp;)**<br>**ColorValue ("fuchsia" &nbsp;)** |**RGBA (&nbsp;255, &nbsp;0, &nbsp;255, &nbsp;1 @ NO__T-5)** |![fuchsia](./media/function-colors/color-fuchsia.png) |
| **Color.Gainsboro** |**ColorValue ("#dcdcdc" &nbsp;)**<br>**ColorValue ("lys grå" &nbsp;)** |**RGBA (&nbsp;220, &nbsp;220, &nbsp;220, &nbsp;1 @ NO__T-5)** |![gainsboro](./media/function-colors/color-gainsboro.png) |
| **Color.GhostWhite** |**ColorValue ("#f8f8ff" &nbsp;)**<br>**ColorValue ("GHOSTWHITE" &nbsp;)** |**RGBA (&nbsp;248, &nbsp;248, &nbsp;255, &nbsp;1 @ NO__T-5)** |![ghostwhite](./media/function-colors/color-ghostwhite.png) |
| **Color.Gold** |**ColorValue ("#ffd700" &nbsp;)**<br>**ColorValue («gull» &nbsp;)** |**RGBA (&nbsp;255, &nbsp;215, &nbsp;0, &nbsp;1 @ NO__T-5)** |![gold](./media/function-colors/color-gold.png) |
| **Color.GoldenRod** |**ColorValue ("#daa520" &nbsp;)**<br>**ColorValue ("gyldenris" &nbsp;)** |**RGBA (&nbsp;218, &nbsp;165, &nbsp;32, &nbsp;1 @ NO__T-5)** |![goldenrod](./media/function-colors/color-goldenrod.png) |
| **Color.Gray** |**ColorValue ("#808080" &nbsp;)**<br>**ColorValue («grå» &nbsp;)** |**RGBA (&nbsp;128, &nbsp;128, &nbsp;128, &nbsp;1 @ NO__T-5)** |![gray](./media/function-colors/color-gray.png) |
| **Color.Green** |**ColorValue ("#008000" &nbsp;)**<br>**ColorValue («grønn» &nbsp;)** |**RGBA (&nbsp;0, &nbsp;128, &nbsp;0, &nbsp;1 @ NO__T-5)** |![green](./media/function-colors/color-green.png) |
| **Color.GreenYellow** |**ColorValue ("#adff2f" &nbsp;)**<br>**ColorValue ("GreenYellow" &nbsp;)** |**RGBA (&nbsp;173, &nbsp;255, &nbsp;47, &nbsp;1 @ NO__T-5)** |![greenyellow](./media/function-colors/color-greenyellow.png) |
| **Color.Grey** |**ColorValue ("#808080" &nbsp;)**<br>**ColorValue («grå» &nbsp;)** |**RGBA (&nbsp;128, &nbsp;128, &nbsp;128, &nbsp;1 @ NO__T-5)** |![grey](./media/function-colors/color-grey.png) |
| **Color.Honeydew** |**ColorValue ("#f0fff0" &nbsp;)**<br>**ColorValue ("Honeydew" &nbsp;)** |**RGBA (&nbsp;240, &nbsp;255, &nbsp;240, &nbsp;1 @ NO__T-5)** |![honeydew](./media/function-colors/color-honeydew.png) |
| **Color.HotPink** |**ColorValue ("#ff69b4" &nbsp;)**<br>**ColorValue ("HOTPINK" &nbsp;)** |**RGBA (&nbsp;255, &nbsp;105, &nbsp;180, &nbsp;1 @ NO__T-5)** |![hotpink](./media/function-colors/color-hotpink.png) |
| **Color.IndianRed** |**ColorValue ("#cd5c5c" &nbsp;)**<br>**ColorValue ("IndianRed" &nbsp;)** |**RGBA (&nbsp;205, &nbsp;92, &nbsp;92, &nbsp;1 @ NO__T-5)** |![indianred](./media/function-colors/color-indianred.png) |
| **Color.Indigo** |**ColorValue ("#4b0082" &nbsp;)**<br>**ColorValue ("Indigo" &nbsp;)** |**RGBA (&nbsp;75, &nbsp;0, &nbsp;130, &nbsp;1 @ NO__T-5)** |![indigo](./media/function-colors/color-indigo.png) |
| **Color.Ivory** |**ColorValue ("#fffff0" &nbsp;)**<br>**ColorValue ("Elfenbenskysten" &nbsp;)** |**RGBA (&nbsp;255, &nbsp;255, &nbsp;240, &nbsp;1 @ NO__T-5)** |![ivory](./media/function-colors/color-ivory.png) |
| **Color.Khaki** |**ColorValue ("#f0e68c" &nbsp;)**<br>**ColorValue ("kaki" &nbsp;)** |**RGBA (&nbsp;240, &nbsp;230, &nbsp;140, &nbsp;1 @ NO__T-5)** |![khaki](./media/function-colors/color-khaki.png) |
| **Color.Lavender** |**ColorValue ("#e6e6fa" &nbsp;)**<br>**ColorValue ("lavendel" &nbsp;)** |**RGBA (&nbsp;230, &nbsp;230, &nbsp;250, &nbsp;1 @ NO__T-5)** |![lavender](./media/function-colors/color-lavender.png) |
| **Color.LavenderBlush** |**ColorValue ("#fff0f5" &nbsp;)**<br>**ColorValue ("lavenderblush" &nbsp;)** |**RGBA (&nbsp;255, &nbsp;240, &nbsp;245, &nbsp;1 @ NO__T-5)** |![lavenderblush](./media/function-colors/color-lavenderblush.png) |
| **Color.LawnGreen** |**ColorValue ("#7cfc00" &nbsp;)**<br>**ColorValue ("LawnGreen" &nbsp;)** |**RGBA (&nbsp;124, &nbsp;252, &nbsp;0, &nbsp;1 @ NO__T-5)** |![lawngreen](./media/function-colors/color-lawngreen.png) |
| **Color.LemonChiffon** |**ColorValue ("#fffacd" &nbsp;)**<br>**ColorValue ("LEMONCHIFFON" &nbsp;)** |**RGBA (&nbsp;255, &nbsp;250, &nbsp;205, &nbsp;1 @ NO__T-5)** |![lemonchiffon](./media/function-colors/color-lemonchiffon.png) |
| **Color.LightBlue** |**ColorValue ("#add8e6" &nbsp;)**<br>**ColorValue ("LightBlue" &nbsp;)** |**RGBA (&nbsp;173, &nbsp;216, &nbsp;230, &nbsp;1 @ NO__T-5)** |![lightblue](./media/function-colors/color-lightblue.png) |
| **Color.LightCoral** |**ColorValue ("#f08080" &nbsp;)**<br>**ColorValue ("lightcoral" &nbsp;)** |**RGBA (&nbsp;240, &nbsp;128, &nbsp;128, &nbsp;1 @ NO__T-5)** |![lightcoral](./media/function-colors/color-lightcoral.png) |
| **Color.LightCyan** |**ColorValue ("#e0ffff" &nbsp;)**<br>**ColorValue ("LightCyan" &nbsp;)** |**RGBA (&nbsp;224, &nbsp;255, &nbsp;255, &nbsp;1 @ NO__T-5)** |![lightcyan](./media/function-colors/color-lightcyan.png) |
| **Color.LightGoldenRodYellow** |**ColorValue ("#fafad2" &nbsp;)**<br>**ColorValue ("lightgoldenrodyellow" &nbsp;)** |**RGBA (&nbsp;250, &nbsp;250, &nbsp;210, &nbsp;1 @ NO__T-5)** |![lightgoldenrodyellow](./media/function-colors/color-lightgoldenrodyellow.png) |
| **Color.LightGray** |**ColorValue ("#d3d3d3" &nbsp;)**<br>**ColorValue ("LightGray" &nbsp;)** |**RGBA (&nbsp;211, &nbsp;211, &nbsp;211, &nbsp;1 @ NO__T-5)** |![lightgray](./media/function-colors/color-lightgray.png) |
| **Color.LightGreen** |**ColorValue ("#90ee90" &nbsp;)**<br>**ColorValue ("Lightgreen" &nbsp;)** |**RGBA (&nbsp;144, &nbsp;238, &nbsp;144, &nbsp;1 @ NO__T-5)** |![lightgreen](./media/function-colors/color-lightgreen.png) |
| **Color.LightGrey** |**ColorValue ("#d3d3d3" &nbsp;)**<br>**ColorValue ("LightGrey" &nbsp;)** |**RGBA (&nbsp;211, &nbsp;211, &nbsp;211, &nbsp;1 @ NO__T-5)** |![lightgrey](./media/function-colors/color-lightgrey.png) |
| **Color.LightPink** |**ColorValue ("#ffb6c1" &nbsp;)**<br>**ColorValue ("LIGHTPINK" &nbsp;)** |**RGBA (&nbsp;255, &nbsp;182, &nbsp;193, &nbsp;1 @ NO__T-5)** |![lightpink](./media/function-colors/color-lightpink.png) |
| **Color.LightSalmon** |**ColorValue ("#ffa07a" &nbsp;)**<br>**ColorValue ("LightSalmon" &nbsp;)** |**RGBA (&nbsp;255, &nbsp;160, &nbsp;122, &nbsp;1 @ NO__T-5)** |![lightsalmon](./media/function-colors/color-lightsalmon.png) |
| **Color.LightSeaGreen** |**ColorValue ("#20b2aa" &nbsp;)**<br>**ColorValue ("lightseagreen" &nbsp;)** |**RGBA (&nbsp;32, &nbsp;178, &nbsp;170, &nbsp;1 @ NO__T-5)** |![lightseagreen](./media/function-colors/color-lightseagreen.png) |
| **Color.LightSkyBlue** |**ColorValue ("#87cefa" &nbsp;)**<br>**ColorValue ("LightSkyBlue" &nbsp;)** |**RGBA (&nbsp;135, &nbsp;206, &nbsp;250, &nbsp;1 @ NO__T-5)** |![lightskyblue](./media/function-colors/color-lightskyblue.png) |
| **Color.LightSlateGray** |**ColorValue ("#778899" &nbsp;)**<br>**ColorValue ("LIGHTSLATEGRAY" &nbsp;)** |**RGBA (&nbsp;119, &nbsp;136, &nbsp;153, &nbsp;1 @ NO__T-5)** |![lightslategray](./media/function-colors/color-lightslategray.png) |
| **Color.LightSlateGrey** |**ColorValue ("#778899" &nbsp;)**<br>**ColorValue ("LightSlateGrey" &nbsp;)** |**RGBA (&nbsp;119, &nbsp;136, &nbsp;153, &nbsp;1 @ NO__T-5)** |![lightslategrey](./media/function-colors/color-lightslategrey.png) |
| **Color.LightSteelBlue** |**ColorValue ("#b0c4de" &nbsp;)**<br>**ColorValue ("lightsteelblue" &nbsp;)** |**RGBA (&nbsp;176, &nbsp;196, &nbsp;222, &nbsp;1 @ NO__T-5)** |![lightsteelblue](./media/function-colors/color-lightsteelblue.png) |
| **Color.LightYellow** |**ColorValue ("#ffffe0" &nbsp;)**<br>**ColorValue ("LightYellow" &nbsp;)** |**RGBA (&nbsp;255, &nbsp;255, &nbsp;224, &nbsp;1 @ NO__T-5)** |![lightyellow](./media/function-colors/color-lightyellow.png) |
| **Color.Lime** |**ColorValue ("#00ff00" &nbsp;)**<br>**ColorValue («sitrus grønn» &nbsp;)** |**RGBA (&nbsp;0, &nbsp;255, &nbsp;0, &nbsp;1 @ NO__T-5)** |![lime](./media/function-colors/color-lime.png) |
| **Color.LimeGreen** |**ColorValue ("#32cd32" &nbsp;)**<br>**ColorValue ("LimeGreen" &nbsp;)** |**RGBA (&nbsp;50, &nbsp;205, &nbsp;50, &nbsp;1 @ NO__T-5)** |![limegreen](./media/function-colors/color-limegreen.png) |
| **Color.Linen** |**ColorValue ("#faf0e6" &nbsp;)**<br>**ColorValue ("linen" &nbsp;)** |**RGBA (&nbsp;250, &nbsp;240, &nbsp;230, &nbsp;1 @ NO__T-5)** |![linen](./media/function-colors/color-linen.png) |
| **Color.Magenta** |**ColorValue ("#ff00ff" &nbsp;)**<br>**ColorValue («magenta» &nbsp;)** |**RGBA (&nbsp;255, &nbsp;0, &nbsp;255, &nbsp;1 @ NO__T-5)** |![magenta](./media/function-colors/color-magenta.png) |
| **Color.Maroon** |**ColorValue ("#800000" &nbsp;)**<br>**ColorValue ("MAROON" &nbsp;)** |**RGBA (&nbsp;128, &nbsp;0, &nbsp;0, &nbsp;1 @ NO__T-5)** |![maroon](./media/function-colors/color-maroon.png) |
| **Color.MediumAquamarine** |**ColorValue ("#66cdaa" &nbsp;)**<br>**ColorValue ("MediumAquamarine" &nbsp;)** |**RGBA (&nbsp;102, &nbsp;205, &nbsp;170, &nbsp;1 @ NO__T-5)** |![mediumaquamarine](./media/function-colors/color-mediumaquamarine.png) |
| **Color.MediumBlue** |**ColorValue ("#0000cd" &nbsp;)**<br>**ColorValue ("mediumblue" &nbsp;)** |**RGBA (&nbsp;0, &nbsp;0, &nbsp;205, &nbsp;1 @ NO__T-5)** |![mediumblue](./media/function-colors/color-mediumblue.png) |
| **Color.MediumOrchid** |**ColorValue ("#ba55d3" &nbsp;)**<br>**ColorValue ("MediumOrchid" &nbsp;)** |**RGBA (&nbsp;186, &nbsp;85, &nbsp;211, &nbsp;1 @ NO__T-5)** |![mediumorchid](./media/function-colors/color-mediumorchid.png) |
| **Color.MediumPurple** |**ColorValue ("#9370db" &nbsp;)**<br>**ColorValue ("MEDIUMPURPLE" &nbsp;)** |**RGBA (&nbsp;147, &nbsp;112, &nbsp;219, &nbsp;1 @ NO__T-5)** |![mediumpurple](./media/function-colors/color-mediumpurple.png) |
| **Color.MediumSeaGreen** |**ColorValue ("#3cb371" &nbsp;)**<br>**ColorValue ("MediumSeaGreen" &nbsp;)** |**RGBA (&nbsp;60, &nbsp;179, &nbsp;113, &nbsp;1 @ NO__T-5)** |![mediumseagreen](./media/function-colors/color-mediumseagreen.png) |
| **Color.MediumSlateBlue** |**ColorValue ("#7b68ee" &nbsp;)**<br>**ColorValue ("mediumslateblue" &nbsp;)** |**RGBA (&nbsp;123, &nbsp;104, &nbsp;238, &nbsp;1 @ NO__T-5)** |![mediumslateblue](./media/function-colors/color-mediumslateblue.png) |
| **Color.MediumSpringGreen** |**ColorValue ("#00fa9a" &nbsp;)**<br>**ColorValue ("MediumSpringGreen" &nbsp;)** |**RGBA (&nbsp;0, &nbsp;250, &nbsp;154, &nbsp;1 @ NO__T-5)** |![mediumspringgreen](./media/function-colors/color-mediumspringgreen.png) |
| **Color.MediumTurquoise** |**ColorValue ("#48d1cc" &nbsp;)**<br>**ColorValue ("MEDIUMTURQUOISE" &nbsp;)** |**RGBA (&nbsp;72, &nbsp;209, &nbsp;204, &nbsp;1 @ NO__T-5)** |![mediumturquoise](./media/function-colors/color-mediumturquoise.png) |
| **Color.MediumVioletRed** |**ColorValue ("#c71585" &nbsp;)**<br>**ColorValue ("MediumVioletRed" &nbsp;)** |**RGBA (&nbsp;199, &nbsp;21, &nbsp;133, &nbsp;1 @ NO__T-5)** |![mediumvioletred](./media/function-colors/color-mediumvioletred.png) |
| **Color.MidnightBlue** |**ColorValue ("#191970" &nbsp;)**<br>**ColorValue ("midnightblue" &nbsp;)** |**RGBA (&nbsp;25, &nbsp;25, &nbsp;112, &nbsp;1 @ NO__T-5)** |![midnightblue](./media/function-colors/color-midnightblue.png) |
| **Color.MintCream** |**ColorValue ("#f5fffa" &nbsp;)**<br>**ColorValue ("MintCream" &nbsp;)** |**RGBA (&nbsp;245, &nbsp;255, &nbsp;250, &nbsp;1 @ NO__T-5)** |![mintcream](./media/function-colors/color-mintcream.png) |
| **Color.MistyRose** |**ColorValue ("#ffe4e1" &nbsp;)**<br>**ColorValue ("MISTYROSE" &nbsp;)** |**RGBA (&nbsp;255, &nbsp;228, &nbsp;225, &nbsp;1 @ NO__T-5)** |![mistyrose](./media/function-colors/color-mistyrose.png) |
| **Color.Moccasin** |**ColorValue ("#ffe4b5" &nbsp;)**<br>**ColorValue ("lys gulbrun" &nbsp;)** |**RGBA (&nbsp;255, &nbsp;228, &nbsp;181, &nbsp;1 @ NO__T-5)** |![moccasin](./media/function-colors/color-moccasin.png) |
| **Color.NavajoWhite** |**ColorValue ("#ffdead" &nbsp;)**<br>**ColorValue ("navajowhite" &nbsp;)** |**RGBA (&nbsp;255, &nbsp;222, &nbsp;173, &nbsp;1 @ NO__T-5)** |![navajowhite](./media/function-colors/color-navajowhite.png) |
| **Color.Navy** |**ColorValue ("#000080" &nbsp;)**<br>**ColorValue ("Navy" &nbsp;)** |**RGBA (&nbsp;0, &nbsp;0, &nbsp;128, &nbsp;1 @ NO__T-5)** |![navy](./media/function-colors/color-navy.png) |
| **Color.OldLace** |**ColorValue ("#fdf5e6" &nbsp;)**<br>**ColorValue ("OLDLACE" &nbsp;)** |**RGBA (&nbsp;253, &nbsp;245, &nbsp;230, &nbsp;1 @ NO__T-5)** |![oldlace](./media/function-colors/color-oldlace.png) |
| **Color.Olive** |**ColorValue ("#808000" &nbsp;)**<br>**ColorValue («olivengrønn» &nbsp;)** |**RGBA (&nbsp;128, &nbsp;128, &nbsp;0, &nbsp;1 @ NO__T-5)** |![olive](./media/function-colors/color-olive.png) |
| **Color.OliveDrab** |**ColorValue ("#6b8e23" &nbsp;)**<br>**ColorValue ("olivedrab" &nbsp;)** |**RGBA (&nbsp;107, &nbsp;142, &nbsp;35, &nbsp;1 @ NO__T-5)** |![olivedrab](./media/function-colors/color-olivedrab.png) |
| **Color.Orange** |**ColorValue ("#ffa500" &nbsp;)**<br>**ColorValue ("appelsin" &nbsp;)** |**RGBA (&nbsp;255, &nbsp;165, &nbsp;0, &nbsp;1 @ NO__T-5)** |![orange](./media/function-colors/color-orange.png) |
| **Color.OrangeRed** |**ColorValue ("#ff4500" &nbsp;)**<br>**ColorValue ("ORANGERED" &nbsp;)** |**RGBA (&nbsp;255, &nbsp;69, &nbsp;0, &nbsp;1 @ NO__T-5)** |![orangered](./media/function-colors/color-orangered.png) |
| **Color.Orchid** |**ColorValue ("#da70d6" &nbsp;)**<br>**ColorValue ("orkide" &nbsp;)** |**RGBA (&nbsp;218, &nbsp;112, &nbsp;214, &nbsp;1 @ NO__T-5)** |![orchid](./media/function-colors/color-orchid.png) |
| **Color.PaleGoldenRod** |**ColorValue ("#eee8aa" &nbsp;)**<br>**ColorValue ("palegoldenrod" &nbsp;)** |**RGBA (&nbsp;238, &nbsp;232, &nbsp;170, &nbsp;1 @ NO__T-5)** |![palegoldenrod](./media/function-colors/color-palegoldenrod.png) |
| **Color.PaleGreen** |**ColorValue ("#98fb98" &nbsp;)**<br>**ColorValue ("PaleGreen" &nbsp;)** |**RGBA (&nbsp;152, &nbsp;251, &nbsp;152, &nbsp;1 @ NO__T-5)** |![palegreen](./media/function-colors/color-palegreen.png) |
| **Color.PaleTurquoise** |**ColorValue ("#afeeee" &nbsp;)**<br>**ColorValue ("PALETURQUOISE" &nbsp;)** |**RGBA (&nbsp;175, &nbsp;238, &nbsp;238, &nbsp;1 @ NO__T-5)** |![paleturquoise](./media/function-colors/color-paleturquoise.png) |
| **Color.PaleVioletRed** |**ColorValue ("#db7093" &nbsp;)**<br>**ColorValue ("PaleVioletRed" &nbsp;)** |**RGBA (&nbsp;219, &nbsp;112, &nbsp;147, &nbsp;1 @ NO__T-5)** |![palevioletred](./media/function-colors/color-palevioletred.png) |
| **Color.PapayaWhip** |**ColorValue ("#ffefd5" &nbsp;)**<br>**ColorValue ("papayawhip" &nbsp;)** |**RGBA (&nbsp;255, &nbsp;239, &nbsp;213, &nbsp;1 @ NO__T-5)** |![papayawhip](./media/function-colors/color-papayawhip.png) |
| **Color.PeachPuff** |**ColorValue ("#ffdab9" &nbsp;)**<br>**ColorValue ("PeachPuff" &nbsp;)** |**RGBA (&nbsp;255, &nbsp;218, &nbsp;185, &nbsp;1 @ NO__T-5)** |![peachpuff](./media/function-colors/color-peachpuff.png) |
| **Color.Peru** |**ColorValue ("#cd853f" &nbsp;)**<br>**ColorValue («PERU» &nbsp;)** |**RGBA (&nbsp;205, &nbsp;133, &nbsp;63, &nbsp;1 @ NO__T-5)** |![peru](./media/function-colors/color-peru.png) |
| **Color.Pink** |**ColorValue ("#ffc0cb" &nbsp;)**<br>**ColorValue («rosa» &nbsp;)** |**RGBA (&nbsp;255, &nbsp;192, &nbsp;203, &nbsp;1 @ NO__T-5)** |![pink](./media/function-colors/color-pink.png) |
| **Color.Plum** |**ColorValue ("#dda0dd" &nbsp;)**<br>**ColorValue ("Plum" &nbsp;)** |**RGBA (&nbsp;221, &nbsp;160, &nbsp;221, &nbsp;1 @ NO__T-5)** |![plum](./media/function-colors/color-plum.png) |
| **Color.PowderBlue** |**ColorValue ("#b0e0e6" &nbsp;)**<br>**ColorValue ("PowderBlue" &nbsp;)** |**RGBA (&nbsp;176, &nbsp;224, &nbsp;230, &nbsp;1 @ NO__T-5)** |![powderblue](./media/function-colors/color-powderblue.png) |
| **Color.Purple** |**ColorValue ("#800080" &nbsp;)**<br>**ColorValue («PURPUR» &nbsp;)** |**RGBA (&nbsp;128, &nbsp;0, &nbsp;128, &nbsp;1 @ NO__T-5)** |![purple](./media/function-colors/color-purple.png) |
| **Color.Red** |**ColorValue ("#ff0000" &nbsp;)**<br>**ColorValue («rød» &nbsp;)** |**RGBA (&nbsp;255, &nbsp;0, &nbsp;0, &nbsp;1 @ NO__T-5)** |![red](./media/function-colors/color-red.png) |
| **Color.RosyBrown** |**ColorValue ("#bc8f8f" &nbsp;)**<br>**ColorValue ("rosybrown" &nbsp;)** |**RGBA (&nbsp;188, &nbsp;143, &nbsp;143, &nbsp;1 @ NO__T-5)** |![rosybrown](./media/function-colors/color-rosybrown.png) |
| **Color.RoyalBlue** |**ColorValue ("#4169e1" &nbsp;)**<br>**ColorValue ("RoyalBlue" &nbsp;)** |**RGBA (&nbsp;65, &nbsp;105, &nbsp;225, &nbsp;1 @ NO__T-5)** |![royalblue](./media/function-colors/color-royalblue.png) |
| **Color.SaddleBrown** |**ColorValue ("#8b4513" &nbsp;)**<br>**ColorValue ("SADDLEBROWN" &nbsp;)** |**RGBA (&nbsp;139, &nbsp;69, &nbsp;19, &nbsp;1 @ NO__T-5)** |![saddlebrown](./media/function-colors/color-saddlebrown.png) |
| **Color.Salmon** |**ColorValue ("#fa8072" &nbsp;)**<br>**ColorValue ("Lakserød" &nbsp;)** |**RGBA (&nbsp;250, &nbsp;128, &nbsp;114, &nbsp;1 @ NO__T-5)** |![salmon](./media/function-colors/color-salmon.png) |
| **Color.SandyBrown** |**ColorValue ("#f4a460" &nbsp;)**<br>**ColorValue ("sandybrown" &nbsp;)** |**RGBA (&nbsp;244, &nbsp;164, &nbsp;96, &nbsp;1 @ NO__T-5)** |![sandybrown](./media/function-colors/color-sandybrown.png) |
| **Color.SeaGreen** |**ColorValue ("#2e8b57" &nbsp;)**<br>**ColorValue ("SeaGreen" &nbsp;)** |**RGBA (&nbsp;46, &nbsp;139, &nbsp;87, &nbsp;1 @ NO__T-5)** |![seagreen](./media/function-colors/color-seagreen.png) |
| **Color.SeaShell** |**ColorValue ("#fff5ee" &nbsp;)**<br>**ColorValue ("SEASHELL" &nbsp;)** |**RGBA (&nbsp;255, &nbsp;245, &nbsp;238, &nbsp;1 @ NO__T-5)** |![seashell](./media/function-colors/color-seashell.png) |
| **Color.Sienna** |**ColorValue ("#a0522d" &nbsp;)**<br>**ColorValue ("Sienna" &nbsp;)** |**RGBA (&nbsp;160, &nbsp;82, &nbsp;45, &nbsp;1 @ NO__T-5)** |![sienna](./media/function-colors/color-sienna.png) |
| **Color.Silver** |**ColorValue ("#c0c0c0" &nbsp;)**<br>**ColorValue («sølv» &nbsp;)** |**RGBA (&nbsp;192, &nbsp;192, &nbsp;192, &nbsp;1 @ NO__T-5)** |![silver](./media/function-colors/color-silver.png) |
| **Color.SkyBlue** |**ColorValue ("#87ceeb" &nbsp;)**<br>**ColorValue ("SkyBlue" &nbsp;)** |**RGBA (&nbsp;135, &nbsp;206, &nbsp;235, &nbsp;1 @ NO__T-5)** |![skyblue](./media/function-colors/color-skyblue.png) |
| **Color.SlateBlue** |**ColorValue ("#6a5acd" &nbsp;)**<br>**ColorValue ("SLATEBLUE" &nbsp;)** |**RGBA (&nbsp;106, &nbsp;90, &nbsp;205, &nbsp;1 @ NO__T-5)** |![slateblue](./media/function-colors/color-slateblue.png) |
| **Color.SlateGray** |**ColorValue ("#708090" &nbsp;)**<br>**ColorValue ("SlateGray" &nbsp;)** |**RGBA (&nbsp;112, &nbsp;128, &nbsp;144, &nbsp;1 @ NO__T-5)** |![slategray](./media/function-colors/color-slategray.png) |
| **Color.SlateGrey** |**ColorValue ("#708090" &nbsp;)**<br>**ColorValue ("slategrey" &nbsp;)** |**RGBA (&nbsp;112, &nbsp;128, &nbsp;144, &nbsp;1 @ NO__T-5)** |![slategrey](./media/function-colors/color-slategrey.png) |
| **Color.Snow** |**ColorValue ("#fffafa" &nbsp;)**<br>**ColorValue («snø» &nbsp;)** |**RGBA (&nbsp;255, &nbsp;250, &nbsp;250, &nbsp;1 @ NO__T-5)** |![snow](./media/function-colors/color-snow.png) |
| **Color.SpringGreen** |**ColorValue ("#00ff7f" &nbsp;)**<br>**ColorValue ("SPRINGGREEN" &nbsp;)** |**RGBA (&nbsp;0, &nbsp;255, &nbsp;127, &nbsp;1 @ NO__T-5)** |![springgreen](./media/function-colors/color-springgreen.png) |
| **Color.SteelBlue** |**ColorValue ("#4682b4" &nbsp;)**<br>**ColorValue ("SteelBlue" &nbsp;)** |**RGBA (&nbsp;70, &nbsp;130, &nbsp;180, &nbsp;1 @ NO__T-5)** |![steelblue](./media/function-colors/color-steelblue.png) |
| **Color.Tan** |**ColorValue ("#d2b48c" &nbsp;)**<br>**ColorValue («Tan» &nbsp;)** |**RGBA (&nbsp;210, &nbsp;180, &nbsp;140, &nbsp;1 @ NO__T-5)** |![tan](./media/function-colors/color-tan.png) |
| **Color.Teal** |**ColorValue ("#008080" &nbsp;)**<br>**ColorValue («Blågrønn» &nbsp;)** |**RGBA (&nbsp;0, &nbsp;128, &nbsp;128, &nbsp;1 @ NO__T-5)** |![teal](./media/function-colors/color-teal.png) |
| **Color.Thistle** |**ColorValue ("#d8bfd8" &nbsp;)**<br>**ColorValue ("THISTLE" &nbsp;)** |**RGBA (&nbsp;216, &nbsp;191, &nbsp;216, &nbsp;1 @ NO__T-5)** |![thistle](./media/function-colors/color-thistle.png) |
| **Color.Tomato** |**ColorValue ("#ff6347" &nbsp;)**<br>**ColorValue ("Tomato" &nbsp;)** |**RGBA (&nbsp;255, &nbsp;99, &nbsp;71, &nbsp;1 @ NO__T-5)** |![tomato](./media/function-colors/color-tomato.png) |
| **Farge. gjennomsiktig** |**ColorValue ("#00000000" &nbsp;)**<br>**ColorValue ("gjennomsiktig" &nbsp;)** |**RGBA (&nbsp;0, &nbsp;0, &nbsp;0, @NO__T – 40 @ NO__T-5)** |![sømløs](./media/function-colors/color-transparent.png) |
| **Color.Turquoise** |**ColorValue ("#40e0d0" &nbsp;)**<br>**ColorValue («turkis» &nbsp;)** |**RGBA (&nbsp;64, &nbsp;224, &nbsp;208, &nbsp;1 @ NO__T-5)** |![turquoise](./media/function-colors/color-turquoise.png) |
| **Color.Violet** |**ColorValue ("#ee82ee" &nbsp;)**<br>**ColorValue («fiolett» &nbsp;)** |**RGBA (&nbsp;238, &nbsp;130, &nbsp;238, &nbsp;1 @ NO__T-5)** |![violet](./media/function-colors/color-violet.png) |
| **Color.Wheat** |**ColorValue ("#f5deb3" &nbsp;)**<br>**ColorValue ("varm SIENNA" &nbsp;)** |**RGBA (&nbsp;245, &nbsp;222, &nbsp;179, &nbsp;1 @ NO__T-5)** |![wheat](./media/function-colors/color-wheat.png) |
| **Color.White** |**ColorValue ("#ffffff" &nbsp;)**<br>**ColorValue («hvit» &nbsp;)** |**RGBA (&nbsp;255, &nbsp;255, &nbsp;255, &nbsp;1 @ NO__T-5)** |![white](./media/function-colors/color-white.png) |
| **Color.WhiteSmoke** |**ColorValue ("#f5f5f5" &nbsp;)**<br>**ColorValue ("WhiteSmoke" &nbsp;)** |**RGBA (&nbsp;245, &nbsp;245, &nbsp;245, &nbsp;1 @ NO__T-5)** |![whitesmoke](./media/function-colors/color-whitesmoke.png) |
| **Color.Yellow** |**ColorValue ("#ffff00" &nbsp;)**<br>**ColorValue («gul» &nbsp;)** |**RGBA (&nbsp;255, &nbsp;255, &nbsp;0, &nbsp;1 @ NO__T-5)** |![yellow](./media/function-colors/color-yellow.png) |
| **Color.YellowGreen** |**ColorValue ("#9acd32" &nbsp;)**<br>**ColorValue ("YELLOWGREEN" &nbsp;)** |**RGBA (&nbsp;154, &nbsp;205, &nbsp;50, &nbsp;1 @ NO__T-5)** |![yellowgreen](./media/function-colors/color-yellowgreen.png) |
