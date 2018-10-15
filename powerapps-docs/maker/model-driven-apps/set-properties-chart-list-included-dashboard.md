---
title: Angi egenskaper for et modelldrevet appdiagram eller en modelldrevet liste i et instrumentbord i PowerApps | MicrosoftDocs
description: Finn ut hvordan du angir egenskaper for et diagram eller en liste på et instrumentbord
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
ms.openlocfilehash: c88fef0412060516ef448c89f5ddfdc9cad00e20
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/08/2018
ms.locfileid: "39695771"
---
# <a name="set-properties-for-a-model-driven-app-chart-or-list-included-in-a-dashboard"></a>Angi egenskaper for et modelldrevet appdiagram eller en modelldrevet liste på et instrumentbord

Hvis du vil redigere en diagram- eller listekomponent fra instrumentbordutforming, velger du diagrammet eller listen du ønsker, og velger Rediger komponent, på verktøylinjen for instrumentbordutforming.   

  ![Diagramredigeringskomponent for instrumentbordutforming](media/dashboard-chart-select.png)

Dette åpner dialogboksen **Angi egenskaper**.

  ![Angitte diagramegenskaper](media/set-properties-chart.png)  
 
Du kan angi følgende diagramegenskaper i dialogboksen **Angi egenskaper**:  
  
- **Navn**. Unikt navn for diagrammet. Systemet foreslår en verdi, men du kan endre den.  
  
- **Etikett**. Etiketten som vises øverst i diagrammet.  
  
- **Vis etikett på instrumentbordet**. Merk eller fjern merket i boksen for å vise eller skjule diagrametiketten.  
  
- **Enhet**. Velg hvilken enhet (posttype) diagrammet skal baseres på. Denne innstillingen bestemmer hvilke verdier som er tilgjengelige for egenskapene for standardvisning og standarddiagram.  
  
- **Standardvisning**. Velg visningen som brukes til å hente dataene for diagrammet.  
  
- **Standarddiagram**. Velg standarddiagrammet du vil skal vises når instrumentbordet åpnes. Tilgjengelige verdier bestemmes av verdien som er angitt for enhetsegenskapen. Denne egenskapen fungerer sammen med egenskapen Vis diagramutvalg. En bruker kan endre diagramtypen hvis alternativet **Vis diagramutvalg** er slått på, men diagrammet går tilbake til standarddiagram neste gang instrumentbordet åpnes.  
  
- **Vis bare diagram**. Merk denne boksen hvis du vil vise bare diagrammet. Fjern merket i boksen hvis du vil vise diagrammet og tilknyttede data.  
  
- **Vis diagramutvalg**. Merk denne boksen for å la brukere endre diagramtype (kolonne, stolpe, sektor osv.) når de bruker instrumentbordet. Hvis brukeren endrer diagramtypen, lagres ikke innstillingene. Diagramtypen går tilbake til standardinnstillingen for diagrammer når instrumentbordet lukkes.  
  
Du kan angi følgende listeegenskaper i dialogboksen **Angi egenskaper**:  
  
- **Navn**. Unikt navn for listen. Systemet foreslår en verdi, men du kan endre den.  
  
- **Etikett**. Etiketten som vises øverst i listen.  
  
- **Vis etikett på instrumentbordet**. Merk eller fjern merket i boksen for å vise eller skjule listeetiketten.  
  
- **Enhet**. Velg hvilken enhet (posttype) listen skal baseres på. Denne innstillingen bestemmer hvilke verdier som er tilgjengelige for egenskapen for standardvisning.  
  
- **Standardvisning**. Velg visningen som brukes til å hente dataene i listen. En bruker kan endre visningen, men listen går tilbake til standardvisning neste gang instrumentbordet åpnes.  
  
- **Vis søkeboks**. Merk denne boksen hvis du vil vise en søkeboks øverst i listen. Hvis søkeboksen er inkludert, kan du eller andre brukere søke etter poster i listen under kjøring.  
  
- **Vis indeks**. Merk denne boksen hvis du vil vise A-til-Z-filtre nederst i listen. Når A-til-Z-filtre vises, kan du eller andre brukere kan velge en bokstav for å hoppe til postene som begynner med denne bokstaven.  
  
- **Visningsvelger**. Velg blant følgende verdier:  
  
    - **Av**. Ikke vis visningsvelgeren. Du eller andre brukere vil ikke kunne endre visninger under kjøring.  
  
    - **Vis alle visninger**. Oppgi en fullstendig liste over visninger som er tilknyttet verdien som er angitt i enhetsegenskapen.  
  
    - **Vis valgte visninger**. Velg denne innstillingen for å begrense visningslisten som er tilgjengelig under kjøring. Hvis du vil at bestemte visninger skal vises, holder du nede CTRL-tasten og trykker på eller merker hver visning du vil inkludere.  
 
## <a name="next-steps"></a>Neste trinn  
 [Opprett eller tilpass instrumentbord](create-edit-dashboards.md)
