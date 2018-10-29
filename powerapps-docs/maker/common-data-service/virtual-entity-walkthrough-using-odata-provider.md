---
title: Gjennomgang av virtuelle enheter ved hjelp av dataleverandøren for OData i Common Data Service for Apps | MicrosoftDocs
description: Lær hvordan du bruker dataleverandøren for OData v4 med en virtuell enhet
ms.custom: ''
ms.date: 06/04/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
ms.assetid: ''
caps.latest.revision: 11
author: Mattp123
ms.author: matp
manager: kvivek
ms.openlocfilehash: ebdd8f80aad2d353d017626b7c403da93803c19b
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/08/2018
ms.locfileid: "39691595"
---
# <a name="virtual-entity-walkthrough-using-the-odata-v4-data-provider"></a>Gjennomgang av virtuelle enheter ved hjelp av OData v4 Data Provider

Tenk deg at du ønsker tilgang til billett-informasjon fra en ekstern datakilde i den modelldrevne appen eller Serviceområdet for Dynamics 365 for Customer Engagement. I denne enkle gjennomgangen skal du utforme en virtuell enhet, med felter som er tilordnet det eksterne XML-skjemaet som henter billett-data under kjøring fra en OData-nettjeneste.

## <a name="data-source-details"></a>Datakildedetaljer

Fordi datakilden som brukes i denne gjennomgangen har en OData v4-nettjeneste, kan vi bruke OData v4 Data Provider inkludert med miljøet ditt.

Nettadresse for nettjeneste: `http://contosowebservice.azurewebsites.net/odata/` 

> [!IMPORTANT]
> Nettadressen til nettjenesten som er brukt for denne gjennomgangen er ikke en fungerende nettjeneste.

Én virtuell enhet som inneholder følgende tre felter er nødvendig for denne gjennomgangen.

|Navn på eksternt felt |Ekstern datatype |Datatype for virtuell enhet |Formål |
|---------|---------|---------|---------|
|TicketID |`Edm.Guid` |Primærnøkkel |Primærnøkkelen for enheten |
|Tittel  |`Edm.String` |Enkeltlinje med tekst |Tittel på billett |
|Alvorsgrad |`Edm.Int32`| Heltall |Nummerverdien for 0–4 som angir alvorlighetsgraden av billetten |

OData-metadataene for den eksterne billettenheten for datakilden:

```xml
<EntityType Name="Ticket">
  <Key>
    <PropertyRef Name="TicketID" />
  </Key>
  <Property Name="TicketID" Nullable="false" Type="Edm.Guid" />
  <Property Name="Title" Type="Edm.String" />
  <Property Name="Severity" Nullable="false" Type="Edm.Int32" />
</EntityType>
```

## <a name="create-the-data-source"></a>Opprett datakilden

Opprett datakilden for dataleverandøren for OData v4 som bruker eksempel på nettjenesten for OASIS Data Protocol (OData).

1. Gå til **Innstillinger** > **Administrasjon** > **Datakilder for virtuell enhet**.
1. Velg **NY**, og velg **OData v4 Data Provider**, og velg deretter **OK**.
1. Skriv inn eller velg følgende informasjon.

    |Felt|Verdi|
    |--|--|
    |**Navn**|Eksempel for Contoso-datakilde|
    |**Nettadresse**|`http://contosowebservice.azurewebsites.net/odata` |
    |**Tidsavbrudd**|30|
    |**Returner innebygd antall**|Sann|

La de andre feltene stå som de er, og velg **LAGRE OG LUKK**.

> [!TIP]
> Når du bruker egen nettjeneste, må du kontrollere at nettadressen er gyldig ved å lime den inn i nettleseren. 

## <a name="open-solution-explorer"></a>Åpne løsningutforsker

En del av navnet til alle enheter du oppretter, er tilpassingsprefikset. Dette angis basert på løsningutgiveren for løsningen du arbeider i. Hvis du er opptatt av tilpassingsprefikset, må du kontrollere at du jobber i en uadministrert løsning, der tilpassingsprefikset er det du vil ha for denne enheten. Mer informasjon: [Endre prefiks for løsningutgiver](change-solution-publisher-prefix.md) 

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]


## <a name="create-the-virtual-entity"></a>Opprett den virtuelle enheten

1. Velg **Enheter**, og velg deretter **Ny** fra hovedruten i venstre navigasjonsrute i løsningsutforsker.
2. Velg **Virtuell enhet** på **Enhet: Ny**-skjemaet, og skriv deretter inn følgende informasjon: 

    |Felt|Verdi|
    |--|--|
    |**Datakilde**|Eksempel for Contoso-datakilde|
    |**Visningsnavn**|Billett|
    |**Flertallsnavn**|Billetter|
    |**Navn**|new_ticket|
    |**Eksternt navn**|Billett|
    |**Navn på ekstern samling**|Billetter|
    |**Notater (inkludert vedlegg)**|valgt|
    |**Aktiviteter**|valgt|

1. Velg **Tjeneste** ved siden av **Områder som viser denne enheten**, og velg deretter **Lagre** (men ikke lukk enhetsskjemaet).
    ![Enhetsdefinisjon for billett](media/ticket-entity.png)

## <a name="create-the-fields-for-the-virtual-entity"></a>Opprett feltene for den virtuelle enheten

Velg **Felter** i den venstre navigasjonsruten for **Enhet: Billett**. Som en del av denne gjennomgangen, vil du redigere to eksisterende felt og legge til et tredje felt.

> [!IMPORTANT]
> Eksterne navn skiller mellom store og små bokstaver. Henvend deg til metadataene for nettjenesten for å kontrollere at du bruker riktig navn.
> En verdi som kan nullstilles til usann indikerer at attributtet er nødvendig. Legg merke til at primærnøkkelfeltene alltid er nødvendige for systemet.

1. Åpne **new_ticketid**-feltet, og endre følgende attributt med verdien som er angitt her: **Eksternt navn**: TicketID ![TicketID-felt](media/ticketid-field.png)
1. Velg **Lagre og lukk**.
1. Åpne **new_name**-feltet, og endre følgende attributter til å ha verdiene som er angitt her:
    - **Visningsnavn**: Tittel
    - **Eksternt navn**: Tittel ![Tittelfelt](media/title-field.png)
1. Velg **Lagre og lukk**.
1. Velg **Ny**, og angi følgende informasjon på **Felt: Ny for billett**-siden:

    |Felt|Verdi|
    |--|--|
    |**Visningsnavn**|Alvorsgrad|
    |**Navn**|new_severity|
    |**Eksternt navn**|Alvorsgrad|
    |**Feltkrav**|Nødvendig for bedrift|
    |**Datatype**|Heltall|
    |**Minimumsverdi**|0|
    |**Maksimumsverdi**|4|

  ![Felt for alvorlighetsgrad](media/severity-field.png)
1. Velg **Lagre og lukk**.

## <a name="add-the-fields-to-the-main-form"></a>Legg til feltene i hovedskjemaet

1. Velg **Skjemaer** på vinduet for billettenheten.
1. Åpne hovedskjemaet, dra og slipp **Alvorlighetsgrad**-feltet fra den høyre ruten til skjemaet i **Generelt**-inndelingen, under **Tittel**-feltet. 
    ![Feltet for alvorlighetsgrad er lagt til i hovedskjemaet](media/drop-severity-field.png)
1. Velg **Lagre og lukk** på vinduet for billettenheten.

## <a name="configure-the-default-view"></a>Konfigurere standardvisningen

1. Velg **Visninger** under **Billettenhet** på den venstre ruten i løsningsutforsker.
1. Åpne visningen **Alle henvendelser**.
1. Velg **Legg til kolonner** i **Vanlige oppgaver**-ruten.
    ![Legg til kolonner for visning](media/addcolumns.png)
1. Velg **Alvorlighetsgrad**, og velg deretter **OK**.
1. Velg **Lagre og lukk** på **Vis: Alle billetter**-vinduet.
1. Velg **Publiser alle tilpassinger** i vinduet for løsningsutforskeren.
    ![Publiser alle tilpassinger](media/publishall.png)
1. Lukk vinduet for løsningsutforskeren når alle tilpassinger er publisert.

## <a name="view-the-virtual-entity-in-action-with-dynamics-365-customer-engagement"></a>Vis den virtuelle enheten i praksis med Dynamics 365 Customer Engagement

1. Gå til **Tjeneste** > **Utvidelser** > **Billetter**.
    
    ![Billettområde](media/ticket-area.png)

    Visningsskjermer for **Alle billetter**. Legg merke til at du kanskje må oppdatere nettleseren for å vise enheten fra **Tjeneste**-området.

    ![Alle billetter-visning](media/all-tickets-view.png)
1. Åpne en **Billett**-post for å vise skjemaet som inkluderer feltene for **Tittel** og **Alvorlighetsgrad** for den angitte posten.
    ![Billettpost](media/ticket-record.png)

### <a name="see-also"></a>Se også

[Konfigurasjon, krav og anbefalte fremgangsmåter for OData v4 Data Provider](virtual-entity-odata-provider-requirements.md)<br />
[Opprett og rediger virtuelle enheter som inneholder data fra en ekstern datakilde](create-edit-virtual-entities.md)
