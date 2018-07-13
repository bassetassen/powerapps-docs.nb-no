---
title: Å forstå datakilder | Microsoft Docs
description: Referanseinformasjon for å arbeide med tilkoblinger og datakilder i Microsoft PowerApps.
documentationcenter: na
author: gregli-msft
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: conceptual
ms.component: canvas
ms.date: 03/08/2017
ms.author: gregli
ms.openlocfilehash: 4cdc1116de5882b69814bd91b4006debb8c5f5cf
ms.sourcegitcommit: 79b8842fb0f766a0476dae9a537a342c8d81d3b3
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 07/07/2018
ms.locfileid: "37899345"
---
# <a name="understand-data-sources-in-powerapps"></a>Å forstå datakilder i PowerApps
De fleste PowerApps-apper bruker ekstern informasjon som er lagret i skytjenester, kalt **Datakilder**. Et vanlig eksempel er en tabell i en Excel-fil som er lagret i OneDrive for Business. Appene får tilgang til disse datakildene ved hjelp av **Tilkoblinger**.

Denne artikkelen beskriver de ulike typene datakilder, og hvordan du arbeider med datakilder for tabeller.

Det er enkelt å opprette en app som utfører grunnleggende lesing og skriving for en datakilde. Men noen ganger vil du ha mer kontroll over hvordan data flyter inn og ut av appen.  Denne artikkelen beskriver hvordan funksjonene **[Patch](functions/function-patch.md)**, **[DataSourceInfo](functions/function-datasourceinfo.md)**, **[Validate](functions/function-validate.md)** og **[Errors](functions/function-errors.md)** gir mer kontroll.

## <a name="kinds-of-data-sources"></a>Datakildetyper
Datakilder kan være koblet til en skytjeneste, eller de kan være lokale for en app.

### <a name="connected-data-sources"></a>Tilkoblede datakilder
De vanligste datakildene er **Tabeller**, som du kan bruke til å hente og lagre informasjon. Du kan bruke **tilkoblinger** til datakilder for å lese og skrive data i Microsoft Excel-arbeidsbøker, SharePoint-lister, SQL-tabeller og mange andre formater, som kan lagres i skytjenester som OneDrive for Business, DropBox, SQL Server osv.

Andre datakilder enn tabeller inkluderer e-post, kalendere, Twitter og varslinger, men denne artikkelen omhandler ikke disse andre datakildetypene.

### <a name="local-data-sources"></a>Lokale datakilder
Ved hjelp av kontrollene **[Galleri](controls/control-gallery.md)**, **[Visningsskjema](controls/control-form-detail.md)**, og **[Redigeringsskjema](controls/control-form-detail.md)**, er det enkelt å opprette en app som leser og skriver data fra en datakilde.  For å komme i gang kan du lese artikkelen [Forstå dataskjemaer](working-with-forms.md).  

Disse kontrollene brukes når du ber PowerApps om å opprette en app fra data. Bak kulissene bruker appen en intern tabell til å lagre og manipulere dataene som kommer fra datakilden.

En spesiell datakildetype er [Samling](working-with-data-sources.md#collections), som er lokal for appen og ikke støttes av en tilkobling til en tjeneste i skyen, slik at informasjonen ikke kan deles på tvers av enheter for samme bruker, eller mellom brukere. Samlinger kan lastes inn og lagres lokalt.

### <a name="kinds-of-tables"></a>Tabelltyper
Tabeller som er interne for en PowerApps-app er faste verdier, på samme måte som at et tall eller en streng er en verdi. Interne tabeller blir ikke lagret noe sted, de eksisterer bare i appens minne. Du kan ikke endre strukturen og dataene i en tabell direkte. Det du i stedet kan gjøre, er å opprette en ny tabell gjennom en formel: du kan bruke denne formelen til å lage en endret kopi av den opprinnelige tabellen.

Eksterne tabeller blir lagret i en datakilde for senere henting og deling.  PowerApps tilbyr «tilkoblinger» for å lese og skrive lagrede data.  Du har tilgang til flere tabeller med informasjon i en tilkobling.  Du velger hvilke tabeller som skal brukes i appen, og hver av dem blir til en egen *datakilde*.  

For å finne ut mer, kan du se [Å arbeide med tabeller](working-with-tables.md), som gir mer detaljert informasjon om interne tabeller, men som også er gjeldende for eksterne tabeller som befinner seg i en skytjeneste.

## <a name="working-with-tables"></a>Å arbeide med tabeller
Du kan bruke tabelldatakilder på samme måte som du bruker en intern PowerApps-tabell.  Hver datakilde har [poster](working-with-tables.md#records), [kolonner](working-with-tables.md#columns) og egenskaper som du kan bruke i formler, akkurat som en intern tabell. I tillegg:

* Datakilden har de samme kolonnenavnene og datatypene som den underliggende tabellen i tilkoblingen.
  
    > [!NOTE]
  > PowerApps erstatter mellomrommene med **"\_x0020\_"** for SharePoint- og Excel-datakilder som inneholder kolonnenavn med mellomrom. **Kolonnenavn** i SharePoint eller Excel vil for eksempel vises som **"Column_x0020_Name"** i PowerApps når de vises i dataoppsettet, eller når de brukes i en formel.
* Datakilden lastes automatisk inn fra tjenesten når appen lastes inn.  Du kan fremtvinge oppdatering av dataene ved hjelp av **[Refresh](functions/function-refresh.md)**-funksjonen.
* Når brukere kjører en app, kan de opprette, endre og slette poster, og skyve disse endringene tilbake til den underliggende tabellen i tjenesten.
  * Poster kan opprettes med funksjonene **[Patch](functions/function-patch.md)** og **[Collect](functions/function-clear-collect-clearcollect.md)**.  
  * Poster kan endres med funksjonene **[Patch](functions/function-patch.md)**, **[Update](functions/function-update-updateif.md)** og **[UpdateIf](functions/function-update-updateif.md)**.
  * Poster kan fjernes med funksjonene **[Remove](functions/function-remove-removeif.md)** og **[RemoveIf](functions/function-remove-removeif.md)**.
  * Feil når du arbeider med en datakilde er tilgjengelig via **[Errors](functions/function-errors.md)**-funksjonen.
* Funksjonene **[DataSourceInfo](functions/function-datasourceinfo.md)**, **[Defaults](functions/function-defaults.md)** og **[Validate](functions/function-validate.md)** gir informasjon om datakilden som du kan bruke til å optimalisere brukeropplevelsen.

### <a name="creating-data-sources"></a>Å opprette datakilder
PowerApps kan ikke brukes til å opprette en koblet datakilde eller til å endre strukturen på den. Datakilden må allerede finnes et sted i en tjeneste. Du bruker for eksempel først Excel Online på OneDrive til å opprette en arbeidsbok for å opprette en tabell i en Excel-arbeidsbok lagret på OneDrive. Deretter oppretter du en tilkobling til den fra appen.  

Datakildesamlinger *kan* imidlertid opprettes og endres inne i en app, men de er bare midlertidige.

### <a name="display-one-or-more-records"></a>Å vise én eller flere poster
![](media/working-with-data-sources/reading-from-a-datasource.png) Diagrammet ovenfor viser informasjonsflyten når en app leser informasjonen i en datakilde:

* Informasjonen lagres og deles gjennom en lagringstjeneste (i dette tilfellet en SharePoint-liste på et Office 365-område).
* En tilkobling gjør denne informasjonen tilgjengelig for appen.  Tilkoblingen tar hånd om godkjenning av brukeren for tilgang til informasjonen.
* Når appen startes eller **[Refresh](functions/function-refresh.md)**-funksjonen trykkes på, blir informasjonen hentet fra tilkoblingen og til en datakilde i appen for lokal bruk.
* Formler brukes til å lese informasjonen og vise den i kontroller som brukeren kan se. Du kan vise postene for en datakilde ved hjelp av et galleri på skjermen, og overføre **[Elementer](controls/properties-core.md)**-egenskapen til datakilden: **Gallery.Items = DataSource**.  Du overfører kontrollene i galleriet til galleriet, ved hjelp av kontrollens **[Standard](controls/properties-core.md)**-egenskap.  
* Datakilden er også en tabell.  Du kan bruke funksjonene **[Filter](functions/function-filter-lookup.md)**, **[Sort](functions/function-sort.md)**, **[AddColumns](functions/function-table-shaping.md)** samt andre funksjoner hvis du ønsker å begrense og utvide datakilden før du bruker den som en helhet.  Du kan også bruke funksjonene **[Lookup](functions/function-filter-lookup.md)**, **[First](functions/function-first-last.md)**, **[Last](functions/function-first-last.md)** samt andre funksjoner hvis du ønsker å arbeide med enkeltposter.

### <a name="modify-a-record"></a>Å endre en post
I den foregående delen så du hvordan du leser en datakilde.  Legg merke til at pilene i diagrammet over peker i én retning.  Endringer i en datakilde blir ikke skjøvet tilbake gjennom de samme formlene som dataene ble hentet fra.  I stedet brukes nye formler.  Det bruker ofte en annen skjerm for redigering av en post enn for å bla gjennom poster, spesielt på en mobil enhet.

Vær oppmerksom på at hvis du vil endre en eksisterende post for en datakilde, må posten opprinnelig ha kommet fra datakilden.  Posten kan ha beveget seg gjennom et galleri, en [kontekstvariabel](working-with-variables.md#create-a-context-variable), og et ubegrenset antall formler, men opprinnelsen skal være sporbar tilbake til datakilden.  Dette er viktig fordi tilleggsinformasjon flyttes sammen med posten som er unik for å identifiserer den, noe som sikrer at du endrer den riktige posten.    

![](media/working-with-data-sources/writing-to-a-datasource.png) Diagrammet ovenfor viser flyten av informasjon for å oppdatere en datakilde:

* En **[Redigeringsskjema](controls/control-form-detail.md)**-kontroll angir en beholder for inndatakort, som består av brukerinndata-kontroller, som for eksempel en tekstinndata-kontroll eller en glidebryter.  **[Datakilde](controls/control-form-detail.md)**- og **[Element](controls/control-form-detail.md)**-egenskaper brukes til å identifisere posten som skal redigeres.
* Hvert inndatakort har en **[Standard](controls/properties-core.md)**-egenskap, som vanligvis er satt til feltet for skjemaets **ThisItem**-post.  Kontrollene i inndatakortet vil deretter hente inndataverdiene sine fra **[Standard](controls/properties-core.md)**.  Vanligvis trenger du ikke endre dette.
* Hvert inndatakort viser en egenskap for **[oppdatering](controls/control-card.md)**.  Denne egenskapen kartlegger brukerens inndata for et bestemt felt i posten for å skrive tilbake til datakilden.  Vanligvis trenger du ikke endre dette.
* En knapp eller en bildekontroll på skjermen lar brukeren lagre endringer i posten.  **[OnSelect](controls/properties-core.md)**-formelen for kontrollen påkaller **[SubmitForm](functions/function-form.md)**-funksjonen til å gjøre dette arbeidet.  **[SubmitForm](functions/function-form.md)** leser alle egenskapene for **[oppdatering](controls/control-card.md)** av kortene, og bruker dette til å skrive tilbake til datakilden.
* Noen ganger vil det dukke opp problemer.  En nettverkstilkobling kan være nede, eller en valideringskontroll er utviklet av tjenesten som appen ikke kjente til.  **Feil-** og  **[ErrorKind](controls/control-form-detail.md)**-egenskapene for skjemakontrollen gjør denne informasjonen tilgjengelig, slik at du kan vise den til brukeren.  

For en mer finjustert kontroll over prosessen kan du også bruke funksjonene **[Patch](functions/function-patch.md)** og **[Errors](functions/function-errors.md)**.  **[Redigeringsskjema](controls/control-form-detail.md)**-kontrollen viser en **[Oppdatering](controls/control-form-detail.md)**-egenskap, slik at du kan lese feltverdiene i skjemaet.  Du kan også bruke denne egenskapen til å oppkalle en egendefinert kobling på en tilkobling, noe som fullstendig hopper over funksjonene **Patch** og **SubmitForm**.

### <a name="validation"></a>Validering
Før du gjør en endring i en post, bør appen gjøre det den kan for å sikre at endringen vil godtas.  Det er to grunner til dette:

* *Umiddelbar tilbakemelding til brukeren*.  Det beste tidspunktet for å løse et problem er akkurat idét det oppstår.  Med bokstavelig talt hver berøring eller hvert tastetrykk, kan rød tekst vises som identifiserer et problem med oppføringen.
* *Mindre nettverkstrafikk og mindre ventetid for brukeren*.  Jo flere problemer som oppdages i appen, jo færre samtaler over nettverket for å finne og løse problemer.  Hver samtale tar tid, hvorpå brukeren må vente før de kan gå videre.

PowerApps tilbyr to verktøy for validering:

* Datakilden kan gi informasjon om hva som er gyldig, og hva som ikke er gyldig.  For eksempel kan tall ha minimums- og maksimumsverdier, og en eller flere poster kan være nødvendig.  Du kan få tilgang til denne informasjonen med **[DataSourceInfo](functions/function-datasourceinfo.md)**-funksjonen.  
* **[Validate](functions/function-validate.md)**-funksjonen bruker den samme informasjonen til å kontrollere verdien av en enkelt kolonne eller en hel post.

### <a name="error-handling"></a>Feilbehandling
Flott, du har godkjent posten.  Det er på tide å oppdatere posten med **[Patch](functions/function-patch.md)**!

Men det kan dessverre fremdeles være problemer.  Nettverket kan være nede, validering hos tjenesten kan mislykkes, eller brukeren har ikke de riktige tillatelsene, bare for å nevne noen av de mulige feilene appen din kan støte på.  Den må respondere riktig på feilsituasjoner, gi tilbakemelding til brukeren og tilby en fremgangsmåte slik at brukeren får løst problemet.  

Når det oppstår feil med en datakilde, vil appen automatisk registrere feilinformasjonen og gjøre den tilgjengelig gjennom **[Errors](functions/function-errors.md)**-funksjonen.  Feil er tilknyttet postene som hadde problemene.  Hvis problemet er noe brukeren kan reparere, som for eksempel et problem med validering, kan de sende inn posten på nytt, og feilene vil bli fjernet.

Hvis det oppstår en feil når en post opprettes med **[ Patch ](functions/function-patch.md)** eller **[ Collect](functions/function-clear-collect-clearcollect.md)**, er det ingen post å knytte eventuelle feil til.  I dette tilfellet vil *tom* bli returnert av **[Patch](functions/function-patch.md)** og kan brukes som argument for Poster til **[Errors](functions/function-errors.md)**.  Opprettingsfeil blir fjernet med neste operasjon.

**[Errors](functions/function-errors.md)**-funksjonen returnerer en tabell med feilinformasjon.  Denne informasjonen kan inkludere kolonneinformasjonen, hvis feilen kan tilskrives til en bestemt kolonne.  Bruk feilmeldinger for kolonnenivå i etikettkontroller som er nær der kolonnen er plassert på Rediger-skjermen.  Bruk feilmeldinger på postnivå hvis **kolonnen** i feiltabellen er *tom*, på en plassering nær **Lagre**-knappen for hele posten.  

### <a name="working-with-large-data-sources"></a>Å arbeide med store datakilder
Når du oppretter rapporter fra store datakilder (kanskje millioner av poster), ønsker du at nettverkstrafikken skal reduseres. La oss si at du vil rapportere om alle kunder som har en StatusCode kalt "Platinum" i New York.  Og at kundetabellen inneholder millioner av poster.

Du ønsker **ikke** å hente alle disse kundene til appen din, for deretter å velge dem du ønsker. Det du ønsker er at disse valgene skal skje i skytjenesten der tabellen er lagret, og sende de valgte postene over nettverket.

Mange, men ikke alle, funksjoner som du kan bruke til å velge poster kan *delegeres*, noe som betyr at de kjøres i skytjenesten. Finn ut hvordan du gjør dette ved å lese om [delegering](delegation-overview.md).

## <a name="collections"></a>Samlinger
Samlinger er en spesiell datakildetype.  De er lokale for appen og støttes ikke av en tilkobling til en tjeneste i skyen, slik at informasjonen ikke kan deles på tvers av enheter for samme bruker, eller mellom brukere.  De fungerer som en hvilken som helst annen datakilde, med noen unntak:

* Samlinger kan opprettes dynamisk med **[Collect](functions/function-clear-collect-clearcollect.md)**-funksjonen.  De trenger ikke å etableres på forhånd, slik som tilkoblingsbaserte datakilder gjør.
* Kolonnene i en samling kan endres når som helst ved bruk av **[Collect](functions/function-clear-collect-clearcollect.md)**-funksjonen.
* Samlinger tillater dupliserte poster.  Mer enn én kopi av samme post kan finnes i en samling.  Funksjoner, som for eksempel **[Remove](functions/function-remove-removeif.md)**, skal fungere på det første treffet den finner, med mindre **Alle**-argumentet er angitt.
* Du kan bruke funksjonene **[SaveData](functions/function-savedata-loaddata.md)** og **[LoadData](functions/function-savedata-loaddata.md)** for å lagre og laste inn en kopi av samlingen på nytt.  Informasjonen blir lagret på en privat plassering som andre brukere, apper eller enheter ikke har tilgang til.
* Du kan bruke **[Eksport](controls/control-export-import.md)**- og **[Import](controls/control-export-import.md)**-kontrollene for å lagre og laste inn en kopi av samlingen på nytt til en fil som brukeren kan samhandle med.  

Hvis du vil ha mer informasjon om hvordan du arbeider med en samling som datakilde, kan du se [Opprett og oppdater en samling](create-update-collection.md).

Samlinger brukes vanligvis til å opprette en global tilstand for appen.  Du kan se [Å arbeide med variabler](working-with-variables.md) for de tilgjengelige alternativene for å administrere en tilstand.

