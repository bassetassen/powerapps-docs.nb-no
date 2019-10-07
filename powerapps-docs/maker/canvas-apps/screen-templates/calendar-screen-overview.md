---
title: Mal i Kalender | Microsoft Docs
description: Forstå hvordan malen kalender-skjerm for lerret apps fungerer, endre skjermen og utvide den som en del av en app
author: emcoope-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 12/28/2018
ms.author: emcoope
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 470aa0671eddc5f4d3621c4dbdd8d81036c358e4
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/07/2019
ms.locfileid: "71989420"
---
# <a name="overview-of-the-calendar-screen-template-for-canvas-apps"></a>Oversikt over malen kalender-skjerm for lerret apper

Legg til en kalender-skjerm i en lerret-app som viser brukerne kommende hendelser fra Office 365 Outlook-kontoene. Brukere kan velge en dato fra en kalender og bla gjennom en liste over dagens arrangementer. Du kan endre hvilke detaljer som vises i listen, legge til en ekstra skjerm som viser flere detaljer om hver hendelse, vise en liste over deltakere for hver hendelse, og gjøre andre tilpasninger.

Du kan også legge til andre mal BAS ert skjermer som viser ulike data fra Office 365, som for eksempel [e-post](email-screen-overview.md), [personer](people-screen-overview.md) i en organisasjon, og [tilgjengelighet](meeting-screen-overview.md) for personer som kan ønske å invitere til et møte.

Denne oversikten lærer deg:
> [!div class="checklist"]
> * Slik bruker du standard kalender-skjermen.
> * Hvordan du endrer den.
> * Slik integrerer du den i en app.

Hvis du vil ha en dypere innsikt i denne skjermens standard funksjon, kan du se [referanse til kalender-skjermen](calendar-screen-reference.md).

## <a name="prerequisite"></a>Nødvendig

Kjennskap til hvordan du legger til og konfigurerer skjermer og andre kontroller mens du [oppretter en app i powerapps](../data-platform-create-app-scratch.md).

## <a name="default-functionality"></a>Standard funksjonalitet

Slik legger du til en kalender-skjerm fra malen:

1. [Logg deg](http://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) på powerapps, og opprett deretter en app eller åpne en eksisterende app i PowerApps Studio.

    Dette emnet viser en telefon app, men de samme begrepene gjelder for en tavle-app.

1. Velg **ny skjerm** > **Kalender**på **hjem** -fanen på båndet.

    Som standard ser skjermen lik dette:

    ![Kalender-skjerm](media/calendar-screen/calendar-initial.png)

1. Hvis du vil vise data, velger du et alternativ i rulle gardin listen nær toppen av skjermen.

    ![Kalender skjermen etter at innlastingen er fullført](./media/calendar-screen/calendar-screen.png)

Noen nyttige notater:

* Dagens dato er valgt som standard, og du kan enkelt gå tilbake til den ved å velge kalender ikonet i øvre høyre hjørne.
* Hvis du velger en annen dato, omslutter en sirkel og et rektangel med lyst farge (blå hvis standard temaet brukes) omslutter dagens dato.
* Hvis minst én hendelse er planlagt for en bestemt dato, vises en liten, farget sirkel under denne datoen i kalenderen.
* Hvis du velger en dato for når én eller flere hendelser planlegges, vises hendelsen (e) i en liste under kalenderen.

## <a name="modify-the-screen"></a>Endre skjermen

Du kan endre standard funksjonaliteten til dette skjerm bildet på noen få vanlige måter:

* [Angi kalenderen](calendar-screen-overview.md#specify-the-calendar).
* [Vis ulike detaljer om en hendelse](calendar-screen-overview.md#show-different-details-about-an-event).
* [Skjul ikke-blokkerende hendelser](calendar-screen-overview.md#hide-nonblocking-events).

Hvis du vil endre skjermen videre, kan du bruke [Referanse for kalender-skjerm](./calendar-screen-reference.md) som en veiledning.

### <a name="specify-the-calendar"></a>Angi kalenderen

Hvis du allerede vet hvilken kalender brukerne skal vise, kan du forenkle skjermen ved å angi denne kalenderen før du publiserer appen. Denne endringen fjerner behovet for rulle gardin listen med kalendere, slik at du kan fjerne den.

1. Angi **[OnStart](../controls/control-screen.md)** -egenskapen for standard skjermen i appen til denne formelen:

    ```powerapps-dot
    Set( _userDomain, Right( User().Email, Len( User().Email ) - Find( "@", User().Email ) ) );
    Set( _dateSelected, Today() );
    Set( _firstDayOfMonth, DateAdd( Today(), 1 - Day( Today() ), Days ) );
    Set( _firstDayInView, 
        DateAdd( _firstDayOfMonth, -( Weekday( _firstDayOfMonth) - 2 + 1 ), Days )
    );
    Set( _lastDayOfMonth, DateAdd( DateAdd( _firstDayOfMonth, 1, Months ), -1, Days ) );
    Set( _calendarVisible, false );
    Set( _myCalendar, 
        LookUp( Office365.CalendarGetTables().value, DisplayName = "{YourCalendarNameHere}" )
    );
    Set( _minDate, 
        DateAdd( _firstDayOfMonth, -( Weekday(_firstDayOfMonth) - 2 + 1 ), Days )
    );
    Set( _maxDate, 
        DateAdd(
            DateAdd( _firstDayOfMonth, -( Weekday(_firstDayOfMonth) - 2 + 1 ), Days ),
            40, 
            Days 
        )
    );
    ClearCollect( MyCalendarEvents, 
        Office365.GetEventsCalendarViewV2( _myCalendar.Name, 
            Text( _minDate, UTC ), 
            Text( _maxDate, UTC ) 
        ).value
    );
    Set( _calendarVisible, true )
    ```

    > [!NOTE]
    > Denne formelen er litt redigert fra standard verdien for egenskapen **OnSelect** for rulle gardin listen for å velge en kalender. Hvis du vil ha mer informasjon om denne kontrollen, kan du se delen i [referanse til kalender-skjermen](./calendar-screen-reference.md#calendar-drop-down).

1. Erstatt `{YourCalendarNameHere}`, inkludert klamme parenteser, med navnet på kalenderen som du vil vise (for eksempel **Kalender**).

    > [!IMPORTANT]
    > De følgende trinnene forutsetter at du har lagt til bare én kalender skjerm i appen. Hvis du har lagt til mer enn ett, avsluttes kontroll navn (for eksempel **iconCalendar1**) seg med et annet tall, og du må justere formlene i henhold til dette.

1. Angi **Y** -egenskapen for **iconCalendar1** -kontrollen til dette uttrykket:

    `RectQuickActionBar1.Height + 20`

1. Angi **Y** -egenskapen for **LblMonthSelected1** -kontrollen til dette uttrykket:

    `iconCalendar1.Y + iconCalendar1.Height + 20`

1. Angi **tekst** -egenskapen for **LblNoEvents1** -kontrollen til denne verdien:

    `"No events scheduled"`

1. Angi **Visible** -egenskapen for **LblNoEvents1** til denne formelen:

    `CountRows(CalendarEventsGallery1.AllItems) = 0 && _calendarVisible`

1. Slett disse kontrollene:

    - **dropdownCalendarSelection1**
    - **LblEmptyState1**
    - **iconEmptyState1**

1. Hvis kalender skjermen ikke er standard skjerm bilde, kan du legge til en knapp som navigerer fra standard skjermen til kalender skjermen, slik at du kan teste appen.

    Du kan for eksempel legge til en knapp på **Screen1** som navigerer til **Screen2** hvis du har lagt til en kalender-skjerm i en app som du opprettet fra tom.

1. Lagre appen, og test den i en nett leser eller på en mobilen het.

### <a name="show-different-details-about-an-event"></a>Å vise ulike detaljer om en hendelse

Som standard viser galleriet under kalenderen, kalt **CalendarEventsGallery**, start tidspunkt, varigheten, emnet og plasseringen av hver hendelse. Du kan konfigurere galleriet til å vise et hvilket som helst felt (for eksempel arrangøren) som [Office 365-koblingen](https://docs.microsoft.com/connectors/office365/#calendareventclientreceive) støtter.

1. Angi **tekst** -egenskapen for en ny eller eksisterende etikett til `ThisItem` etterfulgt av et punktum i **CalendarEventsGallery**.

    IntelliSense viser feltene som du kan velge.

1. Velg feltet du vil bruke.

    Etiketten viser informasjons typen du har angitt.

### <a name="hide-nonblocking-events"></a>Skjul ikke-blokkerende hendelser

I mange kontorer sender gruppe medlemmer møte innkallelser for å varsle hverandre når de blir borte fra kontoret. For å unngå å blokkere alles tids planer, angir personen som sender forespørselen sin tilgjengelighet til **gratis**. Du kan skjule disse hendelsene fra kalenderen og galleriet ved å oppdatere et par egenskaper.

1. Angi **elementer** -egenskapen for **CalendarEventsGallery** til denne formelen:

    ```powerapps-dot
    SortByColumns(
        Filter(
            MyCalendarEvents,
            Text( Start, DateTimeFormat.ShortDate ) = 
                Text( _dateSelected, DateTimeFormat.ShortDate ),
            ShowAs <> "Free"
        ),
        "Start"
    )
    ```

    I denne formelen skjuler **filter** -funksjonen ikke bare de hendelsene som er planlagt for en annen dato enn den som er valgt, men også hendelser som tilgjengeligheten er satt til **gratis**for.

1. Angi **Visible** -egenskapen for **sirkel** kontrollen til denne formelen i kalenderen:

    ```powerapps-dot
    CountRows(
        Filter(
            MyCalendarEvents,
            DateValue( Text(Start) ) = DateAdd( _firstDayInView, ThisItem.Value, Days ),
            ShowAs <> "Free"
        )
    ) > 0 && !Subcircle1.Visible && Title2.Visible
    ```
    Denne formelen inneholder de samme filtrene som den forrige formelen. Sirkel indikatoren vises derfor under en dato bare hvis den har én eller flere hendelser som er på den valgte datoen, og som tilgjengeligheten ikke er satt til **gratis**.

## <a name="integrate-the-screen-into-an-app"></a>Integrer skjermen i en app

Kalender-skjermen er en kraftig gruppe med kontroller i sin egen rettighet, men den fungerer vanligvis best som en del av en større, mer fleksibel app. Du kan integrere denne skjermen i en større app på en rekke måter, inkludert å legge til disse alternativene:

* [Vis hendelses detaljer](calendar-screen-overview.md#view-event-details).
* [Vis arrangements deltakere](calendar-screen-overview.md#show-event-attendees).

### <a name="view-event-details"></a>Vis hendelses detaljer

Hvis brukere velger en hendelse i **CalendarEventsGallery**, kan du åpne en annen skjerm som viser mer informasjon om hendelsen.

> [!NOTE]
> Denne Fremgangs måten viser hendelses detaljer i et galleri med dynamisk innhold, men du kan oppnå lignende resultater ved å gjøre andre måter. Du kan for eksempel få mer utformings kontroll ved å bruke en serie med etiketter i stedet.

1. Legg til en tom skjerm, kalt **EventDetailsScreen**, som inneholder et tomt, fleksibelt høyde galleri og en knapp som navigerer tilbake til kalender skjermen.

1. Legg til en **etikett** -kontroll og en **HTML-tekst** -kontroll i galleriet med fleksible høyder, og angi **autoheight** -egenskapen for begge til **sann**.

    > [!NOTE]
    > PowerApps henter meldings teksten for hver hendelse som HTML-tekst, så du må vise dette innholdet i en **HTML** -tekstkontroll.

1. Angi **Y** -egenskapen for kontrollen for **HTML-tekst** til dette uttrykket:

    `Label1.Y + Label1.Height + 20`

1. Juster flere egenskaper etter behov, slik at de passer til stil behovene dine.

    Det kan for eksempel hende at du ønsker å legge til en skille linje under **HTML** -tekstkontrollen.

1. Angi **elementer** -egenskapen for galleriet med fleksibel høyde til denne formelen:

    ```powerapps-dot
    Table(
        { Title: "Subject", Value: _selectedCalendarEvent.Subject },
        { 
            Title: "Time", 
            Value: _selectedCalendarEvent.Start & " - " & _selectedCalendarEvent.End 
        },
        { Title: "Body", Value: _selectedCalendarEvent.Body }
    )
    ```

    Denne formelen oppretter et galleri med dynamiske data som er satt til felt verdiene for **_selectedCalendarEvent**, som angis hver gang brukeren velger en hendelse i **CalendarEventsGallery** -kontrollen. Du kan utvide dette galleriet for å inkludere flere felt ved å legge til flere etiketter, men dette settet gir et godt utgangs punkt.

1. Hvis Galleri elementene er på plass, kan du angi **tekst** -egenskapen for **etikett** -kontrollen til `ThisItem.Title`, og **HtmlText** -egenskapen til kontrollen for HTML- **tekst** til `ThisItem.Value`.

1. Angi **OnSelect** -egenskapen for **Tittel** -kontrollen i **CalendarEventsGallery**til denne formelen:

    ```powerapps-dot
    Set( _selectedCalendarEvent, ThisItem );
    Navigate( EventDetailsScreen, None )
    ```

    > [!Note]
    > I stedet for å bruke **_selectedCalendarEvent** -variabelen, kan du bruke **CalendarEventsGallery**i stedet. Aktivert.

### <a name="show-event-attendees"></a>Vis arrangements deltakere

@No__t-0-operasjonen henter en rekke felt for hver hendelse, inkludert et semikolondelte sett med obligatoriske og valg frie deltakere. I denne prosedyren analyserer du hvert sett med deltakere, finner ut hvilke deltakere som er i organisasjonen din, og henter Office 365-profilene til alle som er det.

1. Hvis appen ikke inneholder koblingen til Office 365-brukere, kan du [legge den til](../add-data-connection.md).

1. Hvis du vil hente Office 365-profilene til møte deltakerne, angir du **OnSelect** -egenskapen for **title** -kontrollen i **CalendarEventsGallery** til denne formelen:

    ```powerapps-dot
    Set( _selectedCalendarEvent, ThisItem );
    ClearCollect( AttendeeEmailsTemp,
        Filter(
            Split( ThisItem.RequiredAttendees & ThisItem.OptionalAttendees, ";" ),
            !IsBlank( Result )
        )
    );
    ClearCollect( AttendeeEmails,
        AddColumns( AttendeeEmailsTemp, 
            "InOrg",
            Upper( _userDomain ) = Upper( Right( Result, Len( Result ) - Find( "@", Result ) ) )
        )
    );
    ClearCollect( MyPeople,
        ForAll( AttendeeEmails, If( InOrg, Office365Users.UserProfile( Result ) ) ) 
    );
    Collect( MyPeople,
        ForAll( AttendeeEmails,
            If( !InOrg, 
                { DisplayName: Result, Id: "", JobTitle: "", UserPrincipalName: Result }
            )
        )
    )
    ```

Denne listen beskriver hva hver **ClearCollect** -operasjon gjør:

- ClearCollect (AttendeeEmailsTemp)
    ```powerapps-dot
    ClearCollect( AttendeeEmailsTemp,
        Filter(
            Split( ThisItem.RequiredAttendees & ThisItem.OptionalAttendees, ";" ), 
            !IsBlank( Result)
        )
    );
    ```

    Denne formelen kobler sammen de obligatoriske og valg frie deltakerne til én enkelt streng, og deler deretter denne strengen inn i individuelle adresser ved hvert semikolon. Formelen filtrerer deretter tomme verdier fra settet, og legger til de andre verdiene i en samling med navnet **AttendeeEmailsTemp**.

- ClearCollect (AttendeeEmails)
    ```powerapps-dot
    ClearCollect( AttendeeEmails,
        AddColumns( AttendeeEmailsTemp, 
            "InOrg",
            Upper( _userDomain ) = Upper( Right( Result, Len(Result) - Find("@", Result) ) )
        )
    );
    ```
    Denne formelen bestemmer omtrent om en deltaker er i din organisasjon. Definisjonen av **_userDomain** er ganske enkelt URL-adressen til domenet i e-postadressen til personen som kjører appen. Denne linjen oppretter en ekstra sann/usann-kolonne, kalt **InOrg**, i **AttendeeEmailsTemp** -samlingen. Denne kolonnen inneholder **sann** Hvis **userDomain** er identisk med URL-adressen til domenet i e-postadressen i den bestemte raden i **AttendeeEmailsTemp**.

    Denne Fremgangs måten er ikke alltid nøyaktig, men den blir ganske nær. Enkelte deltakere i organisasjonen kan for eksempel ha en e-postadresse som Jane@OnContoso.com, mens **_userDomain** er contoso.com. App-brukeren og Janne kan fungere på samme firma, men som har små variasjoner i e-postadressene sine. I slike tilfeller kan det være lurt å bruke denne formelen:

    `Upper(_userDomain) in Upper(Right(Result, Len(Result) - Find("@", Result)))`

    Denne formelen Sams varer imidlertid med e-postadresser som Jane@NotTheContosoCompany.com med en **_userDomain** som contoso.com, og disse personene fungerer ikke i samme firma.

- ClearCollect (MyPeople)

    ```powerapps-dot
    ClearCollect( MyPeople,
        ForAll( AttendeeEmails, 
            If( InOrg, 
                Office365Users.UserProfile( Result )
            )
        )
    );
    Collect( MyPeople,
        ForAll( AttendeeEmails,
            If( !InOrg, 
                { 
                    DisplayName: Result, 
                    Id: "", 
                    JobTitle: "", 
                    UserPrincipalName: Result
                }
            )
        )
    );
    ```
    Hvis du vil hente Office 365-profiler, må du bruke operasjonen [Office365Users. USERPROFILE](https://docs.microsoft.com/connectors/office365users/#userprofile) eller [Office365Users. UserProfileV2](https://docs.microsoft.com/connectors/office365users/#userprofile) . Disse operasjonene først samler alle Office 365-profilene til deltakerne som er i brukerens organisasjon. Deretter legger operasjonen til noen få felt for deltakere utenfor organisasjonen. Du har adskilt disse to elementene i forskjellige operasjoner, fordi **ForAll** -løkken ikke garanterer rekkefølgen. **ForAll** kan derfor samle inn en deltaker utenfor organisasjonen først. I dette tilfellet inneholder skjemaet for **MyPeople** bare **DisplayName**, **ID**, **JobTitle**og **userPrincipalName**. USERPROFILE-operasjonen henter imidlertid mye bedre data enn det. Så du tvinger **MyPeople** -samlingen til å legge til Office 365-profiler før de andre profilene.

    > [!NOTE]
    > Du kan oppnå samme resultat med bare én **ClearCollect** -funksjon:

    ```powerapps-dot
    ClearCollect( MyPeople, 
        ForAll(
            AddColumns(
                Filter(
                    Split(
                        ThisItem.RequiredAttendees & ThisItem.OptionalAttendees, 
                        ";"
                    ), 
                    !IsBlank( Result )
                ), 
                "InOrg", _userDomain = Right( Result, Len( Result ) - Find( "@", Result ) )
            ), 
            If( InOrg, 
                Office365Users.UserProfile( Result ), 
                { 
                    DisplayName: Result, 
                    Id: "", 
                    JobTitle: "", 
                    UserPrincipalName: Result, 
                    Department: "", 
                    OfficeLocation: "", 
                    TelephoneNumber: ""
                }
            )
        )
    )
    ```

Slik full fører du denne øvelsen:

1. Legg til en skjerm som inneholder et galleri der **element** -egenskapen er satt til **MyPeople**.

1. Legg til en **Naviger** -funksjon på skjermen som du opprettet i forrige trinn, i **OnSelect** -egenskapen i **Tittel** -kontrollen i **CalendarEventsGallery**.

## <a name="next-steps"></a>Neste trinn

* [Vis referanse dokumentasjonen for dette skjerm bildet](calendar-screen-reference.md).
* [Les mer om Office 365 Outlook Connector](../connections/connection-office365-outlook.md).
* [Finn ut mer om koblingen til Office 365-brukere](../connections/connection-office365-users.md).
