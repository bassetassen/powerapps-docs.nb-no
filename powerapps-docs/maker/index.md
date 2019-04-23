---
title: Oversikt over oppretting av apper | Microsoft Docs
description: Oversikt over oppretting av apper i lerret eller modelldreven modus med Common Data Service
author: AFTOwen
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.date: 03/18/2018
ms.author: anneta
ms.reviewer: ''
ms.openlocfilehash: 6a8432e93f854b1c0794512da42ef25c9aa02adc
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/23/2019
ms.locfileid: "61528600"
---
# <a name="overview-of-creating-apps-in-powerapps"></a>Oversikt over oppretting av apper i PowerApps

PowerApps er en utviklingsplattform for bedriftsapper med høy produktivitet, og har tre hovedkomponenter:

- [Lerretsapper](canvas-apps/getting-started.md) bruk mulighetene i et tomt lerret og start med brukeropplevelsen. Opprett et skreddersydd grensesnitt og koble det til én av 200 datakilder. Du kan opprette lerretsapper for nett-, mobil- og nettbrettprogrammer.
- [Modelldrevne apper](model-driven-apps/model-driven-app-overview.md) starter med datamodellen. De utvikles basert på bedriftens data og prosesser i Common Data Service og modellerer skjemaer, visninger og andre komponenter. Modelldrevne apper genererer automatisk brukergrensesnitt som virker på flere forskjellige enheter.
- [Common Data Service](common-data-service/data-platform-intro.md) er dataplattformen som følger med PowerApps, og som gjør det mulig å lagre og modellere bedriftsdata. Det er plattformen Dynamics 365-programmer utvikles på. Hvis du bruker Dynamics 365, er dataene dine allerede i Common Data Service.

Det er enkelt å opprette din første app. Vi har et 30-dagers prøveabonnement og et kostnadsfritt fellesskapsabonnement. Finn ut hva som passer best for deg, og kom i gang.

## <a name="canvas-apps"></a>Lerretsapper

Med fleksibiliteten i lerretsapper kan du arrangere brukeropplevelsen og grensesnittet slik du vil ha det. La kreativitet og forretningssans vise deg hvordan appene skal se ut.

Du kan begynne å utvikle appen med Microsoft-verktøy der dataene befinner seg, for eksempel:

- [Fra en SharePoint-liste](canvas-apps/app-from-sharepoint.md#generate-an-app-from-within-sharepoint-online)
- [Fra et Power BI-instrumentbord](canvas-apps/embed-powerapps-powerbi.md)

Det er enkelt å opprette en lerretsapp. Med PowerApps kan du finne eller opprette appen din på flere måter:

- [Fra data](canvas-apps/app-from-sharepoint.md)
- [Fra et eksempel](canvas-apps/open-and-run-a-sample-app.md)
- [Fra en kilde for Common Data Service](canvas-apps/data-platform-create-app.md)
- [Fra et tomt lerret](canvas-apps/data-platform-create-app-scratch.md)
- [Via AppSource](../user/app-source.md)

## <a name="model-driven-apps"></a>Modelldrevne apper

Når du oppretter en modelldreven app, kan du bruke kraften i Common Data Service til å konfigurere skjemaer, forretningsregler og prosessflyter på en rask måte. Du kan opprette en modelldreven app fra nettområdet for PowerApps.

Det er enkelt å komme i gang med modelldrevne apper, og du kan begynne med disse emnene:

- [Opprette en app](https://docs.microsoft.com/dynamics365/customer-engagement/customize/create-edit-app)
- [Opprette og utforme skjemaer](https://docs.microsoft.com/dynamics365/customer-engagement/customize/create-design-forms)
- [Opprette eller redigere visninger](https://docs.microsoft.com/dynamics365/customer-engagement/customize/create-edit-views)
- [Opprette eller redigere et systemdiagram](https://docs.microsoft.com/dynamics365/customer-engagement/customize/create-edit-system-chart)
- [Opprette eller redigere instrumentbord](https://docs.microsoft.com/dynamics365/customer-engagement/customize/create-edit-dashboards)
- [Legge til sikkerhet](https://docs.microsoft.com/dynamics365/customer-engagement/customize/manage-access-apps-security-roles)
- [Legge til forretningslogikk](https://docs.microsoft.com/dynamics365/customer-engagement/customize/guide-staff-through-common-tasks-processes)

## <a name="common-data-service"></a>Common Data Service

Common Data Service gjør det mulig å lagre og behandle data i et sett med standard og egendefinerte enheter på en sikker måte, og du kan legge til felt i disse enhetene når du trenger dem.

Det er enkelt å komme i gang med Common Data Service. Du kan for eksempel starte med disse elementene:

- [Opprette en egendefinert enhet](common-data-service/data-platform-create-entity.md)
- [Administrere felt](common-data-service/data-platform-manage-fields.md)
- [Opprette egendefinerte alternativsett](common-data-service/custom-picklists.md)
- [Definering av en forretningsregel](https://docs.microsoft.com/dynamics365/customer-engagement/customize/create-business-rules-recommendations-apply-logic-form)

## <a name="canvas-and-model-driven-artifacts"></a>Lerret og modelldrevne artefakter

Mens vi slår sammen erfaringene til lerret og modelldrevne apper, vil disse artefaktene være relevant for enten lerretsapper eller modelldrevne apper.

| Artefakt            | Apptype     |
|---------------------|--------------|
| Enhet > Visninger      | Modelldrevet |
| Enhet > Skjemaer      | Modelldrevet |
| Enhet > Instrumentbord | Modelldrevet |
| Tilkoblinger         | Lerret       |
| Gatewayer            | Lerret       |
| Egendefinerte tilkoblinger   | Lerret       |
| Apper > Import       | Lerret       |

Når du har opprettet appen, kan du [dele den](canvas-apps/share-app.md) med medlemmene i teamet ditt.
