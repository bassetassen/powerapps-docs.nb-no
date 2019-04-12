---
title: Opprette en PowerBI-rapport | Microsoft Docs
description: Koble til dataene fra PowerBI Desktop ved hjelp av Common Data Service.
author: lancedMicrosoft
manager: kfile
ms.service: powerapps
ms.component: cds
ms.topic: conceptual
ms.date: 05/21/2018
ms.author: lanced
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="create-a-power-bi-report"></a>Opprett en Power BI-rapport
Med Common Data Service kan du koble direkte til dataene dine med Power BI Desktop for å opprette rapporter og publisere dem til Power BI. Fra Power BI kan rapporter brukes i instrumentbordene, deles med andre brukere og åpnes på tvers av plattformer i Power BI-mobilapper.

![Power BI Desktop](./media/data-platform-cds-powerbi-connector/PBIDesktop.png "Power BI Desktop")

## <a name="prerequisites"></a>Forhåndskrav

Hvis du vil bruke Power BI med Common Data Service, trenger du følgende:

* Last ned og installer Power BI Desktop, som er et gratis program som kjører på den lokale datamaskinen. Du kan laste ned Power BI Desktop [her](https://powerbi.microsoft.com/desktop/).
* Common Data Service-miljøet med beslutningstakertillatelser for å få tilgang til portalen lesetillatelser for å få tilgang til data i enheter.

## <a name="finding-your-common-data-service-environment-url"></a>Finne URL-adressen for Common Data Service-miljøet

1. Åpne [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc), velg miljøet du skal koble deg til, klikk på **innstillingstannhjulet** i øvre høyre hjørne, og klikk på **Avanserte tilpassinger**

    ![Common Data Service-miljø](./media/data-platform-cds-powerbi-connector/CDSEnv1.png "Common Data Service-miljø")

2. Klikk **Ressurser** under Utviklerressurser-delen, noe som vil åpne en ny kategori.

    ![Common Data Service-miljø](./media/data-platform-cds-powerbi-connector/CDSEnv2.png "Common Data Service-miljø")

3. Kopier roten til URL-adressen i den nye fanen, som er den unike URL-adressen for miljøet. URL-adressen skal være i formatet **https://yourenvironmentid.crm.dynamics.com/**. Pass på at du ikke kopierer resten av URL-adressen. Holde dette et sted praktisk slik at du kan bruke den når du oppretter PowerBI-rapporten.

    > [!div class="mx-imgBorder"] 
    > ![Common Data Service-miljø](./media/data-platform-cds-powerbi-connector/CDSEnv3.png "Common Data Service-miljø")

## <a name="connecting-to-common-data-service-from-power-bi-desktop"></a>Koble til Common Data Service fra Power BI Desktop

1. Start **Power BI Desktop**. Hvis det er første gang, kan det vises en velkomstskjerm, eller du blir tatt rett til et tomt lerret – uansett klikker du **Hent Data** og velger **Mer** for å åpne den fullstendige listen over datakilder tilgjengelig for Power BI Desktop.

    ![Power BI Desktop](./media/data-platform-cds-powerbi-connector/CreateReport1.png "Power BI Desktop")

2. Klikk **Online Services** og **Common Data Service (Beta)** fra listen over kontakter. Klikk **Koble til**.

    ![Power BI Desktop](./media/data-platform-cds-powerbi-connector/CreateReport2.png "Power BI Desktop")

3. Lim inn **URL-adressen for Common Data Service** i feltet **URL-adresse for server**, og klikk **OK**. Hvis dette er første gang, blir du bedt om å logge på med den samme legitimasjonen som du bruker til å koble til PowerApps og Common Data Service.

    ![Power BI Desktop](./media/data-platform-cds-powerbi-connector/CreateReport3.png "Power BI Desktop")

4. Navigatøren viser alle enheter som er tilgjengelige for miljøet ditt, gruppert i tre mapper. Utvid mappen **Common Data Model**.

    * Common Data Model – dette er standardenheter som vanligvis brukes. og som er tilgjengelige i alle miljøer som en del av Common Data Model.
    * Egendefinerte enheter – er enheter som du har opprettet eller importert i organisasjonen.
    * System – inneholder alle enheter i miljøet, inkludert Common Data Model og egendefinerte enheter.

    ![Power BI Desktop](./media/data-platform-cds-powerbi-connector/CreateReport4.png "Power BI Desktop")

5. Velg **Forretningsforbindelse**-enheten for å vise en forhåndsvisning av dataene i ruten til høyre, og klikk **Last**.

    ![Power BI Desktop](./media/data-platform-cds-powerbi-connector/CreateReport5.png "Power BI Desktop")

6. Enheten lastes nå inn i rapporten, og du kan begynne å bygge rapporter eller gjenta dette for å legge til flere enheter.

    ![Power BI Desktop](./media/data-platform-cds-powerbi-connector/CreateReport6.png "Power BI Desktop")

7. Klikk **Navn**-feltet i panelet for å legge til en visualisering på rapportlerretet. Du kan nå gjenta denne prosessen og endre visualiseringer for å bygge rapporten.

    ![Power BI Desktop](./media/data-platform-cds-powerbi-connector/CreateReport7.png "Power BI Desktop")


## <a name="using-option-sets"></a>Bruke alternativsett

Alternativsett brukes i enheter til å gi en bruker en rullegardinliste med verdier i apper og flyter. Når du bruker alternativsettett for Power BI-kontakten, vises felt som to kolonner for å vise både den unike verdien og visningsverdien.

Hvis du for eksempel har et alternativsett for enheten som kalles ApprovalStatus, vil du se to felt i Power BI:

* ApprovalStatus – dette viser en unik heltallsverdi for hver vare i alternativsettet. Dette er nyttig når du bruker filtre, slik at de ikke blir berørt hvis du gjør endringer i visningsnavnet senere.
* ApprovalStatus_display – dette viser det egendefinerte visningsnavnet for elementet og brukes vanligvis når presenterer alternativet i en tabell eller et diagram.

    |ApprovalStatus|ApprovalStatus_Display|
    |---------|---------|
    1|Innsendt
    2|Til gjennomgang
    3|Godkjent
    4|Avslått

## <a name="navigating-relationships"></a>Navigere i relasjoner

Relasjoner i Common Data Service krever at du oppretter en relasjon i PowerBI Desktop mellom de to enhetene ved hjelp av et GUID-felt. Dette er en systemgenerert unik ID som sørger for at relasjoner opprettes for opprettetede oppføringer der tvetydighet eller duplisering kan forekome med andre felt. Du kan les mer om behandling av relasjoner i Power BI Desktop [her](https://docs.microsoft.com/power-bi/desktop-create-and-manage-relationships).

Mens enkelte relasjoner kan opprettes automatisk, kan du fortsatt se gjennom og sikre at de riktige relasjonene opprettes når du oppretter rapporten:

* Oppslagsfelt for enheten inneholder GUID-en til oppføringen i den relaterte enheten.
* Den relaterte enheten har et felt i formatet "[EntityName]id, som inneholder GUID-en, for eksempel Accountid eller MyCustomEntityid.
* Ved hjelp av funksjonen for å behandle relasjoner i PowerBI Desktop kan du opprette en ny relasjon mellom oppslagsfeltet og ID-feltet i den relaterte enheten.


## <a name="next-steps"></a>Neste trinn
* [Administrere felt i en enhet](data-platform-manage-fields.md)
* [Definere relasjoner mellom enheter](data-platform-entity-lookup.md)


