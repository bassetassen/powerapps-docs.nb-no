---
title: Opprette og redigere felt for Common Data Service ved hjelp av PowerApps-portalen | MicrosoftDocs
ms.custom: ''
ms.date: 08/13/2019
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
manager: kvivek
author: Mattp123
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="create-and-edit-fields-for-common-data-service-using-powerapps-portal"></a>Opprette og redigere felt for Common Data Service ved hjelp av PowerApps-portalen

[PowerApps-portalen](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) gir en enkel måte å opprette og redigere enhetsfelt på med Common Data Service.

Portalen gjør det mulig for konfigurasjon av de vanligste alternativene, men enkelte alternativer kan bare angis ved hjelp av løsningsutforskeren. <br />Mer informasjon: 
- [Opprette og rediger felt for Common Data Service](create-edit-fields.md)
- [Opprette og redigere felt for Common Data Service ved hjelp av løsningsutforskeren i PowerApps](create-edit-field-solution-explorer.md)

## <a name="view-fields"></a>Visningsfelt

1. I [PowerApps-portalen](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) velger du utformingsmodusen **Modelldrevet** eller **Lerret**.
2. Velg **Data** > **Enheter**, og velg enheten som har feltene du vil vise.
3. Med **Felt**-kategorien valgt kan du velge følgende visninger: 

 |Visning|Beskrivelse|
 |--|--|
 |**Alle**| Viser alle feltene for enheten|
 |**Egendefinert**|Viser bare egendefinerte felt for enheten|
 |**Standard**|Viser bare standardfeltene for enheten|
<!-- TODO: What is the actual difference between All and Default? -->

## <a name="create-a-field"></a>Opprette et felt

Når feltene vises, klikker du på **Legg til felt** på kommandolinjen, som vil vise **Feltegenskaper**-panelet.

![Feltegenskaper](media/field-properties.png)


Først er bare tre feltegenskaper tilgjengelige:

 |Egenskap|Beskrivelse|
 |--|--|
 |**Visningsnavn**|Teksten som skal vises for feltet i brukergrensesnittet.|
 |**Navn**|Det unike navnet i hele miljøet. Det genereres et navn for deg basert på visningsnavnet som du har angitt, men du kan redigere det før du lagrer. Når et felt er opprettet, kan ikke navnet endres siden den kan bli referert til i programmene eller koden. Navnet vil ha tilpassingsprefikset for **Standardutgiver for Common Data Service** lagt til foran.|
 |**Datatype**|Styrer hvordan verdiene lagres, og hvordan de er formatert i noen programmer. Når et felt lagres, kan du ikke endre datatypen med unntak av å konvertere tekstfelt til autonummereringsfelt.|

Du kan angi flere alternativer, avhengig av **datatypen** som er valgt.

## <a name="field-data-types"></a>Feltdatatyper

Det finnes mange ulike typer felt, men du kan bare opprette noen av dem. Hvis du vil ha mer informasjon om alle typer felt, kan du se [Typer felt og feltdatatyper](types-of-fields.md).

Når du oppretter et felt, har **Datatype** følgende valg:

### <a name="text"></a>Text 

Standardtekstfelt kan inneholde opptil 4 000 tegn. Standardalternativet [Maksimumslengde](#max-length) er satt til en lavere verdi som du kan tilpasse.

|Datatype|Beskrivelse|
|--|--|
|**Tekst**|En tekstverdi som er ment å vises i en enkeltlinjetekstboks.|
|**Tekstområde**|En tekstverdi som er ment å vises i en tekstboks med flere linjer. Hvis du trenger mer enn 4 000 tegn, bruker du en datatype med [tekst med flere linjer](#multi-line-field).|
|**E-postadresse**|En tekstverdi validert som en e-postadresse og gjengitt som en mailto-kobling i feltet. |
|**URL-adresse**|En tekstverdi validert som en URL-adresse og gjengitt som en kobling for å åpne URL-adressen.|
|**Ticker-kode**|En tekstverdi for en ticker-kode som viser en kobling som åpnes for å vise et tilbud for aksje-ticker-koden. |
|**Telefon**|En tekstverdi validert som et telefonnummer gjengitt som kobling for å opprette en telefonsamtale ved bruk av Skype. |
|**Autonummer**|En kombinasjon av tall og bokstaver som kan genereres, som automatisk genereres av serveren når oppføringen opprettes. Mer informasjon: [Autonummereringsfelt](autonumber-fields.md) |

#### <a name="max-length"></a>Maksimumslengde

Felt som lagrer tekst, har et absolutt maksimum avhengig av typen. **Maksimumslengde** angir en verdi under maksimum som er spesifikk for ditt miljø. Du kan øke maksimumslengden, men du bør ikke senke den hvis du har data i systemet som er større enn den lavere verdien.

### <a name="whole-number"></a>Heltall

Disse feltene lagrer data som tall, men inkluderer andre presentasjons- og valideringsalternativer.

|Datatype|Beskrivelse|
|--|--|
|**Heltall**|En tallverdi som vises i en tekstboks.|
|**Varighet**|En tallverdi som vises som en rullegardinliste som inneholder tidsintervaller. En bruker kan velge en verdi fra listen eller skrive inn en heltallsverdi som angir antallet minutter. Varigheten må angis i formatet: "x minutter", "x timer" eller "x dager". Timer og dager kan også angis ved hjelp av desimaler, for eksempel "x,x timer" eller "x,x dager". De angitte verdiene må kunne uttrykkes i minutter, verdier under minutt vil bli avrundet til nærmeste minutt.|
|**Tidssone**|En tallverdi som vises som en rullegardinliste som inneholder en liste med tidssoner.|
|**Språk**|Et tallverdi som vises som en rullegardinliste som inneholder en liste over språk som er aktivert for miljøet. Hvis ingen andre språk er aktivert, blir det eneste alternativet originalspråket. Verdien som er lagret, er ID for nasjonale innstillinger (LCID) for språket.|


### <a name="date-time"></a>Dato/klokkeslett

Bruk disse feltene for å lagre tidsverdier. Du kan lagre verdier så tidlig som 1/1/1753 12:00.

|Datatype|Beskrivelse|
|--|--|
|**Dato og klokkeslett**|En dato- og klokkeslettverdi..|
|**Bare dato**|En dato- og klokkeslettverdi som bare viser en dato. Tidsverdien lagres som 12:00 (00: 00:00) i systemet.|

Du kan også angi bestemt **funksjonalitet** for dato og klokkeslett-felt i **Avanserte alternativer**.

- **Brukerlokal** : Viser verdiene som er konvertert til den gjeldende brukerens lokale tidssone. Dette er standard for nye felt.
- **Bare dato**: Denne funksjonaliteten er tilgjengelig for **Bare dato**-typen. Viser verdier uten tidssonekonvertering. Bruk dette for data som fødselsdager og merkedager.
- **Tidssoneuavhengig**: Viser verdier uten tidssonekonvertering.

Mer informasjon: [Virkemåte og format for dato og klokkeslett-feltet](behavior-format-date-time-field.md)

### <a name="other-data-types"></a>Andre datatyper

|Datatype|Beskrivelse|
|--|--|
|**Valuta**|En pengeverdi for valutaer som er konfigurert for miljøet. Du kan angi et presisjonsnivå eller velge å basere presisjonen på en bestemt valuta eller en enkelt standardpresisjon som brukes av organisasjonen. Mer informasjon: [Bruke valutafelt](types-of-fields.md#using-currency-fields)|
|**Desimaltall**| En desimalverdi med opptil 10 poeng presisjon. Mer informasjon: [Bruke riktig type tall](types-of-fields.md#using-the-right-type-of-number)|
|**Flyttall**|Et flyttall med opptil 5 poeng presisjon. Mer informasjon: [Bruke riktig type tall](types-of-fields.md#using-the-right-type-of-number)|
|**Bilde**|Viser ett enkelt bilde per oppføring i programmet. Hver enhet kan bare ha ett bildefelt. **Navnet** du skriver inn når du oppretter et bildefelt, ignoreres. Bildefelt kalles alltid EntityImage.|
|**Alternativsett med flere valg**|Viser en liste over alternativer der flere kan velges.|
|<a name="multi-line-field"></a> **Tekst med flere linjer**|En tekstverdi som er ment å vises i en tekstboks med flere linjer. Begrenset til maksimalt 1 048 576 tegn. Du kan også angi en lavere [maksimumslengde](#max-length). |
|**Alternativsett**|Viser en liste over alternativer der bare ett kan velges.|
|**To alternativer**|Viser to alternativer der bare ett kan velges. Du velger etikettene som skal vises for hvert alternativ. Standardverdiene er **Ja** og **Nei**.|

## <a name="save-new-field"></a>Lagre nytt felt

Når du har angitt egenskapene **Visningsnavn**, **Navn** og **Datatype**, kan du klikke på **Ferdig** for å lukke **Feltegenskaper**-panelet. 

Du kan fortsette å redigere enheten og legge til flere felt eller gå tilbake og fortsette å redigere dette feltet. Feltene blir ikke opprettet før du klikker på **Lagre enhet** for å lagre alle endringene på enheten.

![Lagre enhet-knappen](media/save-entity-button.png)

Du kan også klikke på **Forkast** for å forkaste endringene du har gjort.
 
## <a name="edit-a-field"></a>Redigere et felt

Når du viser felt, velger du feltet du vil redigere. Du kan endre **Visningsnavn**, men du kan ikke endre **Navn** og **Datatype** hvis du har lagret endringer på enheten for å legge til feltet.

### <a name="general-properties"></a>Generelle egenskaper
Hvert felt har følgende egenskaper du kan endre:

|Egenskap|Beskrivelse|
|--|--|
|**Obligatorisk**|Når dette er valgt, kan ikke en oppføring lagres uten data i dette feltet.|
|**Søkbar**|Opphev dette for felt for enheten som du ikke bruker.  Når et felt er søkbart, vises det i **Avansert søk** og er tilgjengelig når du tilpasser visninger. Hvis du opphever dette, vil dette redusere antall alternativer som vises for brukere som bruker avansert søk.|
|**Beskrivelse**|Finnes i **Avanserte alternativer**. Skriv inn instruksjoner til brukeren om hva feltet er for. Disse beskrivelsene vises som verktøytips for brukeren i modelldrevne apper når de holder musen over etiketten for feltet.|

> [!NOTE]
> **Gjøre felt obligatoriske**: Vær forsiktig når du gjør felt obligatoriske. Brukere vil motsette seg å bruke programmet hvis de ikke kan lagre oppføringer fordi de mangler den riktige informasjonen å angi inn et nødvendig felt. Brukere kan skrive angi feil data bare for å lagre oppføringen og fortsette arbeidet.
>
>**Angi krav dynamisk**: I modelldrevne apper kan du bruke forretningsregler eller skjemaskript til å endre kravnivået når dataene i oppføringen endres når brukere arbeider med den. Mer informasjon: [Opprett forretningsregler og anbefalinger hvis du vil bruke logikk i et skjema](../model-driven-apps/create-business-rules-recommendations-apply-logic-form.md)
>
>**Tilgjengelighet for avansert søk**: Avansert søk er for øyeblikket bare tilgjengelig for modelldrevne apper som bruker webklienten. Avansert søk er ikke tilgjengelig for øyeblikket i Enhetlig grensesnitt-klienter.

## <a name="calculated-or-rollup"></a>Beregnet eller beregnet verdi

Du kan angi at et egendefinert felt skal være et **Beregnet**- eller **Beregnet verdi**-felt. Felt som ikke beregnes eller felt for beregnet verdi kalles noen ganger *enkle* felt.

### <a name="calculated"></a>Beregnet

Du kan angi en formel for å tilordne en verdi til feltet, med et beregnet felt. Disse datatypene kan settes til beregnede felt: **Valuta**, **Dato og klokkeslett**, **Bare dato**, **Desimaltall**, **Varighet**, **E-post**, **Språk**, **Alternativsett med flere valg**, **Alternativsett**, **Tekst**, **Tekstområde**, **Ticker-kode**, **Tidssone**, **To alternativer**, **URL-adresse** og **Heltall**.

Mer informasjon: [Definere beregnede felt for å automatisere manuelle beregninger](define-calculated-fields.md)

### <a name="rollup"></a>Beregnet verdi

Med et felt for beregnet verdi kan du angi mengdefunksjoner som skal kjøres med jevne mellomrom for å angi en tallverdi for feltet. Disse datatypene kan settes til beregnede felt: **Valuta**, **Dato og klokkeslett**, **Bare dato**, **Desimaltall**, **Varighet**, **Språk**, **Tidssone** og **Heltall**.

Mer informasjon: [Definere felt for beregnet verdi som samler verdier](define-rollup-fields.md)

## <a name="number-field-options"></a>Alternativer for tallfelt

Hver type tallfelt har absolutte minimums- og maksimumsverdier. Du kan angi riktig **Minimumsverdi** og **Maksimumsverdi** innenfor disse absolutte verdiene. Gjør dette hvis du vil at Common Data Service skal validere verdiene for dataene du vil lagre i feltet.

For **Flyttall**- og **Desimaltall**-datatypene kan du angi et tall for **Desimalplasser**.


## <a name="option-set-field-options"></a>Alternativer for felt for alternativsett

Felt som inneholder et sett med alternativer, kan inkludere sitt eget sett med *lokale* alternativer eller referere til et fellessett med *globale* alternativer som kan brukes av flere felt.

Et globalt alternativsett er verdifullt når du oppretter det samme settet med alternativer for flere felt. Med et globalt alternativsett trenger du bare å vedlikeholde settet med alternativer på ett sted. 

Når du velger datatypen **Alternativsett med flere valg** eller **Alternativsett**, vil utformingen vise et sett med tilgjengelige globale alternativsett som du kan velge fra, og angi alternativet for å opprette et **Nytt alternativsett**.

![Velge type alternativsett](media/option-set-options.png)

Hvis du velger **Nytt alternativsett**, er standardfunksjonaliteten å opprette et nytt globalt alternativsett.

> [!NOTE]
> Når du redigerer alternativer for et nytt globalt alternativsett, er verdiene **Visningsnavn** og **Navn** for det globale alternativsettet i stedet for feltet. Standardverdiene samsvarer med feltverdiene, men du kan redigere dem når du redigerer det globale alternativsettet til å være forskjellige fra feltet du oppretter nå.

Hvis du vil opprette et lokalt alternativsett, må du klikke på **Vis mer** og velge **Lokalt alternativsett**.

![Lokalt alternativsett](media/local-option-set.png)

> [!NOTE]
> Hvis du angir hvert alternativsett som et globalt alternativsett, vil listen over globale alternativsett vokse og kan bli vanskelig å administrere. Hvis du vet at settet med alternativer bare skal brukes på ett sted, bruker du et lokalt alternativsett.

[!INCLUDE [cc_remove-option-warning](../../includes/cc_remove-option-warning.md)]

## <a name="delete-a-field"></a>Slette et felt

Med sikkerhetsrollen Systemadministrator kan du slette eventuelle egendefinerte felt som ikke er en del av en administrert løsning. Når du sletter et felt, går eventuelle data som er lagret i feltet tapt. Den eneste metoden for å gjenopprette data fra et felt som ble slettet, er å gjenopprette databasen fra et punkt før feltet ble slettet.

> [!NOTE]
> Før du kan slette et egendefinert felt, må du fjerne alle avhengigheter som finnes i andre løsningskomponenter. 

Hvis du velger et egendefinert felt som kan slettes i listen, når du [viser felt](#view-fields), vises **Slett felt**-kommandoen og aktiveres.

![Slette et felt ved hjelp av portalen](media/delete-field-portal.png)

Bruk **Slett felt**-kommandoen for å slette feltet. Når du har slettet feltet, må du lagre endringene på enheten.

![Lagre enhet når du har slettet felt](media/delete-field-portal-save-entity.png)

> [!NOTE]
> Hvis du får en feil relatert til avhengigheter, må du bruke Løsningsutforsker for å registrere avhengigheter. Mer informasjon: [Kontrollere feltavhengigheter](create-edit-field-solution-explorer.md#check-field-dependencies)

## <a name="ime-mode"></a>IME-modus

Felt som gir direkte innskriving av tekst har en IME-modus. IME brukes for østasiatiske språk som japansk. IME lar brukere skrive inn de tusener av ulike tegnene som brukes i østasiatiske skriftspråk med et standard 101-tasters tastatur.



### <a name="see-also"></a>Se også  
[Opprette og rediger felt for Common Data Service](create-edit-fields.md)<br />
[Opprette og redigere felt for Common Data Service ved hjelp av løsningsutforskeren i PowerApps](create-edit-field-solution-explorer.md)<br />
[Typer felt og feltdatatyper](types-of-fields.md)<br />
[Definere beregnede felt for å automatisere manuelle beregninger](define-calculated-fields.md)<br />
[Definere felt for beregnet verdi som samler verdier](define-rollup-fields.md)<br />
[Virkemåte og format for Dato og klokkeslett-feltet](behavior-format-date-time-field.md)
