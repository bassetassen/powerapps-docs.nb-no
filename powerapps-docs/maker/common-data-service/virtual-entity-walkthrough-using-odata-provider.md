---
title: Gjennomgang av den virtuelle enheten med OData-dataleverandøren i Common Data Service | MicrosoftDocs
description: Finn ut hvordan du bruker OData v4-dataleverandøren med en virtuell enhet
ms.custom: ''
ms.date: 06/04/2018
ms.reviewer: ''
ms.service: powerapps
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
ms.assetid: null
caps.latest.revision: 11
author: Mattp123
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="virtual-entity-walkthrough-using-the-odata-v4-data-provider"></a>Virtuelle gjennomgang av enheter ved hjelp av OData v4-dataleverandøren

Tenk deg at du vil ha tilgang til billettinformasjon fra en ekstern datakilde i den modelldrevne appen eller i Service-området for Dynamics 365 for Customer Engagement. I denne enkle gjennomgangen skal du modellere en virtuell enhet med felt tilordnet til det eksterne skjemaet som mottar billettdata ved kjøretid fra en OData-webtjeneste.

## <a name="data-source-details"></a>Datakildedetaljer

Fordi datakilden som brukes for denne gjennomgangen, har en OData v4-webtjeneste, kan vi bruke OData v4-dataleverandøren som er inkludert i miljøet ditt.

URL-adresse for webtjeneste: `http://contosowebservice.azurewebsites.net/odata/` 

> [!IMPORTANT]
> Webtjeneste-URL-en som brukes for denne gjennomgang, er ikke en webtjeneste som fungerer.

For denne gjennomgangen er det nødvendig med en enkelt virtuell enhet som inneholder følgende tre felt.

|Navn på eksternt felt |Type eksterne data |Datatype for virtuell enhet |Hensikt |
|---------|---------|---------|---------|
|Billett-ID |`Edm.Guid` |Primærnøkkel |Primærnøkkel for enheten |
|Tittel  |`Edm.String` |En enkelt linje med tekst |Billettens tittel |
|Alvorlighetsgrad |`Edm.Int32`| Heltall |Tallverdi fra 0 til 4, som angir alvorligshetsgraden til billetten |

OData-metadataene for den eksterne datadatakildens billettenhet:

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

## <a name="create-the-data-source"></a>Opprette datakilden

Opprett datakilden for OData v4-dataleverandøren som bruker OASIS Open Data-protokollen (OData) eksempelwebtjenesten.

1. Gå til **Innstillinger** > **Administrasjon** > **Datakilder for virtuelle enheter**.
1. Velg **NY**, velg **OData v4-dataleverandør**, og velg deretter **OK**.
1. Angi eller velg følgende informasjon.

    |Felt|Verdi|
    |--|--|
    |**Navn**|Contoso eksempeldatakilde|
    |**URL-adresse**|`http://contosowebservice.azurewebsites.net/odata` |
    |**Tidsavbrudd**|30|
    |**Returner innebygd antall**|Sann|

La de andre feltene være, og velg **LAGRE OG LUKK**.

> [!TIP]
> Når du bruker din egen webtjeneste, må du kontrollere at URL-adressen er gyldig ved å lime den inn i webleseren. 

## <a name="open-solution-explorer"></a>Åpne løsningsutforskeren

En del av navnet på egendefinerte enheter du oppretter, er tilpassingsprefikset. Dette angis basert på løsningsutgiveren for løsningen du arbeider i. Hvis du er interessert i tilpassingsprefikset, må du kontrollere at du arbeider i en ikke-administrert løsning der tilpassingsprefikset er det du vil bruke for denne enheten. Mer informasjon: [Endre løsningsutgiverprefikset](change-solution-publisher-prefix.md) 

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]


## <a name="create-the-virtual-entity"></a>Opprette den virtuelle enheten

1. Velg **Enheter** i den venstre navigasjonsruten i løsningsutforskeren, og velg deretter **Ny** fra hovedruten.
2. På skjemaet **Enhet: Ny** velger du **Virtuell enhet**, og deretter angir du følgende informasjon: 

    |Felt|Verdi|
    |--|--|
    |**Datakilde**|Contoso eksempeldatakilde|
    |**Visningsnavn**|Billett|
    |**Flertallsnavn**|Billetter|
    |**Navn**|new_ticket|
    |**Eksternt navn**|Billett|
    |**Navn på ekstern samling**|Billetter|
    |**Notater (inkludert vedlegg)**|valgt|
    |**Aktiviteter**|valgt|

1. Ved siden av **Områder som viser denne enheten** velger du **Service** og deretter **Lagre** (men ikke lukk enhetsskjemaet).
    ![Enhetsdefinisjon for billett](media/ticket-entity.png)

## <a name="create-the-fields-for-the-virtual-entity"></a>Opprett feltene for den virtuelle enheten

I den venstre navigasjonsruten på siden **Enhet: Billett** velger du **Felt**. Som en del av denne gjennomgangen skal du redigere to eksisterende felt og legge til et tredje felt.

> [!IMPORTANT]
> Det skilles mellom små og store bokstaver i eksterne navn. Se metadataene for webtjenesten for å sørge for at du bruker riktig navn.
> En usann verdi som kan nullstilles, angir at attributtet er nødvendig. Vær oppmerksom på at primærnøkkelfelt alltid er nødvendig for systemet.

1. Åpne feltet **new_ticketid**, og endre følgende attributt med verdien angitt her: **Eksternt navn**: Billett-ID ![Feltet Billett-ID](media/ticketid-field.png)
1. Velg **Lagre og lukk**.
1. Åpne feltet **new_name**, og endre følgende attributter med verdiene angitt her:
    - **Visningsnavn**: Tittel
    - **Eksternt navn**: Tittel ![Tittel-feltet](media/title-field.png)
1. Velg **Lagre og lukk**.
1. Velg **Ny**, og på siden **Felt: Ny for billett** angir du følgende informasjon:

    |Felt|Verdi|
    |--|--|
    |**Visningsnavn**|Alvorlighetsgrad|
    |**Navn**|new_severity|
    |**Eksternt navn**|Alvorlighetsgrad|
    |**Feltkrav**|Nødvendig for selskapet|
    |**Datatype**|Heltall|
    |**Minimumsverdi**|0|
    |**Maksimumsverdi**|4|

  ![Feltet Alvorlighetsgrad](media/severity-field.png)
1. Velg **Lagre og lukk**.

## <a name="add-the-fields-to-the-main-form"></a>Legge til feltene i hovedskjemaet

1. I vinduet Billettenhet velger du **Skjemaer**.
1. Åpne hovedskjemaet, dra og slipp feltet **Alvorlighetsgrad** fra den høyre ruten og ned på skjemaet i **Generelt**-delen under **Tittel**-feltet. 
    ![Alvorlighetsgrad-feltet legges til i hovedskjemaet](media/drop-severity-field.png)
1. I vinduet Billettenhet velger du **Lagre og lukk**.

## <a name="configure-the-default-view"></a>Konfigurere standardvisning

1. I den venstre ruten i løsningsutforskeren, under **Billettenhet**, velger du **Visninger**.
1. Åpne visningen **Alle billetter**.
1. I ruten **Vanlige oppgaver** velger du **Legg til kolonner**.
    ![Legg til kolonner for visning](media/addcolumns.png)
1. Velg **Alvorlighetsgrad** og deretter **OK**.
1. I vinduet **Visning: Alle billetter** velger du **Lagre og lukk**.
1. Klikk **Publiser alle tilpassinger** i løsningsutforskervinduet.
    ![Publiser alle tilpassinger](media/publishall.png)
1. Lukk løsningsutforskervinduet når alle tilpassinger er publisert.

## <a name="view-the-virtual-entity-in-action-with-dynamics-365-customer-engagement"></a>Vise den virtuelle enheten i aksjon med Dynamics 365 Customer Engagement

1. Gå til **Service** > **Utvidelser** > **Billetter**.
    
    ![Billett-området](media/ticket-area.png)

    Visningen **Alle billetter** vises. Legg merke til at må du kanskje oppdatere nettleseren for å vise enheten fra **Service**-området.

    ![Visningen Alle billetter](media/all-tickets-view.png)
1. Åpne en **Billett**-oppføring for å vise et skjema som inkluderer feltene **Tittel** og **Alvorlighetsgrad** for en bestemt oppføring.
    ![Billett-oppføring](media/ticket-record.png)

### <a name="see-also"></a>Se også

[Konfigurasjon av, krav for og anbefalte fremgangsmåter for OData v4-dataleverandøren](virtual-entity-odata-provider-requirements.md)<br />
[Opprette og redigere virtuelle enheter som inneholder data fra en ekstern datakilde](create-edit-virtual-entities.md)
