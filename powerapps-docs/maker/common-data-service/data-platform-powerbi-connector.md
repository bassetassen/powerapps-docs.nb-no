---
title: Å opprette en PowerBI-rapport | Microsoft Docs
description: Koble til dataene fra PowerBI-skrivebordet ved hjelp av Common Data Service for apper-koblingen.
author: clwesene
manager: kfile
ms.service: powerapps
ms.component: cds
ms.topic: conceptual
ms.date: 05/21/2018
ms.author: clwesene
ms.openlocfilehash: bb0bec7cf459eb9084aea4db7264350b7913e578
ms.sourcegitcommit: 79b8842fb0f766a0476dae9a537a342c8d81d3b3
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 07/07/2018
ms.locfileid: "37898763"
---
# <a name="create-a-power-bi-report"></a>Opprette en Power BI-rapport
Common Data Service for apper lar deg koble deg direkte til dataene med Power BI Desktop for å opprette rapporter og publisere dem til Power BI. Fra Power BI kan rapporter brukes i instrumentbord, deles med andre brukere og fås tilgang til på tvers av plattformer i Power BI-apper for mobilenheter.

![Power BI Desktop](./media/data-platform-cds-powerbi-connector/PBIDesktop.png "Power BI Desktop")

## <a name="prerequisites"></a>Forutsetninger

Hvis du vil bruke Power BI med Common Data Service for apper, trenger du følgende:

* Last ned og installer Power BI Desktop, som er et gratis program som kjører på den lokale datamaskinen. Du kan laste ned Power BI Desktop [her](https://powerbi.microsoft.com/desktop/).
* Common Data Service for apper-miljøet med opprettertillatelse til å få tilgang til portalen og lese tillatelsene for å få tilgang til data i enheter.

## <a name="finding-your-common-data-service-for-apps-environment-url"></a>Slik finner du nettadressen for miljøet til Common Data Service for apper

1. Åpne [PowerApps](https://web.powerapps.com), og velg miljøet du har tenkt å koble til. Klikk deretter på **tannhjulet for innstillinger** øverst til høyre og klikk på **Avanserte tilpasninger**

    ![CDS for apper-miljøet](./media/data-platform-cds-powerbi-connector/CDSEnv1.png "CDS for apper-miljøet")

2. Klikk på **Ressurser** under inndelingen Ressurser for utviklere, dette vil åpne en ny fane.

    ![CDS for apper-miljøet](./media/data-platform-cds-powerbi-connector/CDSEnv2.png "CDS for apper-miljøet")

3. Kopier roten av nettadressen i den nye fanen, dette er den unike nettadressen for miljøet ditt. Nettadressen vil være i formatet **https://yourenvironmentid.crm.dynamics.com/** – sørg for at du ikke kopierer resten av nettadressen. Behold dette på et nyttig sted slik at du kan bruke det når du oppretter en PowerBI-rapport.

    ![CDS for apper-miljøet](./media/data-platform-cds-powerbi-connector/CDSEnv3.png "CDS for apper-miljøet")

## <a name="connecting-to-common-data-service-for-apps-from-power-bi-desktop"></a>Å koble til Common Data Service for apper fra Power BI Desktop

1. Start **Power BI Desktop**. Hvis det er første gang, kan det være at du får opp en velkomstskjerm eller blir tatt direkte til et tomt lerret – uansett så klikker du på **Hent data** og velger **Mer** for å åpne den fullstendige listen over datakilder som er tilgjengelige for Power BI Desktop.

    ![Power BI Desktop](./media/data-platform-cds-powerbi-connector/CreateReport1.png "Power BI Desktop")

2. Klikk på **Elektroniske tjenester** og **Common Data Service for apper (beta)** fra listen over koblinger. Klikk på **Koble til**.

    ![Power BI Desktop](./media/data-platform-cds-powerbi-connector/CreateReport2.png "Power BI Desktop")

3. Lim inn **nettadresse for miljøet til Common Data Service for apper** i **nettadresse for server**-feltet, og klikk på **OK**. Hvis dette er første gang, blir du bedt om å logge på med samme legitimasjon som du bruker til å koble til PowerApps og Common Data Service for apper.

    ![Power BI Desktop](./media/data-platform-cds-powerbi-connector/CreateReport3.png "Power BI Desktop")

4. Navigatøren viser deg alle enheter som er tilgjengelige for ditt miljø, gruppert i tre mapper. Utvid **Common Data Model**-mappen.

   * Common Data Model – dette er standardenheter som er ofte brukt og som er tilgjengelig i alle miljøer som en del av Common Data Model.
   * Egendefinerte enheter – er enheter som du har opprettet eller importert i miljøet ditt.
   * System – inneholder alle enheter i miljøet, inkludert Common Data Model og Egendefinerte enheter.

     ![Power BI Desktop](./media/data-platform-cds-powerbi-connector/CreateReport4.png "Power BI Desktop")

5. Velg **Konto**-enheten for å se en forhåndsvisning av dataene i den høyre ruten, og klikk på **Last inn**.

    ![Power BI Desktop](./media/data-platform-cds-powerbi-connector/CreateReport5.png "Power BI Desktop")

6. Enheten er nå lastet inn i rapporten, og du kan begynne å bygge rapporter. Eller du kan gjenta denne prosessen for å legge til flere enheter.

    ![Power BI Desktop](./media/data-platform-cds-powerbi-connector/CreateReport6.png "Power BI Desktop")

7. Klikk på **Navn**-feltet i Felt-ruten for å legge til en ny visualisering på rapportlerretet. Nå kan du gjenta denne prosessen og endre visualiseringer for å bygge en rapport.

    ![Power BI Desktop](./media/data-platform-cds-powerbi-connector/CreateReport7.png "Power BI Desktop")


## <a name="using-option-sets"></a>Å bruke alternativsettene

Alternativsett brukes i enheter for å vise en rullegardinliste med verdier til en bruker i apper og flyter. Når Power BI-koblingen brukes, presenteres alternativsett-felt som to kolonner, som viser både den unike verdien og visningsverdien.

Hvis du eksempelvis hadde et alternativsett på enheten kalt ApprovalStatus, ville du se to felt i Power BI:

* ApprovalStatus – dette vil vise en unik heltallsverdi for hvert element i alternativsettet. Dette er til hjelp når det benyttes filtre, slik at de ikke blir påvirket hvis du gjør fremtidige endringer for visningsnavnet.
* ApprovalStatus_display – dette viser det egendefinerte visningsnavnet for elementet og brukes vanligvis når du presenterer alternativet i en tabell eller et diagram.

    |ApproalStatus|ApprovalStatus_Display|
    |---------|---------|
    1|Sendt inn
    2|I gjennomgang
    3|Godkjent
    4|Avvist

## <a name="navigating-relationships"></a>Å navigere relasjoner

Relasjoner i Common Data Service for apper krever at du oppretter en relasjon i Power BI Desktop mellom de to enhetene ved hjelp av et GUID-felt. Dette er en systemgenerert, unik identifikator som sikrer at relasjoner er opprettet for opprettelsespostene der hvor tvetydighet eller duplisering kan foreligge med andre felt. Du kan lese mer om administrasjon av relasjoner i Power BI Desktop [her](https://docs.microsoft.com/power-bi/desktop-create-and-manage-relationships).

Mens noen relasjoner kan opprettes automatisk, kan du fortsatt se gjennom og sikre at riktige relasjonene opprettes når du oppretter rapporten:

* Oppslagsfeltet i enheten inneholder GUID-en for oppføringen i den relaterte enheten.
* Den relaterte enheten vil ha et felt i formatet «[EntityName]id» som inneholder GUID-en, for eksempel Accountid eller MyCustomEntityid
* Ved å bruke funksjonen Behandle relasjoner, kan du opprette en ny relasjon mellom oppslagsfeltet og ID-feltet for den relaterte enheten.


## <a name="next-steps"></a>Neste trinn
* [Administrer felter i en enhet](data-platform-manage-fields.md)
* [Definer relasjoner mellom enheter](data-platform-entity-lookup.md)


