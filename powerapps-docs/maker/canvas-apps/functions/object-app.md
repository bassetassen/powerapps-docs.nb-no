---
title: App-objekt | Microsoft Docs
description: Referanse informasjon, inkludert syntaks og eksempler, for app-objektet i PowerApps
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 05/29/2019
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: b0ab20ce5e0700337bb059644c458a2665d20f1e
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/07/2019
ms.locfileid: "71983574"
ms.PowerAppsDecimalTransform: true
---
# <a name="app-object-in-powerapps"></a>App-objekt i PowerApps

Gir informasjon om appen som kjører, og kontroll over appens virke måte.

## <a name="description"></a>Beskrivelse

På samme måte som en kontroll, inneholder **app** -objektet egenskaper som identifiserer hvilken skjerm som vises, og som ber brukeren om å lagre endringer slik at de ikke går tapt. Hver app har et **app** -objekt.

Du kan skrive formler for noen egenskaper for **app** -objektet. Velg **app** -objektet øverst i **tre visnings** ruten, som en hvilken som helst annen kontroll eller skjerm. Vis og rediger et av objektets egenskaper ved å velge det i rulle gardin listen til venstre for formel linjen.

> [!div class="mx-imgBorder"]
> ![The app-objekt i tre visnings ruten @ no__t-1

## <a name="activescreen-property"></a>ActiveScreen-egenskapen

Egenskapen **ActiveScreen** identifiserer skjermen som vises.

Denne egenskapen returnerer et skjerm objekt, som du kan bruke til å referere til egenskapene til skjermen eller sammenligne med en annen skjerm for å bestemme hvilken skjerm som vises. Du kan også bruke Expression- **app.ActiveScreen.name** til å hente navnet på skjermen som vises.

Bruk **[tilbake](function-navigate.md)** -eller **[Naviger](function-navigate.md)** -funksjonen til å endre skjermen som vises.

## <a name="onstart-property"></a>OnStart-egenskapen

Egenskapen **OnStart** kjører når brukeren starter appen. App-produsenter bruker ofte denne egenskapen til å utføre disse oppgavene:

- Hent og bufre data til samlinger ved hjelp av **[Collect](function-clear-collect-clearcollect.md)** -funksjonen.
- Konfigurer globale variabler ved hjelp av **[Set](function-set.md)** -funksjonen.
- Gå til en start skjerm ved hjelp av **[Naviger](function-navigate.md)** -funksjonen.

Denne formelen evalueres før den første skjermen vises. Ingen skjerm bilder er lastet inn, så du kan ikke angi kontekst variabler med **[UpdateContext](function-updatecontext.md)** -funksjonen. Du kan imidlertid sende kontekst variabler med **Naviger** -funksjonen.

Når du endrer egenskapen **OnStart** , kan du teste den ved å holde pekeren over **app** -objektet i **tre visnings** ruten, velge ellipsen (...) som vises, og deretter velge **Kjør OnStart**. I motsetning til når appen lastes inn for første gang, vil eksisterende samlinger og variabler allerede være angitt. Hvis du vil starte med tomme samlinger, kan du bruke **[ClearCollect](function-clear-collect-clearcollect.md)** -funksjonen i stedet for **Collect** -funksjonen.

> [!div class="mx-imgBorder"]
> hurtig menyen ![App for kjøring OnStart @ no__t-1

## <a name="confirmexit-properties"></a>Egenskaper for ConfirmExit

Ingen ønsker å miste ulagrede endringer. Bruk **ConfirmExit** -og **ConfirmExitMessage** -egenskapene til å advare brukeren før de avslutter appen.

> [!NOTE]
> **ConfirmExit** fungerer ikke i apper som er innebygd i, for eksempel Power bi og SharePoint.

> [!NOTE]
> Nå kan disse egenskapene referere til kontroller på bare den første skjermen hvis forhånds visnings funksjonen for **Forsinket innlasting** er aktivert (som den er som standard for nye apper). Hvis det utføres referanser, PowerApps Studio ikke en feil melding, men den endelige, publiserte appen åpnes ikke i PowerApps Mobile eller en nett leser. Vi jobber aktivt med å løfte denne begrensningen. I mellom tiden kan du slå av **forsinket belastning** i **fil**@no__t – 2**App-innstillinger** > **Avanserte innstillinger** (under **forhånds visnings funksjoner**).

### <a name="confirmexit"></a>ConfirmExit

**ConfirmExit** er en boolsk egenskap som, når *sann*, åpner en bekreftelses dialog boks før appen lukkes. Som standard er denne egenskapen *Usann*, og ingen dialog boks vises.

Bruk denne egenskapen til å vise en bekreftelses dialog boks hvis brukeren har gjort endringer, men ikke lagret dem. Bruk en formel som kan kontrollere variabler og kontroll egenskaper (for eksempel egenskapen **ulagre** for [**redigerings skjema**](../controls/control-form-detail.md) -kontrollen).

Bekreftelses dialog boksen vises i alle situasjoner der data kan gå tapt, som i disse eksemplene:

- Kjører [**Avslutt**](function-exit.md) -funksjonen.
- Hvis appen kjører i en nett leser:
  - Lukke nett leseren eller nett leser fanen der appen kjører.
  - Å velge tilbake-knappen i nett leseren.
- Hvis appen kjører i PowerApps Mobile (iOS eller Android):
  - Kjører [**Start**](function-param.md) funksjonen.<br>**Start** funksjonen utløser ikke dialog boksen i en nett leser fordi en annen fane åpnes slik at data ikke går tapt.
  - Dra for å bytte til en annen app i PowerApps Mobile.
  - Velge tilbakeknappen på en Android-enhet.

Det nøyaktige utseendet på bekreftelses dialog boksen kan variere på tvers av enheter og versjoner av PowerApps.

Bekreftelses dialog boksen vises ikke i PowerApps Studio.

### <a name="confirmexitmessage"></a>ConfirmExitMessage

Som standard viser dialog boksen bekreftelse en generell melding, for eksempel **«du kan ha ulagrede endringer.»** på brukerens språk.

Bruk **ConfirmExitMessage** til å angi en egen definert melding i bekreftelses dialog boksen. Hvis denne egenskapen er *tom*, brukes standard verdien. Egen definerte meldinger avkortes som nødvendig for å passe i bekreftelses dialog boksen, så du kan holde meldingen til et par linjer.

I en nett leser kan bekreftelses dialog boksen vises med en generisk melding fra nett leseren.

### <a name="example"></a>Eksempel

1. Opprett en app som inneholder to skjema kontroller, **AccountForm** og **ContactForm**.

1. Angi **app** -objektets **ConfirmExit** -egenskap til dette uttrykket:

    ```powerapps-comma
    AccountForm.Unsaved Or ContactForm.Unsaved
    ```

    Denne dialog boksen vises hvis brukeren endrer data i et av skjemaene, og deretter prøver å lukke appen uten å lagre disse endringene.

    > [!div class="mx-imgBorder"]
    > dialog boks for bekreftelse av ![Generic @ no__t-1

1. Angi **app** -objektets **ConfirmExitMessage** -egenskap til denne formelen:

    ```powerapps-comma
    If( AccountsForm.Unsaved;
        "Accounts form has unsaved changes.";
        "Contacts form has unsaved changes."
    )
    ```

    Denne dialog boksen vises hvis brukeren endrer data i konto skjemaet, og deretter prøver å lukke appen uten å lagre disse endringene.

    > [!div class="mx-imgBorder"]
    > @no__t – 0Form-spesifikk bekreftelses dialog boks @ no__t-1
