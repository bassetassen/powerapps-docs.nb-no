---
title: Optimaliser ytelsen for lerretsapp | Microsoft Docs
description: Følg de anbefalte fremgangsmåtene i dette emnet for å øke ytelsen til lerretsapper du oppretter i PowerApps.
author: yingchin
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 06/17/2019
ms.author: yingchin
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: c0926c2c38adac6b3377de9a87eef4dd7d7a7cf7
ms.sourcegitcommit: 9c4d95eeace85a3e91a00ef14fefe7cce0af69ec
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/25/2019
ms.locfileid: "67349819"
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

Du kan raskt måle appens ytelse ved å slå på Utviklerverktøy i [Microsoft Edge](https://docs.microsoft.com/microsoft-edge/devtools-guide/network) eller [Google Chrome](https://developers.google.com/web/tools/chrome-devtools/network-performance/) mens appen kjøres. Appen er mer sannsynlig tar lengre tid enn 15 sekunder å returnere data hvis det ofte ber om data fra mer enn 30 datakilder, for eksempel Common Data Service, Azure SQL, SharePoint og Excel i OneDrive.  

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
For å forbedre ytelsen, skjermer i en app som er lastet inn i minnet bare når de trengs. Denne optimaliseringen kan være hemmes Hvis, for eksempel skjermen 1 er lastet inn, og én av dens formlene bruker en egenskap for en kontroll fra 2-skjermen. Nå vil skjermen 2 må være lastet inn for å oppfylle avhengigheten før skjermen 1 kan vises. Tenk deg at skjermen 2 har en avhengighet på skjermen 3, som har en annen avhengighet på skjermen 4, og så videre. Denne avhengighetskjeden kan føre til at mange skjermer som skal lastes inn.

Derfor unngå formelen avhengigheter mellom skjermer. I noen tilfeller kan du bruke en global variabel eller samlingen til å dele informasjon mellom skjermer.

Det er et unntak. Tenk deg at det er den eneste måten å vise skjerm 1 ved å gå fra skjermen 2 i det forrige eksemplet. Deretter skjermen 2 ville ha allerede er lastet inn i minnet når skjermen 1 var som skal lastes inn. Ingen ekstra arbeid er nødvendig for å utføre avhengigheten for skjermen 2, og det er derfor ingen innvirkning på ytelsen.

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
