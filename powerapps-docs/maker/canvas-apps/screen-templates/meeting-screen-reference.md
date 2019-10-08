---
title: Referanse til malen for møte skjermen for lerret apper | Microsoft Docs
description: Få informasjon om hvordan malen for møte skjermen for lerret apper fungerer i PowerApps
author: emcoope-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 01/03/2019
ms.author: emcoope
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: c62c3de56534201a81e9f4d453796ebd9b3a0366
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/07/2019
ms.locfileid: "71989564"
ms.PowerAppsDecimalTransform: true
---
# <a name="reference-information-about-the-meeting-screen-template-for-canvas-apps"></a>Referanse informasjon om malen for møte skjermen for lerret apper

For å få en lerret-app i PowerApps kan du forstå hvordan hver omfattende kontroll i malen for møte skjermen bidrar til skjermens generelle standard funksjon. Denne dype forhandlingen presenterer virke måte formlene og verdiene til andre egenskaper som bestemmer hvordan kontrollene svarer på bruker inn data. Hvis du vil ha en høy nivå diskusjon av denne skjermens standard funksjon, kan du se [Oversikt over møte skjermen](meeting-screen-overview.md).

Dette emnet uthever noen viktige kontroller og forklarer uttrykkene eller formlene som ulike egenskaper (for eksempel **elementer** og **OnSelect**) til disse kontrollene er angitt for:

* [Invitasjons fane (LblInviteTab)](#invite-tab)
* [Plan-fanen (LblScheduleTab)](#schedule-tab)
* [Tekst søkeboks](#text-search-box)
* [Legg til ikon (AddIcon)](#add-icon)
* [Person søk Galleri](#people-browse-gallery) (+ underordnede kontroller)
* [Møte person Galleri](#meeting-people-gallery) (+ underordnede kontroller)
* [Dato velger for møte (MeetingDateSelect)](#meeting-date-picker)
* [Rulle gardin listen for møte varigheten (MeetingDurationSelect)](#meeting-duration-drop-down)
* [Finn møte tids Galleri](#find-meeting-times-gallery) (+ underordnede kontroller)
* [Galleri for rom visning](#room-browse-gallery) (+ underordnede kontroller)
* [Vinkel tegn bakover (RoomsBackNav)](#back-chevron) (kan ikke være synlig hvis leieren ikke har rom lister)
* [Send-ikon](#send-icon)

## <a name="prerequisite"></a>Nødvendig

Kjennskap til hvordan du legger til og konfigurerer skjermer og andre kontroller mens du [oppretter en app i powerapps](../data-platform-create-app-scratch.md).

## <a name="invite-tab"></a>Invitasjons fane

   ![LblInviteTab-kontroll](media/meeting-screen/meeting-invite-text.png)

* Gjelder **Farge**<br>
    Verdi: `If( _showDetails; LblRecipientCount.Color; RectQuickActionBar.Fill )`

    **_showDetails** er en variabel som brukes til å fastslå om **LblInviteTab** -kontrollen eller **LblScheduleTab** -kontrollen er valgt. Hvis verdien for **_showDetails** er **True**, er **LblScheduleTab** valgt. Hvis verdien er **Usann**, er **LblInviteTab** valgt. Dette betyr at hvis verdien for **_showDetails** er **sann** (denne kategorien *ikke* er valgt), Sams varer kategori fargen med **LblRecipientCount**. Ellers Sams varer den med fyll verdien til **RectQuickActionBar**.

* Gjelder **OnSelect**<br> 
    Verdi: `Set( _showDetails; false )`

    Angir **_showDetails** -variabelen til **Usann**, noe som betyr at innholdet i invitasjons fanen er synlig, og at innholdet i kategorien **tids plan** er skjult.

## <a name="schedule-tab"></a>Tids plan-kategori

   ![LblInviteTab-kontroll](media/meeting-screen/meeting-schedule-text.png)

* Gjelder **Farge**<br>
    Verdi: `If( !_showDetails; LblRecipientCount.Color; RectQuickActionBar.Fill )`

    **_showDetails** er en variabel som brukes til å fastslå om **LblInviteTab** -kontrollen eller **LblScheduleTab** -kontrollen er valgt. Hvis det er tilfellet, er **LblScheduleTab** valgt. Hvis usann, **LblInviteTab** er. Dette betyr at hvis **_showDetails** er sann (denne fanen *er* valgt), Sams varer kategori fargen med fyll verdien til **RectQuickActionBar**. Ellers Sams varer den med farge verdien til **LblRecipientCount**.

* Gjelder **OnSelect**<br>
    Verdi: `Set( _showDetails; true )`

    Angir **_showDetails** -variabelen til **sann**, noe som betyr at innholdet i kategorien tids plan er synlig, og at innholdet i invitasjons fanen er skjult.

## <a name="text-search-box"></a>Boks for tekstsøk

   ![TextSearchBox-kontroll](media/meeting-screen/meeting-search-box.png)

<!--Include description of text search box control?-->

Flere andre kontroller på skjermen har en avhengighet på denne:

* Hvis en bruker begynner å skrive inn tekst, blir **PeopleBrowseGallery** synlig.
* Hvis en bruker skriver en gyldig e-postadresse, blir **AddIcon** synlig.
* Når en bruker velger en person i **PeopleBrowseGallery** , tilbakestilles søke innholdet.

## <a name="add-icon"></a>Legg til-ikon

   ![AddIcon-kontroll](media/email-screen/email-add-icon.png)

Med denne kontrollen kan brukere legge til personer som ikke finnes i organisasjonen, i deltaker listen for møtet som er satt sammen.

* Gjelder **Tydelig**<br>
    Revaluer Tre logiske kontroller som alle må evaluere til **sann** for at kontrollen skal være synlige:

    ```powerapps-comma
    !IsBlank( TextSearchBox.Text ) &&
        IsMatch( TextSearchBox.Text; Match.Email ) &&
        Not( Trim( TextSearchBox.Text ) in MyPeople.UserPrincipalName )
    ```

  Linje for linje, sier denne kode blokken at **AddIcon** -kontrollen bare er synlig hvis:

  * **TextSearchBox** inneholder tekst.
  * Teksten i **TextSearchBox** er en gyldig e-postadresse.
  * Teksten i **TextSearchBox** finnes ikke allerede i **MyPeople** -samlingen.

* Gjelder **OnSelect**<br> 
    Revaluer En **Collect** -setning for å legge til brukeren i deltaker listen, en annen å oppdatere tilgjengelige møte tids punkt og flere variable veksler:

    ```powerapps-comma
    Collect( MyPeople;
        { 
            DisplayName: TextSearchBox.Text; 
            UserPrincipalName: TextSearchBox.Text; 
            Mail: TextSearchBox.Text
        }
    );;
    Concurrent(
        Reset( TextSearchBox );
        Set( _showMeetingTimes; false );
        UpdateContext( { _loadMeetingTimes: true } );
        Set( _selectedMeetingTime; Blank() );
        Set( _selectedRoom; Blank() );
        Set( _roomListSelected; false );
        ClearCollect( MeetingTimes; 
            AddColumns(
                'Office365'.FindMeetingTimes(
                    { 
                        RequiredAttendees: Concat(MyPeople; UserPrincipalName & ";")
                        MeetingDuration: MeetingDurationSelect.Selected.Minutes;
                        Start: Text( DateAdd( MeetingDateSelect.SelectedDate; 8; Hours ); UTC );
                        End: Text( DateAdd( MeetingDateSelect.SelectedDate; 17; Hours ); UTC );
                        MaxCandidates: 15; 
                        MinimumAttendeePercentage:1; 
                        IsOrganizerOptional: false; 
                        ActivityDomain: "Work"
                    }
                ).MeetingTimeSuggestions;
                "StartTime"; MeetingTimeSlot.Start.DateTime; 
                "EndTime"; MeetingTimeSlot.End.DateTime
            )
        )
    );;
    UpdateContext( { _loadingMeetingTimes: false } );;
    Set( _showMeetingTimes; true )
    ```

  Hvis du velger denne kontrollen, legges den til i den gyldige e-postadressen (vises bare hvis en gyldig e-postadresse skrives inn i **TextSearchBox**) til **MyPeople** -samlingen (denne samlingen er deltaker listen), og deretter oppdaterer de tilgjengelige møte tidspunktene med den nye bruker oppføring.

  På lavt nivå, denne kode blokken:
  1. Samler e-postadressen inn i **MyPeople** -samlingen, og samler inn e-postadressen i feltene **DisplayName**, **userPrincipalName**og **e-post** .
  1. Tilbakestiller innholdet i **TextSearchBox** -kontrollen.
  1. Angir **_showMeetingTimes** -variabelen som **Usann**. Denne variabelen kontrollerer synligheten til **FindMeetingTimesGallery**, som viser åpne tidspunkter som de valgte deltakerne kan oppfylle.
  1. Angir kontekst variabel for **_loadMeetingTimes** til **sann**. Denne variabelen angir en innlastings tilstand, som aktiverer/deaktiverer synligheten for innlastings status kontroller som **_LblTimesEmptyState** for å angi brukeren at dataene lastes inn.
  1. Setter **_selectedMeetingTime** til **blank ()** . **_selectedMeetingTime** er den valgte posten fra **FindMeetingTimesGallery** -kontrollen. Det er blankt her fordi det å legge til en annen deltaker kanskje bety at den forrige definisjonen av **_selectedMeetingTime** ikke er tilgjengelig for den deltakeren.
  1. Setter **_selectedRoom** til **blank ()** . **_selectedRoom** er den valgte rom posten fra **RoomBrowseGallery**. Rom-tilgjengelighet fastsettes fra verdien til **_selectedMeetingTime**. Med den verdien blank er **_selectedRoom** -verdien ikke lenger gyldig, så den må være tom.
  1. Setter **_roomListSelected** til **Usann**. Denne linjen er kanskje ikke tilgjengelig for alle. I Office kan du gruppere rommene etter ulike «rom lister». Hvis du har rom lister, er dette skjerm bildet for det, slik at du først kan velge en rom liste før du velger et rom i listen. Verdien for **_roomListSelected** er det som bestemmer om en bruker (i en Tenant med rom bare lister) skal vise rom i en rom liste eller settet med rom lister. Den er satt til **False** for å tvinge brukere til å velge en ny rom liste.
  1. Bruker [office365. FindMeetingTimes](https://docs.microsoft.com/connectors/office365/#find-meeting-times) -operasjonen til å fastslå og samle de tilgjengelige møte tidspunktene for deltakerne. Denne operasjonen består av følgende:
      * **UserPrincipalName** for hver valgte bruker i *RequiredAttendees* -parameteren.
      * **MeetingDurationSelect**. Valgt. minutter til *MeetingDuration* -parameteren.
      * MeetingDateSelect. SelectedDate + 8 timer i *Start* parameteren. Åtte timer legges til, fordi det som standard er det fullstendige dato/klokkeslett for kalender-kontrollen er 12:00 for den valgte datoen. Du ønsker sannsynligvis å hente tilgjengelighet i vanlig arbeids tid. Start tidspunkt for normal arbeid vil være 8:00 AM.
      * **MeetingDateSelect**. SelectedDate + 17 timer til *slutt* -parameteren. 17 timer legges til fordi 12:00 AM + 17 = 5:00 PM. Et normalt Slut tids punkt for arbeids plassen ville være 5:00 PM.
      * *15* i *MaxCandidates* -parameteren. Dette betyr at operasjonen bare returnerer de 15 høyeste tidspunktene for den valgte datoen. Dette gir mening fordi det bare er 16 30 minutter i løpet av en arbeids dag på 8 timer, og et 30 minutters møte er minimums grensen som kan angis i dette skjerm bildet.
      * *1* i *MinimumAttendeePercentage* -parameteren. I hoved sak blir møte tids punktet hentet med mindre ingen deltakere er tilgjengelige.
      * **Usann** i *IsOrganizerOptional* -parameteren. App-brukeren er ikke en valg fri deltaker for dette møtet.
      * «Arbeid» i parameteren *ActivityDomain* . Dette betyr at de hentede tidspunktene bare er innenfor en vanlig arbeids tids periode.
  1. **ClearCollect** -funksjonen legger også til to kolonner: «Start Time» og «EndTime». Dette forenkler dataene som returneres. 
  Feltet som inneholder de tilgjengelige start-og Slut tids punktene, er **MeetingTimeSlot** -feltet. Dette feltet er en post som inneholder Start-og slutt-postene, som selv inneholder **datetime** -og **timezone** -verdiene for sitt respektive forslag. I stedet for å prøve å hente denne nestingen av poster, kan du ved å legge til Kol onnene «Start Time» og «EndTime» i **MeetingTimes** -samlingen hente disse **> datetime** og **end > datetime** -verdier til overflaten på samlingen.
  1. Når disse funksjonene er fullført, er variabelen **_loadingMeetingTimes** satt til **False**, fjerning av innlastings statusen og **_showMeetingTimes** er satt til **sann**, og viser **FindMeetingTimesGallery**.

## <a name="people-browse-gallery"></a>Galleri for personer-bla gjennom

   ![PeopleBrowseGallery-kontroll](media/meeting-screen/meeting-browse-gall.png)

* Gjelder **Elementene**<br>
    Revaluer 
    ```powerapps-comma
    If( !IsBlank( Trim( TextSearchBox.Text ) ); 
        'Office365Users'.SearchUser( { searchTerm: Trim(TextSearchBox.Text); top: 15 } )
    )
    ```

Elementene i dette galleriet er fylt ut av søke resultater fra [office365. SearchUser](https://docs.microsoft.com/connectors/office365users/#searchuser) -operasjonen. Operasjonen tar teksten i `Trim(**TextSearchBox**)` som søke ordet og returnerer de 15 høyeste resultatene basert på søket.
  
**TextSearchBox** er pakket i en **trim** -funksjon fordi en bruker søker etter mellomrom ikke er gyldig. @No__t-0-operasjonen brytes i en `If(!IsBlank(Trim(TextSearchBox.Text)) ... )`-funksjon fordi det hentes søke resultater før en bruker har søkt etter en ytelses avfall.

### <a name="people-browse-gallery-title"></a>Person søker Galleri tittel

   ![PeopleBrowseGallery tittel-kontroll](media/meeting-screen/meeting-browse-gall-title.png)

* Gjelder **Tekst**<br>
    Verdi: `ThisItem.DisplayName`

    Viser personens visnings navn fra Office 365-profilen.

* Gjelder **OnSelect**<br>
    Revaluer En **Collect** -setning for å legge til brukeren i deltaker listen, en annen å oppdatere tilgjengelige møte tids punkt og flere variable veksler:

    ```powerapps-comma
    Concurrent(
        Reset( TextSearchBox );
        Set( _selectedUser; ThisItem );
        If( Not( ThisItem.UserPrincipalName in MyPeople.UserPrincipalName ); 
            Collect( MyPeople; ThisItem );; 
            Concurrent(
                Set( _showMeetingTimes; false );
                UpdateContext( { _loadMeetingTimes: true } );
                Set( _selectedMeetingTime; Blank() );
                Set( _selectedRoom; Blank() );
                Set( _roomListSelected; false );
                ClearCollect( MeetingTimes; 
                    AddColumns(
                        'Office365'.FindMeetingTimes(
                            {
                                RequiredAttendees: Concat( MyPeople; UserPrincipalName & ";" );
                                MeetingDuration: MeetingDurationSelect.Selected.Minutes;
                                Start: Text( DateAdd( MeetingDateSelect.SelectedDate; 8; Hours ); UTC );
                                End: Text( DateAdd( MeetingDateSelect.SelectedDate; 17; Hours ); UTC );
                                MaxCandidates: 15; 
                                MinimumAttendeePercentage: 1; 
                                IsOrganizerOptional: false; 
                                ActivityDomain: "Work"
                            }
                        ).MeetingTimeSuggestions;
                        "StartTime"; MeetingTimeSlot.Start.DateTime; 
                        "EndTime"; MeetingTimeSlot.End.DateTime
                    )
                )
            );;
            UpdateContext( { _loadingMeetingTimes: false } );;
            Set( _showMeetingTimes; true )
        )
    )
    ```

    Hvis du velger denne kontrollen på et høyt nivå, legges personen til i **MyPeople** -samlingen (appens lagring av deltaker listen) og oppdaterer de tilgjengelige møte tidspunktene basert på det nye bruker tillegget.

    Valg av denne kontrollen er veldig lik når du velger **AddIcon** -kontrollen. den eneste forskjellen er at `Set(_selectedUser; ThisItem)`-setningen og UTFØRINGS rekkefølgen til operasjonene. Denne diskusjonen vil da ikke være så dyp. Hvis du vil ha en full forklaring, kan du lese gjennom [AddIcon-kontroll](#add-icon) delen.

    Hvis du velger denne kontrollen, tilbakestilles **TextSearchBox**. Hvis valget ikke er i **MyPeople** -samlingen, er kontrollen:
    1. Setter **_loadMeetingTimes** -tilstanden til **sann** og **_showMeetingTimes** -tilstanden til **Usann**, null stiller **_SelectedMeetingTime** -og **_selectedRoom** -variablene og oppdaterer **MeetingTimes** samling med det nye tillegget i **MyPeople** -samlingen. 
    1. Setter **_loadMeetingTimes** -tilstanden til **Usann**, og setter **_showMeetingTimes** til **sann**. Hvis utvalget allerede er i **MyPeople** -samlingen, tilbakestilles bare innholdet i **TextSearchBox**.

## <a name="meeting-people-gallery"></a>Møte person galleri

   ![MeetingPeopleGallery-kontroll](media/meeting-screen/meeting-people-gall.png)

* Gjelder **Elementene**<br>
    Verdi: `MyPeople`

    **MyPeople** -samlingen er samlingen av personer som er initialisert eller lagt til ved å velge **PeopleBrowseGallery tittel** -kontrollen.

* Gjelder **Høyden**<br>
    Revaluer Logikk som tillater at galleriet vokser til en maksimums høyde på 350:

    ```powerapps-comma
    Min( 
        76 * RoundUp( CountRows( MeetingPeopleGallery.AllItems ) / 2; 0 );
        350
    )
    ```

  
   Høyden på dette galleriet justerer etter antall elementer i galleriet, til en maksimums høyde på 350. Formelen tar 76 som høyde på én enkelt rad med **MeetingPeopleGallery**, og multipliserer den med antallet rader. **WrapCount** -egenskapen er satt til 2, så antallet virkelige rader er `RoundUp(CountRows(MeetingPeopleGallery.AllItems) / 2; 0)`.

* Gjelder **ShowScrollbar**<br>
    Verdi: `MeetingPeopleGallery.Height >= 350`

    Når den maksimale høyden på galleriet nås (350), er rulle feltet synlig.

### <a name="meeting-people-gallery-title"></a>Tittel på møte person galleri

   ![MeetingPeopleGallery tittel-kontroll](media/meeting-screen/meeting-people-gall-title.png)

* Gjelder **OnSelect**<br>
    
    Verdi: `Set(_selectedUser; ThisItem)`
    
    Angir **_selectedUser** -variabelen til elementet som er valgt i **MeetingPeopleGallery**.

### <a name="meeting-people-gallery-iconremove"></a>Møte person Galleri iconRemove

   ![MeetingPeopleGallery iconRemove-kontroll](media/meeting-screen/meeting-people-gall-delete.png)

* Gjelder **OnSelect**<br>
    Revaluer En **Remove** -setning for å fjerne brukeren fra deltaker listen, en **samle** konto for å oppdatere tilgjengelige møte tidspunkter og flere variable veksler:

    ```powerapps-comma
    Remove( MyPeople; LookUp( MyPeople; UserPrincipalName = ThisItem.UserPrincipalName ) );;
    Concurrent(
        Reset( TextSearchBox );
        Set( _showMeetingTimes; false );
        UpdateContext( { _loadMeetingTimes: true } );
        Set( _selectedMeetingTime; Blank() );
        Set( _selectedRoom; Blank() );
        Set( _roomListSelected; false );
        ClearCollect( MeetingTimes; 
            AddColumns(
                'Office365'.FindMeetingTimes(
                    {
                        RequiredAttendees: Concat( MyPeople; UserPrincipalName & ";" ); 
                        MeetingDuration: MeetingDurationSelect.Selected.Minutes;
                        Start: Text( DateAdd( MeetingDateSelect.SelectedDate; 8; Hours ); UTC ); 
                        End: Text( DateAdd( MeetingDateSelect.SelectedDate; 17; Hours ); UTC );
                        MaxCandidates: 15; 
                        MinimumAttendeePercentage: 1; 
                        IsOrganizerOptional: false; 
                        ActivityDomain: "Work"
                    }
                ).MeetingTimeSuggestions;
                "StartTime"; MeetingTimeSlot.Start.DateTime; 
                "EndTime"; MeetingTimeSlot.End.DateTime
            )
        )
    );;
    UpdateContext( { _loadingMeetingTimes: false } );;
    Set( _showMeetingTimes; true )
    ```

  Hvis du velger denne kontrollen på et høyt nivå, fjernes personen fra deltaker listen, og de tilgjengelige møte tidspunktene oppdateres basert på fjerningen av denne personen.

  Når du velger denne kontrollen, er det nesten identisk med den første linjen i koden ovenfor for å velge **AddIcon** -kontrollen. Denne diskusjonen vil da ikke være så dypt. Hvis du vil ha en full forklaring, kan du lese gjennom [AddIcon-kontroll delen](#add-icon).

  I den første kode linjen fjernes det valgte elementet fra **MyPeople** -samlingen. Koden blir da:
  1. Tilbakestiller **TextSearchBox**, og fjerner deretter valget fra **MyPeople** -samlingen. 
  1. Setter **_loadMeetingTimes** -tilstanden til **sann** og **_showMeetingTimes** -tilstanden til **Usann**, null stiller **_SelectedMeetingTime** -og **_selectedRoom** -variablene og oppdaterer **MeetingTimes** samling med det nye tillegget i **MyPeople** -samlingen. 
  1. Setter **_loadMeetingTimes** -tilstanden til **Usann**, og setter **_showMeetingTimes** til **sann**.

## <a name="meeting-date-picker"></a>Dato velger for møte

   ![MeetingDateSelect-kontroll](media/meeting-screen/meeting-datepicker.png)

* Gjelder **Display Mode**<br>
    Verdi: `If( IsEmpty(MyPeople); DisplayMode.Disabled; DisplayMode.Edit )`

    Kan ikke velge en dato for et møte før minst én deltaker er lagt til i **MyPeople** -samlingen.

* Gjelder **OnChange**<br>
    Verdi: `Select( MeetingDateSelect )`

    Endring av den valgte datoen utløser koden i **OnSelect** -egenskapen for denne kontrollen til å kjøre.

* Gjelder **OnSelect**<br>
    Revaluer En **Collect** -setning for å oppdatere tilgjengelige møte tidspunkter og flere variable veksler:
  
    ```powerapps-comma
    Concurrent(
        Reset( TextSearchBox );
        Set( _showMeetingTimes; false );
        UpdateContext( { _loadingMeetingTimes: true } );
        Set( _selectedMeetingTime; Blank() );
        Set( _selectedRoom; Blank() );
        Set( _roomListSelected; false );
        ClearCollect( MeetingTimes; 
            AddColumns(
                'Office365'.FindMeetingTimes(
                    {
                        RequiredAttendees: Concat( MyPeople; UserPrincipalName & ";" ); 
                        MeetingDuration: MeetingDurationSelect.Selected.Minutes;
                        Start: Text( DateAdd( MeetingDateSelect.SelectedDate; 8; Hours ); UTC ); 
                        End: Text( DateAdd( MeetingDateSelect.SelectedDate; 17; Hours ); UTC );
                        MaxCandidates: 15; 
                        MinimumAttendeePercentage: 1; 
                        IsOrganizerOptional: false; 
                        ActivityDomain: "Work"
                    }
                ).MeetingTimeSuggestions;
                "StartTime"; MeetingTimeSlot.Start.DateTime; 
                "EndTime"; MeetingTimeSlot.End.DateTime
            )
        )
    );;
    UpdateContext( { _loadingMeetingTimes: false } );;
    Set( _showMeetingTimes; true )
    ```

  Hvis du velger denne kontrollen på et høyt nivå, oppdateres de tilgjengelige møte tidspunktene. Det er nyttig fordi hvis en bruker endrer datoen, må de tilgjengelige møte tidspunktene oppdateres for å gjenspeile deltakerens tilgjengelighet for den dagen.

  Med unntak av den første **Collect** -setningen er dette identisk med **OnSelect** -funksjonaliteten til **AddIcon** -kontrollen. Denne diskusjonen vil da ikke være så dypt. Hvis du vil ha en full forklaring, kan du lese gjennom [AddIcon-kontroll](#add-icon) delen.

  Hvis du velger denne kontrollen, tilbakestilles **TextSearchBox**. Den: 
  1. Setter **_loadMeetingTimes** -tilstanden til **sann** og **_showMeetingTimes** -tilstanden til **Usann**, null stiller **_SelectedMeetingTime** -og **_selectedRoom** -variablene og oppdaterer **MeetingTimes** samling med det nye dato valget. 
  1. Setter **_loadMeetingTimes** -tilstanden til **Usann**, og setter **_showMeetingTimes** til **sann**.

## <a name="meeting-duration-drop-down"></a>Rulle gardin listen møte varighet

   ![MeetingDateSelect-kontroll](media/meeting-screen/meeting-timepicker.png)

* Gjelder **Display Mode**<br>
    Verdi: `If( IsEmpty(MyPeople); DisplayMode.Disabled; DisplayMode.Edit )`

    Du kan ikke velge en varighet før minst én deltaker er lagt til i **MyPeople** -samlingen.

* Gjelder **OnChange**<br>
    Verdi: `Select(MeetingDateSelect1)`

    Hvis du endrer den valgte varigheten, utløses koden i **OnSelect** -egenskapen for **MeetingDateSelect** -kontrollen.

## <a name="find-meeting-times-gallery"></a>Søk etter møte tids galleri

   ![FindMeetingTimesGallery-kontroll](media/meeting-screen/meeting-time-gall.png)

* Gjelder **Elementene**<br>
    Verdi: `MeetingTimes`

    Samlingen av potensielle møte tider Hentet fra [office365. FindMeetingTimes](https://docs.microsoft.com/connectors/office365/#find-meeting-times) -operasjonen.

* Gjelder **Tydelig**<br>
    Verdi: `_showMeetingTimes && _showDetails && !IsEmpty( MyPeople )`

    Galleriet er bare synlig hvis **_showMeetingTimes** er satt til **True**, brukeren har valgt **LblScheduleTab** -kontrollen, og det finnes minst én deltaker som er lagt til i møtet.

### <a name="find-meeting-times-gallery-title"></a>Finn møte tids Galleri tittel

   ![FindMeetingTimesGallery tittel-kontroll](media/meeting-screen/meeting-time-gall-title.png)

* Gjelder **Tekst**<br>
    Revaluer En konvertering av Start tidspunktet som skal vises i brukerens lokale klokkeslett:

    ```powerapps-comma
    Text(
        DateAdd(
            DateTimeValue( ThisItem.StartTime );
            - TimeZoneOffset(); 
            Minutes
        );
        DateTimeFormat.ShortTime
    )
    ```

  Den hentede verdien for **Start Time** er i UTC-format. Hvis du vil [konvertere fra UTC til lokal tid](../functions/function-dateadd-datediff.md#converting-from-utc), brukes **DateAdd** -funksjonen.
  [Text-funksjonen](../functions/function-text.md#datetime) tar dato/klokkeslett som første argument, og formaterer den basert på det andre argumentet. Du overfører den lokale tids konverteringen for **ThisItem. Start Time**, og viser den som **DateTimeFormat. ShortTime**.

* Gjelder **OnSelect**<br>
    Revaluer Flere **innsamlings** erklæringer for innhenting av møterom og deres foreslåtte tilgjengelighet, i tillegg til flere variable vekslinger:

    ```powerapps-comma
    Set( _selectedMeetingTime; ThisItem );;
    UpdateContext( { _loadingRooms: true } );;
    If( IsEmpty( RoomsLists );
        ClearCollect( RoomsLists; 'Office365'.GetRoomLists().value) );;
    If( CountRows( RoomsLists ) <= 1;
        Set( _noRoomLists; true );;
        ClearCollect( AllRooms; 'Office365'.GetRooms().value );;
        Set( _allRoomsConcat; Concat( FirstN( AllRooms; 20 ); Address & ";" ) );;
        ClearCollect( RoomTimeSuggestions; 
            'Office365'.FindMeetingTimes(
                {
                    RequiredAttendees: _allRoomsConcat; 
                    MeetingDuration: MeetingDurationSelect.Selected.Minutes;
                    Start: _selectedMeetingTime.StartTime & "Z"; 
                    End: _selectedMeetingTime.EndTime & "Z"; 
                    MinimumAttendeePercentage: "1";
                    IsOrganizerOptional: "false"; 
                    ActivityDomain: "Unrestricted"
                }
            ).MeetingTimeSuggestions
        );;
        ClearCollect( AvailableRooms; 
            AddColumns(
                AddColumns(
                    Filter( 
                        First( RoomTimeSuggestions ).AttendeeAvailability;
                        Availability="Free"
                    ); 
                    "Address"; Attendee.EmailAddress.Address
                ); 
                "Name"; LookUp( AllRooms; Address = Attendee.EmailAddress.Address ).Name 
            )
        );;
        ClearCollect( AvailableRoomsOptimal; 
            DropColumns(
                DropColumns( AvailableRooms; "Availability" ); 
                "Attendee" 
            )
        );
        Set( _roomListSelected; false) 
    );;
    UpdateContext( {_loadingRooms: false} )
    ```

  På høyt nivå samler denne kode blokken opp tilgjengelige rom for brukere som ikke har rom-lister, basert på det valgte dato/klokkeslett for møtet. Ellers henter den bare rom listene.

  På lavt nivå, denne kode blokken:
  1. Setter **_selectedMeetingTime** til det valgte elementet. Dette brukes til å finne hvilke rom som er tilgjengelige i løpet av denne tiden.
  1. Angir variabelen **_loadingRooms** for innlastings tilstand til **sann**, og aktiverer innlastings tilstanden.
  1. Hvis **RoomsLists** -samlingen er tom, henter den brukerens tenant's rom-lister og lagrer dem i **RoomsLists** -samlingen.
  1. Hvis brukeren ikke har noen rom liste eller en romliste:
      1. **NoRoomLists** -variabelen er satt til **sann**, og denne variabelen brukes til å fastsette elementene som vises i **RoomBrowseGallery** -kontrollen.
      1. @No__t-0-operasjonen brukes til å hente de første 100 rommene i tenanten. Disse lagres i **AllRooms** -samlingen.
      1. **_AllRoomsConcat** -variabelen er satt til en semikolondelt streng av de første 20 e-postadressene til rommene i **AllRooms** -samlingen. Dette er fordi [office365. FindMeetingTimes](https://docs.microsoft.com/connectors/office365/#find-meeting-times) er begrenset til å søke etter de tilgjengelige tidspunktene på 20 person objekter i én enkelt operasjon.
      1. **RoomTimeSuggestions** -samlingen bruker [office365. FindMeetingTimes](https://docs.microsoft.com/connectors/office365/#find-meeting-times) til å hente tilgjengelighet for de første 20 rommene i **AllRooms** -samlingen, basert på klokkeslett verdiene fra **_selectedMeetingTime** -variabelen. Vær oppmerksom på at `& "Z"` brukes til å formatere **datetime** -verdien riktig.
      1. **AvailableRooms** -samlingen er opprettet. Dette er bare **RoomTimeSuggestions** -samlingen av deltaker tilgjengelighet med to ekstra kolonner som er lagt til i den: "Adresse" og "navn". «Adresse» er e-postadressen til rommet, og «navn» er navnet på rommet.
      1. Deretter opprettes samlingen **AvailableRoomsOptimal** . Dette er bare **AvailableRooms** -samlingen der «tilgjengelighet»-og «deltaker»-Kol onnene er fjernet. Dette Sams varer med XML-skjemaene i **AvailableRoomsOptimal** og **AllRooms**. Dette gjør at du kan bruke begge samlingene i **Items** -egenskapen til **RoomBrowseGallery**.
      1. **_roomListSelected** er satt til **False**.
  1. Innlastings tilstanden, **_loadingRooms**, er satt til **Usann** når alt annet er ferdig med å kjøre.

## <a name="room-browse-gallery"></a>Galleri for rom visning

   ![RoomBrowseGallery-kontroll](media/meeting-screen/meeting-rooms-gall.png)

* Gjelder **Elementene**<br>
    Revaluer Logisk satt til to interne samlinger med identisk XML-skjema, avhengig av om brukeren har valgt en rom liste eller inneholder rom lister i leieren:

    ```powerapps-comma
    Search(
        If( _roomListSelected || _noRoomLists; AvailableRoomsOptimal; RoomsLists );
        Trim(TextMeetingLocation1.Text); 
        "Name"; 
        "Address"
    )
    ```

  Dette galleriet viser samlingen **AvailableRoomsOptimal** Hvis **_roomListSelected** eller **_noRoomLists** er **sann**. Ellers vises samlingen **RoomsLists** . Dette kan gjøres fordi skjemaet for disse samlingene er identiske.

* Gjelder **Tydelig**<br>
    Verdi: ```_showDetails && !IsBlank( _selectedMeetingTime ) && !_loadingRooms```

    Galleriet er bare synlig hvis de tre foregående setningene evalueres til **sann**.

### <a name="roombrowsegallery-title"></a>RoomBrowseGallery tittel

   ![RoomBrowseGallery tittel-kontroll](media/meeting-screen/meeting-rooms-gall-title.png)

* Gjelder **OnSelect**<br>
    Revaluer Et sett med logisk bundne **samle** -og **angivelses** setninger, som kanskje eller kanskje ikke utløses, avhengig av om brukeren viser rom lister eller rom:

    ```powerapps-comma
    UpdateContext( { _loadingRooms: true } );;
    If( !_roomListSelected && !noRoomLists;
        Set( _roomListSelected; true );;
        Set( _selectedRoomList; ThisItem.Name );;
        ClearCollect( AllRooms; 'Office365'.GetRoomsInRoomList( ThisItem.Address ).value );;
        Set( _allRoomsConcat; Concat( FirstN( AllRooms; 20 ); Address & ";" ) );;
        ClearCollect( RoomTimeSuggestions; 
            'Office365'.FindMeetingTimes(
                {
                    RequiredAttendees: _allRoomsConcat; 
                    MeetingDuration: MeetingDurationSelect.Selected.Minutes;
                        Start: _selectedMeetingTime.StartTime & "Z"; 
                    End: _selectedMeetingTime.EndTime & "Z"; 
                    MinimumAttendeePercentage: "1";
                    IsOrganizerOptional: "false"; 
                    ActivityDomain: "Unrestricted"
                }
            ).MeetingTimeSuggestions
        );;
        ClearCollect( AvailableRooms; 
            AddColumns(
                AddColumns(
                    Filter(
                        First( RoomTimeSuggestions ).AttendeeAvailability; 
                        Availability = "Free"
                    );
                    "Address"; Attendee.EmailAddress.Address 
                ); 
                "Name"; LookUp( AllRooms; Address = Attendee.EmailAddress.Address ).Name
            )
        );;
        ClearCollect( AvailableRoomsOptimal; 
            DropColumns(
                DropColumns( AvailableRooms; "Availability" )
            ); 
            "Attendee" )
        );
        Set( _selectedRoom; ThisItem )
    );;
    UpdateContext( {_loadingRooms: false} )
    ```

  Handlingene som forekommer når denne kontrollen velges, avhenger av om en bruker viser et sett med rom lister eller et sett med rom. Hvis det er den første, kan du velge denne kontrollen henter rommene som er tilgjengelige på det valgte tidspunktet, fra den valgte rom listen. Hvis det er det siste, kan du velge denne kontrollen for å angi **_selectedRoom** -variabelen til det valgte elementet. Oven stående uttrykk ligner veldig på **Select** -setningen for [**FindMeetingTimesGallery title**](#find-meeting-times-gallery).

  På lavt nivå, den foregående kode blokken:
  1. Aktiverer innlastings tilstanden for rommene ved å sette **_loadingRooms** til **sann**.
  1. Kontrollerer om en romliste er valgt, og om leieren har rom lister. Hvis det er tilfellet:
      1. Setter **_roomListSelected** til **sann** og angir **_selectedRoomList** til det valgte elementet.
      1. **_AllRoomsConcat** -variabelen er satt til en semikolondelt streng av de første 20 e-postadressene til rommene i **AllRooms** -samlingen. Dette er fordi [office365. FindMeetingTimes](https://docs.microsoft.com/connectors/office365/#find-meeting-times) -operasjonen er begrenset til å søke etter de tilgjengelige tidspunktene på 20 person objekter i én enkelt operasjon.
      1. **RoomTimeSuggestions** -samlingen bruker [office365. FindMeetingTimes](https://docs.microsoft.com/connectors/office365/#find-meeting-times) -operasjonen til å hente tilgjengelighet for de første 20 rommene i samlingen **AllRooms** , basert på klokkeslett verdiene fra **_selectedMeetingTime** variabel. Vær oppmerksom på at `& "Z"` brukes til å formatere **datetime** -verdien riktig.
      1. **AvailableRooms** -samlingen er opprettet. Dette er bare **RoomTimeSuggestions** -samlingen av deltaker tilgjengelighet med to ekstra kolonner som er lagt til i den: "Adresse" og "navn". «Adresse» er e-postadressen til rommet, og «navn» er navnet på rommet.
      1. Deretter opprettes samlingen **AvailableRoomsOptimal** . Dette er bare **AvailableRooms** -samlingen der «tilgjengelighet»-og «deltaker»-Kol onnene er fjernet. Dette Sams varer med XML-skjemaene i **AvailableRoomsOptimal** og **AllRooms**. Dette gjør at du kan bruke begge samlingene i **Items** -egenskapen til **RoomBrowseGallery**.
      1. **_roomListSelected** er satt til **False**.
  1. Innlastings tilstanden, **_loadingRooms**, er satt til **Usann** når alt annet er ferdig med å kjøre.

## <a name="back-chevron"></a>Tilbake vinkel

   ![RoomsBackNav-kontroll](media/meeting-screen/meeting-back.png)

* Gjelder **Tydelig**<br>
    Verdi: `_roomListSelected && _showDetails`

    Denne kontrollen er bare synlig hvis både en romliste er valgt og **tids plan** -fanen er valgt.

* Gjelder **OnSelect**<br>
    Verdi: `Set( _roomListSelected; false )`

    Når **_roomListSelected** er satt til **False**, endres **RoomBrowseGallery** -kontrollen for å vise elementer fra **RoomsLists** -samlingen.

## <a name="send-icon"></a>Send-ikon

   ![IconSendItem-kontroll](media/meeting-screen/meeting-send-icon.png)

* Gjelder **Display Mode**<br>
    Revaluer Logikk som tvinger brukeren til å skrive inn bestemte møte detaljer før ikonet kan redigeres.
    
    ```powerapps-comma
    If( Len( Trim( TextMeetingSubject1.Text ) ) > 0
        && !IsEmpty( MyPeople ) && !IsBlank( _selectedMeetingTime );
        DisplayMode.Edit; DisplayMode.Disabled
    )
    ```
  Ikonet kan bare velges hvis emnet for møte emne er fylt ut, det finnes minst én deltaker for møtet, og et møte tids punkt er valgt. Ellers er den deaktivert.

* Gjelder **OnSelect**<br>

    Revaluer Kode for å sende møte invitasjonen til de valgte deltakerne og fjerne alle inn data feltene:

    ```powerapps-comma
    Set( _myCalendarName; LookUp( 'Office365'.CalendarGetTables().value; DisplayName = "Calendar" ).Name );;
    Set( _myScheduledMeeting; 
        'Office365'.V2CalendarPostItem( _myCalendarName;
            TextMeetingSubject1.Text; 
            Text(DateAdd(DateTimeValue( _selectedMeetingTime.StartTime); -TimeZoneOffset(); Minutes) );
            Text(DateAdd(DateTimeValue( _selectedMeetingTime.EndTime); -TimeZoneOffset(); Minutes) );
            {
                RequiredAttendees: Concat( MyPeople; UserPrincipalName & ";" ) & _selectedRoom.Address; 
                Body: TextMeetingMessage1.Text; 
                Location: _selectedRoom.Name; 
                Importance: "Normal"; 
                ShowAs: "Busy"; 
                ResponseRequested: true
            }
        )
    );;
    Concurrent(
        Reset( TextMeetingLocation1 );
        Reset( TextMeetingSubject1 );
        Reset( TextMeetingMessage1 );
        Clear( MyPeople );
        Set( _selectedMeetingTime; Blank() );
        Set( _selectedRoomList; Blank() );
        Set( _selectedRoom; Blank() );
        Set( _roomListSelected; false )
    )
    ```
  
  På lavt nivå, denne kode blokken:
  1. Setter **_myCalendarName** til kalenderen i [office365. CalendarGetTables ()](https://docs.microsoft.com/connectors/office365/#get-calendars) -operasjonen med et **DisplayName** for Calendar.
  1. Planlegger møtet med alle inn data verdiene fra de ulike valgene som brukeren har gjort på skjermen, ved hjelp av [office365. V2CalendarPostItem](https://docs.microsoft.com/connectors/office365/#create-event--v2-) -operasjonen.
  1. Tilbakestiller alle inn data feltene og variablene som brukes ved oppretting av møtet.

> [!NOTE]
> Avhengig av området ditt, kan det hende at kalenderen du vil ha, ikke har et visnings navn på kalender. Gå til Outlook for å se hva tittelen på kalenderen er, og foreta riktig endring i appen.

## <a name="next-steps"></a>Neste trinn

* [Lær mer om denne skjermen](./meeting-screen-overview.md)
* [Finn ut mer om Office 365 Outlook Connector i PowerApps](../connections/connection-office365-outlook.md)
* [Les mer om Office 365 brukere-koblingen i PowerApps](../connections/connection-office365-users.md)
