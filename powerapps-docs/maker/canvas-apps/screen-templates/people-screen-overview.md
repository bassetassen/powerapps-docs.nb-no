---
title: Mal for personer – skjermen | Microsoft Docs
description: Forstå hvordan malen for personer-skjermen for lerret fungerer og hvordan du utvider skjermen for dine egne bruks tilfeller
author: emcoope-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 12/30/2018
ms.author: emcoope
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: da7f7c037010df0da30e0363f988ac616f9fb6cc
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/07/2019
ms.locfileid: "71995676"
---
# <a name="overview-of-the-people-screen-template-for-canvas-apps"></a>Oversikt over malen for personer-skjermen for lerret apper

Legg til en skjerm i en lerret-app som lar brukere søke etter personer i organisasjonen. Brukere kan søke etter, velge og legge til personer i en samling. Du kan endre hvilke typer data som vises i søke resultat galleriet, bruke person valgene dine til å sende en e-post og gjøre andre tilpasninger.

Du kan også legge til andre mal BAS ert skjermer som viser ulike data fra Office 365, som for eksempel [e-post](email-screen-overview.md), en brukers [Kalender](calendar-screen-overview.md)og [tilgjengelighet](meeting-screen-overview.md) for personer som kan ønske å invitere til et møte.

Denne oversikten lærer deg:
> [!div class="checklist"]
> * Slik bruker du standard personer-skjerm.
> * Hvordan du endrer skjermen.
> * Slik integrerer du skjermen i apper.

Hvis du vil ha en dypere innsikt i denne skjermens standard funksjon, kan du se [referanse til personer-skjermen](people-screen-reference.md).

## <a name="prerequisite"></a>Nødvendig

Kjennskap til hvordan du legger til og konfigurerer skjermer og andre kontroller mens du [oppretter en app i powerapps](../data-platform-create-app-scratch.md).

## <a name="default-functionality"></a>Standard funksjonalitet

Slik legger du til en person-skjerm fra malen:

1. [Logg deg](http://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) på powerapps, og opprett deretter en app eller åpne en eksisterende app i PowerApps Studio.

    Dette emnet viser en telefon app, men de samme begrepene gjelder for en tavle-app.

1. Velg **ny skjerm**@no__t – 2**personer**på **hjem** -fanen på båndet.

    Som standard ser skjermen lik dette:

    ![Tilstand for første persons skjerm](media/people-screen/people-screen-empty.png)

1. Hvis du vil begynne å søke etter brukere, velger du tekst inn data-boksen øverst og begynner å skrive inn navnet til en kollega. Søke resultatene vises under tekst inn data-boksen:

    ![søke status for personer-skjerm](media/people-screen/people-browse-gall-full.png)

1. Når du velger enkelt personer fra søke resultatene, legges de til i **MyPeople** -samlingen. Inn data verdien for søke feltet tilbakestilles, og samlingen av personer du har valgt, vises:

    ![resultater for personens skjerm samling](media/people-screen/people-people-gall-full.png)

## <a name="modify-the-screen"></a>Endre skjermen

Du kan endre standard funksjonaliteten til dette skjerm bildet ved å [vise ulike data for personer](people-screen-overview.md#show-different-data-for-people).

Hvis du vil endre skjermen videre, kan du bruke [referansene i personer-skjermen](./people-screen-reference.md) som veiledning.

### <a name="show-different-data-for-people"></a>Å vise ulike data for personer

Denne skjermen bruker [Office365Users. SearchUser](https://docs.microsoft.com/connectors/office365users/#searchuser) -operasjonen til å søke etter brukere i organisasjonen. Det gir flere felt for hver hendelse utover det som vises i **UserBrowseGallery** -kontrollen. Å legge til eller endre felt i galleriet er en enkel prosess:

1. Velg en etikett i **UserBrowseGallery**-feltet for å endre (eller legge til en, og Behold den valgt).

1. Når **tekst** -egenskapen er valgt, erstatter du innholdet med `ThisItem.` i formel linjen.

    IntelliSense viser en liste over felt som du kan velge.

1. Velg feltet du vil bruke.

    **Tekst** -egenskapen må oppdatere til `ThisItem.{FieldSelection}`.

## <a name="integrate-the-screen-into-an-app"></a>Integrer skjermen i en app

Personer-skjermen er en kraftig gruppe med kontroller i sin egen rettighet, men den fungerer vanligvis best som en del av en større, mer fleksibel app. Du kan integrere denne skjermen i en større app på en rekke måter, inkludert [Bruk av bufret liste over personer](people-screen-overview.md#use-your-cached-list-of-people).

### <a name="use-your-cached-list-of-people"></a>Bruk hurtigbufret liste over personer

Personer-skjermen bufrer personene som er valgt i **MyPeople** -samlingen. Hvis du har et person oppslag i forretnings scenarioet, må du vite hvordan du bruker denne samlingen. Her finner du ut hvordan du kobler denne skjermen til en rudimentary e-post-skjerm og sender e-post til brukere i **MyPeople** -samlingen. Du får også innsikt i hvordan e- [postskjermen](./email-screen-overview.md) fungerer.

1. Legg til Office 365 Outlook-datakilden i appen ved å velge **Vis** -fanen, velge **data kilder** > **Legg til data kilde**og søke etter Office 365 Outlook Connector. Det kan hende du må velge **ny tilkobling** for å finne den.
1. Når du har satt inn personer-skjermen, kan du sette inn en ny blank skjerm. Legg til et back-pil-ikon, to tekst inn data bokser og et Send-ikon i skjerm bildet.
1. Gi nytt navn til skjermen i **EmailScreen**, det bakre pil ikonet til back- **ikonet**, én tekst inn data boks til **SubjectLine**, den andre til **MessageBody**og Send-ikonet til **SendIcon**.
1. Angi **OnSelect** -egenskapen for **museikon** til `Back()`.
1. Angi **OnSelect** -egenskapen for **SendIcon** til denne formelen:

    ```powerapps-dot
    Office365.SendEmail( 
        Concat( MyPeople, UserPrincipalName & ";" ), 
        SubjectLine.Text, 
        MessageBody.Text 
    )
    ```
    
    Her bruker du Outlook Connector til å sende en e-post. Du sender det `Concat(MyPeople, UserPrincipalName & ";")` som listen over mottakere. Denne formelen setter sammen alle e-postadressene i **MyPeople** -samlingen til én enkelt streng med semikolon som skiller dem. Dette er ikke det samme som å skrive ut en streng med e-postadresser atskilt med semikolon i «til»-linjen i e-postklienten.
    * Du sender `SubjectLine.Text` som emne for meldingen, og `MessageBody.Text` som brød teksten i meldingen.
1. På personer-skjermen, i hjørnet øverst til høyre, setter du inn **e-post** -ikonet.
   Endre ikon fargen til det som passer deg.
1. Angi **OnSelect** -egenskapen for **SendIcon** til `Navigate( EmailScreen, None )`.

    Du har nå en app med to skjerm bilder der du kan velge brukere, skrive en e-postmelding til dem, og deretter sende den. Prøv gjerne å teste det ut, men vær forsiktig, fordi appen sender e-postmeldinger til alle du legger til i **MyPeople** -samlingen.

## <a name="next-steps"></a>Neste trinn

* [Vis referanse dokumentasjonen for dette skjerm bildet](./people-screen-reference.md).
* [Les mer om Office 365 Outlook Connector](../connections/connection-office365-outlook.md).
* [Finn ut mer om koblingen til Office 365-brukere](../connections/connection-office365-users.md).
