---
title: Å bygge inn Power BI-prosjektrapporter i SharePoint Online i Microsoft Docs
description: I denne oppgaven skal vi bygge inn Power BI-rapporten i det samme SharePoint Online-området som er vert for de to listene våre.
author: NickWaggoner
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 01/30/2018
ms.author: niwaggon
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 92ae77237064d28e3070f7e7bc9cb94c4493a3c6
ms.sourcegitcommit: 90245baddce9d92c3ce85b0537c1ac1cf26bf55a
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 01/26/2019
ms.locfileid: "57799598"
---
# <a name="embed-the-power-bi-project-report-in-sharepoint-online"></a>Å bygge inn Power BI-prosjektrapporten i SharePoint Online
> [!NOTE]
> Denne artikkelen er en del av en opplæringsserie om hvordan du bruker PowerApps, Microsoft Flow og Power BI med SharePoint Online. Sørg for å lese [serieinnføringen](sharepoint-scenario-intro.md) for å få en fornemmelse av det store bildet, i tillegg til relaterte nedlastinger.

Vi skal nå bygge inn Power BI-rapporten i det samme SharePoint Online-området som er vert for de to listene våre. Power BI støtter en rekke måter å bygge inn på, inkludert direkte integrering i SharePoint-sider for nett og mobilvisninger.

Med denne typen innebygging bygger Power BI rapporten inn som en nettdel, gir riktig tilgang for brukere og lar deg klikke gjennom fra den innebygde rapporten til rapporten på powerbi.com. Først skal vi generere en kobling for innebygging i Power BI, og deretter skal vi bruke koblingen på en side som vi oppretter. Hvis du vil ha mer informasjon om innebygging, kan du se [Bygge inn med nettdelen for rapporter i SharePoint Online](https://docs.microsoft.com/power-bi/service-embed-report-spo).

## <a name="step-1-generate-an-embed-link"></a>Trinn 1: Generere en innebyggingskobling
1. Logg på Power BI, og deretter klikker eller trykker du på rapportnavnet i den venstre navigasjonsruten.
   
    ![Å gå til rapport](./media/sharepoint-scenario-embed-report/08-01-01-reports.png)
2. Klikk eller trykk på **Fil**, og deretter på **Bygg inn i SharePoint Online**.
   
    ![Å bygge inn i SharePoint Online](./media/sharepoint-scenario-embed-report/08-01-02-embed-spo.png)
3. Kopier innebyggingskoblingen fra dialogboksen til en fil, og klikk eller trykk deretter på **Lukk**. Vi vil bruke koblingen etter vi har opprettet en SharePoint-side.
   
    ![Innbyggingskobling for SharePoint](./media/sharepoint-scenario-embed-report/08-01-03-embed-url.png)

## <a name="step-2-embed-the-report"></a>Trinn 2: Bygge inn rapporten
1. Logg deg på SharePoint, og deretter klikker eller trykker du på **Områdeinnhold**.
   
    ![SharePoint-områdeinnhold](./media/sharepoint-scenario-embed-report/08-01-04-site-contents.png)
2. Du kan velge å bare inkludere en rapport på teamets hjemmeside, men vi skal vise deg hvordan du oppretter en separat side for dette også. Klikk eller trykk på **Ny** og deretter på **Side**.
   
    ![Ny SharePoint-side](./media/sharepoint-scenario-embed-report/08-01-05-new-page.png)
3. Angi et navn for siden, som «Prosjektanalyse».
4. Klikk eller trykk på ![pluss-ikonet](./media/sharepoint-scenario-embed-report/icon-plus.png), og deretter på **Power BI**.
   
    ![Å legge til en sidedel for Power BI](./media/sharepoint-scenario-embed-report/08-01-06-add-page-part.png)
5. Klikk eller trykk på **Legg til rapport**.
   
    ![Å legge til rapport](./media/sharepoint-scenario-embed-report/08-01-07-add-report.png)
6. I den høyre ruten kan du kopiere nettadressen for innebygging til **Power BI-rapportkobling**-boksen. Sett både **Vis filtreringsrute** og **Vis navigasjonsrute** til **På**.
   
    ![Rapportinnstillinger](./media/sharepoint-scenario-embed-report/08-01-08-report-settings.png)
7. Rapporten er nå innebygd på siden. Klikk på **Publiser** for å gjøre den tilgjengelig for alle som har tilgang til den underliggende rapporten.
   
    ![Innebygging av rapport fullført](./media/sharepoint-scenario-embed-report/08-01-09-report-complete.png)

## <a name="step-3-grant-access-to-the-report"></a>Trinn 3: Gi tilgang til rapporten.
Hvis du bruker Office 365-grupper, som vi anbefaler, må du kontrollere at brukere som trenger tilgang er medlemmer av gruppens arbeidsområde i Power BI-tjenesten. Dette sikrer at brukere kan vise innholdet i denne gruppen. Hvis du vil ha mer informasjon, kan du se [Samarbeide i arbeidsområdet for Power BI-appen](https://docs.microsoft.com/power-bi/service-collaborate-power-bi-workspace).

Dette oppsummerer arbeidet vårt i Power BI for dette scenarioet. Du startet med å hente data fra våre SharePoint-lister til Power BI, og har nå fullført prosessen med å bygge inn Power BI-rapporten tilbake til SharePoint.

## <a name="next-steps"></a>Neste trinn
Det neste trinnet i denne opplæringsserien er å [gå gjennom arbeidsflyten vi opprettet fra start til slutt](sharepoint-scenario-summary.md).

