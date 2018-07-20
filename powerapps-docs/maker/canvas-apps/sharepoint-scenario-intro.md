---
title: Å integrere PowerApps, Microsoft Flow og Power BI med SharePoint Online (introduksjon) i Microsoft Docs
description: 'Denne serien av veiledninger utforsker hvordan du bygger en grunnleggende app for prosjektstyring, som er basert på SharePoint-lister og tre viktige teknologier, som kan integreres med SharePoint Online: PowerApps, Microsoft Flow og Power BI.'
author: mgblythe
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 12/19/2017
ms.author: mblythe
ms.openlocfilehash: e8a7860920f25572ec899ee93d501ed553ee62f9
ms.sourcegitcommit: dfa0e1a7981814e15e6ca4720e2a5f930e859db1
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 07/13/2018
ms.locfileid: "39019576"
---
# <a name="integrate-powerapps-microsoft-flow-and-power-bi-with-sharepoint-online"></a>Å integrere PowerApps, Microsoft Flow og Power BI med SharePoint Online
Har du SharePoint Online og ønsker å automatisere og strømlinjeforme forretningsprosessene bedre? Har du jobbet med PowerApps, Microsoft Flow eller Power BI, men er ikke sikker på hvordan du bruker dem med SharePoint Online? Du har kommet til rett sted! Denne serien av veiledninger utforsker hvordan du bygger en grunnleggende app for prosjektstyring, som er basert på SharePoint-lister og tre viktige teknologier, som kan integreres med SharePoint Online: PowerApps, Microsoft Flow og Power BI. Disse teknologiene arbeider sammen, noe som gjør det enkelt å *måle* bedriften, *reagere* på resultatene, og *automatisere* arbeidsflyten. Når du er ferdig med denne serien, har du et stilig scenario, som følgende:

![Diagram over fullført scenario](./media/sharepoint-scenario-intro/composite-with-background.png)

## <a name="business-scenario"></a>Forretningsscenario
I denne serien av opplæringer har firmaet Contoso et SharePoint Online-området der de administrere livssyklusen for prosjekter, fra forespørsel, til godkjenning, til utvikling til endelig gjennomgang. En *prosjektanmoder*, for eksempel en avdelingsleder, forespør et IT-prosjekt ved å legge til et element i en SharePoint-liste. En *prosjektgodkjenner*, for eksempel en IT-sjef, vurderer prosjektet, og deretter godkjenner eller avslår det. Prosjektet blir tilordnet til en *prosjektleder* hvis det blir godkjent, og ytterligere detaljer blir lagt til en annen liste gjennom samme app. En *forretningsanalytiker* vurderer gjeldende og fullførte prosjekter ved hjelp av en Power BI-rapport i SharePoint.  Microsoft Flow brukes til å sende e-post for godkjenning, og svare på Power BI-varsler.

## <a name="getting-started-quickly"></a>Å komme raskt i gang
Scenarioet vi presenterer i denne serien av opplæringer, er enkelt sammenlignet med en komplett prosjektstyring- og analyse-app, men det tar fremdeles litt tid å fullføre alle oppgavene. Hvis du bare ønsker en rask innføring i å bruke PowerApps, Microsoft Flow og Power BI med SharePoint, se følgende artikler:

* **PowerApps**: [Å generere en app fra innsiden av SharePoint ved hjelp av PowerApps](generate-app-from-sharepoint-list-interface.md), og [Å generere en app for å behandle data i en SharePoint-liste](app-from-sharepoint.md)
* **Microsoft Flow**: [Å vente på godkjenning i Microsoft Flow](https://docs.microsoft.com/flow/wait-for-approvals)
* **Power BI**: [Å bygge inn med nettdelen for rapporter i SharePoint Online](https://docs.microsoft.com/power-bi/service-embed-report-spo)

Vi håper du kommer tilbake for å se på dette fullstendige scenarioet når du er ferdig.

Selv innenfor scenarioet, kan du fokusere på oppgavene som interesserer deg, og utføre oppgaver etter som du har tid. Når du setter opp SharePoint-lister i oppgave 1, kan du arbeide gjennom oppgavene 2-5 i en hvilken som helst rekkefølge. Deretter er oppgavene 6-8 sekvensielle. Vi har til slutt inkludert to ferdig apper og en Power BI Desktop-rapport, som en del av [nedlastingspakken](https://aka.ms/o4ia0f) for dette scenarioet. Du kan se på disse og lære av eksempel, selv om du ikke går gjennom alle trinnene i hver oppgave.

## <a name="prerequisites"></a>Forutsetninger
For å fullføre scenarioet trenger du følgende abonnementer og skrivebordsverktøy. Office 365 Business Premium-abonnementet inkluderer PowerApps og Microsoft Flow.

| **Abonnement eller verktøy** | **Kobling** |
| --- | --- |
| Office 365 Business Premium-abonnement |[Prøveabonnement](https://signup.microsoft.com/Signup?OfferId=467eab54-127b-42d3-b046-3844b860bebf&dl=O365_BUSINESS_PREMIUM&ali=1) |
| Power BI Pro-abonnement |[Prøveabonnement](https://powerbi.microsoft.com/get-started/) (Klikk på **Prøv gratis**) |
| Power BI Desktop |[Gratis nedlasting](https://powerbi.microsoft.com/get-started/) (Klikk på **LAST NED GRATIS**) |

Ideelt sett bør du har grunnleggende kjennskap til hver teknologi, men du kan fortsatt fullføre scenarioet hvis du har brukt noen av disse teknologiene. Bruk følgende innhold for å komme i gang:

* [Kom i gang med SharePoint](https://support.office.com/article/Get-started-with-SharePoint-909ec2f0-05c8-4e92-8ad3-3f8b0b6cf261)
* [Veiledet læring for PowerApps](../../guided-learning/index.md)
* [Veiledet læring for Microsoft Flow](https://docs.microsoft.com/flow/guided-learning/)
* [Veiledet læring for Power BI](https://docs.microsoft.com/power-bi/guided-learning/)

## <a name="next-steps"></a>Neste trinn
Det neste trinnet i denne opplærings-serien, er å [konfigurere SharePoint Online-lister](sharepoint-scenario-setup.md) som vi bruker gjennom hele serien.

