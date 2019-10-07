---
title: Choices-funksjonen | Microsoft Docs
description: Referanseinformasjon, inkludert syntaks, for Choices-funksjonen i PowerApps
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 06/15/2018
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 8ac88e1b9e81b9c42c8c9ac187d569573fc10ac3
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/07/2019
ms.locfileid: "71992972"
---
# <a name="choices-function-in-powerapps"></a>Choices-funksjonen i PowerApps
Returnerer en tabell med de mulige verdiene for en oppslagskolonne.

## <a name="description"></a>Beskrivelse
**Choices**-funksjonen returnerer en tabell med de mulige verdiene for en oppslagskolonne.  

Bruk **Choices**-funksjonen for å vise en liste over valg som brukeren kan velge fra. Denne funksjonen brukes ofte med [**Kombinasjonsboks**](../controls/control-combo-box.md)-kontrollen i redigeringsskjemaer.

For et oppslag: tabellen som **Choices** returnerer samsvarer med den sekundære tabellen som er tilknyttet med oppslaget. Ved å legge til **Choices** eliminerer du behovet for å legge til en sekundær tabell som en ekstra datakilde. **Choices** returnerer alle kolonnene i den sekundære tabellen.

Siden **Choices** returnerer en tabell, kan du bruke [**Filter**](function-filter-lookup.md), [**Sort**](function-sort.md), [**AddColumns**](function-table-shaping.md) og alle de andre tabellmanipuleringsfunksjonene til å filtrere, sortere og forme tabellen. 

Du kan ikke [delegere](../delegation-overview.md) **Choices** for øyeblikket. Hvis denne begrensningen blir et problem i appen, kan du legge til den sekundære enheten som en datakilde og bruke den direkte. 

**Choices** krever ikke at kolonnenavnene må være strenger og omsluttet av doble anførselstegn, i motsetning til [**ShowColumns**](function-table-shaping.md), [**Search**](function-filter-lookup.md) og andre tabellfunksjoner. Angi formelen som om du henviste til kolonnen direkte.

Kolonnereferanser må være direkte til datakilden. Hvis datakilden er for eksempel **Kontoer** og oppslaget er **SLA**, blir kolonnereferansen **Accounts.SLA**. Referansen kan ikke gå gjennom en funksjon, variabel eller kontroll. Hvis **Kontoer** i tillegg mates til en **Galleri**-kontroll, bruker du formelen **Gallery.Selected.SLA** for å henvise til den utvalgte kontoen. Denne referansen har imidlertid gått gjennom en kontroll, så den kan ikke sendes til **Columns**-funksjonen – du må fremdeles bruke **Accounts.SLA**.

På dette tidspunktet kan du bare bruke oppslags Kol onner med SharePoint og Common Data Service.

## <a name="syntax"></a>Syntaks
**Choices**( *column-reference* )

* *column-reference* – obligatorisk.  En oppslagskolonne for en datakilde. Ikke omslutt kolonnenavnet i doble anførselstegn. Referansen må være direkte til kolonnen i datakilden, og kan ikke gå gjennom en funksjon eller kontroll.

## <a name="examples"></a>Eksempler

#### <a name="choices-for-a-lookup"></a>Valg for et oppslag

1. [Opprett en database](../../../administrator/create-database.md) i Common data service, og velg **eksempler-apper og data** Box.

    Mange enheter, som **Kontoer**, opprettes.

    **Obs!** Enhets navn er en tall på web.powerapps.com og flertall i PowerApps Studio.

    ![En ufullstendig liste over feltene fra kontoen heten i Common Data Service for apper, som uthever at «primær kontakt» er et oppslags felt](media/function-choices/entity-account.png)

    **Kontoer**-enheten har en **Hovedkontakt**-kolonne, som er et oppslag for **Kontakter**-enheten.  

    ![En ufullstendig liste over feltene fra kontakt-enheten i Common Data Service](media/function-choices/entity-contact.png)

    En kontaktperson er angitt som hovedkontakt for hver konto, eller hovedkontakt er *tom*.

1. [Generere en app](../data-platform-create-app.md) fra **Kontoer**-enheten.

1. I listen over skjermer og kontroller nær venstre kant kan du bla ned til **EditScreen1** vises, og deretter velge **EditForm1** like under.

    ![Velg EditForm1 på EditScreen1 i navigasjonsfeltet til venstre](media/function-choices/select-editform.png)

1. Velg **Rediger felt**på **Egenskaper** -fanen i ruten til høyre.

    ![Åpne data-ruten](media/function-choices/open-data-pane.png)

1. Velg **Legg til felt**i **felt** -ruten.

1. Søk etter feltet for **primær kontakt** , Merk avmerkings boksen, og velg deretter **Legg til**.

    ![Velg Kontoer for å åpne Data-ruten](media/function-choices/field-list.png)

    Det **primære kontakt** feltet vises nederst i skjemaet. Hvis feltet viser en feil, velger du **data kilder** på **Vis** -fanen, velger ellipsen (...) for **kontoer** -datakilden, og deretter velger du **Oppdater**.

1. (valgfritt) Dra **Hovedkontakt**-feltet fra bunnen til toppen av listen over felter.

1. Velg **Kombinasjonsboks**-kontrollen i kortet for **Hovedkontakt**.

    **Element** -egenskapen for kontrollen er satt til en formel som identifiserer kolonnen med visnings navnet, som i det første eksemplet eller det logiske navnet, som i det andre eksemplet:

   - **Choices( Accounts.'Primary Contact' )**
   - **Choices( Accounts.primarycontactid )**

     ![En lerretskjerm med en Skjema-kontroll. Kombinasjons boks kontrollen i det primære kontakt kortet er valgt, og elementer-egenskapen med formel valg (kontoer. primær kontakt) vises](media/function-choices/accounts-primary-contact.png)

1. Velg **Ny skjerm**, og velg deretter **Tom** på **Hjem**-fanen.

1. Velg **Datatabell** på **Sett inn**-fanen.

1. Angi **elementer** -egenskapen for **data tabell** -kontrollen til denne formelen:

     **Choices( Accounts.'Primary Contact' )**

1. I midten av **data tabell** -kontrollen velger du koblingen som begynner å **velge feltene...** , og deretter merker du av for feltet eller feltene du vil vise (for eksempel for **navn** og **etter navn**).

     ![En lerretskjerm med en Datatabell-kontroll. Elementer-egenskapen er angitt til formelen Choices( Accounts.'Primary Contact' ), og tabellen viser fornavn- og etternavn-kolonnene for det første settet med poster fra Kontakter-enheten](media/function-choices/full-accounts-pc.png)