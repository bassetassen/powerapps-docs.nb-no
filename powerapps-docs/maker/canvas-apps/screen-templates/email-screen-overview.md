---
title: E-post-skjermen malen | Microsoft Docs
description: Forstå hvordan e-post-skjermen malen for lerret-apper fungerer, og Utvid skjermen for din egen brukstilfeller
author: emcoope-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 12/29/2018
ms.author: emcoope
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: a1aad5ca9e8c7f8b55b1645b04d6c8dc0b9c707b
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/23/2019
ms.locfileid: "61539235"
ms.PowerAppsDecimalTransform: true
---
# <a name="overview-of-the-email-screen-template-for-canvas-apps"></a>Oversikt over e-post-skjermen malen for lerretsapper

I en lerretsapp, kan du legge til en e postskjermen som lar brukerne sende en e-post fra Office 365 Outlook-kontoen deres. Brukere kan søke etter mottakere i deres orgs og legge til eksterne e-postadresser, også. Du kan legge til støtte for bilde-vedlegg, endre brukerdataene som vises i galleriet for søk, og gjøre andre tilpasninger.

Du kan også legge til andre malbaserte skjermer som viser ulike data fra Office 365, for eksempel en brukers [kalender](calendar-screen-overview.md), [personer](people-screen-overview.md) i en organisasjon, og [tilgjengelighet](meeting-screen-overview.md) av personer brukerne vil kanskje invitere til et møte.

Denne oversikten lærer deg:
> [!div class="checklist"]
> * Slik bruker du standard e-post-skjermen.
> * Hvordan til å endre den.
> * Slik integrerer dem i en app.

Hvis en nærmere titt på denne skjermen standard funksjonalitet, kan du se den [e-post-skjermen referanse](email-screen-reference.md).

## <a name="prerequisite"></a>Forutsetning

Kjennskap til hvordan du legger til og konfigurerer skjermbilder og andre kontroller som du [oppretter en app i PowerApps](../data-platform-create-app-scratch.md).

## <a name="default-functionality"></a>Standard-funksjonalitet

Å legge til en skjerm for e-post fra malen:

1. [Logg deg på](http://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) til PowerApps, og deretter opprette en app eller åpne en eksisterende app i PowerApps Studio.

    Dette emnet viser en telefonapp, men samme konsepter gjelder for en nettbrett-app.

1. På den **Hjem** -fanen på båndet, velg **ny skjerm** > **e-post**.

    Som standard ser skjermen omtrent slik ut:

    ![E postskjermen](media/email-screen/email-screen-full.png)

Noen nyttige notater:

* Begynn å skrive navnet i tekstinndata-boksen under «Til» for å søke etter brukere i organisasjonen.
* Når du søker etter personer, returneres bare de øverste 15 resultatene.
* Hvis du vil legge til e-postadresser for e-postmottakere utenfor organisasjonen, Skriv ut full, gyldig e-postadressen, og velg "+" ikonet som vises til høyre for den.
* Du må legge til minst én person som en mottaker, og angi et emne for å sende en e-post.
* Når du har sendt e-postmeldingen, vil innholdet i emnelinjen og meldingsteksten, i tillegg til listen over mottakere alle slettes.

## <a name="modify-the-screen"></a>Endre skjermen

Du kan endre standardfunksjonaliteten til denne skjermen i noen vanlige måter:

* [Legge til støtte for bilde-vedlegg](email-screen-overview.md#add-image-attachment-support)
* [Vis forskjellige data for personer](email-screen-overview.md#show-different-data-for-people)

Hvis du vil endre skjermen ytterligere, kan du bruke den [e-post-skjermen referanse](./email-screen-reference.md) som en veiledning.

> [!IMPORTANT]
> De følgende trinnene antar at du har lagt til bare én e postskjermen til appen. Hvis du har lagt til mer enn én, kontrollnavnene (som **iconMail1**) avsluttes med et annet nummer, og du må justere formlene i henhold til dette.

### <a name="add-image-attachment-support"></a>Legge til støtte for bilde-vedlegg

Dette gjør at brukere kan sende en enkelt avbildning med e-posten som et vedlegg.

1. På den **Sett inn** fanen og velge **Media**, og velg deretter **Legg til bilde**.
1. Angi den nye kontrollen **Y** egenskapen til dette uttrykket:

    `TextEmailMessage1.Y + TextEmailMessage1.Height + 20`
    
1. Med den **AddMediaWithImage** kontrollen settes inn, angi høyden til å være mindre enn 210.
1. Velg i trevisningen kontrollen **AddMediaWithImage** > **...**   >  **Endre rekkefølgen på** > **Plasser lengst bak**.
   Dette hindrer at kontrollen økt foran den **PeopleBrowseGallery** kontroll.
1. Endre den **høyde** -egenskapen for **EmailPeopleGallery** til denne formelen:

    ```powerapps-comma
    Min( 
        ( EmailPeopleGallery1.TemplateHeight + EmailPeopleGallery1.TemplatePadding * 2 ) *
            RoundUp( CountRows( EmailPeopleGallery1.AllItems ) / 2; 0 ); 
        304
    )
    ```

1. Angi den **ShowScrollbar** -egenskapen for **EmailPeopleGallery** til dette uttrykket:

    ```EmailPeopleGallery1.Height >= 304```
    
    Dette hindrer at Maks høyden automatisk installasjon av **AddMediaWithImage** kontroll av siden.
    
1. Endre den **OnSelect** -egenskapen for den **iconMail** kontrollen som denne formelen:

    ```powerapps-comma
    Set( _emailRecipientString; Concat(MyPeople; Mail & ";") );;
    If( IsBlank( UploadedImage1 );
        'Office365'.SendEmail( _emailRecipientString; 
            TextEmailSubject1.Text; 
            TextEmailMessage1.Text; 
            { Importance: "Normal" }
        );
        'Office365'.SendEmail( _emailRecipientString; 
            TextEmailSubject1.Text; 
            TextEmailMessage1.Text; 
            {
                Importance: "Normal";
                Attachments: Table(
                    {
                        Name: "Image.jpg"; 
                        ContentBytes: UploadedImage1.Image
                    }
                )
            }
        )
    );;
    Reset( TextEmailSubject1 );;
    Reset( TextEmailMessage1 );;
    Reset( AddMediaButton1 );;
    Clear( MyPeople )
    ```
    
    Denne formelen kontrollerer om en opplastede avbildningen. Hvis det ingen finnes, deretter den bruker den samme `Office365.SendEmail` som før operasjonen. Hvis det er et bilde, legges den som et vedlegg i tabellen vedlegg.
    Etter sending av e-postmeldingen, ytterligere **tilbakestille** utføres operasjonen på **AddMediaButton** fjerne den opplastede avbildningen.
> [!NOTE]
> Hvis du vil legge til mer enn ett vedlegg i en e-post, kan du legge til poster i tabellen vedlegg.

### <a name="show-different-data-for-people"></a>Vis forskjellige data for personer

Denne skjermen bruker den [Office365Users.SearchUser](https://docs.microsoft.com/connectors/office365users/#searchuser) operasjonen til å søke etter brukere i din organisasjon. Den gir flere felt for hver hendelse utover hva, vises i den **PeopleBrowseGallery** kontroll. Det er enkelt å legge til eller endre feltene i galleriet:

1. I den **PeopleBrowseGallery** kontroll, velg en etikett til å endre (eller Legg til en og holde dem valgt).

1. Med sin **tekst** egenskapen som er valgt, på formellinjen, erstatter innholdet med `ThisItem.`

    IntelliSense viser en liste over felt som du kan velge.

1. Velg feltet du vil bruke.

    Den **tekst** egenskapen oppdateringer til `ThisItem.{FieldSelection}`.

## <a name="integrate-the-screen-into-an-app"></a>Integrere skjermen i en app

E postskjermen er en kraftig gruppe av kontroller i seg selv, men det utfører vanligvis beste som en del av en større, mer allsidig app. Du kan integrere dette skjermbildet i en større app på en rekke måter, inkludert [kobling til skjermbildet kalender](email-screen-overview.md#linking-to-the-calendar-screen).

### <a name="linking-to-the-calendar-screen"></a>Koble til kalender-skjermen

Følg trinnene som er beskrevet i delen «Vis hendelsen deltakere» i [oversikt over kalender-skjermen](./calendar-screen-overview.md#show-event-attendees) men, i det siste trinnet, angi den **Navigate** funksjonen til å åpne skjermbildet e-post. Når du har fullført trinnene, den **MyPeople** samling er utfylt, som gjør at brukere kan sende e-post for personer som er at du deltok den valgte hendelsen.

> [!NOTE]
> Sende denne e-post, sender en egen e-post fra den faktiske hendelsen i Outlook.

## <a name="next-steps"></a>Neste trinn

* [Vis referansedokumentasjon for denne skjermen](./email-screen-reference.md).
* [Finn ut mer om Office 365-brukere-kobling i PowerApps](../connections/connection-office365-users.md).
* [Se alle tilgjengelige tilkoblinger i PowerApps](../connections-list.md).