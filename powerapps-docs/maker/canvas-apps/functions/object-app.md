---
title: App-objektet | Microsoft Docs
description: Referanseinformasjon, inkludert syntaks og eksempler på App-objektet i PowerApps
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 05/29/2019
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 232accd1050fb84816e86ea95069b8c8778f6586
ms.sourcegitcommit: 562c7ed5fbb116be1cbb0f45e3f6e75e3e4cf011
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 05/31/2019
ms.locfileid: "66451614"
ms.PowerAppsDecimalTransform: true
---
# <a name="app-object-in-powerapps"></a>App-objekt i PowerApps

Gir informasjon om den kjørende appen og kontroll over appens virkemåte.

## <a name="description"></a>Beskrivelse

Som en kontroll, den **App** objektet inneholder egenskaper som identifiserer hvilken skjerm vises, og som ber brukeren om å lagre endringene slik at de ikke er brutt. Alle apper har en **App** objektet.

Du kan skrive formler for noen egenskaper for den **App** objektet. På toppen av den **trevisning** rute, velger du **App** objekt som du ville alle andre kontroll eller skjerm. Vis og Rediger ett av objektets egenskaper ved å velge den i rullegardinlisten til venstre for formellinjen.

> [!div class="mx-imgBorder"]
> ![App-objektet i treet Vis-ruten](media/object-app/appobject.png)

## <a name="activescreen-property"></a>ActiveScreen egenskapen

Den **ActiveScreen** egenskapen identifiserer skjermen som vises.

Denne egenskapen returnerer et skjermobjekt som du kan bruke til å referere til egenskaper til skjermen, eller sammenligne en annen skjerm for å bestemme hvilken skjerm vises. Du kan også bruke uttrykket **App.ActiveScreen.Name** til å hente navnet på skjermen som vises.

Bruk den **[tilbake](function-navigate.md)** eller **[Navigate](function-navigate.md)** funksjonen for å endre skjermen som vises.

## <a name="onstart-property"></a>OnStart egenskapen

Den **OnStart** egenskapen som kjøres når brukeren starter appen. Applagere bruker ofte denne egenskapen for å utføre disse oppgavene:

- Hente og hurtigbufring av data til samlinger ved å bruke den **[samle inn](function-clear-collect-clearcollect.md)** funksjonen.
- Konfigurer globale variabler ved å bruke den **[angi](function-set.md)** funksjonen.
- Naviger til en innledende skjermen ved hjelp av den **[Navigate](function-navigate.md)** funksjonen.

Denne formelen evalueres før den første skjermen vises. Ingen skjermen er lastet inn, slik at du ikke kan angi kontekstvariabler med den **[UpdateContext](function-updatecontext.md)** funksjonen. Du kan imidlertid overføre kontekstvariablene med den **Navigate** funksjonen.

Når du har endret den **OnStart** -egenskapen, teste den ved å hvile over den **App** objektet i den **trevisning** ruten, å velge ellipsen (...) som vises, og deretter velge **Kjøre OnStart**. I motsetning til når appen er lastet for første gang, angis eksisterende samlinger og variabler allerede. Starte med tom samlinger, kan du bruke den **[ClearCollect](function-clear-collect-clearcollect.md)** funksjonen i stedet for den **samle inn** funksjonen.

> [!div class="mx-imgBorder"]
> ![App-element hurtigmenyen for kjøre OnStart](media/object-app/appobject-runonstart.png)

## <a name="confirmexit-properties"></a>ConfirmExit egenskaper

Ingen vil mister ulagrede endringer. Bruk den **ConfirmExit** og **ConfirmExitMessage** egenskaper for å gi brukeren en advarsel før de lukker appen.

> [!NOTE]
> **ConfirmExit** virker ikke i apper som er innebygd i, for eksempel Power BI og SharePoint.

> [!NOTE]
> I øyeblikket, disse egenskapene kan referere til kontroller i bare den første skjermen hvis den **forsinket innlasting** forhåndsvisningsfunksjonen er aktivert (som det er som standard for nye apper). Hvis referanser blir gjort, PowerApps Studio viser ikke en feil, men den resulterende publiserte appen åpnes ikke i PowerApps Mobile eller en nettleser. Vi arbeider aktivt for å fjerne denne begrensningen. I mellomtiden kan du slå av **forsinket innlasting** i **filen** > **appinnstillinger** > **avanserte innstillinger**(under **forhåndsvisningsfunksjoner**).

### <a name="confirmexit"></a>ConfirmExit

**ConfirmExit** er en boolsk egenskap som, når *SANN*, åpnes en bekreftelsesdialogboks før appen lukkes. Denne egenskapen er som standard *USANN*, og det vises ingen dialogboks.

Bruk denne egenskapen til å vise en bekreftelsesdialogboks Hvis brukeren har gjort endringer, men ikke lagret dem. Bruke en formel som kan kontrollere variabler og kontrollegenskaper (for eksempel den **Unsaved** -egenskapen for den [ **redigeringsskjema** ](../controls/control-form-detail.md) kontroll).

Bekreftelsesdialogboksen vises i alle situasjoner der data kan gå tapt, som i disse eksemplene:

- Kjører den [ **Avslutt** ](function-exit.md) funksjonen.
- Hvis appen kjøres i en nettleser:
  - Lukke nettleseren eller nettleserfanen som appen kjører.
  - Å velge leserens tilbake-knappen.
- Hvis appen kjøres i PowerApps Mobile (iOS eller Android):
  - Kjører den [ **Start** ](function-param.md) funksjonen.<br>Den **Start** funksjonen utløser ikke dialogboksen i en nettleser fordi en annen kategori åpner slik at dataene ikke går tapt.
  - Sveipe for å bytte til en annen app i PowerApps Mobile.
  - Å velge på Tilbake-knappen på en Android-enhet.

Nøyaktig utseendet på bekreftelsesdialogboksen kan variere på tvers av enheter og versjoner av PowerApps.

Dialogboksen vises ikke i PowerApps Studio.

### <a name="confirmexitmessage"></a>ConfirmExitMessage

Som standard viser bekreftelsesdialogboksen en standardmelding, for eksempel **"Du kan har ulagrede endringer."** på brukerens språk.

Bruk **ConfirmExitMessage** til å gi en egendefinert melding i bekreftelsesdialogboksen. Hvis denne egenskapen er *tom*, brukes standardverdien. Egendefinerte meldinger er avkortet trenger for å passe i bekreftelsesdialogboksen, og bør meldingen til noen få linjer maksimalt.

I en nettleser, kanskje bekreftelsesdialogboksen vises med en standardmelding fra nettleseren.

### <a name="example"></a>Eksempel

1. Opprette en app som inneholder to skjemakontroller, **AccountForm** og **ContactForm**.

1. Angi den **App** objektets **ConfirmExit** egenskapen til dette uttrykket:

    ```powerapps-comma
    AccountForm.Unsaved Or ContactForm.Unsaved
    ```

    Denne dialogboksen vises hvis brukeren endrer data i begge formene og deretter prøver å lukke appen uten å lagre disse endringene.

    > [!div class="mx-imgBorder"]
    > ![Generisk bekreftelsesdialogboks](media/object-app/confirm-native.png)

1. Angi den **App** objektets **ConfirmExitMessage** egenskapen til denne formelen:

    ```powerapps-comma
    If( AccountsForm.Unsaved;
        "Accounts form has unsaved changes.";
        "Contacts form has unsaved changes."
    )
    ```

    Denne dialogboksen vises hvis brukeren endrer data i skjemaet kontoen, og deretter prøver å lukke appen uten å lagre disse endringene.

    > [!div class="mx-imgBorder"]
    > ![Skjema-spesifikke bekreftelsesdialogboks](media/object-app/confirm-native-custom.png)
