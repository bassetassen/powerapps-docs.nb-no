---
title: Language-funksjonen | Microsoft Docs
description: Referanseinformasjon for Language-funksjonen i PowerApps, inkludert syntaks og eksempler
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 10/16/2016
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 45ffd324ff5409a49f1ec8c4c8ea3529c1cf5c5f
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/24/2018
ms.locfileid: "42833290"
---
# <a name="language-function-in-powerapps"></a>Language-funksjonen i PowerApps
Returnerer språkkoden for gjeldende bruker.

## <a name="description"></a>Beskrivelse
**Language**-funksjonen returnerer språket, skriptet og området for gjeldende bruker som en språkkode.

Bruk språkinformasjonen for å skreddersy appen på tvers av nasjonale innstillinger.  Hvis du for eksempel oppretter en app som skal brukes i Italia og Frankrike, kan du bruke **Language** for å automatisk vise italienske og franske strenger for brukerne på de forskjellige stedene. 

### <a name="language-tags"></a>Språkkoder
En *språkkode* kan være i ett av tre formater:

| Returverdi | Beskrivelse |
| --- | --- |
| **"*lg&#8209;RE*"** |*lg* er forkortelsen av språket på to bokstaver og *RE* er forkortelsen for området på to bokstaver.  Dette er den vanligste returverdien.  en-GB returneres for eksempel for Storbritannia. |
| **"*lg*"** |*lg* er forkortelsen av språket på to bokstaver.  Dette er formatet som brukes når PowerApps har informasjon om språket, men ikke har informasjon om det bestemte området. |
| **"*lg&#8209;scrp&#8209;RE*"** |*lg* er forkortelsen av språket på to bokstaver, *scrp* er forkortelsen for skriptet på fire bokstaver og *RE* er forkortelsen for området på to bokstaver. |

PowerApps bruker formatet [IETF BCP-47](https://tools.ietf.org/html/bcp47) for språkkoder.  

Hvis du vil se en liste over støttede språkkoder, skriver du inn **Value( "1", )** i formellinjen eller avansert visning, og bla gjennom listen over språk som foreslås for det andre argumentet.  

**[Text](function-text.md)**- og **[Value](function-value.md)**-funksjonene er også språkkoder.  Bruk disse funksjonene for å oversette til og fra tekststrenger, ved å ta høyde for globale forskjeller.  Når du sender en språkkode til disse funksjonene og område ikke spiller noen rolle, kan du bruke bare språkdelen av koden.

## <a name="syntax"></a>Syntaks
**Language**()

## <a name="examples"></a>Eksempler
### <a name="users-locale"></a>Brukerens nasjonale innstilling
Det antas at operativsystemet og/eller -nettleseren for verten bruker standard nasjonale innstilling for området.

| Formel | Plassering | Returverdi |
| --- | --- | --- |
| **Language()** |Lisboa i Portugal |pt-PT |
| **Language()** |Rio de Janeiro i Brasil |pt-BR |
| **Language()** |Atlanta i USA |en-US |
| **Language()** |Manchester i Storbritannia |en-GB |
| **Language()** |Paris i Frankrike |fr-FR |
| **Language()** |Roseau i Dominica |en |
| **Language()** |Beograd i Serbia |sr-cyrl-RS eller sr-latn-RS, avhengig av brukerens systeminnstillinger |

### <a name="localization-table"></a>Oversettelsestabell
En enkel tilnærming til lokalisering er å opprette et Excel-regneark som tilordner en definert **TextID** til en oversatt tekst på brukerens språk.  Selv om du kan bruke en samling eller en annen datakilde for denne tabellen, valgte vi Excel fordi det er enkelt å redigere og administrere utenfor appen av oversettere.

1. Opprett følgende tabell i Excel: 
   
    ![](media/function-language/loc-table.png)
   
    Oppføringen med *tom* for **Språk**-kolonnen brukes som standard hvis ingen spesifikk tekststreng finnes for et gitt språk. Denne oppføringen må vises etter alle andre oppføringer for en gitt **TextID**.
   
    For vårt formål trenger vi bare å ta en titt på språket for den nasjonale innstillingen og ikke området.  Hvis regionale hensyn var viktig, kunne vi ha inkludert den fullstendige språkkodeverdien i tabellen ovenfor. 
2. Bruk **Sett inn**-båndet og **Tabell**-kommandoen for å gjøre dette til en skikkelig Excel-tabell.  Tabellen får navnet **Table1** som standard, men du kan gi den hvilket som helst navn med **Tabellverktøy/Utforming**-båndet og tekstboksen **Tabellnavn:** til venstre på skjermen.
3. Lagre Excel-filen lokalt.   
4. Klikk eller trykk på **Data**-fanen i Power Apps i den høyre ruten, og klikk eller trykk på **Legg til datakilde**.
5. Klikk eller trykk på **Legg til statiske data på appen**, klikk eller trykk på Excel-filen som du lagret, og klikk eller trykk på **Åpne**.
6. Velg tabellen som du opprettet, og deretter klikker eller trykker du på **Koble til**.

Der du tidligere ville ha brukt teksten **«Hello»** i appen, bruker du nå heller denne formelen:

* **LookUp( Table1, TextID = "Hello" && (LanguageTag = Left( Language(), 2 ) || IsBlank( LanguageTag ))).LocalizedText**  

Denne formelen vil slå opp riktig **LocalizedText**-verdi for språket til brukeren, og hvis det ikke finnes, brukes standard *blank*-versjon. 

Vær oppmerksom på at oversatte strenger på andre språk kan være betydelig lengre enn de er på ditt språk.  I mange tilfeller må etiketter og andre elementer som viser strengene i brukergrensesnittet, være bredere for å få plass.

### <a name="translation-service"></a>Oversettingstjeneste
Du kan oversette tekst ved behov ved bruk av en oversettingstjeneste, som for eksempel Microsoft Translator-tjenesten:  

1. Klikk eller trykk på **Data**-fanen i Power Apps i den høyre ruten, og klikk eller trykk på **Legg til datakilde**.
2. Klikk eller trykk på **Microsoft Translator**.

Der du tidligere ville ha brukt teksten **«Hello»** i appen, bruker du nå heller denne formelen:

* **MicrosoftTranslator.Translate( "Hello", Language() )**

Microsoft Translator-tjenesten bruker de samme språkkodene som **Language**-funksjonen returnerer.

Denne tilnærmingen har sine ulemper når den sammenlignes med det forrige eksemplet, som tok i bruk en forhåndsoversatt tabell med tekststrenger:

* Oversettelsen bruker litt tid på bli ferdig, og det kreves at en tjeneste påkalles over nettverket.  Dette resulterer i en forsinkelse før du får se teksten i appen. 
* Oversettelsen utføres maskinelt, og det kan hende den ikke er som forventet eller det beste valget for situasjonen i appen din.

