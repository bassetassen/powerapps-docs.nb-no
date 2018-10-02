---
title: Opprette eller redigere en modelldrevet appvisning i PowerApps | MicrosoftDocs
description: Lær hvordan du oppretter eller redigerer en visning
ms.custom: ''
ms.date: 06/11/2018
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
ms.assetid: bd1d393d-16ea-40ac-8136-26643c37dd2a
caps.latest.revision: 25
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="create-or-edit-a-model-driven-app-view"></a>Opprette eller redigere en modelldrevet appvisning

<a name="BKMK_CreatingAndEditingViews"></a>   

 I dette emnet kan du opprette en ny egendefinert fellesvisning. Du kan også redigere en eksisterende visning.  
  
### <a name="create-a-new-view"></a>Opprett en ny visning  
  
1.  På [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)-området velger du **Modelldrevet** (nederst til venstre i navigasjonsruten).  

    ![Modelldrevet utformingsmodus](media/model-driven-switch.png)

    > [!IMPORTANT]
    > "Hvis utformingsmodusen **Modelldrevet** ikke er tilgjengelig, må du kanskje [opprette et miljø](https://docs.microsoft.com/powerapps/administrator/create-environment). 

2.  Utvid **Data**, velg **Enheter**, velg **Forretningsforbindelse**-enheten, og velg deretter **Visninger**-kategorien. 

3.  Velg **Legg til visning** på verktøylinjen.  

4.  I **Visningsegenskaper**-dialogboksen angir du et **Navn**, for eksempel **Forretningsforbindelser med 25 eller flere ansatte**, eventuelt en **beskrivelse** for visningen og velger deretter **OK**.

    > [!div class="mx-imgBorder"] 
    > ![Vis egenskaper](media/view-properties.png)
  
5.  Velg **Legg til kolonner** i den høyre ruten for fellesoppgaver, i dialogboksen **Legg til kolonner** velger du **Antall ansatte** og deretter **OK**.  

    > [!div class="mx-imgBorder"] 
    > ![Kolonnen Antall ansatte](media/column-no-employees.png)
  
6. I den høyre ruten for fellesoppgaver velger du **Rediger filtervilkår**, i dialogboksen Rediger filtervilkår velger du **Antall ansatte**, velger **Er større enn eller lik**, og skriver deretter inn **25**.  

    > [!div class="mx-imgBorder"] 
    > ![Redigere filtervilkår](media/edit-filter-criteria.png)

7.  Velg **OK** for å lukke dialogboksen **Rediger filtervilkår**, og velg deretter **Lagre og lukk** i visningsredigeringsprogrammet.  
  
8.  Legg merke til at visningen din nå er tilgjengelig fra **Visninger**-kategorien på PowerApps-området, noe som gjør det mulig å legge den til en app.
  
### <a name="edit-a-view"></a>Redigere en visning  
  
1.  Fra **Visninger**-kategorien på PowerApps-området velger du **Antall ansatte**-visningen.
  
2.  Endre **navnet** på visningen til **Antall ansatte med 25 eller flere ansatte i Arizona**, og velg deretter **OK**.  

3.  Velg **Legg til kolonner** i den høyre ruten for fellesoppgaver, i dialogboksen **Legg til kolonner** velger du **Adresse 1: Poststed** og deretter **OK**.  

4. I den høyre ruten for fellesoppgaver velger du **Rediger filtervilkår**, i dialogboksen Rediger filtervilkår legger du til en ny filtersetning. Velg **Adresse 2: Delstat/område**, velg **Er lik**, og angi deretter **Arizona**. 

    > [!div class="mx-imgBorder"] 
    > ![Adresse 2: Område](media/column-address-2-state.png)

5. Velg **OK** for å lukke dialogboksen **Rediger filtervilkår**, og velg deretter **Lagre og lukk** i visningsredigeringsprogrammet.  
  

## <a name="create-a-new-view-from-an-existing-view"></a>Opprette en ny visning fra en eksisterende visning  
 Følg fremgangsmåten for å redigere en visning, men velg **Lagre som** i stedet for **Lagre og Lukk**, og skriv inn et nytt **Navn** og en ny **Beskrivelse** for visningen.  
 
### <a name="next-steps"></a>Neste trinn
[Velge og konfigurere kolonner](choose-and-configure-columns.md)  
  
[Redigere filtervilkår](edit-filter-criteria.md)  
  
[Konfigurere sortering](configure-sorting.md)  
