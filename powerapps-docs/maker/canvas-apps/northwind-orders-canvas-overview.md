---
title: Oversikt over lerretsapp for Northwind Traders | Microsoft Docs
description: ''
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 05/17/2019
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: e2f28b07f53646e6fbf5afc0b1510bd37e3262b8
ms.sourcegitcommit: e85072f7a80da308c4caabe20adbf2509588ca57
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/07/2019
ms.locfileid: "66761055"
---
# <a name="overview-of-the-canvas-app-for-northwind-traders"></a>Oversikt over lerretsapp for Northwind Traders

Lær mer om lerretsapp for administrasjon av relasjonelle data i Northwind Traders databasen som du [installert i miljøet ditt](northwind-install.md). Følg deretter trinnvise instruksjoner i senere emner til å bygge denne appen fra grunnen av, og dermed få praktisk erfaring med å arbeide med relasjonelle data.

I dette emnet, kan du oppdage:

- Hvordan en appbruker viser og administrerer relasjonelle data i appen.
- Hvilke typer data stasjonen appen.
- Hvordan relasjoner mellom disse typer data ble opprettet.

I en enkelt skjerm, kan appbrukeren vise, oppdatere, opprette og slette bestillinger.

> [!div class="mx-imgBorder"]
> ![Fullstendig lerretsapp](media/northwind-orders-canvas-part1/orders-finished.png)

## <a name="explore-the-user-interface"></a>Utforsk brukergrensesnittet

### <a name="order-gallery"></a>Ordre-galleriet

En galleriet viser en liste over ordrer, inkludert nummeret for, status, navnet på kunden, og den totale kostnaden for rekkefølgen på venstre kant av appen. Brukeren kan bla gjennom listen for å finne en ordre, og deretter vise mer informasjon om den ved å velge pilen for ordren. Mer informasjon: [Opprett galleriet rekkefølge](northwind-orders-canvas-part1.md).

### <a name="summary-form"></a>Sammendrag av skjema

I hjørnet øverst til høyre oppsummerer et skjema rekkefølgen at brukeren har valgt i galleriet rekkefølge. Sammendraget inneholder mye av den samme informasjonen som gjør galleriet, men sammendraget viser også datoene når bestillingen er opprettet og betalt, samt navnet og bildet av ansatt som administrerte rekkefølgen. Brukeren kan endre dataene i skjemaet, lagre disse endringene, annullere dem eller slette rekkefølgen ved å velge et ikon nær høyre kant av tittellinjen. Mer informasjon: [Opprett sammendrag skjemaet](northwind-orders-canvas-part2.md).

### <a name="detail-gallery"></a>Detaljer-galleriet

En annen galleriet viser informasjon om hvilke produkter som inneholder den valgte ordren og hvor mange i hjørnet nederst til høyre. Hvert element i dette galleriet er kjent som en Ordredetaljer. Appbrukeren kan legge til og slette et element i galleriet ved hjelp av kontrollene i og under den. Mer informasjon: [Opprett galleriet detaljer](northwind-orders-canvas-part3.md).

> [!div class="mx-imgBorder"]
> ![Definisjonen av skjermen områder](media/northwind-orders-canvas-part1/orders-parts.png)

## <a name="explore-the-data-sources"></a>Finn ut mer om datakilder

Hvis du vil opprette denne appen, viser data fra fem enheter og et alternativsett. De fleste områder av denne appen viser faktisk data fra flere enheter. Rekkefølgen galleriet inneholder for eksempel denne informasjonen:

- Nummeret for er et felt i den **ordrer** enhet.
- Statusen er et annet felt i den **ordrer** enhet, et alternativ fra den **ordrestatus** alternativsett.
- Kundenavn er et felt i den **kunder** enhet.
- Den totale kostnaden beregnes basert på data i den **Ordredetaljer** enhet.

Sammendraget inneholder noen av den samme informasjonen som listen av bestillinger, men den inneholder også navnet og bildet av ansatt som administrerte rekkefølgen. At informasjonen er trukket ut av feltene i den **ansatte** enhet. Detaljert galleriet viser poster i den **Ordredetaljer** enheten, og hvert produkt i disse detaljene er en post i den **bestille produkter** enhet.

## <a name="explore-the-relationships"></a>Utforske relasjoner

Du kan vise data fra forskjellige kilder (for eksempel entiteter) i det samme galleriet eller skjemaet fordi disse enhetene har relasjoner som ble opprettet for deg i databasen.

### <a name="many-to-one-relationships"></a>Mange-til-én-relasjoner

For eksempel informasjon om kunden og ansatt for hver ordre ligger i den **kunder** og **ansatte** enheter. Derfor den **ordrer** enheten har mange-til-én-relasjoner med disse enhetene fordi det finnes mange ordrer, som kan være plassert av bare én kunde og administreres av bare én ansatt.

Hver ordre har også en eller flere elementer som representerer produkter som inneholder rekkefølgen og deres antall. Hvert linjeelement er en post i den **Ordredetaljer** enhet, som henter informasjon om hvert produkt fra den **bestille produkter** enhet. Hver detalj identifiserer bare ett produkt, men hvert produkt kan vises i flere detaljer. Derfor den **Ordredetaljer** enheten har en mange-til-én-relasjon med den **bestille produkter** enhet.

### <a name="one-to-many-relationships"></a>Én-til-mange-relasjoner

Hver ordre kan inneholde flere elementer, men hvert linjeelement er knyttet til bare ett Sorter. Derfor den **ordrer** enheten har en én-til-mange-relasjon med den **Ordredetaljer** enhet.

### <a name="dot-notation-for-relationships"></a>Prikk notasjon for relasjoner 

For å vise data som er basert på en relasjon mellom enheter, kan du bruke prikk egenskapen velgeren til å veilede på tvers av en relasjon fra én enhet til en annen.  For eksempel hver post i den **ordrer** enheten henter informasjon fra den **kunder** enhet slik at rekkefølgen galleriet kan vise kundenavn. I galleriet, konfigurerer du denne virkemåten ved å angi den **tekst** egenskapen for en etikett til dette uttrykket:<br>`ThisItem.Customer.Company`

**ThisItem** angir en post i den **ordrer** informasjon om enheten og trekkes fra den **kunder** enhet om kunden som la inn ordren. I dette tilfellet angir uttrykket at kundens firmanavn vises. Imidlertid trekkes hele posten for den aktuelle kunden ut, slik at du kan like enkelt viser, for eksempel en e-postadresse for denne kunden i stedet.

Som et annet eksempel på walking fra én enhet til en annen, kan du angi at en galleriet skal vise poster i én enhet som er basert på en post som brukeren har valgt i en annen galleriet, og som er i en annen enhet. Hvis du vil vise du bestillingsdetaljene, vil du angi detaljer galleriets **elementer** egenskapen til dette uttrykket:<br>`Gallery1.Selected.'Order Details'`

I dette tilfellet **Gallery1.Selected** angir en post i den **ordrer** enhet, akkurat som **ThisItem** gjorde i det forrige eksemplet. Dette uttrykket dra ikke imidlertid én post som gjorde det forrige uttrykket. I stedet de henter en hel tabell med poster å vise navnet og per enhet kostnaden for hvert produkt (i den **bestille produkter** enhet) og antallet (i den **Ordredetaljer** enhet).

## <a name="do-it-yourself"></a>Gjøre det selv

Du kan følge trinnvise instruksjoner for å lage Northwind ordrer-lerretsapp.  Instruksjonene består av tre deler:

1. [Opprett en ordre galleri](northwind-orders-canvas-part1.md).
1. [Opprette et sammendrag av skjema](northwind-orders-canvas-part2.md).
1. [Opprett et galleri i detalj](northwind-orders-canvas-part3.md).

Hvis du vil Hopp fremover, inneholder løsningen en startmappe app for hver del.  I listen over apper, ser du etter **Northwind ordrer (lerret) - begynne del 1** og så videre.

> [!div class="nextstepaction"]
> [Fortsett ved å opprette galleriet rekkefølge](northwind-orders-canvas-part1.md)
