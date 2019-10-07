---
title: Optimaliser ytelsen for lerretsapp | Microsoft Docs
description: Følg de anbefalte fremgangsmåtene i dette emnet for å øke ytelsen til lerretsapper du oppretter i PowerApps.
author: yingchin
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 06/17/2019
ms.author: yingchin
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 9943678815b53df048ad197e3cdcbd56f4070fa3
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/07/2019
ms.locfileid: "71995792"
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

Du kan raskt måle appens ytelse ved å slå på Utviklerverktøy i [Microsoft Edge](https://docs.microsoft.com/microsoft-edge/devtools-guide/network) eller [Google Chrome](https://developers.google.com/web/tools/chrome-devtools/network-performance/) mens appen kjøres. Det er mer sannsynlig at appen tar lengre tid enn 15 sekunder å returnere data hvis den ofte ber om data fra mer enn 30 data kilder, for eksempel Common Data Service, Azure SQL, SharePoint og Excel på OneDrive.  

## <a name="limit-the-number-of-controls"></a>Begrens antallet kontroller 
**Ikke legg til flere enn 500 kontroller i den samme appen**. PowerApps genererer en HTML DOM for å gjengi hver kontroll. Jo flere kontroller du legger til, jo mer genereringstid trenger PowerApps. 

Du kan, i enkelte tilfeller, oppnå det samme resultatet og få appen til å starte raskere, hvis du bruker et galleri i stedet for individuelle kontroller. Du kan også redusere antallet kontrolltyper på den samme skjermen. Noen kontroller (som PDF-visningsprogrammet, datatabellen og kombinasjonsboksen) samler inn store kjøringsskript, og det tar lenger tid å gjengi dem. 

## <a name="optimize-the-onstart-function"></a>Optimaliser OnStart-funksjonen
Bruk [**ClearCollect**](functions/function-clear-collect-clearcollect.md)-funksjonen til å bufre data lokalt, hvis de ikke endres i løpet av brukerøkten. Du kan også bruke [**Concurrent**](functions/function-concurrent.md)-funksjonen til å laste datakilder samtidig.

Som [dette referanseemnet](functions/function-concurrent.md) demonstrerer, kan du bruke **Samtidig** for å redusere tiden det tar appen å laste data, med nesten halvparten.

Uten **Samtidig**-funksjonen så laster denne formelen fire tabeller, én etter én:

```
ClearCollect( Product, '[SalesLT].[Product]' );
ClearCollect( Customer, '[SalesLT].[Customer]' );
ClearCollect( SalesOrderDetail, '[SalesLT].[SalesOrderDetail]' );
ClearCollect( SalesOrderHeader, '[SalesLT].[SalesOrderHeader]' )
```

Du kan bekrefte denne virkemåten i utviklerverktøyene for nettleseren:

![Seriell ClearCollect](./media/performance-tips/perfconcurrent1.png)
    
Du kan legge inn den samme formelen i **Samtidigt**-funksjonen for å redusere den totale tiden operasjonen trenger:

```
Concurrent( 
    ClearCollect( Product, '[SalesLT].[Product]' ),
    ClearCollect( Customer, '[SalesLT].[Customer]' ),
    ClearCollect( SalesOrderDetail, '[SalesLT].[SalesOrderDetail]' ),
    ClearCollect( SalesOrderHeader, '[SalesLT].[SalesOrderHeader]' ))
```

Med denne endringen så henter appen henter tabellene parallelt: 

![Parallelle ClearCollect](./media/performance-tips/perfconcurrent2.png)  

## <a name="cache-lookup-data"></a>Hurtigbufre oppslagsdata
Bruk **Angi**-funksjonen til å bufre dataene fra oppslagstabeller for å unngå gjentatt henting av data fra kilden. Denne teknikken optimaliserer ytelsen hvis dataene sannsynligvis ikke endres under en økt. I dette eksemplet så hentes dataene fra kilden én gang, og deretter refereres det til dataene lokalt etter det, helt til brukeren lukker appen. 

```
Set(CustomerOrder, Lookup(Order, id = “123-45-6789”));
Set(CustomerName, CustomerOrder.Name);
Set(CustomerAddress, CustomerOrder.Address);
Set(CustomerEmail, CustomerOrder.Email);
Set(CustomerPhone, CustomerOrder.Phone);
```

Kontaktinformasjon endres ikke ofte, det samme gjelder for standardverdier og brukerinformasjon. Du kan også generelt bruke denne teknikken med **Standard** og **Bruker**-funksjonen. 

## <a name="avoid-controls-dependency-between-screens"></a>Unngå kontrollavhengighet mellom skjermbilder
For å forbedre ytelsen blir skjermene i en app lastet inn i minnet bare etter behov. Denne optimaliseringen kan være hemmes Hvis for eksempel skjerm 1 er lastet inn, og én av formlene bruker en egenskap til en kontroll fra skjerm 2. Nå må skjerm 2 være lastet inn for å fullføre avhengigheten før skjerm 1 kan vises. Tenk deg at skjerm 2 har en avhengighet på skjerm 3, som har en annen avhengighet på skjermen 4, og så videre. Denne avhengighetstypen kan føre til at mange skjermer lastes inn.

Derfor unngår du avhengigheter mellom formler mellom skjermer. I noen tilfeller kan du bruke en global variabel eller samling til å dele informasjon mellom skjermer.

Det er et unntak. I det forrige eksemplet forestiller du deg at den eneste måten å vise skjerm 1 på, er å navigere fra skjerm 2. Deretter er skjerm 2 allerede lastet inn i minnet da skjerm 1 ble lastet inn. Det kreves ingen ekstra arbeid for å fullføre avhengigheten for skjerm 2, og det er derfor ingen innvirkning på ytelsen.

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

## <a name="avoid-repeating-the-same-formula-in-multiple-places"></a>Unngå å gjenta den samme formelen flere steder
Hvis flere egenskaper kjører den samme formelen (spesielt hvis den er kompleks), kan du vurdere å angi den én gang og deretter referere til utdataene for den første egenskapen i etterfølgende dem. Du kan for eksempel ikke angi **Display Mode** -egenskapen for kontrollene A, B, C, D og E til den samme komplekse formelen. I stedet angir du en **Display Mode** -egenskap til den kompleks formelen, angir B s **Display Mode** -egenskap til resultatet av egenskapen **Display Mode** , og så videre for C, D og E.

## <a name="enable-delayoutput-on-all-text-input-controls"></a>Aktiver DelayOutput på alle tekst inn data-kontroller
Hvis du har flere formler eller regler som refererer til verdien for en **tekst inn data** -kontroll, kan du angi **DelayedOutput** -egenskapen for denne kontrollen til sann. **Tekst** -egenskapen for denne kontrollen blir bare oppdatert etter at taste trykk som er skrevet inn i rask rekkefølge, har sluttet. Formlene eller reglene kan ikke kjøres så mange ganger, og app-ytelsen vil bli bedre.

## <a name="avoid-using-formupdates-in-rules-and-formulas"></a>Unngå å bruke skjema. oppdateringer i regler og formler
Hvis du refererer til en verdi for bruker inn data i en regel eller formel ved hjelp av et **skjema. oppdaterer** variabelen ved å gjenta alle data kortene i skjemaet og opprette en post hver gang. Hvis du vil gjøre appen din mer effektiv, kan du referere til verdien direkte fra data kortet eller kontroll verdien.

## <a name="next-steps"></a>Neste trinn
Gjennomgå [kode standardene](https://aka.ms/powerappscanvasguidelines) for å få mest mulig ut av app-ytelsen og holde appene enklere å vedlikeholde.
