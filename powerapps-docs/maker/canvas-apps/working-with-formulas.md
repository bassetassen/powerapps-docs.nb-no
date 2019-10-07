---
title: Kom i gang med formler i en lerretsapp | Microsoft Docs
description: Bruk formler til å tilpasse en lerretsapp i PowerApps.
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 03/01/2019
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 7865b2123f0d179d5d132cca838684f0c83cfd31
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/07/2019
ms.locfileid: "71994789"
---
# <a name="get-started-with-canvas-app-formulas-in-powerapps"></a>Kom i gang med lerretsappformler i PowerApps

Konfigurer lerretsappen din med formler som ikke bare beregner verdier og utfører andre oppgaver (slik de gjør i Excel), men som også responderer på brukerinndata (som kreves av en app).

* I Excel bygger du formler som eksempelvis fyller ut celler og oppretter tabeller og diagrammer.
* I PowerApps oppretter du lignende formler når du konfigurerer kontroller i stedet for celler. I tillegg kan du opprette formler som gjelder spesielt for apper i stedet for regneark.

For eksempel kan du opprette en formel til å bestemme hvordan appen din responderer når brukere velger en knapp, justerer en glidebryter eller angir andre inndata. Disse formlene kan vise et annet skjermbilde, oppdatere en datakilde som er ekstern for appen eller opprette en tabell som inneholder et delsett av dataene i en eksisterende tabell.

Du kan bruke formler for et bredt utvalg av scenarioer. Du kan for eksempel bruke enhetens GPS, en kartkontroll og en formel som bruker **Location.Latitude** og **Location.Longitude** til å vise gjeldende plassering. Når du flytter på deg, sporer kartet automatisk plasseringen din.

Dette emnet gir bare en oversikt over det å arbeide med formler. Bla gjennom [formelreferansen](formula-reference.md) for mer informasjon og en fullstendig liste over funksjoner, operatorer og andre byggeblokker som du kan bruke.

## <a name="prerequisites"></a>Forutsetninger

* [Registrer deg](../signup-for-powerapps.md) for PowerApps, og deretter [logger du deg på](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) ved å angi samme legitimasjon som du brukte til å registrere deg.
* Finn ut hvordan du [konfigurerer en kontroll](add-configure-controls.md) i PowerApps.

## <a name="show-a-simple-value"></a>Å vise en enkel verdi

I Excel kan du angi en bestemt type data, for eksempel tallet **42** eller uttrykket **Hello World**, ved å skrive det inn i en celle. Denne cellen viser alltid disse dataene nøyaktig slik du skrev dem inn. I PowerApps kan du på samme måte angi data som ikke endres ved å angi **[tekst](controls/properties-core.md)** -egenskapen for en etikett til den nøyaktige sekvensen av tegn du vil bruke, omsluttet av doble anførselstegn.

1. Velg **Ny** i **Fil**-menyen (nær den venstre kanten på skjermen).
2. Under **Opprett app** velger du **Telefonoppsett** på **Tom app**-flisen.

    Formellinjen er på toppen av skjermen.

    ![Formellinje](./media/working-with-formulas/formula-bar.png)

    Dette feltet har to deler:

   * *Egenskaps liste*:  Hver kontroll og skjerm har et [sett med egenskaper](reference-properties.md).  Bruk denne listen til å velge en bestemt egenskap.  
   * *Formel*:  Formelen som skal beregnes for denne egenskapen, som består av [verdier, operatorer og funksjoner](formula-reference.md).

     Du kan se og redigere egenskaper for den valgte kontrollen i formellinjen, eller for skjermen hvis ingen kontroller er valgt.  Du kan se navnet på den merkede kontrollen på **Innhold**-fanen:

     ![Innholdslinjen viser den merkede kontrollen](./media/working-with-formulas/content-tab-selection.png)

     Du kan endre navnet på den valgte kontrollen i **Innhold**-fanen ved å klikke på navnet.
3. Legg til en **[Etikett](controls/control-text-box.md)** -kontroll til skjermen.

    ![La til en TextBox-kontroll](./media/working-with-formulas/add-a-label.png)

    Når du legger til en etikett, viser egenskapslisten automatisk  **[Tekst](controls/properties-core.md)** -egenskapen, som styrer hva kontrollen viser. Verdien for denne egenskapen er som standard **«Tekst»** .  
4. Angi verdien for **[Tekst](controls/properties-core.md)** -egenskapen til **"Hello World"** ved å skrive inn denne strengen, omsluttet av doble anførselstegn i formellinjen:

    ![Å bruke etiketten "Hello World"](./media/working-with-formulas/label-hello-world.png)

    Etiketten gjenspeiler denne nye verdien når du skriver den inn.  Skjermen viser kanskje gule utropstegn-ikoner mens du skriver. Disse ikonene indikerer feil, men de går bort når du er ferdig med å skrive inn en gyldig verdi. En streng uten doble anførselstegn i begge ender er for eksempel ikke gyldig.

    I Excel kan du vise et tall, for eksempel **42**, ved å skrive det inn i en celle eller ved å skrive inn en formel som løses til dette nummeret, for eksempel slik: **=SUM(30,12)** . Du kan oppnå den samme effekten i PowerApps ved å angi **Tekst**-egenskapen for en kontroll, for eksempel en etikett, til **42** eller **Sum(30,12)** . Cellen og etiketten viser alltid dette tallet uavhengig av andre endringer i regnearket eller appen.

    > [!NOTE]
   > I PowerApps skal du ikke sette et likhetstegn eller et plusstegn før en formel, som du gjør i Excel. Formellinjen behandler som standard alt du skriver inn der som en formel. Du skal heller ikke omgi en formel med doble anførselstegn ("), som du gjorde tidligere for å angi en tekststreng.
5. I **[Tekst](controls/properties-core.md)** -egenskapen for etiketten erstatter du **"Hello World"** med **Sum(1,2,3)** .

    ![Å skrive inn den delvise funksjonen Sum(1,2,3 uten en avsluttende parentes viser feil](./media/working-with-formulas/label-sum-partial.png)

    Mens du skriver inn, hjelper formellinjen deg ved å vise beskrivelsen og de forventede argumentene for denne funksjonen.  Som med det endelige doble anførselstegnet i **"Hello World"** , viser skjermbildet gule utropstegn for å indikere en feil før du skriver inn de avsluttende parentesene for denne formelen:

    ![Å bruke den komplette formelen Sum(1,2,3)](./media/working-with-formulas/label-sum.png)

## <a name="change-a-value-based-on-input"></a>Å endre en verdi basert på inndata

I Excel skriver du inn **= a1 + a2** i en celle for å vise summen av verdiene celle **a1** og **a2** inneholder. Hvis én eller begge av disse verdiene endres, viser cellen som inneholder formelen automatisk det oppdaterte resultatet.

![Animasjon av Excel beregner summen av to tall på nytt](./media/working-with-formulas/excel-recalc.gif)

I PowerApps kan du oppnå et lignende resultat ved å legge til kontroller på en skjerm og angi egenskapene. Dette eksemplet viser en etikett-kontroll med navnet **Label1** og to **[tekst inn data](controls/control-text-input.md)** -kontroller, kalt **TextInput1** og **TextInput2**.

![Illustrasjon av PowerApps beregner summen av to tall](./media/working-with-formulas/recalc1.png)

Uavhengig av hvilke tall du skriver inn i kontrollene for innskriving av tekst, viser etiketten alltid summen av disse tallene fordi **[Tekst](controls/properties-core.md)** -egenskapen dens er angitt til denne formelen:

`TextInput1 + TextInput2`

![Animasjon av PowerApps beregner summen av to tall](./media/working-with-formulas/recalc2.gif)

I Excel kan du bruke formler for betinget formatering til å vise for eksempel negative verdier i rødt. I PowerApps kan du bruke formler til å bestemme, ikke bare den primære verdien av en kontroll, men også egenskaper som formatering. I det neste eksemplet viser en formel for **[farge](controls/properties-color-border.md)** -egenskapen for etiketten automatisk negative verdier i rødt. **[If](functions/function-if.md)** -funksjonen bør du kunne kjenne igjen fra Excel:

`If( Value(Label1.Text) < 0, Red, Black )`

![Animasjon av betinget formatering](media/working-with-variables/recalc-color.gif)

## <a name="change-a-color-based-on-user-input"></a>Å endre en farge som er basert på brukerinndata

Du kan konfigurere appen med formler, slik at brukere kan endre utseendet eller virkemåten for appen. For eksempel kan du opprette et filter for å vise bare data som inneholder en tekststreng som brukeren angir, eller du kan la brukerne sortere et sett med data basert på en bestemt kolonne i datasettet. I denne prosedyren vil du la brukerne endre fargen på skjermbildet ved å justere én eller flere glidebrytere.

1. Fjern kontrollene fra fremgangsmåtene ovenfor, eller opprett en tom app som du gjorde tidligere, og legg til tre glidebrytere:

    ![Å sette inn en glidebryter](./media/working-with-formulas/insert-slider.png)
2. Ordne glidebryterne slik at de ikke overlapper hverandre, legg til tre etiketter, og konfigurer dem til å vise **Rød**, **Grønn** og **Blå**:

    ![Ordne glidebryterne og legg til etiketter for hver fargekomponent](./media/working-with-formulas/three-sliders.png)
3. Angi **Maks**-egenskapen for hver glidebryter til 255, som er den maksimale verdien for en fargekomponent for **[RGBA](functions/function-colors.md)** -funksjonen.

    Du kan angi **Maks**-egenskapen ved å velge den på **Innhold**-fanen eller i egenskapslisten:

    ![Å endre den maksimale verdien for hver glidebryter](./media/working-with-formulas/three-sliders-max.png)
4. Velg skjermen ved å klikke bort fra en kontroll, og angi deretter skjermens  **[Fyll](controls/properties-color-border.md)** -egenskap til denne formelen:<br>**RGBA( Slider1.Value, Slider2.Value, Slider3.Value, 1 )**

    Som allerede beskrevet får du tilgang til kontrollegenskaper ved å bruke **.** -operatoren.  **Slider1.Value** refererer til glidebryterens **[Verdi](controls/properties-core.md)** -egenskap, som gjenspeiler hvor brukeren har plassert glidebryteren mellom **Min.-** og **Maks**-verdiene. Når du skriver inn denne formelen, er hver kontroll den inneholder fargekodet mellom skjermen og formellinjen:

    ![Endre formelen for fyllfargen for bakgrunnen på skjermen, men ikke fullført enda](./media/working-with-formulas/three-sliders-partial-rgba.png)

    Mens du skriver den avsluttende parentesen vil bakgrunnen på skjermen endres til mørk grå basert på standardverdien for hver glidebryter, som er **50**. Den beregnes i det øyeblikket du er ferdig med å skrive inn formelen, og brukes som verdi for fyllfargen for bakgrunnen. Du kan samhandle med appen i standardarbeidsområdet uten å måtte åpne forhåndsvisning:

    ![Å endre den maksimale verdien for hver glidebryter](./media/working-with-formulas/three-sliders-complete-rgba.png)
5. Juster glidebryterne, og se hvordan endringene påvirker bakgrunnsfargen.

    Ettersom hver glidebryter endres, beregnes formelen som inneholder **[RGBA](functions/function-colors.md)** på nytt, som umiddelbart endrer hvordan skjermen vises.

    ![Endre formelen for fyllfargen for bakgrunnen på skjermen, nå fullført](./media/working-with-formulas/color-sliders.gif)

## <a name="manage-app-behavior"></a>Å administrere virkemåte for apper

Du kan bruke formler ikke bare til å utføre beregninger og endre utseendet, men også til å foreta deg noe. Du kan for eksempel angi **[OnSelect](controls/properties-core.md)** -egenskapen for en knapp til en formel som inkluderer **[Navigate](functions/function-navigate.md)** -funksjonen. Når en bruker velger denne knappen, vises skjermen som du angir i formelen.

Noen funksjoner, for eksempel **[Navigate](functions/function-navigate.md)** og **[Collect](functions/function-clear-collect-clearcollect.md)** , kan bare brukes i formler for virkemåte.  Formelreferansen gjenspeiler det hvis du kan bruke en funksjon bare i denne konteksten.  

Du kan utføre mer enn én handling i en formel for virkemåte hvis du atskiller funksjoner med et semikolon (;). Du kan for eksempel oppdatere en kontekstvariabel, sende data til en datakilde, og til slutt navigerer du til en annen skjerm.

## <a name="view-a-list-of-properties-by-category"></a>Å vise en liste over egenskaper etter kategori

Egenskaper-listen viser egenskaper alfabetisk, men du kan også vise alle egenskapene for en kontroll, ordnet etter kategori, hvis du velger **Avansert**-alternativet på **Vis**-fanen:

![Avansert visning](./media/working-with-formulas/advanced-open.png)

Du kan redigere formler direkte i denne visningen.  Du kan raskt finne en kontroll å arbeide med, med kontroll-velgeren øverst i ruten.  Og med egenskapsøket kan du raskt finne en egenskap for denne kontrollen.

I utgangspunktet viser denne visningen de viktigste egenskapene.  Hvis du vil vise alle egenskapene, klikker du på Pil ned nederst i ruten.  Hver kontroll har en lang liste med egenskaper som styrer alle aspekter av kontrollens virkemåte og utseende. Du kan bla gjennom listen eller søke etter en egenskap ved å skrive inn i boksen øverst i ruten.

## <a name="formula-syntax"></a>Formelsyntaks

Mens du skriver en formel på formellinjen, vises forskjellige syntakselementer i forskjellige farger for å forbedre lesbarheten og hjelpe deg med å forstå lange formler. Her er listen med fargekoder i PowerApps.

![utheving av syntaks](./media/working-with-formulas/syntax-highlighting.png)