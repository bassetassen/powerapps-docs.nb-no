---
title: Å importere eller eksportere data fra Common Data Service for apper
description: Ved hjelp av Get-Data fra Excel og Eksporter Data funksjonalitet på masseimport og eksportere data fra Excel- eller CSV-filer i enheter i Common Data Service (CDS) for apper
author: sabinn-msft
ms.service: powerapps
ms.topic: conceptual
ms.component: cds
ms.date: 05/14/2018
ms.author: sabinn
ms.openlocfilehash: 7f3e16be5bba1874759e0f9e40dc455f1e29c2bc
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/04/2018
ms.locfileid: "34697582"
---
# <a name="import-or-export-data-from-the-common-data-service-for-apps"></a>Å importere eller eksportere data fra Common Data Service for apper

Hvis du vil ha muligheten til å masseimportere og -eksportere data fra Excel- eller CSV-filer, kan du bruke Hent data fra Excel-filer og Eksporter data-funksjoner for oppdaterte Common Data Service (CDS) for apper-miljøer.

Det finnes to måter man kan importere filen til enheten på fra Excel- eller csv-filer

## <a name="option-1-import-by-creating-and-modifying-a-file-template"></a>Alternativ 1: Å importere ved å opprette og endre en filmal

Hver enhet har obligatoriske felt som må finnes i inndatafilen. For en mer sømløs tilnærming anbefaler vi at du oppretter en mal ved først å eksportere data fra enheten og bruke den samme filen (endret med dataene) til å importere data til enheten. Dette vil spare deg for tid og krefter versus det å måtte ta høyde for de påkrevde feltene for hver enhet.

1. Å klargjøre filmalen

    - Start ved å eksportere enhetsdata til en CSV-fil ved å følge trinnene under Eksportering av data til CSV
    - Angi en plan for å sikre at dataene er unike ved enten å bruke primærnøkler eller alternative nøkler.
    - Se inndelingen nedenfor om hvordan du sikrer unikhet før du importerer data til enheten

1. Å endre filen med dataene

    - Slik kopierer du data fra Excel- eller CSV-filen til malen du nettopp opprettet

1. Å importere filen
    - Utvid **Data**-delen på [powerapps.com](https://web.powerapps.com/), og trykk eller klikk på **Enheter** i venstre navigasjonsrute.
    - Velg enheten du vil importere data til
    - Klikk på ellipsen eller menyen øverst og velg **Hent data**, og klikk eller trykk på **Hent data fra Excel**

> [!NOTE]
> For å importere data til mer enn én enhet, velger du **Hent data** i menyen øverst, og deretter klikker eller trykker du på **Hent data fra Excel**. Du skal kunne velge flere enheter og trykke på **Neste**

![Eksempel på å importere data til kontoenhet](./media/data-platform-import-export/import-data-to-account.png)

- Dette fører deg til **Importer data**-skjermen der du kan velge å importere data via en Excel- eller CSV-fil
- Klikk eller trykk på **Last opp**
- Velg filen, og følg instruksjonene for å begynne å laste opp filen

![Eksempel på opplastingsfil til konto-enhet](./media/data-platform-import-export/upload-account.png)

- Når filen er lastet opp og tilordningsstatusen er grønn, klikker du på **Importer** øverst til høyre. Hvis det oppstår feil under tilordningen, kan du referere til inndelingen nedenfor for å navigere og løse feilene med tilordningen.

![Eksempel på vellykket tilordningsstatus og Importer-knappen](./media/data-platform-import-export/success-map-imp.png)

- Så snart **importen er gjennomført**, viser den deg alle innsettinger og oppdateringer

![Eksempel på vellykket import som viser antallet innsettinger og oppdateringer](./media/data-platform-import-export/success-imp-insert.png)

> [!NOTE]
> Vi bruker Upsert-logikk (oppdatering eller sett inn) til enten å oppdatere posten hvis den allerede finnes, eller til å sette inn en ny post.

## <a name="option-2-import-by-bringing-your-own-source-file"></a>Alternativ 2: Å importere ved å bruke din egen kildefil

Hvis du er en erfaren bruker og er godt kjent med de obligatoriske feltene for en gitt enhet for Common Data service for apper-enheten, kan du definere din egen Excel- eller CSV-kildefil og følge trinnene som er beskrevet under **Importer filen**

## <a name="navigating-mapping-errors"></a>Navigere tilordningsfeil

Hvis det oppstår tilordningsfeil, klikker du på **Tilordne status** etter du har lastet opp filen. Bruk deretter følgende fremgangsmåte til å kontrollere og rette opp felttilordningsfeil.

- Bruk rullegardinlisten nede til høyre under **Vis** til å gå gjennom **ikke-tilordnede felt**, **felt med feil** eller **obligatoriske felt**

> [!TIP]
> Avhengig av om du får en advarsel eller feil, kan du starte med å undersøke **ikke-tilordnede felt** eller **felt med feil** via rullegardinlisten i **felttilordninger**

![Eksempel på et delvis samsvar på grunn av advarsler med felttilordninger](./media/data-platform-import-export/partial-match.png)

![Eksempel på navigering av felttilordningsproblemer](./media/data-platform-import-export/navigate-mappings.png)

![ Eksempel på undersøkelser og korrigeringer av advarsler med felttilordninger](./media/data-platform-import-export/inspect-warnings.png)

- Når du har korrigert alle feil eller advarsler, klikker du på **Lagre endringer** øverst til høyre, som fører deg tilbake til **Importer data**-skjermen
- Så snart **tilordningstatus**-kolonnen angir **Fullført** i grønt, klikker du på **Importer** øverst til høyre
- Så snart du får meldingen om at **importen er gjennomført**, viser den deg alle innsettinger og oppdateringer

## <a name="ensuring-uniqueness-while-importing-data-into-entity-from-excel-or-csv"></a>Dette sikrer unikhet under import av data til enheter fra Excel eller CSV

Enheter for Common Data Service for apper bruker en primærnøkkel til å identifisere poster på en unik måte i en tabell for CDS-enheter. Primærnøkkelen for en CDS-enhet er en globalt unik identifikator (GUID) og danner standardgrunnlaget for post-identifikasjon. Dataoperasjoner som for eksempel importering av data til CDS-enheter vil vise til standard primærnøklene.

Eksempel: Primærnøkkelen for kontoenheten accountid

![Eksport av en eksempelfil fra konto-enhet som viser accountid som primærnøkkel](./media/data-platform-import-export/export-pk.png)

Noen ganger er kanskje ikke primærnøkkelen tilstrekkelig og/eller den imøtegår ikke gjeldende behov under integrering av data fra en ekstern kilde. I dette tilfellet lar CDS deg definere alternative nøkler som unikt identifiserer en post i stedet for den primære nøkkelen.

Eksempel: Du kan angi transactioncurrencyid som en alternativ nøkkel for konto-enhet ved hjelp av en naturlig nøkkelbasert ID (f.eks. bruke «Amerikanske dollar» i stedet for en GUID-verdi *88c6c893-5b45-e811-a953-000d3a33bcb9* vist ovenfor). Du kan også velge valutasymbol eller valutanavn som nøkler.

![Eksempel på å opprette alternativ nøkkel i valuta-enhet](./media/data-platform-import-export/create-ak.png)

![Eksporter eksempelfil fra konto-enhet som viser valutanavnet som naturlig nøkkel](./media/data-platform-import-export/export-nk.png)

Brukeren kan fortsatt bruke primærnøkler som identifikator når de har angitt alternative nøkler. Så i eksemplet ovenfor er den første filen fremdeles gyldig, og angitte GUIDer er gyldige data.

## <a name="export-data-to-csv"></a>Å eksportere data til CSV

Du kan gjøre en engangs dataeksport fra en standardenhet eller en egendefinert enhet, og du kan eksportere data fra mer enn én enhet om gangen. Hvis du eksporterer data fra mer enn én enhet, eksporteres hver enhet til sin egen Microsoft csv-fil.

1. Utvid **Data**-delen på [powerapps.com](https://web.powerapps.com/), og trykk eller klikk på **Enheter** i venstre navigasjonsrute.
1. Velg enheten du vil eksportere data fra
1. Klikk på ellipsen eller menyen øverst, og velg **Eksporter**, og klikk eller trykk på **Data**

    ![Eksempel på eksport av data fra konto-enhet](./media/data-platform-import-export/export-account.png)

    > [!NOTE]
    > Ved eksport av data fra flere enheter velger du **Eksporter** i den øverste menyen, og deretter klikker eller trykker du på **Data**. Du skal kunne velge flere enheter

1. Når eksporten er fullført, skal du kunne **laste ned eksporterte data** som skal vise deg en kobling til den nedlastbare CSV-filen

    ![Eksempel-eksport som viser en vellykket eksport med kobling til nedlastbar fil](./media/data-platform-import-export/export-success.png)

## <a name="unsupported-data-types"></a>Datatyper som ikke støttes

Følgende datatyper støttes ikke for øyeblikket

- Tidssone
- Flervalg av alternativsett
- Bilde
