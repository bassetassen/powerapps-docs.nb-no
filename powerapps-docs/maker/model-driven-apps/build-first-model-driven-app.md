---
title: Hurtigveiledning til bygging av din første modelldrevne app fra grunnen av med PowerApps | Microsoft Docs
description: Lær hvordan du bygger en enkel modelldrevet app
documentationcenter: ''
author: Mattp123
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: conceptual
ms.component: model
ms.date: 04/18/2018
ms.author: matp
ms.openlocfilehash: c1c03202cb95500bb019a3c23a68e0e8d5418cc9
ms.sourcegitcommit: 79b8842fb0f766a0476dae9a537a342c8d81d3b3
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 07/07/2018
ms.locfileid: "37898402"
---
# <a name="quickstart-build-your-first-model-driven-app-from-scratch"></a>Hurtigstart: Bygg din første modelldrevne app fra grunnen av
Utforming av modelldrevne apper er en komponentfokusert tilnærming til apputvikling. I denne hurtigveiledningen oppretter du en modelldrevet app på en forenklet måte ved å bruke en av standardenhetene som er tilgjengelige i [!INCLUDE [powerapps](../../includes/powerapps.md)]-miljøet ditt. 

## <a name="sign-in-to-powerapps"></a>Logg deg på PowerApps
Logg deg på [PowerApps](https://web.powerapps.com/). Hvis du ikke allerede har en [!INCLUDE [powerapps](../../includes/powerapps.md)]-konto, velger du koblingen **Kom i gang gratis**. 

## <a name="create-your-model-driven-app"></a>Lag den modelldrevne appen

1. Velg miljøet du vil bruke, eller gå til [administrasjonssenteret for PowerApps](https://admin.powerapps.com/) for å opprette et nytt.
2. I navigasjonsruten til venstre velger du **Model-driven** (Modelldrevet). 

   ![Modelldrevet](media/build-first-model-driven-app/choose-design-mode.png)

   > [!IMPORTANT]
   > Hvis den **modelldrevne** utformingsmodusen ikke er tilgjengelig, må du kanskje [opprette et miljø](https://docs.microsoft.com/powerapps/administrator/create-environment).   

3. I ruten til venstre velger du **Apps** (Apper) og deretter **Create an app** (Opprett en app).

4. På siden **Create a New App** (Opprett en ny app) skriver du inn følgende informasjon og velger deretter **Done** (Fullført): 
   - **Name** (Navn): Skriv inn et navn på appen, for eksempel *Minførsteapp*. 
   - **Description** (Beskrivelse): Skriv inn en kort beskrivelse av hva appen er eller gjør, for eksempel *Dette er min første app*.
   Du finner informasjon om ytterligere appegenskaper i [Opprette en app](https://docs.microsoft.com/dynamics365/customer-engagement/customize/create-edit-app#create-an-app).
 
   ![Opprett-ny-app](media/build-first-model-driven-app/create-new-app.png)

## <a name="add-components-to-your-app"></a>Legg til komponenter i appen din
Fra verktøyet for apputforming kan du legge til komponenter i appen.
1. Velg pilen for **Open the Site Map Designer** (Åpne verktøy for utforming av områdekart) for å åpne verktøyet for utforming av områdekart. 

   ![Opprett-nytt-områdekart](media/build-first-model-driven-app/new-sitemap.png)

2. I verktøyet for utforming av områdekart velger du **New Subarea** (Nytt underområde). I ruten til høyre velger du fanen **Properties** (Egenskaper) og deretter følgende egenskaper.
   - **Type** (Type): Entity (Enhet)
   - **Entity** (Enhet): Account (Konto)

   ![Legg til komponenter i områdekartet](media/build-first-model-driven-app/sitemap.png)

3. Velg **Save And Close** (Lagre og lukk).
4. På apputformingslerretet velger du **Forms** (Skjemaer). Under gruppen **Main Forms** (Hovedskjemaer) i ruten til høyre velger du deretter skjemaet **Account** (Konto).

   ![Hovedskjema for konto](media/build-first-model-driven-app/main-form.png)

5. På apputformingslerretet velger du **Views** (Visninger). Deretter velger du visningene **Active Accounts** (Aktive kontoer), **All Accounts** (Alle kontoer) og **My Active Accounts** (Mine aktive kontoer).

   ![Kontovisninger](media/build-first-model-driven-app/views.png)

6. På apputformingslerretet velger du **Charts** (Diagrammer). Deretter velger du diagrammet **Accounts by Industry** (Kontoer etter bransje).
7. På verktøylinjen i apputformingen velger du **Save** (Lagre).

    ![Lagre på verktøylinjen i apputformingen](media/build-first-model-driven-app/app-designer-toolbar.png)
 
<!-- ##  Validate your app
This step checks for component dependencies that are required for the app to work, but haven't yet been added to the app. 

1. On the app designer canvas, select the component that indicates a dependency, such as the **Forms** component. Then, on the right-pane select the **Required** tab, expand **Entity Dependencies** and then select all required dependencies. 

    ![Add dependencies](media/build-first-model-driven-app/resolve-dependencies.png)

2. Select **Add Dependencies**.
3. On the app designer toolbar, select **Save**.  -->

## <a name="publish-your-app"></a>Publiser appen din
På verktøylinjen i apputformingen velger du **Publish** (Publiser).

Når du har publisert appen, kan du kjøre den eller dele den med andre.

![En enkel kontoenhetsapp](media/build-first-model-driven-app/accounts-quickstart-app.png)

## <a name="next-steps"></a>Neste trinn
I denne hurtigveiledningen laget du en enkel modelldrevet app. Hvis du vil se hvordan appen din ser ut når du kjører den, kan du se [Quickstart: Run a model-driven app on a mobile device](../../user/run-app-client-model-driven.md) (Hurtigstart: Kjør en modelldrevet app på en mobilenhet).
Hvis du vil lære hvordan du deler appen din, går du videre til opplæringen for hvordan du deler en modelldrevet app, [Dele en modelldrevet app](share-model-driven-app.md).
