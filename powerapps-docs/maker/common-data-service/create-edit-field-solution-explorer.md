---
title: Opprette og redigere felt for Common Data Service ved hjelp av løsningsutforskeren i PowerApps | MicrosoftDocs
ms.custom: ''
ms.date: 05/18/2018
ms.reviewer: ''
ms.service: powerapps
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - PowerApps
ms.author: matp
manager: brycho
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="create-and-edit-fields-for-common-data-service-using-powerapps-solution-explorer"></a>Opprette og redigere felt for Common Data Service ved hjelp av løsningsutforskeren i PowerApps

Løsningsutforskeren har en måte for å opprette og redigere felt for Common Data Service.

[PowerApps-portalen](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) gjør det mulig for konfigurasjon av de vanligste alternativene, men enkelte alternativer kan bare angis ved hjelp av løsningsutforskeren. <br />Mer informasjon: 
- [Opprette og redigere felt for Common Data Service](create-edit-fields.md)
- [Opprette og redigere felt for Common Data Service ved hjelp av PowerApps-portalen](create-edit-field-portal.md)
  
## <a name="open-solution-explorer"></a>Åpne løsningsutforskeren

En del av navnet på egendefinerte felt du oppretter, er tilpassingsprefikset. Dette angis basert på løsningsutgiveren for løsningen du arbeider i. Hvis du er interessert i tilpassingsprefikset, må du kontrollere at du arbeider i en ikke-administrert løsning der tilpassingsprefikset er det du vil bruke for denne enheten. Mer informasjon: [Endre løsningsutgiverprefikset](change-solution-publisher-prefix.md) 

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]


## <a name="view-fields"></a>Visningsfelt

Med løsningsutforskeren åpen, under **Komponenter**, utvider du **Enheter** og velger enheten der du vil opprette eller redigere feltet.

![Feltvisning i løsningsutforsker](media/solution-explorer-fields-view.png)

Du kan velge følgende visninger: 

 |Visning|Beskrivelse|
 |--|--|
 |**Alle**| Viser alle feltene for enheten|
 |**Egendefinert**|Viser bare egendefinerte felt for enheten|
 |**Kan tilpasses**|Viser bare feltene som kan redigeres|

## <a name="create-a-field"></a>Opprette et felt

Når du viser felt, klikker du på **Ny** på kommandolinjen som åpner skjemaet for nytt felt.  Noen standardenheter eller egendefinerte enheter som er inkludert i en administrert løsning, lar deg kanskje ikke legge til nye felt.

> [!NOTE]
> For modelldrevne apper kan du også opprette et nytt felt fra skjemaredigeringsprogrammet. I skjemaredigeringsprogrammet klikker du på **Nytt felt** under **Feltutforsker** for å opprette et nytt felt. Mer informasjon: [Legge til et felt i et skjema](../model-driven-apps/add-field-form.md)

![Skjema for nytt felt i løsningsutforsker](media/solution-explorer-new-field-form.png)

Du må skrive inn data og bekrefte standardverdiene som er angitt for følgende egenskaper før du lagrer.

|Egenskap|Beskrivelse|
|--|--|
|**Visningsnavn**|Teksten som skal vises for feltet i brukergrensesnittet. Du kan endre dette når du har lagret, men verdien du angir, genererer en verdi for **Navn**-feltet.|
|**Feltkrav**|Om data kreves i feltet for å lagre oppføringen. Mer informasjon: [Feltkravalternativer](#field-requirement-options)|
|**Navn**|Det unike navnet i hele miljøet. Det genereres et navn for deg basert på visningsnavnet som du har angitt, men du kan redigere det før du lagrer. Når et felt er opprettet, kan ikke navnet endres siden den kan bli referert til i programmene eller koden. Navnet vil ha tilpassingsprefikset for utgiveren av gjeldende løsning foran.|
|**Søkbar**|Sett dette til **Nei** for felt for enheten som du ikke bruker.  Når et felt er søkbart, vises det i **Avansert søk** i modelldrevne apper og er tilgjengelig når du tilpasser visninger. Hvis du opphever dette, vil dette redusere antall alternativer som vises for brukere som bruker avansert søk.|
|**Feltsikkerhet**|Om dataene i feltet sikres på et høyere nivå enn enheten. Mer informasjon: [Feltnivåsikkerhet for å kontrollere tilgang](/dynamics365/customer-engagement/admin/field-level-security)|
|**Sporing av endringer**|Om data for dette feltet skal spores for endringer når enheten aktiveres for sporing av endringer. Mer informasjon: [Spore endringer av data og brukeraktivitet for sikkerhet og samsvar](/customer-engagement/admin/audit-data-user-activity)|
|**Beskrivelse**|Skriv inn instruksjoner til brukeren om hva feltet er for. Disse beskrivelsene vises som verktøytips for brukeren i modelldrevne apper når de holder musen over etiketten for feltet.|
|**Vises i globalt filter i interaktiv opplevelse**|Mer informasjon: [Konfigurer instrumentbord for interaktiv opplevelse](/dynamics365/customer-engagement/customize/configure-interactive-experience-dashboards) |
|**Sorterbar på instrumentbordet for interaktiv opplevelse**|Mer informasjon: [Konfigurer instrumentbord for interaktiv opplevelse](/dynamics365/customer-engagement/customize/configure-interactive-experience-dashboards)|
|**Datatype**|Styrer hvordan verdiene lagres, og hvordan de er formatert i noen programmer. Når et felt er lagret, kan du ikke endre datatypen siden det kan påvirke dataene i enheten. Mer informasjon: [Feltdatatyper](#field-data-types).|
|**Felttype**|Om feltet er **Enkel**, **Beregnet** eller **Beregnet verdi**. Mer informasjon: [Felttype](#field-type).|
|**Format**|Hvordan feltet formateres. Formateringsalternativene som er tilgjengelige, avhenger av **datatypen**.|

Du kan angi flere alternativer, avhengig av **datatypen** som er valgt. Mer informasjon: [Feltdatatyper](#field-data-types).

## <a name="field-requirement-options"></a>Alternativer for feltkrav

Det er tre feltkravalternativer:
- **Valgfritt**: Oppføringen kan lagres selv om det ikke finnes data i dette feltet.
- **Anbefalt for selskapet**: Oppføringen kan lagres selv om det ikke finnes data i dette feltet. Det vises imidlertid et blått symbol ved siden av et felt for å angi at det er viktig.
- **Nødvendig for selskapet**: Oppføringen kan ikke lagres hvis det ikke er data i dette feltet.
> [!NOTE]
> Vær forsiktig når du gjør forretningsfelt nødvendige. Brukere vil motsette seg å bruke programmet hvis de ikke kan lagre oppføringer fordi de mangler den riktige informasjonen å angi inn et nødvendig felt. Brukere kan skrive angi feil data bare for å lagre oppføringen og fortsette arbeidet. Du kan bruke forretningsregler eller skjemaskript til å endre kravnivået når dataene i oppføringen endres når brukere arbeider med den. Mer informasjon: [Opprett forretningsregler og anbefalinger hvis du vil bruke logikk i et skjema](../model-driven-apps/create-business-rules-recommendations-apply-logic-form.md)

## <a name="field-data-types"></a>Feltdatatyper

Det finnes mange ulike typer felt, men du kan bare opprette noen av dem. Hvis du vil ha mer informasjon om alle typer felt, kan du se [Typer felt og feltdatatyper](types-of-fields.md).

Når du oppretter et felt, har **Datatype** følgende valg:

|Alternativ|Beskrivelse|
|--|--|
|**En enkelt linje med tekst**|Dette feltet kan ta opptil 4 000 teksttegn. Du kan angi en maksimumslengde som er mindre enn dette. Dette feltet har flere formateringsalternativer som vil endre presentasjonen av teksten.  Mer informasjon: [Alternativer for én linje med tekst](#single-line-of-text-options)|
|**Alternativsett**|Viser en liste over alternativer der ett kan velges. Mer informasjon: [Alternativer for alternativsettfelt](#option-set-field-options)|
|**Alternativsett med flere valg**|Viser en liste over alternativer der flere kan velges. Mer informasjon: [Alternativer for alternativsettfelt](#option-set-field-options)|
|**To alternativer**|Viser en liste over alternativer der ett av to kan velges.<br /><br /> Felt for to alternativer inneholder ikke formateringsalternativer på feltnivået. Når du legger til et i skjemaet, kan du imidlertid velge å vise dem som alternativknapper, en avmerkingsboks eller en valgliste.|
|**Bilde**|Viser ett enkelt bilde per oppføring i programmet. Hver enhet kan bare ha ett bildefelt. Bildefelt kalles alltid `EntityImage`.|
|**Heltall**|Dette feltet kan inneholde heltall med en verdi mellom -2 147 483 648 og 2 147 483 647.  Dette feltet inneholder alternativer som endres avhengig av hvordan feltet vises. Mer informasjon: [Heltallsalternativer](#whole-number-options)|
|**Flyttall**|I dette feltet kan det brukes en presisjon med opptil fem desimaler for verdier mellom -100 000 000 000 og 100 000 000 000. Du kan angi presisjonsnivået og minimums- og maksimumsverdier. Mer informasjon: [Bruke riktig type tall](types-of-fields.md#using-the-right-type-of-number)|
|**Desimaltall**|I dette feltet kan det brukes en presisjon med opptil ti desimaler for verdier mellom -100 000 000 000 og 100 000 000 000. Du kan angi presisjonsnivået og minimums- og maksimumsverdier. Mer informasjon: [Bruke riktig type tall](types-of-fields.md#using-the-right-type-of-number)|
|**Valuta**|Dette feltet kan inneholde pengeverdier mellom -922 337 203 685 477 og 922 337 203 685 477. Du kan angi et presisjonsnivå eller velge å basere presisjonen på en bestemt valuta eller en enkelt standardpresisjon som brukes av organisasjonen. Mer informasjon: [Bruke valutafelt](types-of-fields.md#using-currency-fields)|
|**Flere linjer med tekst**|Dette feltet kan ta opptil 1 048 576 teksttegn. Du kan angi en maksimumslengde som er mindre enn dette. Når du legger til dette feltet i et modelldrevet appskjema, kan du angi dimensjonene på feltet.|
|**Dato og klokkeslett**|Bruk disse feltene for å lagre tidsverdier. Du kan lagre verdier så tidlig som 1/1/1753 12:00. Mer informasjon: [Alternativer for dato og klokkeslett](#date-and-time-options)|
|**Oppslag**|Et felt som lar deg angi en referanse til en enkelt oppføring for en bestemt enhetstype. Noen systemoppslagsfelt kan ha en annen virkemåte. Mer informasjon: [Ulike typer oppslag](types-of-fields.md#different-types-of-lookups)|
|**Kunde**|Et oppslagsfelt som du kan bruke til å angi en kunde, som kan være en forretningsforbindelse eller kontakt.  Mer informasjon: [Ulike typer oppslag](types-of-fields.md#different-types-of-lookups)|

### <a name="single-line-of-text-options"></a>Alternativer for én linje med tekst

Datatypen for enkeltlinje med tekst har følgende formatalternativer:

|Format|Beskrivelse|
|--|--|
|**Tekst**|En tekstverdi som er ment å vises i en enkeltlinjetekstboks.|
|**Tekstområde**|En tekstverdi som er ment å vises i en tekstboks med flere linjer. Hvis du trenger mer enn 4 000 tegn, bruker du en datatype med **Flere linjer med tekst**.|
|**E-postadresse**|En tekstverdi validert som en e-postadresse og gjengitt som en mailto-kobling i feltet. |
|**URL-adresse**|En tekstverdi validert som en URL-adresse og gjengitt som en kobling for å åpne URL-adressen.|
|**Ticker-kode**|En tekstverdi for en ticker-kode som viser en kobling som åpnes for å vise et tilbud for aksje-ticker-koden. |
|**Telefon**|En tekstverdi validert som et telefonnummer gjengitt som kobling for å opprette en telefonsamtale ved bruk av Skype. |

Du kan også angi en **Maksimumslengde** slik at systemet ikke tillater tekstverdier som er lenger enn du angir.

### <a name="option-set-field-options"></a>Alternativer for felt for alternativsett

Felt som inneholder et sett med alternativer, kan inkludere sitt eget sett med *lokale* alternativer eller referere til et fellessett med *globale* alternativer som kan brukes av flere felt.

Et globalt alternativsett er verdifullt når du oppretter det samme settet med alternativer for flere felt. Med et globalt alternativsett trenger du bare å vedlikeholde settet med alternativer på ett sted. 

Når du velger datatypen **Alternativsett med flere valg** eller **Alternativsett**, gir utformingen for løsningsutforskeren alternativet for et lokalt alternativsett som standard.

![Konfigurere et lokalt alternativsett](media/local-option-set-solution-explorer.png)

#### <a name="configure-local-options"></a>Konfigurere lokale alternativer

[!INCLUDE [cc_configure-option-set-options-solution-explorer](../../includes/cc_configure-option-set-options-solution-explorer.md)]

#### <a name="use-existing-option-set"></a>Bruke eksisterende alternativsett

Hvis du velger **Bruk eksisterende alternativsett**, viser utformingen en liste over eksisterende *globale alternativsett* og inkluderer en **Rediger**- og **Ny**-knapp for å konfigurere de globale alternativer som dette feltet skal bruke.

![Konfigurere et globalt alternativsett](media/global-option-set-solution-explorer.png)

Du kan også konfigurere globale alternativsett separat. Mer informasjon: [Opprette og redigere globale alternativsett for Common Data Service (valglister)](create-edit-global-option-sets.md)

> [!NOTE]
> Hvis du angir hvert alternativsett som et globalt alternativsett, vil listen over globale alternativsett vokse og kan bli vanskelig å administrere. Hvis du vet at settet med alternativer bare skal brukes på ett sted, bruker du et lokalt alternativsett.


### <a name="whole-number-options"></a>Alternativer for heltall

Heltallsfelt har følgende formatvalg:

|Format|Beskrivelse|
|--|--|
|**Ingen**|En tallverdi som vises i en tekstboks.|
|**Varighet**|En tallverdi som vises som en rullegardinliste som inneholder tidsintervaller. En bruker kan velge en verdi fra listen eller skrive inn en heltallsverdi som angir antallet minutter.|
|**Tidssone**|En tallverdi som vises som en rullegardinliste som inneholder en liste med tidssoner.|
|**Språk**|Et tallverdi som vises som en rullegardinliste som inneholder en liste over språk som er aktivert for miljøet. Hvis ingen andre språk er aktivert, blir det eneste alternativet originalspråket. Verdien som er lagret, er ID for nasjonale innstillinger (LCID) for språket.|

Du kan også begrense største eller minste tillatte verdier.

### <a name="date-and-time-options"></a>Alternativer for dato og klokkeslett

Dato og klokkeslett-felt har følgende alternativer:

|Format |Beskrivelse|
|--|--|
|**Dato og klokkeslett**|En dato- og klokkeslettverdi..|
|**Bare dato**|En dato- og klokkeslettverdi som bare viser en dato. Tidsverdien lagres som 12:00 (00: 00:00) i systemet.|

Du kan også angi bestemt **funksjonalitet** for dato og klokkeslett-felt i **Avanserte alternativer**.

- **Brukerlokal** : Viser verdiene som er konvertert til den gjeldende brukerens lokale tidssone. Dette er standard for nye felt.
- **Bare dato**: Denne funksjonaliteten er tilgjengelig for **Bare dato**-typen. Viser verdier uten tidssonekonvertering. Bruk dette for data som fødselsdager og merkedager.
- **Tidssoneuavhengig**: Viser verdier uten tidssonekonvertering.

Mer informasjon: [Virkemåte og format for dato og klokkeslett-feltet](behavior-format-date-time-field.md)

## <a name="field-type"></a>Felttype

Du kan angi at det egendefinerte feltet **Felttype** skal være et **Enkelt**-, **Beregnet**- eller **Beregnet verdi**-felt. 

### <a name="simple"></a>Enkel

Enkel betyr at feltet ikke er et beregnet- eller beregnet verdi-felt.

### <a name="calculated"></a>Beregnet

Du kan angi en formel for å tilordne en verdi til feltet, med et beregnet felt. Disse datatypene kan angis til beregnede felt: **Valuta**, **Dato og klokkeslett**, **Desimaltall**, **Alternativsett med flere valg**, **Alternativsett**, **En enkelt linje med tekst**, **To alternativer** og **Heltall**.

Mer informasjon: [Definere beregnede felt for å automatisere manuelle beregninger](define-calculated-fields.md)

### <a name="rollup"></a>Beregnet verdi

Med et felt for beregnet verdi kan du angi mengdefunksjoner som skal kjøres med jevne mellomrom for å angi en tallverdi for feltet. Disse datatypene kan settes til beregnede felt: **Valuta**, **Dato og klokkeslett**, **Desimaltall** og **Heltall**.

Mer informasjon: [Definere felt for beregnet verdi som samler verdier](define-rollup-fields.md)

## <a name="save-new-field"></a>Lagre nytt felt

Når du har konfigurert feltet, kan du bruke én av tre kommandoer på kommandolinjen:

|Kommando|Beskrivelse|
|--|--|
|**Lagre**|Lagre feltdefinisjonen og la skjemavinduet være åpent.|
|**Lagre og lukk**|Lagre feltdefinisjonen og lukk vinduet.|
|**Lagre og ny(tt)**|Lagre feltdefinisjonen, og åpne et nytt skjema for å opprette en nytt felt.|


## <a name="edit-a-field"></a>Redigere et felt 

Når du [viser felt](#view-fields), klikker du på feltet du vil redigere. Noen standardfelt eller egendefinerte felt som er inkludert i en administrert løsning, lar deg kanskje ikke redigere dem.

> [!NOTE]
> Når du redigerer et skjema, for alle felt som allerede er lagt til i skjemaet, kan du dobbeltklikke feltet for å vise **Feltegenskaper**. Klikk **Rediger** i kategorien **Detaljer**. Mer informasjon: [Legge til et felt i et skjema](../model-driven-apps/add-field-form.md)

Når du har gjort endringer i et felt, må du publisere tilpassingene. 

- Hvis du vil publisere endringene for én enhet, velger du **Enheter** under **Komponenter**, og deretter velger du enheten du har gjort endringer i. Velg **Publiser** på **handlingsverktøylinjen**.  
  
- Hvis du vil publisere alle endringene du har gjort i flere enheter eller komponenter, velger du **Publiser alle tilpassinger** på **handlingsverktøylinjen**.  
  
> [!NOTE]
>  Installasjon av løsninger eller publisering av tilpassinger kan forstyrre den ordinære driften av systemet. Vi anbefaler at du planlegger publisering av en løsning når det i minst mulig grad vil forstyrre brukerne.  

### <a name="edit-multiple-fields"></a>Rediger flere felt

Hvis du vil redigere ett eller flere felt, merker du feltet eller feltene (Bruk SKIFT-tasten) du vil endre, og deretter velger du **Rediger** på **handlingsverktøylinjen**. 
  
Når du velger flere felt for redigering, vises dialogboksen **Rediger flere felt**. Du kan redigere **Feltkrav**, **Søkbare** og **Sporing av endringer**. 

## <a name="delete-a-field"></a>Slette et felt

Med sikkerhetsrollen Systemadministrator kan du slette eventuelle egendefinerte felt som ikke er en del av en administrert løsning. Når du sletter et felt, går eventuelle data som er lagret i feltet tapt. Den eneste metoden for å gjenopprette data fra et felt som ble slettet, er å gjenopprette databasen fra et punkt før feltet ble slettet.

> [!NOTE]
> Før du kan slette et egendefinert felt, må du fjerne alle avhengigheter som finnes i andre løsningskomponenter. 

1. Velg et egendefinert felt som kan slettes i listen, når du [viser felt](#view-fields), og klikk på ![Slett-kommandoen](../model-driven-apps/media/delete.gif)-knappen på kommandolinjen.
2. Velg **Slett** i dialogboksen **Bekreft sletting**.

> [!TIP]
> Du kan velge flere egendefinerte felt som skal slettes samtidig.

### <a name="check-field-dependencies"></a>Kontrollere feltavhengigheter 

Velg feltet i listen. På menyen **Flere handlinger** velger du **Vis avhengigheter**.

![Vis avhengigheter for feltet](media/check-field-dependencies.png)

Avhengigheter er relatert bruk av feltet som vil hindre at det blir slettet. Hvis feltet for eksempel brukes i et skjema eller en visning, må du først fjerne referanser til felt i disse løsningskomponentene.  
  
Hvis du sletter et oppslagsfelt, vil 1:N-enhetsrelasjonen for den automatisk bli slettet.  

## <a name="ime-mode"></a>IME-modus

Felt som gir direkte innskriving av tekst har en IME-modus. IME brukes for østasiatiske språk som japansk. IME lar brukere skrive inn de tusener av ulike tegnene som brukes i østasiatiske skriftspråk med et standard 101-tasters tastatur.


### <a name="see-also"></a>Se også  
[Opprette og redigere felt for Common Data Service](create-edit-fields.md)<br />
[Opprette og redigere felt for Common Data Service ved hjelp av PowerApps-portalen](create-edit-field-portal.md)<br />
[Typer felt og feltdatatyper](types-of-fields.md)<br />
[Definere beregnede felt for å automatisere manuelle beregninger](define-calculated-fields.md)<br />
[Definere felt for beregnet verdi som samler verdier](define-rollup-fields.md)<br />
[Virkemåte og format for Dato og klokkeslett-feltet](behavior-format-date-time-field.md)
