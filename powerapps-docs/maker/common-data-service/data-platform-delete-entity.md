---
title: Slette en egendefinert enhet | Microsoft Docs
description: Trinnvise instruksjoner for hvordan du sletter en egendefinert enhet og fjerner alle data i PowerApps
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

# <a name="delete-a-custom-entity"></a>Slette en egendefinert enhet
Du kan slette egendefinerte enheter, men du kan ikke slette standardenheter.

1. På [powerapps.com](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) utvider du **Data**-delen og klikker eller trykker på **Enheter** i den venstre navigasjonsruten.

    ![Enhetsdetaljer](./media/data-platform-cds-create-entity/entitylist.png "Enhetsliste")

2. I listen over enheter klikker eller trykker du på enheten du vil slette, og klikker eller trykker deretter på **Slett enhet**-alternativet på kommandolinjen.

3. I dialogboksen som vises, klikker eller trykker du på **Slett** for å slette enheten.

>[!NOTE]
>Når du sletter en enhet, sletter du både enhetsdefinisjonen og alle data som enheten inneholder. Enheter og dataene i dem kan ikke gjenopprettes hvis de er slettet.

>[!NOTE]
>Du kan ødelegge en app eller flyt hvis du sletter en enhet som brukes i denne appen.

>[!NOTE]
>Hvis enhet A har [oppslagsfelt](data-platform-entity-lookup.md) til enhet B, må du kanskje slette enhet B før du kan slette enhet A.

