---
title: Slik oppretter man et alternativsett | Microsoft Docs
description: Trinnvise instruksjoner for hvordan man oppretter et alternativsett.
author: clwesene
manager: kfile
ms.service: powerapps
ms.component: cds
ms.topic: conceptual
ms.date: 03/21/2018
ms.author: clwesene
ms.openlocfilehash: 188add46a8e52cfeb75ef1bb670ca3b457963024
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/04/2018
ms.locfileid: "34168600"
---
# <a name="create-an-option-set"></a>Å opprette et alternativsett

Med alternativsett kan du inkludere rullegardinlister med fastsatte verdier til en bruker i appen for å sikre datakonsekvens. Dette kalles av og til for nedtrekksmenyer eller valgfelt i andre programmer. De ligner på enheter, og det finnes både standard alternativsett eller muligheten for å opprette egendefinerte alternativsett i appen.

Du kan opprette alternativsett på to måter, enten fra listen over alternativsett i portalen eller direkte i en enhet mens du oppretter et felt. Hvis du vil ha mer informasjon om hvordan du oppretter en enhet, kan du se [Å opprette en enhet](data-platform-create-entity.md).

## <a name="creating-an-option-set-while-adding-a-field"></a>Å opprette et alternativsett mens du legger til et felt

1. Utvid **Data**-delen på [powerapps.com](https://web.powerapps.com), og trykk eller klikk på **Enheter** i venstre navigasjonsrute.

    ![Enhetsdetaljer](./media/data-platform-cds-create-entity/entitylist.png "Enhetsliste")

2. Klikk eller trykk på en eksisterende enhet, eller [opprett en ny enhet](data-platform-create-entity.md)

3. Legg til et nytt felt i enheten ved å klikke på **Legg til felt**.

4. I Nytt felt-panelet angir du **visningsnavn** for feltet. **Navn**-feltet blir automatisk utfylt og brukes som det unike navnet for feltet. **Visningsnavnet** brukes ofte når du presenterer dette feltet for brukerne dine, og **Navn**-feltet brukes når du bygger en app, i uttrykk og formler.

    ![Nytt felt](./media/data-platform-cds-create-entity/newfieldpanel.png "Nytt felt-panel")

5. Klikk på rullegardinlisten **Datatype** og velg **Alternativsett**, eller **Flervalg av alternativsett**.

6. Klikk på rullegardinlisten **Alternativsett** og velg **Nytt alternativsett**

    > [!NOTE]
    > Hvis du kan bruke et eksisterende alternativsett for enheten din, kan du velge den fra listen uten å måtte opprette en ny.

    ![Liste over alternativsett](./media/data-platform-cds-newoptionset/fieldpanel-1.png "Liste over alternativsett")

7. Et nytt panel åpnes der du kan opprette alternativsettet, **visningsnavnet** og **navnet** hentes fra feltnavnet. Dette kan endres ved behov. Klikk på **Legg til nytt element** for å opprette listen over alternativer. Gjenta dette trinnet til alle elementene er opprettet.

    ![Nytt alternativsett](./media/data-platform-cds-newoptionset/field-optionsetpanel.png "Nytt alternativsett")

8. Når du er ferdig med å opprette alle elementene, klikker du på **Lagre** for å lagre alternativsettet.

    ![Nytt alternativsett](./media/data-platform-cds-newoptionset/field-optionsetpanel-values.png "Nytt alternativsett")

9. Klikk på **Ferdig** for å lukke feltpanelet, og klikk deretter på **Lagre enhet** for å lagre enheten i Common Data Service.

    > [!NOTE]
    > Du kan velge ett av elementene som **standard** for dette feltet, og det blir valgt som standard når brukerne oppretter nye poster i enheten din.

    ![Nytt felt](./media/data-platform-cds-newoptionset/fieldpanel-2.png "Nytt felt-panel")

## <a name="creating-an-option-set-from-the-option-set-list"></a>Å opprette et alternativsett fra listen over alternativsett

1. Utvid **Data**-delen på [powerapps.com](https://web.powerapps.com), og trykk eller klikk på **Alternativsett** i venstre navigasjonsrute.

    ![Alternativsett](./media/data-platform-cds-newoptionset/optionsetlist.png "Liste over alternativsett")

2. Klikk på **Nytt alternativsett**.

3. Et nytt panel åpnes der du kan opprette alternativsettet, og du angir **visningsnavn** og **navn**. Klikk på **Legg til nytt element** for å opprette listen over alternativer. Gjenta dette trinnet til alle elementene er opprettet.

    ![Å opprette alternativsett](./media/data-platform-cds-newoptionset/optionset-create.png "Å opprette alternativsett")

4. Når du er ferdig med å opprette alle elementene, klikker du på **Lagre** for å lagre alternativsettet.

    ![Nytt alternativsett](./media/data-platform-cds-newoptionset/optionset-create-values.png "Nytt alternativsett")

5. Du kan nå bruke dette alternativsettet ved å opprette et nytt felt i enhet.

## <a name="global-and-local-option-sets"></a>Globale og lokale alternativsett

Alternativsett opprettes som standard som globale alternativsett, noe som gjør at de kan brukes på nytt for flere enheter. Når du oppretter et nytt alternativsett, kan du velge at det er **Lokalt**. Dette gjør du under alternativet **Vis mer**. Dette alternativet er bare tilgjengelig når du oppretter et alternativsett mens du legger til et felt, og ikke gjennom listen over alternativsett. Lokale alternativsett kan brukes av bare enheten og feltet de er opprettet mot, og kan ikke brukes flere ganger for andre enheter. Denne tilnærmingen er bare anbefalt for avanserte brukere som har et spesifikt behov for lokale alternativsett.

> [!IMPORTANT]
> Når alternativet er opprettet som lokalt eller globalt, kan dette ikke endres.