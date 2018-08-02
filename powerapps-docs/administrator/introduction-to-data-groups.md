---
title: Datagrupper | Microsoft Docs
description: Gjennomgang av hvordan du bruker datagrupper i PowerApps.
author: manasmams
manager: kvivek
ms.service: powerapps
ms.component: pa-admin
ms.topic: conceptual
ms.date: 03/21/2018
ms.author: manasma
ms.openlocfilehash: 6a6217c0a344d0501c8a856b0632397044ceb465
ms.sourcegitcommit: 2e7b621066cdc3e7be329d5213ecfee0b4223641
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 07/30/2018
ms.locfileid: "39349643"
---
# <a name="data-groups"></a>Datagrupper
Med datagrupper kan du enkelt kategorisere tjenester i en [policy for hindring av datatap (DLP)](prevent-data-loss.md). De to tilgjengelige datagruppene er gruppene **Bare forretningsdata** og **Ingen forretningsdata er tillatt**. Organisasjoner kan selv bestemme hvilke tjenester de plasserer i en bestemt datagruppe. En god måte å kategorisere tjenester på, er å plassere dem i grupper, basert på innvirkningen på organisasjonen. Alle tjenester plasseres i datagruppen **Ingen forretningsdata er tillatt** som standard. Du administrerer tjenestene i en datagruppe når du oppretter eller endrer egenskapene til en DLP-policy fra administrasjonssenteret.

## <a name="how-data-is-shared-between-data-groups"></a>Slik deles data mellom datagrupper
Data kan ikke deles blant tjenester som befinner seg i ulike grupper. Hvis du for eksempel plasserer SharePoint og Salesforce i **Bare forretningsdata**-gruppen og du plasserer Facebook og Twitter i **Ingen forretningsdata er tillatt**-gruppen, kan du ikke opprette en PowerApp som flytter data mellom SharePoint og Facebook. Mens data ikke kan deles blant tjenestene som befinner seg i ulike grupper, kan du dele data blant tjenestene i en bestemt gruppe. Hvis vi ser på det tidligere eksemplet der SharePoint og Salesforce ble plassert i samme datagruppe, kan PowerApps som sluttbrukerne oppretter, dele data mellom SharePoint og Salesforce. Det viktigste punktet er at tjenestene i en bestemt gruppe kan dele data, mens tjenester i ulike grupper ikke kan dele data.

Én datagruppe må i tillegg angis som *standard*-gruppen. I utgangspunktet er gruppen **Ingen forretningsdata er tillatt** *standardgruppen*, og alle tjenestene befinner seg i datagruppen. En administrator kan endre standarddatagruppe til **Bare forretningsdata**-datagruppen. 

> [!NOTE]
> Eventuelle nye tjenester som legges til i PowerApps plasseres i den angitte *standard*-gruppen. På grunn av dette anbefaler vi at du beholder **Ingen forretningsdata er tillatt** som standardgruppe, og legger til tjenester i **Bare forretningsdata**-gruppen manuelt, etter at organisasjonen har evaluert innvirkningen av at forretningsdata kan deles med den nye tjenesten.

## <a name="add-services-to-a-data-group"></a>Å legge til tjenester i en datagruppe
I denne gjennomgangen legger vi til SharePoint og Salesforce i **Bare forretningsdata**-datagruppen for en DLP-policy.

1. Velg **+ Legg til**-koblingen fra **Bare forretningsdata**-gruppeboksen for en DLP-policy:    
   ![Å legge til bilde](./media/introduction-to-data-groups/add-to-data-group-1.png)  
2. Velg SharePoint og Salesforce, velg deretter **Legg til tjenester** for å legge til begge tjenestene i Bare forretningsdata-gruppen:    
   ![Et bilde av Legg til tjenester](./media/introduction-to-data-groups/add-to-data-group-2.png)  
3. Velg **Lagre policy** fra menyen øverst:  
   ![Lagre policy](./media/introduction-to-data-groups/add-to-data-group-4.png)
4. Legg merke til at både SharePoint og Salesforce befinner seg i Bare forretningsdata-gruppen:  
   ![oppdatert forretningsdata-gruppe](./media/introduction-to-data-groups/add-to-data-group-3.png)   

I denne gjennomgangen har du lagt til SharePoint og Salesforce i **Bare forretningsdata**-datagruppen for en DLP-policy. Hvis én person som er en del av DLP-policyens miljø oppretter en app som deler data mellom SharePoint eller Salesforce og eventuelle tjenester i datagruppen **Ingen forretningsdata er tillatt**, har ikke appen lov til å kjøre.

## <a name="remove-services-from-a-data-group"></a>Å fjerne tjenester fra en datagruppe
Siden alle tjenester må befinne seg i én av de tilgjengelige datagruppene, må du legge til tjenesten i en annen gruppe og deretter lagre policyen, hvis du vil fjerne en tjeneste fra en bestemt gruppe.  

## <a name="change-the-default-data-group"></a>Endring av standarddatagruppen
I denne gjennomgangen endrer vi standarddatagruppe fra **Ingen forretningsdata er tillatt** til **Bare forretningsdata**.  

> [!IMPORTANT]
> Eventuelle nye tjenester som legges til i PowerApps plasseres i den angitte *standard*-gruppen. På grunn av dette anbefaler vi at du beholder **Ingen forretningsdata er tillatt** som standardgruppe, og legger til tjenester i **Bare forretningsdata**-gruppen manuelt.

1. Velg **...** som du finner øverst til høyre i datagruppen du ønsker å angi som standard datagruppe:    
   ![å endre standardgruppe](./media/introduction-to-data-groups/default-data-group-0.png)  
2. Velg **Angi som standardgruppe**:  
   ![å endre standardgruppe](./media/introduction-to-data-groups/default-data-group-1.png)   
3. Velg **Lagre policy** fra menyen øverst:  
   ![å endre standardgruppe](./media/introduction-to-data-groups/add-to-data-group-4.png)
4. Vær oppmerksom på at datagruppen nå er angitt som standard datagruppe:  
   ![å endre standardgruppe](./media/introduction-to-data-groups/default-data-group-2.png)   

## <a name="next-steps"></a>Neste trinn
* [Å finne ut mer om policyer for hindring av datatap](prevent-data-loss.md)
* [Å finne ut mer om miljøer](environments-overview.md)
* [Å finne ut mer om Microsoft PowerApps](../maker/canvas-apps/getting-started.md)
