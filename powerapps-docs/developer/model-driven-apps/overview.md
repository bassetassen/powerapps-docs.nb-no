---
title: Modelldrevne apper – Oversikt for utviklere | Microsoft Docs
description: Finn ut hvordan utviklere kan utvikle verdifulle modelldrevne apper.
services: ''
suite: powerapps
documentationcenter: na
author: JimDaly
manager: faisalmo
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/17/2018
ms.author: jdaly
search.audienceType:
- developer
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: 39fe83cdb059e0f1df634b9933f4a2f4251bca7b
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/24/2018
ms.locfileid: "42852418"
---
# <a name="model-driven-apps-developer-overview"></a>Modelldrevne apper – Oversikt for utviklere

PowerApps tilbyr firmaer, partnere, uavhengige programvareleverandører og systemintegratorer en kraftig plattform for å bygge forretningsapper. Det nye tillegget til PowerApps som er tilgjengelig i denne versjonen er modelldrevne apper. De er bygget ved bruk av den nye tjenesten Common Data Service for Apps. Common Data Service for Apps inneholder nå kjernefunksjonaliteten til apper for  Dynamics 365 Customer Engagement. Med modelldrevne apper kan du bygge apper som bruker de samme utvidbare funksjonene som disse appene.

Du trenger ikke å ha kjennskap til koding for å utvikle modelldrevne apper, da de inneholder ingen eller svært lite kode. Verdien for utviklerne er at de kan utvide programmet. Før du starter å skrive kode bør du gå gjennom hvordan man bygger modelldrevne apper, og hvilke alternativer som kan brukes uten kode. 

## <a name="get-started"></a>Kom i gang
Hvis du allerede har erfaring med apper for Dynamics 365 Customer Engagement, oppdager du at du kan ta i bruk din erfaring i byggingen av modelldrevne apper. Det finnes noen tilgjengelige utformingsprogrammer, men generelt sett så er konseptene de samme.

> [!NOTE]
> Modelldrevne apper kobler til Common Data Service for Apps. Hvis du vil ha mer informasjon om hvordan utviklere kan legge til verdi på tjenestenivå, kan du se [Oversikt for utviklere – Common Data Service for Apps](../common-data-service/overview.md).
> Innhold i denne inndelingen henviser bare til utvidelser utviklere kan ta i bruk som gjelder for opplevelsen for brukere av modelldrevne apper. 

Hvis du ikke har tidligere erfaring med apper for Dynamics 365 Customer Engagement, gir emnet i denne inndelingen en overordnet oversikt over de viktige konseptene for at utviklere skal komme i gang med modelldrevne apper. 

> [!NOTE]
> Fordi Common Data Service for Apps og Dynamics 365 Customer Engagement benytter samme plattform, finner du mer fullstendig informasjon for utviklere i [Dynamics 365 Customer Engagement – Veiledning for utviklere](/dynamics365/customer-engagement/developer/developer-guide). Disse emnene gir en oversikt med koblinger til veiledning for utviklere og andre støttelinjer for mer informasjon.


## <a name="community-tools-for-model-driven-apps"></a>Fellesskapsverktøy for modelldrevne apper

Dynamics 365-fellesskapet oppretter verktøy! Mange av de mest populære distribueres i [XrmToolBox](https://www.xrmtoolbox.com/). XrmToolBox er et Windows-program som kobler til Common Data Service for apper, som leverer verktøy for å forenkle tilpasning, konfigurering og operasjonsoppgaver. Den leveres med mer enn 30 programtillegg for gjøre administrasjons-, tilpassings- eller konfigurasjonsoppgaver enklere og mindre tidkrevende.

Følgende er en valgt liste med fellesskapsverktøy distribuert via XrmToolBox som du kan bruke når du arbeider med modelldrevne apper

|Verktøy  |Beskrivelse  |
|---------|---------|
|[Enkel oversetter](https://www.xrmtoolbox.com/plugins/MsCrmTools.Translator/)|Å eksportere og importere oversettelser med begrepsinformasjon|
|[Eksporter til Excel](https://www.xrmtoolbox.com/plugins/Ryr.XrmToolBox.ExportToExcel/)|Enkel eksport av poster fra den valgte visningen/fetchxml til Excel.|
|[Iconator](https://www.xrmtoolbox.com/plugins/MscrmTools.Iconator/)|Å behandle egendefinerte enhetsikoner i en enkelt skjerm|
|[Båndet Workbench 2016](https://www.xrmtoolbox.com/plugins/RibbonWorkbench2016/)|Å redigere Dynamics CRM-båndet eller kommandolinjen fra inne i XrmToolbox|
|[Visningsutforming](https://www.xrmtoolbox.com/plugins/Cinteros.XrmToolBox.ViewDesigner/)|Enkelt brukergrensesnitt til å utforme visning av oppsett og endre spørringer ved hjelp av FetchXML Builder|
|[Vis oppsettreplikator](https://www.xrmtoolbox.com/plugins/MsCrmTools.ViewLayoutReplicator/)|Å bruke samme oppsett på flere visninger av samme enhet i én enkelt operasjon|
|[WebResources Manager](https://www.xrmtoolbox.com/plugins/MsCrmTools.WebResourcesManager/)|Enkel administrasjon av nettressurser|

Et annet verktøy som ikke er distribuert via XrmToolBox er Jason Lattimer sin [CRM REST Builder](https://github.com/jlattimer/CRMRESTBuilder). Dette verktøyet genererer JavaScript-kode for bruk med Web-API.

> [!NOTE]
> Verktøy som er laget av fellesskapet støttes ikke av Microsoft. Hvis du har spørsmål eller problemer med fellesskapsverktøy, kan du kontakte utgiveren av verktøyet.




