---
title: Optimaliser ytelsen for lerretsapp | Microsoft Docs
description: Følg de anbefalte fremgangsmåtene i dette emnet for å øke ytelsen til lerretsapper du oppretter i PowerApps.
author: yingchin
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 08/31/2018
ms.author: yingchin
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: a04320d2d8bb2d8ad3ebf30d3ecbd0dfe7f9b0bd
ms.sourcegitcommit: 4db9c763455d141a7e1dd569a50c86bd9e50ebf0
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 02/20/2019
ms.locfileid: "57801967"
---
# <a name="optimize-canvas-app-performance-in-powerapps"></a>Optimaliser ytelsen for lerretsapp i PowerApps
Microsoft jobber hardt for å forbedre ytelsen til alle appene som kjører på Power-plattformen. Me du kan følge de anbefalte fremgangsmåtene i dette emnet for å øke ytelsen til apper du oppretter.

Når en bruker åpner en app, går den gjennom disse kjøringsfasene før du ser et brukergrensesnitt: 
1. **Godkjenner brukeren** – Ber brukeren, hvis vedkommende aldri har åpnet appen før, om å logge seg på med legitimasjonen for tilkoblingene appen trenger. Hvis den samme brukeren åpner appen på nytt, kan det hende vedkommende blir spurt på nytt, men det er avhengig av organisasjonens sikkerhetspolicyer. 
2. **Henter metadata** – Henter metadata som for eksempel versjonen av Power-plattformen der appen kjører, og kildene til datahentingen. 
3. **Initialiserer appen** – Utfører de oppgavene som er angitt i **OnStart**-egenskapen. 
4. **Gjengir skjermbilder** – Gjengir det første skjermbildet med kontroller som appen har forhåndsutfylt med data. Hvis brukeren åpner de andre skjermbildene, gjengir appen dem ved å bruke den samme prosessen.  

## <a name="limit-data-connections"></a>Begrense datatilkoblinger 
**Ikke koble til flere enn 30 datakilder fra samme app**. Apper ber nye brukere om å logge seg på hver kobling. Hver nye kobling øker derfor tiden det tar før appen starter. Når appen kjøres, krever hver kobling prosessorressurser, minne og nettverksbåndbredde når appen ber om data fra den kilden. 

Du kan raskt måle appens ytelse ved å slå på Utviklerverktøy i [Microsoft Edge](https://docs.microsoft.com/microsoft-edge/devtools-guide/network) eller [Google Chrome](https://developers.google.com/web/tools/chrome-devtools/network-performance/) mens appen kjøres. Det tar som regel mer enn 15 sekunder før appen returnerer data, hvis den ofte ber om data fra flere enn 30 datakilder. Det kan være Common Data Service for apper, Azure SQL, SharePoint og Excel på OneDrive.  

## <a name="limit-the-number-of-controls"></a>Begrens antallet kontroller 
**Ikke legg til flere enn 500 kontroller i den samme appen**. PowerApps genererer en HTML DOM for å gjengi hver kontroll. Jo flere kontroller du legger til, jo mer genereringstid trenger PowerApps. 

Du kan, i enkelte tilfeller, oppnå det samme resultatet og få appen til å starte raskere, hvis du bruker et galleri i stedet for individuelle kontroller. Du kan også redusere antallet kontrolltyper på den samme skjermen. Noen kontroller (som PDF-visningsprogrammet, datatabellen og kombinasjonsboksen) samler inn store kjøringsskript, og det tar lenger tid å gjengi dem. 

## <a name="optimize-the-onstart-function"></a>Optimaliser OnStart-funksjonen
Bruk [**ClearCollect**](functions/function-clear-collect-clearcollect.md)-funksjonen til å bufre data lokalt, hvis de ikke endres i løpet av brukerøkten. Du kan også bruke [**Concurrent**](functions/function-concurrent.md)-funksjonen til å laste datakilder samtidig.

Som [dette referanseemnet](functions/function-concurrent.md) demonstrerer, kan du bruke **Samtidig** for å redusere tiden det tar appen å laste data, med nesten halvparten.

Uten **Samtidig**-funksjonen så laster denne formelen fire tabeller, én etter én:

    ClearCollect( Product, '[SalesLT].[Product]' );
    ClearCollect( Customer, '[SalesLT].[Customer]' );
    ClearCollect( SalesOrderDetail, '[SalesLT].[SalesOrderDetail]' );
    ClearCollect( SalesOrderHeader, '[SalesLT].[SalesOrderHeader]' )

Du kan bekrefte denne virkemåten i utviklerverktøyene for nettleseren:

![Seriell ClearCollect](./media/performance-tips/perfconcurrent1.png)
    
Du kan legge inn den samme formelen i **Samtidigt**-funksjonen for å redusere den totale tiden operasjonen trenger:

    Concurrent( 
        ClearCollect( Product, '[SalesLT].[Product]' ),
        ClearCollect( Customer, '[SalesLT].[Customer]' ),
        ClearCollect( SalesOrderDetail, '[SalesLT].[SalesOrderDetail]' ),
        ClearCollect( SalesOrderHeader, '[SalesLT].[SalesOrderHeader]' ))
        
Med denne endringen så henter appen henter tabellene parallelt: 

![Parallell ClearCollect](./media/performance-tips/perfconcurrent2.png)  

## <a name="cache-lookup-data"></a>Hurtigbufre oppslagsdata
Bruk **Angi**-funksjonen til å bufre dataene fra oppslagstabeller for å unngå gjentatt henting av data fra kilden. Denne teknikken optimaliserer ytelsen hvis dataene sannsynligvis ikke endres under en økt. I dette eksemplet så hentes dataene fra kilden én gang, og deretter refereres det til dataene lokalt etter det, helt til brukeren lukker appen. 

    Set(CustomerOrder, Lookup(Order, id = “123-45-6789”));
    Set(CustomerName, CustomerOrder.Name);
    Set(CustomerAddress, CustomerOrder.Address);
    Set(CustomerEmail, CustomerOrder.Email);
    Set(CustomerPhone, CustomerOrder.Phone);

Kontaktinformasjon endres ikke ofte, det samme gjelder for standardverdier og brukerinformasjon. Du kan også generelt bruke denne teknikken med **Standard** og **Bruker**-funksjonen. 

## <a name="avoid-controls-dependency-between-screens"></a>Unngå kontrollavhengighet mellom skjermbilder
Hvis en kontrollverdi avhenger av verdien til en kontroll i et annet skjermbilde, kan du administrere dataene ved bruk av en variabel, samling eller en datakildereferanse.

## <a name="use-global-variables"></a>Bruk globale variabler
Hvis du vil sende apptilstanden fra ett skjermbilde til et annet, kan du opprette eller endre en global variabelverdi ved bruk av [**Angi**](functions/function-set.md)-funksjonen, i stedet for å bruke **Naviger** og **UpdateContext)**-funksjonene.

## <a name="use-delegation"></a>Bruk delegering
Bruk funksjoner, hvis mulig, som delegerer databehandling til datakilden, i stedet for å hente data til den lokale enheten for behandling. Hvis en app må behandle data lokalt, krever operasjonen mye mer prosessorkraft, minne og nettverksbåndbredde, spesielt hvis datasettet er stort.

Som [denne listen](delegation-list.md) viser, så støtter ulike datakilder delegering fra ulike funksjoner:

![Bruk delegering](./media/performance-tips/perfdelegation1.png)

SharePoint-lister støtter for eksempel delegering fra [**Filter**](functions/function-filter-lookup.md)-funksjonen, men ikke [**Søk**](functions/function-filter-lookup.md)-funksjonen. Du bør heller bruke **Filter** i stedet for **Søk** til å finne elementer i et galleri, hvis SharePoint-listen inneholder mer enn 500 elementer. Hvis du vil ha mer tips, kan du se [Arbeid med store SharePoint-lister i PowerApps](https://powerapps.microsoft.com/blog/powerapps-now-supports-working-with-more-than-256-items-in-sharepoint-lists/) (blogginnlegg). 

## <a name="use-delayed-load"></a>Bruk forsinket innlesing
Slå på den [eksperimentelle funksjonen](working-with-experimental.md) for Forsinket innlasting hvis appen har flere enn 10 skjermbilder, ingen regler, og mange kontroller på flere skjermer, og som er direkte knyttet til datakilden. Hvis du bygger denne apptypen og ikke aktiverer denne funksjonen, kan appytelsen forringes fordi kontrollene på alle skjermbildene må forhåndsutfylles, selv på skjermbilder som ikke er åpne. Alle skjermbildene i appen må oppdateres når datakilden endres, som når brukeren legger til en post.

## <a name="working-with-large-data-sets"></a>Arbeid med store datasett
Bruk datakilder og formler som kan delegeres slik at appen fungerer bra, samtidig som brukerne får tilgang til all informasjonen de trenger og at de unngår å nå grensen på 2000 for ikke-delegerbare spørringer. Når det gjelder datapostkolonner der brukerne kan søke etter, filtrere og sortere data, utformes disse kolonneindeksene på en vellykket måte. Det beskrives i disse dokumentene for [SQL Server](https://docs.microsoft.com/sql/relational-databases/sql-server-index-design-guide?view=sql-server-2017) og [SharePoint](https://support.office.com/article/Add-an-index-to-a-SharePoint-column-f3f00554-b7dc-44d1-a2ed-d477eac463b0).  

## <a name="republish-apps-regularly"></a>Publiser apper på nytt jevnlig
[Publiser appene](https://powerapps.microsoft.com/blog/republish-your-apps-to-get-performance-improvements-and-additional-features/) (blogginnnlegg) for å få bedre ytelse og tilleggsfunksjoner fra PowerApps-plattformen.

## <a name="avoid-repeating-the-same-formula-in-multiple-places"></a>Ikke gjenta den samme formelen på flere steder
Hvis flere egenskaper kjører den samme formelen (spesielt hvis det er komplekse), kan du vurdere å sette det én gang, og deretter refererer til resultatet av den første egenskapen i etterfølgende felt. For eksempel ikke angi den **DisplayMode** -egenskapen for Kontroller A, B, C, D og E i samme komplekse formelen. Angi i stedet AS **DisplayMode** til komplekse formelen, sette BS **DisplayMode** egenskapen til resultatet av AS **DisplayMode** -egenskapen, og så videre for C D og E.

## <a name="enable-delayoutput-on-all-text-input-controls"></a>Aktiver DelayOutput på alle inndatakontroller for tekst
Hvis du har flere formler eller regler som refererer til verdien for en **tekstinndata** kontroll, angi den **DelayedOutput** -egenskapen for kontrollen til true. Den **tekst** -egenskapen for kontrollen, oppdateres bare etter at tastetrykk angitt raskt har sluttet. Formler eller regler vil ikke kjøre så mange ganger, og vil forbedre appytelsen.

## <a name="avoid-using-formupdates-in-rules-and-formulas"></a>Unngå å bruke Form.Updates i regler og formler
Hvis du refererer til en brukerinndata verdi i en regel eller en formel ved hjelp av en **Form.Updates** variabelen, den gjentas over alle kortene til skjemaet data og oppretter en post hver gang. Hvis du vil gjøre appen mer effektiv, referere til verdien direkte fra datakortet eller kontrollverdien.

## <a name="next-steps"></a>Neste trinn
Se gjennom den [koding standarder](https://aka.ms/powerappscanvasguidelines) for maksimal appytelse og holde apper enklere å vedlikeholde.
