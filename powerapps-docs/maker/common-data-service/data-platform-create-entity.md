---
title: Hurtiginnføring i hvordan du oppretter en egendefinert enhet i Microsoft Docs
description: Hurtiginnføring i hvordan oppretter en egendefinert enhet, basert på en annen enhet eller fra grunnen av.
services: powerapps
documentationcenter: na
author: clwesene
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 3/21/2018
ms.author: clwesene
ms.openlocfilehash: e22a18bacb258ca46c8f36d647f9ebcc45282929
ms.sourcegitcommit: a9d33322228c398d29964429602dc3fe19fa67d2
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/28/2018
ms.locfileid: "30998092"
---
# <a name="quickstart-create-a-custom-entity"></a>Hurtiginnføring i hvordan oppretter en egendefinert enhet
Du kan opprette en egendefinert enhet for å lagre data som er spesifikk for din organisasjon. Deretter kan du vise dataene ved å utvikle en app som refererer til enheten. Etter at du har opprettet en enhet, kan du [opprette flere felter eller endre ett eller flere av feltene](data-platform-manage-fields.md) og [bygge relasjoner mellom enheter](data-platform-entity-lookup.md).

Disse instruksjonene viser deg hvordan du kan opprette en egendefinert enhet manuelt, men du kan også bruke Power Query til å opprette en enhet basert på dine eksisterende data. Hvis du vil ha mer informasjon, kan du se [Slik oppretter du en ny enhet ved bruk av Power Query](data-platform-cds-newentity-pq.md)

> [!NOTE]
> Før du oppretter en enhet, kan du se på [enhetsreferansen](../../developer/common-data-service/reference/about-entity-reference.md). Disse enhetene dekker vanlige scenarioer, for eksempel forretningsforbindelser og kontakter. Hvis ett av disse enhetene oppfyller kravene dine som den er eller etter bare små endringer, kan du spare litt tid ved å starte med denne enheten.

## <a name="create-an-entity"></a>Å opprette en enhet
1. Utvid **Data**-delen på [powerapps.com](https://web.powerapps.com), og trykk eller klikk på **Enheter** i venstre navigasjonsrute.

    ![Enhetsdetaljer](./media/data-platform-cds-create-entity/entitylist.png "Enhetsliste")

2. Klikk eller trykk på **Ny enhet** fra kommandolinjen.
3. Skriv inn et navn som er gjenkjennelig for deg i **Visningsnavn**, slik at du kan henvise til denne enheten i framtiden. Dette brukes også i forum, diagrammer og andre objekter som opprettes ved bruk av denne enheten. Du ser to andre felt som også fylles ut:

    * Visningsnavn i flertall – dette brukes når du samhandler med denne enheten fra Powerapps elle Flow, og brukes som navnet på enheten i Common Data Service WebAPI. Flertallsnavnet genereres sannsynligvis automatisk, men det kan endres.
    * Navn – dette er det unike navnet på enheten, det kan ikke inneholde spesialtegn eller mellomrom, og det må være unikt. Navnet inkluderer også et prefiks som ble konfigurert da miljøer ble opprettet. Dette brukes for å sikre at enhetene du oppretter kan eksporteres og importeres i andre miljøer, der andre enheter kan ha samme navn. Dette prefikset kan endres ved å oppdatere prefikset i Publisher for standardmiljøet i Common Data Service.

    > [!NOTE]
    > **Visningsnavn**-feltet kan oppdateres når som helst til en annen visning i appene dine, men **Navn**-feltet kan ikke endres etter at enheten er lagret. Dette kan resultere i at en eksisterende app ødelegges.

    ![Ny enhet](./media/data-platform-cds-create-entity/newentitypanel.png "Nytt enhetspanel")

4. Klikk på **Neste**, og du blir deretter omdirigert til Enhetsdetaljer-siden. Hver enhet begynner med ett felt, Primært navn, som standard, og dette feltet brukes når oppslag opprettes mot denne enheten. Det skal som regel brukes for å lagre navnet eller den primære beskrivelsen av dataene som lagres i enheten.

    > [!NOTE]
    > Navnet og visningsnavnet til **Primært navn**-feltet kan oppdateres før du lagrer enheten første gang. Hvis du for eksempel ønsket å kalle dette feltet Elevnavn i stedet for Primært navn

    ![Enhetsdetaljer](./media/data-platform-cds-create-entity/newentitydetails.png "Nye enhetsdetaljer")

5. (valgfritt) Legg til et tekstfelt i enheten ved å klikke på **Legg til felt**. Skriv inn **Visningsnavn** i Nytt felt-panelet for feltet, og velg datatypen. Hvis du vil ha mer informasjon, kan du se[Å administrere felter i en enhet](data-platform-manage-fields.md).

    ![Nytt felt](./media/data-platform-cds-create-entity/newfieldpanel-2.png "Nytt felt-panel")


6. Klikk på **Ferdig** for å legge til feltet, og gjenta trinn 5 for å legge til ytterligere felter.
7. Klikk på **Lagre enhet** for å lagre enheten og gjøre den tilgjengelig for bruk i apper.

    Enheten vises i listen over enheter i databasen. Hvis du vil se enheter du har opprettet, kan du endre filteret i kommandolinjen fra Standard til Egendefinert

## <a name="system-fields"></a>Systemfelt
Alle enheter har systemfelter. Disse feltene er skrivebeskyttet. Derfor du ikke endre eller slette disse feltene, og du kan ikke tilordne verdier til dem. Systemfelt blir som standard ikke vist i listen over felter, selv om de finnes i enheten. Hvis du vil se alle feltene, kan du endre filteret på kommandolinjen fra **Standard** til **Alle**.

Hvis du vil ha mer informasjon om metadataene som er knyttet til enheten, kan du se [Enhetsmetadata](../../developer/common-data-service/entity-metadata.md)

## <a name="next-steps"></a>Neste trinn
* [Administrer felter i en enhet](data-platform-manage-fields.md)
* [Definer relasjoner mellom enheter](data-platform-entity-lookup.md)
* [Generer en app ved hjelp av en Common Data Service-database](../canvas-apps/data-platform-create-app.md)
* [Opprett en app fra grunnen av ved hjelp av en Common Data Service-database](../canvas-apps/data-platform-create-app-scratch.md)

## <a name="privacy-notice"></a>Erklæring om personvern
Med den vanlige datamodellen i Microsoft PowerApps samler vi inn og lagrer egendefinerte enhets- og feltnavn i diagnostiseringssystemene.  Vi bruker denne kunnskapen til å forbedre den vanlige datamodellen for kundene våre. Enhets- og feltnavnene som skapere oppretter, hjelper oss med å forstå scenarioene som er typiske i Microsoft PowerApps-fellesskapet og få rede på hull i tjenestens standarddekning for enheter, som eksempelvis skjemaer knyttet til organisasjoner. Dataene i databasetabeller som er knyttet til disse enhetene, blir ikke åpnet eller brukt av Microsoft eller replisert utenfor området hvor databasen er klargjort. Merk deg imidlertid at den egendefinerte enheten og feltnavnene kan repliseres på tvers av områder og blir slettet i henhold til retningslinjene våre for dataoppbevaring. Microsoft tar vare på personvernet ditt, som ytterligere beskrevet i [Klareringssenteret](https://www.microsoft.com/trustcenter/Privacy/default.aspx).

