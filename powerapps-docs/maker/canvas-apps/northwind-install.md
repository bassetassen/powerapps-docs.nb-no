---
title: Installer Gastronor-databaser og-apper | Microsoft Docs
description: Installer Gastronor-databasen og-appene i et miljø for å utforske Relasjons konsepter.
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 06/06/2019
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 3a2c3b468c7ccc09c49221c65113e66b562f5ed1
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/07/2019
ms.locfileid: "71990548"
---
# <a name="install-northwind-traders-database-and-apps"></a>Installer databaser og apper for Gastronor-delikat Esser

Ved å følge trinnene i [denne serien av emner](northwind-orders-canvas-part1.md), kan du oppdage konsepter om relasjonelle data som implementert i en eksempel database i Common data service. Du kan også utforske eksempel virksomhets programmer, både lerret og modell drevne, for å administrere dataene og oppnå praktisk erfaring ved å opprette en slik app. Dette første emnet forklarer hvordan du installerer databasen Gas tro nor delikat Esser i ditt eget miljø og får tilgang til eksempel programmene, som du kan åpne for redigering for å vise hvordan de ble bygd.

Gas tro nor delikat Esser er en fiktiv organisasjon som administrerer ordrer, produkter, kunder, leverandører og mange andre deler av en liten bedrift. Dette eksemplet ble vist med de første versjonene av Microsoft Access og er fremdeles tilgjengelig som en Access-mal.

## <a name="prerequisites"></a>Forutsetninger

- En PowerApps-lisens som støtter Common Data Service. Du kan [bruke en gratis prøve lisens](../signup-for-powerapps.md) i 30 dager.
- Et miljø med en Common Data Service-database. Du kan [opprette et slikt miljø](https://docs.microsoft.com/power-platform/admin/create-environment) hvis du har riktige tillatelser.

## <a name="download-the-solution"></a>Last ned løsningen

> [!div class="nextstepaction"]
> [Last ned løsnings filen for Gas tro nor delikat Esser](https://pwrappssamples.blob.core.windows.net/samples/NorthwindTraders_1_0_0_6.zip)

Denne [løsnings](../../developer/common-data-service/introduction-solutions.md) filen (zip) inneholder definisjonene av enheter, alternativ sett og forretnings prosesser. lerretet og modell drevne apper; og andre deler som brukes sammen.

## <a name="install-the-solution"></a>Installer løsningen

1. Logg deg på [powerapps](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc), og kontroller deretter at du jobber i et miljø som inneholder en Common data service-database.

1. Velg **løsninger**i den venstre navigasjons ruten, og velg deretter **Importer** på verktøy linjen nær toppen av skjermen:

    > [!div class="mx-imgBorder"]
    > @no__t – 0Solutions visnings-og import løsnings punkt @ no__t-1

1. Velg **Bla gjennom**på siden **Velg løsnings pakke** .

    > [!div class="mx-imgBorder"]
    > ![Select løsnings pakkes IDen før pakken er valgt @ no__t-1

1. Finn filen du lastet ned, og velg deretter **Åpne**.

    Hvis du ikke har valgt en annen plassering, vises filen i nedlastinger-mappen.

1. Hvis du har riktig fil (versjons nummeret kan variere), velger du **neste**:

    > [!div class="mx-imgBorder"]
    > ![Select på løsnings pakkes IDen etter at pakken er valgt @ no__t-1

1. Velg **neste** hvis navnet på løsningen og utgiveren er riktig på siden **løsnings informasjon** .

    > [!div class="mx-imgBorder"]
    > @no__t informasjons side for 0Solution @ no__t-1

1. På siden for **import alternativer** velger du **Importer** for å bekrefte behandling av SDK-melding, som eksemplet krever:

    > [!div class="mx-imgBorder"]
    > @no__t 0Import Options-siden @ no__t-1

    En annen side vises og viser frem driften når løsningen installeres i løpet av de neste minuttene:

    > [!div class="mx-imgBorder"]
    > ![progress stolpe @ no__t-1

    Når installasjonen er ferdig, viser den opprinnelige siden resultatet:

    > [!div class="mx-imgBorder"]
    > ![Importing løsnings side @ no__t-1

1. Velg **Lukk**.

## <a name="load-the-sample-data"></a>Last inn eksempel dataene

1. Velg **apper**, og velg **eksempel dataene Gas tro nor**.

    Vent noen minutter hvis appene Gas tro nor ikke vises umiddelbart etter at du har installert løsningen:

    > [!div class="mx-imgBorder"]
    > ![Northwind database i listen over apper @ no__t-1

1. Når appen ber om tillatelse til å samhandle med Common Data Service, velger du **Tillat**:

    > [!div class="mx-imgBorder"]
    > dialog boksen @no__t – 0Consent for Common Data Service @ no__t-1

1. Når appen er lastet inn og viser at eksempel enhetene ikke inneholder noen poster, velger du **Last inn data** for å fylle ut enhetene:

    > [!div class="mx-imgBorder"]
    > @no__t data-knapp for 0Load i eksempel data behandling @ no__t-1

    Når appen laster inn dataene, prikker mars i hele appen, og antallet poster øker.

    Enheter lastes inn i en bestemt rekkefølge, slik at relasjoner kan opprettes mellom poster. For eksempel har enheten for **ordre detaljer** en mange-til-én-relasjon **med ordrene** og **ordre produkt** enhetene, som lastes inn først.

    Du kan når som helst avbryte prosessen ved å velge **Avbryt**, og du kan når som helst fjerne dataene ved å velge **Fjern data**:

    > [!div class="mx-imgBorder"]
    > 0Sample data behandling som data lastes inn @ no__t-1 @no__t

    Når dataene er lastet inn, vises den siste raden (**mange til mange relasjoner** **), og**knappen **Last inn data** og **Fjern data** er aktivert på nytt:

    > [!div class="mx-imgBorder"]
    > @no__t – 0Sample data Manager etter at data er lastet inn @ no__t-1

## <a name="sample-apps"></a>Eksempelapper

Gastronor-løsningen inkluderer disse appene for samhandling med disse dataene:

- Gastronor-ordrer (lerret)
- Gastronor-ordrer (modell drevet)

Du åpner disse appene på samme måte som du åpnet appen i forrige prosedyre.

### <a name="canvas"></a>Lerret

Denne appen med én skjerm har en enkel overordnet – detaljert visning av **Orders** -enheten, der du kan vise og redigere et sammendrag av ordren og hvert linje element for en ordre. En liste over ordrer vises nær den venstre kanten, og du kan velge en pil i listen for å vise et sammendrag og detaljene i den rekkefølgen. Mer informasjon: [Oversikt over lerret-appen for Gas tro nor delikat Esser](northwind-orders-canvas-overview.md).

> [!div class="mx-imgBorder"]
> @no__t – 0List av ordrer og detaljer i Gastronor-lerret-appen @ no__t-1

### <a name="model-driven"></a>Modelldrevet

Denne appen opererer på de samme dataene (i **Orders** -enheten) som lerret-appen. Vis mer informasjon om en ordre ved å velge nummeret i listen over ordrer:

> [!div class="mx-imgBorder"]
> @no__t – 0list av ordrer i Gastronor-modell drevne appen @ no__t-1

Et sammendrag av ordren vises i et separat skjema:

> [!div class="mx-imgBorder"]
> @no__t 0order detaljer i modell drevne appen @ no__t-1

Hvis du ruller ned i skjemaet, vises de samme linje elementene som lerretet gjør:

> [!div class="mx-imgBorder"]
> @no__t bestillings detaljer i modell drevne apper @ no__t-1

## <a name="do-it-yourself"></a>Gjør det selv

Du kan følge trinn vise instruksjoner for å opprette lerret-appen som vises tidligere i dette emnet.  Instruksjonene er delt inn i tre deler:

1. [Opprett et ordre Galleri](northwind-orders-canvas-part1.md).
1. [Opprett et sammendrags skjema](northwind-orders-canvas-part2.md).
1. [Opprett et detalj Galleri](northwind-orders-canvas-part3.md).

Hvis du vil hoppe over, inneholder løsningen en start-og-punkt-app for hver del.  Se etter **Gas tro nor orders (lerret) i listen over apper – Start del 1** og så videre.

Denne [oversikten over appen](northwind-orders-canvas-overview.md) forklarer bruker grensesnittet, data kildene og hvordan relasjoner brukes.

> [!div class="nextstepaction"]
> [Begynn med å lese oversikten](northwind-orders-canvas-overview.md)
