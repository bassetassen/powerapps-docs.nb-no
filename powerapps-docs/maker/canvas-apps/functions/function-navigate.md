---
title: Funksjonene Back og Navigate | Microsoft Docs
description: Referanseinformasjon for funksjonene Back og Navigate i PowerApps, inkludert syntaks og eksempler
documentationcenter: na
author: gregli-msft
manager: kvivek
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: reference
ms.component: canvas
ms.date: 11/08/2015
ms.author: gregli
ms.openlocfilehash: e00ee9b3a58bf3255b9f581f405381af05aa07f9
ms.sourcegitcommit: 6d9fe9967841e381b108a7fb53c9057e295336ea
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 07/10/2018
ms.locfileid: "37948576"
---
# <a name="back-and-navigate-functions-in-powerapps"></a>Funksjonene Back og Navigate i PowerApps
Endre hvilken skjerm som vises.

## <a name="overview"></a>Oversikt
De fleste appene inneholder flere skjermer.  Bruk **Back**- og **Navigate**-funksjonene til å endre hvilken skjerm som vises. Du kan for eksempel angi **[OnSelect](../controls/properties-core.md)**-egenskapen til en knapp til en formel som inkluderer en **Navigate**-funksjon, hvis du ønsker å vise en annen skjerm når en bruker velger den knappen. I denne formelen kan du angi en visuell overgang, som **Nedtoning**, for å kontrollere hvordan en skjerm endres til en annen.  

**Back** og **Navigate** endrer bare hvilken skjerm som vises. Skjermer som ikke vises for øyeblikket fortsetter å operere i bakgrunnen. Du kan opprette formler og henvise til egenskaper for kontroller på en annen skjerm. En bruker kan for eksempel endre verdien for en glidebryter på en skjerm, navigere til en annen skjerm som bruker den verdien i en formel, og se hvordan de påvirker det som skjer på den nye skjermen.  Brukeren kan deretter navigere tilbake til den opprinnelige skjermen og se at glidebryteren har beholdt verdien.

[Kontekstvariabler](../working-with-variables.md#create-a-context-variable) beholdes også når en bruker navigerer mellom skjermer. Du kan bruke **Navigate** for å angi én eller flere kontekstvariabler for skjermen som formelen skal vise. Dette er den eneste måten du kan angi kontekstvariabler utenfor skjermen på. Du kan bruke denne fremgangsmåten for å sende parametre til en skjerm. Hvis du har brukt et annet programmeringsverktøy, er denne fremgangsmåten lik den for å sende parametre til prosedyrer.

## <a name="description"></a>Beskrivelse
### <a name="back"></a>Tilbake
**Back**-funksjonen viser skjermen som sist ble vist. Du trenger ikke å angi noen argumenter for denne funksjonen.

### <a name="navigate"></a>Navigate
Angi navnet på den første skjermen som skal vises i det første argumentet.  

 I det andre argumentet angir du hvordan den gamle skjermen endres til den nye:

| Overgangsargument | Beskrivelse |
| --- | --- |
| **ScreenTransition.Cover** |Den nye skjermen glir inn, og dekker den gjeldende skjermen. |
| **ScreenTransition.Fade** |Den gamle skjermen tones ned for å vise den nye skjermen. |
| **ScreenTransition.None** |Den gamle skjermen erstattes raskt med den nye skjermen. |
| **ScreenTransition.UnCover** |Den gamle skjermen glir ut av visningen, og avdekker den nye skjermen. |

Du kan bruke **Navigate** til å opprette eller oppdatere kontekstvariabler på den nye skjermen. Som et valgfritt tredje argument kan du sende en [post](../working-with-tables.md#records) som inneholder kontekstvariabelnavnet som et [kolonnenavn](../working-with-tables.md#columns) og den nye verdien for kontekstvariabelen.  Denne posten er den samme som posten du brukte med **[UpdateContext](function-updatecontext.md)**-funksjonen.

Angi **[OnHidden](../controls/control-screen.md)**-egenskapen til den forrige skjermen, **[OnVisible](../controls/control-screen.md)**-egenskapen til den nye skjermen, eller begge, for å foreta flere endringer i løpet av overgangen. **App.ActiveScreen**-egenskapen oppdateres for å gjenspeile endringen.

**Back** returnerer som regel **sann**, men returnerer **usann** hvis brukeren befinner seg på den første skjermen som vises, og det ikke finnes en tidligere skjerm.  **Navigate** returnerer som regel **sann**, men returnerer **usann** hvis det oppstår et problem med ett av argumentene.

Du kan bruke disse funksjonene bare i en [formel for virkemåte](../working-with-formulas-in-depth.md).

## <a name="syntax"></a>Syntaks
**Back**()

**Navigate**( *Screen*, *Transition* [, *UpdateContextRecord* ] )

* *Screen* – obligatorisk. Skjermen som skal vises.
* *Transition* – obligatorisk.  Den visuelle overgangen som skal brukes mellom gjeldende skjerm og den nye skjermen. Se listen over gyldige verdier for dette argumentet tidligere i dette emnet.
* *UpdateContextRecord* – valgfritt.  En post som inneholder navnet på minst én kolonne og en verdi for hver kolonne. Denne posten oppdaterer kontekstvariablene til den nye skjermen som om den ble sendt til **[UpdateContext](function-updatecontext.md)**-funksjonen.

## <a name="examples"></a>Eksempler

| Formel | Beskrivelse | Resultat |
| --- | --- | --- |
| **Navigate( Details, ScreenTransition.None )** |Viser **Details**-skjermen uten overgang eller endring i verdi for en kontekstvariabel. |**Detaljer**-skjermen vises raskt. |
| **Navigate( Details, ScreenTransition.Fade )** |Viser **Detaljer**-skjermen med en **Tone**-overgang.  Ingen verdier for en kontekstvariabel endres. |Den gjeldede skjermen tones ned for å vise **Details**-skjermen. |
| **Navigate( Details, ScreenTransition.Fade, {&nbsp;ID:&nbsp;12&nbsp;} )** |Viser **Details**-skjermen med en **Fade**-overgang, og oppdaterer verdien til kontekstvariabelen **ID** til **12**. |Den gjeldende skjermen tones ned for å vise **Details**-skjermen, og kontekstvariabelen **ID** på den skjermen som angis til **12**. |
| **Navigate( Details, ScreenTransition.Fade, {&nbsp;ID:&nbsp;12&nbsp;,&nbsp;Shade:&nbsp;Color.Red&nbsp;} )** |Viser **Detaljer**-skjermen med en **Tone**-overgang. Oppdaterer verdien til kontekstvariabelen **ID** til **12**, og oppdaterer verdien til kontekstvariabelen **Shade** til **Color.Red**. |Den gjeldede skjermen tones ned for å vise **Details**-skjermen. Kontekstvariabelen **ID** på **Detaljer**-skjermen angis til **12**, og kontekstvariabelen **Nyanse** angis til **Color.Red**. Hvis du angir **Fyll**-egenskapen til en kontroll på **Detaljer**-skjermen til **Nyanse**, vises denne kontrollen i rødt. |

### <a name="step-by-step"></a>Trinnvis
1. Gi standardskjermen navnet **DefaultScreen**, legg til en etikett, og angi **[Tekst](../controls/properties-core.md)**-egenskapen til etiketten slik at den viser **Standard**.
2. Legg til en skjerm, og kall den **AddlScreen**.
3. Legg til en etikett for **AddlScreen**, og angi **[Tekst](../controls/properties-core.md)**-egenskapen til etiketten slik at den viser **Addl**.
4. Legg til en knapp i **AddlScreen**, og angi knappens **[OnSelect](../controls/properties-core.md)**-egenskap til denne funksjonen:<br>**Navigate(DefaultScreen, ScreenTransition.Fade)**
5. Trykk på F5 fra **AddlScreen**, og velg deretter knappen.<br>**DefaultScreen** vises.

[Et annet eksempel](../add-screen-context-variables.md)

