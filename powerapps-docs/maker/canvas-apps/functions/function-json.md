---
title: JSON-funksjonen | Microsoft Docs
description: Referanseinformasjon, inkludert syntaks, for JSON-funksjonen i PowerApps
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 05/02/2019
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 74e10a5b073e16ba9f35139441c94e9911446a0f
ms.sourcegitcommit: 2084789802fc5134dbeb888e759cced46019a017
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/06/2019
ms.locfileid: "66736403"
---
# <a name="json-function-in-powerapps"></a>JSON-funksjonen i PowerApps

Genererer en JSON-tekststreng for en tabell, en post eller en verdi.

## <a name="description"></a>Beskrivelse

Den **JSON** -funksjonen returnerer JavaScript Object Notation (JSON)-representasjon av en datastruktur som tekst, slik at den er egnet for å lagre eller overføring over et nettverk. [ECMA-404](http://www.ecma-international.org/publications/files/ECMA-ST/ECMA-404.pdf) og [IETF RFC 8259](https://tools.ietf.org/html/rfc8259) beskrive format, som brukes mye av JavaScript og andre programmeringsspråk.

Lerret apper støtte den [datatyper](data-types.md) som denne tabellen viser detaljer om deres tekstrepresentasjonen:

| Datatype | Beskrivelse | Resultatet eksempel |
|-----------|-------------|---------|
| **Boolsk** | *SANN* eller *USANN*. | `true` |
| **Farge** | Streng som inneholder den 8-sifrede heksadesimale representasjonen for fargen. Denne representasjon tar formatet #*rrggbbaa*, der *rr* er den røde komponenten, *gg* er grønn, *bb* er blå og *aa* er alfa kanalen. For den alfa kanalen, **00** er fullstendig gjennomsiktig, og **ff** er helt ugjennomsiktig. Du kan sende strengen som skal den [ **ColorValue** ](function-colors.md) funksjonen.  | `"#102030ff"` |
| **Valuta** | Nummeret som bruker riktig desimalskilletegnet for brukerens språk. Vitenskapelig notasjon brukes hvis nødvendig. | `1.345` |
| **Dato** | Streng som inneholder datoen i ISO 8601 **åååå-mm-dd** format. | `"2019-03-31"` |
| **Dato og klokkeslett** | Streng som inneholder en ISO 8601 dato/klokkeslett. Dato/klokkeslett verdier er i UTC, som angir sluttdato» Z».  | `"2019-03-31T22:32:06.822Z"`  |
| **GUID** | Streng som inneholder GUID-verdi. Bokstavene er små bokstaver. | `"751b58ac-380e-4a04-a925-9f375995cc40"`
| **Media-bilde** | Hvis **IncludeBinaryData** er angitt, mediefiler er kodet i en streng. Web-referanser som bruker http: eller https: URL-skjemaet ikke er endret. Referanser til binære data i minnet er kodet med den ["data:*mimetype*; base64,..."](https://en.wikipedia.org/wiki/Data_URI_scheme) format. Data i minnet, inkluderer bilder som brukere registrere ved hjelp av den [ **kamera** ](../controls/control-camera.md) kontrollen og alle andre referanser med appres: og blob: URL-valgene.| `"data:image/jpeg;base64,/9j/4AA..."` |
| **Tall** | Nummeret som bruker riktig desimalskilletegnet for brukerens språk. Vitenskapelig notasjon brukes hvis nødvendig. | `1.345` |
| **Alternativet&nbsp;angitt** | Numeriske verdien for alternativet angitt, ikke etiketten som brukes for visning. Den numeriske verdien brukes fordi det er språk uavhengig.  | `1001` |
| **Tid** | Streng som inneholder en ISO 8601 *hh:mm:ss.fff* format.  | `"23:12:49.000"` |
| **Post** | Kommadelt liste over, mellom **{** og **}** , felt og verdiene deres. Notation ligner som for postene i lerret-apper, men navnet er alltid mellom doble anførselstegn. Dette formatet støtter ikke poster som er basert på mange-til-én-relasjoner.  | `{ "First Name": "Fred", "Age": 21 }` |
| **Tabell** | Kommadelt liste over, mellom **[** og **]** , med poster. Dette formatet støtter ikke tabeller som er basert på én-til-mange-relasjoner.  | `[ { "First Name": "Fred", "Age": 21 }, { "First Name": "Jean", "Age": 20 } ]` |
| **To&nbsp;alternativet** | Boolsk verdi for alternativet to *SANN* eller *USANN*, ikke etiketten som brukes for visning. Den boolske verdien brukes fordi det er språk uavhengig. | `false` |
| **Hyperkobling, tekst** | Streng mellom doble anførselstegn. Funksjonen escapes innebygde doble anførselstegn med en omvendt skråstrek, erstatter newlines med «\n», og gjør andre standard JavaScript-erstatninger. | `"This is a string."` |

Angi den valgfrie *Format* argumentet til å kontrollere hvordan lesbare resultatet er og hvordan støttes ikke og binære datatyper håndteres. Utdataene er så kompakt som mulig uten unødvendige mellomrom eller newlines som standard, og som ikke støttes datatyper og binære data er ikke tillatt. Du kan kombinere flere formater Hvis du angir den **&** operatoren.

| JSONFormat enum | Beskrivelse |
|-----------------|-------------|
| **CD** | Standard.  Utdataene er så kompakt som mulig uten ekstra mellomrom eller newlines. |
| **IndentFour** | Utdataene inneholder en ny linje for hver kolonne og nestingsnivå for å forbedre lesbarheten, og bruker fire mellomrom for hvert Innrykkingsnivå. |
| **IncludeBinaryData** | Resultatet inneholder bilde, video og lyd-videoklipp kolonner. Dette formatet kan dramatisk øke størrelsen på den resultatet og redusere ytelsen til appen. |
| **IgnoreBinaryData** | Resultatet inneholder ikke bilde, video eller lyd-videoklipp kolonner. Hvis du ingen angir **IncludeBinaryData** eller **IgnoreBinaryData**, funksjonen produserer en feil hvis det oppstår binære data. |
| **IgnoreUnsupportedTypes** | Datatyper som ikke støttes, er tillatt, men resultatet kan ikke omfatte dem. Som standard datatyper som ikke støttes, får du en feilmelding. |

Bruk den [ **ShowColumns** og **DropColumns** ](function-table-shaping.md) funksjonene til å kontrollere hvilke data som omfatter resultatet og fjerne datatyper som ikke støttes.

Fordi **JSON** kan være både minne og Beregn intensive, du kan bruke denne funksjonen bare i [virkemåte funksjoner](../working-with-formulas-in-depth.md). Du kan samle inn resultatet fra **JSON** i en [variabelen](../working-with-variables.md), som du deretter kan bruke i dataflyten.

Hvis en kolonne inneholder både et visningsnavn og et logisk navn, vil resultatet inneholder det logiske navnet. Visningsnavn gjenspeiler språket for den appbrukeren og kan derfor, passer ikke for dataoverføring til en common service.

## <a name="syntax"></a>Syntaks

**JSON**( *DataStructure* [, *Format* ])

* *DataStructure* – obligatorisk. Datastrukturen til å konvertere til JSON.  Tabeller, poster, og primitive verdier støttes, tilfeldige nestet.
* *Format* – valgfritt.  **JSONFormat** opplistingsverdi. Standardverdien er **kompakt**, som ikke legger til newlines eller mellomrom og blokkerer binære data og kolonner som ikke støttes.

## <a name="examples"></a>Eksempler

### <a name="hierarchical-data"></a>Hierarkiske data

1. Sett inn en [ **knappen** ](../controls/control-button.md) kontroll, og angi dens **OnSelect** egenskapen til denne formelen.

    ```powerapps-dot
    ClearCollect( CityPopulations,
        { City: "London",    Country: "United Kingdom", Population: 8615000 },
        { City: "Berlin",    Country: "Germany",        Population: 3562000 },
        { City: "Madrid",    Country: "Spain",          Population: 3165000 },
        { City: "Hamburg",   Country: "Germany",        Population: 1760000 },
        { City: "Barcelona", Country: "Spain",          Population: 1602000 },
        { City: "Munich",    Country: "Germany",        Population: 1494000 }
    );
    ClearCollect( CitiesByCountry, GroupBy( CityPopulations, "Country", "Cities" ) )
    ```

1. Velg knappen mens du holder nede Alt-tasten.

    Den **CitiesByCountry** samlingen er opprettet med denne datastruktur, som du kan vise ved å velge **samlinger** på den **filen** -menyen, og deretter velge navnet på den samling.

    > [!div class="mx-imgBorder"]
    > ![CitiesByCountry samling](media/function-json/cities-grouped.png)

    Du kan også vise denne samlingen ved å velge **filen** > **appinnstillinger** > **avanserte innstillinger**  >   **Aktiver formellinjen resultatvisningen**, å velge navnet på samlingen i formellinjen, og deretter velge pil ned ved siden av navnet på samlingen under formellinjen.

    > [!div class="mx-imgBorder"]
    > ![Samlingen i resultatvisningen på formellinjen](media/function-json/cities-grouped-resultview.png)

1. Sett inn en annen knapp, og angi dens **OnSelect** egenskapen til denne formelen:

    ```powerapps-dot
    Set( CitiesByCountryJSON, JSON( CitiesByCountry ) )
    ```

    Denne formelen angir den globale variabelen **CitiesByCountryJSON** til JSON-representasjon for **CitiesByCountry**.

1. Velg knappen mens du holder nede Alt-tasten.

1. Sett inn en [ **etikett** ](../controls/control-text-box.md) kontroll, og angi dens **tekst** egenskapen til denne variabelen.

    ```powerapps-dot
    CitiesByCountryJSON
    ```

    Etiketten viser dette resultatet, på en enkelt linje uten mellomrom, egnet for overføring over et nettverk:

    ```json
    [{"Cities":[{"City":"London","Population":8615000}],"Country":"United Kingdom"},{"Cities":[{"City":"Berlin","Population":3562000},{"City":"Hamburg","Population":1760000},{"City":"Munich","Population":1494000}],"Country":"Germany"},{"Cities":[{"City":"Madrid","Population":3165000},{"City":"Barcelona","Population":1602000}],"Country":"Spain"}]
    ```

1. Endre formelen for den andre knappen for å gjøre det lettere å lese utdataene.

    ```powerapps-dot
    Set( CitiesByCountryJSON, JSON(CitiesByCountry, JSONFormat.IndentFour ))
    ```

1. Velg den andre knappen mens du holder nede Alt-tasten.

    Etiketten viser mer lesbare resultatet.

    ```json
    [
        {
            "Cities": [
                {
                    "City": "London",
                    "Population": 8615000
                }
            ],
            "Country": "United Kingdom"
        },
        {
            "Cities": [
                {
                    "City": "Berlin",
                    "Population": 3562000
                },
                {
                    "City": "Hamburg",
                    "Population": 1760000
                },
                {
                    "City": "Munich",
                    "Population": 1494000
                }
            ],
            "Country": "Germany"
        },
        {
            "Cities": [
                {
                    "City": "Madrid",
                    "Population": 3165000
                },
                {
                    "City": "Barcelona",
                    "Population": 1602000
                }
            ],
            "Country": "Spain"
        }
    ]
    ```

### <a name="images-and-media-in-base64"></a>Bilder og medier i base64

1. Legg til en [ **bilde** ](../controls/control-image.md) kontroll.

    Denne kontrollen bringer **SampleImage** med den.

1. Legg til en [ **knappen** ](../controls/control-button.md) kontroll, og angi dens **OnSelect** egenskapen til denne formelen.

    ```powerapps-dot
    Set( ImageJSON, JSON( SampleImage, JSONFormat.IncludeBinaryData ) )
    ```

1. Velg knappen mens du holder nede Alt-tasten.

1. Legg til en etikett, og angi dens **tekst** egenskapen til denne variabelen.

    ```powerapps-dot
    ImageJSON
    ```

1. Endre størrelsen på kontrollen, og Reduser skriftstørrelsen etter behov for å vise de fleste av resultatet.

    Etiketten viser tekststrengen som den **JSON** funksjonen som er registrert.

    ```json
    "data:image/svg+xml;base64,PD94bWwgdmVyc2lvbj0iMS4wIiBlbmNvZGluZz0idXRmLTgiPz4NCjxzdmcgdmVyc2lvbj0iMS4xIg0KCSB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHhtbG5zOnhsaW5rPSJodHRwOi8vd3d3LnczLm9yZy8xOTk5L3hsaW5rIiB4bWxuczphPSJodHRwOi8vbnMuYWRvYmUuY29tL0Fkb2JlU1ZHVmlld2VyRXh0ZW5zaW9ucy8zLjAvIg0KCSB4PSIwcHgiIHk9IjBweCIgd2lkdGg9IjI3MHB4IiBoZWlnaHQ9IjI3MHB4IiBlbmFibGUtYmFja2dyb3VuZD0ibmV3IDAgMCAyNzAgMjcwIiB4bWw6c3BhY2U9InByZXNlcnZlIj4NCgk8ZyBjbGFzcz0ic3QwIj4NCgkJPHJlY3QgeT0iMC43IiBmaWxsPSIjRTlFOUU5IiB3aWR0aD0iMjY5IiBoZWlnaHQ9IjI2OS4zIi8+DQoJCTxwb2x5Z29uIGZpbGw9IiNDQkNCQ0EiIHBvaW50cz0iMjc3LjksMTg3LjEgMjQ1LDE0My40IDE4OC42LDIwMi44IDc1LDgwLjUgLTQuMSwxNjUuMyAtNC4xLDI3MiAyNzcuOSwyNzIiLz4NCgkJPGVsbGlwc2UgZmlsbD0iI0NCQ0JDQSIgY3g9IjIwMi40IiBjeT0iODQuMSIgcng9IjI0LjQiIHJ5PSIyNC4zIi8+DQoJPC9nPg0KPC9zdmc+"
    ```
