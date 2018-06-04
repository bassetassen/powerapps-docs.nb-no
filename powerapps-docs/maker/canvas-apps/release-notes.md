---
title: Hva som er nytt i PowerApps | Microsoft Docs
description: Oppdateringer for PowerApps, organisert etter utgivelsesdato
services: powerapps
suite: powerapps
documentationcenter: na
author: skjerland
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/21/2018
ms.author: sharik
ms.openlocfilehash: e9e5c156e9cb3ad47375be9a237a757a6db1158b
ms.sourcegitcommit: a9d33322228c398d29964429602dc3fe19fa67d2
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/28/2018
ms.locfileid: "30998147"
---
# <a name="whats-new-in-powerapps"></a>Hva som er nytt i PowerApps
For informasjon om kjente begrensninger, kan du se [Vanlige problemer og løsninger](common-issues-and-resolutions.md).


> [!NOTE]
> Versjoner distribueres over flere dager. Nye eller oppdaterte funksjoner vises kanskje ikke umiddelbart.

## <a name="announcing-the-business-applications-spring-18-release-notes"></a>Annonsering av forretningsappens produktmerknader for våren 2018

Oppdag de nyeste oppdateringene våre forretningsprogrammer, samt en rekke nye muligheter for å bygge dine egne programmer og programutvidelser på plattformen vår. [Last ned PDF-en med produktmerknadene for våren 2018](https://aka.ms/businessappsreleasenotes), som dekker Dynamics 365, PowerApps, Microsoft Flow og Power BI.

**Kommer snart:** vi oppdaterer PDF-filen med produktmerknadene ettersom nye funksjoner lanseres, og vi gjør dem også tilgjengelige på en nettside.

## <a name="mar-21"></a>21. mars
1. Opprett [modelldrevne apper](../model-driven-apps/model-driven-app-overview.md), med utgangspunkt i datamodellen, og som bygges opp via formen på bedriftens kjernedata og -prosesser i Common Data Service, til former, visninger og andre komponenter for modellen. Modelldrevne apper genererer automatisk flotte brukergrensesnitt som virker på flere forskjellige enheter.
2. [Opprett en database](../../administrator/create-database.md) på den nyeste versjonen av Common Data Service i et miljø.
3. Common Data Service for apper inneholder nå:

    - **Flere datatyper** støtter mer komplekse enhetsdefinisjoner og gir bedre opplevelser. (Gjelder for lerret og modelldrevne apper.)
    - [Opprett og tilpass enheter](../common-data-service/data-platform-create-entity.md) i Common Data Service-for apper direkte fra nettområdet for PowerApps. Den **forbedrede opplevelsen** inkluderer bedre ytelse, et mer brukervennlig grensesnitt og nyttige funksjoner, som for eksempel innebygd oppretting av alternativsett. (Gjelder for lerret og modelldrevne apper.)
    - Opprett **forretningsregler for serversiden** for validering av dataene som angis i Common Data Service for apper. (Gjelder for lerret og modelldrevne apper.)
    - Opprett **beregnede felt for beregnet verdi** i Common Data Service for apper-enheter direkte fra PowerApps-området. (Gjelder for lerret og modelldrevne apper.)  
    - Utviklere kan bruke **Software Development Kit** (SDK) for Common Data Service for apper til å opprette kodebaserte tilpasninger for Common Data Service.
    - Viderekomne brukere kan få tilgang til data lagret i Common Data Service for apper gjennom et nytt **Web-API for OData** .
    - [Importer data](../common-data-service/data-platform-cds-newentity-pq.md) til Common Data Service med **Power Query**. Bruk Power Query på nettet til å importere data direkte til Common Data Service for-apper fra flere kilder

## <a name="mar-5"></a>05. mars
1. Legg til (og slett) [vedlegg](controls/control-attachments.md) til SharePoint-lister.
2. Åpne eksterne [PDF](controls/control-pdf-viewer.md)-filer i en nettleser. (Eksperimentell funksjon)

## <a name="feb-12"></a>12. feb.
* Volumkontrollen for innebygd avspilling av [video](controls/control-audio-video.md) og [lyd](controls/control-audio-video.md) er nå innebygd. Hvis du vil dempe avspillingen i stedet for å klikke eller trykke på en knapp, må brukere nå benytte lydkontrollen for å redusere volumet.

## <a name="feb-7"></a>07. feb.
1. Fjern egenskapene Zoom, Lysstyrke og Kontrast fra kontrollene [Kamera](controls/control-camera.md) og [Strekkodeleser](controls/control-barcodescanner.md).
2. Løste problemet hvor Fjern knapper på [Tekstinndata](controls/control-text-input.md)-kontroller begrenser plass ment for brukerinndata. Som et resultat av denne løsningen, støttes [Fjern](controls/control-text-input.md#additional-properties)-egenskapen for en inndatakontroll for tekst bare i Microsoft Edge (nyeste versjon) og Internet Explorer 11 for nettlesere.
3. Lagt til tilgjengelighetsforbedringer til [multimedia](add-images-pictures-audio-video.md)-kontroller.

## <a name="jan-31"></a>31. jan.
1. Legg til teksting for hørselshemmede til [video](controls/control-audio-video.md)-kontroller.
2. Forbedret feilhåndtering i [PDF-visningsprogram](controls/control-pdf-viewer.md)-kontroller.

## <a name="jan-18"></a>18. jan.
1. PowerApps for iOS og Android støtter nå integrering med Microsoft Authenticator.
2. En [kombinasjonsboks](controls/control-combo-box.md) erstatter [SharePoint-oppslagskontrollen](sharepoint-lookup-fields.md) i skjemaer, og en ny [datakort](working-with-cards.md)-mal for enkeltvalg av oppslagsfelt er valgt som standard i PowerApps Studio.
3. I en [kombinasjonsboks](controls/control-combo-box.md) ser du alle elementer i en lang liste med forbedret lesemodus.
4. Angi den øvre lagringsgrensen for poster til 2000 poster i [ikke-delegerbare spørringer](delegation-overview.md#non-delegable-limits). (Eksperimentell funksjon)

## <a name="jan-5"></a>05. jan.
* Utfør en handling med data fra Power BI-rapporten eller -instrumentbordet ved å integrere et [egendefinert visualobjekt i PowerApps (forhåndsversjon)](https://powerapps.microsoft.com/blog/powerbi-powerapps-visual/), som henter kontekstavhengige data fra Power BI-rapporten.

## <a name="dec-8"></a>08. des.
1. [Maler for betingelser](working-with-rules.md) for regler utleder felles egenskaper for en kontroll (for eksempel **tekst** eller **verdi**).
2. Slutt å vise bekreftelsesdialogboksen [ **Definer handlinger** ](working-with-rules.md) når du definerer regelhandlinger.

## <a name="nov-13"></a>13. nov.
1. Velg flere verdier for samme felt i SharePoint-lister.
2. [Vis og last ned vedlegg](controls/control-attachments.md) i SharePoint-lister.
3. [Tilpass SharePoint-listeskjemaer](customize-list-form.md) ved hjelp av PowerApps.

## <a name="nov-10"></a>10. nov.
* [Gi nytt navn til regler](working-with-rules.md) i en app, og vis regler når den valgte kontrollen er i betingelsen for regelen.

## <a name="oct-30"></a>30. okt.
1. [Vis alle regler](working-with-rules.md) i en app, ikke bare de for den valgte kontrollen.
2. Legg til de ikonene som apputviklere etterspør mest.
3. Forbedret ytelse for apper på Android- og iOS-enheter.
