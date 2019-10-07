---
title: Slik fungerer oppsett for dataskjemaer for lerretsapper | Microsoft Docs
description: Opprett flotte skjemaoppsett i lerretsapper i PowerApps ved å bruke rader og kolonner.
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 06/17/2017
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 2ef11e767fcf92259839c4bebe282757b0004f21
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/07/2019
ms.locfileid: "71989128"
---
# <a name="understand-data-form-layout-for-canvas-apps-in-powerapps"></a>Slik fungerer oppsett for dataskjemaer for lerretsapper i PowerApps

Opprett et flott og effektivt skjema på en enkel måte når du bygger en lerretsapp i PowerApps. Ta for eksempel i betraktning denne grunnleggende formen for registrering av salgsordre:

![Eksempel på salgsordre](./media/working-with-form-layout/sales-order.png)

I denne opplæringen går vi gjennom trinnene for å opprette dette skjemaet. Vi skal også se på noen avanserte emner, for eksempel dynamisk skalering av feltene, for å fylle tilgjengelig plass.

## <a name="before-you-start"></a>Før du starter

Hvis PowerApps er nytt for deg (eller du bare har generert apper automatisk), må du [bygge en app fra grunnen av](get-started-create-from-blank.md) før du fordyper deg i dette emnet. Ved å bygge en app fra grunnen av blir du kjent med nødvendige konsepter, for eksempel å legge til datakilder og kontroller, som er nevnt, men som ikke er beskrevet i dette emnet.

Dette emnet er skrevet som om du har en data kilde som heter **salgs ordre** , og som inneholder feltene i den forrige grafikken. Hvis du har en PowerApps plan 2-lisens eller en [prøve lisens](../signup-for-powerapps.md) og system administrator eller Systemtilpasser-tillatelser, kan du [opprette en enhet](../common-data-service/data-platform-create-entity.md) i Common data service og legge til lignende felt. 

## <a name="add-a-gallery"></a>Å legge til et galleri

1. Opprett en tavle-app fra grunnen av, og Legg til data kilden.

    Alt som beskrives i dette emnet gjelder også for telefonoppsett, men telefonapper har ofte bare én loddrett kolonne.
    
2. Legg til en loddrett **Galleri**-kontroll, og angi **Element**-egenskapen til **Salgsordre**.
   
    (valgfritt) Endre **Oppsett** i galleriet til å vise bare **Tittel og undertittel** for å samsvare med eksemplene i denne opplæringen.
   
    ![Liste for salgsordre](./media/working-with-form-layout/gallery-layout.png)
3. Klikk eller trykk på **SO004** i galleriet.
   
    ![Liste for salgsordre](./media/working-with-form-layout/sales-order-gallery-screen.png)
   
    Denne oppføringen vises i skjemaet som du bygger ved å følge trinnene senere i dette emnet.

## <a name="add-a-title-bar"></a>Å legge til en tittellinje
1. Legg til en tom skjerm der du vil legge til skjemaet.
   
    Utenfor denne opplæringen, kan du plassere **Galleri**- og **[Redigeringsskjema](controls/control-form-detail.md)** -kontrollene i den samme skjermen, men du får mer plass å arbeide med hvis du legger dem til på separate skjermer.
2. Øverst på den nye skjermen, kan du legge til en **[Etikett](controls/control-text-box.md)** -kontroll, og angi **Tekst**-egenskapen til dette uttrykket:
   <br>**"Sales Order " & Gallery1.Selected.SalesOrderId**
   
    Etiketten viser salgsordre-nummer for posten som du har valgt i galleriet.
3. (valgfritt) Formater etiketten som følger:
   
   1. Angi **Juster**-egenskapen til **Midtstilt**.
   
   2. Angi **Størrelse**-egenskapen til **20**.
   
   3. Angi **Fyll**-egenskapen til **Marineblå**.
   
   4. Angi **Farge**-egenskapen til **Hvit**.
   
   5. Angi **Bredde**-egenskapen til **Parent.Width**.
   
   6. Angi **X**- og **Y**-egenskapen til **0**.
      
      ![Tittellinje](./media/working-with-form-layout/title-bar.png)

## <a name="add-a-form"></a>Å legge til et skjema
1. Legg til en **Redigeringsskjema**-kontroll, og flytt og endre deretter størrelsen, slik at den fyller skjermen under etiketten.
   
    I neste trinn, kobler du sammen skjemakontrollen til datakilden **Salgsordre** ved hjelp av den høyre ruten, ikke formellinjen. Hvis du bruker formellinjen, viser ikke skjemaet noen felt som standard. Du kan alltid vise alle feltene du vil, ved å velge én eller flere avmerkingsbokser i ruten til høyre.
2. Klikk eller trykk på Pil ned, til høyre for **Ingen datakilde er valgt** i den høyre ruten, og klikk eller trykk deretter på **Salgsordre**.
   
    Et standardsett med felt fra datakilden for **Salgsordre** vises i et enkelt oppsett med tre kolonner. Mange av dem er imidlertid tomme, og de kan bruke litt tid å tilpasse seg til sine endelige posisjoner.  
3. Angi **Element**-egenskapen for skjemaet til **Gallery1.Selected**.
   
    Skjemaet viser posten som du valgte i galleriet, men standard filsett samsvarer kanskje ikke med det du ønsker i det endelige produktet.
4. I den høyre ruten skjuler du hver av disse feltene ved å fjerne merket for avmerkingsboksen:
   
   * **Salgsordre-ID**
   * **Konto**
   * **Selger**
   * **Kontaktperson**
5. Flytt feltet for **Ordrestatus** ved å dra det til venstre og plassere det på den andre siden av feltet for **Bestillingsreferanse for kunde**.
   
    Skjermen bør ligne på dette eksemplet:
   
    ![Salgsordren i et grunnleggende oppsett med tre kolonner](./media/working-with-form-layout/sales-order-form-screen-3.png)

## <a name="select-a-data-card"></a>Å velge et datakort
Hvert felt som vises har et tilsvarende datakort i skjemaet. Dette kortet består av et sett med kontroller for tittelfeltet, en inndataboks, en stjerne (som vises hvis feltet er nødvendig) og en feilmelding for validering.

Du kan også velge kort direkte i skjemaet. Når et kort er valgt, vises en svart bildetekst over det.

![Utvalg for datakort](./media/working-with-form-layout/sales-order-data-card-selection.png)

> [!NOTE]
> Velg kortet, og trykk deretter på Slett for å slette et kort (ikke bare skjule det).

## <a name="arrange-cards-in-columns"></a>Å ordne kortene i kolonner
Skjemaer for nettbrettapper har tre kolonner og de for telefonapper har én, som standard. Du kan ikke bare angi hvor mange kolonner et skjema har, men også om alle kortene skal passe innenfor kantlinjer for kolonner.

I denne grafikken er antall kolonner i skjemaet som ble endret fra tre til fire med avmerkingsboksen **Fest til kolonner**, valgt. Kortene i skjemaet ble ordnet automatisk for å passe til det nye oppsettet.

![Salgsordre i et grunnleggende oppsett med fire kolonner](./media/working-with-form-layout/sales-order-form-screen-4.png)

## <a name="resize-cards-across-multiple-columns"></a>Å endre størrelse på kort på tvers av flere kolonner
Avhengig av dataene i hvert kort vil du kanskje at noen kort skal få plass i en enkelt kolonne, og at andre kort skal strekke seg over flere kolonner. Hvis et kort inneholder mer data enn det du vil vise i en enkelt kolonne, kan du utvide kortet ved å merke det og deretter dra i håndtaket på venstre eller høyre kantlinjen av valgboksen. Når du drar i håndtaket, vil kortet «festes» til kolonnegrensene.

Hvis du vil gjøre utformingen mer fleksibel, men beholde noe struktur, kan du øke antallet kolonner til 12. Med denne endringen kan du enkelt konfigurere hvert kort for å dekke hele skjemaet, halvparten av skjemaet, en tredjedel, en fjerdedel, en sjettedel, og så videre. La oss se på dette i praksis.

1. I den høyre ruten angir du antall kolonner i skjemaet til **12**.
   
    ![Å angi antall kolonner](./media/working-with-form-layout/12-columns.png)
   
    Skjemaet endrer ikke utseende, men du har flere forankringspunkter mens du drar i det venstre eller høyre håndtaket.
2. Øk bredden på **Bestillingsdato**-kortet ved å dra det høyre håndtaket ett forankringspunkt til høyre.
   
    Kortet strekker seg over fire av skjemaets 12 kolonner (eller 1/3 av skjemaet), i stedet for bare tre av skjemaets 12 kolonner (eller 1/4 av skjemaet). Når du øker bredden på et kort med et forankringspunkt, vil kortet strekke seg over en ekstra 1/12 for skjemaet.
   
    ![Å endre størrelsen på et kort med dra-og-slipp](./media/working-with-form-layout/card-resize-1.png)
3. Gjenta det forrige trinnet med kortene **Ordrestatus** og **Bestillingsreferanse for kunde**.
   
    ![Tre kort i første rad](./media/working-with-form-layout/card-resize-2.png)

4. Endre størrelsen på kortene **Navn** og **Beskrivelse** til å oppta seks kolonner (eller 1/2) for skjemaet.

5. Få de to første linjene for leveringsadressen til å strekke seg helt ut på tvers av skjemaet:

Ferdig. Vi har det ønskede skjemaet vårt, med en blanding av rader med ulikt antall kolonner:

![Salgsordren i et oppsett med 12 kolonner med skalering](./media/working-with-form-layout/card-resize-done.png)

## <a name="manipulate-controls-in-a-card"></a>Å endre kontroller i et kort
Leveringsadressen består av flere deler med informasjon som vi ønsker å gruppere for brukeren visuelt. Hvert felt forblir i sine egne datakort, men vi kan endre kontrollene i kortet slik at de passer bedre sammen.

1. Velg kortet for **Første linje i leveringsadresse**, velg deretter etiketten i kortet, og slett de tre første ordene fra teksten.
   
    ![Å gi nytt navn til den første etikettlinjen i leveringsadresse for salgsordre](./media/working-with-form-layout/delivery-address-rename.png)
2. Velg kortet for **Andre linje i leveringsadresse**, velg deretter etiketten i kortet, og slett all tekst i det.
   
    Det kan være fristende å ganske enkelt fjerne etiketten, og i mange tilfeller vil det fungere bra. Men formler kan være avhengige av at denne kontrollen finnes. En tryggere tilnærming er å fjerne teksten eller angi **Synlig**-egenskapen for kontrollen til **usann**.
   
    ![Gi nytt navn til den andre etikettlinjen i leveringsadresse for salgsordre](./media/working-with-form-layout/delivery-address-rename-2.png)
3. Flytt inndata tekstboksen over etiketten for å redusere avstanden mellom første og andre linjene av adressen i det samme kortet.
   
    Høyden på kortet krymper når innholdet tar opp mindre plass.
   
    ![Å gi nytt navn til den andre etikettlinjen i leveringsadresse for salgsordre](./media/working-with-form-layout/delivery-address-move-input.png)

La oss nå rette oppmerksomheten mot tredje linje i adressen. I likhet med det vi nettopp gjorde, kan vi forkorte teksten i hver etikett for disse kortene og ordne Tekstinndata-boksen til å stå til høyre for hver etikett. Her er fremgangsmåten for **Tilstand**-kortet:

| Step | Beskrivelse | Resultat |
| --- | --- | --- |
| 1 |Velg **Tilstand**-kortet slik at håndtak vises rundt det. |![Slik velger man et kort](./media/working-with-form-layout/state-morph-2.png) |
| 2 |Velg etiketten i dette kortet, slik at håndtak vises rundt den. |![Slik velger du en kontroll i et kort](./media/working-with-form-layout/state-morph-3.png) |
| 3 |Plasser markøren til høyre for teksten, og slett deretter delen som vi ikke trenger. |![Slik endrer du teksten i en kontroll i et kort](./media/working-with-form-layout/state-morph-3b.png) |
| 4 |Du kan endre størrelse på etikettkontrollen for å få plass til den nye tekststørrelsen ved hjelp av sidene på håndtakene. |![Slik endrer du en kontroll i et kort](./media/working-with-form-layout/state-morph-4b.png) |
| 5 |Velg Tekstinndata-kontrollen i dette kortet. |![Slik velger du en annen kontroll i kortet](./media/working-with-form-layout/state-morph-6.png) |
| 6 |Du kan endre størrelse på Tekstinndata-kontrollen til ønsket størrelse ved hjelp av sidene på håndtakene. |![Slik endrer du en kontroll i et kort](./media/working-with-form-layout/state-morph-6b.png) |
| 7 |Dra Tekstinndata-boksen opp og til høyre for etiketten, og slipp deretter Tekstinndata-boksen. |![Å flytte en kontroll i et kort](./media/working-with-form-layout/state-morph-7b.png) |
| Våre endringer i **Tilstand**-kortet er nå fullført. |![Endringene i kortet er nå fullført](./media/working-with-form-layout/state-morph-8.png) | |

Resultatet for den fullstendige tredje adresselinjen:

![Leveringsadresse for salgsordre med en mer konsis tredje linje](./media/working-with-form-layout/delivery-address-resize-city-1.png)

Vær oppmerksom på at mange av kortene begynner med en dynamisk formel for egenskapene. Tekstinndata-kontrollen som vi endret størrelsen på og flyttet tidligere, hadde for eksempel en **Bredde**-egenskap basert på bredden på det overordnede området. Når du flytter eller endrer størrelse på en kontroll, erstattes disse dynamisk formlene med statiske verdier. Hvis du vil, kan du gjenopprette de dynamiske formlene ved hjelp av formellinjen.

## <a name="turning-off-snap-to-columns"></a>Slå av Festing til kolonner
Noen ganger vil du ha bedre kontroll enn det standarden med 12 kolonner kan gi. For disse tilfellene kan du slå av **Fest til kolonner** og deretter plassere kort manuelt. Skjemaet vil fortsette å feste seg til 12 kolonner, men du kan også holde nede ALT for å manuelt plassere og endre størrelsen på et kort slik du ønsker.

I vårt eksempel har alle de fire komponentene som utgjør den tredje adresselinjen nøyaktig samme bredde. Men dette er kanskje ikke det beste oppsettet, siden bynavn er lengre enn forkortelser for tilstand, og Tekstinndata-boksen for land/områder er korte på grunn av lengden på etiketten.

Hvis du vil optimalisere området, kan du slå av **Fest til kolonner** i den høyre ruten, og deretter holde nede ALT mens du endrer størrelse og plassering for disse kortene. Alle kontroller viser svart bildetekst når du holder nede ALT. Denne virkemåten er etter utforming standard til å vise kontrollnavn.

![Flytte og endre størrelse ved bruk av ALT-tasten](./media/working-with-form-layout/delivery-address-alt-resize.png)

Etter forsiktig plassering har resultatet riktig størrelse for hvert felt, og til og med for vannrett avstanden mellom feltene:

![Nøyaktig plassering for tredje linje for leveringsadresse for salgsordre](./media/working-with-form-layout/delivery-address-resize-city-2.png)

For å summere: hva er forskjellene når **Fest til kolonner** er på eller av?

| Virkemåte | Fest til kolonner på | Fest til kolonner av |
| --- | --- | --- |
| Endring av størrelse på festing |Antall kolonner som du velger:<br>1, 2, 3, 4, 6, eller 12 |12 kolonner |
| Endring av størrelse på festing kan ikke overstyres |nei |Ja, ved bruk av ALT |
| Kort lager automatisk nye oppsett mellom rader (mer om dette senere) |ja |nei |

## <a name="set-width-and-height"></a>Å angi bredde og høyde
Utformingen styres av egenskaper i kortkontrollene, i likhet med alt annet i PowerApps. Du kan endre verdiene for disse egenskapene som allerede beskrevet ved å dra kontrollene til forskjellige plasseringer, eller å dra i håndtakene for å endre størrelsen på kontroller. Men du vil oppdage situasjoner der du vil forstå og endre disse egenskapene mer nøyaktig, spesielt når du vil gjøre skjemaene dynamiske med formler.

### <a name="basic-layout-x-y-and-width"></a>Grunnleggende oppsett: X, Y og bredde
**X**- og **Y**-egenskaper kontrollerer plasseringen av kortene. Når vi arbeider med kontroller på arbeidssonen, vil disse egenskapene gi en absolutt plassering. Disse egenskapene har en annen betydning i et skjema:

* **X**: Rekkefølge i en rad.
* **Y**: Rad nummer.

**Bredde**-egenskapen angir minimumsbredden på kortet (mer om minimumsaspektet om et øyeblikk), i likhet med kontroller på lerretet.

La oss ta en titt på **X**-, **Y**- og **Bredde**-egenskaper for kortene i skjemaet vårt:

![X- og Y-koordinater for salgsordreskjemaer](./media/working-with-form-layout/sales-order-xy.png)

### <a name="overflowing-rows"></a>Overflytende rader
Hva skjer hvis kortene i en rad er for brede til å få plass på denne raden? Vanligvis trenger du ikke å bekymre deg om dette. Med **Fest til kolonner** slått på, vil disse tre egenskapene justeres automatisk slik at alt passer fint inn i rader uten overflyt.

Men med **Fest til kolonner** slått av, eller med en formel-basert **Bredde** på ett eller flere av kortene, kan det oppstå overflyt av en rad. I dette tilfellet vil kortene automatisk tekstbrytes, noe som fører til at en ny rad opprettes. La oss for eksempel manuelt endre **Bredde**-egenskapen for kortet **Bestillingsreferanse for kunde** (første rad, tredje elementet) til **500**:

![Manuell endring av størrelse på et kort, dynamisk tilpasning til en ny rad](./media/working-with-form-layout/manual-size-500.png)

De tre kortene på den øverste raden passer ikke lenger vannrett, og en annen rad er opprettet for å tekstbryte overflyten. **Y**-koordinaten for alle disse kortene er fremdeles det samme ved 0, og **Navn**- og **Beskrivelse**-kort har fortsatt 1 for **Y**. Kort som har ulike **Y**-verdier blir ikke slått sammen på tvers av rader.

Du kan bruke denne virkemåten til å opprette et fullstendig dynamisk oppsett der kort plasseres basert på en Z-rekkefølge, som fyller på tvers av så mye som mulig før den flyttes til neste rad. Gi alle kortene den samme **Y**-verdien for å oppnå denne effekten, og bruk **X** for rekkefølgen på kortene.

### <a name="filling-spaces-widthfit"></a>Fyller mellomrom: WidthFit
Overflyten i det siste eksemplet opprettet et mellomrom etter **Ordrestatus**-kortet, som var det andre kortet i den første raden. Vi kan manuelt justere på **Bredde**-egenskapene for de to gjenstående kortene til å fylle ut området, men denne tilnærmingen er langtekkelig.

Som et alternativ kan du bruke **WidthFit**-egenskapen. Hvis denne egenskapen er satt til **sann** for én eller flere kort i en rad, vil resten av området på raden bli jevnt fordelt mellom dem. Denne virkemåten er grunnen til at vi tidligere nevnte at **Bredde**-egenskapen for et kort er et *minimum*, og at det som faktisk vises kan være bredere. Denne egenskapen vil aldri føre til at et kort reduseres, bare utvides.

Hvis du vi angi **WidthFit** til **sann** på **Ordrestatus**-kortet, vil den fylle den tilgjengelige plassen, mens det første kortet forblir uendret:

![Med WidthFit satt til sann på andre kort](./media/working-with-form-layout/manual-widthfit-1.png)

Hvis vi også vil sette **WidthFit** til **sann** på **Bestillingsdato**-kortet, vil begge kortene dele den tilgjengelige plassen likt:

![Med WidthFit satt til sann på første og andre kort](./media/working-with-form-layout/manual-widthfit-2.png)

Vær oppmerksom på at håndtakene på disse kortene tar hensyn til den ekstra bredden oppgitt for **WidthFit**, ikke minimumsbredden som oppgis for **Bredde**-egenskapen. Det kan være forvirrende å endre **Bredde**-egenskapen mens **WidthFit** er aktivert. Du vil kanskje deaktivere den, gjøre endringer i **Bredde**, og deretter slå den på igjen.

Når kan **WidthFit** være nyttig? Hvis du har et felt som bare brukes i enkelte situasjoner, kan du angi **Synlig**-egenskapen til **usann**, og de andre kortene på raden vil automatisk fylle området rundt det. Du vil kanskje bruke en formel som viser et felt bare når et annet felt har en bestemt verdi.

Vi konfigurerer **Synlig**-egenskapen for **Ordrestatus**-feltet til en statisk **usann**:

![Med WidthFit angitt til SANN på første kortet med usynlig ordrestatus](./media/working-with-form-layout/manual-widthfit-3.png)

Med det andre kortet effektivt fjernet, kan det tredje kortet nå returnere til den samme raden som det første kortet. Det første kortet har fortsatt **WidthFit** satt til **sann**, slik at kun det utvides for å fylle den tilgjengelige plassen.

Fordi **Ordrestatus** er usynlig, kan du ikke velge det like enkelt på arbeidssonen. Du kan imidlertid velge en kontroll, synlig eller ikke, i den hierarkiske listen over kontroller på venstre side av skjermen.

### <a name="height"></a>Høyde
**Høyde**-egenskapen styrer høyden på hvert kort. Kort er tilsvarende for **WidthFit** som for **Høyde**, og de er alltid satt til **sann**. Tenk deg at en **HeightFit**-egenskap finnes, men ikke let etter den i produktet fordi egenskapen er ikke eksponert ennå.

Du kan ikke slå av denne virkemåten, slik at det kan være utfordrende å endre høyden på kort. Alle kortene i en rad ser ut til å ha samme høyde som det høyeste kortet. Du ser kanskje på en rad som dette:

![Med WidthFit satt til sann på det første kortet med usynlig ordrestatus](./media/working-with-form-layout/height-3.png)

Hvilket kort gjør raden høy? I den forrige grafikken var **Totalbeløp**-kortet valgt, og så ut til å være høyt, men **Høyde**-egenskapen er angitt til **80** (samme som høyden på den første raden). Hvis du vil redusere høyden på en rad, må du redusere **Høyde** for det høyeste kortet i denne raden, og du kan ikke identifisere det høyeste kortet uten å gå gjennom **Høyde**-egenskapen for hvert kort.

### <a name="autoheight"></a>AutoHeight
Et kort kan også være høyere enn forventet hvis det inneholder en kontroll der **AutoHeight**-egenskapen er satt til **sann**. Mange kort inneholder for eksempel en etikett som viser en feilmelding, hvis feltverdien forårsaker et problem for validering.

Uten noen tekst som skal vises (ingen feil), vil etiketten skjules til null i høyde. Hvis du ikke visste bedre, ville du ikke visst at det var der, og det er slik det skal være:

![Kort som inneholder kontroller med AutoHeight satt til sann, som ikke viser en høyde](./media/working-with-form-layout/autoheight-0.png)

Listen over kontroller viser **ErrorMessage1** på venstre side av skjermen, som er vår etikettkontroll. Når du oppdaterer en app, kan du velge denne kontrollen til å gi den litt høyde og vise håndtakene som du kan bruke til å plassere og endre størrelse på kontrollen. «A»-en i en blå boks indikerer at kontrollen har **AutoHeight** satt til **sann**:

![I redigeringsmodus viser AutoHeight-kontrollene noe høyde som gjør dra-og-slipp enklere](./media/working-with-form-layout/autoheight-1.png)

**Tekst**-egenskapen for denne kontrollen er angitt til **Parent.Error**, som brukes for å få dynamisk informasjon om feil basert på regler for validering. La oss statisk angi **Tekst**-egenskapen for denne kontrollen for å illustrere formålet, noe som vil øke høyden (og følgelig høyden på kortet) for å få plass til lengden på teksten:

![Med en feilmelding vokser kontrollen og kortet automatisk](./media/working-with-form-layout/autoheight-2.png)

La oss gjøre feilmeldingen litt lengre, slik at kontrollen og kortet igjen vokser for å lage plass. Vær oppmerksom på at hele raden vokser i høyden, mens den bevarer loddrett justering mellom kortene:

![Med en lengre feilmelding vokser kontrollen og kortet enda mer, og legg merke til at alle kortene på den samme raden vokser sammen](./media/working-with-form-layout/autoheight-3.png)

