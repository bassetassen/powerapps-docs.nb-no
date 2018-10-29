---
title: Angi egenskaper for apper med modelldrevet enhetlig grensesnitt i PowerApps | MicrosoftDocs
description: Lær hvordan du konfigurerer rutenettkontrollen for appen
keywords: ''
ms.date: 06/06/2018
ms.service: crm-online
ms.custom: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
author: Mattp123
ms.assetid: 3ecea4a7-0d18-4ccd-9609-3a62179e9e1b
ms.author: matp
manager: kvivek
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
caps.latest.revision: 0
topic-status: Drafting
ms.openlocfilehash: 007ac566e317ee99bd85ab0675e5a53839800bb4
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/08/2018
ms.locfileid: "39691603"
---
# <a name="specify-properties-for-model-driven-unified-interface-apps"></a>Angi egenskaper for apper med modelldrevet enhetlig grensesnitt

Rammeverket for enhetlig grensesnitt bruker prinsipper for responsiv utforming til å gi en optimal visning og samhandling for enhver skjermstørrelse eller retning. Rutenettkontrollen (visning) gir respons for modelldrevne apper som bruker rammeverket for enhetlig grensesnitt. Når størrelsen på beholderen avtar – for eksempel på telefoner og mindre visningsområder – blir rutenettet transformert til en liste. 

Den skrivebeskyttede rutenettkontrollen angir hvordan et rutenett skal tilpasses dynamisk til ulike skjermstørrelser. Hvis du arbeider med en enhetlig grensesnitt-app som app-oppretter, kan du konfigurere rutenettkontrollen for skrivebeskyttelse, og egenskapene for egendefinert rutenett og lister.
- **Kortskjema**-egenskapen: Bruk et kortskjema for lister i stedet for standard listemalen. Kortskjemaer gir mer informasjon for listeelementer enn standard listemal.
- Egenskapen **Virkemåte for Dynamisk tilpassing**: Bruk denne parameteren til å angi om et rutenett skal ha dynamisk tilpasning i en liste eller ikke.

## <a name="allow-grid-to-reflow-into-list"></a>Tillat en dynamisk tilpassing av rutenett for liste

Ved å legge til den skrivebeskyttede rutenettkontrollen til listen over kontroller kan du konfigurere følgende funksjoner: 
- Tillat en dynamisk tilpassing av rutenett for en liste på små skjermer, som en mobiltelefon.
- Angi gjengivelsesmodus som bare et rutenettet eller bare en liste.  

1. Åpne [løsningsutforsker](advanced-navigation.md#solution-explorer).
2. Utvid **Enheter** i navigasjonsruten, velg den aktuelle enheten (som **Kontoen** eller **Kontakt**), og velg deretter **Legg til kontroll** på **Kontroller**-fanen.

    ![Åpne legg til kontroll](media/UnifiedInterface_ReadOnlyGrid_AddControl.png "Åpne Legg til kontroll")

3. Velg **Skrivebeskyttet rutenett** fra listen over kontroller, og velg deretter **Legg til**.

    Kontrollen er lagt til i listen over tilgjengelige kontroller.
   
    ![Velg en kontroll](media/UnifiedInterface_ReadOnlyGrid_SelectControl.png "Velg en kontroll")
    
4. Velg enhetene (**Nett**, **Telefon**, eller **Nettbrett**) hvor du vil skrivebeskytte rutenettet.

    ![Velg enhetstypen](media/UnifiedInterface_ReadOnlyGrid_SelectDevice.png "Velg enheter")

5. Konfigurer **Kortskjema**-egenskapen.

    Du kan bruke kortskjema-egenskapen til å vise listeelementer i stedet for standard-listemal. Kortskjemaer gir mer informasjon for listeelementer enn standard listemal.    

    a. Velg blyantikonet ved siden av **Kortskjema**.

    ![Rediger kortskjema](media/UnifiedInterface_ReadOnlyGrid_CardForm.png "Rediger kortskjema")

    b.  Velg **Enheten**- og **Kortskjema**-typer.

    ![Kortskjema-egenskaper](media/UnifiedInterface_ReadOnlyGrid_CardFormProperties.png "Kortskjema-egenskaper")

    c. Velg **OK**.
6. Konfigurer egenskapen **Virkemåte for dynamisk tilpassing**. 
    
    a. Velg blyantikonet ved siden av **Virkemåte for dynamisk tilpassing**.

    ![Rediger virkemåte for dynamisk tilpassing](media/UnifiedInterface_ReadOnlyGrid_EditReflow.png "Rediger virkemåte for dynamisk tilpassing")

    b. Velg rutenett-type for dynamisk tilpassing fra **Alternativer for bind til statisk**-rullegardin.
    |Flyttype|Beskrivelse|
    |--------------|--------------------|
    |**Dynamisk tilpassing**|Tillater gjengivelse av rutenett til listemodus avhengig av om det er nok plass på skjermen.|
    |**Bare rutenett**|Begrenser dynamisk tilpassing av rutenett for en liste, selv når det ikke er nok plass på skjermen.|
    |**Bare liste**|Vises bare som en liste, selv når det er nok plass til å vise som rutenett.|
    
     ![Egenskaper for virkemåte for dynamisk tilpassing](media/UnifiedInterface_ReadOnlyGrid_ReflowProperties.png "Egenskaper for virkemåte for dynamisk tilpassing")

    c. Velg **OK**.


7.  Lagre og publiser endringene. 


## <a name="conditional-image"></a>Betinget bilde
Du kan vise et egendefinert ikon i stedet for en verdi i en liste, og etablere logikken som brukes til å velge dem basert på verdier for en kolonne ved hjelp av JavaScript. Hvis du vil ha mer informasjon om betingede bilder, kan du se [Vis egendefinerte ikoner i stedet for verdier i listevisninger](../common-data-service/display-custom-icons-instead.md).

## <a name="next-steps"></a>Neste trinn
[Opprett eller rediger en visning](create-edit-views.md)