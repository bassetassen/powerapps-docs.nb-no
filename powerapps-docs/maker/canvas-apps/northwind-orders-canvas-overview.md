---
title: Oversikt over lerret-appen for Gas tro nor delikat Esser | Microsoft Docs
description: ''
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 05/17/2019
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 48966659ca12ada12448543492731fff8431fbde
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/07/2019
ms.locfileid: "71995827"
---
# <a name="overview-of-the-canvas-app-for-northwind-traders"></a>Oversikt over lerret-appen for Gas tro nor delikat Esser

Finn ut mer om lerret-appen for å administrere Relasjons data i Gastronor-delikat Esser-databasen som du [installerte i miljøet ditt](northwind-install.md). Deretter følger du trinn vise instruksjoner i etterfølgende emner for å bygge denne appen fra grunnen av, slik at du får praktisk erfaring med å arbeide med relasjonelle data.

Oppdag følgende i dette emnet:

- Hvordan en app-bruker viser og administrerer relasjonelle data i appen.
- Hvilke typer data driver appen.
- Hvordan relasjoner mellom disse data typene ble opprettet.

I en enkelt skjerm kan app-brukeren vise, oppdatere, opprette og slette ordrer.

> [!div class="mx-imgBorder"]
> ![Complete for lerret @ no__t-1

## <a name="explore-the-user-interface"></a>Utforsk bruker grensesnittet

### <a name="order-gallery"></a>Rekkefølge galleri

På venstre kant av appen viser et galleri en liste over ordrer, inkludert ordre nummer, status, navn på kunden og total kostnaden for ordren. Brukeren kan bla gjennom listen for å finne en ordre, og deretter vise mer informasjon om den ved å velge pilen for ordren. Mer informasjon: [Opprett ordre galleriet](northwind-orders-canvas-part1.md).

### <a name="summary-form"></a>Sammendrags skjema

I øvre høyre hjørne summeres rekkefølgen som brukeren valgte i rekkefølge-galleriet. Sammendraget inneholder mye av den samme informasjonen som galleriet gjør, men sammendraget viser også datoene da ordren ble opprettet og betalt, i tillegg til navnet og bildet til den ansatte som behandlet ordren. Brukeren kan endre dataene i skjemaet, lagre disse endringene, avbryte dem eller slette rekkefølgen ved å velge et ikon nær høyre kant av tittel linjen. Mer informasjon: [Opprett sammendrags skjemaet](northwind-orders-canvas-part2.md).

### <a name="detail-gallery"></a>Detalj galleri

I hjørnet nederst til høyre viser et annet galleri informasjon om hvilke produkter den valgte ordren inneholder, og i hvilket antall. Hvert element i dette galleriet er kjent som en ordre detaljer. App-brukeren kan legge til og slette et hvilket som helst element i galleriet ved hjelp av kontrollene i og under det. Mer informasjon: [Opprett detalj galleriet](northwind-orders-canvas-part3.md).

> [!div class="mx-imgBorder"]
> @no__t – 0Definition av skjerm områder @ no__t-1

## <a name="explore-the-data-sources"></a>Utforsk data kildene

Hvis du vil opprette denne appen, viser du data fra fem enheter og et alternativ sett. Faktisk viser de fleste områder i denne appen data fra flere enheter. Rekkefølge galleriet inneholder for eksempel denne informasjonen:

- Ordre nummeret er et felt i **Orders** -enheten.
- Statusen er et annet felt i **Orders** -enheten, et alternativ fra alternativet **ordre status** angitt.
- Kunde navnet er et felt i **kunder** -enheten.
- Total kostnaden beregnes basert på data i **ordre detaljer** enheten.

Sammendraget inneholder noe av den samme informasjonen som listen over ordrer, men den inneholder også navnet og bildet til den ansatte som behandlet ordren. Denne informasjonen hentes fra feltene i **ansatte** -enheten. Detalj galleriet viser poster i **ordre detaljer** enheten, og hvert produkt i disse detaljene er en post i **ordrens produkt** enhet.

## <a name="explore-the-relationships"></a>Utforsk relasjonene

Du kan vise data fra ulike kilder (for eksempel enheter) i samme galleri eller skjema, fordi disse enhetene har relasjoner som ble opprettet for deg i databasen.

### <a name="many-to-one-relationships"></a>Mange-til-én-relasjoner

Det finnes for eksempel informasjon om kunden og den ansatte for hver ordre i enheter for **kunder** og **ansatte** . **Ordrer** -enheten har derfor mange-til-én-relasjoner med disse enhetene, fordi det finnes mange ordrer, og hver av dem kan bare plasseres av én kunde og bare administreres av én ansatt.

Hver ordre har også én eller flere linje elementer som representerer produktene som ordren inneholder og antallet. Hvert linje element er en post i **Order detaljer** -enheten, som henter informasjon om hvert produkt fra enheten **for ordre produkter** . Hver detalj identifiserer bare ett produkt, men hvert produkt kan forekomme i flere detaljer. Derfor har **ordre detaljer** enheten en mange-til-én-relasjon med **ordrens produkt** enheter.

### <a name="one-to-many-relationships"></a>Én-til-mange-relasjoner

Hver ordre kan inneholde flere linje elementer, men hvert linje element er knyttet til bare én ordre. Derfor har **Orders** -enheten en én-til-mange-relasjon med **Order detaljer** -enheten.

### <a name="dot-notation-for-relationships"></a>Punktnotasjon for relasjoner 

Hvis du vil vise data basert på en relasjon mellom enheter, kan du bruke egenskaps velgeren dot til å gå gjennom en relasjon fra én enhet til en annen.  Hver post i **Orders** -enheten henter for eksempel informasjon fra **kunder** -enheten, slik at ordre galleriet kan vise kunde navnene. I dette galleriet konfigurerer du denne virke måten ved å angi **tekst** -egenskapen for en etikett til dette uttrykket:<br>`ThisItem.Customer.Company`

**ThisItem** angir en post i **Orders** -enheten og henter informasjon fra **kunder** -enheten om kunden som la inn ordren. I dette tilfellet angir uttrykket at kundens firma navn vises. Hele posten for denne kunden blir imidlertid trukket, så du kan enkelt vise for eksempel en e-postadresse for kunden i stedet.

Som et annet eksempel på å gå fra én enhet til en annen, kan du angi at et galleri skal vise poster i én enhet basert på en post som brukeren valgte i et annet galleri, og som er i en annen enhet. Hvis du vil vise ordre detaljene, kan du angi **element** -egenskapen for detalj galleriet til dette uttrykket:<br>`Gallery1.Selected.'Order Details'`

I dette tilfellet angir **Gallery1. selected** en post i **Orders** -enheten, akkurat som **ThisItem** i det forrige eksemplet. Dette uttrykket henter imidlertid bare én post som forrige uttrykk. Den henter i stedet en hel tabell med poster for å vise navn og per enhet for hvert produkt (som gjenspeiles i **ordre produkter** -enheten) og antallet (som gjenspeiles i **ordre detaljer** enheten).

## <a name="do-it-yourself"></a>Gjør det selv

Du kan følge trinn vise instruksjoner for å opprette lerret-appen for Gastronor-ordrer.  Instruksjonene er delt inn i tre deler:

1. [Opprett et ordre Galleri](northwind-orders-canvas-part1.md).
1. [Opprett et sammendrags skjema](northwind-orders-canvas-part2.md).
1. [Opprett et detalj Galleri](northwind-orders-canvas-part3.md).

Hvis du vil hoppe over, inneholder løsningen en start-og-punkt-app for hver del.  Se etter **Gas tro nor orders (lerret) i listen over apper – Start del 1** og så videre.

> [!div class="nextstepaction"]
> [Fortsett ved å opprette ordre galleriet](northwind-orders-canvas-part1.md)
