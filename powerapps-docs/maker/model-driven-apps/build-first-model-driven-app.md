---
title: Lage din første modelldrevne app fra bunnen med PowerApps | Microsoft Docs
description: Finn ut hvordan du lager en enkel modelldrevet app
documentationcenter: ''
author: Mattp123
manager: kvivek
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: conceptual
ms.component: model
ms.date: 04/18/2018
ms.author: matp
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="build-your-first-model-driven-app-from-scratch"></a>Lage din første modelldrevne app fra bunnen
Modelldrevet apputforming er en komponentfokusert metode for apputvikling. I dette emnet forenkler du hvordan du oppretter en modelldrevet app ved hjelp av standardenhetene som er tilgjengelige i PowerApps-miljøet.

> [!TIP]
> Start her for å lære alt om utvikling av modelldrevne apper: [Forstå modelldrevne appkomponenter](model-driven-app-components.md). 

## <a name="sign-in-to-powerapps"></a>Logg på PowerApps
Logg på [PowerApps](https://web.powerapps.com/). Hvis du ikke allerede har en [!INCLUDE [powerapps](../../includes/powerapps.md)]-konto, velger du **Kom i gang gratis**-koblingen. 

## <a name="create-your-model-driven-app"></a>Opprette modelldrevet app

1.  Velg miljøet du vil bruke, eller gå til [PowerApps-administrasjonssenteret](https://admin.powerapps.com/) for å opprette et nytt.
2.  Velg **Modelldrevet** fra den venstre navigasjonsruten. 

    ![Modelldrevet](media/build-first-model-driven-app/choose-design-mode.png)

  > [!IMPORTANT]
  > Hvis utformingsmodusen **Modelldrevet** ikke er tilgjengelig, må du kanskje [opprette et miljø](https://docs.microsoft.com/powerapps/administrator/create-environment).   

3. Velg **Apper** fra den venstre ruten, og velg deretter **Opprett en app**.

4.  På **Opprett en ny app**-siden angir du følgende detaljer, og velger deretter **Ferdig**: 
  - **Navn**: Angi et navn på appen, for eksempel *MinFørsteApp*. 
  - **Beskrivelse**: Skriv inn en kort beskrivelse av hva appen er eller gjør, for eksempel *Dette er den første appen min*.
For informasjon om de ekstra appegenskapene, kan du se [Opprette en app](https://docs.microsoft.com/dynamics365/customer-engagement/customize/create-edit-app#create-an-app).
 
    ![Opprette ny app](media/build-first-model-driven-app/create-new-app.png)

## <a name="add-components-to-your-app"></a>Legge til komponenter i appen
Fra apputformingen kan du legge til komponenter i appen.
1.  Velg **Åpne områdekartutforming**-pilen for å åpne områdekartutformingen. 

    ![Opprette nytt områdekart](media/build-first-model-driven-app/new-sitemap.png)

2.  Velg **Nytt underområde** i områdekartutformingen , i den høyre ruten velger du **Egenskaper**-kategorien, og velg deretter følgende egenskaper.
  - **Type**: Enhet
  - **Enhet**: Forretningsforbindelse

    ![Legge til komponenter i områdekartet](media/build-first-model-driven-app/sitemap.png)

3.  Velg **Lagre og lukk**.
4.  I apputformingslerretet velger du **Skjemaer**, og deretter i den høyre ruten under **Hovedskjemaer**-gruppen velger du **Forretningsforbindelse**-skjemaet.

    ![Hovedskjema for forretningsforbindelse](media/build-first-model-driven-app/main-form.png)

5.  I apputformingslerretet velger du **Visninger**, og deretter velger du visningene **Aktive forretningsforbindelser**, **Alle forretningsforbindelser** og **Mine aktive forretningsforbindelser**.

    ![Forretningsforbindelsesvisninger](media/build-first-model-driven-app/views.png)

6. I apputformingslerretet velger du **Diagrammer**, og deretter velger du **Forretningsforbindelser etter bransje**-diagrammet.
7. Velg **Lagre** på verktøylinjen for apputforming.

    ![Lagre på verktøylinjen for apputforming](media/build-first-model-driven-app/app-designer-toolbar.png)
 
<!-- ##  Validate your app
This step checks for component dependencies that are required for the app to work, but haven't yet been added to the app. 

1. On the app designer canvas, select the component that indicates a dependency, such as the **Forms** component. Then, on the right-pane select the **Required** tab, expand **Entity Dependencies** and then select all required dependencies. 

    ![Add dependencies](media/build-first-model-driven-app/resolve-dependencies.png)

2. Select **Add Dependencies**.
3. On the app designer toolbar, select **Save**.  -->

## <a name="publish-your-app"></a>Publisere appen
Velg **Publiser** på verktøylinjen for apputforming.

Når publiseringen av appen er ferdig, er den klar til å kjøres eller deles med andre.

![Enkel app for forretningsforbindelsesenheten](media/build-first-model-driven-app/accounts-quickstart-app.png)

## <a name="next-steps"></a>Neste trinn
I dette emnet skal du lage en enkel modelldrevet app. 
- Hvis du vil se hvordan appen din ser ut når du kjører den, kan du se [Kjør en modelldrevet app på en mobilenhet](../../user/run-app-client-model-driven.md).
- Hvis du vil vite hvordan du deler appen, kan du se [Dele en modelldrevet app](share-model-driven-app.md).
- For å komme i gang og lære alt om utvikling av modelldrevne apper, kan du se [Forstå modelldrevne appkomponenter](model-driven-app-components.md).
