---
title: Oversikt over Power BI-tilkoblingen | Microsoft Docs
description: Å se tilgjengelige Power BI-tilkoblinger
author: lancedMicrosoft
ms.service: powerapps
ms.topic: reference
ms.component: canvas
ms.date: 10/12/2016
ms.author: lanced
ms.openlocfilehash: a3a5d24efffd7cd3c9430cafd5050dc96632ee76
ms.sourcegitcommit: 7354a0c61578fcc0b9965bf557b9d7c553c73e96
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/05/2018
ms.locfileid: "34803171"
---
# <a name="connect-to-power-bi-from-powerapps"></a>Å koble til Power BI fra PowerApps
![strøm~~POS=TRUNC BI](./media/connection-powerbi/powerbiicon.png)

Power BI er en verktøyserie for forretningsanalyse som kan brukes til å analysere data og dele innsikter. Overvåk bedriften din og få svar raskt med avanserte instrumentbord tilgjengelig på alle enheter. I appen din kan du kontrollere statusen for datavarsler som du har satt opp i Power BI-tjenesten. Hvis du vil ha mer informasjon om datavarsler i Power BI, kan du gå til [dokumentasjonssiden](https://https://docs.microsoft.com/power-bi/service-set-data-alerts).

Dette emnet viser deg hvordan du bruker Power BI-tilkoblingen i en app, og lister opp de tilgjengelige funksjonene.

## <a name="prerequisites"></a>Forutsetninger
* [Registrer deg](https://web.powerapps.com)
* Å legge til Power BI-[tilkobling](https://powerapps.microsoft.com/tutorials/add-manage-connections/)
* Opprett en app fra en [mal](https://powerapps.microsoft.com/tutorials/get-started-test-drive/), fra [data](https://powerapps.microsoft.com/tutorials/get-started-create-from-data/) eller fra [grunnen av](https://powerapps.microsoft.com/tutorials/get-started-create-from-blank/)

## <a name="use-the-power-bi-connection-in-your-app"></a>Å bruke Power BI-tilkobling i appen
### <a name="list-the-alerts-that-youve-set-up-in-the-power-bi-service"></a>Å vise varsler du har satt opp i Power BI-tjenesten
1. Velg **Galleri** på **Sett inn**-menyen, og legg til noen av **tekstgalleriene**.
2. Hvis du vil vise varslene for den gjeldende brukeren, angir du galleriets [Elementer](../controls/properties-core.md)-egenskap til følgende formel:
   
   `PowerBI.GetAlerts()`

Galleriet oppdateres med listen over varsler. For hvert varsel får du varselnavnet, ID-nummer for varselet, og ID-en til gruppens arbeidsområde hvor varselet ble konfigurert. Du trenger ID-en for varselet for å få mer informasjon om det.

### <a name="view-the-status-of-an-alert"></a>Å vise statusen for et varsel
Hvis du vil vise statusen for varselet, kan du benytte deg av funksjonen CheckAlertStatus med varsel-ID-en som er hentet fra trinnet ovenfor.

Varsel-ID-en kan brukes enten som en litteral streng (f.eks. "1234") eller som en referanse til en galleridel som er fylt ut ved hjelp av GetAlerts()-oppkalling (f.eks. Gallery1.Selected.alertId)

Legg til en etikett og angi [Tekst](../controls/properties-core.md)-egenskapen dens til én av disse formlene:

* `PowerBI.CheckAlertStatus( /* alert ID that you received from GetAlert */ ).alertTitle`
* `PowerBI.CheckAlertStatus( /* alert ID that you received from GetAlert */ ).currentTileValue`
* `PowerBI.CheckAlertStatus( /* alert ID that you received from GetAlert */ ).alertThreshold`
* `PowerBI.CheckAlertStatus( /* alert ID that you received from GetAlert */ ).isAlertTriggered`

Etiketten oppdateres med gjeldende status for varselet.

## <a name="view-the-available-functions"></a>Å vise de tilgjengelige funksjonene
Denne tilkoblingen har følgende funksjoner:

| Funksjonsnavn | Beskrivelse |
| --- | --- |
| GetAlerts |Å vise varsler du har satt opp i Power BI-tjenesten |
| CheckAlertStatus |Å kontrollere statusen for en bestemt varsling |

## <a name="getalerts"></a>GetAlerts
Vis varsler som du har satt opp i Power BI-tjenesten.

#### <a name="input-properties"></a>Inndataegenskaper
Ingen.

#### <a name="output-properties"></a>Utdataegenskaper
| Egenskapsnavn | Datatype | Kreves | Beskrivelse |
| --- | --- | --- | --- |
| verdi |matrise |Nei |En matrise for datavarslene som du har satt opp i Power BI-tjenesten. Hvert element i matrisen inkluderer: <ul><li>alertTitle: tittel på varslingen</li><li>alertTitle: ID-en for varslingen</li><li>groupId: ID-en for gruppen som varselet ble opprettet i</li></ul> |

## <a name="checkalertstatus"></a>CheckAlertStatus
Vise statusen for et varsel.

> [!NOTE]
> Forespørsler til dette endepunktet blir begrenset på basis av hvert enkelt varsel hvis det benyttes for hyppig.

#### <a name="input-properties"></a>Inndataegenskaper
| Egenskapsnavn | Datatype | Kreves | Beskrivelse |
| --- | --- | --- | --- |
| alertId |heltall |Ja |ID-en for varselet, slik det er returnert av GetAlerts |

#### <a name="output-properties"></a>Utdataegenskaper
| Egenskapsnavn | Datatype | Kreves | Beskrivelse |
| --- | --- | --- | --- |
| tileValue |tall |Nei |Verdien for flisen når varselet ble utløst |
| tileUrl |streng |Nei |Nettadressen for flisen som har varselet |
| alertTitle |streng |Nei |Navn på varselet |
| isAlertTriggered |boolsk |Nei |Om varselet utløses for øyeblikket |
| alertThreshold |tall |Nei |Terskelen varselet utløses ved |

## <a name="helpful-links"></a>Nyttige koblinger
Se alle [tilgjengelige tilkoblinger](../connections-list.md).  
Finn ut hvordan du [legger til tilkoblinger](../add-manage-connections.md) i appene dine.

