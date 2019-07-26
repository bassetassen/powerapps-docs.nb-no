---
title: Feilsøke problemer med data som ikke vises i en rapport | Microsoft Docs
description: Feilsøke problemer med data som ikke vises i en rapport
author: mduelae
manager: kvivek
ms.service: powerapps
ms.component: pa-user
ms.topic: conceptual
ms.date: 06/27/2019
ms.author: mkaur
ms.custom: ''
ms.reviewer: ''
ms.assetid: ''
search.audienceType:
- enduser
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: 1156aa8fb5fbc3ae51c21b8aa41606df6dbc2e86
ms.sourcegitcommit: e9671e018c1ee4b640528915350a367758991b6a
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/27/2019
ms.locfileid: "67420770"
---
# <a name="troubleshoot-problems-with-data-not-displaying-in-a-report"></a>Feilsøke problemer med data som ikke vises i en rapport

Det finnes flere mulige årsaker til at data som du forventer å være i en rapport, ikke vises:  
  
- **Utilstrekkelige sikkerhets tillatelser**. Hvis du ikke har tillatelse i Common Data Service til å vise en post, vil den ikke vises i rapporten.  
  
- **Data er ikke angitt.** Personen som registrerer data, kan ha latt feltene stå tomme.  
  
- **Dataene Sams varer ikke med vilkårene for rapporten.** Mange rapporter inkluderer et standard filter som viser bare aktive poster, eller du kan ha valgte vilkår som ikke har noen samsvarende post. Prøv å endre rapport filteret. Hvis du vil ha mer informasjon, kan du se [redigere standard filteret for en rapport](edit-report-filter.md)  
  
- **Det kan hende du viser en hurtigbufret kopi av rapporten.** Som standard hentes data i Common Data Service rapporter fra databasen hver gang du kjører en rapport. Systemansvarlig kan imidlertid ha endret en rapport for kjøring fra hurtig bufferen. Hvis data du har angitt nylig, ikke er inkludert i rapporten, kan det hende du har en eldre versjon av rapporten fra hurtig bufferen. Hvis du vil oppdatere rapporten, velger du **Oppdater** -knappen på rapport verktøy linjen.  
  
- **Du har kanskje ikke tillatelse til å lese poster i en del rapport.** Hvis du ikke har tillatelse til å lese post typer som er inkludert i en del rapport, får du en feil melding om at del rapporten ikke kunne vises.  
  
- **Person vern innstillingene i Microsoft Internet Explorer kan blokkere nødvendige informasjons kapsler.** Hvis du i stedet for ser diagrammet, ser du en rød bokstav, og person vern innstillingene kan blokkere en informasjons kapsel som kreves for diagramkontrollen. Du kan løse dette problemet ved å aktivere informasjons kapsler for serveren som kjører Reporting Services, i nett leseren.  
  

### <a name="see-also"></a>Se også
[Arbeide med rapporter](work-with-reports.md) 

[Å opprette en rapport ved hjelp av rapport vei viseren](create-report-with-wizard.md)

[Legg til en eksisterende rapport](add-existing-report.md)

[Rediger rapport filter](edit-report-filter.md)

