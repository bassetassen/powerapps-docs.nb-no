---
title: Å vise tekst og formatere en dato eller et klokkeslett | Microsoft Docs
description: Å legge til og formatere datoer og klokkeslett ved hjelp av PowerApps
documentationcenter: ''
author: AFTOwen
manager: kfile
editor: ''
ms.service: powerapps
ms.devlang: na
ms.topic: conceptual
ms.component: canvas
ms.date: 10/16/2016
ms.author: anneta
ms.openlocfilehash: faa8db15596dc0da0d5b5638f5dd9c334517fc7c
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/04/2018
ms.locfileid: "32330955"
---
# <a name="show-text-and-format-dates-and-times-in-powerapps"></a>Å vise tekst og formatere datoer og klokkeslett i PowerApps
Legg til datoer og klokkeslett, og formater dem for å vise det riktige detaljnivået eller for å gjenspeile de nasjonale innstillingene. Å beregne tidsrommet mellom to datoer, eller beregne en dato som er en viss tid før eller etter en dato du angir. Konverter datoer til eller fra separate verdier for dager, måneder og år, og konvertere klokkeslett til eller fra separate verdier for timer, minutter og sekunder.

For eksempel kan du legge til data fra brukere om lagerbeholdning eller kundemøter, data fra en ekstern kilde, eller data fra et annet program som er opprettet i PowerApps. Rund av til nærmeste minutt for enkelhets skyld, hvis dataene inneholder klokkeslett ned til millisekund. Beregn hvor mange dager som står igjen før en viktig milepæl. Hvis du vil planlegge møter hver femte dag, kan du automatisk beregne disse datoene. Hvis 10. mai 1985 lagres i separate felt for dagen, måneden og året, kan du konsolidere dem til en enkelt verdi. Og motsatt kan du også skille hver dato til separate verdier, hvis appen din administrerer dem separat.

## <a name="prerequisites"></a>Forutsetninger

* [Registrer deg](../signup-for-powerapps.md) for PowerApps, og deretter [logger du deg på](https://web.powerapps.com) ved å angi samme legitimasjon som du brukte til å registrere deg.
* Opprett en app eller åpne en eksisterende app i PowerApps.
* Finn ut hvordan du kan [konfigurere en kontroll](add-configure-controls.md) i PowerApps.

## <a name="show-text-in-a-label-control"></a>Å vise teksten i en Etikettkontroll
Vis teksten i en **[Etikett](controls/control-text-box.md)**-kontroll ved å angi verdien for **[Tekst](controls/properties-core.md)**-egenskapen. Angi denne egenskapen ved å skrive direkte inn i kontrollen, eller ved å skrive inn et uttrykk i formellinjen.

* Hvis du skriver direkte inn i kontrollen, vil den vise nøyaktig hva du skriver.
* Hvis du skriver inn et uttrykk i formellinjen, viser kontrollen resultatet av uttrykket.

Her er noen eksempler.

1. Legg til en **[Etikett](controls/control-text-box.md)**-kontroll med navnet **ShowText**, og angi **[Tekst](controls/properties-core.md)**-egenskapen til denne formelen:
   <br>**Now()**
   
    Hvis datamaskinen er satt til den nasjonale innstillingen «en-us», vil gjeldende dato og klokkeslett vises i dette formatet:  <br>*mm/dd/åååå tt:mm AM/PM*
   
    Hvis datamaskinen er satt til en nasjonal innstilling som for eksempel «fr-fr», vises gjeldende dato og klokkeslett i dette formatet:  <br>*dd/mm/åååå tt:mm AM/PM*
2. Angi **[Tekst](controls/properties-core.md)**-egenskapen for **ShowText** til denne formelen:
   <br>**DateDiff(Today(), DateValue("01/01/2020"))**
   
    ![Antall dager mellom dagens dato og 01. jan. 2020](./media/show-text-dates-times/date-diff-text.png)
   
    Kontrollen viser antall dager mellom i dag og 01. januar 2020 ved hjelp av disse funksjonene:
   
   * **DateDiff**, som beregner antall dager, kvartaler eller år mellom to datoer.
   * **Today**, som beregner den gjeldende dagen som en verdi.
   * **DateValue**, som konverterer en litteral streng, som vist mellom doble anførselstegn, til en verdi der beregninger kan utføres.
3. Legg til en **[Tekstinndata](controls/control-text-input.md)**-kontroll kalt **BirthDate**, og flytt den til under **ShowText**.

4. I **Fødselsdato** skriver du inn måneden og dagen for fødselsdagen din (for eksempel **18/05**).

5. Angi **[Tekst](controls/properties-core.md)**-egenskapen for **ShowText** til denne formelen:
   <br>**DateDiff(Today(), DateValue(BirthDate.Text))**
   
    ![Antall dager mellom i dag og fødselsdagen din](./media/show-text-dates-times/birth-diff.png)
   
    **ShowText** viser antall dager mellom i dag og den datoen du skriver inn i **BirthDate**. Hvis fødselsdagen din allerede har vært i år, vil **ShowText** vise en negativ verdi.

## <a name="format-dates-and-times-by-using-datetimevalue"></a>Å formatere datoer og klokkeslett ved hjelp av DateTimeValue
Konverter datoer og klokkeslett fra tekststrenger til verdier, som du kan formatere på en rekke måter og bruke i beregninger. Angi formatet ved hjelp av innebygde og egendefinerte alternativer.

> [!NOTE]
> **[DateTimeValue](functions/function-datevalue-timevalue.md)** og **[DateValue](functions/function-datevalue-timevalue.md)**-funksjonene kan konvertere datoer i alle disse formatene til verdier:  
> 
> * MM/DD/ÅÅÅÅ  
> * DD/MM/ÅÅÅÅ  
> * DD Måned ÅÅÅÅ  
> * Måned DD, ÅÅÅÅ  
> 
> 

1. Legg til en **[Tekstinndata](controls/control-text-input.md)**-kontroll med navnet **ArrivalDateTime**, og skriv inn en dato og et klokkeslett i dette formatet:
   <br>**10/05/85 06:15:00**
2. Legg til en **[Etikett](controls/control-text-box.md)**-kontroll, kalt **ShowDate**, og angi **[Tekst](controls/properties-core.md)**-egenskapen til denne formelen:
   <br>**DateTimeValue(ArrivalDateTime.Text)**
   
    ![Å konvertere dato/klokkeslett fra tekst til en verdi](./media/show-text-dates-times/date-value.png)
   
    **ShowDate** viser den samme informasjonen som du skrev inn, men den har blitt konvertert fra tekst til en verdi, og formatert på en annen måte. For eksempel vises året med fire sifre i stedet for bare to.
3. Endre **[Tekst](controls/properties-core.md)**-egenskapen for **ShowDate** til denne formelen:
   <br>**DateTimeValue(ArrivalDateTime.Text, "fr")**
   
    ![Å vise en dato/klokkeslett-verdi i fransk format](./media/show-text-dates-times/date-value-fr.png)
   
    **ShowDate** viser dagen før måneden, som en fransk bruker vil forvente.
   
   > [!TIP]
   > Hvis du vil vise en liste over andre nasjonale innstillinger i Intellisense, kan du fjerne det avsluttende anførselstegnet og **fr** fra formelen og la det åpne anførselstegnet stå:
   > 
   > ![Å vise en liste over nasjonale innstillinger](./media/show-text-dates-times/locale-list.png)
   > 
   > 
4. Hvis du vil bruke ett av flere innebygde formater, kan du endre **[Tekst](controls/properties-core.md)**-egenskapen for **ShowDate** til denne formelen:
   <br>**Text(DateTimeValue(ArrivalDateTime.Text), DateTimeFormat.LongDateTime)**
   
    ![Å vise en dato/klokkeslett-verdi i fransk format](./media/show-text-dates-times/long-date-time.png)
   
    **ShowDate** viser dagen i uken, datoen og klokkeslettet.
   
   > [!TIP]
   > **DateTimeFormat**-parameteren støtter flere andre innebygde formater. Du kan fjerne **LongDateTime** fra formelen hvis du vil vise denne listen.
   > 
   > 
5. Hvis du vil bruke et egendefinert format, kan du endre **[Tekst](controls/properties-core.md)**-egenskapen for **ShowDate** til denne formelen:
   <br>**Text(DateTimeValue(ArrivalDateTime.Text), "mm/dd/yyyy hh:mm:ss.fff AM/PM")**
   
    ![Å vise en dato/klokkeslett-verdi i fransk format](./media/show-text-dates-times/format-milliseconds.png)
   
    **ShowDate** viser dato/klokkeslett-verdien i formatet som du har angitt, inkludert millisekunder.
   
   > [!TIP]
   > Hvis du vil runde av tiden til nærmeste tiende- eller hundredelen av et sekund, kan du angi **hh:mm:ss.f** eller **hh:mm:ss.ff** i formelen.
   > 
   > 

## <a name="format-a-date-by-using-datevalue"></a>Å formatere en dato ved hjelp av DateValue

1. Legg til en **[Tekstinndata](controls/control-text-input.md)**-kontroll, kalt **ArrivalDate**, og skriv deretter inn en dato i den (for eksempel **10/05/85**).

2. Legg til en **[Etikett](controls/control-text-box.md)**-kontroll, kalt **FormatDate**, og angi **[Tekst](controls/properties-core.md)**-egenskapen til denne formelen:
   <br>**DateValue(ArrivalDate.Text)**
   
    **FormatDate** viser datoen du skrev inn, bortsett fra at året vises med fire sifre.
3. Angi **[Tekst](controls/properties-core.md)**-egenskapen for **FormatDate** til denne formelen:
   <br>**DateValue(ArrivalDate.Text, "fr")**
   
    **FormatDate** viser dagen før måneden, akkurat som en fransk bruker vil forvente.
4. Hvis du vil bruke ett av flere innebygde formater, kan du angi **[Tekst](controls/properties-core.md)**-egenskapen for **FormatDate** til denne formelen:
   <br>**Text(DateValue(ArrivalDate.Text), DateTimeFormat.LongDate)**
   
    **FormatDate** viser dagen i uken, måneden, dagen og året.
5. Hvis du vil bruke et egendefinert format, kan du angi **[Tekst](controls/properties-core.md)**-egenskapen for **FormatDate** til denne formelen:
   <br>**Text(DateValue(ArrivalDate.Text), "yy/mm/dd")**
   
    **FormatDate** viser datoen i formatet som du har angitt.

## <a name="format-a-time-using-datetimevalue"></a>Å formatere et klokkeslett ved å bruke DateTimeValue

1. Legg til en **[Tekstinndata](controls/control-text-input.md)**-kontroll, kalt **ArrivalTime**, og skriv deretter inn **06:15:00** i den.

2. Legg til en **[Etikett](controls/control-text-box.md)**-kontroll kalt **ShowTime**.

3. Hvis du vil bruke ett av flere innebygde formater, kan du angi **[Tekst](controls/properties-core.md)**-egenskapen for **ShowTime** til denne formelen:
   <br>**Text(DateTimeValue(ArrivalTime.Text), DateTimeFormat.LongTime)**
   
    **ShowTime** viser tiden du angav, inkludert sekunder.
4. Hvis du vil bruke et egendefinert format, kan du angi **[Tekst](controls/properties-core.md)**-egenskapen for **ShowTime** til denne formelen:
   <br>**Text(DateTimeValue(ArrivalTime.Text), "hh:mm:ss.fff AM/PM")**
   
    **ShowTime** viser tiden du angav, inkludert sekunder og millisekunder.
   
   > [!TIP]
   > Hvis du vil runde av tiden til nærmeste tiende- eller hundredel av et sekund, kan du angi **hh:mm:ss.f**, eller **hh:mm:ss.ff** i formelen.
   > 
   > 

## <a name="show-the-time-between-dates"></a>Å vise tiden mellom datoer

1. Legg til to **[Tekstinndata](controls/control-text-input.md)** kontroller, kalt **Start** og **Slutt**.

2. Skriv inn **1/4/2015** i **Start**, og skriv inn **1/1/2016** i **Slutt**.

3. Legg til en **[Etikett](controls/control-text-box.md)**-kontroll, kalt **DateDiff**, og angi **[Tekst](controls/properties-core.md)**-egenskapen til denne formelen:
   <br>**DateDiff(DateValue(Start.Text), DateValue(End.Text))**
   
    ![Å sammenligne to datoer](./media/show-text-dates-times/date-diff.png)
   
    **DateDiff** viser **275**, som er antall dager mellom 01. apr. 2015 og 01. jan. 2016.
4. Angi **[Tekst](controls/properties-core.md)**-egenskapen for **DateDiff** til denne formelen:  <br>**DateDiff(DateValue(Start.Text), DateValue(End.Text), måneder)**
   
    **DateDiff** viser **9**, som er antall måneder mellom 01. apr. 2015 og 1. jan. 2016. Erstatt **Måneder** med **Kvartaler**, eller **År** for å vise tiden i disse enhetene.

## <a name="identify-a-date-before-or-after-another-date"></a>Å identifisere en dato før eller etter en annen dato

1. Legg til en **[Tekstinndata](controls/control-text-input.md)**-kontroll, kalt **Start**, og skriv inn **10/05/1985** i den.

2. Legg til en **[Etikett](controls/control-text-box.md)**-kontroll kalt **DateAdd**, og angi **[Tekst](controls/properties-core.md)**-egenskapen til denne formelen:
   <br>**DateAdd(DateValue(Start.Text), 3)**
   
    ![Å legge til tre dager](./media/show-text-dates-times/date-add.png)
   
    **DateAdd** viser **13/05/1985**, som er tre dager etter datoen i **Start**.
3. Angi **[Tekst](controls/properties-core.md)**-egenskapen for **DateAdd** til denne formelen:
   <br>**DateAdd(DateValue(Start.Text), -3)**
   
    ![Å trekke fra tre dager](./media/show-text-dates-times/date-subtract.png)
   
    **DateAdd** viser **07/05/1985**, som er tre dager før datoen i **Start**.
4. Endre **[Tekst](controls/properties-core.md)**-egenskapen for **DateAdd** til denne formelen:
   <br>**DateAdd(DateValue(Start.Text), 3, Months)**
   
    ![Å legge til tre måneder](./media/show-text-dates-times/date-add-months.png)
   
    Etiketten viser **10/08/1985**, som er tre måneder etter datoen i **Start**. Erstatt **Måneder** med **Kvartaler** eller **År** for å identifisere en dato som er det angitte antallet kvartal eller år før eller etter datoen i **Start**.

## <a name="calculate-dates-based-on-years-months-and-days"></a>Å beregne datoer basert på år, måneder og dager

1. Legg til tre **[Rullegardin](controls/control-drop-down.md)**-kontroller, kalt **År**, **Måned** og **Dag**.

2. Angi **[Element](controls/properties-core.md)**-egenskapen for **År** til denne formelen:
   <br>**Table({Year:"2014"}, {Year:"2015"}, {Year:"2016"})**

3. Angi **[Element](controls/properties-core.md)**-egenskapen for **Måned** til denne formelen:
   <br>**Table({Month:"1"}, {Month:"2"}, {Month:"3"}, {Month:"4"}, {Month:"5"}, {Month:"6"}, {Month:"7"}, {Month:"8"}, {Month:"9"}, {Month:"10"}, {Month:"11"}, {Month:"12"})**

4. Angi **[Element](controls/properties-core.md)**-egenskapen for **Dag** til denne formelen:
   <br>**Table({Day:"1"}, {Day:"2"}, {Day:"3"}, {Day:"4"}, {Day:"5"}, {Day:"6"}, {Day:"7"}, {Day:"8"}, {Day:"9"}, {Day:"10"}, {Day:"11"}, {Day:"12"}, {Day:"13"}, {Day:"14"}, {Day:"15"}, {Day:"16"}, {Day:"17"}, {Day:"18"}, {Day:"19"}, {Day:"20"}, {Day:"21"}, {Day:"22"}, {Day:"23"}, {Day:"24"}, {Day:"25"}, {Day:"26"}, {Day:"27"}, {Day:"28"}, {Day:"29"}, {Day:"30"}, {Day:"31"})**

5. Legg til en **[Etikett](controls/control-text-box.md)**-kontroll, og angi **[Tekst](controls/properties-core.md)**-egenskapen til denne formelen:
   <br>**Text(Date(Value(Year.Selected.Value), Value(Month.Selected.Value), Value(Day.Selected.Value)), DateTimeFormat.LongDate)**
   
    **Onsdag 01. jan. 2014** er oppført som standard. Velg forskjellige verdier i **[Rullegardin](controls/control-drop-down.md)**-kontrollene for å endre datoen i **[Etikett](controls/control-text-box.md)**-kontrollen.

Du må kanskje konvertere data som du ikke forventet. En bruker kan angi feil dato, for eksempel 45. mai, hvis du legger til **[Tekstinndata](controls/control-text-input.md)**-kontroller i stedet for **[Rullegardin](controls/control-drop-down.md)**-kontroller. **[Date](functions/function-date-time.md)**-funksjonen håndterer avvikende data på følgende måter:

* Hvis en årsverdi er mellom 0 og 1899 (samlet), legger funksjonen til denne verdien som 1900 for å beregne året.
* Hvis en årsverdi er mellom 1900 og 9999 (samlet), legger funksjonen til denne verdien som året.
* Hvis en årsverdi er mindre enn 0, eller er 10000 eller høyere, returnerer funksjonen en feilverdi.
* Hvis en månedsverdi er større enn 12, legger funksjonen dette antallet måneder til den første måneden av det angitte året.
* Hvis en månedsverdi er mindre enn 1, trekker funksjonen dette antallet fra, pluss 1, fra den første måneden av det angitte året.
* Hvis dagsverdien er større enn antallet dager i den angitte måneden, legger funksjonen til dette antallet dager til den første dagen i måneden, og returnerer den tilsvarende datoen fra en påfølgende måned.
* Hvis en dagsverdi er mindre enn 1, trekker funksjonen fra så mange dager, pluss 1, fra den første dagen i den angitte måneden.

## <a name="calculate-times-based-on-hours-minutes-and-seconds"></a>Å beregne klokkeslett basert på timer, minutter og sekunder

1. Legg til to **Rullegardin**-lister kalt **Time** og **Minutt**.

2. Angi **[Element](controls/properties-core.md)**-egenskapen for **Time** til denne formelen:
   <br>**Table({Hour:"9"}, {Hour:"10"}, {Hour:"11"}, {Hour:"12"}, {Hour:"13"}, {Hour:"14"}, {Hour:"15"}, {Hour:"16"}, {Hour:"17"})**

3. Angi **[Element](controls/properties-core.md)**-egenskapen for **Minutt** til denne formelen:
   <br>**Table({Minute:"0"}, {Minute:"15"}, {Minute:"30"}, {Minute:"45"})**

4. Legg til en **[Etikett](controls/control-text-box.md)**-kontroll, og angi **[Tekst](controls/properties-core.md)**-egenskapen til denne formelen:  
   <br>**Text(Time(Value(Hour.Selected.Value), Value(Minute.Selected.Value), 0), DateTimeFormat.ShortTime)**

5. Velg **15** i **Time** og **45** i **Minutt**.
   
    **[Etikett](controls/control-text-box.md)**-kontrollen viser **15:45:00**.
   
    Du kan legge til oppføringer til **Time** og **Minutt**, slik at brukere kan velge fra et større utvalg av timer, og et mer nøyaktig antall minutter. Du kan også legge til en tredje **[Rullegardin](controls/control-drop-down.md)**-kontroll, slik at brukere kan angi sekunder. Hvis du legger til en tredje liste, kan du angi **[Tekst](controls/properties-core.md)**-egenskapen for **[Etikett](controls/control-text-box.md)**-kontrollen til følgende uttrykk:<br>**Text(Time(Value(Hour.Selected.Value), Value(Minute.Selected.Value), Value(Second.Selected.Value)), DateTimeFormat.LongTime)**

