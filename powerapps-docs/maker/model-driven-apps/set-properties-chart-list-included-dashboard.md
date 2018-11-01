---
title: 'Angi egenskaper for et diagram eller en liste over modelldrevne apper som er inkludert i et instrumentbord, i PowerApps | MicrosoftDocs'
description: Finn ut hvordan du angir egenskaper for et diagram eller en liste som er inkludert i et instrumentbord
ms.custom: ''
ms.date: 06/06/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
author: Mattp123
ms.assetid: 50fb2ab0-5c1a-4a5e-8ebc-5603fecc4da0
caps.latest.revision: 26
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="set-properties-for-a-model-driven-app-chart-or-list-included-in-a-dashboard"></a>Angi egenskaper for et diagram eller en liste over modelldrevne apper som er inkludert i et instrumentbord

Hvis du vil redigere et diagram eller en komponent fra redigeringsprogrammet for instrumentbord, velger du diagrammet eller listen du vil ha, og velg deretter Rediger komponent på designerverktøylinjen for instrumentbord.   
  > [!div class="mx-imgBorder"] 
  > ![Instrumentbord-designer, redigere diagramkomponent](media/dashboard-chart-select.png)

Dialogboksen **Angi egenskaper** vises.

  > [!div class="mx-imgBorder"] 
  > ![Angi egenskaper for diagram](media/set-properties-chart.png)  
 
Du kan angi følgende egenskaper for diagrammet fra dialogboksen **Angi egenskaper**:  
  
- **Name**. Unikt navn for diagrammet. Systemet forslår en verdi, men du kan endre den.  
  
- **Etikett**. Etiketten som vises øverst i diagrammet.  
  
- **Vis etikett på instrumentbordet**. Merk av eller fjern avmerkingen hvis du vil vise eller skjule etiketten for diagrammet.  
  
- **Enhet**. Velg enheten (oppføringstype) som diagrammet skal baseres på. Denne innstillingen bestemmer de tilgjengelige verdiene for egenskapene for standardvisning og standarddiagram.  
  
- **Standardvisning**. Velg visningen som skal brukes til å hente dataene for diagrammet.  
  
- **Standarddiagram**. Velg standarddiagrammet du vil vise når instrumentbordet åpnes for første gang. De tilgjengelige verdiene bestemmes av den angitte verdien for egenskapen Enhet. Denne egenskapen fungerer sammen med egenskapen Vis diagramutvalg. En bruker kan endre diagramtypen hvis alternativet **Vis diagramutvalg** er aktivert, men diagrammet går tilbake til Standarddiagram neste gang instrumentbordet åpnes.  
  
- **Vis bare diagram**. Merk av hvis du bare vil vise diagrammet. Fjern avmerkingen hvis du vil vise diagrammet og de tilknyttede dataene.  
  
- **Vis diagramutvalg**. Merk av i denne avmerkingsboksen hvis du vil at brukerne skal kunne endre diagramtypen (kolonne, linje, sektor osv.) når de bruker instrumentbordet. Hvis brukeren endrer diagramtypen, lagres ikke innstillingene. Diagramtypen går tilbake til innstillingen Standarddiagram når instrumentbordet lukkes.  
  
Du kan angi følgende listeegenskaper fra dialogboksen **Angi egenskaper**:  
  
- **Name**. Unikt navn for listen. Systemet forslår en verdi, men du kan endre den.  
  
- **Etikett**. Etiketten som vises øverst i listen.  
  
- **Vis etikett på instrumentbordet**. Merk av eller fjern avmerkingen hvis du vil vise eller skjule etiketten for listen.  
  
- **Enhet**. Velg enheten (oppføringstype) som listen skal baseres på. Denne innstillingen bestemmer de tilgjengelige verdiene for egenskapene for standardvisning.  
  
- **Standardvisning**. Velg visningen som skal brukes til å hente dataene i listen. En bruker kan endre visningen, men listen går tilbake til Standardvisning neste gang instrumentbordet åpnes.  
  
- **Vis søkeboks**. Merk av for dette alternativet hvis du vil vise en søkeboks øverst i listen. Hvis søkeboksen er inkludert, kan du eller andre brukere søke etter oppføringer i listen under kjøring.  
  
- **Vis indeks**. Merk av for dette alternativet hvis du vil vise A til Å filtre nederst i listen. Når A til Å filtre vises, kan du eller andre brukere velge en bokstav for å hoppe til oppføringer som begynner med denne bokstaven.  
  
- **Visningsvelger**. Velg blant følgende verdier:  
  
    - **Av**. Ikke vis visningsvelgeren. Du eller andre brukere vil ikke kunne endre visninger ved kjøretid.  
  
    - **Vis alle visninger**. Gir en fullstendig liste over visninger som er knyttet til verdien som er angitt i egenskapen Enhet.  
  
    - **Vis valgte visninger**. Velg denne innstillingen for å begrense listen over tilgjengelige visninger under kjøring. Hvis du vil velge bestemte visninger som skal vises, holder du nede CTRL og velger hver visning du vil ta med.  
 
## <a name="next-steps"></a>Neste trinn  
 [Opprette eller redigere instrumentbord](create-edit-dashboards.md)
