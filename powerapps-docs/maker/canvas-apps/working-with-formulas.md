---
title: Å komme i gang med formler | Microsoft Docs
description: Å bruke formler til å tilpasse en app.
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 04/26/2016
ms.author: gregli
ms.openlocfilehash: b40abdc4c8d5d8a33a9aec32a1826476500405c8
ms.sourcegitcommit: dfa0e1a7981814e15e6ca4720e2a5f930e859db1
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 07/13/2018
ms.locfileid: "39017874"
---
# <a name="get-started-with-formulas"></a>Å komme i gang med formler
Konfigurer appen din med formler som ikke bare beregner verdier og utfører andre oppgaver (som de gjør i Excel) men som også responderer på inndata fra brukeren (som kreves av en app).

* I Excel bygger du formler som eksempelvis fyller ut celler og oppretter tabeller og diagrammer.
* I PowerApps oppretter du lignende formler når du konfigurerer kontroller i stedet for celler. I tillegg kan du opprette formler som gjelder spesielt for apper i stedet for regneark.

For eksempel kan du opprette en formel til å bestemme hvordan appen din responderer når brukere velger en knapp, justerer en glidebryter eller angir andre inndata. Disse formlene kan vise et annet skjermbilde, oppdatere en datakilde som er ekstern for appen eller opprette en tabell som inneholder et delsett av dataene i en eksisterende tabell.

Du kan bruke formler for et bredt utvalg av scenarioer. Du kan for eksempel bruke enhetens GPS, en kartkontroll og en formel som bruker **Location.Latitude** og **Location.Longitude** til å vise gjeldende plassering. Når du flytter på deg, sporer kartet automatisk plasseringen din.

Dette emnet gir bare en oversikt over det å arbeide med formler. Bla gjennom [formelreferansen](formula-reference.md) for mer informasjon og en fullstendig liste over funksjoner, operatorer og andre byggeblokker som du kan bruke.

## <a name="prerequisites"></a>Forutsetninger

* [Registrer deg](../signup-for-powerapps.md) for PowerApps, og deretter [logger du deg på](https://web.powerapps.com) ved å angi samme legitimasjon som du brukte til å registrere deg.
* Finn ut hvordan du [konfigurerer en kontroll](add-configure-controls.md) i PowerApps.

## <a name="show-a-simple-value"></a>Å vise en enkel verdi
I Excel kan du angi en bestemt type data, for eksempel tallet **42** eller uttrykket **Hello World**, ved å skrive det inn i en celle. Denne cellen viser alltid disse dataene nøyaktig slik du skrev dem inn. I PowerApps kan du på samme måte angi data som ikke endres ved å angi **[tekst](controls/properties-core.md)**-egenskapen for en etikett til den nøyaktige sekvensen av tegn du vil bruke, omsluttet av doble anførselstegn.

1. Velg **Ny** i **Fil**-menyen (nær den venstre kanten på skjermen).
2. Under **Opprett app** velger du **Telefonoppsett** på **Tom app**-flisen.
   
    Formellinjen er på toppen av skjermen.
   
    ![Formellinje](./media/working-with-formulas/formula-bar.png)
   
    Dette feltet har to deler:
   
   * *Egenskapslisten*: hver kontroll og skjerm har et [sett med egenskaper](reference-properties.md).  Bruk denne listen til å velge en bestemt egenskap.  
   * *Formelen*: formelen som skal beregnes for denne egenskapen, består av [verdier, operatorer og funksjoner](formula-reference.md).
     
     Du kan se og redigere egenskaper for den valgte kontrollen i formellinjen, eller for skjermen hvis ingen kontroller er valgt.  Du kan se navnet på den merkede kontrollen på **Innhold**-fanen:
     
     ![Innholdslinjen viser den merkede kontrollen](./media/working-with-formulas/content-tab-selection.png)
     
     Du kan endre navnet på den valgte kontrollen i **Innhold**-fanen ved å klikke på navnet.
3. Legg til en **[Etikett](controls/control-text-box.md)**-kontroll til skjermen.
   
    ![La til en TextBox-kontroll](./media/working-with-formulas/add-a-label.png)
   
    Når du legger til en etikett, viser egenskapslisten automatisk  **[Tekst](controls/properties-core.md)**-egenskapen, som styrer hva kontrollen viser. Verdien for denne egenskapen er som standard **«Tekst»**.  
4. Angi verdien for **[Tekst](controls/properties-core.md)**-egenskapen til **"Hello World"** ved å skrive inn denne strengen, omsluttet av doble anførselstegn i formellinjen:
   
    ![Å bruke etiketten "Hello World"](./media/working-with-formulas/label-hello-world.png)
   
    Etiketten gjenspeiler denne nye verdien når du skriver den inn.  Skjermen viser kanskje gule utropstegn-ikoner mens du skriver. Disse ikonene indikerer feil, men de går bort når du er ferdig med å skrive inn en gyldig verdi. En streng uten doble anførselstegn i begge ender er for eksempel ikke gyldig.
   
    I Excel kan du vise et tall, for eksempel **42**, ved å skrive det inn i en celle eller ved å skrive inn en formel som løses til dette nummeret, for eksempel slik: **=SUM(30,12)**. Du kan oppnå den samme effekten i PowerApps ved å angi **Tekst**-egenskapen for en kontroll, for eksempel en etikett, til **42** eller **Sum(30,12)**. Cellen og etiketten viser alltid dette tallet uavhengig av andre endringer i regnearket eller appen.
   
    > [!NOTE]
   > I PowerApps skal du ikke sette et likhetstegn eller et plusstegn før en formel, som du gjør i Excel. Formellinjen behandler som standard alt du skriver inn der som en formel. Du skal heller ikke omgi en formel med doble anførselstegn ("), som du gjorde tidligere for å angi en tekststreng.
5. I **[Tekst](controls/properties-core.md)**-egenskapen for etiketten erstatter du **"Hello World"** med **Sum(1,2,3)**.
   
    ![Å skrive inn den delvise funksjonen Sum(1,2,3 uten en avsluttende parentes viser feil](./media/working-with-formulas/label-sum-partial.png)
   
    Mens du skriver inn, hjelper formellinjen deg ved å vise beskrivelsen og de forventede argumentene for denne funksjonen.  Som med det endelige doble anførselstegnet i **"Hello World"**, viser skjermbildet gule utropstegn for å indikere en feil før du skriver inn de avsluttende parentesene for denne formelen:
   
    ![Å bruke den komplette formelen Sum(1,2,3)](./media/working-with-formulas/label-sum.png)

## <a name="change-a-value-based-on-input"></a>Å endre en verdi basert på inndata
I Excel kan du skrive inn **=SUM(A1:A2)** i en celle for å vise summen av verdiene som celle A1 og A2 inneholder. Hvis én eller begge av disse verdiene endres, viser cellen som inneholder formelen automatisk det oppdaterte resultatet.

![Illustrasjon av en oppdatert beregning i Excel hvor to tall legges sammen](./media/working-with-formulas/excel-recalc.png)

Du kan oppnå et lignende resultat ved å legge til kontroller og angi egenskapene deres i PowerApps. Dette eksemplet viser etiketten fra den forrige prosedyren og to **[Tekstinndata](controls/control-text-input.md)**-kontroller, kalt **TextInput1** og **TextInput2**.

![Illustrasjon av en oppdatert beregning i PowerApps hvor to tall legges sammen](./media/working-with-formulas/recalc1.png)

Uavhengig av hvilke tall du skriver inn i kontrollene for innskriving av tekst, viser etiketten alltid summen av disse tallene fordi **[Tekst](controls/properties-core.md)**-egenskapen dens er angitt til denne formelen:
<br>**TextInput1 + TextInput2**

![Illustrasjon av en oppdatert beregning i PowerApps hvor to tall legges sammen](./media/working-with-formulas/recalc2.png)

I Excel kan du bruke betinget formatering for å vise eksempelvis negative verdier i rødt. I PowerApps kan du bruke en formel som inneholder **[If](functions/function-if.md)**-funksjonen, som fungerer på lignende måte som det den gjør i Excel.

1. Angi **[Farge](controls/properties-color-border.md)**-egenskapen for etiketten til denne formelen:<br>**If( Value(TextBox1.Text) < 0, Red, Black )**
   
    > [!NOTE]
   > I en formel angir du egenskapen for en kontroll ved å angi navnet på kontrollen, etterfulgt av et punktum, etterfulgt av navnet på egenskapen. Angi for eksempel **[Tekst](controls/properties-core.md)**-egenskapen for **TextBox1** ved å skrive inn **TextBox1.Text**.
   
    ![Illustrasjon av oppdatert beregning i PowerApps hvor fargen på en etikett endres, basert på verdien sin](./media/working-with-formulas/recalc-color1.png)
2. I **TextInput1** og **TextInput2** kan du angi to tall som resulterer i et negativt tall når de legges sammen.
   
    ![Illustrasjon av oppdatert beregning i PowerApps hvor fargen på en etikett endres, basert på verdien sin](./media/working-with-formulas/recalc-color2.png)
   
    Verdien i etiketten vises i rødt.

## <a name="change-a-color-based-on-user-input"></a>Å endre en farge som er basert på brukerinndata
Du kan konfigurere appen med formler, slik at brukere kan endre utseendet eller virkemåten for appen. For eksempel kan du opprette et filter for å vise bare data som inneholder en tekststreng som brukeren angir, eller du kan la brukerne sortere et sett med data basert på en bestemt kolonne i datasettet. I denne prosedyren vil du la brukerne endre fargen på skjermbildet ved å justere én eller flere glidebrytere.

1. Fjern kontrollene fra fremgangsmåtene ovenfor, eller opprett en tom app som du gjorde tidligere, og legg til tre glidebrytere:
   
    ![Å sette inn en glidebryter](./media/working-with-formulas/insert-slider.png)
2. Ordne glidebryterne slik at de ikke overlapper hverandre, legg til tre etiketter, og konfigurer dem til å vise **Rød**, **Grønn** og **Blå**:
   
    ![Ordne glidebryterne og legg til etiketter for hver fargekomponent](./media/working-with-formulas/three-sliders.png)
3. Angi **Maks**-egenskapen for hver glidebryter til 255, som er den maksimale verdien for en fargekomponent for **[RGBA](functions/function-colors.md)**-funksjonen.
   
    Du kan angi **Maks**-egenskapen ved å velge den på **Innhold**-fanen eller i egenskapslisten:
   
    ![Å endre den maksimale verdien for hver glidebryter](./media/working-with-formulas/three-sliders-max.png)
4. Velg skjermen ved å klikke bort fra en kontroll, og angi deretter skjermens  **[Fyll](controls/properties-color-border.md)**-egenskap til denne formelen:<br>**RGBA( Slider1.Value, Slider2.Value, Slider3.Value, 1 )**
   
    Som allerede beskrevet får du tilgang til kontrollegenskaper ved å bruke **.** -operatoren.  **Slider1.Value** refererer til glidebryterens **[Verdi](controls/properties-core.md)**-egenskap, som gjenspeiler hvor brukeren har plassert glidebryteren mellom **Min.-** og **Maks**-verdiene. Når du skriver inn denne formelen, er hver kontroll den inneholder fargekodet mellom skjermen og formellinjen:
   
    ![Endre formelen for fyllfargen for bakgrunnen på skjermen, men ikke fullført enda](./media/working-with-formulas/three-sliders-partial-rgba.png)
   
    Mens du skriver den avsluttende parentesen vil bakgrunnen på skjermen endres til mørk grå basert på standardverdien for hver glidebryter, som er **50**. Den beregnes i det øyeblikket du er ferdig med å skrive inn formelen, og brukes som verdi for fyllfargen for bakgrunnen. Du kan samhandle med appen i standardarbeidsområdet uten å måtte åpne forhåndsvisning:
   
    ![Å endre den maksimale verdien for hver glidebryter](./media/working-with-formulas/three-sliders-complete-rgba.png)
5. Juster glidebryterne, og se hvordan endringene påvirker bakgrunnsfargen.
   
    Ettersom hver glidebryter endres, beregnes formelen som inneholder **[RGBA](functions/function-colors.md)** på nytt, som umiddelbart endrer hvordan skjermen vises.
   
    ![Endre formelen for fyllfargen for bakgrunnen på skjermen, nå fullført](./media/working-with-formulas/three-sliders-example-colors.png)

## <a name="manage-app-behavior"></a>Å administrere virkemåte for apper
Du kan bruke formler ikke bare til å utføre beregninger og endre utseendet, men også til å foreta deg noe. Du kan for eksempel angi **[OnSelect](controls/properties-core.md)**-egenskapen for en knapp til en formel som inkluderer **[Navigate](functions/function-navigate.md)**-funksjonen. Når en bruker velger denne knappen, vises skjermen som du angir i formelen.

Noen funksjoner, for eksempel **[Navigate](functions/function-navigate.md)** og **[Collect](functions/function-clear-collect-clearcollect.md)**, kan bare brukes i formler for virkemåte.  Formelreferansen gjenspeiler det hvis du kan bruke en funksjon bare i denne konteksten.  

Du kan utføre mer enn én handling i en formel for virkemåte hvis du atskiller funksjoner med et semikolon (;). Du kan for eksempel oppdatere en kontekstvariabel, sende data til en datakilde, og til slutt navigerer du til en annen skjerm.

## <a name="view-a-list-of-properties-by-category"></a>Å vise en liste over egenskaper etter kategori
Egenskaper-listen viser egenskaper alfabetisk, men du kan også vise alle egenskapene for en kontroll, ordnet etter kategori, hvis du velger **Avansert**-alternativet på **Vis**-fanen:

![Avansert visning](./media/working-with-formulas/advanced-open.png)

Du kan redigere formler direkte i denne visningen.  Du kan raskt finne en kontroll å arbeide med, med kontroll-velgeren øverst i ruten.  Og med egenskapsøket kan du raskt finne en egenskap for denne kontrollen.

I utgangspunktet viser denne visningen de viktigste egenskapene.  Hvis du vil vise alle egenskapene, klikker du på Pil ned nederst i ruten.  Hver kontroll har en lang liste med egenskaper som styrer alle aspekter av kontrollens virkemåte og utseende. Du kan bla gjennom listen eller søke etter en egenskap ved å skrive inn i boksen øverst i ruten.

## <a name="formula-syntax"></a>Formelsyntaks
Mens du skriver en formel på formellinjen, vises forskjellige syntakselementer i forskjellige farger for å forbedre lesbarheten og hjelpe deg med å forstå lange formler. Her er listen med fargekoder i PowerApps.

![utheving av syntaks](./media/working-with-formulas/syntax-highlighting.png)

