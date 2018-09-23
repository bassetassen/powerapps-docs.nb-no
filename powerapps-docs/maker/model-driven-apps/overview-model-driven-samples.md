---
title: Modelldrevne eksempelapper
description: Forstå hvordan du henter, egendefinerer og fjerner modelldrevne eksempelapper.
documentationcenter: na
author: caburk
manager: kvivek
ms.service: powerapps
ms.devlang: na
ms.topic: conceptual
ms.component: model
ms.date: 03/08/2018
ms.author: caburk
ms.openlocfilehash: 0b34a32281fb4f64bc918de81b3920edf5a7000b
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/08/2018
ms.locfileid: "39664431"
---
# <a name="model-driven-sample-apps"></a>Modelldrevne eksempelapper

I [powerapps.com](https://powerapps.com) kan du bruke en eksempelapp til å utforske utformingsmuligheter og oppdage begreper som du kan bruke når du utvikler apper. Hver eksempelapp bruker fiktive data til å vise et virkelig scenario. 

Sørg for å lese dokumentasjonen som er spesifikk for hver eksempelapp for mer detaljer. 

![Eksempelapp for innsamling](media/overview-model-driven-samples/fundraiser-app1.png)


## <a name="get-sample-apps"></a>Å hente eksempelapper

Hvis du ønsker å spille av eller redigere modelldrevne eksempelapper, må appene først klargjøres i Common Data Service-databasen. Du oppretter først prøvemiljø og -database, og sørg for at du merker av for **Inkluder eksempelapper and -data**.

![Å opprette en database](media/overview-model-driven-samples/create-database1.png)


> [!IMPORTANT]
> Dette alternativet installerer alle tilgjengelige eksempelapper i databasen. Eksempelapper brukes for utdannings- og demonstrasjonsformål, og vi anbefaler ikke at du installerer dem i produksjonsdatabaser. 

## <a name="customize-a-sample-app"></a>Å egendefinere en eksempelapp

1. Logg deg på [powerapps.com](https://powerapps.com), og velg **Modelldrevet** for utformingsmodus. 

    ![Å velge en utformingsmodus](media/overview-model-driven-samples/choose-design-mode.png)

2. Beveg pekeren over eksempelappen på startskjermen og klikk på **Egendefiner**.
3. Apputformingsprogrammet åpnes og gir deg mange alternativer for egendefinering av appen. 
4. Hvis du ønsker flere alternativer for egendefinering, klikker du på **Avansert** fra navigasjonen til venstre i portalen.

## <a name="remove-sample-apps-and-data"></a>Å fjerne eksempelapper og -data 
- Hvis du sletter en eksempelapp, må du også slette den tilsvarende  [administrerte løsningen](https://docs.microsoft.com/dynamics365/customer-engagement/developer/uninstall-delete-solution). 
- Hvis du sletter løsningen, så slettes også eventuelle spesifikke eksempeldata for de egendefinerte enhetene i appen.
- Hvis det ble foretatt endringer i eksempelappen, kan det hende det finnes [avhengigheter](https://docs.microsoft.com/dynamics365/customer-engagement/developer/dependency-tracking-solution-components). Dette må fjernes før du kan slette løsningen.

### <a name="steps"></a>Trinn
1. Logg deg på [administrasjonsportalen for PowerApps](https://admin.powerapps.com).

2. Velg et miljø.

3. Klikk på **administrasjonssenteret for Dynamics 365**. 

    ![Administrasjonssenteret for Dynamics 365](media/overview-model-driven-samples/admin-center.png)

4. Velg databasen fra listen, og klikk på **ÅPNE**.

    ![Å velge database](media/overview-model-driven-samples/select-database.png)

5. Gå til **Innstillinger/Løsninger**.

6. Velg løsningen for appen som skal slettes, og klikk deretter på **Slett**.

    ![Å slette løsningen](media/overview-model-driven-samples/delete-solution.png)

*Du kan alternativt gå til listen over løsninger ved å klikke på **Avansert** i Maker-portalen og slette alt i nettadressen etter .dynamics.com/*

> [!IMPORTANT]
> Slett ikke andre systemløsninger med mindre du er klar over innvirkningen av dette.

## <a name="install-or-uninstall-sample-data"></a>Å installere eller avinstallere eksempeldata
1. Følg trinnene 1-4 ovenfor.
2. Gå til **Innstillinger/Dataadministrasjon/Eksempeldata**.
3. Hvis eksempeldata er installert, er alternativet for å fjerne tilgjengelig. Ellers så er alternativet for å installere tilgjengelig. 

    ![Å fjerne eksempeldata](media/overview-model-driven-samples/remove-sample-data.png)




