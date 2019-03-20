---
title: Referanse for malen møte-skjermen for lerret-apper | Microsoft Docs
description: Forstå detaljene for hvordan møte-skjermen malen for lerret-apper fungerer i PowerApps
author: emcoope-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 01/03/2019
ms.author: emcoope
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: a7559f84b43d3c0372dea71d49c35461ba9d4e57
ms.sourcegitcommit: 5e15a1033a68289781f8092fb65c57432501f911
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 01/23/2019
ms.locfileid: "54459532"
---
# <a name="reference-information-about-the-meeting-screen-template-for-canvas-apps"></a>Referanseinformasjon om møte-skjermen malen for lerretsapper

Forstå hvordan hver betydelige kontroll i malen møte skjerm bidrar til skjermens overordnede standardfunksjonaliteten for lerret-apper i PowerApps. Dette dypdykket noe presenterer formler for virkemåte og verdiene i andre egenskaper som bestemmer hvordan kontrollene svare på inndata fra brukeren. Hvis en på høyt nivå gjennomgang av denne skjermen standard funksjonalitet, kan du se den [møte-skjermen oversikt over](meeting-screen-overview.md).

Dette emnet uthever noen viktige kontroller og forklarer uttrykk eller formler til hvilke ulike egenskaper (slik som **elementer** og **OnSelect**) av disse kontrollene er angitt:

* [Inviter fanen (LblInviteTab)](#invite-tab)
* [Schedule tab (LblScheduleTab)](#schedule-tab)
* [Tekstboks for søk](#text-search-box)
* [Legg til ikonet (AddIcon)](#add-icon)
* [Personer Bla gjennom galleriet](#people-browse-gallery) (+ underordnede kontroller)
* [Møte personer galleriet](#meeting-people-gallery) (+ underordnede kontroller)
* [Møte datovelger (MeetingDateSelect)](#meeting-date-picker)
* [Møte varighet rullegardinlisten (MeetingDurationSelect)](#meeting-duration-drop-down)
* [Finn møtetidspunkter galleriet](#find-meeting-times-gallery) (+ underordnede kontroller)
* [Plass Bla gjennom galleriet](#room-browse-gallery) (+ underordnede kontroller)
* [Tilbake vinkeltegn (RoomsBackNav)](#back-chevron) (kan ikke vises hvis leieren ikke har romlister)
* [Send ikon](#send-icon)

## <a name="prerequisite"></a>Forutsetning

Kjennskap til hvordan du legger til og konfigurerer skjermbilder og andre kontroller som du [oppretter en app i PowerApps](../data-platform-create-app-scratch.md).

## <a name="invite-tab"></a>Inviter fanen

   ![LblInviteTab control](media/meeting-screen/meeting-invite-text.png)

* Egenskap: **Farge**<br>
    Verdi: `If( _showDetails, LblRecipientCount.Color, RectQuickActionBar.Fill )`

    **_showDetails** er en variabel som brukes til å bestemme om den **LblInviteTab** kontroll eller **LblScheduleTab** kontroll er valgt. Hvis verdien for **_showDetails** er **SANN**, **LblScheduleTab** er merket; hvis verdien er **USANN**, **LblInviteTab**  er valgt. Det betyr at hvis verdien for **_showDetails** er **SANN** (denne kategorien *er ikke* valgte), samsvarer med kategorien fargen som **LblRecipientCount**. Hvis ikke, den samsvarer med verdien fyll for **RectQuickActionBar**.

* Egenskap: **OnSelect**<br> 
    Verdi: `Set( _showDetails, false )`

    Sett den **_showDetails** variabel som skal **USANN**, noe som betyr at innholdet i kategorien invitasjon er synlige, og innholdet i den **tidsplan** kategorien er skjult.

## <a name="schedule-tab"></a>Kategorien tidsplan

   ![LblInviteTab control](media/meeting-screen/meeting-schedule-text.png)

* Egenskap: **Farge**<br>
    Verdi: `If( !_showDetails, LblRecipientCount.Color, RectQuickActionBar.Fill )`

    **_showDetails** er en variabel som brukes til å bestemme om den **LblInviteTab** kontroll eller **LblScheduleTab** kontroll er valgt. Hvis den er SANN, **LblScheduleTab** er valgt; Hvis USANN, **LblInviteTab** er. Dette betyr at hvis **_showDetails** er SANN (denne kategorien *er* valgte), fanen fargen samsvarer med verdien fyll for **RectQuickActionBar**. Hvis ikke, den samsvarer med fargeverdien til **LblRecipientCount**.

* Egenskap: **OnSelect**<br>
    Verdi: `Set( _showDetails, true )`

    Sett den **_showDetails** variabel som skal **SANN**, noe som betyr at innholdet i kategorien tidsplan er synlige, og innholdet i kategorien invitasjon er skjult.

## <a name="text-search-box"></a>Boks for tekstsøk

   ![TextSearchBox kontroll](media/meeting-screen/meeting-search-box.png)

<!--Include description of text search box control?-->

Flere andre kontroller i skjermen har en avhengighet på denne:

* Hvis en bruker starter å skrive inn tekst, **PeopleBrowseGallery** blir synlig.
* Hvis en bruker skriver inn en gyldig e-postadresse, **AddIcon** blir synlig.
* Når en bruker velger en person i **PeopleBrowseGallery** Søk innholdet tilbakestilles.

## <a name="add-icon"></a>Legg til-ikon

   ![AddIcon kontroll](media/email-screen/email-add-icon.png)

Denne kontrollen kan brukere til å legge til personer som ikke finnes i deres organisasjon til deltakerlisten for møtet skrevet.

* Egenskap: **Synlig**<br>
    Verdi: Tre logiske kontrollerer at alle må evalueres som **SANN** for kontrollen skal vises:

    ```powerapps-dot
    !IsBlank( TextSearchBox.Text ) &&
        IsMatch( TextSearchBox.Text, Match.Email ) &&
        Not( Trim( TextSearchBox.Text ) in MyPeople.UserPrincipalName )
    ```

  Linje for linje, denne kodeblokk sier at den **AddIcon** kontrollen er synlig bare hvis:

  * Den **TextSearchBox** inneholder tekst.
  * Teksten i **TextSearchBox** er en gyldig e-postadresse.
  * Teksten i **TextSearchBox** ikke allerede finnes i den **MyPeople** samling.

* Egenskap: **OnSelect**<br> 
    Verdi: A **samle inn** -setningen for å legge til brukeren til deltageren liste, en annen for å oppdatere tilgjengelige møtetidspunkter og flere variable veksler:

    ```powerapps-dot
    Collect( MyPeople,
        { 
            DisplayName: TextSearchBox.Text, 
            UserPrincipalName: TextSearchBox.Text, 
            Mail: TextSearchBox.Text
        }
    );
    Concurrent(
        Reset( TextSearchBox ),
        Set( _showMeetingTimes, false ),
        UpdateContext( { _loadMeetingTimes: true } ),
        Set( _selectedMeetingTime, Blank() ),
        Set( _selectedRoom, Blank() ),
        Set( _roomListSelected, false ),
        ClearCollect( MeetingTimes, 
            AddColumns(
                'Office365'.FindMeetingTimes(
                    { 
                        RequiredAttendees: Concat(MyPeople, UserPrincipalName & ";")
                        MeetingDuration: MeetingDurationSelect.Selected.Minutes,
                        Start: Text( DateAdd( MeetingDateSelect.SelectedDate, 8, Hours ), UTC ),
                        End: Text( DateAdd( MeetingDateSelect.SelectedDate, 17, Hours ), UTC ),
                        MaxCandidates: 15, 
                        MinimumAttendeePercentage:1, 
                        IsOrganizerOptional: false, 
                        ActivityDomain: "Work"
                    }
                ).MeetingTimeSuggestions,
                "StartTime", MeetingTimeSlot.Start.DateTime, 
                "EndTime", MeetingTimeSlot.End.DateTime
            )
        )
    );
    UpdateContext( { _loadingMeetingTimes: false } );
    Set( _showMeetingTimes, true )
    ```

  Å velge denne kontrollen legger til gyldige e-postadressen (vises bare hvis en gyldig e-postadresse er skrevet inn i **TextSearchBox**) til den **MyPeople** samling (denne samlingen er listen over deltakere) og deretter Oppdaterer de tilgjengelige møtetidspunktene med den nye oppføringen for brukeren.

  På et lavt nivå, denne kodeblokk:
  1. Samler inn e-postadressen til den **MyPeople** samling, samler inn e-postadressen til den **DisplayName**, **UserPrincipalName**, og **e-post**  felt.
  1. Tilbakestiller innholdet i den **TextSearchBox** kontroll.
  1. Sett den **_showMeetingTimes** variabel som skal **USANN**. Denne variabelen kontrollerer synligheten til **FindMeetingTimesGallery**, som viser åpne ganger for valgte deltakerne for å oppfylle.
  1. Sett den **_loadMeetingTimes** kontekstvariabel til **SANN**. Denne variabelen angir en tilstand for innlasting, som aktiverer/deaktiverer synligheten for innlasting av tilstand kontroller for eksempel **_LblTimesEmptyState** å fortelle brukeren at dataene blir lastet inn.
  1. Sett **_selectedMeetingTime** til **Blank()**. **_selectedMeetingTime** er den valgte posten fra den **FindMeetingTimesGallery** kontroll. Det er blanked her fordi tillegg av en annen deltaker kan bety som tidligere definisjonen av **_selectedMeetingTime** er ikke tilgjengelig for den aktuelle deltakeren.
  1. Sett **_selectedRoom** til **Blank()**. **_selectedRoom** er valgte plass posten fra **RoomBrowseGallery**. ROM-tilgjengelighet fastsettes fra verdien til **_selectedMeetingTime**. Med den verdien blanked, den **_selectedRoom** verdien er ikke lenger gyldig, slik at den må være blanked.
  1. Sett **_roomListSelected** til **USANN**. Denne linjen kanskje gjelder ikke tilgjengelig for alle. I Office, kan du gruppere din ROM av ulike «alle ROM lister.» Hvis du har romlister, kontoer for denne skjermen for denne, slik at du først å velge en romliste før du velger et ROM fra i listen. Verdien for **_roomListSelected** bestemmer om en bruker (i en leier med bare romlister) skal vise ROM i en romliste eller settet med romlister. Det er satt til **USANN** tvinge brukere til å velge en ny romliste på nytt.
  1. Bruker den [Office365.FindMeetingTimes](https://docs.microsoft.com/connectors/office365/#find-meeting-times) operasjonen til å finne og samle inn de tilgjengelige møtetidspunktene for deltakere. Denne operasjonen sender:
      * Den **UserPrincipalName** til de valgte brukerne i den *RequiredAttendees* parameteren.
      * **MeetingDurationSelect**. Selected.Minutes i den *MeetingDuration* parameteren.
      * MeetingDateSelect.SelectedDate + 8 timer i den *Start* parameteren. Åtte timer er lagt til fordi det full dato/klokkeslettet for Kalender-kontrollen er som standard 12:00 AM av den valgte datoen. Du vil sannsynligvis hente tilgjengelighet i vanlig arbeidstid. Et vanlig arbeid starttidspunkt ville være 08:00:00.
      * **MeetingDateSelect**. SelectedDate + 17 timer i den *slutten* parameteren. 17 timer legges til fordi 12:00:00 + 17 = 5:00 PM. En vanlig arbeid sluttidspunkt er 5:00 PM.
      * *15* i den *MaxCandidates* parameteren. Dette betyr at operasjonen returnerer bare toppen 15 tilgjengelige tidspunkter for den valgte datoen. Dette gir mening fordi det er bare seksten 30 minutters deler i en 8-timers arbeidsdag, og en 30 minutters møte er minst ett kan angi i dette skjermbildet.
      * *1* i den *MinimumAttendeePercentage* parameteren. Med mindre det finnes ingen deltakere, hentes i hovedsak tid.
      * **USANN** i den *IsOrganizerOptional* parameteren. Appbrukeren er ikke en valgfri deltaker for dette møtet.
      * «Fungerer» i den *ActivityDomain* parameteren. Dette betyr at tidene hentet er bare de i en vanlig arbeidstid periode.
  1. Den **ClearCollect** funksjonen legger også til to kolonner: «StartTime» og «Sluttid». Dette forenkler dataene som returneres. 
  Feltet som inneholder den tilgjengelige start og slutt er den **MeetingTimeSlot** felt. Dette feltet er en post som inneholder starten og slutten poster, hvilke seg selv, inneholder den **DateTime** og **tidssone** verdiene til deres respektive forslag. I stedet for forsøk på å hente denne nesting av poster, å legge til kolonnene «StartTime» og «Sluttid» til den **MeetingTimes** samling bringer de **Start > DateTime** og **slutten > DateTime** verdier på overflaten på samlingen.
  1. Når disse funksjonene har alle fullført, den **_loadingMeetingTimes** variabelen er satt til **USANN**, fjerner tilstand for innlasting, og **_showMeetingTimes** er satt til **SANN**, displaying **FindMeetingTimesGallery**.

## <a name="people-browse-gallery"></a>Personer Bla gjennom-galleriet

   ![PeopleBrowseGallery kontroll](media/meeting-screen/meeting-browse-gall.png)

* Egenskap: **Elementer**<br>
    Verdi: 
    ```powerapps-dot
    If( !IsBlank( Trim( TextSearchBox.Text ) ), 
        'Office365Users'.SearchUser( { searchTerm: Trim(TextSearchBox.Text), top: 15 } )
    )
    ```

Elementene i dette galleriet fylles som søkeresultater fra den [Office365.SearchUser](https://docs.microsoft.com/connectors/office365users/#searchuser) operasjonen. Operasjonen tar teksten `Trim(**TextSearchBox**)` som søket term og returnerer resultatene topp 15 som er basert på dette søket.
  
**TextSearchBox** er pakket i en **Trim** fungere fordi et bruker-Søk etter mellomrom er ikke gyldig. Den `Office365Users.SearchUser` operasjonen er pakket i en `If(!IsBlank(Trim(TextSearchBox.Text)) ... )` fungere fordi henting av søkeresultater før en bruker har søkt er sløsing ytelse.

### <a name="people-browse-gallery-title"></a>Personer Bla gjennom-galleriet tittel

   ![PeopleBrowseGallery tittel kontroll](media/meeting-screen/meeting-browse-gall-title.png)

* Egenskap: **Tekst**<br>
    Verdi: `ThisItem.DisplayName`

    Viser personens visningsnavn fra deres Office 365-profilen.

* Egenskap: **OnSelect**<br>
    Verdi: A **samle inn** -setningen for å legge til brukeren til deltageren liste, en annen for å oppdatere tilgjengelige møtetidspunkter og flere variable veksler:

    ```powerapps-dot
    Concurrent(
        Reset( TextSearchBox ),
        Set( _selectedUser, ThisItem ),
        If( Not( ThisItem.UserPrincipalName in MyPeople.UserPrincipalName ), 
            Collect( MyPeople, ThisItem ); 
            Concurrent(
                Set( _showMeetingTimes, false ),
                UpdateContext( { _loadMeetingTimes: true } ),
                Set( _selectedMeetingTime, Blank() ),
                Set( _selectedRoom, Blank() ),
                Set( _roomListSelected, false ),
                ClearCollect( MeetingTimes, 
                    AddColumns(
                        'Office365'.FindMeetingTimes(
                            {
                                RequiredAttendees: Concat( MyPeople, UserPrincipalName & ";" ),
                                MeetingDuration: MeetingDurationSelect.Selected.Minutes,
                                Start: Text( DateAdd( MeetingDateSelect.SelectedDate, 8, Hours ), UTC ),
                                End: Text( DateAdd( MeetingDateSelect.SelectedDate, 17, Hours ), UTC ),
                                MaxCandidates: 15, 
                                MinimumAttendeePercentage: 1, 
                                IsOrganizerOptional: false, 
                                ActivityDomain: "Work"
                            }
                        ).MeetingTimeSuggestions,
                        "StartTime", MeetingTimeSlot.Start.DateTime, 
                        "EndTime", MeetingTimeSlot.End.DateTime
                    )
                )
            );
            UpdateContext( { _loadingMeetingTimes: false } );
            Set( _showMeetingTimes, true )
        )
    )
    ```

    På et høyt nivå, hvis du velger denne kontrollen legger til personen til den **MyPeople** samling (appens lagring av listen over deltakere), og oppdaterer de tilgjengelige møtetidspunktene basert på det nye bruker-tillegget.

    Å velge denne kontrollen er veldig lik å velge den **AddIcon** kontroll; den eneste forskjellen er at den `Set(_selectedUser, ThisItem)` setningen og kjøring av rekkefølgen av operasjonene. Denne diskusjonen vil følgelig ikke like dype. For en mer utfyllende forklaring, kan du lese gjennom den [AddIcon kontrollen](#add-icon) delen.

    Å velge denne kontrollen tilbakestiller **TextSearchBox**. Hvis det merkede området ikke er i den **MyPeople** samling, kontrollen:
    1. Sett den **_loadMeetingTimes** tilstand til **SANN** og **_showMeetingTimes** tilstand til **USANN**, tomme celler i **_ selectedMeetingTime** og **_selectedRoom** variabler og oppdateringer av **MeetingTimes** samling med det nye tillegget til den **MyPeople** samling. 
    1. Angir den **_loadMeetingTimes** tilstand til **USANN**, og angir **_showMeetingTimes** til **SANN**. Hvis det merkede området er allerede i den **MyPeople** samling, tilbakestilles bare innholdet i **TextSearchBox**.

## <a name="meeting-people-gallery"></a>Møte personer galleri

   ![MeetingPeopleGallery kontroll](media/meeting-screen/meeting-people-gall.png)

* Egenskap: **Elementer**<br>
    Verdi: `MyPeople`

    Den **MyPeople** samlingen er samlingen av personer initialisert eller legges til ved å velge den **PeopleBrowseGallery tittel** kontroll.

* Egenskap: **Høyde**<br>
    Verdi: Logikk for å tillate galleriet skal vokse til en maksimal høyde på 350:

    ```powerapps-dot
    Min( 
        76 * RoundUp( CountRows( MeetingPeopleGallery.AllItems ) / 2, 0 ),
        350
    )
    ```

  
   Høyden på dette galleriet Justerer hvor mange elementer i galleriet, til en maksimal høyde på 350. Formelen tar 76 som høyden på en enkelt rad med **MeetingPeopleGallery**, deretter multipliserer verdien med antall rader. Den **WrapCount** egenskapen er satt til 2, så er antall rader som SANN `RoundUp(CountRows(MeetingPeopleGallery.AllItems) / 2, 0)`.

* Egenskap: **ShowScrollbar**<br>
    Verdi: `MeetingPeopleGallery.Height >= 350`

    Når den maksimale høyden på galleriet er nådd (350), er rullefeltet synlig.

### <a name="meeting-people-gallery-title"></a>Møte personer galleriet tittel

   ![MeetingPeopleGallery tittel kontroll](media/meeting-screen/meeting-people-gall-title.png)

* Egenskap: **OnSelect**<br>
    
    Verdi: `Set(_selectedUser, ThisItem)`
    
    Sett den **_selectedUser** variabel som skal det valgte elementet i **MeetingPeopleGallery**.

### <a name="meeting-people-gallery-iconremove"></a>Møte personer galleriet iconRemove

   ![MeetingPeopleGallery iconRemove kontroll](media/meeting-screen/meeting-people-gall-delete.png)

* Egenskap: **OnSelect**<br>
    Verdi: A **fjerne** -setningen for å fjerne brukeren fra listen over deltakere en **samle inn** -setningen for å oppdatere tilgjengelige møtetidspunkter og flere variable veksler:

    ```powerapps-dot
    Remove( MyPeople, LookUp( MyPeople, UserPrincipalName = ThisItem.UserPrincipalName ) );
    Concurrent(
        Reset( TextSearchBox ),
        Set( _showMeetingTimes, false ),
        UpdateContext( { _loadMeetingTimes: true } ),
        Set( _selectedMeetingTime, Blank() ),
        Set( _selectedRoom, Blank() ),
        Set( _roomListSelected, false ),
        ClearCollect( MeetingTimes, 
            AddColumns(
                'Office365'.FindMeetingTimes(
                    {
                        RequiredAttendees: Concat( MyPeople, UserPrincipalName & ";" ), 
                        MeetingDuration: MeetingDurationSelect.Selected.Minutes,
                        Start: Text( DateAdd( MeetingDateSelect.SelectedDate, 8, Hours ), UTC ), 
                        End: Text( DateAdd( MeetingDateSelect.SelectedDate, 17, Hours ), UTC ),
                        MaxCandidates: 15, 
                        MinimumAttendeePercentage: 1, 
                        IsOrganizerOptional: false, 
                        ActivityDomain: "Work"
                    }
                ).MeetingTimeSuggestions,
                "StartTime", MeetingTimeSlot.Start.DateTime, 
                "EndTime", MeetingTimeSlot.End.DateTime
            )
        )
    );
    UpdateContext( { _loadingMeetingTimes: false } );
    Set( _showMeetingTimes, true )
    ```

  På et høyt nivå, hvis du velger denne kontrollen fjerner personen fra listen over deltakere og oppdaterer de tilgjengelige møtetidspunktene basert på fjerning av denne personen.

  Etter den første linjen i foregående kode, hvis du velger denne kontrollen er nesten identisk til å velge den **AddIcon** kontroll. Følgelig vil ikke denne diskusjonen være like dype. For en mer utfyllende forklaring, kan du lese gjennom den [AddIcon control-delen](#add-icon).

  Den første linje i koden, fjernes det valgte elementet fra den **MyPeople** samling. Koden deretter:
  1. Tilbakestiller **TextSearchBox**, og deretter fjerner det merkede området fra den **MyPeople** samling. 
  1. Sett den **_loadMeetingTimes** tilstand til **SANN** og **_showMeetingTimes** tilstand til **USANN**, tomme celler i **_ selectedMeetingTime** og **_selectedRoom** variabler og oppdateringer av **MeetingTimes** samling med det nye tillegget til den **MyPeople** samling. 
  1. Angir den **_loadMeetingTimes** tilstand til **USANN**, og angir **_showMeetingTimes** til **SANN**.

## <a name="meeting-date-picker"></a>Møte datovelger

   ![MeetingDateSelect kontroll](media/meeting-screen/meeting-datepicker.png)

* Egenskap: **DisplayMode**<br>
    Verdi: `If( IsEmpty(MyPeople), DisplayMode.Disabled, DisplayMode.Edit )`

    En dato for et møte kan ikke velges til minst én deltaker har blitt lagt til den **MyPeople** samling.

* Egenskap: **OnChange**<br>
    Verdi: `Select( MeetingDateSelect )`

    Endre den valgte datoen utløser koden i det **OnSelect** for denne kontrollen til å kjøre.

* Egenskap: **OnSelect**<br>
    Verdi: A **samle inn** -setningen for å oppdatere tilgjengelige møtetidspunkter og flere variable veksler:
  
    ```powerapps-dot
    Concurrent(
        Reset( TextSearchBox ),
        Set( _showMeetingTimes, false ),
        UpdateContext( { _loadingMeetingTimes: true } ),
        Set( _selectedMeetingTime, Blank() ),
        Set( _selectedRoom, Blank() ),
        Set( _roomListSelected, false ),
        ClearCollect( MeetingTimes, 
            AddColumns(
                'Office365'.FindMeetingTimes(
                    {
                        RequiredAttendees: Concat( MyPeople, UserPrincipalName & ";" ), 
                        MeetingDuration: MeetingDurationSelect.Selected.Minutes,
                        Start: Text( DateAdd( MeetingDateSelect.SelectedDate, 8, Hours ), UTC ), 
                        End: Text( DateAdd( MeetingDateSelect.SelectedDate, 17, Hours ), UTC ),
                        MaxCandidates: 15, 
                        MinimumAttendeePercentage: 1, 
                        IsOrganizerOptional: false, 
                        ActivityDomain: "Work"
                    }
                ).MeetingTimeSuggestions,
                "StartTime", MeetingTimeSlot.Start.DateTime, 
                "EndTime", MeetingTimeSlot.End.DateTime
            )
        )
    );
    UpdateContext( { _loadingMeetingTimes: false } );
    Set( _showMeetingTimes, true )
    ```

  Oppdaterer de tilgjengelige møtetidspunktene på et høyt nivå, hvis du velger denne kontrollen. Det er viktig fordi Hvis en bruker endrer datoen, de tilgjengelige møtetidspunktene må du oppdatere for å gjenspeile de deltakere-tilgjengelighet for den aktuelle dagen.

  Med unntak av første **samle inn** -setningen, dette er identisk med den **OnSelect** funksjonaliteten til den **AddIcon** kontroll. Følgelig vil ikke denne diskusjonen være like dype. For en mer utfyllende forklaring, kan du lese gjennom den [AddIcon kontrollen](#add-icon) delen.

  Å velge denne kontrollen tilbakestiller **TextSearchBox**. Den deretter: 
  1. Sett den **_loadMeetingTimes** tilstand til **SANN** og **_showMeetingTimes** tilstand til **USANN**, tomme celler i **_ selectedMeetingTime** og **_selectedRoom** variabler og oppdateringer av **MeetingTimes** samling med det nye dato-området. 
  1. Angir den **_loadMeetingTimes** tilstand til **USANN**, og angir **_showMeetingTimes** til **SANN**.

## <a name="meeting-duration-drop-down"></a>Møtevarighet rullegardinlisten

   ![MeetingDateSelect kontroll](media/meeting-screen/meeting-timepicker.png)

* Egenskap: **DisplayMode**<br>
    Verdi: `If( IsEmpty(MyPeople), DisplayMode.Disabled, DisplayMode.Edit )`

    En varighet for et møte kan ikke velges til minst én deltaker har blitt lagt til den **MyPeople** samling.

* Egenskap: **OnChange**<br>
    Verdi: `Select(MeetingDateSelect1)`

    Endret valgte varigheten utløser koden i det **OnSelect** -egenskapen for den **MeetingDateSelect** kontroll for å kjøre.

## <a name="find-meeting-times-gallery"></a>Finn møtetidspunkter galleri

   ![FindMeetingTimesGallery kontroll](media/meeting-screen/meeting-time-gall.png)

* Egenskap: **Elementer**<br>
    Verdi: `MeetingTimes`

    Samlingen av potensielle møtetidspunkter hentet fra den [Office365.FindMeetingTimes](https://docs.microsoft.com/connectors/office365/#find-meeting-times) operasjonen.

* Egenskap: **Synlig**<br>
    Verdi: `_showMeetingTimes && _showDetails && !IsEmpty( MyPeople )`

    Galleriet er synlig bare hvis **_showMeetingTimes** er satt til **SANN**, brukeren har valgt den **LblScheduleTab** kontroll, og det finnes minst én deltaker lagt til den møte.

### <a name="find-meeting-times-gallery-title"></a>Finn møtetidspunkter galleriet tittel

   ![FindMeetingTimesGallery tittel kontroll](media/meeting-screen/meeting-time-gall-title.png)

* Egenskap: **Tekst**<br>
    Verdi: En konvertering av starttidspunktet som skal vises i brukerens lokaltid:

    ```powerapps-dot
    Text(
        DateAdd(
            DateTimeValue( ThisItem.StartTime ),
            - TimeZoneOffset(), 
            Minutes
        ),
        DateTimeFormat.ShortTime
    )
    ```

  De hentede verdien for **StartTime** er i UTC-format. Til [konverteres UTC til lokaltid](../functions/function-dateadd-datediff.md#converting-from-utc), **DateAdd** funksjonen brukes.
  Den [tekst-funksjonen](../functions/function-text.md#datetime) tar en dato/klokkeslett som den første argument, og formater den basert på det andre argumentet. Du sender den til lokal tidskonvertering av **ThisItem.StartTime**, og Vis det som **DateTimeFormat.ShortTime**.

* Egenskap: **OnSelect**<br>
    Verdi: Flere **samle inn** setninger til å samle møterom og deres foreslåtte-tilgjengelighet, i tillegg til flere variable veksler:

    ```powerapps-dot
    Set( _selectedMeetingTime, ThisItem );
    UpdateContext( { _loadingRooms: true } );
    If( IsEmpty( RoomsLists ),
        ClearCollect( RoomsLists, 'Office365'.GetRoomLists().value) );
    If( CountRows( RoomsLists ) <= 1,
        Set( _noRoomLists, true );
        ClearCollect( AllRooms, 'Office365'.GetRooms().value );
        Set( _allRoomsConcat, Concat( FirstN( AllRooms, 20 ), Address & ";" ) );
        ClearCollect( RoomTimeSuggestions, 
            'Office365'.FindMeetingTimes(
                {
                    RequiredAttendees: _allRoomsConcat, 
                    MeetingDuration: MeetingDurationSelect.Selected.Minutes,
                    Start: _selectedMeetingTime.StartTime & "Z", 
                    End: _selectedMeetingTime.EndTime & "Z", 
                    MinimumAttendeePercentage: "1",
                    IsOrganizerOptional: "false", 
                    ActivityDomain: "Unrestricted"
                }
            ).MeetingTimeSuggestions
        );
        ClearCollect( AvailableRooms, 
            AddColumns(
                AddColumns(
                    Filter( 
                        First( RoomTimeSuggestions ).AttendeeAvailability,
                        Availability="Free"
                    ), 
                    "Address", Attendee.EmailAddress.Address
                ), 
                "Name", LookUp( AllRooms, Address = Attendee.EmailAddress.Address ).Name 
            )
        );
        ClearCollect( AvailableRoomsOptimal, 
            DropColumns(
                DropColumns( AvailableRooms, "Availability" ), 
                "Attendee" 
            )
        ),
        Set( _roomListSelected, false) 
    );
    UpdateContext( {_loadingRooms: false} )
    ```

  På et høyt nivå, denne kodeblokk samler tilgjengelige ROM for brukere som ikke har ROM lister, basert på det valgte dato/klokkeslettet for møtet. Hvis ikke, henter det ganske enkelt listene ROM.

  På et lavt nivå, denne kodeblokk:
  1. Sett **_selectedMeetingTime** til det valgte elementet. Dette brukes til å finne hvilke ROM er tilgjengelige i den perioden.
  1. Angir innlasting tilstand variabel **_loadingRooms** til **SANN**, aktivere tilstand for innlasting.
  1. Hvis den **RoomsLists** samlingen er tom, henter brukerens leier romlister, og lagrer dem i den **RoomsLists** samling.
  1. Hvis brukeren har ingen romliste eller én romliste:
      1. Den **noRoomLists** variabelen er satt til **SANN**, og denne variabelen brukes til å fastslå hvilke elementer som vises i den **RoomBrowseGallery** kontroll.
      1. Den `Office365.GetRooms()` operasjonen brukes til å hente de første 100 ROM i leieren. Disse er lagret i den **AllRooms** samling.
      1. Den **_allRoomsConcat** variabelen er satt til en adskilt med semikolon streng med de første 20 e-postadressene til ROM i den **AllRooms** samling. Dette er fordi den [Office365.FindMeetingTimes](https://docs.microsoft.com/connectors/office365/#find-meeting-times) er begrenset til å søke etter de tilgjengelige tidspunktene av 20 personobjekter i én enkelt operasjon.
      1. Den **RoomTimeSuggestions** samling bruker den [Office365.FindMeetingTimes](https://docs.microsoft.com/connectors/office365/#find-meeting-times) hente tilgjengelighet i de første 20 ROM i den **AllRooms** samling, basert på tidsverdier fra den **_selectedMeetingTime** variabel. Vær oppmerksom på at den `& "Z"` brukes til å formatere riktig den **DateTime** verdi.
      1. Den **AvailableRooms** samlingen er opprettet. Dette er ganske enkelt den **RoomTimeSuggestions** samling av deltaker tilgjengelighet med to ekstra kolonner som er lagt til: "Adresse" og "Name". "Adresse" er e-postadressen til rommet, og "Name" er navnet på rommet.
      1. Deretter, den **AvailableRoomsOptimal** samlingen er opprettet. Dette er bare den **AvailableRooms** samling med kolonnene «Tilgjengelig» og «Deltakere» fjernet. Hvis du gjør dette samsvarer med skjemaene i **AvailableRoomsOptimal** og **AllRooms**. Dette gjør det mulig å bruke begge samlingene i den **elementer** -egenskapen for den **RoomBrowseGallery**.
      1. **_roomListSelected** er satt til **USANN**.
  1. Tilstand for innlasting, **_loadingRooms**, er satt til **USANN** når alt annet er ferdig med å kjøre.

## <a name="room-browse-gallery"></a>Plass Bla gjennom-galleriet

   ![RoomBrowseGallery kontroll](media/meeting-screen/meeting-rooms-gall.png)

* Egenskap: **Elementer**<br>
    Verdi: Logisk satt til to intern samlinger med identiske skjema, avhengig av om brukeren har valgt en romliste eller har romlister i leieren:

    ```powerapps-dot
    Search(
        If( _roomListSelected || _noRoomLists, AvailableRoomsOptimal, RoomsLists ),
        Trim(TextMeetingLocation1.Text), 
        "Name", 
        "Address"
    )
    ```

  Dette galleriet viser den **AvailableRoomsOptimal** samling Hvis **_roomListSelected** eller **_noRoomLists** er **SANN**. Ellers vises den **RoomsLists** samling. Dette kan gjøres fordi skjemaet for disse samlingene er identiske.

* Egenskap: **Synlig**<br>
    Verdi: ```_showDetails && !IsBlank( _selectedMeetingTime ) && !_loadingRooms```

    Galleriet er bare synlig hvis de tre foregående setningene evalueres til **SANN**.

### <a name="roombrowsegallery-title"></a>RoomBrowseGallery tittel

   ![RoomBrowseGallery tittel kontroll](media/meeting-screen/meeting-rooms-gall-title.png)

* Egenskap: **OnSelect**<br>
    Verdi: Et sett med logisk bundne **samle inn** og **angi** utdrag, som kan eller kan ikke utløses, avhengig av om brukeren er viser romlister eller ROM:

    ```powerapps-dot
    UpdateContext( { _loadingRooms: true } );
    If( !_roomListSelected && !noRoomLists,
        Set( _roomListSelected, true );
        Set( _selectedRoomList, ThisItem.Name );
        ClearCollect( AllRooms, 'Office365'.GetRoomsInRoomList( ThisItem.Address ).value );
        Set( _allRoomsConcat, Concat( FirstN( AllRooms, 20 ), Address & ";" ) );
        ClearCollect( RoomTimeSuggestions, 
            'Office365'.FindMeetingTimes(
                {
                    RequiredAttendees: _allRoomsConcat, 
                    MeetingDuration: MeetingDurationSelect.Selected.Minutes,
                        Start: _selectedMeetingTime.StartTime & "Z", 
                    End: _selectedMeetingTime.EndTime & "Z", 
                    MinimumAttendeePercentage: "1",
                    IsOrganizerOptional: "false", 
                    ActivityDomain: "Unrestricted"
                }
            ).MeetingTimeSuggestions
        );
        ClearCollect( AvailableRooms, 
            AddColumns(
                AddColumns(
                    Filter(
                        First( RoomTimeSuggestions ).AttendeeAvailability, 
                        Availability = "Free"
                    ),
                    "Address", Attendee.EmailAddress.Address 
                ), 
                "Name", LookUp( AllRooms, Address = Attendee.EmailAddress.Address ).Name
            )
        );
        ClearCollect( AvailableRoomsOptimal, 
            DropColumns(
                DropColumns( AvailableRooms, "Availability" )
            ), 
            "Attendee" )
        ),
        Set( _selectedRoom, ThisItem )
    );
    UpdateContext( {_loadingRooms: false} )
    ```

  Handlingene som forekommer når denne kontrollen er valgt, avhenger av om en bruker er for øyeblikket viser et sett med romlister eller et sett med ROM. Hvis det er den tidligere, og deretter velge denne kontrollen henter ROM som er tilgjengelige på angitt tidspunkt fra listen over valgte plass. Hvis det er det siste, hvis du velger denne kontrollen settes den **_selectedRoom** variabel til det valgte elementet. Den foregående setningen er veldig lik den **Velg** -setning for [ **FindMeetingTimesGallery tittel**](#find-meeting-times-gallery).

  På et lavt nivå, den foregående kodeblokk:
  1. Aktiverer lasting av tilstanden for ROM ved å angi **_loadingRooms** til **SANN**.
  1. Kontrollerer om en romliste er valgt, og hvis leieren har plass viser. Fall i så:
      1. Angir **_roomListSelected** til **SANN** og angir **_selectedRoomList** til det valgte elementet.
      1. Den **_allRoomsConcat** variabelen er satt til en adskilt med semikolon streng med de første 20 e-postadressene til ROM i den **AllRooms** samling. Dette er fordi den [Office365.FindMeetingTimes](https://docs.microsoft.com/connectors/office365/#find-meeting-times) operasjonen er begrenset til å søke etter de tilgjengelige tidspunktene av 20 personobjekter i én enkelt operasjon.
      1. Den **RoomTimeSuggestions** samling bruker den [Office365.FindMeetingTimes](https://docs.microsoft.com/connectors/office365/#find-meeting-times) operasjonen til å hente tilgjengelighet i de første 20 ROM i den **AllRooms** samling, basert på klokkeslett-verdiene fra den **_selectedMeetingTime** variabel. Legg merke til at `& "Z"` brukes til å formatere riktig den **DateTime** verdi.
      1. Den **AvailableRooms** samlingen er opprettet. Dette er ganske enkelt den **RoomTimeSuggestions** samling av deltaker tilgjengelighet med to ekstra kolonner som er lagt til: "Adresse" og "Name". "Adresse" er e-postadressen til rommet, og "Name" er navnet på rommet.
      1. Deretter, den **AvailableRoomsOptimal** samlingen er opprettet. Dette er bare den **AvailableRooms** samling med kolonnene «Tilgjengelig» og «Deltakere» fjernet. Hvis du gjør dette samsvarer med skjemaene i **AvailableRoomsOptimal** og **AllRooms**. Dette gjør det mulig å bruke begge samlingene i den **elementer** -egenskapen for **RoomBrowseGallery**.
      1. **_roomListSelected** er satt til **USANN**.
  1. Tilstand for innlasting, **_loadingRooms**, er satt til **USANN** når alt annet er ferdig med å kjøre.

## <a name="back-chevron"></a>Ta en vinkel

   ![RoomsBackNav kontroll](media/meeting-screen/meeting-back.png)

* Egenskap: **Synlig**<br>
    Verdi: `_roomListSelected && _showDetails`

    Denne kontrollen er synlig bare hvis begge en romliste er valgt og **tidsplan** fanen er valgt.

* Egenskap: **OnSelect**<br>
    Verdi: `Set( _roomListSelected, false )`

    Når **_roomListSelected** er satt til **USANN**, endres den **RoomBrowseGallery** kontroll til å vise elementer fra den **RoomsLists** samling.

## <a name="send-icon"></a>Send ikon

   ![IconSendItem kontroll](media/meeting-screen/meeting-send-icon.png)

* Egenskap: **DisplayMode**<br>
    Verdi: Logikk for å tvinge brukeren til å skrive inn noen opplysninger møte før ikonet redigeres.
    
    ```powerapps-dot
    If( Len( Trim( TextMeetingSubject1.Text ) ) > 0
        && !IsEmpty( MyPeople ) && !IsBlank( _selectedMeetingTime ),
        DisplayMode.Edit, DisplayMode.Disabled
    )
    ```
  Ikonet er valgbar bare hvis emnet for møte er fylt, det finnes minst én deltaker for møtet, og et møtetidspunkt er valgt. Hvis ikke, den er deaktivert.

* Egenskap: **OnSelect**<br>

    Verdi: Kode for å sende møteinvitasjonen valgte deltakere og Fjern alle inndatafeltene:

    ```powerapps-dot
    Set( _myCalendarName, LookUp( 'Office365'.CalendarGetTables().value, DisplayName = "Calendar" ).Name );
    Set( _myScheduledMeeting, 
        'Office365'.V2CalendarPostItem( _myCalendarName,
            TextMeetingSubject1.Text, 
            Text(DateAdd(DateTimeValue( _selectedMeetingTime.StartTime), -TimeZoneOffset(), Minutes) ),
            Text(DateAdd(DateTimeValue( _selectedMeetingTime.EndTime), -TimeZoneOffset(), Minutes) ),
            {
                RequiredAttendees: Concat( MyPeople, UserPrincipalName & ";" ) & _selectedRoom.Address, 
                Body: TextMeetingMessage1.Text, 
                Location: _selectedRoom.Name, 
                Importance: "Normal", 
                ShowAs: "Busy", 
                ResponseRequested: true
            }
        )
    );
    Concurrent(
        Reset( TextMeetingLocation1 ),
        Reset( TextMeetingSubject1 ),
        Reset( TextMeetingMessage1 ),
        Clear( MyPeople ),
        Set( _selectedMeetingTime, Blank() ),
        Set( _selectedRoomList, Blank() ),
        Set( _selectedRoom, Blank() ),
        Set( _roomListSelected, false )
    )
    ```
  
  På et lavt nivå, denne kodeblokk:
  1. Sett **_myCalendarName** i kalenderen i den [Office365.CalendarGetTables()](https://docs.microsoft.com/connectors/office365/#get-calendars) operasjonen med en **DisplayName** av "Kalender".
  1. Tidsplaner møtet med alle inndataene verdier fra ulike valgene brukeren har gjort i hele skjermen ved hjelp av den [Office365.V2CalendarPostItem](https://docs.microsoft.com/connectors/office365/#create-event--v2-) operasjonen.
  1. Tilbakestiller alle inndatafeltene og variabler som brukes for å opprette møtet.

> [!NOTE]
> Avhengig av ditt område kanskje i kalenderen du vil ikke et visningsnavn for "Kalender". Gå til Outlook for å se hva som tittelen på kalenderen er, og gjøre riktige endringen i appen.

## <a name="next-steps"></a>Neste trinn

* [Finn ut mer om denne skjermen](./meeting-screen-overview.md)
* [Finn ut mer om Office 365 Outlook connector i PowerApps](../connections/connection-office365-outlook.md)
* [Finn ut mer om Office 365-brukere-kobling i PowerApps](../connections/connection-office365-users.md)
