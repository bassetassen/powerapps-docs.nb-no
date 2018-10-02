---
title: Distribuere en modelldreven app ved hjelp av en løsning | MicrosoftDocs
description: Finn ut hvordan du distribuerer en modelldreven app ved hjelp av løsninger
keywords: ''
ms.date: 08/06/2018
ms.service: crm-online
ms.custom: null
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
ms.assetid: e82e7f64-37ad-41e5-acd7-16309881c6a2
author: Mattp123
ms.author: matp
manager: kvivek
ms.reviewer: null
ms.suite: null
ms.tgt_pltfrm: null
caps.latest.revision: 9
topic-status: Drafting
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="distribute-a-model-driven-app-using-a-solution"></a>Distribuere en modelldreven app ved hjelp av en løsning

Modelldrevne apper distribueres som løsningskomponenter. Når du har laget en modelldrevet app, kan du gjøre den tilgjengelig for andre miljøer ved å pakke appen i en løsning og deretter eksportere den til en ZIP-fil. Når løsningen (ZIP-filen) er importert i målmiljøet, er den pakkede appen tilgjengelig for bruk. 
  
## <a name="add-an-app-to-a-solution"></a>Legge til en app i en løsning
For å kunne distibute appen må du opprette en løsning slik at appen kan pakkes for eksport.

1. På [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)-området velger du **Modelldrevet** (nederst til venstre i navigasjonsruten).  

    ![Modelldrevet utformingsmodus](media/model-driven-switch.png)

2. Velg **Løsninger** og deretter **Ny løsning**.
3. Fyll ut feltene på siden **Ny løsning**, og velg deretter **Lagre**. Mer informasjon: [Opprette en løsning](../common-data-service/create-solution.md)
4. Siden **Løsning** vises. Velg **Legg til eksisterende**, velg **App**, velg appen du vil legge til i løsningen, og velg deretter **OK**. 

    ![Velg løsningskomponenter](media/select-solution-components.png)

5. Hvis siden **Mangler obligatoriske komponenter** vises, anbefaler vi at du velger **Ja, ta med nødvendige komponenter** for å legge til nødvendige komponenter, for eksempel enheter, visninger, skjemaer, diagrammer og områdekartet, som er en del av appen. Velg **OK**.
6. På **Løsning**-siden velger du **Lagre og lukk**.

## <a name="export-a-solution"></a>Eksportere en løsning
For å distribuere appen din, slik at den kan importeres til andre miljøer eller gjøres tilgjengelig i [Microsoft AppSource](https://appsource.microsoft.com/), eksporter løsningen til en zip-fil. Deretter kan zip-filen som inneholder appen og komponentene, importeres til andre miljøer.

1. Åpne [Løsninger-siden](advanced-navigation.md#solutions). 
2. Velg løsningen du vil eksportere, og velg deretter **Eksporter** på verktøylinjen. 
3. På siden **Publiser tilpassinger** velger du **Neste**.
4. Hvis siden **Mangler obligatoriske komponenter** vises, velger du **Neste**. 
5. På siden **Eksporter systeminnstillinger** velger du de valgfrie funksjonene du vil ta med, og velg deretter **Neste**. 
6. På siden **Pakketype** velger du **Uadministrert** eller **Administrert** og velger deretter **Eksporter**. For mer informasjon om løsningspakketyper, se [Løsningsoversikt](../common-data-service/solutions-overview.md).
7. Avhengig av nettleseren og innstillingene bygges en ZIP-pakkefil og kopieres til standardmappen for nedlastinger. Navnet på pakken er basert på det unike navnet på løsningen med understrekingstegn og versjonsnummeret for løsningen.

    > [!NOTE]
    > Når du eksporterer en app ved hjelp av en løsning, eksporteres ikke URL-adressen for appen.
  
## <a name="import-a-solution"></a>Importere en løsning  
Når du mottar en løsnings-ZIP-fil som inneholder appen som du vil importere, åpner du siden for løsningskomponenten og importerer løsningen. Når løsningen er importert, er appen tilgjengelig i miljøet.

1. På [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)-området velger du **Modelldrevet** (nederst til venstre i navigasjonsruten).  

    ![Modelldrevet utformingsmodus](media/model-driven-switch.png)

2. Velg **Løsninger** og deretter **Importer** på verktøylinjen.
3. Bla til filen du vil importere, og velg deretter **Neste**.
4. Velg **Importer**.

## <a name="see-also"></a>Se også
[Endre løsningsutgiverprefikset](../common-data-service/change-solution-publisher-prefix.md)
