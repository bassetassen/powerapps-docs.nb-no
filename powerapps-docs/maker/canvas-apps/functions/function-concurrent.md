---
title: Concurrent-funksjonen | Microsoft Docs
description: Referanseinformasjon, inkludert syntaks, for Concurrent-funksjonen i PowerApps
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 06/26/2018
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 7ab695d461cb980556a3027297c3e7f5ac5bde61
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/07/2019
ms.locfileid: "71985505"
ms.PowerAppsDecimalTransform: true
---
# <a name="concurrent-function-in-powerapps"></a>Concurrent-funksjonen i PowerApps
Evaluerer flere formler samtidig mot hverandre.

## <a name="description"></a>Beskrivelse
**Concurrent**-funksjonen evaluerer flere formler samtidig. Vanligvis evalueres flere formler ved å kjede dem sammen med operatoren [ **;** ](operators.md) , som evaluerer hver sekvensielt i rekkefølge. Når appen utfører operasjoner samtidig, slipper brukerne å vente lenge på resultatene.

Bruk **Concurrent** i egenskapen [**OnStart**](../controls/control-screen.md) i appen for å forbedre ytelsen når appen laster data. Når datakall ikke starter før det forrige avsluttes, må appen vente på summen av alle forespørselstidene. Hvis datakallene begynner samtidig, må appen bare vente på den lengste forespørselstiden. Nettlesere forbedrer ofte ytelsen ved å utføre dataoperasjoner samtidig.

Du kan ikke forutse rekkefølgen formlene i **Concurrent**-funksjonen begynner og avslutter evalueringen. Formler i **Concurrent**-funksjonen bør ikke inneholde avhengigheter på andre formler i samme **Concurrent**-funksjon, og PowerApps viser en feilmelding hvis du prøver dette. Du kan helt trygt ha avhengigheter på formler utenfor **Concurrent**-funksjonen, da de fullføres før **Concurrent**-funksjonen starter. Formler etter **samtidige** funksjoner kan trygt ta avhengigheter på formler i: alle full fører før **samtidige** funksjoner full føres og flyttes til den neste formelen i en kjede (Hvis du **bruker operatoren** ). Vær oppmerksom på umerkelige rekkefølgeavhengigheter hvis du påkaller funksjoner eller tjenestemetoder som har bivirkninger.

Du kan koble sammen formler med operatoren **;** **i et argument for samtidig**. For eksempel: **Concurrent( Set( a; 1 );; Set( b; a+1 ); Set( x; 2 );; Set( y; x+2 ) )** evaluerer **Set( a; 1 );; Set( b; a+1 )** samtidig med **Set( x; 2 );; Set( y; x+2 )** . I dette tilfellet er det helt greit med avhengigheter inni formlene: **a** angis før **b**, og **x** angis før **y**.

Det kan hende at bare en håndfull formler evalueres samtidig, avhengig av enheten eller nettleseren som kjører appen. **Concurrent** bruker de tilgjengelige egenskapene og avsluttes ikke før alle formlene har blitt evaluert.

Hvis du aktiverer **Feiladministrasjon på formelnivå** (i avanserte innstillinger), returneres den første feilen som oppdages i argumentrekkefølgen fra **Concurrent**. Ellers returneres *tom*. Hvis alle formlene er vellykkede, returneres *sann*. Hvis én formel mislykkes, stanser resten av den formelen, men andre formler fortsetter evalueringen.

Du kan bare bruke **Concurrent** i [formler for virkemåte](../working-with-formulas-in-depth.md).

## <a name="syntax"></a>Syntaks
**Concurrent**( *Formula1*; *Formula2* [; ...] )

* *Formula* – obligatorisk. Formler som skal evalueres samtidig. Du må oppgi minst to formler.

## <a name="examples"></a>Eksempler

#### <a name="loading-data-faster"></a>Å laste inn data raskere

1. Opprett en app, og Legg til fire data kilder fra Common Data Service, SQL Server eller SharePoint. 

    Dette eksemplet bruker fire tabeller fra [eksemplet Adventure Works-databasen på SQL Azure](https://docs.microsoft.com/azure/sql-database/sql-database-get-started-portal). Etter at du har opprettet databasen, kobler du til den fra PowerApps ved bruk av det fullstendige servernavnet (for eksempel, srvname.database.windows.net):

    ![Å koble til Adventure Works-databasen i Azure](media/function-concurrent/connect-database.png)

2. Legg til en **[Knapp](../controls/control-button.md)** -kontroll, og angi **OnSelect**-egenskapen til denne formelen:

    ```powerapps-comma
    ClearCollect( Product; '[SalesLT].[Product]' );;
    ClearCollect( Customer; '[SalesLT].[Customer]' );;
    ClearCollect( SalesOrderDetail; '[SalesLT].[SalesOrderDetail]' );; 
    ClearCollect( SalesOrderHeader; '[SalesLT].[SalesOrderHeader]' )
    ```

3. Slå på utviklerverktøyene for å overvåke nettverkstrafikken mens appen kjører, i [Microsoft Edge](https://docs.microsoft.com/microsoft-edge/devtools-guide/network) eller [Google Chrome](https://developers.google.com/web/tools/chrome-devtools/network-performance/).

1. (valgfritt) Slå på nettverksbegrensning for å overdrive effektene av denne sammenligningen.

4. Velg knappen mens du holder nede ALT, og deretter kan du se nettverkstrafikken.

    Verktøyene viser fire forespørsler som utføres i serier, lik dette eksemplet.  Faktiske tider har blitt fjernet da det er store variasjoner.  Diagrammet viser at hver kall begynner etter at det foregående er fullført:

    ![Tidsdiagram over fire nettverksforespørsler der hver av dem starter etter at det foregående er fullført. Dette dekker hele tidsintervallet](media/function-concurrent/chained-network.png)

5. Lagre, lukk, og åpne appen på nytt.

    PowerApps bufrer dataene. Det vil si at hvis du velger knappen på nytt, blir det ikke nødvendigvis fire nye forespørsler. Hver gang du ønsker å teste ytelsen, lukker du og åpner appen på nytt. Hvis du har slått på nettverksbegrensning, kan du slå dette av til du er klar for å utføre en ny test.

1. Legg til en ny **[Knapp](../controls/control-button.md)** -kontroll, og angi **OnSelect**-egenskapen til denne formelen:

    ```powerapps-comma
    Concurrent( 
        ClearCollect( Product; '[SalesLT].[Product]' ); 
        ClearCollect( Customer; '[SalesLT].[Customer]' );
        ClearCollect( SalesOrderDetail; '[SalesLT].[SalesOrderDetail]' );
        ClearCollect( SalesOrderHeader; '[SalesLT].[SalesOrderHeader]' )
    )
    ```

    Vær oppmerksom på at du la til det samme **ClearCollect**-kallene i den første knappen, men de er denne gangen innpakket i en **Concurrent**-funksjon og adskilt med komma.

2. Fjern nettverksovervåking i nettleseren.

1. Hvis du brukte nettverksbegrensning før, kan du slå dette på igjen.

3. Velg den andre knappen mens du holder nede ALT, og deretter kan du se nettverkstrafikken.

    Verktøyene viser fire forespørsler som utføres samtidig, som i dette eksemplet.  Faktiske tider har på nytt blitt fjernet da det er store variasjoner.  Diagrammet viser at alle kallene begynner omtrent samtidig og at de ikke venter på at det foregående skal fullføres:

    ![Tidsdiagram over fire nettverksforespørsler der alle fire starter samtidig. Dette dekker omtrent halve tidsintervallet](media/function-concurrent/concurrent-network.png)

    Disse diagrammene er basert på den samme skalaen. Ved å bruke **Concurrent** halverte du tiden det tok disse operasjonene å fullføre. 

5. Lagre, lukk, og åpne appen på nytt.

#### <a name="race-condition"></a>Kappløpssituasjon

1. Legg til en tilkobling til [Microsoft Translator](../connections/connection-microsoft-translator.md)-tjenesten i appen.

2. Legg til en [**Tekstinndata**](../controls/control-text-input.md)-kontroll, og gi den det nye navnet **TextInput1** hvis den har et annet navn.

3. Legg til en **Knapp**-kontroll, og angi **OnSelect**-egenskapen til denne formelen:

    ```powerapps-comma
    Set( StartTime; Value( Now() ) );;
    Concurrent(
        Set( FRTrans; MicrosoftTranslator.Translate( TextInput1.Text; "fr" ) );; 
            Set( FRTransTime; Value( Now() ) );
        Set( DETrans; MicrosoftTranslator.Translate( TextInput1.Text; "de" ) );; 
            Set( DETransTime; Value( Now() ) )
    );;
    Collect( Results;
        { 
            Input: TextInput1.Text;
            French: FRTrans; FrenchTime: FRTransTime - StartTime; 
            German: DETrans; GermanTime: DETransTime - StartTime; 
            FrenchFaster: FRTransTime < DETransTime
        }
    )
    ```

4. Legg til en [**Datatabell**](../controls/control-data-table.md)-kontroll, og angi **Elementer**-egenskapen til **Resultater**.

1. Velg **Rediger felt** i **Egenskaper** -fanen i høyre rute for å åpne **felt** -ruten.

1. Merk av for hvert felt i listen over felter for å vise alle i datatabellen.

1. (valgfritt) Dra **Inndata**-feltet øverst i listen, og dra **FrenchFaster**-feltet nederst i listen.

    ![Liste over felter i Resultat-samlingen](media/function-concurrent/field-list.png) 

6. Skriv eller lim inn ordene som skal oversettes, i **Tekstinndata**-kontrollen.

7. Velg knappen flere ganger for å fylle tabellen mens du holder nede ALT.

    Tidene vises i millisekunder.
  
    ![Visning av datatabellen som inneholder resultatene av oversettelsen av strengen «Hello World» til fransk og tysk. Noen ganger er den franske oversettelsen raskere enn den tyske og omvendt.](media/function-concurrent/race-condition.png) 

    I enkelte tilfeller er den franske oversettelsen raskere enn den tyske oversettelsen og omvendt. Begge starter samtidig, men den ene returnerer før den andre av en rekke årsaker, inkludert nettverksventetid og behandling på serversiden.

    En [kappløpssituasjon](https://en.wikipedia.org/wiki/Race_condition) vil oppstå hvis appen er avhengig av at én oversettelse avsluttes først. PowerApps flagger heldigvis de fleste tidsberegningsavhengigheter den kan oppdage.
