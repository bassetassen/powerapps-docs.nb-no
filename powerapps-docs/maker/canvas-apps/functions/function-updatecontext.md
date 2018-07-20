---
title: UpdateContext-funksjonen | Microsoft Docs
description: Referanseinformasjon, inkludert syntaks og eksempler, for UpdateContext-funksjonen i PowerApps
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 11/08/2015
ms.author: gregli
ms.openlocfilehash: 0128c0b31e2941b59167a0515b993e9a5517d040
ms.sourcegitcommit: dfa0e1a7981814e15e6ca4720e2a5f930e859db1
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 07/13/2018
ms.locfileid: "39023072"
---
# <a name="updatecontext-function-in-powerapps"></a>UpdateContext-funksjonen i PowerApps
Oppretter eller oppdaterer[kontekstvariabler](../working-with-variables.md#create-a-context-variable) på den gjeldende skjermen.

## <a name="overview"></a>Oversikt
Bruk **UpdateContext**-funksjonen til å opprette en kontekstvariabel, som inneholder midlertidig informasjon, for eksempel hvor mange ganger brukeren har valgt en knapp eller resultatet av en dataoperasjon.

Kontekstvariablene er avgrenset til ett skjermbilde, noe som betyr at du ikke kan opprette en formel som refererer til en kontekstvariabel på et annet skjermbilde. Hvis du har brukt et annet programmeringsverktøy, kan du anse en kontekstvariabel som noe som ligner en lokal variabel.  Bruk [ **Set**-funksjonen](function-set.md) til å arbeide med globale variabler som er tilgjengelige i hele appen.  

PowerApps er basert på formler som automatisk beregnes på nytt når brukeren samhandler med en app.  Kontekstvariabler tilbyr ikke denne fordelen, og kan gjøre appen vanskeligere å opprette og forstå.  Før du bruker en kontekstvariabel, er det lurt å se gjennom [Å arbeide med variabler](../working-with-variables.md).

## <a name="description"></a>Beskrivelse
Hvis du vil opprette eller oppdatere en kontekstvariabel, kan du sende en enkelt [post](../working-with-tables.md#records) til **UpdateContext**-funksjonen. I hver post kan du angi navnet på en [kolonne](../working-with-tables.md#columns), som definerer eller tilsvarer navnet på variabelen og verdien du vil angi denne variabelen for.

* Hvis du angir navnet på en variabel som du tidligere har definert, angir **UpdateContext** verdien for variabelen til verdien du angir.
* Hvis du angir navnet på en variabel som ikke finnes ennå, oppretter **UpdateContext** en variabel med dette navnet, og setter verdien for denne variabelen til verdien du angir.
* Hvis du tidligere har definert en variabel men ikke angitt verdien i denne bestemte **UpdateContext**-formelen, forblir verdien den samme.

Kontekstvariabler opprettes implisitt ved hjelp av **UpdateContext**- eller [ **Navigate**-funksjonen](function-navigate.md).  Det kreves ingen eksplisitt deklarasjon.  Hvis du fjerner alle **UpdateContext**- og **Naviger**-referansene til en kontekstvariabel, vil denne kontekstvariabelen opphøre.  Angi variabelens verdi som resultatet av [**Blank**-funksjonen](function-isblank-isempty.md) for å fjerne variabelen.

Du kan se variablenes verdier, definisjoner og bruk ved hjelp av Variabler-visningen under Fil-menyen i redigeringsmiljøet.

Du refererer til en kontekstvariabel i en formel ved hjelp av variabelens kolonnenavn. **UpdateContext ({ShowLogo: true})** oppretter for eksempel en kontekstvariabel kalt **ShowLogo**, og setter verdien til **sann**. Du kan deretter bruke verdien i denne kontekstvariabelen med navnet **ShowLogo** i en formel.  Du kan skrive **ShowLogo** som formelen for **Synlig**-egenskapen for en bildekontroll, og vise eller skjule kontrollen basert på om verdien for kontekstvariabelen er **sann**eller **usann**.

I eksemplene senere i dette emnet ser du at kontekstvariabler kan inneholde flere typer informasjon, deriblant disse:

* en enkelt verdi
* en post
* en tabell
* en objektreferanse
* et resultat av en formel

En kontekstvariabel inneholder verdien til appen lukkes.  Hvis du definerer en kontekstvariabel og angir verdien på et bestemt skjermbilde, vil denne informasjonen forbli intakt selv om brukeren bytter til et annet skjermbilde.  Når appen lukkes, går verdien til kontekstvariabelen tapt, og den må opprettes på nytt når appen er lastet inn på nytt.  

Alle kontekstvariabler er begrenset til ett skjermbilde. Hvis du vil definere en kontekstvariabel på ett skjermbilde og endre denne variabelen fra et annet skjermbilde, må du opprette en formel som er basert på **[Navigate](function-navigate.md)**-funksjonen.  Eller bruk en global variabel.

**UpdateContext** har ingen returverdi, og du kan kun bruke den i en [formel for virkemåte](../working-with-formulas-in-depth.md).

## <a name="syntax"></a>Syntaks
**UpdateContext**( *UpdateRecord* )

* *UpdateRecord* – obligatorisk. En post som inneholder navnet på minst én kolonne og en verdi for denne kolonnen. En kontekstvariabel opprettes eller oppdateres for hver kolonne og verdi som du angir.

**UpdateContext**( { *ContextVariable1*: *Value1* [, *ContextVariable2*: *Value2* [, ... ] ] } )

* *ContextVariable1* – obligatorisk.  Navnet på en kontekstvariabel som skal opprettes eller oppdateres.
* *Value1* – obligatorisk.  Verdien som skal tilordnes kontekstvariabelen.
* *ContextVariable2*: *Value2*, ... – valgfritt. Ekstra kontekstvariabler å opprette eller oppdatere, og tilknyttede verdier.

## <a name="examples"></a>Eksempler

| Formel | Beskrivelse | Resultat |
| --- | --- | --- |
| **UpdateContext( {&nbsp;Counter:&nbsp;1&nbsp;} )** |Oppretter eller endrer kontekstvariabelen **Teller**, og angir verdien dens til **1**. |**Counter** har verdien **1**. Du kan referere til denne variabelen med navnet **Counter** i en formel. |
| **UpdateContext( {&nbsp;Counter:&nbsp;2&nbsp;} )** |Angir verdien for kontekstvariabelen **Counter** fra det forrige eksemplet som **2**. |**Counter** har verdien **2**. |
| **UpdateContext( {&nbsp;Name:&nbsp;"Lily",&nbsp;Score:&nbsp;10&nbsp;} )** |Oppretter eller endrer kontekstvariablene **Name** og **Score**, angir verdiene til henholdsvis **Lily** og **10**. |**Name** har verdien **Lily**, og **Score** har verdien **10**. |
| **UpdateContext( {&nbsp;Person:&nbsp;{&nbsp;Name:&nbsp;"Milton", Address:&nbsp;"1&nbsp;Main&nbsp;St"&nbsp;}&nbsp;} )** |Oppretter eller endrer kontekstvariabelen **Person**, og angir verdien dens som en post. Posten inneholder to kolonner, kalt **Navn** og **Adresse**. Verdien til **Navn**-kolonnen er **Milton**, og verdien til **Adresse**-kolonnen er **1 Main St**. |**Person** har posten **{&nbsp;Name:&nbsp;"Milton", Address:&nbsp;"1&nbsp;Main&nbsp;St"&nbsp;}&nbsp;}** som verdi.<br><br>Du kan referere til denne posten som helhet med navnet **Person** eller referer til en individuell kolonne for denne posten med **Person.Name** eller **Person.Address**. |
| **UpdateContext( {&nbsp;Person: Patch(&nbsp;Person,&nbsp;{Address:&nbsp;"2&nbsp;Main&nbsp;St"&nbsp;}&nbsp;) }&nbsp;)** |Fungerer med **[Patch](function-patch.md)**-funksjonen for å oppdatere kontekstvariabelen **Person**, ved å angi verdien til **Adresse**-kolonnen som **2 Main St**. |**Person** har nå posten **{&nbsp;Name:&nbsp;"Milton", Address:&nbsp;"2&nbsp;Main&nbsp;St"&nbsp;}&nbsp;}** som verdi. |

### <a name="step-by-step-example"></a>Trinnvis veiledning – eksempel
1. Gi standardskjermbildet navnet **Kilde**, legg til et annet skjermbilde, og gi det navnet **Mål**.
2. Legg til to knapper på **Kilde**-skjermbildet, og angi  **[Tekst](../controls/properties-core.md)**-egenskapene slik at den ene er konfigurert for **engelsk** og den andre for **spansk**.
3. Angi **[OnSelect](../controls/properties-core.md)**-egenskapen for **Engelsk**-knappen til dette uttrykket:<br>**Navigate(Target, ScreenTransition.Fade, {Language:"English"})**
4. Angi **[OnSelect](../controls/properties-core.md)**-egenskapen for **Spansk**-knappen til dette uttrykket:<br>**Navigate(Target, ScreenTransition.Fade, {Language:"Spanish"})**
5. På **Mål**-skjermbildet legger du til en etikett, og angir **[Tekst](../controls/properties-core.md)**-egenskapen til dette uttrykket:<br>**If(Language="English", "Hello!", "Hola!")**
6. Velg **Figurer** på **Mål**-skjermbildet på **Sett inn**-fanen, og velg deretter Tilbake-pilen.
7. Angi Tilbake-pilens **[OnSelect](../controls/properties-core.md)**-egenskap til denne formelen:<br>**Navigate(Source, ScreenTransition.Fade)**
8. Trykk på F5 i **Kilde**-skjermbildet, og velg deretter knappen for begge språk.

    Etiketten vises på språket som tilsvarer knappen du har valgt på **Mål**-skjermbildet.
9. Velg Tilbake-pil for å gå tilbake til **Kilde**-skjermbildet, og velg deretter knappen for det andre språket.

    Etiketten vises på språket som tilsvarer knappen du har valgt på **Mål**-skjermbildet.
10. Trykk på ESC for å gå tilbake til standardarbeidsområdet.

[Et annet eksempel](../add-screen-context-variables.md)

