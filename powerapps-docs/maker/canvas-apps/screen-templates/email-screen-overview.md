---
title: Skjerm bilde for e-post | Microsoft Docs
description: Forstå hvordan malen for e-postskjermen for lerret apps fungerer, og Utvid skjermen for dine egne bruks tilfeller
author: emcoope-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 12/29/2018
ms.author: emcoope
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 2fd03b1a54b54c1abe1d6c30270861b6fc9b8054
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/07/2019
ms.locfileid: "71989343"
---
# <a name="overview-of-the-email-screen-template-for-canvas-apps"></a>Oversikt over malen for e-postskjermen for lerret apper

Legg til en e-postskjerm i en lerret-app som lar brukere sende en e-postmelding fra sin Office 365 Outlook-konto. Brukere kan også søke etter mottakere i sine organisasjoner og legge til eksterne e-postadresser. Du kan legge til støtte for bilde vedlegg, endre bruker dataene som vises i søke galleriet, og gjøre andre tilpasninger.

Du kan også legge til andre mal BAS ert skjermer som viser ulike data fra Office 365, som for eksempel en brukers [Kalender](calendar-screen-overview.md), [personer](people-screen-overview.md) i en organisasjon, og [tilgjengelighet](meeting-screen-overview.md) for personer som bruker kanskje ønsker å invitere til et møte.

Denne oversikten lærer deg:
> [!div class="checklist"]
> * Slik bruker du standard skjermen for e-post.
> * Hvordan du endrer den.
> * Slik integrerer du den i en app.

Hvis du vil ha en dypere innsikt i denne skjermens standard funksjon, kan du se [referanse til e-post-skjermen](email-screen-reference.md).

## <a name="prerequisite"></a>Nødvendig

Kjennskap til hvordan du legger til og konfigurerer skjermer og andre kontroller mens du [oppretter en app i powerapps](../data-platform-create-app-scratch.md).

## <a name="default-functionality"></a>Standard funksjonalitet

Slik legger du til en e-postskjerm fra malen:

1. [Logg deg](http://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) på powerapps, og opprett deretter en app eller åpne en eksisterende app i PowerApps Studio.

    Dette emnet viser en telefon app, men de samme begrepene gjelder for en tavle-app.

1. Velg **ny skjerm** > **e-post**på **hjem** -fanen på båndet.

    Som standard ser skjermen lik dette:

    ![E-post-skjerm](media/email-screen/email-screen-full.png)

Noen nyttige notater:

* Hvis du vil søke etter brukere i organisasjonen, begynner du å skrive inn navnet i tekst inn data-boksen under til.
* Når du søker etter personer, blir bare de 15 øverste resultatene returnert.
* Hvis du vil legge til e-postadresser for e-postmottakere utenfor organisasjonen, skriver du inn den fullstendige, gyldige e-postadressen og velger +-ikonet som vises til høyre for den.
* Du må legge til minst én person som mottaker og angi et emne for å sende en e-post.
* Etter at du har sendt e-postmeldingen, slettes også innholdet i Emne linjen og meldings teksten, i tillegg til mottaker listen.

## <a name="modify-the-screen"></a>Endre skjermen

Du kan endre standard funksjonaliteten til dette skjerm bildet på noen få vanlige måter:

* [Legg til støtte for bilde vedlegg](email-screen-overview.md#add-image-attachment-support)
* [Å vise ulike data for personer](email-screen-overview.md#show-different-data-for-people)

Hvis du vil endre skjermen videre, kan du bruke [referanse til e-post](./email-screen-reference.md) som en veiledning.

> [!IMPORTANT]
> De følgende trinnene forutsetter at du har lagt til bare én e-postskjerm i appen. Hvis du har lagt til mer enn ett, avsluttes kontroll navn (for eksempel **iconMail1**) seg med et annet tall, og du må justere formlene i henhold til dette.

### <a name="add-image-attachment-support"></a>Legg til støtte for bilde vedlegg

Dette gjør at brukerne kan sende ett enkelt bilde med e-post som et vedlegg.

1. Velg **Media**på **Sett inn** -fanen, og velg deretter **Legg til bilde**.
1. Angi **Y** -egenskapen for den nye kontrollen til dette uttrykket:

    `TextEmailMessage1.Y + TextEmailMessage1.Height + 20`
    
1. Når **AddMediaWithImage** -kontrollen er satt inn, setter du høyden til mindre enn 210.
1. Velg **AddMediaWithImage** >  i kontroll tre visningen. **.** .  > **Omorganiser** > **Send lengst bak**.
   Dette hindrer at kontrollen sitter foran **PeopleBrowseGallery** -kontrollen.
1. Endre **Height** -egenskapen for **EmailPeopleGallery** til denne formelen:

    ```powerapps-dot
    Min( 
        ( EmailPeopleGallery1.TemplateHeight + EmailPeopleGallery1.TemplatePadding * 2 ) *
            RoundUp( CountRows( EmailPeopleGallery1.AllItems ) / 2, 0 ), 
        304
    )
    ```

1. Angi **ShowScrollbar** -egenskapen for **EmailPeopleGallery** til dette uttrykket:

    ```EmailPeopleGallery1.Height >= 304```
    
    Dette hindrer den maksimale høyden i å skyve **AddMediaWithImage** -kontrollen bort fra siden.
    
1. Endre **OnSelect** -egenskapen for **iconMail** -kontrollen til denne formelen:

    ```powerapps-dot
    Set( _emailRecipientString, Concat(MyPeople, Mail & ";") );
    If( IsBlank( UploadedImage1 ),
        'Office365'.SendEmail( _emailRecipientString, 
            TextEmailSubject1.Text, 
            TextEmailMessage1.Text, 
            { Importance: "Normal" }
        ),
        'Office365'.SendEmail( _emailRecipientString, 
            TextEmailSubject1.Text, 
            TextEmailMessage1.Text, 
            {
                Importance: "Normal",
                Attachments: Table(
                    {
                        Name: "Image.jpg", 
                        ContentBytes: UploadedImage1.Image
                    }
                )
            }
        )
    );
    Reset( TextEmailSubject1 );
    Reset( TextEmailMessage1 );
    Reset( AddMediaButton1 );
    Clear( MyPeople )
    ```
    
    Denne formelen søker etter en opplastet avbildning. Hvis det ikke finnes noen, bruker den samme `Office365.SendEmail`-operasjonen som før. Hvis det finnes et bilde, legges det til som et vedlegg i Vedleggs tabellen.
    Når du har sendt e-postmeldingen, utføres en ekstra **reset** -operasjon på **AddMediaButton** for å fjerne den opplastede avbildningen.
> [!NOTE]
> Hvis du vil legge til mer enn ett vedlegg i en e-post, kan du legge til poster i vedlegg-tabellen.

### <a name="show-different-data-for-people"></a>Å vise ulike data for personer

Denne skjermen bruker [Office365Users. SearchUser](https://docs.microsoft.com/connectors/office365users/#searchuser) -operasjonen til å søke etter brukere i organisasjonen. Det gir flere felt for hver hendelse utover det som vises i **PeopleBrowseGallery** -kontrollen. Det er enkelt å legge til eller endre felt i galleriet:

1. Velg en etikett i **PeopleBrowseGallery** -kontrollen for å endre (eller Legg til en og Behold den valgt).

1. Når **tekst** -egenskapen er valgt, erstatter du innholdet med `ThisItem.` i formel linjen.

    IntelliSense viser en liste over felt som du kan velge.

1. Velg feltet du vil bruke.

    **Tekst** -egenskapen oppdateres til `ThisItem.{FieldSelection}`.

## <a name="integrate-the-screen-into-an-app"></a>Integrer skjermen i en app

E-skjermen er en kraftig gruppe med kontroller i sin egen rettighet, men den fungerer vanligvis best som en del av en større, mer fleksibel app. Du kan integrere denne skjermen i en større app på en rekke måter, inkludert [kobling til kalender-skjermen](email-screen-overview.md#linking-to-the-calendar-screen).

### <a name="linking-to-the-calendar-screen"></a>Koble til kalender-skjermen

Følg trinnene som er beskrevet i delen «Vis hendelses deltakere» i [Oversikt over kalender-skjermen](./calendar-screen-overview.md#show-event-attendees) , men i det siste trinnet kan du angi funksjonen **Naviger** til å åpne e-postskjermen. Etter at du har fullført disse trinnene, fylles **MyPeople** -samlingen ut, slik at brukere kan sende e-post til personene som deltar på den valgte hendelsen.

> [!NOTE]
> Hvis du sender denne e-posten, sendes en egen e-postmelding fra den faktiske hendelsen i Outlook.

## <a name="next-steps"></a>Neste trinn

* [Vis referanse dokumentasjonen for dette skjerm bildet](./email-screen-reference.md).
* [Les mer om Office 365 brukere-koblingen i powerapps](../connections/connection-office365-users.md).
* [Se alle tilgjengelige tilkoblinger i powerapps](../connections-list.md).