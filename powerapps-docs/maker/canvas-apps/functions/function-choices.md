---
title: Choices-funksjonen | Microsoft Docs
description: Referanseinformasjon, inkludert syntaks, for Choices-funksjonen i PowerApps
author: gregli-msft
ms.service: powerapps
ms.topic: reference
ms.component: canvas
ms.date: 06/15/2018
ms.author: gregli
ms.openlocfilehash: ec39a9970c2135e9cf4633f8266d9b2980d8cd9b
ms.sourcegitcommit: 79b8842fb0f766a0476dae9a537a342c8d81d3b3
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 07/07/2018
ms.locfileid: "37895964"
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

Du kan på dette tidspunktet bruke oppslagskolonner bare med SharePoint og Common Data Service for Apps.

## <a name="syntax"></a>Syntaks
**Choices**( *column-reference* )

* *column-reference* – obligatorisk.  En oppslagskolonne for en datakilde. Ikke omslutt kolonnenavnet i doble anførselstegn. Referansen må være direkte til kolonnen i datakilden, og kan ikke gå gjennom en funksjon eller kontroll.

## <a name="examples"></a>Eksempler

#### <a name="choices-for-a-lookup"></a>Valg for et oppslag

1. [Opprett en database](../../../administrator/create-database.md) i Common Data Service for Apps, og velg boksen **Inkluder eksempelapper og -data**.

    Mange enheter, som **Kontoer**, opprettes.

    **Obs!** Enhetsnavn er i entall på web.powerapps.com og flertall i PowerApps Studio.

    ![En delvis liste over felter fra Konto-enheten i Commmon Data Service for Apps, som uthever at Hovedkontakt er et oppslagsfelt](media/function-choices/entity-account.png)

    **Kontoer**-enheten har en **Hovedkontakt**-kolonne, som er et oppslag for **Kontakter**-enheten.  

    ![En delvis liste over felter fra Kontakt-enheten i Commmon Data Service](media/function-choices/entity-contact.png)

    En kontaktperson er angitt som hovedkontakt for hver konto, eller hovedkontakt er *tom*.

2. [Generere en app](../data-platform-create-app.md) fra **Kontoer**-enheten.

3. I listen over skjermer og kontroller nær venstre kant kan du bla ned til **EditScreen1** vises, og deretter velge **EditForm1** like under.

    ![Velg EditForm1 på EditScreen1 i navigasjonsfeltet til venstre](media/function-choices/select-editform.png)

4. Velg **Kontoer** på **Egenskaper**-fanen i ruten til høyre.

    ![Velg Kontoer for å åpne Data-ruten](media/function-choices/open-data-pane.png)

5. Bla ned til listen over felter i **Data**-ruten.

    ![Velg Kontoer for å åpne Data-ruten](media/function-choices/field-list.png)

6. Finn avmerkingsboksen **Hovedkontakt**, og merk den av hvis merket er fjernet.

7. (valgfritt) Dra **Hovedkontakt**-feltet fra bunnen til toppen av listen over felter.

8. Velg **Kombinasjonsboks**-kontrollen i kortet for **Hovedkontakt**.

    **Elementer**-egenskapen til den kontrollen er angitt til én av to formler basert på tilstanden til avmerkingsboksen **Bruk kolonnevisningsnavn** i Avanserte innstillinger.

   - Hvis det merkes av for dette, angis egenskapen til denne formelen:<br>**Choices( Accounts.'Primary Contact' )**
   - Hvis merket fjernes for dette, angis egenskapen til denne formelen:<br>**Choices( Accounts.primarycontactid )**

     ![En lerretskjerm med en Skjema-kontroll. **Kombinasjonsboks**-kontrollen i **Hovedkontakt**-kortet blir valgt, og Elementer-egenskapen med formelen Choices( Accounts.'Primary Contact' ) vises](media/function-choices/accounts-primary-contact.png)

9. Velg **Ny skjerm**, og velg deretter **Tom** på **Hjem**-fanen.

10. Velg **Datatabell** på **Sett inn**-fanen.

11. Angi **Elementer**-egenskapen til **Datatabell**-kontrollen til én av disse formlene:

     - Hvis avmerkingsboksen **Bruk kolonnevisningsnavn** i Avanserte innstillinger er valgt, bruker du denne formelen:<br>**Choices( Accounts.'Primary Contact' )**
     - Ellers kan du bruke denne formelen:<br>**Choices( Accounts.primarycontactid )**

12. Åpne **Data**-ruten, og merk deretter av for **fornavn**, **etternavn**, eller hvilket som helst felt du ønsker å vise.

     ![En lerretskjerm med en Datatabell-kontroll. Elementer-egenskapen er angitt til formelen Choices( Accounts.'Primary Contact' ), og tabellen viser fornavn- og etternavn-kolonnene for det første settet med poster fra Kontakter-enheten](media/function-choices/full-accounts-pc.png)