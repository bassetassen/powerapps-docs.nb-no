---
title: Opprett svar oppsett i lerreter | Microsoft Docs
description: Referanse informasjon om hvordan du konfigurerer egenskapene Height, Width, X og Y på kontroller i lerret apper
author: emcoope-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: tapanm-msft
ms.date: 9/20/2019
ms.author: emcoope
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: eee82691b288f21749fe58adbf02ab5ffc3bd8b4
ms.sourcegitcommit: 7016ff837eff2cb0985fc71edab95cbf99335677
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 09/20/2019
ms.locfileid: "71159871"
---
# <a name="create-responsive-layouts-in-canvas-apps"></a>Opprett svar oppsett i lerret apper

Før du bygger en lerret-app i PowerApps, kan du angi om du vil skreddersy appen for en telefon eller et nett brett. Dette valget bestemmer størrelsen på og formen på arbeids sonen der du vil bygge appen.

Etter at du har gjort dette valget, kan du få flere valg hvis du velger**Innstillinger** > for**skjerm størrelse og retning**på **fil** > -appen. Du kan velge stående eller liggende retning og skjerm størrelse (bare på nett brett). Du kan også låse eller låse opp størrelses forhold og støtte enhets rotasjon (eller ikke).

Disse valgene liggerer alle andre valg du gjør mens du utformer skjerm oppsett. Hvis appen kjører på en enhet med en annen størrelse eller på nettet, skaleres hele oppsettet for å tilpasse skjermen der appen kjører. Hvis en app som er utviklet for en telefon, kjører i et stort nett leser vindu, skaleres for eksempel appen for å kompensere og ser ut til å være større enn det som er plass. Appen kan ikke dra nytte av de ekstra pikslene ved å vise flere kontroller eller mer innhold.

Hvis du oppretter et svar oppsett, kan kontroller svare på ulike enheter eller vindus størrelser, noe som gjør at ulike opplevelser er mer naturlige. For å oppnå respons oppsett, kan du justere enkelte innstillinger og skrive uttrykk i hele appen. 

## <a name="disable-scale-to-fit"></a>Deaktiver Tilpass til side

Du kan konfigurere hver skjerm slik at oppsettet tilpasses den faktiske plassen appen kjører på.

Du aktiverer svar tid ved å slå av **skaleringen for appen for å få plass til** innstillingen, som er aktivert som standard. Når du deaktiverer denne innstillingen, deaktiverer du også **Lås størrelses forhold** fordi du ikke lenger utformer for en bestemt skjerm figur. (Du kan fremdeles angi om appen støtter enhets rotasjon.)

![Deaktiver Tilpass til innstilling](media/create-responsive-layout/scale-to-fit-off.png)

Hvis du vil at appen skal svare, må du utføre flere trinn, men denne endringen er det første trinnet for å gjøre det mulig å svare.

## <a name="understand-app-and-screen-dimensions"></a>Forstå app-og skjerm dimensjoner

Hvis du vil at utformingen av appen skal reagere på endringer i skjerm dimensjonene, skriver du formler som bruker **bredde** -og **høyde** -egenskapene på skjermen. Hvis du vil vise disse egenskapene, åpner du en app i PowerApps Studio, og deretter velger du en skjerm. Standard formlene for disse egenskapene vises i **Avansert** -fanen i ruten til høyre.

**Bredde** = `Max(App.Width, App.DesignWidth)`

**Høyden** = `Max(App.Height, App.DesignHeight)`

Disse formlene refererer til egenskapene **Width**, **Height**, **DesignWidth**og **DesignHeight** i appen. Egenskapene for **bredden** og **høyden** på appen Sams varer med dimensjonene til enheten eller nett leser vinduet der appen kjører. Hvis brukeren endrer størrelse på nett leser vinduet (eller roterer enheten hvis du har deaktivert **Lås retningen**), endres verdiene til disse egenskapene dynamisk. Formlene i egenskapene for **bredden** og **høyden** på skjermen evalueres på nytt når disse verdiene endres.

**DesignWidth** -og **DesignHeight** -egenskapene kommer fra dimensjonene som du angir i **skjerm størrelse + retning** -ruten for **App-innstillinger**. Hvis du for eksempel velger telefon oppsettet i stående retning, er **DesignWidth** 640, og **DesignHeight** er 1136.

Som de brukes i formlene for skjermens **bredde** -og **høyde** egenskaper, kan du tenke på **DesignWidth** og **DesignHeight** som minimums dimensjonene du skal utforme appen med. Hvis det faktiske området som er tilgjengelig for appen, er enda mindre enn disse minimums dimensjonene, sikrer formlene for skjermens **bredde** og **høyde** egenskapene at verdiene ikke blir mindre enn minimum. I så fall må brukeren rulle for å vise alt innholdet på skjermen.

Når du har opprettet appens **DesignWidth** og **DesignHeight**, trenger du ikke (i de fleste tilfeller) å endre standard formler for egenskapene for **bredde** og **høyde** i hvert skjerm bilde. Senere diskuterer dette emnet tilfeller der du kanskje vil tilpasse disse formlene.

## <a name="use-formulas-for-dynamic-layout"></a>Bruk formler for dynamisk oppsett

Hvis du vil opprette en svar utforming, kan du finne og skalere hver kontroll ved å bruke formler i stedet for absolutte koordinat verdier (konstant). Disse formlene uttrykker plasseringen og størrelsen til hver kontroll i henhold til den totale skjerm størrelsen eller i forhold til andre kontroller på skjermen.

> [!IMPORTANT]
> Når du har skrevet formler for egenskapene **X**, **Y**, **bredde** og **høyde** i en kontroll, overskrives formlene med konstant verdier hvis du senere drar kontrollen i redigerings programmet for lerret. Når du begynner å bruke formler til å oppnå dynamisk oppsett, bør du unngå å dra kontroller.

I det enkleste tilfellet fyller én kontroll hele skjermen. Hvis du vil opprette denne effekten, kan du angi kontrollens egenskaper til disse verdiene:

| Egenskap      | Value            |
|--------|---------------|
| **KRYSSET**      | `0`             |
| **LODDRETT**      | `0`             |
| **Bredde**  | `Parent.Width`  |
| **Høyden** | `Parent.Height` |

Disse formlene bruker den **overordnede** operatoren. For en kontroll som er plassert direkte på en skjerm, refererer **overordnet** til skjermen. Med disse egenskaps verdiene vises kontrollen i hjørnet øverst til venstre på skjermen (0, 0) og har samme **bredde** og **høyde** som skjermen.

Senere i dette emnet vil du bruke disse prinsippene (og den **overordnede** operatoren) for å plassere kontrollene i andre beholdere, som gallerier, gruppe kontroller og komponenter.

Som et alternativ kan kontrollen bare fylle den øverste halv delen av skjermen. Hvis du vil opprette denne effekten, angir du **Height** -egenskapen til **Parent. Height** /2, og lar de andre formlene være uendret.

Hvis du vil at en annen kontroll skal fylle den nederste halv delen av samme skjerm, kan du ta minst to andre Fremgangs måter for å konstruere formlene. For å gjøre det enkelt kan du ta denne Fremgangs måten:

| Kontroll | Egenskap | Formel           |
|-|----------|-------------------|
| **Øverst** | **KRYSSET**        | `0`                 |
| **Øverst** | **LODDRETT**        | `0`                 |
| **Øverst** | **Bredde**    | `Parent.Width`      |
| **Øverst** | **Høyden**   | `Parent.Height / 2` |
| **Heve** | **KRYSSET**        | `0`                 |
| **Heve** | **LODDRETT**        | `Parent.Height / 2` |
| **Heve** | **Bredde**    | `Parent.Width`      |
| **Heve** | **Høyden**   | `Parent.Height / 2` |

![Øvre og nedre kontroll](media/create-responsive-layout/dynamic-layout.png)

Denne konfigurasjonen vil oppnå ønsket effekt, men du må redigere hver formel hvis du har endret mening om de relative størrelsene på kontrollene. Du kan for eksempel bestemme at den øverste kontrollen skal oppta bare toppen av skjermen, med den nedre kontrollen som fyller ut de nedre to tredje partene. 

Hvis du vil opprette denne effekten, må du oppdatere **Height** -egenskapen for den **øvre** kontrollen og **Y** -og **høyde** -egenskapene for den **nedre** kontrollen. I stedet kan du vurdere å skrive formlene for den **nedre** kontrollen i henhold til den **øvre** kontrollen (og seg selv), som i dette eksemplet:


| Kontroll | Egenskap | Formel           |
|-|----------|-------------------|
| **Øverst** | **KRYSSET**        | `0`                 |
| **Øverst** | **LODDRETT**        | `0`                 |
| **Øverst** | **Bredde**    | `Parent.Width`      |
| **Øverst** | **Høyden**   | `Parent.Height / 2` |
| **Heve** | **KRYSSET**        | `0`                       |
| **Heve** | **LODDRETT**        | `Upper.Y + Upper.Height`  |
| **Heve** | **Bredde**    | `Parent.Width`            |
| **Heve** | **Høyden**   | `Parent.Height - Lower.Y` |

![Øvre og nedre kontroller i forhold til størrelse](media/create-responsive-layout/dynamic-layout2.png)

Med disse formlene, trenger du bare å endre **høyde** -egenskapen for den **øvre** kontrollen for å uttrykke en annen brøk del av høyden på skjermen. Den **nedre** kontrollen flytter og endrer størrelse på til kontoen for endringen.

Du kan bruke disse formel mønstrene for å trykke på felles oppsett relasjoner mellom en kontroll, med navnet **C**og dens overordnede eller en sideordnet kontroll, kalt **D**.

| Relasjon mellom C og dens overordnede | Egenskap | Formel | Illustrasjoner |
|--|--|--|--|
| **C** fyller bredden på det overordnede området, med en margin på *N* | **KRYSSET**| `N` | ![Eksempel på C-utfylling av overordnet objekt](media/create-responsive-layout/c1.png) |
|  | **Bredde** | `Parent.Width - (N * 2)` |  |
| **C** fyller høyden på det overordnede området, med en margin på *N* | **LODDRETT** | `N` | ![Eksempel på C-Utfyllings høyden for overordnet](media/create-responsive-layout/c2.png) |
|  | **Høyden** | `Parent.Height - (N * 2)` |  |
| **C** justert med høyre kant av overordnet, med en margin på *N* | **KRYSSET** | `Parent.Width - (C.Width + N)` | ![Eksempel på C-justering med kant av overordnet](media/create-responsive-layout/c3.png) |
| **C** justert med nedre kant av overordnet, med en margin på *N* | **LODDRETT** | `Parent.Height - (C.Height + N)` | ![Eksempel på C-justering med kant av overordnet](media/create-responsive-layout/c4.png) |
| **C** midt stilt vannrett på overordnet | **KRYSSET** | `(Parent.Width - C.Width) / 2` | ![Eksempel på C midstilt vannrett på overordnet](media/create-responsive-layout/c5.png) |
| **C** midt stilt loddrett på overordnet | **LODDRETT** | `(Parent.Height - C.Height) / 2` | ![Eksempel på C midt stilt loddrett på overordnet](media/create-responsive-layout/c6.png) |

| Relasjon mellom C og D | Egenskap | Formel | Illustrasjoner |
|--|--|--|--|
| **E** vannrett justert med **d** og samme bredde som **D** | **KRYSSET** | `D.X` | ![Eksempel på mønster](media/create-responsive-layout/d1.png) |
|  | **Bredde**    | `D.Width` |  |
| **S** loddrett justert med **d** og samme høyde som **D**  | **LODDRETT** | `D.Y` | ![Eksempel på mønster](media/create-responsive-layout/d2.png) |
|  | **Høyden** | `D.Height` |  |
| Høyre kant på **C** , justert med høyre kant av **D** | **KRYSSET** | `D.X + D.Width - C.Width` | ![Eksempel på mønster](media/create-responsive-layout/d3.png) |
| Nedre kant på **C** , justert med nedre kant av **D** | **LODDRETT** | `D.Y + D.Height - C.Height` | ![Eksempel på mønster](media/create-responsive-layout/d4.png) |
| **C** midt stilt vannrett i forhold til **D** | **KRYSSET** | `D.X + (D.Width - C.Width) / 2`  | ![Eksempel på mønster](media/create-responsive-layout/d5.png) |
| **C** midt stilt loddrett i forhold til **D** | **LODDRETT** | `D.Y + (D.Height - C.Height) /2` | ![Eksempel på mønster](media/create-responsive-layout/d6.png) |
| **C** plassert til høyre for **D** med et tomrom på N | **KRYSSET** | `D.X + D.Width + N` | ![Eksempel på mønster](media/create-responsive-layout/d7.png) |
| **C** plassert under **D** med et intervall på *N*             | **LODDRETT** | `D.Y + D.Height + N` | ![Eksempel på mønster](media/create-responsive-layout/d8.png) |
| **C** fyller ut mellomrom mellom **D** og høyre kant av det overordnede | **KRYSSET** | `D.X + D.Width` | ![Eksempel på mønster](media/create-responsive-layout/d9.png) |
|  | **Bredde** | `Parent.Width - C.X` |  |
| **C** fyller opp mellomrom mellom **D** og nedre kant av det overordnede | Y | `D.Y + D.Height` | ![Eksempel på mønster](media/create-responsive-layout/d10.png) |

## <a name="hierarchical-layout"></a>Hierarkisk oppsett

Når du bygger skjermer som inneholder flere kontroller, blir det mer praktisk (eller nødvendig) å plassere kontrollene i forhold til en overordnet kontroll, i stedet for i forhold til skjermen eller en sideordnet kontroll. Ved å organisere kontrollene i en hierarkisk struktur, kan du gjøre formlene enklere å skrive og vedlikeholde.

### <a name="galleries"></a>Galleri

Hvis du bruker et galleri i appen, må du sette opp kontroller i malen for galleriet. Du kan plassere disse kontrollene ved å skrive formler som bruker den **overordnede** operatoren, som vil referere til galleri malen. Bruk egenskapene **Parent. TemplateHeight** og **Parent. TemplateWidth** i formler på kontroller i en Galleri mal. ikke bruk **forelder. Width** og **Parent. Height**, som refererer til den totale størrelsen på galleriet.

![Loddrett galleri som viser mal bredde og-høyde](media/create-responsive-layout/gallery-vertical.png)

### <a name="container-control"></a>Container-kontroll

Du kan bruke en eksperimentell funksjon, **beholder** -kontrollen, som en overordnet kontroll. Hvis du vil aktivere denne funksjonen, velger du**Avanserte innstillinger**for **fil** > **program innstillinger** > .

Tenk deg eksempel på en topp tekst øverst på et skjerm bilde. Det er vanlig å ha et hode med tittel og flere ikoner som brukerne kan samhandle med. Du kan opprette en slik overskrift ved hjelp av **beholder** kontrollen, som inneholder en **etikett** -kontroll og to- **ikon** -kontroller:

![Topp tekst eksempel ved hjelp av en gruppe](media/create-responsive-layout/header-group.png)

Angi egenskapene for disse kontrollene til disse verdiene:

| Egenskap | Topptekst | Menynavn | Lukk | Tittel |
|--|--|--|--|--|
| **KRYSSET** | `0`  | `0` | `Parent.Width - Close.Width` | `Menu.X + Menu.Width` |
| **LODDRETT** | `0` | `0` | `0` | `0` |
| **Bredde**  | `Parent.Width` | `Parent.Height` | `Parent.Height` | `Close.X - Title.X` |
| **Høyden** | `64` | `Parent.Height` | `Parent.Height` | `Parent.Height` |

`Parent` Refererer til skjermen for **topp tekst** kontrollen. For de andre, `Parent` refererer til **hode** kontrollen.

Hvis du har skrevet disse formlene, kan du justere størrelsen eller plasseringen til **topp tekst** kontrollen ved å endre formlene for egenskapene. Størrelsene og plasseringen til de underordnede kontrollene blir automatisk justert tilsvarende.

### <a name="components"></a>Komponenten

Hvis du bruker en annen eksperimentell funksjon, navngitte komponenter, kan du opprette bygge blokker og bruke dem på nytt i appen. Som med **beholder** kontrollen, bør kontrollene du plasserer i en komponent basere plasserings-og størrelses formlene `Parent.Width` på `Parent.Height`og, som refererer til størrelsen på komponenten. Mer informasjon: [Opprett en komponent](create-component.md).

## <a name="adapting-layout-for-device-size-and-orientation"></a>Tilpasse oppsett for enhets størrelse og-retning

Så langt har du lært hvordan du bruker formler til å endre størrelsen på hver kontroll som svar på den tilgjengelige plassen, samtidig som du beholder kontrollene som er justert i forhold til hverandre. Men det kan være lurt å gjøre mer omfattende oppsett endringer som svar på ulike enhets størrelser og-retninger. Når en enhet roteres fra stående til liggende retning, kan det for eksempel hende at du ønsker å bytte fra et loddrett oppsett til en vannrett. På en større enhet kan du presentere mer innhold eller ordne det på nytt for å gi et mer tiltalende oppsett. På en mindre enhet må du kanskje dele innhold på tvers av flere skjermer.

### <a name="device-orientation"></a>Enhets retning

Standard formlene for egenskapene for **bredden** og **høyden** på et skjerm bilde, siden dette emnet beskrevet tidligere, vil ikke nødvendigvis gi en god opplevelse hvis en bruker roterer en enhet. For eksempel har en app som er utformet for en telefon i stående retning, en **DesignWidth** på 640 og en **DesignHeight** på 1136. Den samme appen på en telefon i liggende retning vil ha disse egenskaps verdiene:

- Skjermens **bredde** -egenskap er satt til `Max(App.Width, App.DesignWidth)`. **Størrelsen** på appen (1136) er større enn **DesignWidth** (640), så formelen evaluerer til 1136.
- Skjerm **høyden** -egenskapen er satt til `Max(App.Height, App.DesignHeight)`. **Høyden** på appen (640) er mindre enn **DesignHeight** (1136), så formelen evalueres til 1136.

Med en skjerm **høyde** på 1136 og en enhets høyde (i denne retningen) 640, må brukeren rulle skjermen loddrett for å vise alt innholdet, som kanskje ikke er den ønskede opplevelsen.

Hvis du vil tilpasse egenskapene for **bredden** og **høyden** på skjermen til enhets retningen, kan du bruke disse formlene:

**Bredde** = `Max(App.Width, If(App.Width < App.Height, App.DesignWidth, App.DesignHeight))`

**Høyden** = `Max(App.Height, If(App.Width < App.Height, App.DesignHeight, App.DesignWidth))`

Disse formlene bytter appens **DesignWidth** -og **DesignHeight** -verdier basert på om enhetens bredde er mindre enn høyden (stående retning) eller mer enn høyden (liggende retning).

Når du justerer skjermens **bredde** -og **høyde** -formler, kan det hende du også vil ordne kontrollene på skjermen på nytt for å bedre bruke den tilgjengelige plassen. Hvis for eksempel hver av to kontroller opptar halv parten av skjermen, kan du stable dem loddrett i stående, men ordne dem side ved side i liggende retning.

Du kan bruke skjermens **retning** -egenskap til å finne ut om skjermen er orientert loddrett eller vannrett.

> [!NOTE]
> I liggende retning vises de **øvre** og **nedre** kontrollene som venstre og høyre kontroller.

| Kontroll | Egenskap | Formel |
|--|----------|---|
| **Øverst** | **KRYSSET** | `0` |
| **Øverst** | **LODDRETT** | `0` |
| **Øverst** | **Bredde** | `If(Parent.Orientation = Layout.Vertical, Parent.Width, Parent.Width / 2)` |
| **Øverst** | **Høyden**   | `If(Parent.Orientation = Layout.Vertical, Parent.Height / 2, Parent.Height)` |
| **Heve** | X | `If(Parent.Orientation = Layout.Vertical, 0, Upper.X + Upper.Width)`  |
| **Heve** | Y | `If(Parent.Orientation = Layout.Vertical, Upper.Y + Upper.Height, 0)` |
| **Heve** | **Bredde** | `Parent.Width - Lower.X` |
| **Heve** | **Høyden** | `Parent.Height - Lower.Y` |

![uttrykk for å tilpasse en stående retning](media/create-responsive-layout/portrait.png)

![uttrykk for å tilpasse en liggende retning](media/create-responsive-layout/landscape.png)

### <a name="screen-sizes-and-breakpoints"></a>Skjerm størrelser og-stoppunkt

Du kan justere oppsettet basert på størrelsen på enheten. Skjerm **størrelses** egenskapen klassifiserer gjeldende enhets størrelse. Størrelsen er et positivt hel tall. ScreenSize-typen gir navn til konstanter for å hjelpe deg med lesbarhet. Denne tabellen inneholder en liste over konstantene:

| Fast              | Value | Vanlig enhets type (ved hjelp av standard app-innstillinger) |
|-----------------------|-------|--------------------------------------------------|
| ScreenSize. Small      | 1     | Samtaler                                            |
| ScreenSize. middels     | 2     | Nett brett, holdt loddrett                          |
| ScreenSize. store      | 3     | Nett brett, holdt vannrett                        |
| ScreenSize.ExtraLarge | 4     | Stasjonær data maskin                                 |

Bruk disse størrelsene for å ta avgjørelser om utformingen av appen. Hvis du for eksempel vil at en kontroll skal skjules på en enhet med telefon størrelsen, men kan vises på en annen måte, kunne du angi kontrollens **synlige** egenskap til denne formelen:

`Parent.Size >= ScreenSize.Medium`

Denne formelen evalueres til **sann** når størrelsen er middels eller større og ellers **False** .

Hvis du vil at en kontroll skal ha en annen brøk av skjerm bredden basert på skjerm størrelsen, kan du angi **bredde** -egenskapen for kontrollen til denne formelen:

```powerapps-dot
Parent.Width *  
    Switch(Parent.Size,  
        ScreenSize.Small, 0.5,  
        ScreenSize.Medium, 0.3,  
        0.25)
```
Denne formelen angir bredden til kontrollen til halv parten av skjerm bredden på en liten skjerm, tre tiende deler av skjerm bredden på en middels skjerm, og et kvartal av skjerm bredden på alle andre skjermer.

## <a name="custom-breakpoints"></a>Egen definerte stoppunkt

Skjermens **størrelse** -egenskap beregnes ved å sammenligne skjermens **bredde** -egenskap med verdiene i **SizeBreakpoints** -egenskapen for appen. Denne egenskapen er en tabell med én kolonne med tall som angir bredden på grense punkter som skiller de navngitte skjerm størrelsene:

I en app som er opprettet for nett brett eller nett, er standard verdien i appens **SizeBreakpoints** -egenskap **[600, 900, 1200]** . I en app som er opprettet for telefoner, er verdien **[1200, 1800, 2400]** . (Verdiene for telefon programmer dobles fordi slike apper bruker koordinater som effektivt dobler koordinatene som brukes i andre apper.)

![standard verdier for App. SizeBreakpoints-egenskap](media/create-responsive-layout/default-breakpoints.png)

Du kan tilpasse avbrudds punkt for appen ved å endre verdiene i appens **SizeBreakpoints** -egenskap. Velg **app** i tre visningen, velg **SizeBreakpoints** i egenskaps listen, og rediger deretter verdiene i formel linjen. Du kan opprette så mange stoppunkt som appen trenger, men bare størrelsene 1 til 4 Sams varer med navngitte skjerm størrelser. I formler kan du referere til størrelser utover ExtraLarge etter de numeriske verdiene (5, 6 og så videre).

Du kan også angi færre stoppunkt. For eksempel kan appen kanskje bare ha tre størrelser (to stoppunkt), så de mulige skjerm størrelsene vil være små, middels og store.

## <a name="known-limitations"></a>Kjente begrensninger

Redigerings lerretet svarer ikke til de opprettede Skalerings formlene. Hvis du vil teste svar atferden, kan du lagre og publisere appen, og deretter åpne den på enheter eller i nett leser Vinduer av ulike størrelser og retnings programmer.

Hvis du skriver uttrykk eller formler i egenskapene **X**, **Y**, **bredde**og **høyde** for en kontroll, overskrives disse uttrykkene eller formlene hvis du senere drar kontrollen til en annen plassering eller endrer størrelsen på kontrollen ved å dra kant linjen.
