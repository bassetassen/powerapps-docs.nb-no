---
title: Installere Northwind Traders databasen og appene | Microsoft Docs
description: Installere Northwind-databasen og apper i et miljø for å utforske tilhørende konsepter.
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 06/06/2019
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 351f9fd4fe369b3073a9edfb0158883140f50693
ms.sourcegitcommit: e85072f7a80da308c4caabe20adbf2509588ca57
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/07/2019
ms.locfileid: "66761032"
---
# <a name="install-northwind-traders-database-and-apps"></a>Installere Northwind Traders database og apper

Ved å følge trinnene i [denne serien av emner](northwind-orders-canvas-part1.md), kan du oppdage begreper om relasjonelle data som er implementert i en eksempeldatabasen i Common Data Service. Du kan også utforske business eksempelapper, begge lerret og modelldrevne, for administrasjon av dataene og få praktisk erfaring med å opprette en slik app. Dette første emnet forklarer hvordan du installerer Northwind Traders databasen i ditt eget miljø og få tilgang til eksempelapper, som du kan åpne for redigering hvis du vil vise hvordan de ble bygget.

Northwind Traders er en fiktive organisasjon som administrerer ordrer, produkter, kunder, leverandører og mange andre aspekter av små bedrifter. Dette eksemplet ble vist i de første versjonene av Microsoft Access, og er fremdeles tilgjengelig som en Access-mal.

## <a name="prerequisites"></a>Forutsetninger

- En PowerApps-lisens som støtter Common Data Service. Du kan [bruker en gratis prøveversjon](../signup-for-powerapps.md) i 30 dager.
- Et miljø med en Common Data Service-database. Du kan [opprette et slikt miljø](https://docs.microsoft.com/power-platform/admin/create-environment) Hvis du har riktige tillatelser.

## <a name="download-the-solution"></a>Last ned-løsningen

> [!div class="nextstepaction"]
> [Last ned filen Northwind Traders løsning](https://pwrappssamples.blob.core.windows.net/samples/NorthwindTraders_1_0_0_6.zip)

Dette [løsningen](../../developer/common-data-service/introduction-solutions.md) filen (ZIP) inneholder definisjonene av enheter, alternativsett og forretningsprosesser; lerretet og modelldrevne apper – og noen andre brikker som brukes sammen.

## <a name="install-the-solution"></a>Installere løsningen

1. Logg deg på [PowerApps](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc), og kontroller deretter at du arbeider i et miljø som inneholder en Common Data Service-database.

1. I den venstre navigasjonsruten, velg **løsninger**, og velg deretter **Import** på verktøylinjen nær toppen av skjermen:

    > [!div class="mx-imgBorder"]
    > ![Løsninger import-løsning og Vis inngangspunktet](media/northwind-install/solution-import.png)

1. I den **Velg løsningspakke** velger **Bla gjennom**.

    > [!div class="mx-imgBorder"]
    > ![Velg løsningspakke siden før pakken er valgt](media/northwind-install/select-solution2.png)

1. Finn filen du lastet ned, og velg deretter **åpne**.

    Hvis du ikke valgt et annet sted, blir filen i nedlastinger-mappen.

1. Hvis du har riktig fil (versjonsnummeret kan variere), velger du **neste**:

    > [!div class="mx-imgBorder"]
    > ![Velg løsningspakke side når pakken er valgt](media/northwind-install/confirm-solution2.png)

1. I den **informasjon om løsning** velger **neste** Hvis navnet på løsningen og utgiveren er riktige.

    > [!div class="mx-imgBorder"]
    > ![Løsningen informasjonsside](media/northwind-install/confirm-publisher.png)

1. I den **importalternativer** velger **Import** å bekrefte SDK-Meldingsbehandling, noe som krever eksemplet:

    > [!div class="mx-imgBorder"]
    > ![Importer alternativer for side](media/northwind-install/confirm-sdk.png)

    En annen side som viser fremdriften som løsningen er installert over de neste minuttene:

    > [!div class="mx-imgBorder"]
    > ![fremdriftsindikator](media/northwind-install/solution-progress.png)

    Når installasjonen er fullført, viser den opprinnelige siden resultatet:

    > [!div class="mx-imgBorder"]
    > ![Import av løsning-siden](media/northwind-install/solution-success.png)

1. Velg **Lukk**.

## <a name="load-the-sample-data"></a>Laste inn eksempeldata

1. Velg **apper**, og velg deretter **Northwind eksempeldata**.

    Vent et øyeblikk Hvis Northwind-appene ikke vises umiddelbart etter at du installerer løsningen:

    > [!div class="mx-imgBorder"]
    > ![Northwind-database i listen over apper](media/northwind-install/sample-data-app.png)

1. Når appen ber om tillatelse til å samhandle med Common Data Service, velg **Tillat**:

    > [!div class="mx-imgBorder"]
    > ![Dialogboksen for samtykke for Common Data Service](media/northwind-install/sample-data-permission.png)

1. Når appen laster inn og viser at enhetene eksemplet inneholder ingen poster, velger du **laste Data inn** til å fylle ut enhetene:

    > [!div class="mx-imgBorder"]
    > ![Laste inn data-knappen i eksemplet Data Manager](media/northwind-install/sample-data-load.png)

    Når appen laster inn dataene, mars punkt på tvers av øverst i appen, og hvor mange poster øker.

    De er lastet inn i en bestemt rekkefølge slik at relasjoner kan opprettes mellom poster. For eksempel den **Ordredetaljer** enheten har en mange-til-én-relasjon med den **ordrer** og **bestille produkter** enheter, som er lastet inn, først.

    Du kan avbryte prosessen når som helst ved å velge **Avbryt**, og du kan fjerne dataene når som helst ved å velge **Fjern Data**:

    > [!div class="mx-imgBorder"]
    > ![Eksempel på Data Manager som data er lastet inn](media/northwind-install/sample-data-progress.png)

    Når dataene er ferdig lastet inn, den siste raden (**mange til mange-relasjoner**) viser **ferdig**, og den **laste Data inn** og **Fjern Data** knapper er aktivert på nytt:

    > [!div class="mx-imgBorder"]
    > ![Eksempel på Data Manager etter at dataene er lastet inn](media/northwind-install/sample-data-complete.png)

## <a name="sample-apps"></a>Eksempelapper

Northwind løsningen inkluderer disse appene for samhandling med disse dataene:

- Northwind ordrer (lerret)
- Northwind ordrer (modelldreven)

Du åpner disse appene på samme måte som at du har åpnet appen i den forrige prosedyren.

### <a name="canvas"></a>Lerret

Denne appen for én skjerm tilbyr en enkel overordnet-detaljert visning av den **ordrer** enhet, der du kan vise og redigere et sammendrag av rekkefølgen og hvert linjeelement for en ordre. En liste over ordrer vises nær venstre kant, og du kan velge en pil i denne listen for å vise et sammendrag og detaljene i den rekkefølgen. Mer informasjon: [Oversikt over lerretsapp for Northwind Traders](northwind-orders-canvas-overview.md).

> [!div class="mx-imgBorder"]
> ![Liste over ordrer og detaljer i Northwind lerret app](media/northwind-install/orders-canvas.png)

### <a name="model-driven"></a>Modelldrevet

Denne appen fungerer på samme data (i den **ordrer** enhet) som lerretsapp. I listen over ordrer, kan du vise mer informasjon om en ordre ved å velge tallet:

> [!div class="mx-imgBorder"]
> ![liste over ordrer i Northwind modelldrevet app](media/northwind-install/orders-model.png)

Det vises et sammendrag av rekkefølgen på et eget skjema:

> [!div class="mx-imgBorder"]
> ![Ordredetaljer i modelldrevne apper](media/northwind-install/orders-model-2.png)

Hvis du ruller nedover i skjemaet, viser den samme linjeelementene som lerret-app:

> [!div class="mx-imgBorder"]
> ![mer informasjon i rekkefølge i modelldrevne apper](media/northwind-install/orders-model-3.png)

## <a name="do-it-yourself"></a>Gjøre det selv

Du kan følge trinnvise instruksjoner for å lage lerretsapp som er vist tidligere i dette emnet.  Instruksjonene består av tre deler:

1. [Opprett en ordre galleri](northwind-orders-canvas-part1.md).
1. [Opprette et sammendrag av skjema](northwind-orders-canvas-part2.md).
1. [Opprett et galleri i detalj](northwind-orders-canvas-part3.md).

Hvis du vil Hopp fremover, inneholder løsningen en startmappe app for hver del.  I listen over apper, ser du etter **Northwind ordrer (lerret) - begynne del 1** og så videre.

Dette [oversikt over appen](northwind-orders-canvas-overview.md) forklarer brukeren grensesnitt, datakilder, og hvordan relasjoner brukes.

> [!div class="nextstepaction"]
> [Begynn med å lese oversikten](northwind-orders-canvas-overview.md)
