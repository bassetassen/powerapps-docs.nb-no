---
title: Importere eller eksportere data fra Common Data Service for Apps
description: Masseimportere og -eksportere data fra Excel- eller CSV-filer til enheter i Common Data Service for Apps ved hjelp av Hent data fra Excel- og Eksporter data-funksjonaliteten
author: sabinn-msft
ms.service: powerapps
ms.topic: conceptual
ms.component: cds
ms.date: 05/14/2018
ms.author: sabinn
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="import-or-export-data-from-common-data-service-for-apps"></a>Importere eller eksportere data fra Common Data Service for Apps

Hvis du vil masseimportere og -eksportere data fra Microsoft Excel- eller CSV-filer, bruker du Hent data fra Excel-fil og Eksporter data-funksjonene for oppdaterte Common Data Service for Apps-miljøer.

Det er to måter du kan importere filer til enheter på fra Excel- eller CSV-filer.

## <a name="option-1-import-by-creating-and-modifying-a-file-template"></a>Alternativ 1: Importer ved å opprette og endre en filmal

Hver enhet har obligatoriske felt som må finnes i inndatafilen din. Vi anbefaler at du oppretter en mal. Først eksporterer du data fra enheten. Bruk samme fil (endret med dataene dine) for å importere data til enheten. Denne malen sparer tid og anstrengelser. Du trenger ikke ta hensyn til de obligatoriske feltene for hver enhet.

1. Klargjør filmalen.

    a. Eksporter enhetsdataene til CSV-filen. Følg fremgangsmåten i **Eksporter data til CSV**.  
    b. Definer en plan for å kontrollere at dataene er unike. Bruk **hovednøkler** eller **alternative nøkler**.  
    c. Se delen nedenfor for instruksjoner om hvordan du kontrollerer at data er unike før du importerer dem til en enhet. 

1. Endre filen med dataene.

    - Kopier data fra Excel- eller CSV-filen til malen du nettopp opprettet.

1. Importer filen.  
    a. På [powerapps.com](https://web.powerapps.com/) utvider du **Data**-delen. Velg **Enheter** i venstre navigasjonsrute.  
    b. Velg enheten du vil importere data til.  
    c. Velg ellipsen eller menyen øverst. Velg **Hent data**. Velg **Hent data fra Excel**.  

    > [!NOTE]
    > Hvis du vil importere data til mer enn én enhet, velger du **Hent Data** på den øverste menyen. Velg **Hent data fra Excel**. Deretter kan du velge flere enheter og velge **Neste**.

    > [!div class="mx-imgBorder"] 
    > ![Eksempel på import av data til en **Forretningsforbindelse**-enhet](./media/data-platform-import-export/import-data-to-account.png)

    d. I **Importer data**-skjermbildet velger du om du vil importere data fra en Excel- eller CSV-fil.  
    e. Velg **Last opp**.  
    f. Velg filen din. Følg instruksjonene for å laste opp filen.  

    > [!div class="mx-imgBorder"] 
    > ![Eksempel på opplasting av en fil til en **Forretningsforbindelse**-enhet](./media/data-platform-import-export/upload-account.png)

    g. Når filen er lastet opp og **Tilordningsstatus** er grønn, velger du **Importer** i det øvre høyre hjørnet. Se neste del for å navigere og rette opp tilordningsfeil.  

    > [!div class="mx-imgBorder"] 
    > ![Eksempel på vellykket **Tilordningsstatus** og **Importer**-knappen](./media/data-platform-import-export/success-map-imp.png)

    h. Når importen er fullført, kan du se totalt antall innsettinger og oppdateringer.  

    > [!div class="mx-imgBorder"] 
    > ![Eksempel på vellykket import som viser antall innsettinger og oppdateringer](./media/data-platform-import-export/success-imp-insert.png)

    > [!NOTE]
    > Bruk Upsert-logikken (oppdater og sett inn) for å oppdatere oppføringen hvis den allerede finnes, eller for å sette inn en ny oppføring.

## <a name="option-2-import-by-bringing-your-own-source-file"></a>Alternativ 2: Importer ved å hente din egen kildefil

Hvis du er en erfaren bruker og kjenner til de obligatoriske feltene for en gitt enhet for Common Data Service for Apps-enheter, kan du definere din egen Excel- eller CSV-kildefil. Følg fremgangsmåten i **Importer filen**.

## <a name="navigate-mapping-errors"></a>Navigere i tilordningsfeil

Hvis du får tilordningsfeil når du har lastet opp filen, velger du **Tilordningsstatus**. Gjør følgende for å undersøke og rette opp felttilordningsfeilene.

1. Bruk rullegardinmenyen til høyre under **Vis** for å gå gjennom **Felt som ikke er tilordnet**, **Felt med feil** eller **Obligatoriske felt**.

    > [!TIP]
    > Avhengig av om du får en advarsel eller feil, kan du undersøke **Felt som ikke er tilordnet** eller **Felt med feil** via rullegardinmenyen i **Felttilordninger**.

    > [!div class="mx-imgBorder"] 
    > ![Eksempel på delvis samsvar på grunn av advarsler med felttilordninger](./media/data-platform-import-export/partial-match.png)

    > [!div class="mx-imgBorder"] 
    > ![Eksempel på navigering i felttilordningsfeil](./media/data-platform-import-export/navigate-mappings.png)

    > [!div class="mx-imgBorder"] 
    > ![Eksempel på å undersøke og korrigere advarsler med felttilordninger](./media/data-platform-import-export/inspect-warnings.png)

2. Når du har løst alle feil og advarsler, velger du **Lagre endringer** i det øvre høyre hjørnet. Du går tilbake til **Importer data**-skjermbildet.
3. Når **Tilordningsstatus**-kolonnen viser **Fullført** i grønt, velger du **Importer** i det øvre høyre hjørnet.
4. Når du får meldingen **Importen ble fullført**, viser den totalt antall innsettinger og oppdateringer.

## <a name="ensure-uniqueness-when-you-import-data-into-an-entity-from-excel-or-csv"></a>Sikre unikhet når du importerer data til en enhet fra Excel eller CSV

Common Data Service for Apps-enheter bruker en primærnøkkel for å entydig identifisere oppføringer i en Common Data Service-enhetstabell. Primærnøkkelen for en Common Data Service-enhet er en globalt unik identifikator (GUID). Den er standardgrunnlag for identifikasjon av oppføringer. Dataoperasjoner som import av data til Common Data Service-enheter viser standard primærnøkler.

Eksempel:  
Primærnøkkelen for en **Forretningsforbindelse**-enhet er **accountid**.

   > [!div class="mx-imgBorder"] 
   > ![Eksempeleksportfil fra en **Forretningsforbindelse**-enhet som viser **accountid** som primærnøkkel](./media/data-platform-import-export/export-pk.png)

Noen ganger kan det hende at en primærnøkkel ikke fungerer når du integrerer data fra en ekstern kilde. Bruk Common Data Service for å definere alternative nøkler som unikt identifiserer en oppføring i stedet for primærnøkkelen.

Eksempel:  
For en **Forretningsforbindelse**-enhet kan du angi **transactioncurrencyid** som alternativ nøkkel ved hjelp av naturlig nøkkelbasert identifikasjon. Bruk for eksempel **Amerikanske dollar** i stedet for GUID-verdien **88c6c893-5b45-e811-a953-000d3a33bcb9** som ble vist tidligere. Du kan også velge **valutasymbol** eller **valutanavn** som nøkler.

   > [!div class="mx-imgBorder"] 
   > ![Eksempel på oppretting av en alternativ nøkkel i en **Valuta**-enhet](./media/data-platform-import-export/create-ak.png)

   > [!div class="mx-imgBorder"] 
   > ![Eksempeleksportfil fra en **Forretningsforbindelse**-enhet som viser **valutanavn** som naturlig nøkkel](./media/data-platform-import-export/export-nk.png)

Brukere kan fortsatt bruke primærnøkler som identifikatorer etter de har angitt alternative nøkler. I det foregående eksemplet er den første filen fortsatt gyldig hvis GUID-er er gyldige data.

## <a name="export-data-to-csv"></a>Eksporter data til CSV

Du kan utføre en engangs dataeksport fra en standardenhet eller egendefinert enhet. Og du kan eksportere data fra flere enheter om gangen. Hvis du eksporterer data fra flere enheter, eksporteres hver enhet til sin egen Microsoft CSV-fil.

1. På [powerapps.com](https://web.powerapps.com/) utvider du **Data**-delen. Velg **Enheter** i venstre navigasjonsrute.
1. Velg enheten du vil eksportere data fra.
1. Velg ellipsen eller menyen øverst. Velg **Eksporter**. Velg **Data**.

    > [!div class="mx-imgBorder"] 
    > ![Eksempel på eksport av data fra en **Forretningsforbindelse**-enhet](./media/data-platform-import-export/export-account.png)

    > [!NOTE]
    > Hvis du vil eksportere data fra flere enheter, velger du **Eksporter** på den øverste menyen. Velg **Data**. Du kan velge flere enheter.

1. Når eksporten er fullført, kan du **Last ned eksporterte data**. Denne nedlastingen gir deg en kobling til den nedlastbare CSV-filen.

    > [!div class="mx-imgBorder"] 
    > ![Eksempeleksport som viser vellykket eksport med kobling til nedlastbar fil](./media/data-platform-import-export/export-success.png)

## <a name="unsupported-data-types"></a>Datatyper som ikke støttes

Følgende datatyper støttes ikke for øyeblikket.

- Tidssone
- Alternativsett med flere valg
- Bilde
