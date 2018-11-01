---
title: Angi egenskaper for modelldrevne apper med enhetlig grensesnitt i PowerApps | MicrosoftDocs
description: Finn ut hvordan du konfigurerer rutenettkontrollen for appen
keywords: ''
ms.date: 06/06/2018
ms.service: crm-online
ms.custom: null
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
author: Mattp123
ms.assetid: 3ecea4a7-0d18-4ccd-9609-3a62179e9e1b
ms.author: matp
manager: kvivek
ms.reviewer: null
ms.suite: null
ms.tgt_pltfrm: null
caps.latest.revision: 0
topic-status: Drafting
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="specify-properties-for-model-driven-unified-interface-apps"></a>Angi egenskaper for modelldrevne apper med enhetlig grensesnitt

Rammeverket for enhetlig grensesnitt bruker responsive utformingsprinsipper til å gi en optimal visnings- og samhandlingsopplevelse enhver skjermstørrelse eller -retning. Rutenettkontrollen (for visning) er responsiv med modelldrevne apper som bruker rammeverket for enhetlig grensesnitt. Når størrelsen på beholderen reduseres, for eksempel på telefoner og mindre visningsområder, endres rutenettet til en liste. 

Den skrivebeskyttede rutenettkontrollen angir hvordan et rutenett skal tilpasses dynamisk til ulike størrelser. Hvis du er apputvikler og arbeider med en app for enhetlig grensesnitt, kan du konfigurere den skrivebeskyttede rutenettkontrollen og egenskapene for egendefinerte rutenett og lister.
- **Kortskjema-egenskapen**: Bruk et kortskjemaet for lister i stedet for standard listemal. Kortskjemaer inneholder mer informasjon for listeelementer enn standard listemal.
- **Egenskapen Virkemåte for dynamisk tilpassing**: Bruk denne parameteren for å angi at et rutenett skal tilpasses dynamisk til en liste.

## <a name="allow-grid-to-reflow-into-list"></a>Tillat at rutenettet tilpasses dynamisk til liste

Hvis du legger til den skrivebeskyttede rutenettkontroller i kontrollisten, kan du konfigurere følgende funksjoner: 
- Tillat at et rutenett tilpasses dynamisk til en liste på små skjermer, for eksempel mobiler.
- Angi gjengivelsesmodus som bare rutenett eller bare liste.  

1. Åpne [løsningsutforskeren](advanced-navigation.md#solution-explorer).
2. I navigasjonsruten utvider du **Enheter** og velger den aktuelle enheten (for eksempel **Forretningsforbindelse** eller **Kontakt**), og deretter velger du **Legg til kontroll** i kategorien **Kontroller**.

    ![Åpne Legg til kontroll](media/UnifiedInterface_ReadOnlyGrid_AddControl.png "Åpne Legg til kontroll")

3. Velg **Skrivebeskyttet rutenett** fra listen over kontroller, og velg deretter **Legg til**.

    Kontrollen legges til i listen over tilgjengelige kontroller.
   
    ![Velg en kontroll](media/UnifiedInterface_ReadOnlyGrid_SelectControl.png "Velg en kontroll")
    
4. Velg enhetene (**Web**, **Telefon** eller **Nettbrett**) som du vil skrivebeskytte rutenettet for.

    ![Velg enhetstype](media/UnifiedInterface_ReadOnlyGrid_SelectDevice.png "Velg enhetstype")

5. Konfigurer egenskapen **Kortskjema**.

    Du kan bruke egenskapen for kortskjema for å vise listeelementer i stedet for standard listemal. Kortskjemaer inneholder mer informasjon for listeelementer enn standard listemal.    

    a. Velg blyantikonet ved siden av **Kortskjema**.

    ![Rediger kortskjema](media/UnifiedInterface_ReadOnlyGrid_CardForm.png "Rediger kortskjema")

    b.  Velg typene **Enhet** og **Kortskjema**.

    ![Egenskaper for kortskjema](media/UnifiedInterface_ReadOnlyGrid_CardFormProperties.png "Egenskaper for kortskjema")

    c. Velg **OK**.
6. Konfigurer egenskapen **Virkemåte for dynamisk tilpassing**. 
    
    a. Velg blyantikonet ved siden av **Virkemåte for dynamisk tilpassing**.

    ![Rediger Virkemåte for dynamisk tilpassing](media/UnifiedInterface_ReadOnlyGrid_EditReflow.png "Rediger Virkemåte for dynamisk tilpassing")

    b. Velg flyttype for rutenettet fra rullegardinlisten **Bind til statiske alternativer**.
    |Flyttype|Beskrivelse|
    |--------------|--------------------|
    |**Dynamisk tilpassing**|Lar rutenettet gjengis i listemodus avhengig av når det ikke er nok visningplass.|
    |**Bare rutenett**|Begrenser rutenettet til å tilpasses dynamisk til liste selv når det ikke er nok visningplass.|
    |**Bare liste**|Vises bare som en liste, selv om det er nok plass til å vise rutenettet.|
    
     ![Egenskaper for Virkemåte for dynamisk tilpassing](media/UnifiedInterface_ReadOnlyGrid_ReflowProperties.png "Egenskaper for Virkemåte for dynamisk tilpassing")

    c. Velg **OK**.


7.  Lagre og publiser endringene. 


## <a name="conditional-image"></a>Betinget bilde
Du kan vise et egendefinert ikon i stedet for en verdi i en liste, og opprette logikken som brukes for å velge dem basert på verdiene i en kolonne, ved å bruke JavaScript. Hvis du vil ha mer informasjon om betingede bilder, kan du se [Vise egendefinerte ikoner i stedet for verdier i listevisninger](../common-data-service/display-custom-icons-instead.md).

## <a name="next-steps"></a>Neste trinn
[Opprette eller redigere en visning](create-edit-views.md)
