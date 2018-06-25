---
title: Dataintegrasjon av kundedata for administratorer
description: Identifisering, eksportering og sletting av personlige data i dataintegrering for administratorer for CDS for apper
author: sabinn-msft
ms.service: powerapps
ms.topic: how-to
ms.component: cds
ms.date: 05/20/2018
ms.author: sabinn
ms.openlocfilehash: 01dafceacff89cb9b3a400caad5dde07a0995f1c
ms.sourcegitcommit: e59c849a88c6fc0ed333ef4ce2d982a5b8623c97
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/04/2018
ms.locfileid: "34754229"
---
# <a name="responding-to-data-subject-rights-dsr-requests-for-data-integration-for-common-data-service-for-apps-customer-data"></a>Svar på DSR-forespørsler om integrering av kundedata i Common Data Service for apper

## <a name="introduction-to-dsr-requests"></a>Innføring i DSR-forespørsler

EUs personvernforordning (GDPR) gir en bruker (kalt «den registrerte» i forordningen) rett til å behandle personopplysningene som en arbeidsgiver eller et annet byrå eller organisasjon («datakontrollør» eller bare «kontrollør») har samlet inn. Personopplysninger er definert svært bredt under GDPR som alle data som er knyttet til en identifisert eller identifiserbar person. GDPR gir dataemner rett til å gjøre følgende, slik det gjelder deres personopplysninger:

- Få kopier
- Be om rettelser
- Begrense behandling
- Slette den
- Motta den i elektronisk format, slik at den kan flyttes til en annen kontrollør

En formell forespørsel fra en bruker til en kontrollør om behandling av personopplysningene hans eller hennes, kalles en DSR-forespørsel.

Denne artikkelen beskriver hvordan Microsoft forbereder seg på GDPR, og gir eksempler på hva du kan gjøre for å sikre at du samsvarer med GDPR-forskriftene når du bruker dataintegrering for administratorer via administratorportalen i CDS for apper. Du finner ut hvordan du bruker Microsofts produkter, tjenester og administrative verktøy for å hjelpe kontrollørkundene med å finne, få tilgang til og behandle personopplysninger i Microsoft-skyen i forbindelse med DSR-forespørsler.

### <a name="searching-for-and-identifying-personal-data"></a>Å søke etter og identifisere personlige data

Integrering av data for administratorer i CDS for apper lar alle brukere av integreringsprogrammet vise sine data ved hjelp av dataintegreringsfanen på:

[https://admin.powerapps.com/dataintegration](https://admin.powerapps.com/dataintegration)

Dataene som er lagret for brukeren vises i portalen. Alle prosjekter er synlige i kategorien Prosjekter:

![Vis prosjekter under Prosjekter-fanen](./media/data-integration-gdpr-dsr/projects-tab.png)

Alle tilkoblingssett er synlige på Tilkoblingssett-fanen:

![Vis tilkoblingssett under Tilkoblingssett-fanen](./media/data-integration-gdpr-dsr/connections-tab.png)

Alle maler er synlige på Maler-fanen:

![Vis maler under Maler-fanen](./media/data-integration-gdpr-dsr/templates-tab.png)

## <a name="securing-and-controlling-access-to-personal-information"></a>Å sikre og kontrollere tilgang til personlige opplysninger

I dataintegrering for administratorer i CDS for apper kan data som er lagret av programmet for dataintegrering bare åpnes gjennom administratorportalen.

## <a name="deleting-personal-data"></a>Sletting av personlige data

I dataintegrering for administratorer i CDS for apper kan data opprettet av brukere, prosjekter og tilkoblingssett slettes av brukeren dataene er tilknyttet. Brukere kan logge seg på administratorportalen for å slette sine personlige opplysninger: [https://admin.powerapps.com](https://admin.powerapps.com)

Brukere kan slette prosjekter ved å navigere til Prosjekter-fanen, klikke på ellipsen ved siden av prosjektet og deretter velge alternativet Slett:

![Å slette prosjekter ved å klikke på ellipsen](./media/data-integration-gdpr-dsr/projects-del.png)

Brukere kan slette maler ved å navigere til Maler-fanen, klikke på ellipsen ved siden av malen, og deretter velge alternativet Slett:

![Å slette maler ved å klikke på ellipsen](./media/data-integration-gdpr-dsr/templates-del.png)

Brukere kan slette tilkoblingssett ved å navigere til Tilkoblingssett-fanen, klikke på ellipsen ved siden av tilkoblingssettet og deretter velge alternativet Slett:

![Å slette tilkoblingssett ved å klikke på ellipsen](./media/data-integration-gdpr-dsr/connsets-del.png)

## <a name="exporting-personal-data"></a>Eksport av personlige data

I dataintegrering for administratorer i CDS for apper kan data opprettet av brukere eksporteres av brukeren dataene er knyttet til. Brukere kan logge seg på administratorportalen for å eksportere sine personlige opplysninger:

[https://admin.powerapps.com](https://admin.powerapps.com)

Hvis du vil eksportere prosjekter eller prosjekter med utførelseshistorikk, kan brukere gå til Prosjekter-fanen, klikke på ellipsen ved siden av prosjektet og deretter velge ønsket eksportalternativ:

![Å eksportere prosjekter ved å klikke på ellipsen](./media/data-integration-gdpr-dsr/projects-exp.png)

Brukere kan eksportere maler ved å navigere til Maler-fanen, klikke på ellipsen ved siden av malen og deretter velge alternativet Eksporter:

![Å eksportere maler ved å klikke på ellipsen](./media/data-integration-gdpr-dsr/templates-exp.png)

Brukere kan eksportere tilkoblingssett ved å navigere til Tilkoblingssett-fanen, klikke på ellipsen ved siden av tilkoblingssettet og deretter velge alternativet Eksporter:

![Å eksportere tilkoblingssett ved å klikke på ellipsen](./media/data-integration-gdpr-dsr/connsets-exp.png)
