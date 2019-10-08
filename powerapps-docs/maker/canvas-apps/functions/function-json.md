---
title: JSON-funksjon | Microsoft Docs
description: Referanse informasjon, inkludert syntaks, for JSON-funksjonen i PowerApps
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 05/02/2019
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: ba852093da05c3fa69cc47b219a0bef65908c170
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/07/2019
ms.locfileid: "71992636"
ms.PowerAppsDecimalTransform: true
---
# <a name="json-function-in-powerapps"></a>JSON-funksjonen i PowerApps

Genererer en JSON-tekststreng for en tabell, en post eller en verdi.

## <a name="description"></a>Beskrivelse

**JSON** -funksjonen returnerer JavaScript Object NOTATION (JSON) for en data struktur som tekst, slik at den passer for lagring eller overføring over et nettverk. [ECMA-404](http://www.ecma-international.org/publications/files/ECMA-ST/ECMA-404.pdf) og [IETF RFC 8259](https://tools.ietf.org/html/rfc8259) beskriver formatet, som brukes mye av JavaScript og andre programmerings språk.

Lerret apper støtter [data typene](data-types.md) som denne tabellen viser med detaljer om teksten som vises:

| Datatype | Beskrivelse | Resultat eksempel |
|-----------|-------------|---------|
| **Verdien** | *sann* eller *Usann*. | `true` |
| **Farge** | Streng som inneholder den 8-sifrede heksadesimale representasjonen for fargen. Denne representasjonen tar formatet #*rrggbbaa*, der *RR* er den røde komponenten, *GG* er grønn, *bb* er blå, og *AA* er alfa kanalen. For alfa kanalen er **00** fullstendig gjennomsiktig, og **FF** er helt ugjennomsiktig. Du kan sende strengen til [**ColorValue**](function-colors.md) -funksjonen.  | `"#102030ff"` |
| **Valuta** | Tall som bruker riktig desimal skille tegn for brukerens språk. Vitenskapelig notasjon brukes hvis det er nødvendig. | `1,345` |
| **Aktivabokføringsdato** | Streng som inneholder datoen i ISO 8601 **yyyy-mm-dd-** format. | `"2019-03-31"` |
| **DateTime** | Streng som inneholder en ISO 8601-dato/klokkeslett. Dato/klokkeslett-verdiene er i UTC, da avsluttende Z indikerer.  | `"2019-03-31T22:32:06.822Z"`  |
| **OBJEKT** | Streng som inneholder GUID-verdien. Små bokstaver. | `"751b58ac-380e-4a04-a925-9f375995cc40"`
| **Bilde, Media** | Hvis **IncludeBinaryData** er angitt, kodes medie filer i en streng. Nett referanser som bruker http: eller https: URL-skjemaet er ikke endret. Referanser til binære data i minnet kodes med formatet ["data:*Mimetype*; Base64,..."](https://en.wikipedia.org/wiki/Data_URI_scheme) . Data i minnet inkluderer bilder som brukere registrerer ved hjelp av [**kamera**](../controls/control-camera.md) -kontrollen og andre referanser med appres: og blob: Nett adresse skjemaer.| `"data:image/jpeg;base64,/9j/4AA..."` |
| **Rekke** | Tall som bruker riktig desimal skille tegn for brukerens språk. Vitenskapelig notasjon brukes hvis det er nødvendig. | `1,345` |
| **Alternativ @ no__t-1set** | Numerisk verdi for alternativ settet, ikke etiketten som brukes til visning. Den numeriske verdien brukes fordi det er språk uavhengig.  | `1001` |
| **Tid** | Streng som inneholder et ISO 8601 *TT: mm: ss. FFF* -format.  | `"23:12:49.000"` |
| **Registrerer** | Kommadelt liste, mellom **{** og **}** , av felt og verdiene. Denne notasjonen ser ut som om det er poster i lerret apps, men navnet er alltid mellom doble anførsels tegn. Dette formatet støtter ikke poster som er basert på mange-til-én-relasjoner.  | `{ "First Name": "Fred"; "Age": 21 }` |
| **Tegn** | Kommadelt liste, mellom **[** og **]** , for poster. Dette formatet støtter ikke tabeller som er basert på én-til-mange-relasjoner.  | `[ { "First Name": "Fred"; "Age": 21 }; { "First Name": "Jean"; "Age": 20 } ]` |
| **To @ no__t-1option** | Boolsk verdi for det to alternativet, *sann* eller *Usann*, ikke etiketten som brukes til visning. Den boolske verdien brukes fordi den er språk uavhengig. | `false` |
| **Hyperkobling, tekst** | Streng mellom doble anførsels tegn. Funksjonen Escape-er innebygde doble anførsels tegn med en omvendt skrå strek, erstatter linje SKIFT med «\n» og gjør andre standard JavaScript-erstatninger. | `"This is a string."` |

Angi valg fritt *Format* -argumentet for å kontrollere hvor leselig resultatet er, og hvordan data typer som støttes og binære, behandles. Utdataene er som standard komprimert som mulig uten unødvendige mellomrom eller linje SKIFT, og data typer som ikke støttes, og binære data er ikke tillatt. Du kan kombinere flere formater hvis du angir **&-** operatoren.

| JSONFormat-opplisting | Beskrivelse |
|-----------------|-------------|
| **Komprimerte** | Standard.  Utdataene er så kompakt som mulig uten ekstra mellomrom eller ny linje. |
| **IndentFour** | For å forbedre lesbarheten, inneholder utdataene en ny linje for hvert kolonne-og nestet nivå og bruker fire mellomrom for hvert inn rykks nivå. |
| **IncludeBinaryData** | Resultatet inkluderer kolonner for bilde, video og lyd klipp. Dette formatet kan øke resultat størrelsen dramatisk og redusere appens ytelse. |
| **IgnoreBinaryData** | Resultatet inkluderer ikke kolonner for bilde, video eller lyd. Hvis du angir verken **IncludeBinaryData** eller **IgnoreBinaryData**, gir funksjonen en feil melding hvis det oppstår binære data. |
| **IgnoreUnsupportedTypes** | Data typer som ikke støttes, er tillatt, men resultatet vil ikke inkludere dem. Som standard gir data typer som ikke støttes, en feil. |

Bruk [ **ShowColumns** -og **DropColumns** ](function-table-shaping.md) -funksjonene til å kontrollere hvilke data resultatet inkluderer, og til å fjerne data typer som ikke støttes.

Ettersom **JSON** kan være både minne og data behandlings intensivt, kan du bare bruke denne funksjonen i [virke måte funksjoner](../working-with-formulas-in-depth.md). Du kan hente resultatet fra **JSON** til en [variabel](../working-with-variables.md), som du deretter kan bruke i data flyten.

Hvis en kolonne har både et visnings navn og et logisk navn, inneholder resultatet det logiske navnet. Visnings navn gjenspeiler språket til appens bruker, og er derfor ikke upassende for data overføring til en felles tjeneste.

## <a name="syntax"></a>Syntaks

**JSON**( *DataStructure* [; *Format* ])

* *DataStructure* – obligatorisk. Data strukturen som skal konverteres til JSON.  Tabeller, poster og primitive verdier støttes, tilfeldig nestet.
* *Format* -valg fritt.  **JSONFormat** -nummererings verdi. Standard verdien er **kompakt**, som ikke legger til linje SKIFT eller mellomrom, og blokkerer binære data og kolonner som ikke støttes.

## <a name="examples"></a>Eksempler

### <a name="hierarchical-data"></a>Hierarkiske data

1. Sett inn en [**knapp**](../controls/control-button.md) -kontroll, og angi **OnSelect** -egenskapen til denne formelen.

    ```powerapps-comma
    ClearCollect( CityPopulations;
        { City: "London";    Country: "United Kingdom"; Population: 8615000 };
        { City: "Berlin";    Country: "Germany";        Population: 3562000 };
        { City: "Madrid";    Country: "Spain";          Population: 3165000 };
        { City: "Hamburg";   Country: "Germany";        Population: 1760000 };
        { City: "Barcelona"; Country: "Spain";          Population: 1602000 };
        { City: "Munich";    Country: "Germany";        Population: 1494000 }
    );;
    ClearCollect( CitiesByCountry; GroupBy( CityPopulations; "Country"; "Cities" ) )
    ```

1. Velg knappen mens du holder nede Alt-tasten.

    **CitiesByCountry** -samlingen opprettes med denne data strukturen, som du kan vise ved å velge **samlinger** på **fil** -menyen, og deretter velge navnet på samlingen.

    > [!div class="mx-imgBorder"]
    > ![CitiesByCountry samling @ no__t-1

    Du kan også vise denne samlingen ved å velge **fil** > -**App-innstillinger** > **Avanserte innstillinger** > **Aktiver formel linje resultat visning**, velge navnet på samlingen i formel linjen og deretter velge pil ned ved siden av navnet på samlingen under formel linjen.

    > [!div class="mx-imgBorder"]
    > @no__t – 0Collection i resultat visningen for formel linjen @ no__t-1

1. Sett inn en annen knapp, og angi **OnSelect** -egenskapen til denne formelen:

    ```powerapps-comma
    Set( CitiesByCountryJSON; JSON( CitiesByCountry ) )
    ```

    Denne formelen angir den globale variabelen **CitiesByCountryJSON** til JSON-representasjonen for **CitiesByCountry**.

1. Velg knappen mens du holder nede Alt-tasten.

1. Sett inn en [**etikett**](../controls/control-text-box.md) -kontroll, og angi **tekst** -egenskapen til denne variabelen.

    ```powerapps-comma
    CitiesByCountryJSON
    ```

    Etiketten viser dette resultatet, alt på én linje uten mellomrom, som passer for overføring over et nettverk:

    ```json
    [{"Cities":[{"City":"London","Population":8615000}],"Country":"United Kingdom"},{"Cities":[{"City":"Berlin","Population":3562000},{"City":"Hamburg","Population":1760000},{"City":"Munich","Population":1494000}],"Country":"Germany"},{"Cities":[{"City":"Madrid","Population":3165000},{"City":"Barcelona","Population":1602000}],"Country":"Spain"}]
    ```

1. Endre formelen for den andre knappen for å gjøre utdataene enklere å lese.

    ```powerapps-comma
    Set( CitiesByCountryJSON; JSON(CitiesByCountry; JSONFormat.IndentFour ))
    ```

1. Velg den andre knappen mens du holder nede Alt-tasten.

    Etiketten viser det mer leselige resultatet.

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

1. Legg til en [**bilde**](../controls/control-image.md) -kontroll.

    Denne kontrollen bringer **SampleImage** sammen med den.

1. Legg til en [**knapp**](../controls/control-button.md) -kontroll, og angi **OnSelect** -egenskapen til denne formelen.

    ```powerapps-comma
    Set( ImageJSON; JSON( SampleImage; JSONFormat.IncludeBinaryData ) )
    ```

1. Velg knappen mens du holder nede Alt-tasten.

1. Legg til en etikett, og angi **tekst** -egenskapen til denne variabelen.

    ```powerapps-comma
    ImageJSON
    ```

1. Endre størrelsen på kontrollen og Reduser skrift størrelsen etter behov for å vise meste parten av resultatet.

    Etiketten viser tekst strengen som **JSON** -funksjonen har registrert.

    ```json
    "data:image/svg+xml;base64,PD94bWwgdmVyc2lvbj0iMS4wIiBlbmNvZGluZz0idXRmLTgiPz4NCjxzdmcgdmVyc2lvbj0iMS4xIg0KCSB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHhtbG5zOnhsaW5rPSJodHRwOi8vd3d3LnczLm9yZy8xOTk5L3hsaW5rIiB4bWxuczphPSJodHRwOi8vbnMuYWRvYmUuY29tL0Fkb2JlU1ZHVmlld2VyRXh0ZW5zaW9ucy8zLjAvIg0KCSB4PSIwcHgiIHk9IjBweCIgd2lkdGg9IjI3MHB4IiBoZWlnaHQ9IjI3MHB4IiBlbmFibGUtYmFja2dyb3VuZD0ibmV3IDAgMCAyNzAgMjcwIiB4bWw6c3BhY2U9InByZXNlcnZlIj4NCgk8ZyBjbGFzcz0ic3QwIj4NCgkJPHJlY3QgeT0iMC43IiBmaWxsPSIjRTlFOUU5IiB3aWR0aD0iMjY5IiBoZWlnaHQ9IjI2OS4zIi8+DQoJCTxwb2x5Z29uIGZpbGw9IiNDQkNCQ0EiIHBvaW50cz0iMjc3LjksMTg3LjEgMjQ1LDE0My40IDE4OC42LDIwMi44IDc1LDgwLjUgLTQuMSwxNjUuMyAtNC4xLDI3MiAyNzcuOSwyNzIiLz4NCgkJPGVsbGlwc2UgZmlsbD0iI0NCQ0JDQSIgY3g9IjIwMi40IiBjeT0iODQuMSIgcng9IjI0LjQiIHJ5PSIyNC4zIi8+DQoJPC9nPg0KPC9zdmc+"
    ```
