---
title: Hva som er nytt | Microsoft Docs
description: Oppdateringer for PowerApps, organisert etter utgivelsesdato
author: AFTOwen
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 05/21/2018
ms.author: anneta
ms.openlocfilehash: 55b60abd9dc07d5b6c1979190f20ef893265475f
ms.sourcegitcommit: b9fa569153924af9815db45d52c04e764ddb7fa2
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 07/17/2018
ms.locfileid: "39094706"
---
# <a name="whats-new-in-powerapps"></a>Hva som er nytt i PowerApps
> [!IMPORTANT]
> **Annonsering av produktmerknader**<br>
> Lurer du på noe om kommende og nylig utgitte funksjoner i PowerApps?<br>
[Vis produktmerknadene](https://docs.microsoft.com/business-applications-release-notes/april18/powerapps/overview). Vi har tatt med alle detaljer, fra ende til annen, som du kan dra nytte av når du skal planlegge.

For informasjon om kjente begrensninger, kan du se [Vanlige problemer og løsninger](common-issues-and-resolutions.md).

> [!NOTE]
> Versjoner distribueres over flere dager. Nye eller oppdaterte funksjoner vises kanskje ikke umiddelbart.

## <a name="may-30"></a>30. mai
1. [Redigeringskontroll for rik tekst](controls/control-richtexteditor.md) (eksperimentell) – lar sluttbrukere formatere tekst i et WYSIWYG-redigeringsområde. 

## <a name="may-21"></a>21. mai
1. La appbrukere få muligheten til å importere og eksportere data fra Excel- eller CSV-filer som er lagret lokalt ved å bruke funksjonene **Hent data fra Excel-fil** og **Eksporter data** som nå er tilgjengelige for oppdaterte Common Data Service (CDS) for apper-miljøer. 
1. Lar appbrukere [åpne enheter i Excel](../common-data-service/data-platform-excel-addin.md) for å opprette, oppdatere og slette data som er lagret i CDS for apper ved å bruke Excel-tillegget for PowerApps. 
1. [Å opprette og publisere Power BI-rapporter](../common-data-service/data-platform-powerbi-connector.md) ved hjelp av Power BI Desktop koblet til CDS for apper. 

## <a name="april-23"></a>23. april
* Nedlasting av [vedlegg](controls/control-attachments.md) i Internet Explorer, i egendefinerte listeskjemaer for SharePoint.

## <a name="april-9"></a>9. april
* Kontrollene Klipp ut (CTRL + X), Kopier (CTRL + C) og Lim inn (CTRL + V) &mdash;, inkludert kontrollenes stiler, formler og egenskaper&mdash;på tvers av apper i en nettleser.

## <a name="march-21"></a>21. mars
1. Opprett [modelldrevne apper](../model-driven-apps/model-driven-app-overview.md) med utgangspunkt i datamodellen, og som bygges opp via formen på bedriftens kjernedata og -prosesser i Common Data Service for apper, for å utforme skjemaer, visninger og andre komponenter. Modelldrevne apper genererer automatisk flotte brukergrensesnitt som virker på flere forskjellige enheter.
2. [Opprett en database](../../administrator/create-database.md) på den nyeste versjonen av Common Data Service for apper i et miljø.
3. CDS for apper inkluderer nå:
    - **Flere datatyper** støtter mer komplekse enhetsdefinisjoner og gir bedre opplevelser. (Gjelder for lerret og modelldrevne apper.)
    - [Opprett og tilpass enheter](../common-data-service/data-platform-create-entity.md) i Common Data Service for apper direkte fra nettområdet for PowerApps. Den **forbedrede opplevelsen** inkluderer bedre ytelse, et mer brukervennlig grensesnitt og nyttige funksjoner, som for eksempel innebygd oppretting av alternativsett. (Gjelder for lerret og modelldrevne apper.)
    - Opprett **forretningsregler for serversiden** for validering av dataene som angis i Common Data Service for apper. (Gjelder for lerret og modelldrevne apper.)
    - Opprett **beregnede felt for beregnet verdi** i Common Data Service for apper-enheter direkte fra PowerApps-området. (Gjelder for lerret og modelldrevne apper.)  
    - Utviklere kan bruke **Software Development Kit** (SDK) for CDS for apper for å opprette kodebaserte tilpasninger for CDS for apper.
    - Viderekomne brukere kan få tilgang til data lagret i Common Data Service for apper gjennom et nytt **Web-API for OData** .
    - [Importer data](../common-data-service/data-platform-cds-newentity-pq.md) i CDS for apper med **Power Query**. Bruk Power Query på nettet til å importere data direkte til Common Data Service for apper fra flere kilder

## <a name="march-5"></a>05. mars
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
