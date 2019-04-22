---
title: Opprette responsive oppsett i lerret-apper | Microsoft Docs
description: Referanseinformasjon om hvordan du konfigurerer høyde, bredde, X og Y-egenskaper på kontrollene i lerret-apper
author: emcoope-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 02/28/2019
ms.author: emcoope
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: cad1d7f138a8f831631d9a57b55c54b30d537b9c
ms.sourcegitcommit: 39c9b4cbc26617e302d46085d81c6d397e01fbf7
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/17/2019
ms.locfileid: "59671611"
---
# <a name="create-responsive-layouts-in-canvas-apps"></a>Opprette responsive oppsett i lerret-apper

Før du bygger en lerret-app i PowerApps, angir du om å skreddersy appen for en telefon eller et nettbrett. Dette valget fastsetter størrelsen og formen på lerretet som du vil bygge appen din.

Når du gjør dette valget, kan du gjøre noen flere valg hvis du velger **filen** > **appinnstillinger** > **skjermstørrelse og retning**. Du kan velge stående eller liggende retning og skjermstørrelse (bare nettbrett). Du kan også låser eller låser opp størrelsesforholdet og støtter enheten rotasjon (eller ikke).

Disse valgene ligger til grunn for alle andre valget du foretar når du utformer skjermoppsett. Hvis appen din kjører på en enhet med en annen størrelse eller på nettet, skalerer hele oppsettet for å fylle hele skjermen der appen kjøres. Hvis en app som er utformet for en telefon kjører i et stort nettleservindu, for eksempel appen skaleres for å kompenserer og ser forstørret for den tilhørende plassen. Appen kan ikke dra nytte av de ekstra pikslene ved å vise flere kontroller eller mer innhold.

Hvis du oppretter et responsivt oppsett, kan Kontroller svare på forskjellige enheter eller vindusstørrelser, noe som gjør ulike opplevelser virker mer naturlige. For å oppnå responsivt oppsett, kan du justere noen innstillinger og skriver inn uttrykk i hele appen. 

## <a name="disable-scale-to-fit"></a>Deaktiver Tilpass til

Du kan konfigurere hver skjerm slik at oppsettet tilpasser seg hvor mye diskplass som appen kjører.

Du aktiverer svartid ved å slå av appens **Tilpass til** innstilling, som er aktivert som standard. Når du aktiverer denne innstillingen, du også slå av **Lås størrelsesforhold** fordi du ikke lenger lager for en bestemt skjermbilde figur. (Du kan fremdeles angi om appen støtter enheten rotasjon.)

![Deaktiver skala slik at den passer innstillingen](media/create-responsive-layout/scale-to-fit-off.png)

Hvis du vil gjøre appen responsiv, må du gjøre mer for, men denne endringen er det første skrittet mot gjør det mulig å svartid.

## <a name="understand-app-and-screen-dimensions"></a>Forstå appen og skjermen dimensjoner

Hvis du vil gjøre appens oppsett reagere på endringer i skjermen dimensjonene, vil du skrive formler som bruker den **bredde** og **høyde** egenskaper til skjermen. Hvis du vil vise disse egenskapene, åpne en app i PowerApps Studio, og velg deretter en skjerm. Standard formlene for disse egenskapene vises på den **avansert** fanen i ruten til høyre.

**Bredde** = `Max(App.Width, App.DesignWidth)`

**Høyde** = `Max(App.Height, App.DesignHeight)`

Disse formler refererer til den **bredde**, **høyde**, **DesignWidth**, og **DesignHeight** egenskapene til appen. Appens **bredde** og **høyde** samsvarer egenskapene med dimensjonene i vinduet enheten eller nettleseren som appen kjører. Hvis brukeren endrer størrelsen på nettleservinduet (eller roterer enheten hvis du har deaktivert **Lås retning**), verdiene for disse egenskapene endres dynamisk. Formlene i skjermens **bredde** og **høyde** egenskaper er evalueres på nytt når disse verdiene endres.

Den **DesignWidth** og **DesignHeight** egenskaper som kommer fra dimensjonene som du angir i den **skjermstørrelse og retning** ruten i **appinnstillinger** . Hvis du velger oppsettet på telefonen i stående retning, for eksempel **DesignWidth** er 640, og **DesignHeight** er 1136.

Når de brukes i formler for skjermens **bredde** og **høyde** egenskaper, kan du tenke på **DesignWidth** og **DesignHeight** som minimum dimensjonene som skal du utforme appen. Hvis det faktiske området som er tilgjengelig for appen din er mindre enn disse minimum dimensjoner, formlene for skjermens **bredde** og **høyde** egenskaper sikre at verdiene ikke vil bli mindre enn minimumspriser. I så fall må brukeren rulle for å vise alt innholdet på skjermen.

Når du har opprettet til appens **DesignWidth** og **DesignHeight**, trenger du ikke (i de fleste tilfeller) til å endre standardformler for hver skjerm **bredde** og **Høyde** egenskaper. Dette emnet beskriver senere, tilfeller der du kanskje vil tilpasse disse formlene.

## <a name="use-formulas-for-dynamic-layout"></a>Bruke formler for dynamisk oppsett

Hvis du vil opprette en responsiv utforming, kan du finne og endrer størrelsen hver kontroll ved hjelp av formler i stedet for absolutte koordinaten (konstante) verdier. Disse formlene express hver kontroll plassering og størrelse når det gjelder den totale skjermstørrelsen eller i forhold til andre kontroller på skjermen.

> [!IMPORTANT]
> Når du skriver formler for den **X**, **Y**, **bredde** og **høyde** egenskaper for en kontroll, formler, overskrives med konstante verdier hvis du senere drar kontrollen i redigeringsprogrammet for lerretet. Når du begynner å bruke formler til å oppnå dynamisk oppsett, bør du unngå å dra kontrollene.

I det enkleste tilfellet fyller én kontroll en hele skjermen. Hvis du vil opprette denne effekten, angi kontrollens egenskaper i disse verdiene:

| Egenskap      | Value            |
|--------|---------------|
| **X**      | `0`             |
| **Y**      | `0`             |
| **Bredde**  | `Parent.Width`  |
| **Høyde** | `Parent.Height` |

Disse formlene bruker den **overordnede** operatoren. For en kontroll som er plassert direkte på en skjerm, **overordnede** refererer til skjermen. Med disse egenskapsverdiene kontrollen vises i hjørnet øverst til venstre på skjermen (0, 0) og har samme **bredde** og **høyde** som skjermen.

Senere i dette emnet, skal du bruke disse prinsippene (og **overordnede** operatoren) Hvis du vil plassere kontrollene i andre beholdere, for eksempel gallerier, kan du gruppere kontroller og komponenter.

Som et alternativ fyller kontrollen bare den øverste halvdelen av skjermen. Hvis du vil opprette denne effekten, kan du angi den **høyde** egenskapen til **Parent.Height** / 2, og la andre formler forblir uendret.

Hvis du vil bruke en annen kontroll til å fylle nederst halvdel av den samme skjermen, kan du ta minst to andre fremgangsmåtene til å opprette med formler. For enkelhets skyld, kan du ta med denne fremgangsmåten:

| Kontroll | Egenskap | Formel           |
|-|----------|-------------------|
| **Øvre** | **X**        | `0`                 |
| **Øvre** | **Y**        | `0`                 |
| **Øvre** | **Bredde**    | `Parent.Width`      |
| **Øvre** | **Høyde**   | `Parent.Height / 2` |
| **Lavere** | **X**        | `0`                 |
| **Lavere** | **Y**        | `Parent.Height / 2` |
| **Lavere** | **Bredde**    | `Parent.Width`      |
| **Lavere** | **Høyde**   | `Parent.Height / 2` |

![Øvre og nedre kontroll](media/create-responsive-layout/dynamic-layout.png)

Denne konfigurasjonen vil oppnå effekten som du vil, men du må redigere hver formel Hvis du ombestemmer deg om de relative størrelsen på kontrollene. Du kan for eksempel bestemme som øverste kontrollen skal oppta bare de øverste en tredjedel på skjermen, med den nederste kontrollen fyller den lavere to tredjedeler. 

Hvis du vil opprette denne effekten, må du oppdatere den **høyde** -egenskapen for den **øvre** kontroll og den **Y** og **høyde** egenskapene for den **Lavere** kontroll. I stedet, vurdere å skrive formlene for den **lavere** kontroll basert på den **øvre** kontrollen (og selve), som i dette eksemplet:


| Kontroll | Egenskap | Formel           |
|-|----------|-------------------|
| **Øvre** | **X**        | `0`                 |
| **Øvre** | **Y**        | `0`                 |
| **Øvre** | **Bredde**    | `Parent.Width`      |
| **Øvre** | **Høyde**   | `Parent.Height / 2` |
| **Lavere** | **X**        | `0`                       |
| **Lavere** | **Y**        | `Upper.Y + Upper.Height`  |
| **Lavere** | **Bredde**    | `Parent.Width`            |
| **Lavere** | **Høyde**   | `Parent.Height - Lower.Y` |

![Øvre og nedre kontrollerer relativ størrelse](media/create-responsive-layout/dynamic-layout2.png)

Med disse formlene på sted, trenger du bare endre den **høyde** -egenskapen for den **øvre** kontroll å uttrykke en annen brøkdel av høyden på skjermen. Den **lavere** kontrollen automatisk flytter og endrer størrelse for å ta høyde for at endringen.

Du kan bruke disse formelen mønstre for å uttrykke vanlige oppsett relasjoner mellom en kontroll, kalt **C**, og det overordnede området eller en sideordnet-kontroll, kalt **D**.

| Relasjonen mellom C og det overordnede elementet | Egenskap | Formel | Illustrasjon |
|--|--|--|--|
| **C** fyller bredden på overordnede, med en marg på *N* | **X**| `N` | ![Eksempel på C fylling bredden på overordnede](media/create-responsive-layout/c1.png) |
|  | **Bredde** | `Parent.Width - (N * 2)` |  |
| **C** fyller høyden på overordnede, med en marg på *N* | **Y** | `N` | ![Eksempel på C fylling høyden på overordnede](media/create-responsive-layout/c2.png) |
|  | **Høyde** | `Parent.Height - (N * 2)` |  |
| **C** justert med høyre kant av overordnede, etter marg på *N* | **X** | `Parent.Width - (C.Width + N)` | ![Eksempel på C justere med kanten av overordnet](media/create-responsive-layout/c3.png) |
| **C** justert med nedre kanten av overordnede, etter marg på *N* | **Y** | `Parent.Height - (C.Height + N)` | ![Eksempel på C justere med kanten av overordnet](media/create-responsive-layout/c4.png) |
| **C** vannrett midtstilt på overordnede | **X** | `(Parent.Width - C.Width) / 2` | ![Eksempel på C vannrett midtstilt på overordnede](media/create-responsive-layout/c5.png) |
| **C** loddrett midtstilt på overordnede | **Y** | `(Parent.Height - C.Height) / 2` | ![Eksempel på C loddrett midtstilt på overordnede](media/create-responsive-layout/c6.png) |

| Relasjonen mellom C- og D | Egenskap | Formel | Illustrasjon |
|--|--|--|--|
| **C** ord som er justert med **D** og samme bredde som **D** | **X** | `D.X` | ![Eksempel på mønster](media/create-responsive-layout/d1.png) |
|  | **Bredde**    | `D.Width` |  |
| **C** loddrett justert med **D** og samme høyde som **D**  | **Y** | `D.Y` | ![Eksempel på mønster](media/create-responsive-layout/d2.png) |
|  | **Høyde** | `D.Height` |  |
| Høyre kant av **C** justert med høyre kant av **D** | **X** | `D.X + D.Width - C.Width` | ![Eksempel på mønster](media/create-responsive-layout/d3.png) |
| Nedre kant av **C** justert med nedre kanten av **D** | **Y** | `D.Y + D.Height - C.Height` | ![Eksempel på mønster](media/create-responsive-layout/d4.png) |
| **C** midtstilt vannrett forhold til **D** | **X** | `D.X + (D.Width - C.Width) / 2`  | ![Eksempel på mønster](media/create-responsive-layout/d5.png) |
| **C** midtstilt loddrett forhold til **D** | **Y** | `D.Y + (D.Height - C.Height) /2` | ![Eksempel på mønster](media/create-responsive-layout/d6.png) |
| **C** plassert til høyre for **D** med et mellomrom av N | **X** | `D.X + D.Width - N` | ![Eksempel på mønster](media/create-responsive-layout/d7.png) |
| **C** plassert under **D** med en åpning av *N*             | **Y** | `D.Y + D.Height + N` | ![Eksempel på mønster](media/create-responsive-layout/d8.png) |
| **C** fyller mellomrom mellom **D** og høyre kant av overordnet | **X** | `D.X + D.Width` | ![Eksempel på mønster](media/create-responsive-layout/d9.png) |
|  | **Bredde** | `Parent.Width - C.X` |  |
| **C** fyller mellomrom mellom **D** og nedre kant av overordnet | Y | `D.Y + D.Height` | ![Eksempel på mønster](media/create-responsive-layout/d10.png) |

## <a name="hierarchical-layout"></a>Hierarkiske oppsett

Når du definerer skjermbilder som inneholder flere kontroller, vil det bli enklere (eller med nødvendig) til å plassere kontrollene i forhold til en overordnet kontroll, i stedet for i forhold til skjermen eller sideordnet kontroll. Ved å organisere kontrollene i en hierarkisk struktur, kan du gjøre formlene enklere å skrive og vedlikeholde.

### <a name="galleries"></a>Gallerier

Hvis du bruker et galleri i appen din, må du til å sette opp kontrollene i malen i galleriet. Du kan plassere disse kontrollene ved skriving av formler som bruker den **overordnede** -operatoren, vil vise i malgalleriet. I formler i kontrollene i et galleri-mal, kan du bruke den **Parent.TemplateHeight** og **Parent.TemplateWidth** egenskaper; ikke bruker **Parent.Width** og  **Parent.Height**, som refererer til den totale størrelsen på galleriet.

![Loddrett galleri som viser malen bredde og høyde](media/create-responsive-layout/gallery-vertical.png)

### <a name="enhanced-group-control"></a>Forbedret Gruppekontrollen

Du kan bruke en eksperimentell funksjon, de forbedrede **gruppe** kontroll, som en overordnet kontroll. Hvis du vil aktivere denne funksjonen, kan du velge **filen** > **appinnstillinger** > **avanserte innstillinger**.

Vurder å eksempel på en topptekst øverst på en skjerm. Det er vanlig at et hode med en tittel og flere ikoner som brukerne kan bruke. Du kan lage slike en overskrift ved hjelp av de forbedrede **gruppe** kontrollen, som inneholder en **etikett** kontroll og to **ikonet** kontroller:

![Topptekst eksempel ved hjelp av en gruppe](media/create-responsive-layout/header-group.png)

Angi egenskaper for disse kontrollene i disse verdiene:

| Egenskap | Topptekst | Menyen | Lukk | Tittel |
|--|--|--|--|--|
| **X** | `0`  | `0` | `Parent.Width - Close.Width` | `Menu.X + Menu.Width` |
| **Y** | `0` | `0` | `0` | `0` |
| **Bredde**  | `Parent.Width` | `Parent.Height` | `Parent.Height` | `Close.X - Title.X` |
| **Høyde** | `64` | `Parent.Height` | `Parent.Height` | `Parent.Height` |

For den **topptekst** kontroll, `Parent` refererer til skjermen. For de andre, `Parent` refererer til den **topptekst** kontroll.

Å ha skrevet disse formlene, kan du justere størrelsen eller posisjonen for den **topptekst** kontrollen ved å endre formlene for egenskapene. Størrelsene og plasseringen av underordnede kontroller justeres automatisk i henhold til dette.

### <a name="components"></a>Komponenter

Hvis du bruker en annen eksperimentell funksjon, med navnet komponenter, kan du konstruere byggeblokker og bruke dem på nytt i hele appen. Som med den **gruppe** kontroll, kontrollene som du plasserer i en komponent skal basere formler deres plassering og størrelse på `Parent.Width` og `Parent.Height`, som refererer til størrelsen på komponenten. Mer informasjon: [Opprette en komponent](create-component.md).

## <a name="adapting-layout-for-device-size-and-orientation"></a>Å tilpasse deg oppsett for enheten størrelse og retning

Så langt, har du lært hvordan du bruke formler til å endre størrelsen på hver kontroll som svar på den tilgjengelige plassen, mens å holde kontroller justert i forhold til hverandre. Men du kanskje vil eller trenger å gjøre mer omfattende oppsettendringer som svar på en annen enhet størrelser og retninger. Når en enhet er rotert fra stående til liggende retning, kan, du for eksempel å bytte fra en loddrett oppsett til en vannrett. Du kan presentere mer innhold på en større enhet eller omorganisere for å gi et mer tiltalende oppsett. På en mindre enhet må du kanskje dele opp innholdet på tvers av flere skjermer.

### <a name="device-orientation"></a>Retning for enheten

Standard formlene for en skjerm **bredde** og **høyde** egenskaper, slik dette emnet som er beskrevet tidligere, vil ikke nødvendigvis gi en god opplevelse Hvis en bruker roterer en enhet. For eksempel en app som er utformet for en telefon i stående retning har en **DesignWidth** av 640 og en **DesignHeight** av 1136. Samme app på en telefon i liggende retning har disse egenskapsverdiene:

- Skjermens **bredde** egenskapen er satt til `Max(App.Width, App.DesignWidth)`. Appens **bredde** (1136) er større enn den **DesignWidth** (640), slik at formelen evalueres til 1136.
- Skjermens **høyde** egenskapen er satt til `Max(App.Height, App.DesignHeight)`. Appens **høyde** (640) er mindre enn den **DesignHeight** (1136), slik at formelen evalueres til 1136.

Med en skjerm **høyde** av 1136 og en enhet høyde (i dette retning) for 640, må brukeren ruller skjermen loddrett for å vise alt innholdet, noe som kanskje ikke opplevelsen du ønsker.

Tilpasse skjermens **bredde** og **høyde** egenskaper retningen på enheten, kan du bruke disse formlene:

**Bredde** = `Max(App.Width, If(App.Width < App.Height, App.DesignWidth, App.DesignHeight))`

**Høyde** = `Max(App.Height, If(App.Width < App.Height, App.DesignHeight, App.DesignWidth))`

Disse formlene Bytt appens **DesignWidth** og **DesignHeight** verdier, basert på om enhetens bredde er mindre enn i høyde (stående retning) eller mer enn i høyde (liggende retning) .

Når du har justert skjermens **bredde** og **høyde** formler, du kan også vil ordne kontrollene i skjermen for å bruke bedre den tilgjengelige plassen på nytt. Hvis hver av to kontroller tar opp halve skjermen, kan du for eksempel plassere dem loddrett i stående men ordne dem side ved side i liggende visning.

Du kan bruke skjermens **retning** til å fastslå om skjermen er innrettet vannrett eller loddrett.

> [!NOTE]
> I liggende retning, den **øvre** og **lavere** kontroller vises som venstre og høyre kontroller.

| Kontroll | Egenskap | Formel |
|--|----------|---|
| **Øvre** | **X** | `0` |
| **Øvre** | **Y** | `0` |
| **Øvre** | **Bredde** | `If(Parent.Orientation = Layout.Vertical, Parent.Height, Parent.Width, Parent.Width / 2)` |
| **Øvre** | **Høyde**   | `If(Parent.Orientation = Layout.Vertical, Parent.Height / 2, Parent.Height)` |
| **Lavere** | X | `If(Parent.Orientation = Layout.Vertical, 0, Upper.X + Upper.Width)`  |
| **Lavere** | Y | `If(Parent.Orientation = Layout.Vertical, Upper.Y + Upper.Height, 0)` |
| **Lavere** | **Bredde** | `Parent.Width - Lower.X` |
| **Lavere** | **Høyde** | `Parent.Height - Lower.Y` |

![uttrykk for å tilpasse en stående retning](media/create-responsive-layout/portrait.png)

![uttrykk for å tilpasse liggende retning](media/create-responsive-layout/landscape.png)

### <a name="screen-sizes-and-breakpoints"></a>Skjermstørrelser og stoppunkt

Du kan justere oppsettet basert på størrelsen på enheten. Skjermens **størrelse** egenskapen klassifiserer den gjeldende enheten-størrelsen. Størrelsen er et positivt heltall; den ScreenSize typen inneholder navngitte konstanter som hjelper med å lese. Denne tabellen viser konstantene:

| Konstant              | Value | Vanlig enhetstypen (ved hjelp av standard appinnstillinger) |
|-----------------------|-------|--------------------------------------------------|
| ScreenSize.Small      | 1     | Telefon                                            |
| ScreenSize.Medium     | 2     | Tavle, beholdes loddrett                          |
| ScreenSize.Large      | 3     | Tavle, beholdes vannrett                        |
| ScreenSize.ExtraLarge | 4     | Stasjonær datamaskin                                 |

Bruk disse størrelsene til å ta avgjørelser om appens oppsett. Hvis du vil at en kontroll til å være skjult på en telefon-størrelse enhet men synlig ellers, kan du for eksempel angi kontrollens **Visible** egenskapen til denne formelen:

`Parent.Size >= ScreenSize.Medium`

Denne formelen returnerer **SANN** når størrelsen er Middels eller større og **USANN** ellers.

Hvis du vil at en kontroll skal ha en annen brøkdel av skjermbredde basert på skjermstørrelse, angi kontrollens **bredde** egenskapen til denne formelen:

```
Parent.Width *  
    Switch(Parent.Size,  
        ScreenSize.Small, 0.5,  
        ScreenSize.Medium, 0.3,  
        0.25)
```
Denne formelen angir bredden til kontrollen til halvdel av skjermen bredden på en liten skjerm, tre-tideler av skjermen bredden på en middels skjerm, og et kvartal i skjermen bredden på alle andre skjermer.

## <a name="custom-breakpoints"></a>Egendefinert stoppunkt

Skjermens **størrelsen** egenskapen beregnes ved å sammenligne skjermens **bredde** egenskapen til verdiene i appens **SizeBreakpoints** egenskapen. Denne egenskapen er en tabell med én kolonne med tall som angir bredden-stoppunkt som skiller de navngitte skjermstørrelser:

I en app som er opprettet for nettbrett eller web, standard-verdi i appens **SizeBreakpoints** egenskapen er **[600, 900, 1200]**. Verdien er i en app som er opprettet for telefoner, **[1200, 1800, 2400]**. (Verdiene for telefonapper er dobbel fordi slike apper bruker koordinater som er effektivt dobbel koordinatene brukes i andre apper.)

![standardverdier for App.SizeBreakpoints egenskap](media/create-responsive-layout/default-breakpoints.png)

Du kan tilpasse appens stoppunkt ved å endre verdiene i appens **SizeBreakpoints** egenskapen. Velg **App** i trevisningen, velg **SizeBreakpoints** i egenskapen listen, og rediger deretter verdiene i formellinjen. Du kan opprette så mange stoppunkt som appen trenger, men bare størrelser på 1 til 4 tilsvarer navngitte skjermstørrelser. I formler, kan du referere til størrelser utover ExtraLarge etter deres numeriske verdier (5, 6 og så videre).

Du kan også angi færre stoppunkt. Appen din kan for eksempel må bare tre størrelser (to stoppunkt), slik at det blir mulig skjermstørrelser liten, Middels og stor.

## <a name="known-limitations"></a>Kjente begrensninger

Redigeringsopplevelsen lerretet svarer ikke til skalering formler som er opprettet. Hvis du vil teste responsive virkemåte, lagre og Publiser appen din, og åpne den på enheter eller i nettleservinduer i forskjellige størrelser og retninger.

Hvis du skriver uttrykk eller formler i den **X**, **Y**, **bredde**, og **høyde** egenskaper for en kontroll, vil du overskrive de uttrykk eller formler hvis du senere dra kontrollen til en annen plassering eller endre størrelsen på kontrollen ved å dra kantlinjene.
