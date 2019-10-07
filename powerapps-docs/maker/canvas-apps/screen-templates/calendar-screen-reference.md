---
title: Referanse til malen kalender-skjerm for lerret apper | Microsoft Docs
description: Få informasjon om hvordan malen kalender-skjerm for lerret apps fungerer i PowerApps.
author: emcoope-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 12/31/2018
ms.author: emcoope
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: b9e5425244d819816fa05c4b780a6be092b0d22c
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/07/2019
ms.locfileid: "71995711"
---
# <a name="reference-information-about-the-calendar-screen-template-for-canvas-apps"></a>Referanse informasjon om malen kalender-skjerm for lerret apps

For å få en lerret-app i PowerApps kan du forstå hvordan hver omfattende kontroll i kalenderen i Kalender-skjermen bidrar til skjermens generelle standard funksjon. Denne dype forhandlingen presenterer virke måte formlene og verdiene til andre egenskaper som bestemmer hvordan kontrollene svarer på bruker inn data. Hvis du vil ha en høy nivå diskusjon av denne skjermens standard funksjon, kan du se [Oversikt over kalender-skjermen](calendar-screen-overview.md).

Dette emnet uthever noen viktige kontroller og forklarer uttrykkene eller formlene som ulike egenskaper (for eksempel **elementer** og **OnSelect**) til disse kontrollene er angitt for:

- [Kalender-rulle gardin listen (dropdownCalendarSelection)](#calendar-drop-down)
- [Kalender ikon (iconCalendar)](#calendar-icon)
- [Vinkel på forrige måned (iconPrevMonth)](#previous-month-chevron)
- [Vinkel på neste måned (iconNextMonth)](#next-month-chevron)
- [Kalender galleri (MonthDayGallery) (+ underordnede kontroller)](#calendar-gallery)
- [Hendelses galleri (CalendarEventsGallery)](#events-gallery)

## <a name="prerequisite"></a>Nødvendig

Kjennskap til hvordan du legger til og konfigurerer skjermer og andre kontroller mens du [oppretter en app i powerapps](../data-platform-create-app-scratch.md).

## <a name="calendar-drop-down"></a>Rulle gardin liste for kalender

![dropdownCalendarSelection-kontroll](media/calendar-screen/calendar-dropdown.png)

- Gjelder **Elementene**<br>
    Verdi: `Office365.CalendarGetTables().value`

    Denne verdien er en koblings operasjon som henter appens brukerens Outlook-kalendere. Du kan se [verdien](https://docs.microsoft.com/connectors/office365/#entitylistresponse[table]) som denne operasjonen henter.

- Gjelder **OnChange**<br>Verdi: `Select(dropdownCalendarSelection)`

    Når brukeren velger et alternativ i listen, kjører funksjonen i kontrollens **OnSelect** -egenskap.

- Gjelder **OnSelect**<br>
    Revaluer En **IF** -funksjon, som vises i følgende kode blokk, og flere ekstra funksjoner, som vises i kode blokken etter dette.

   Denne delen av formelen kjører bare første gang brukeren velger et alternativ i rulle gardin listen etter å ha åpnet appen:

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

    Den foregående koden definerer følgende variabler:
    
  - **@no__t – 1userDomain**: Program brukerens firma domene, som gjenspeilet i brukerens e-postadresse.
  - **@no__t – 1dateSelected**: Dagens dato (som standard). Kalender galleriet uthever denne datoen, og hendelses galleriet viser hendelsene som er planlagt for denne datoen.
  - **@no__t – 1firstDayOfMonth**: Den første dagen i gjeldende måned. Fordi `(Today + (1 - Today)) = Today - Today + 1 = 1`, returnerer denne **DateAdd** -funksjonen alltid den første dagen i måneden.
  - **@no__t – 1firstDayInView**: Den første dagen kalender galleriet kan vise. Denne verdien er ikke den samme som den første dagen i måneden, med mindre måneden begynner på søndag. For å unngå å vise en hel uke i forrige måned, er verdien for **\_firstDayInView** `_firstDayOfMonth - Weekday(_firstDayOfMonth) + 1`.
  - **@no__t – 1lastDayOfMonth**: Den siste dagen i gjeldende måned, som er den samme som den første dagen i neste måned, minus én dag.

   Funksjonene etter **IF** -funksjonen kjører når brukeren velger et alternativ i rulle gardin listen for kalender (ikke bare første gang brukeren åpner appen):

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

    Den foregående koden definerer disse variablene og én samling:

    - **@no__t – 1calendarVisible**: Settes til **False** , slik at kalenderen ikke vises mens det nye valget er lastet inn.
    - **@no__t – 1showLoading**: Satt til **sann** , slik at innlastings indikatorer vises mens det nye valget lastes inn.
    - **@no__t – 1myCalendar**: Settes til gjeldende verdi i **rulle gardin** listen for en kalender, slik at hendelser fra den riktige kalenderen hentes.
    - **@no__t – 1minDate**: Satt til samme verdi som **\_firstDayInView**. Denne variabelen bestemmer hvilke hendelser som allerede er Hentet fra Outlook og hurtigbufres i appen.
    - **@no__t – 1maxDate**: Sett til siste synlige dag i kalenderen. Formelen er `_firstDayInView + 40`. Kalenderen viser maksimalt 41 dager, slik at **\_maxDate** variabel alltid gjenspeiler den siste visnings dagen, og avgjør hvilke hendelser som allerede er Hentet fra Outlook og hurtigbufres i appen.
    - **MyCalendarEvents**: Sett til en samling av brukerens hendelser fra den valgte kalenderen, fra **\_minDate** til **\_maxDate**.
    - **@no__t – 1showLoading**: Satt til **Usann**. **\_calendarVisible** er satt til **sann** når alt annet er lastet inn.

## <a name="calendar-icon"></a>Kalender-ikon

![iconCalendar-kontroll](media/calendar-screen/calendar-today-icon.png)

- Gjelder **OnSelect**<br>
    Revaluer Fire **Sett** funksjoner som tilbakestiller kalender galleriet til dagens dato:

    ```powerapps-dot
    Set( _dateSelected, Today() );
    Set( _firstDayOfMonth, DateAdd( Today(), 1 - Day( Today() ), Days) );
    Set( _firstDayInView, DateAdd(_firstDayOfMonth, -(Weekday( _firstDayOfMonth ) - 2 + 1), Days));
    Set( _lastDayOfMonth, DateAdd( DateAdd( _firstDayOfMonth, 1, Months ), -1, Days ) )
    ```

    Den foregående koden tilbakestiller alle dato variabler som er nødvendige for å vise den riktige Kalender visningen:

    - **\_dateSelected** tilbakestilles til i dag.
    - **\_firstDayOfMonth** tilbakestilles til den første dagen i dagens måned.
    - **\_firstDayInView** tilbakestilles til første dag som vises når dagens måned er valgt.
    - **\_lastDayOfMonth** tilbakestilles til den siste dagen i dagens måned.

    I [**rulle gardin delen kalender**](#calendar-drop-down) i dette emnet forklares disse variablene mer detaljert.

## <a name="previous-month-chevron"></a>Vinkel på forrige måned

![iconPrevMonth-kontroll](media/calendar-screen/calendar-back.png)

- Gjelder **OnSelect**<br>Revaluer Fire **Set** -funksjoner og en **IF** -funksjon som viser forrige måned i Kalender galleriet:

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
    > Definisjoner for **\_firstDayOfMonth**, **\_firstDayInView**og **\_lastDayOfMonth** er nesten identiske med dem i [rulle gardin](#calendar-drop-down) delen for kalender i dette emnet.

    De tre første linjene av koden ovenfor kjøres hver gang brukeren velger vinkel tegnet forrige måned. Koden angir variablene som er nødvendige for å vise den riktige Kalender visningen. Den gjenværende koden kjører bare hvis brukeren ikke tidligere har valgt denne måneden for den valgte kalenderen.

    Hvis dette er tilfellet, **\_minDate** er den første dagen som vises når den forrige måneden vises. **@No__t-1minDate** har en minimums verdi for 23rd for den gjeldende måneden før brukeren velger ikonet. (Når 1. mars faller på en lørdag, er **\_firstDayInView** for mars 23. februar) Dette betyr at hvis en bruker ikke har valgt denne måneden ennå, **\_minDate** er større enn den nye **\_FirstDayOfMonth**, og **Hvis** -funksjonen returnerer **True**. Koden kjøres, og en samling og en variabel blir oppdatert:

    - **MyCalendarEvents** henter hendelser fra den valgte kalenderen med [office365. GetEventsCalendarViewV2](https://docs.microsoft.com/connectors/office365/#get-calendar-view-of-events--v2-) -operasjonen. Dato området er mellom **@no__t 1firstDayInView** dato og **\_minDate** -1. Fordi **MyCalendarEvents** allerede inneholder hendelser på **\_minDate-** datoen, trekkes 1 fra den datoen for maksimums verdien i dette nye dato området.

    - **\_minDate** er satt til gjeldende **\_firstDayInView** , fordi dette er den første datoen som hendelser er Hentet fra. Hvis en bruker returnerer til denne datoen ved å velge vinkel parentesen forrige måned, returnerer **IF** -funksjonen **Usann**. koden kjører ikke fordi hendelser for denne visningen allerede er bufret i **MyCalendarEvents**.

## <a name="next-month-chevron"></a>Vinkel på neste måned

![iconNextMonth-kontroll](media/calendar-screen/calendar-forward.png)

- Gjelder **OnSelect**<br>
    Revaluer Fire **Set** -funksjoner og en **IF** -funksjon som viser neste måned i Kalender galleriet:

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
    > Definisjoner for **\_firstDayOfMonth**, **\_firstDayInView**og **\_lastDayOfMonth** er nesten identiske med dem i [rulle gardin](#calendar-drop-down) delen for kalender i dette emnet.

    De tre første linjene av den foregående koden, som kjøres når brukeren velger vinkel tegn på neste måned, angir variablene som er nødvendige for å vise den riktige Kalender visningen. Den gjenværende koden kjører bare hvis brukeren ikke tidligere har valgt denne måneden for den valgte kalenderen.

    I dette tilfellet er **\_maxDate** den siste dagen som vises når den forrige måneden vises. **@No__t-1maxDate** har en maksimums verdi for 13th i neste måned før brukeren velger vinkel tegn neste måned. (Når 1. februar faller på et år søndag, er **\_maxDate** 13. mars, som er **@no__t 3firstDayInView** + 40 dager.) Dette betyr at hvis en bruker ikke har valgt denne måneden ennå, **\_maxDate** er større enn den nye **\_LastDayOfMonth**, og **Hvis** -funksjonen returnerer **True**. Koden kjøres, og en samling og en variabel blir oppdatert:

    - **MyCalendarEvents** henter hendelser fra den valgte kalenderen med [office365. GetEventsCalendarViewV2](https://docs.microsoft.com/connectors/office365/#get-calendar-view-of-events--v2-) -operasjonen. Dato området er mellom **\_maxDate** + 1 dag og **\_firstDayInView** + 40 dager. Fordi **MyCalendarEvents** allerede inneholder hendelser i **\_minDate** date, legges 1 til denne datoen for minimums verdien i dette nye dato området. **\_firstDayInView** + 40 er formelen for **\_maxDate**, så den andre datoen i området er bare den nye **\_maxDate**.

    - **\_maxDate** er satt til **\_firstDayInView** + 40 dager fordi dette er den siste dagen som hendelser er Hentet fra. Hvis en bruker returnerer til denne datoen ved å velge vinkel parentesen neste måned, returnerer **IF** -funksjonen **Usann**. koden kjører ikke fordi hendelser for denne visningen allerede er bufret i **MyCalendarEvents**.

## <a name="calendar-gallery"></a>Kalender galleri

![MonthDayGallery-kontroll](media/calendar-screen/calendar-month-gall.png)

- Gjelder **Elementene**<br>
    Verdi: `[0,1,2,3,4,5,6,7,8,9,10,11,12,13,14,15,16,17,18,19,
    20,21,22,23,24,25,26,27,28,29,30,31,32,33,34,35,36,37,38,39,40,41]`
  
  Settet mellom 0 og 41 brukes for elementene i Kalender galleriet, fordi i det verste tilfellet vil Kalender-visningen vise 42 hel dager. Dette forekommer når den første av måneden forekommer på en lørdag, og den siste måneden forekommer på en søndag. I dette tilfellet viser kalenderen seks dager fra den forrige måneden i raden som inneholder den første dagen i måneden, og seks dager fra måneden som inneholder den siste dagen i måneden. Dette er 42 unike verdier som 30 er for den valgte måneden.

- Gjelder **WrapCount**<br>
    Verdi: `7`

  Denne verdien gjenspeiler en sju dagers uke.

### <a name="title-control-in-the-calendar-gallery"></a>Tittel-kontrollen i Kalender galleriet

![MonthDayGallery tittel-kontroll](media/calendar-screen/calendar-month-text.png)

- Gjelder **Tekst**<br>
    Verdi: `Day( DateAdd( _firstDayInView, ThisItem.Value, Days ) )`

    Tilbake kall at **\_firstDayInView** er definert som ( **\_firstDayOfMonth** -sin ukedag-verdi) + 1. Dette forteller deg at **\_firstDayInView** alltid er en søndag, og at **\_firstDayOfMonth** alltid er i den første raden i **MonthDayGallery**. På grunn av disse to faktaene er **\_firstDayInView** alltid i veldig første celle i **MonthDayGallery**. **ThisItem. Value** er tallet for denne cellen i egenskapen **MonthDayGallery** element. Hvis du tar **\_firstDayInView** som et utgangs punkt, viser hver celle økningen av **\_firstDayInView** + dens respektive celle verdi.

- Gjelder **Feltene**<br>
    Revaluer En **IF** -funksjon:

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

  Som beskrevet i beskrivelsen av **tekst** -egenskapen, representerer `DateAdd(_firstDayInView, ThisItem.Value)` dagen i den synlige cellen. Hvis du tar dette inn i kontoen, utfører den foregående koden disse sammenligningene:
  1. Hvis celle verdien er dagens dato og denne cellen tilsvarer **\_dateSelected**, må du ikke oppgi en fyll verdi.
  1. Hvis celle verdien er dagens dato, men ikke tilsvarer **\_dateSelected**, oppgir du **ColorFade** -fyllet.
  1. Den siste sammenligningen er ikke som klar. Det er en sammenligning mellom den faktiske tekst verdien i cellen og verdien for celle elementet (tallet som vises og element nummeret).<br>

      For å forstå dette, bør du vurdere september 2018, en måned som starter på en lørdag og slutter på en søndag. I dette tilfellet viser kalenderen 26th gjennom 31 august og 1. september i første rad, og `Abs(Title.Text - ThisItem.Value) = 26` til og med 1. september. @No__t-0. Den forblir på 5 til den siste raden i kalenderen, som viser 30. september og 1. oktober til 6. @No__t – 0 vil fremdeles være 5 for 30. september, men vil være 35 for oktober-datoene.<br>

      Dette er mønsteret: For dager som vises fra forrige måned, `Abs(Title.Text - ThisItem.Value)` alltid lik `Title.Text`-verdien for den første dagen som vises. @No__t-0 for dager som vises i neste måned, vil alltid være lik **MonthDayGallery** element-verdien for den første cellen i måneden (i dette tilfellet, oktober) minus 1. Og det meste viktiget, for dager som vises i den valgte måneden, `Abs(Title.Text - ThisItem.Value)`, vil også alltid være lik verdien for det første elementet i måneden minus 1 og vil aldri overskride 5, som det forrige eksemplet viser. Så det er helt gyldig å skrive formelen som `Abs(Title.Text - ThisItem.Value) > 5`.

      Denne erklæringen kontrollerer om dato verdien er utenfor den valgte måneden. Hvis det er tilfellet, er **Fyll** en delvis ugjennomsiktig grå.

    > [!NOTE]
    > Du kan kontrollere gyldigheten til denne siste sammenligningen for deg selv ved å sette inn en **etikett** -kontroll i galleriet og angi **tekst** -egenskapen til denne verdien:<br>`Abs(Title.Text - ThisItem.Value)`.

- Gjelder **Tydelig**<br>
    Revaluer

    ```powerapps-dot
    !(
        DateAdd( _firstDayInView, ThisItem.Value, Days ) - 
            Weekday( DateAdd( _firstDayInView, ThisItem.Value,Days ) ) + 1 
        > _lastDayOfMonth
    )
    ```

    Oven stående setning kontrollerer om cellen er i en rad der ingen dager av den valgte måneden inntreffer. Tilbake kalling av at verdien for ukedagen for en dag fra dato-verdien og legges til, returnerer alltid det første elementet i raden som bor i. Dette utsagnet kontrollerer om den første dagen i raden er etter den siste dagen i den viste måneden. Hvis det er tilfellet, vises den ikke fordi hele raden inneholder dager i følgende måned.

- Gjelder **OnSelect**<br>
    Revaluer En **Set** -funksjon som angir den **@no__t 2dateSelected-** variabelen til datoen for den valgte cellen:

    ```powerapps-dot
    Set( _dateSelected, DateAdd( _firstDayInView, ThisItem.Value, Days ) )
    ```

### <a name="circle-control-in-the-calendar-gallery"></a>Sirkel kontroll i Kalender galleriet

![MonthDayGallery sirkel-kontroll](media/calendar-screen/calendar-month-event.png)

- Gjelder **Tydelig**<br>
    Revaluer En formel som bestemmer om eventuelle hendelser er planlagt for den valgte datoen, og om under **sirkel** -og **Tittel** kontrollene er synlige:

    ```powerapps-dot
    CountRows(
        Filter( MyCalendarEvents, 
            DateValue( Text( Start ) ) = DateAdd( _firstDayInView, ThisItem.Value, Days )
        )
    ) > 0 && !Subcircle.Visible && Title.Visible
    ```

    **Sirkel** kontrollen er synlig hvis **Start** -feltet for en hvilken som helst hendelse tilsvarer datoen for denne cellen, hvis **Tittel** -kontrollen er synlig, og hvis **delsirkel** -kontrollen ikke er synlig. Denne kontrollen er med andre ord synlig når minst én hendelse forekommer på denne dagen, og denne dagen er ikke valgt. Hvis det er merket av for dette, vises hendelsene for den dagen i **CalendarEventsGallery** -kontrollen.

### <a name="subcircle-control-in-the-calendar-gallery"></a>Under sirkel kontroll i Kalender galleriet

![MonthDayGallery under sirkel kontroll](media/calendar-screen/calendar-month-selected.png)

- Gjelder **Tydelig**<br>
    Revaluer

    ```powerapps-dot
    DateAdd( _firstDayInView, ThisItem.Value ) = _dateSelected && Title.Visible
    ```

  Under **sirkel** kontrollen er synlig når **\_dateSelected** er identisk med datoen for cellen, og **Tittel** -kontrollen er synlig. Denne kontrollen vises med andre ord når cellen er den gjeldende valgte datoen.

## <a name="events-gallery"></a>Hendelses galleri

![CalendarEventsGallery-kontroll](media/calendar-screen/calendar-events-gall.png)

- Gjelder **Elementene**<br>
    Revaluer En formel som sorterer og filtrerer hendelses galleriet:

    ```powerapps-dot
    SortByColumns(
        Filter( MyCalendarEvents,
            Text( Start, DateTimeFormat.ShortDate ) = Text( _dateSelected, DateTimeFormat.ShortDate )
        ),
        "Start"
    )
    ```

   **MyCalendarEvents** -samlingen inneholder alle hendelsene mellom **\_minDate** og **\_maxDate**. Hvis du vil vise hendelser bare for den valgte datoen, brukes et filter på **MyCalendarEvents** for å vise hendelsene som har en start dato som tilsvarer **\ _dateSelected**. Elementene sorteres deretter etter start datoene for å plassere dem i sekvensiell rekkefølge.

## <a name="next-steps"></a>Neste trinn

- [Lær mer om denne skjermen](./calendar-screen-overview.md)
- [Finn ut mer om Office 365 Outlook Connector i PowerApps](../connections/connection-office365-outlook.md)
- [Les mer om Office 365 brukere-koblingen i PowerApps](../connections/connection-office365-users.md)
