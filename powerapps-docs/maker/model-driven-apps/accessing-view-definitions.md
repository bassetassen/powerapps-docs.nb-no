---
title: Få tilgang til en modelldrevet appvisningsdefinisjon | MicrosoftDocs
description: I dette emnet lærer du hvordan du får tilgang til enhetsvisninger
ms.custom: ''
ms.date: 06/12/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - PowerApps
author: Mattp123
ms.assetid: 034c8bef-0d1c-4ef9-8da7-f81343c4553a
caps.latest.revision: 25
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="access-a-model-driven-app-view-definition-in-powerapps"></a>Få tilgang til en modelldrevet appvisningsdefinisjon i PowerApps

 I dette emnet kan du åpne en visningsdefinisjon for å vise egenskapene og alternativene for å konfigurere visningen. Du kan få tilgang til visningsdefinisjoner på flere måter i PowerApps. 
  
  
## <a name="open-a-view-in-powerapps"></a>Åpne en visning i PowerApps

1.  Logg på [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc).  


    > [!IMPORTANT]
    > "Hvis utformingsmodusen **Modelldrevet** ikke er tilgjengelig, må du kanskje [opprette et miljø](https://docs.microsoft.com/powerapps/administrator/create-environment). 

2.  Utvid **Data**, velg **Enheter**, og velg deretter **Forretningsforbindelse**-enheten.   
3. Velg kategorien **Visninger**, og velg deretter **Fjern filter**.

    > [!div class="mx-imgBorder"] 
    > ![Visningsdefinisjoner for forretningsforbindelse](media/account-view-definitions.png)

4. Velg visningen du vil åpne, for eksempel forretningsforbindelsesenheten **Alle forretningsforbindelser**-visningen.

    > [!div class="mx-imgBorder"] 
    > ![Alle forretningsforbindelser-visningen](media/all-accounts-view.png)

5. Fra visningsredigeringsprogrammet kan du utføre flere oppgaver: 
 
- [Sortere oppføringer i en visning](configure-sorting.md)
- [Velge og konfigurere kolonner i visninger](choose-and-configure-columns.md)
- [Bruke egendefinerte kontroller for datavisualiseringer](use-custom-controls-data-visualizations.md) 

## <a name="open-a-view-from-an-app"></a>Åpne en visning fra en app

Du finner følgende kommandoer på kommandolinjen i enhver listevisning for en enhet etter at du har valgt ellipseknappen (...):  
- **Vis**: Åpner definisjonen av gjeldende visning i standardløsningen.  
  
- **Ny systemvisning**: Åpner et nytt vindu for å opprette en ny visning for gjeldende enhet i standardløsningen.  
  
- **Tilpass enhet**: Tar deg til definisjonen av gjeldende enhet i standardløsningen, der du deretter kan velge **Visninger**.  
  
- **Systemvisninger**: Åpner samme vindu som **Tilpass enhet**, men denne gang med **Visninger** valgt.  

## <a name="open-a-view-in-solution-explorer"></a>Åpne en visning i løsningsutforskeren 
  
1.  Åpne [løsningsutforskeren](advanced-navigation.md#solution-explorer).  
  
2.  Vis **Enheter** under **Komponenter**, og vis deretter ønsket enhet.  
  
3.  Velg **Visninger**.  
  
4.  Dobbeltklikk visningen du vil åpne.  
  
 Denne listen over visninger har fire filtre du kan bruke til å søke etter ønskede visninger på en enklere måte:  
  
    - **Alle aktive visninger**  
  
    - **Aktive offentlige visninger**  
  
    - **Inaktive offentlige visninger**  
  
    - **Aktive systemdefinerte visninger**  
  
 Hvis enheten som visningen er knyttet til, er en del av en uadministrert løsning, kan du likevel opprette eller redigere visninger for denne enheten i standardløsningen. Systemvisninger er knyttet til en enhet og er ikke tilgjengelige som separate løsningskomponenter. I motsetning til felt bruker ikke visninger et tilpassingsprefiks i et unikt navn som må være konsekvent i en løsning. Dermed trenger du ikke å opprette visninger i sammenheng med en løsning. 
 
## <a name="next-steps"></a>Neste trinn
[Forstå visninger](create-edit-views.md)


