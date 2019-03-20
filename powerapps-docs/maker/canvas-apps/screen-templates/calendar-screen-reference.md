---
title: Referanse for kalender-skjermen malen for lerretsapper | Microsoft Docs
description: Forstå detaljene for hvordan kalender-skjermen malen for lerret-apper fungerer i PowerApps.
author: emcoope-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 12/31/2018
ms.author: emcoope
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: abf88db2bfb97a6541ee638ba8be5af27c20bc5f
ms.sourcegitcommit: 5e15a1033a68289781f8092fb65c57432501f911
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 01/23/2019
ms.locfileid: "54459578"
---
# <a name="reference-information-about-the-calendar-screen-template-for-canvas-apps"></a>Referanseinformasjon om kalender-skjermen malen for lerretsapper

Forstå hvordan hver betydelige kontroll i malen kalender-skjermen, bidrar til skjermens overordnede standardfunksjonaliteten for lerret-apper i PowerApps. Dette dypdykket noe presenterer formler for virkemåte og verdiene i andre egenskaper som bestemmer hvordan kontrollene svare på inndata fra brukeren. Hvis en på høyt nivå gjennomgang av denne skjermen standard funksjonalitet, kan du se den [kalender-skjermen oversikt over](calendar-screen-overview.md).

Dette emnet uthever noen viktige kontroller og forklarer uttrykk eller formler til hvilke ulike egenskaper (slik som **elementer** og **OnSelect**) av disse kontrollene er angitt:

- [Kalender-listen (dropdownCalendarSelection)](#calendar-drop-down)
- [Kalender-ikonet (iconCalendar)](#calendar-icon)
- [Forrige måned vinkeltegn (iconPrevMonth)](#previous-month-chevron)
- [Neste måned vinkeltegn (iconNextMonth)](#next-month-chevron)
- [Kalender-galleri (MonthDayGallery) (+ underordnede kontroller)](#calendar-gallery)
- [Hendelser galleriet (CalendarEventsGallery)](#events-gallery)

## <a name="prerequisite"></a>Forutsetning

Kjennskap til hvordan du legger til og konfigurerer skjermbilder og andre kontroller som du [oppretter en app i PowerApps](../data-platform-create-app-scratch.md).

## <a name="calendar-drop-down"></a>Kalender-listen

![dropdownCalendarSelection kontroll](media/calendar-screen/calendar-dropdown.png)

- Egenskap: **Elementer**<br>
    Verdi: `Office365.CalendarGetTables().value`

    Denne verdien er en kobling-operasjon som henter app brukerens Outlook kalendere. Du kan se [verdien](https://docs.microsoft.com/connectors/office365/#entitylistresponse[table]) som denne operasjonen henter.

- Egenskap: **OnChange**<br>Verdi: `Select(dropdownCalendarSelection)`

    Når brukeren velger et alternativ i listen, funksjonen i kontrollens **OnSelect** egenskapen kjøringer.

- Egenskap: **OnSelect**<br>
    Verdi: En **Hvis** -funksjonen, som vises i du følgende kodeblokk, og flere ekstra funksjoner, som vises i du kodeblokk etter dette.

   Denne delen av formelen kjører bare første gang at brukeren velger et alternativ i fra rullegardinlisten når du har åpnet appen:

    ```powerapps-dot
    If( IsBlank( _userDomain ),
        UpdateContext( {_showLoading: true} );
        Set( _userDomain, Right( User().Email, Len( User().Email ) - Find( "@", User().Email ) ) );
        Set( _dateSelected, Today() );
        Set( _firstDayOfMonth, DateAdd( Today(), 1 - Day( Today() ), Days ) );  
        Set( _firstDayInView, DateAdd( _firstDayOfMonth, -(Weekday(_firstDayOfMonth) - 1), Days ) );
        Set( _lastDayOfMonth, DateAdd( DateAdd( _firstDayOfMonth, 1, Months ), -1, Days ) )  
    );
    ```

    Koden ovenfor definerer følgende variabler:
    
  - **\_userDomain**: App brukerens-firmadomenenavn, i brukerens e-postadresse.
  - **\_dateSelected**: Dagens dato (som standard). Kalender-galleriet uthever denne datoen, og hendelsen galleriet viser hendelser som er planlagt for den datoen.
  - **\_firstDayOfMonth**: Den første dagen i gjeldende måned. Fordi `(Today + (1 - Today)) = Today - Today + 1 = 1`, denne **DateAdd** funksjonen alltid returnerer den første dagen i måneden.
  - **\_firstDayInView**: Den første dagen som kan vise i galleriet for kalenderen. Denne verdien, er ikke det samme som den første dagen i måneden med mindre måneden starter på en søndag. Til å forhindre at en hele uken i forrige måned, verdien for  **\_firstDayInView** er `_firstDayOfMonth - Weekday(_firstDayOfMonth) + 1`.
  - **\_lastDayOfMonth**: Den siste dagen i gjeldende måned, som er den samme som den første dagen i neste måned, minus én dag.

   Funksjonene etter den **Hvis** funksjonen kjøres når brukeren velger et alternativ i rullegardinlisten kalenderlisten (ikke bare første gang brukeren åpner appen):

    ```powerapps-dot
    Set( _calendarVisible, false );
    UpdateContext( {_showLoading: true} );
    Set( _myCalendar, dropdownCalendarSelection2.Selected );
    Set( _minDate, 
        DateAdd( _firstDayOfMonth, -(Weekday( _firstDayOfMonth ) - 2 + 1), Days )
    );
    Set(_maxDate, 
        DateAdd(
            DateAdd( _firstDayOfMonth, -(Weekday( _firstDayOfMonth ) - 2 + 1), Days ), 
            40, 
            Days
        )
    );
    ClearCollect( MyCalendarEvents, 
        'Office365'.GetEventsCalendarViewV2( _myCalendar.Name, 
            Text( _minDate, UTC ), 
            Text( _maxDate, UTC )
        ).value
    );
    UpdateContext( {_showLoading: false} );
    Set( _calendarVisible, true )
    ```

    Koden ovenfor definerer disse variablene og én samling:

    - **\_calendarVisible**: Satt til **USANN** slik at kalenderen ikke vises under det nye merkede området er lastet.
    - **\_showLoading**: Satt til **SANN** slik at lasting av indikatorer vises når det nye merkede området lastes.
    - **\_myCalendar**: Satt til gjeldende verdi for den **kalender rullegardinlisten** kontroll, slik at hendelser fra den riktige kalenderen er hentet.
    - **\_minDate**: Satt til samme verdi som  **\_firstDayInView**. Denne variabelen bestemmer hvilke hendelser har allerede er hentet fra Outlook og bufres i appen.
    - **\_maxDate**: Angi til den siste dagen som kan vises i kalenderen. Formelen er `_firstDayInView + 40`. Kalenderen viser maksimalt 41 dager, slik at den  **\_maxDate** variabel alltid gjenspeiler den siste dagen som kan vises, og bestemmer hvilke hendelser har allerede er hentet fra Outlook og bufres i appen.
    - **MyCalendarEvents**: Satt til en samling av brukerens hendelser fra den valgte kalenderen, fra  **\_minDate** til  **\_maxDate**.
    - **\_showLoading**: Satt til **USANN**;  **\_calendarVisible** er satt til **SANN** etter at alt annet er lastet inn.

## <a name="calendar-icon"></a>Kalender-ikonet

![iconCalendar kontroll](media/calendar-screen/calendar-today-icon.png)

- Egenskap: **OnSelect**<br>
    Verdi: Fire **angi** funksjoner som tilbakestille kalender galleriet til dagens dato:

    ```powerapps-dot
    Set( _dateSelected, Today() );
    Set( _firstDayOfMonth, DateAdd( Today(), 1 - Day( Today() ), Days) );
    Set( _firstDayInView, DateAdd(_firstDayOfMonth, -(Weekday( _firstDayOfMonth ) - 2 + 1), Days));
    Set( _lastDayOfMonth, DateAdd( DateAdd( _firstDayOfMonth, 1, Months ), -1, Days ) )
    ```

    Koden ovenfor tilbakestiller alle Datovariabler som er nødvendige for å vise riktig Kalender-visningen:

    - **\_dateSelected** tilbakestilles til i dag.
    - **\_firstDayOfMonth** tilbakestilles til den første dagen i dagens måned.
    - **\_firstDayInView** tilbakestilles til den første dagen kan vises når dagens måned er valgt.
    - **\_lastDayOfMonth** tilbakestilles til den siste dagen i dagens måned.

    Den [ **kalender rullegardinlisten** ](#calendar-drop-down) delen av dette emnet forklarer disse variablene i mer detalj.

## <a name="previous-month-chevron"></a>Vinkeltegn for forrige måned

![iconPrevMonth kontroll](media/calendar-screen/calendar-back.png)

- Egenskap: **OnSelect**<br>Verdi: Fire **angi** funksjoner og en **Hvis** funksjonen som viser forrige måned i kalenderen galleriet:

    ```powerapps-dot
    Set( _firstDayOfMonth, DateAdd( _firstDayOfMonth, -1, Months ) );
    Set( _firstDayInView, 
        DateAdd( _firstDayOfMonth, -(Weekday( _firstDayOfMonth ) - 2 + 1), Days )
    );
    Set( _lastDayOfMonth, DateAdd(DateAdd( _firstDayOfMonth, 1, Months ), -1, Days ) );
    If( _minDate > _firstDayOfMonth,
        Collect( MyCalendarEvents,
            'Office365'.GetEventsCalendarViewV2( _myCalendar.Name,
                Text( _firstDayInView, UTC ), 
                Text( DateAdd( _minDate, -1, Days ), UTC )
            ).value
        );
        Set( _minDate, _firstDayInView )
    )
    ```

    > [!NOTE]
    > Definisjoner for  **\_firstDayOfMonth**,  **\_firstDayInView**, og  **\_lastDayOfMonth** er nesten identisk med de i den [kalender rullegardinlisten](#calendar-drop-down) delen i dette emnet.

    De tre første linjene av foregående koden kjøres når brukeren velger vinkeltegnet for forrige måned. Koden angir variablene som er nødvendig for å vise riktig Kalender-visningen. Gjenværende koden kjøres bare hvis brukeren ikke har valgt tidligere denne måneden for den valgte kalenderen.

    Hvis dette er tilfellet,  **\_minDate** er den første dagen som vises når forrige måned vises. Før brukeren velger ikonet,  **\_minDate** har en mulig minimumsverdien for 23rd av gjeldende måned. (Når 1. mars faller på en lørdag  **\_firstDayInView** for mars er februar 23.) Det betyr at hvis en bruker ikke har valgt denne måneden ennå,  **\_minDate** er større enn den nye  **\_firstDayOfMonth**, og den **Hvis** funksjonen returnerer **SANN**. De koden kjøringene, og en samling og en variabel oppdateres:

    - **MyCalendarEvents** henter hendelser fra den valgte kalenderen med den [Office365.GetEventsCalendarViewV2](https://docs.microsoft.com/connectors/office365/#get-calendar-view-of-events--v2-) operasjonen. Datoområdet er mellom den  **\_firstDayInView** dato og  **\_minDate** - 1. Fordi **MyCalendarEvents** allerede inneholder hendelser på den  **\_minDate** dato, 1 trekkes fra denne datoen for maksimumsverdien i dette nye datointervallet.

    - **\_minDate** er satt til gjeldende  **\_firstDayInView** fordi dette er den første datoen som hendelser er hentet. Hvis en bruker kommer tilbake til denne datoen ved å velge vinkeltegnet forrige måned, den **Hvis** -funksjonen returnerer **USANN**; koden ikke kjøres fordi hendelser for denne visningen er allerede hurtigbufret i  **MyCalendarEvents**.

## <a name="next-month-chevron"></a>Neste måned vinkeltegn

![iconNextMonth kontroll](media/calendar-screen/calendar-forward.png)

- Egenskap: **OnSelect**<br>
    Verdi: Fire **angi** funksjoner og en **Hvis** funksjonen som viser neste måned i kalenderen galleriet:

    ```powerapps-dot
    Set( _firstDayOfMonth, DateAdd( _firstDayOfMonth, 1, Months ) );
    Set( _firstDayInView, 
        DateAdd( _firstDayOfMonth, -(Weekday( _firstDayOfMonth ) - 2 + 1), Days ) );
    Set( _lastDayOfMonth, DateAdd( DateAdd( _firstDayOfMonth, 1, Months ), -1, Days ) );
    If( _maxDate < _lastDayOfMonth,
        Collect( MyCalendarEvents, 
            'Office365'.GetEventsCalendarViewV2( _myCalendar.Name, 
                Text( DateAdd( _maxDate, 1, Days ), UTC ), 
                DateAdd( _firstDayInView, 40, Days )
            ).value
        );
        Set( _maxDate, DateAdd( _firstDayInView, 40, Days) )    
    )
    ```

    > [!NOTE]
    > Definisjoner for  **\_firstDayOfMonth**,  **\_firstDayInView**, og  **\_lastDayOfMonth** er nesten identisk med de i den [kalender rullegardinlisten](#calendar-dropdown) delen i dette emnet.

    De tre første linjene av foregående kode som kjøres når brukeren velger vinkeltegnet for neste måned, angi variabler som er nødvendig for å vise riktig Kalender-visningen. Gjenværende koden kjøres bare hvis brukeren ikke har valgt tidligere denne måneden for den valgte kalenderen.

    I så fall  **\_maxDate** er den siste dagen som vises når forrige måned vises. Før brukeren velger vinkeltegnet for neste måned,  **\_maxDate** har en mulig maksimumsverdien for 13th av neste måned. (Når 1. februar er på et ikke-skuddår søndag,  **\_maxDate** er mars 13, som er  **\_firstDayInView** + 40 dager.) Det betyr at hvis en bruker ikke har valgt denne måneden ennå,  **\_maxDate** er større enn den nye  **\_lastDayOfMonth**, og den **Hvis** funksjonen Returnerer **SANN**. De koden kjøringene, og en samling og en variabel oppdateres:

    - **MyCalendarEvents** henter hendelser fra den valgte kalenderen med den [Office365.GetEventsCalendarViewV2](https://docs.microsoft.com/connectors/office365/#get-calendar-view-of-events--v2-) operasjonen. Datoområdet er mellom  **\_maxDate** + 1 dag og  **\_firstDayInView** + 40 dager. Fordi **MyCalendarEvents** allerede inneholder hendelser på den  **\_minDate** dato, 1 legges til denne datoen for den minste verdien i denne nye datoområdet. **\_firstDayInView** + 40 er formelen for  **\_maxDate**, slik at den andre datoen i området er bare den nye  **\_maxDate**.

    - **\_maxDate** er satt til  **\_firstDayInView** + 40 dager siden dette er den siste dagen for hvilke hendelser som er hentet. Hvis en bruker kommer tilbake til denne datoen ved å velge neste måned vinkeltegnet, den **Hvis** -funksjonen returnerer **USANN**; koden ikke kjøres fordi hendelser for denne visningen er allerede hurtigbufret i  **MyCalendarEvents**.

## <a name="calendar-gallery"></a>Kalender-galleriet

![MonthDayGallery kontroll](media/calendar-screen/calendar-month-gall.png)

- Egenskap: **Elementer**<br>
    Verdi: `[0,1,2,3,4,5,6,7,8,9,10,11,12,13,14,15,16,17,18,19,
    20,21,22,23,24,25,26,27,28,29,30,31,32,33,34,35,36,37,38,39,40,41]`
  
  Settet med 0 til 41 brukes for elementene i galleriet kalenderen fordi, i verste scenario, får Kalender-visningen til å vise 42 full dager. Dette skjer når først dagen i måneden forekommer på en lørdag og sist av måneden forekommer på en søndag. I dette tilfellet vises i kalenderen seks dager fra den forrige måneden i raden som inneholder først dagen i måneden og seks dager fra neste måned i raden som inneholder siste i måneden. Dette er 42 unike verdier, som 30 er for den valgte måneden.

- Egenskap: **WrapCount**<br>
    Verdi: `7`

  Denne verdien gjenspeiler sju dager i uken.

### <a name="title-control-in-the-calendar-gallery"></a>Tittel-kontroll i galleriet for kalender

![MonthDayGallery tittel kontroll](media/calendar-screen/calendar-month-text.png)

- Egenskap: **Tekst**<br>
    Verdi: `Day( DateAdd( _firstDayInView, ThisItem.Value, Days ) )`

    Tilbakekall som  **\_firstDayInView** er definert som (**\_firstDayOfMonth** -verdien ukedag) + 1. Dette forteller deg at  **\_firstDayInView** er alltid en søndag, og  **\_firstDayOfMonth** er alltid i den første raden i **MonthDayGallery**. På grunn av disse to fakta,  **\_firstDayInView** er alltid i den første cellen i **MonthDayGallery**. **ThisItem.Value** er nummeret for denne cellen i den **MonthDayGallery** elementet egenskapen. I så fall å ta  **\_firstDayInView** som et utgangspunkt, viser hver celle tidsintervall  **\_firstDayInView** + sine respektive celleverdien.

- Egenskap: **Fyll**<br>
    Verdi: Én **Hvis** funksjonen:

    ```powerapps-dot
    If( DateAdd( _firstDayInView, ThisItem.Value ) = Today() && 
                DateAdd( _firstDayInView, ThisItem.Value ) = _dateSelected, 
            RGBA( 0, 0, 0, 0 ),
        DateAdd( _firstDayInView, ThisItem.Value) = Today(), 
            ColorFade( Subcircle.Fill, 0.67 ),
        Abs( Title.Text - ThisItem.Value) > 10,
            RGBA( 200, 200, 200, 0.3 ),
        RGBA( 0, 0, 0, 0 )
    )
    ```

  Som beskrevet i beskrivelsen av den **tekst** -egenskapen, `DateAdd(_firstDayInView, ThisItem.Value)` representerer dagen i visible-cellen. Å ta dette i betraktning, utfører foregående kode disse sammenligningene:
  1. Hvis celleverdien er dagens dato, og denne cellen tilsvarer  **\_dateSelected**, ikke gir en fyll-verdi.
  1. Hvis celleverdien er dagens dato, men tilsvarer ikke  **\_dateSelected**, gi den **ColorFade** fyll.
  1. Siste sammenligningen er ikke så tydelig. Det er en sammenligning mellom faktiske tekstverdien i cellen, og verdien av celle-elementet (hvor på skjermen), og hvor elementet.<br>

      Til å bedre forstå dette vurdere. September 2018, en måned som starter på en lørdag og slutter på en søndag. I dette tilfellet viser kalenderen 26th gjennom 31 August og 1 av September i den første raden, og `Abs(Title.Text - ThisItem.Value) = 26` frem til 1. September. Deretter `Abs(Title.Text - ThisItem.Value) = 5`. Det blir værende på 5 frem til den siste raden i kalenderen, som viser 30. September og 1. oktober gjennom 6th. Ved at `Abs(Title.Text - ThisItem.Value)` vil fortsatt være 5 for 30. September, men vil ikke 35 for oktober datoene.<br>

      Dette er mønsteret: For dagene som vises fra forrige måned, `Abs(Title.Text - ThisItem.Value)` alltid vil være lik den `Title.Text` verdien for den første dagen på skjermen. Dagene som vises i neste måned, `Abs(Title.Text - ThisItem.Value)` alltid vil være lik den **MonthDayGallery** elementet verdien for den første cellen i den måneden (i dette tilfellet oktober 1) minus 1. Og viktigst av alt, for dagene som vises i den valgte måneden, `Abs(Title.Text - ThisItem.Value)` vil også alltid være lik verdien for det første elementet i den måneden minus 1 og er aldri større enn 5, som vist i forrige eksempel. Slik at det er helt gyldig skrive formelen som `Abs(Title.Text - ThisItem.Value) > 5`.

      Denne setningen kontrollerer om date-verdien er utenfor den valgte måneden. Hvis det er, **Fyll** er en delvis ugjennomsiktig grå.

    > [!NOTE]
    > Du kan kontrollere gyldigheten av denne siste sammenligningen selv ved å sette inn en **etikett** kontroll i galleriet og innstillingen sin **tekst** egenskapen til denne verdien:<br>`Abs(Title.Text - ThisItem.Value)`.

- Egenskap: **Synlig**<br>
    Verdi:

    ```powerapps-dot
    !(
        DateAdd( _firstDayInView, ThisItem.Value, Days ) - 
            Weekday( DateAdd( _firstDayInView, ThisItem.Value,Days ) ) + 1 
        > _lastDayOfMonth
    )
    ```

    Den foregående setningen kontrollerer om cellen er i en rad der noen dager i måneden som for øyeblikket er valgt forekommer. Tilbakekalling som å trekke ukedag verdien i en dag fra datoverdien og legge til 1 alltid returnerer det første elementet i raden den dagen bor i. Slik at denne setningen kontrollerer om den første dagen i raden er etter den siste dagen i måneden som kan vises. Hvis det er, vises den ikke fordi hele raden inneholder dager i måneden.

- Egenskap: **OnSelect**<br>
    Verdi: A **angi** -funksjonen, som angir den  **\_dateSelected** variabel til datoen i den valgte cellen:

    ```powerapps-dot
    Set( _dateSelected, DateAdd( _firstDayInView, ThisItem.Value, Days ) )
    ```

### <a name="circle-control-in-the-calendar-gallery"></a>Sirkel-kontroll i galleriet for kalender

![MonthDayGallery sirkel kontroll](media/calendar-screen/calendar-month-event.png)

- Egenskap: **Synlig**<br>
    Verdi: En formel som bestemmer om hendelser som er planlagt for den valgte datoen og om den **Subcircle** og **tittel** kontrollene er synlig:

    ```powerapps-dot
    CountRows(
        Filter( MyCalendarEvents, 
            DateValue( Text( Start ) ) = DateAdd( _firstDayInView, ThisItem.Value, Days )
        )
    ) > 0 && !Subcircle.Visible && Title.Visible
    ```

    Den **sirkel** kontrollen er synlig hvis den **Start** feltet for en hendelse er tilsvarer datoen for cellen, hvis den **tittel** kontrollen er synlig, og hvis den  **Subcircle** kontrollen ikke vises. Med andre ord, er denne kontrollen synlig når minst én hendelse forekommer på denne dagen, og ikke er merket av for denne dagen. Hvis den er valgt, vises hendelsene for den aktuelle dagen i den **CalendarEventsGallery** kontroll.

### <a name="subcircle-control-in-the-calendar-gallery"></a>Subcircle kontroll i galleriet for kalender

![MonthDayGallery Subcircle kontroll](media/calendar-screen/calendar-month-selected.png)

- Egenskap: **Synlig**<br>
    Verdi:

    ```powerapps-dot
    DateAdd( _firstDayInView, ThisItem.Value ) = _dateSelected && Title.Visible
    ```

  Den **Subcircle** kontrollen er synlig når  **\_dateSelected** tilsvarer datoen for cellen, og den **tittel** kontrollen er synlig. Med andre ord, vises denne kontrollen når cellen er gjeldende valgte dato.

## <a name="events-gallery"></a>Hendelser galleri

![CalendarEventsGallery kontroll](media/calendar-screen/calendar-events-gall.png)

- Egenskap: **Elementer**<br>
    Verdi: En formel som sorterer og filtrerer galleriet hendelser:

    ```powerapps-dot
    SortByColumns(
        Filter( MyCalendarEvents,
            Text( Start, DateTimeFormat.ShortDate ) = Text( _dateSelected, DateTimeFormat.ShortDate )
        ),
        "Start"
    )
    ```

   Den **MyCalendarEvents** samlingen inneholder alle hendelser mellom  **\_minDate** og  **\_maxDate**. For å kunne vise hendelsene for bare datoen som er valgt, et filter på **MyCalendarEvents** til å vise hendelser som har en startdato tilsvarer **\ _dateSelected**. Elementene er sorteres etter deres startdatoer for å ordne dem i sekvensiell rekkefølge.

## <a name="next-steps"></a>Neste trinn

- [Finn ut mer om denne skjermen](./calendar-screen-overview.md)
- [Finn ut mer om Office 365 Outlook connector i PowerApps](../connections/connection-office365-outlook.md)
- [Finn ut mer om Office 365-brukere-kobling i PowerApps](../connections/connection-office365-users.md)
