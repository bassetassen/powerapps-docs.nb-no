---
title: Opprette et alternativsett | Microsoft Docs
description: Trinnvise instruksjoner for hvordan du oppretter et alternativsett.
author: clwesene
manager: kfile
ms.service: powerapps
ms.component: cds
ms.topic: conceptual
ms.date: 03/21/2018
ms.author: clwesene
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="create-an-option-set"></a>Opprette et alternativsett

Med Alternativsett kan du inkludere rullegardinlister med faste verdier for en bruker i appen for å sikre datakonsistens, også referert til som valglister eller valgfelt i andre programmer. På samme måte som med enheter, finnes det både standard alternativsett og mulighet for å opprette egendefinerte alternativsett for bruk i appen.

Alternativsett kan opprettes på to måter, enten fra alternativsettlisten i portalen eller direkte i en enhet under oppretting av et felt. Hvis du vil ha mer informasjon om hvordan du oppretter en enhet, kan du se [Opprette en enhet](data-platform-create-entity.md).

## <a name="creating-an-option-set-while-adding-a-field"></a>Opprette et alternativsett når du legger til et felt.

1. På [powerapps.com](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) utvider du **Data**-delen og klikker eller trykker på **Enheter** i den venstre navigasjonsruten.

    ![Enhetsdetaljer](./media/data-platform-cds-create-entity/entitylist.png "Enhetsliste")

2. Klikk eller trykk på en eksisterende enhet, eller [opprett en ny enhet](data-platform-create-entity.md)

3. Legg til et nytt felt i enheten ved å klikke på **Legg til felt**.

4. I panelet for nytt felt angir du **Visningsnavn** for feltet. **Navn** fylles ut automatisk og brukes som det unike navnet på feltet. **Visningsnavn** brukes når du presenterer dette feltet til brukerne. **Navn** brukes når du bygger appen, i uttrykk og formler.

    > [!div class="mx-imgBorder"] 
    > ![Nytt felt](./media/data-platform-cds-create-entity/newfieldpanel.png "Panelet for nytt felt")

5. Klikk på **Datatype**-rullegardinlisten og velg **Alternativsett** eller **Alternativsett med flere valg**.

6. Klikk på **Alternativsett**-rullegardinlisten og velg **Nytt alternativsett**

    > [!NOTE]
    > Hvis et eksisterende alternativsett kan brukes for enheten, kan du velge det fra listen uten å opprette et nytt.

    ![Liste med alternativsett](./media/data-platform-cds-newoptionset/fieldpanel-1.png "Liste med alternativsett")

7. Et nytt panel åpnes for å opprette alternativsettet. **Visningsnavn** og **Navn** hentes som standard fra navnet på feltet, men du kan endre det om nødvendig. Klikk på **Legg til nytt element** for å begynne oppretting av listen over alternativer. Gjenta dette trinnet til alle elementene er opprettet.

    > [!div class="mx-imgBorder"] 
    > ![Nytt alternativsett](./media/data-platform-cds-newoptionset/field-optionsetpanel.png "Nytt alternativsett")

8. Når du har angitt elementene, klikker du på **Lagre** for å opprette alternativsettet.

    > [!div class="mx-imgBorder"] 
    > ![Nytt alternativsett](./media/data-platform-cds-newoptionset/field-optionsetpanel-values.png "Nytt alternativsett")

9. Klikk på **Ferdig** for å lukke feltpanelet og deretter **Lagre enhet** for å lagre enheten i Common Data Service.

    > [!NOTE]
    > Du kan velge ett av disse elementene som **standard** for dette feltet, og det velges som standard når brukerne oppretter nye oppføringer i enheten.

    > [!div class="mx-imgBorder"] 
    > ![Nytt felt](./media/data-platform-cds-newoptionset/fieldpanel-2.png "Panelet for nytt felt")

## <a name="creating-an-option-set-from-the-option-set-list"></a>Opprette et alternativsett fra listen med alternativsett

1. På [powerapps.com](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) utvider du **Data**-delen og klikker eller trykker på **Alternativsett** i den venstre navigasjonsruten.

    > [!div class="mx-imgBorder"] 
    > ![Alternativsett](./media/data-platform-cds-newoptionset/optionsetlist.png "Alternativsett")

2. Klikk på **Nytt alternativsett**

3. En nytt panel åpnes for å opprette alternativsettet. Angi **Visningsnavn** og **Navn**. Klikk på **Legg til nytt element** for å begynne oppretting av listen over alternativer. Gjenta dette trinnet til alle elementene er opprettet.

    > [!div class="mx-imgBorder"] 
    > ![Oppretting av alternativsett](./media/data-platform-cds-newoptionset/optionset-create.png "Oppretting av alternativsett")

4. Når du har angitt elementene, klikker du på **Lagre** for å opprette alternativsettet.

    > [!div class="mx-imgBorder"] 
    > ![Nytt alternativsett](./media/data-platform-cds-newoptionset/optionset-create-values.png "Nytt alternativsett")

5. Du kan nå bruke dette alternativsettet ved å opprette nytt felt på en enhet.

## <a name="global-and-local-option-sets"></a>Globale og lokale alternativsett

Som standard opprettes alternativsett som globale alternativsett som gjør at de kan brukes på nytt på flere enheter. Under **Vis mer**-alternativet når du oppretter et nytt alternativsett, kan du velge å gjøre et alternativsett **lokalt**. Dette alternativet er bare tilgjengelig når du oppretter et alternativsett mens du legger til et felt, og ikke via listen over alternativsett. Lokale alternativsett kan bare brukes av enheten og feltet de er opprettet for, og kan ikke brukes på nytt på andre enheter. Denne metoden anbefales bare for avanserte brukere som har et bestemt behov for et lokalt alternativsett.

> [!IMPORTANT]
> Når et alternativsett er opprettet som lokal eller global, kan ikke dette endres.
