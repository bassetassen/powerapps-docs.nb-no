---
title: Kalender-skjermen malen | Microsoft Docs
description: Forstå hvordan det fungerer kalender-skjermen malen for lerret-apper, endre skjermen, og utvid den som en del av en app
author: emcoope-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 12/28/2018
ms.author: emcoope
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 745b4232a43a06c46866e83ca2452f8a55afeddf
ms.sourcegitcommit: 5e15a1033a68289781f8092fb65c57432501f911
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 01/23/2019
ms.locfileid: "54459509"
---
# <a name="overview-of-the-calendar-screen-template-for-canvas-apps"></a>Oversikt over kalender-skjermen malen for lerretsapper

Legg til en kalender-skjerm som viser brukere kommende hendelser fra Office 365 Outlook-kontoene deres i en lerretsapp. Brukere kan velge en dato fra en kalender og bla gjennom en liste over dagens hendelser. Du kan endre hvilke detaljer vises i listen, Legg til en skjerm som viser flere detaljer om hver hendelse, vise en liste over deltakere for hver hendelse og gjøre andre tilpasninger.

Du kan også legge til andre malbaserte skjermer som viser ulike data fra Office 365, som [e-post](email-screen-overview.md), [personer](people-screen-overview.md) i en organisasjon, og [tilgjengelighet](meeting-screen-overview.md) personer brukere gjerne invitere til et møte.

Denne oversikten lærer deg:
> [!div class="checklist"]
> * Slik bruker du standard kalender-skjermen.
> * Hvordan til å endre den.
> * Slik integrerer dem i en app.

Hvis en nærmere titt på denne skjermen standard funksjonalitet, kan du se den [kalender-skjermen referanse](calendar-screen-reference.md).

## <a name="prerequisite"></a>Forutsetning

Kjennskap til hvordan du legger til og konfigurerer skjermbilder og andre kontroller som du [oppretter en app i PowerApps](../data-platform-create-app-scratch.md).

## <a name="default-functionality"></a>Standard-funksjonalitet

Å legge til en skjerm for kalender fra malen:

1. [Logg deg på](http://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) til PowerApps, og deretter opprette en app eller åpne en eksisterende app i PowerApps Studio.

    Dette emnet viser en telefonapp, men samme konsepter gjelder for en nettbrett-app.

1. På den **Hjem** -fanen på båndet, velg **ny skjerm** > **kalender**.

    Som standard ser skjermen omtrent slik ut:

    ![Kalender-skjermen](media/calendar-screen/calendar-initial.png)

1. For å vise data, velg et alternativ i rullegardinlisten nær toppen av skjermen.

    ![Kalender-skjermen når innlastingen er fullført](./media/calendar-screen/calendar-screen.png)

Noen nyttige notater:

* Dagens dato er valgt som standard, og du kan komme tilbake til den ved å velge Kalender-ikonet i hjørnet øverst til høyre.
* Hvis du velger en annen dato, omgis den av en sirkel og et lyse rektangel (blå hvis standardtemaet brukes) omslutter dagens dato.
* Hvis minst én hendelse er planlagt for en bestemt dato, vises en liten farget sirkel under denne datoen i kalenderen.
* Hvis du velger en dato som en eller flere hendelser er planlagt, vises hendelse(r) i en liste under kalenderen.

## <a name="modify-the-screen"></a>Endre skjermen

Du kan endre standardfunksjonaliteten til denne skjermen i noen vanlige måter:

* [Angi kalenderen](calendar-screen-overview.md#specify-the-calendar).
* [Vis forskjellige detaljer om en hendelse](calendar-screen-overview.md#show-different-details-about-an-event).
* [Skjul ikke-blokkerende hendelser](calendar-screen-overview.md#hide-nonblocking-events).

Hvis du vil endre skjermen ytterligere, kan du bruke den [kalender-skjermen referanse](./calendar-screen-reference.md) som en veiledning.

### <a name="specify-the-calendar"></a>Angi kalenderen

Hvis du allerede vet hvilken kalender som brukerne skal vise, kan du forenkle skjermen ved å angi denne kalenderen før du publiserer appen. Denne endringen fjerner behovet for rullegardinlisten i kalendere, slik at du kan fjerne den.

1. Angi den **[OnStart](../controls/control-screen.md)** -egenskapen for standard-skjermen i appen til denne formelen:

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
    > Denne formelen er litt redigeres fra standardverdien for den **OnSelect** -egenskapen for rullegardinlisten for å velge en kalender. For mer informasjon om denne kontrollen, kan du se den i den [kalender-skjermen referanse](./calendar-screen-reference.md#calendar-drop-down).

1. Erstatt `{YourCalendarNameHere}`, inkludert klammeparenteser, med navnet på kalenderen som du vil vise (for eksempel **kalender**).

    > [!IMPORTANT]
    > De følgende trinnene antar at du har lagt til bare én kalender-skjermen til appen. Hvis du har lagt til mer enn én, kontrollnavnene (som **iconCalendar1**) avsluttes med et annet nummer, og du må justere formlene i henhold til dette.

1. Angi den **Y** -egenskapen for den **iconCalendar1** kontrollen til dette uttrykket:

    `RectQuickActionBar1.Height + 20`

1. Angi den **Y** -egenskapen for den **LblMonthSelected1** kontrollen til dette uttrykket:

    `iconCalendar1.Y + iconCalendar1.Height + 20`

1. Angi den **tekst** -egenskapen for den **LblNoEvents1** kontrollen som denne verdien:

    `"No events scheduled"`

1. Angi den **Visible** -egenskapen for **LblNoEvents1** til denne formelen:

    `CountRows(CalendarEventsGallery1.AllItems) = 0 && _calendarVisible`

1. Slett disse kontrollene:

    - **dropdownCalendarSelection1**
    - **LblEmptyState1**
    - **iconEmptyState1**

1. Hvis kalender-skjermen ikke er standardskjermen, kan du legge til en knapp som navigerer fra standardskjermen til kalender-skjermen slik at du kan teste appen.

    For eksempel legge til en knapp på **Screen1** som går til **skjerm2** Hvis du har lagt til en kalender-skjermen til en app som du opprettet fra tomt.

1. Lagre appen, og test den deretter i en nettleser eller på en mobil enhet.

### <a name="show-different-details-about-an-event"></a>Vis forskjellige detaljer om en hendelse

Som standard, galleriet under kalenderen, kalt **CalendarEventsGallery**, viser starttidspunktet, varigheten, emnet og plasseringen av hver hendelse. Du kan konfigurere galleriet for å vise alle felt (for eksempel arrangøren) som den [Office 365-koblingen](https://docs.microsoft.com/connectors/office365/#calendareventclientreceive) støtter.

1. I **CalendarEventsGallery**, kan du angi den **tekst** -egenskapen for en ny eller en eksisterende etikett til `ThisItem` etterfulgt av et punktum.

    IntelliSense viser feltene som du kan velge.

1. Velg feltet du vil bruke.

    Etiketten viser informasjonen du har angitt.

### <a name="hide-nonblocking-events"></a>Skjul ikke-blokkerende hendelser

I mange kontorer sende gruppemedlemmer møteforespørsler til å varsle hverandre når de vil være borte fra kontoret. For å unngå blokkerer alles tidsplaner, personen som sender forespørselen angir at det er tilgjengelig til **gratis**. Du kan skjule disse hendelser fra kalenderen og galleriet ved å oppdatere noen av egenskapene.

1. Angi den **elementer** -egenskapen for **CalendarEventsGallery** til denne formelen:

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

    I denne formelen den **Filter** funksjonen aktiveres, skjules ikke bare disse hendelser som er planlagt for en dato enn det som er valgt, men også hendelser som tilgjengeligheten er satt til **gratis**.

1. I kalenderen, kan du angi den **Visible** -egenskapen for den **sirkel** kontrollen som denne formelen:

    ```powerapps-dot
    CountRows(
        Filter(
            MyCalendarEvents,
            DateValue( Text(Start) ) = DateAdd( _firstDayInView, ThisItem.Value, Days ),
            ShowAs <> "Free"
        )
    ) > 0 && !Subcircle1.Visible && Title2.Visible
    ```
    Denne formelen inneholder de samme filtrene som formelen. Derfor hendelse-indikator sirkelen vises under en dato bare hvis den har én eller flere hendelser som er på den valgte datoen og for tilgjengeligheten er ikke satt til **gratis**.

## <a name="integrate-the-screen-into-an-app"></a>Integrere skjermen i en app

Kalender-skjermen er en kraftig gruppe av kontroller i seg selv, men det utfører vanligvis beste som en del av en større, mer allsidig app. Du kan integrere dette skjermbildet i en større app på en rekke måter, inkludert å legge til disse alternativene:

* [Vis hendelsesdetaljer](calendar-screen-overview.md#view-event-details).
* [Vis deltakere for hendelsen](calendar-screen-overview.md#show-event-attendees).

### <a name="view-event-details"></a>Vis hendelsesdetaljer

Hvis brukere velger en hendelse i **CalendarEventsGallery**, kan du åpne en annen skjerm som viser mer informasjon om den hendelsen.

> [!NOTE]
> Denne fremgangsmåten viser hendelsesdetaljer i et galleri med dynamisk innhold, men du kan oppnå lignende resultater ved å ta andre tilnærminger. Du kan for eksempel få mer design-kontroll ved hjelp av en serie med etiketter i stedet.

1. Legg til en tom skjerm, med navnet **EventDetailsScreen**, som inneholder en tom galleri med fleksibel høyde og en knapp som går tilbake til skjermbildet kalenderen.

1. I galleriet fleksibel høyde, kan du legge til en **etikett** kontroll og en **HTML-tekst** kontroll, og angi den **AutoHeight** i begge til **SANN** .

    > [!NOTE]
    > PowerApps henter meldingsteksten i hver hendelse som HTML-tekst, slik at du vil vise innholdet i en **HTML-tekst** kontroll.

1. Angi den **Y** -egenskapen for den **HTML-tekst** kontrollen til dette uttrykket:

    `Label1.Y + Label1.Height + 20`

1. Justere flere egenskaper etter behov til dine behov stil.

    Du kan for eksempel legge til en skillelinje nedenfor den **HTML-tekst** kontroll.

1. Angi den **elementer** -egenskapen for galleriet fleksibel høyde til denne formelen:

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

    Denne formelen oppretter et galleri med dynamiske data som er angitt til verdiene i **_selectedCalendarEvent**, som er angitt hver gang brukeren velger en hendelse i den **CalendarEventsGallery** kontroll. Du kan utvide dette galleriet for å inkludere flere felt ved å legge til flere etiketter til den, men dette settet inneholder et godt utgangspunkt.

1. Med elementene i galleriet på sted, angi den **tekst** -egenskapen for den **etikett** kontrollen til `ThisItem.Title`, og den **HtmlText** -egenskapen for den **HTML-tekst**  kontrollen til `ThisItem.Value`.

1. I **CalendarEventsGallery**, kan du angi den **OnSelect** -egenskapen for den **tittel** kontrollen som denne formelen:

    ```powerapps-dot
    Set( _selectedCalendarEvent, ThisItem );
    Navigate( EventDetailsScreen, None )
    ```

    > [!Note]
    > I stedet for å bruke den **_selectedCalendarEvent** variabelen, du kan bruke i stedet **CalendarEventsGallery**. Valgt.

### <a name="show-event-attendees"></a>Vis deltakere for hendelsen

Den `Office365.GetEventsCalendarViewV2` operasjonen henter en rekke feltene for hver hendelse, inkludert et adskilt med semikolon sett med nødvendige og valgfrie deltakere. I denne prosedyren skal du analysere hvert sett av deltakere, finne ut hvilke deltakere som er i organisasjonen din og hente Office 365-profiler for alle som er.

1. Hvis appen ikke inneholder koblingen for Office 365-brukere, [legge den](../add-data-connection.md).

1. Hvis du vil hente Office 365-profiler for møtedeltakerne, kan du angi den **OnSelect** -egenskapen for den **tittel** kontroll i den **CalendarEventsGallery** til denne formelen:

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

Denne listen beskriver hva hver **ClearCollect** operasjonen samsvarer:

- ClearCollect(AttendeeEmailsTemp)
    ```powerapps-dot
    ClearCollect( AttendeeEmailsTemp,
        Filter(
            Split( ThisItem.RequiredAttendees & ThisItem.OptionalAttendees, ";" ), 
            !IsBlank( Result)
        )
    );
    ```

    Denne formelen Kjeder sammen nødvendige og valgfrie deltakere til en enkelt streng, og deretter deler denne strengen i individuelle postadresser ved hver semikolon. Formelen og deretter filtrerer ut tomme verdier fra dette settet og legger til de andre verdiene i en samling med navnet **AttendeeEmailsTemp**.

- ClearCollect(AttendeeEmails)
    ```powerapps-dot
    ClearCollect( AttendeeEmails,
        AddColumns( AttendeeEmailsTemp, 
            "InOrg",
            Upper( _userDomain ) = Upper( Right( Result, Len(Result) - Find("@", Result) ) )
        )
    );
    ```
    Denne formelen omtrent bestemmer om en deltaker i organisasjonen din. Definisjonen av **_userDomain** er ganske enkelt domene URL-adressen i e-postadressen til personen som kjører appen. Denne linjen oppretter en ekstra SANN/USANN-kolonne, kalt **InOrg**, i den **AttendeeEmailsTemp** samling. Denne kolonnen inneholder **SANN** Hvis **userDomain** tilsvarer domene URL-adressen til e-postadressen i den bestemte raden i **AttendeeEmailsTemp**.

    Denne tilnærmingen er ikke alltid nøyaktig, men det blir ganske Lukk. Bestemte deltakere i organisasjonen kan for eksempel ha en e-postadresse som Jane@OnContoso.com, mens **_userDomain** er Contoso.com. Appen bruker- og Stine kan arbeide i den samme firmarelaterte, men har små variasjoner i deres e-postadresser. For tilfeller som disse, kan du vil bruke denne formelen:

    `Upper(_userDomain) in Upper(Right(Result, Len(Result) - Find("@", Result)))`

    Denne formelen samsvarer imidlertid med e-postadresser som Jane@NotTheContosoCompany.com med en **_userDomain** som Contoso.com og de som ikke fungerer i samme firmaet.

- ClearCollect(MyPeople)

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
    Hvis du vil hente Office 365-profiler, må du bruke den [Office365Users.UserProfile](https://docs.microsoft.com/connectors/office365users/#userprofile) eller [Office365Users.UserProfileV2](https://docs.microsoft.com/connectors/office365users/#userprofile) operasjonen. Disse operasjonene først samle alle Office 365-profiler for deltakere som er i brukerens organisasjon. Operasjonene Legg deretter til noen få felt for deltakere fra utenfor organisasjonen. Du atskilt disse to elementene i forskjellige operasjoner, fordi den **ForAll** løkke garanterer ikke rekkefølge. Derfor **ForAll** kan samle inn en deltaker fra utenfor organisasjonen først. I dette tilfellet skjemaet for **MyPeople** inneholder bare **DisplayName**, **Id**, **JobTitle**, og **UserPrincipalName** . Operasjonene UserProfile hente imidlertid mye mer omfattende data enn det som. Slik at du tvinge den **MyPeople** samlingen for å legge til Office 365-profiler før de andre profilene.

    > [!NOTE]
    > Du kan oppnå det samme resultatet med bare én **ClearCollect** funksjonen:

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

Å fullføre denne øvelsen:

1. Legg til en skjerm som inneholder et galleri som den **elementer** egenskapen er satt til **MyPeople**.

1. I den **OnSelect** -egenskapen for den **tittel** kontroll i den **CalendarEventsGallery**, legge til en **Navigate** fungere på skjermen som du opprettet i forrige trinn.

## <a name="next-steps"></a>Neste trinn

* [Vis referansedokumentasjon for denne skjermen](calendar-screen-reference.md).
* [Finn ut mer om Office 365 Outlook connector](../connections/connection-office365-outlook.md).
* [Finn ut mer om Office 365-brukere connector](../connections/connection-office365-users.md).
